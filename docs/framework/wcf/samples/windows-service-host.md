---
title: Windows-Diensthost
ms.date: 03/30/2017
helpviewer_keywords:
- NT Service
- NT Service Host Sample [Windows Communication Foundation]
ms.assetid: 1b2f45c5-2bed-4979-b0ee-8f9efcfec028
ms.openlocfilehash: 65797863fc8187ffebbcb660e9fb285bfa1aabd0
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48583853"
---
# <a name="windows-service-host"></a>Windows-Diensthost
Dieses Beispiel zeigt einen Windows Communication Foundation (WCF)-Dienst in einem verwalteten Windows-Dienst gehostet wird. Windows-Dienste gesteuert werden, verwenden das Applet "Dienste" in **Systemsteuerung** und konfiguriert werden können, um automatisch nach einem Systemneustart gestartet. Das Beispiel besteht aus einem Clientprogramm und einem Windows-Dienstprogramm. Der Dienst wird als EXE-Programm implementiert und enthält seinen eigenen Hostingcode. In anderen Hostumgebungen, z. B. WAS (Windows Process Activation Services, Windows-Prozessaktivierungsdienste) oder IIS (Internet Information Services, Internetinformationsdienste), müssen Sie keinen Hostcode schreiben.

> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.

> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WindowsService`  
  
 Nach dem Erstellen muss dieser Dienst mit dem Hilfsprogramm Installutil.exe wie jeder andere Windows-Dienst installiert werden. Wenn Sie Änderungen am Dienst vornehmen, müssen Sie ihn zuerst mit `installutil /u` deinstallieren. Die in diesem Beispiel enthaltenen Dateien Setup.bat und Cleanup.bat sind die Befehle zum Installieren und Starten bzw. zum Herunterfahren und Deinstallieren des Windows-Diensts. Der WCF-Dienst kann nur auf Clients reagieren, wenn der Windows-Dienst ausgeführt wird. Wenn Sie den Windows-Dienst beenden, mithilfe des Applets für Dienste von **Systemsteuerung** und den Client ausführen, eine <xref:System.ServiceModel.EndpointNotFoundException> Ausnahme tritt auf, wenn ein Client versucht, auf den Dienst zuzugreifen. Wenn Sie den Windows-Dienst neu starten und den Client erneut ausführen, ist Kommunikation erfolgreich.  
  
 Der Dienstcode enthält eine Installerklasse, eine WCF-Implementierung-Dienstklasse, die den ICalculator-Vertrag implementiert und eine Windows-Dienst-Klasse, die als Host für die Laufzeit fungiert. Dank der Installerklasse, die von <xref:System.Configuration.Install.Installer> vererbt ist, kann das Programm mit dem Tool Installutil.exe als ein NT-Dienst installiert werden. Die Dienstimplementierungsklasse, `WcfCalculatorService`, ist ein WCF-Dienst, der einen grundlegenden Dienstvertrag implementiert. Diesen WCF-Dienst gehostet wird, in einer Windows-Dienstklasse namens `WindowsCalculatorService`. Damit sich die Klasse als Windows-Dienst eignet, erbt sie von <xref:System.ServiceProcess.ServiceBase> und implementiert die <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29>-Methode und die<xref:System.ServiceProcess.ServiceBase.OnStop>-Methode. In <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> wird ein <xref:System.ServiceModel.ServiceHost>-Objekt für den `WcfCalculatorService`-Typ erstellt und geöffnet. In <xref:System.ServiceProcess.ServiceBase.OnStop> wird der ServiceHost durch Aufrufen der <xref:System.ServiceModel.Channels.CommunicationObject.Close%28System.TimeSpan%29>-Methode des <xref:System.ServiceModel.ServiceHost>-Objekts geschlossen. Die Basisadresse des Hosts erfolgt über die [ \<hinzufügen >](../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md) -Element, das ein untergeordnetes Element von [ \<BaseAddresses >](../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md), dies ist ein untergeordnetes Element des der [ \<Host >](../../../../docs/framework/configure-apps/file-schema/wcf/host.md) -Element, das ein untergeordnetes Element von der [ \<Service >](../../../../docs/framework/configure-apps/file-schema/wcf/service.md) Element.  
  
 Der Endpunkt, der definiert wird, verwendet die Basisadresse und einen [ \<WsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md). Das folgende Beispiel zeigt die Konfiguration der Basisadresse sowie den Endpunkt, der den CalculatorService verfügbar macht.  
  
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
  
1.  Stellen Sie sicher, dass Sie ausgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3.  Nachdem die Lösung erstellt wurde, führen Sie Setup.bat aus einer erhöhten Eingabeaufforderung von Visual Studio 2012, auf den Windows-Dienst, der mit dem Tool Installutil.exe zu installieren. Der Dienst sollte unter Dienste angezeigt werden.  
  
4.  Folgen Sie den Anweisungen, um das Beispiel in einer Konfiguration für die einzelnen-Computer oder computerübergreifend auszuführen, [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## <a name="see-also"></a>Siehe auch  
 [AppFabric-Hosting- und-persistenzbeispiele](https://go.microsoft.com/fwlink/?LinkId=193961)
