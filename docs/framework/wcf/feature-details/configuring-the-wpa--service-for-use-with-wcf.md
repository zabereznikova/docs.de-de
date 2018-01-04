---
title: Konfigurieren des Windows-Prozessaktivierungsdiensts zur Verwendung mit Windows Communication Foundation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d50712e-53cd-4773-b8bc-a1e1aad66b78
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 12df9e3760774b4dc8d4e8f73a09df5e79c2453e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="configuring-the-windows-process-activation-service-for-use-with-windows-communication-foundation"></a>Konfigurieren des Windows-Prozessaktivierungsdiensts zur Verwendung mit Windows Communication Foundation
In diesem Thema werden die Schritte vorgestellt, mit denen der Windows-Prozessaktivierungsdienst (auch WAS für Windows Process Activation Service genannt) in [!INCLUDE[wv](../../../../includes/wv-md.md)] als Host für [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Dienste, die nicht über HTTP-Netzwerkprotokolle kommunizieren, konfiguriert wird. In den folgenden Abschnitten werden die für diese Konfiguration erforderlichen Schritte kurz beschrieben:  
  
-   Installieren Sie die (oder bestätigen Sie die Installation der) erforderlichen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Aktivierungskomponenten.  
  
-   Erstellen Sie eine WAS-Site mit den Netzwerkprotokollbindungen, die Sie verwenden möchten, oder fügen Sie einer vorhandenen Site eine neue Protokollbindung hinzu.  
  
-   Erstellen Sie eine Anwendung, die als Host der Dienste fungieren soll, und bereiten Sie diese Anwendung auf die Verwendung der erforderlichen Netzwerkprotokolle vor.  
  
-   Erstellen Sie einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst, der einen Nicht-HTTP-Endpunkt verfügbar macht.  
  
## <a name="configuring-a-site-with-non-http-bindings"></a>Konfigurieren einer Site mit Nicht-HTTP-Bindungen  
 Damit eine Nicht-HTTP-Bindung in WAS verwendet werden kann, muss die Sitebindung der WAS-Konfiguration hinzugefügt werden. Die WAS-Konfiguration wird in der Datei applicationHost.config im Verzeichnis %windir%\system32\inetsrv\config gespeichert. Diese Konfigurationsdatei wird sowohl für WAS als auch für IIS&#160;7.0 genutzt.  
  
 Bei der Datei applicationHost.config handelt es sich um eine XML-Textdatei, die mit jedem Standardtexteditor (wie Editor) geöffnet werden kann. Das Befehlszeilenkonfigurationsprogramm von [!INCLUDE[iisver](../../../../includes/iisver-md.md)] (appcmd.exe) wird jedoch zum Hinzufügen von Nicht-HTTP-Sitebindungen bevorzugt.  
  
 Mit dem folgenden Befehl wird mit „appcmd.exe“ eine net.tcp-Sitebindung der Standardwebsite hinzugefügt (der gesamte Befehl wird in eine Zeile eingegeben).  
  
```  
appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']  
```  
  
 Mit dem folgenden Befehl wird die neue net.tcp-Sitebindung der Standardwebsite hinzugefügt, indem die unten dargestellte Zeile in die Datei „applicationHost.config“ eingefügt wird.  
  
```xml  
<sites>  
    <site name="Default Web Site" id="1">  
        <bindings>  
            <binding protocol="HTTP" bindingInformation="*:80:" />  
            //The following line is added by the command.  
            <binding protocol="net.tcp" bindingInformation="808:*" />  
        </bindings>  
    </site>  
</sites>  
```  
  
## <a name="enabling-an-application-to-use-non-http-protocols"></a>Aktivieren der Verwendung von Nicht-HTTP-Protokollen auf Anwendungsebene  
 Sie können aktivieren oder deaktivieren einzelne Protocolsat Anwendungsebene. Der folgende Befehl veranschaulicht, wie die Protokolle HTTP und net.tcp für eine Anwendung aktiviert werden, die auf der `Default Web Site` ausgeführt wird.  
  
```  
appcmd.exe set app "Default Web Site/appOne" /enabledProtocols:net.tcp  
```  
  
 Die Liste der aktivierten Protokolle kann auch festgelegt werden, der \<ApplicationDefaults >-Element von der Website XML-Konfiguration in "applicationHost.config" gespeichert.  
  
 Der folgende XML-Code aus applicationHost.config veranschaulicht eine Site, die sowohl an HTTP als auch an Nicht-HTTP-Protokolle gebunden ist. Die zusätzliche Konfiguration, die zur Unterstützung von Nicht-HTTP-Protokollen erforderlich ist, wird durch Kommentare hervorgehoben.  
  
```xml  
<sites>  
    <site name="Default Web Site" id="1">  
    <application path="/">  
        <virtualDirectory path="/" physicalPath="D:\inetpub\wwwroot" />  
    </application>  
       <bindings>  
            //The following two lines are added by the command.  
            <binding protocol="HTTP" bindingInformation="*:80:" />  
            <binding protocol="net.tcp" bindingInformation="808:*" />  
       </bindings>  
    </site>  
    <siteDefaults>  
        <logFile   
        customLogPluginClsid="{FF160663-DE82-11CF-BC0A-00AA006111E0}"  
          directory="D:\inetpub\logs\LogFiles" />  
        <traceFailedRequestsLogging   
          directory="D:\inetpub\logs\FailedReqLogFiles" />  
    </siteDefaults>  
    <applicationDefaults   
      applicationPool="DefaultAppPool"   
      //The following line is inserted by the command.  
      enabledProtocols="http, net.tcp" />  
    <virtualDirectoryDefaults allowSubDirConfig="true" />  
</sites>  
```  
  
 Wenn Sie versuchen, einen Dienst mithilfe von WAS zur Aktivierung von Nicht-HTTP-Protokollen zu aktivieren, und WAS nicht installiert und konfiguriert ist, erhalten Sie möglicherweise folgende Fehlermeldung:  
  
```Output  
[InvalidOperationException: The protocol 'net.tcp' does not have an implementation of HostedTransportConfiguration type registered.]   System.ServiceModel.AsyncResult.End(IAsyncResult result) +15778592   System.ServiceModel.Activation.HostedHttpRequestAsyncResult.End(IAsyncResult result) +15698937   System.ServiceModel.Activation.HostedHttpRequestAsyncResult.ExecuteSynchronous(HttpApplication context, Boolean flowContext) +265   System.ServiceModel.Activation.HttpModule.ProcessRequest(Object sender, EventArgs e) +227   System.Web.SyncEventExecutionStep.System.Web.HttpApplication.IExecutionStep.Execute() +80   System.Web.HttpApplication.ExecuteStep(IExecutionStep step, Boolean& completedSynchronously) +171  
```  
  
 Wenn dieser Fehler angezeigt wird, stellen Sie sicher, dass WAS zur Aktivierung von Nicht-HTTP-Protokollen installiert und ordnungsgemäß konfiguriert ist. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Vorgehensweise: Installieren und Konfigurieren von WCF-Aktivierungskomponenten](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md).  
  
## <a name="building-a-wcf-service-that-uses-was-for-non-http-activation"></a>Erstellen eines WCF-Diensts, der WAS zur Aktivierung von Nicht-HTTP-Protokollen verwendet  
 Nachdem Sie die Schritte zum Installieren und konfigurieren Sie WAS ausführen (finden Sie unter [Vorgehensweise: Installieren und Konfigurieren von WCF-Aktivierungskomponenten](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md)), konfigurieren einen Dienst, um WAS für die Aktivierung ist vergleichbar mit der Konfiguration eines Diensts, der gehostet wird in IIS zu verwenden.  
  
 Ausführliche Anweisungen zum Erstellen von einem von WAS aktivierten [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Diensts [wie: Hosten eines WCF-Diensts in WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Hosting in Windows Process Activation Service (Hosten im Windows-Prozessaktivierungsdienst)](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md)  
 [Windows Server AppFabric-Hostingfunktionen](http://go.microsoft.com/fwlink/?LinkId=201276)
