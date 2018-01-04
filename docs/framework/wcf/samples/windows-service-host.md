---
title: Windows-Diensthost
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- NT Service
- NT Service Host Sample [Windows Communication Foundation]
ms.assetid: 1b2f45c5-2bed-4979-b0ee-8f9efcfec028
caps.latest.revision: "40"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3634d5c14b0d0fcc0113296dec4843585625698d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="windows-service-host"></a>Windows-Diensthost
Dieses Beispiel zeigt einen [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Dienst, der in einem verwalteten Windows-Dienst gehostet wird. Windows-Dienste gesteuert werden, verwenden das Applet "Dienste" in **Systemsteuerung** und kann so konfiguriert werden, dass nach einem Neustart des Systems automatisch starten. Das Beispiel besteht aus einem Clientprogramm und einem Windows-Dienstprogramm. Der Dienst wird als EXE-Programm implementiert und enthält seinen eigenen Hostingcode. In anderen Hostumgebungen, z. B. WAS (Windows Process Activation Services, Windows-Prozessaktivierungsdienste) oder IIS (Internet Information Services, Internetinformationsdienste), müssen Sie keinen Hostcode schreiben.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WindowsService`  
  
 Nach dem Erstellen muss dieser Dienst mit dem Hilfsprogramm Installutil.exe wie jeder andere Windows-Dienst installiert werden. Wenn Sie Änderungen am Dienst vornehmen, müssen Sie ihn zuerst mit `installutil /u` deinstallieren. Die in diesem Beispiel enthaltenen Dateien Setup.bat und Cleanup.bat sind die Befehle zum Installieren und Starten bzw. zum Herunterfahren und Deinstallieren des Windows-Diensts. Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst kann Clients nur dann antworten, wenn der Windows-Dienst ausgeführt wird. Wenn Sie den Windows-Dienst beenden, mithilfe des Dienste-Applets aus **Systemsteuerung** und führen Sie den Client ein <xref:System.ServiceModel.EndpointNotFoundException> Ausnahme tritt auf, wenn ein Client versucht, auf den Dienst zuzugreifen. Wenn Sie den Windows-Dienst neu starten und den Client erneut ausführen, ist Kommunikation erfolgreich.  
  
 Der Dienstcode enthält eine Installerklasse, eine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienstimplementierungsklasse, die den Icalculator-Vertrag implementiert, und eine Windows-Dienstklasse, die als Laufzeithost fungiert. Dank der Installerklasse, die von <xref:System.Configuration.Install.Installer> vererbt ist, kann das Programm mit dem Tool Installutil.exe als ein NT-Dienst installiert werden. Die Dienstimplementierungsklasse, `WcfCalculatorService`, ist ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst, der einen grundlegenden Dienstvertrag implementiert. Dieser [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst ist in einer Windows-Dienstklasse namens `WindowsCalculatorService` gehostet. Damit sich die Klasse als Windows-Dienst eignet, erbt sie von <xref:System.ServiceProcess.ServiceBase> und implementiert die <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29>-Methode und die<xref:System.ServiceProcess.ServiceBase.OnStop>-Methode. In <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> wird ein <xref:System.ServiceModel.ServiceHost>-Objekt für den `WcfCalculatorService`-Typ erstellt und geöffnet. In <xref:System.ServiceProcess.ServiceBase.OnStop> wird der ServiceHost durch Aufrufen der <xref:System.ServiceModel.Channels.CommunicationObject.Close%28System.TimeSpan%29>-Methode des <xref:System.ServiceModel.ServiceHost>-Objekts geschlossen. Die Basisadresse des Hosts wird konfiguriert, mit der [ \<hinzufügen >](../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md) -Element, das ein untergeordnetes Element ist der [ \<BaseAddresses >](../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md), ist ein untergeordnetes Element eines der [ \<Host >](../../../../docs/framework/configure-apps/file-schema/wcf/host.md) Elements, d. ein untergeordnetes Element h. von der [ \<Service >](../../../../docs/framework/configure-apps/file-schema/wcf/service.md) Element.  
  
 Der Endpunkt, der definiert ist, verwendet die Basisadresse und einen [ \<WsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md). Das folgende Beispiel zeigt die Konfiguration der Basisadresse sowie den Endpunkt, der den CalculatorService verfügbar macht.  
  
```xml  
<services>  
  <service name="Microsoft.ServiceModel.Samples.WcfCalculatorService"  
           behaviorConfiguration="CalculatorServiceBehavior">  
    <host>  
      <baseAddresses>  
        <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
      </baseAddresses>  
    </host>  
    <!-- This endpoint is exposed at the base address provided by host: http://localhost:8000/ServiceModelSamples/service.  -->  
    <endpoint address=""  
              binding="wsHttpBinding"  
              contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    ...  
  </service>  
</services>  
```  
  
 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Dienst- und Clientkonsolenfenster angezeigt. Drücken Sie die EINGABETASTE in den einzelnen Konsolenfenstern, um den Dienst und den Client zu schließen.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3.  Nachdem die Projektmappe erstellt wurde, führen Sie Setup.bat an einer [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]-Eingabeaufforderung mit erhöhten Rechten aus, um den Windows-Dienst mit dem Tool Installutil.exe zu installieren. Der Dienst sollte unter Dienste angezeigt werden.  
  
4.  Um das Beispiel in einer Einzelcomputer- oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## <a name="see-also"></a>Siehe auch  
 [AppFabric-Hosting und Persistenzbeispiele](http://go.microsoft.com/fwlink/?LinkId=193961)
