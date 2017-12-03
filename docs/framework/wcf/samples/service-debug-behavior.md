---
title: Debugverhalten von Diensten
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d8fd3fb-dc39-427a-8235-336a7e7162ba
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cb609857dbe3aaee0014e284d80af3b93ac395e5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="service-debug-behavior"></a>Debugverhalten von Diensten
In diesem Beispiel wird veranschaulicht, wie die Einstellungen für das Debugverhalten von Diensten konfiguriert werden können. Das Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md), implementiert die `ICalculator` Dienstvertrag. Dieses Beispiel definiert das Debugverhalten von Diensten explizit in der Konfigurationsdatei. Das Debugverhalten kann auch zwingend im Code definiert werden.  
  
 In diesem Beispiel ist der Client eine Konsolenanwendung (.exe), und der Dienst wird von IIS (Internet Information Services, Internetinformationsdienste) gehostet.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Die Datei Web.config für den Server definiert das Debugverhalten des Diensts, um die Hilfeseiten und die Behandlung von Ausnahmen zu aktivieren, wie im folgenden Beispiel dargestellt.  
  
```xml  
<behaviors>  
     <serviceBehaviors>  
         <behavior name="CalculatorServiceBehavior">  
         <!-- WARNING: Setting includeExceptionDetailInFaults = "True" could result in leaking secured server information to the client.-->  
         <!-- Please set this to false when deploying -->  
             <serviceDebug includeExceptionDetailInFaults="True" httpHelpPageEnabled="True"/>  
         </behavior>  
     </serviceBehaviors>  
</behaviors>  
```  
  
 [\<ServiceDebug >](../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md) ist das Konfigurationselement, das Ändern der Debug-dienstverhaltenseigenschaften ermöglicht. Der Benutzer kann dieses Verhalten ändern, um Folgendes zu erreichen:  
  
-   Dadurch kann der Dienst Ausnahmen zurückgeben, die von der Anwendung ausgelöst werden, auch wenn die Ausnahmen nicht mit <xref:System.ServiceModel.FaultContractAttribute> deklariert sind. `includeExceptionDetailInFaults` wird dazu auf `true` festgelegt. Diese Einstellung ist in Debuggingfällen hilfreich, in denen der Server eine unerwartete Ausnahme ausgibt.  
  
    > [!IMPORTANT]
    >  Es ist nicht sicher, diese Einstellung in einer Produktionsumgebung zu aktivieren. Eine unerwartete Ausnahme des Servers besitzt möglicherweise Informationen, die nicht für den Client bestimmt sind. Wenn `includeExceptionDetailsInFaults` auf `true` festgelegt ist, kann es möglicherweise zu Informationsverlusten kommen.  
  
-   Die [ \<ServiceDebug >](../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md) können auch einen Benutzer aktivieren oder deaktivieren die Seite "Hilfe". Jeder Dienst kann optional eine Hilfeseite verfügbar machen, die Informationen zum Dienst enthält, einschließlich des Endpunkts, um WSDL für den Dienst abzurufen. Dies kann durch Festlegen von `httpHelpPageEnabled` auf `true` aktiviert werden. Dadurch kann die Hilfeseite an eine GET-Anforderung der Basisadresse des Diensts zurückgegeben werden. Durch Festlegen des Attributs `httpHelpPageUrl` können Sie diese Adresse ändern. Sie können dies sichern, indem Sie HTTPS statt HTTP verwenden. Legen Sie dazu `httpsHelpPageEnabled` auf `httpsHelpPageUrl` fest.  
  
 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt. Die ersten drei Vorgänge (Add, Subtract und Multiply) müssen erfolgreich sein. Der letzte Vorgang ("divide") schlägt mit einer Ausnahme, der Division durch 0 (null), fehl.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3.  Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\ServiceDebug`  
  
## <a name="see-also"></a>Siehe auch
