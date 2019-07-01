---
title: Konfigurieren des Windows-Prozessaktivierungsdiensts zur Verwendung mit Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 1d50712e-53cd-4773-b8bc-a1e1aad66b78
ms.openlocfilehash: 7ab62bda5e579bcd80a7403d9af3a7e7f9836647
ms.sourcegitcommit: 2d42b7ae4252cfe1232777f501ea9ac97df31b63
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2019
ms.locfileid: "67487002"
---
# <a name="configuring-the-windows-process-activation-service-for-use-with-windows-communication-foundation"></a><span data-ttu-id="b4dfd-102">Konfigurieren des Windows-Prozessaktivierungsdiensts zur Verwendung mit Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="b4dfd-102">Configuring the Windows Process Activation Service for Use with Windows Communication Foundation</span></span>
<span data-ttu-id="b4dfd-103">In diesem Thema wird die erforderlichen Schritte zum Einrichten der Windows Process Activation Service (auch WAS genannt) [!INCLUDE[wv](../../../../includes/wv-md.md)] zum Hosten von Windows Communication Foundation (WCF) Dienste, die nicht über HTTP kommunizieren die Netzwerkprotokolle.</span><span class="sxs-lookup"><span data-stu-id="b4dfd-103">This topic describes the steps required to set up Windows Process Activation Service (also known as WAS) in [!INCLUDE[wv](../../../../includes/wv-md.md)] to host Windows Communication Foundation (WCF) services that do not communicate over HTTP network protocols.</span></span> <span data-ttu-id="b4dfd-104">In den folgenden Abschnitten werden die für diese Konfiguration erforderlichen Schritte kurz beschrieben:</span><span class="sxs-lookup"><span data-stu-id="b4dfd-104">The following sections outline the steps for this configuration:</span></span>  
  
- <span data-ttu-id="b4dfd-105">Installieren (oder bestätigen Sie die Installation von) die WCF-aktivierungskomponenten erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="b4dfd-105">Install (or confirm the installation of) the WCF activation components required.</span></span>  
  
- <span data-ttu-id="b4dfd-106">Erstellen Sie eine WAS-Site mit den Netzwerkprotokollbindungen, die Sie verwenden möchten, oder fügen Sie einer vorhandenen Site eine neue Protokollbindung hinzu.</span><span class="sxs-lookup"><span data-stu-id="b4dfd-106">Create a WAS site with the network protocol bindings you wish to use, or add a new protocol binding to an existing site.</span></span>  
  
- <span data-ttu-id="b4dfd-107">Erstellen Sie eine Anwendung, die als Host der Dienste fungieren soll, und bereiten Sie diese Anwendung auf die Verwendung der erforderlichen Netzwerkprotokolle vor.</span><span class="sxs-lookup"><span data-stu-id="b4dfd-107">Create an application to host your services and enable that application to use the required network protocols.</span></span>  
  
- <span data-ttu-id="b4dfd-108">Erstellen Sie einen WCF-Dienst, der einen nicht-HTTP-Endpunkt verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="b4dfd-108">Build a WCF service that exposes a non-HTTP endpoint.</span></span>  
  
## <a name="configuring-a-site-with-non-http-bindings"></a><span data-ttu-id="b4dfd-109">Konfigurieren einer Site mit Nicht-HTTP-Bindungen</span><span class="sxs-lookup"><span data-stu-id="b4dfd-109">Configuring a Site with Non-HTTP bindings</span></span>  
 <span data-ttu-id="b4dfd-110">Damit eine Nicht-HTTP-Bindung in WAS verwendet werden kann, muss die Sitebindung der WAS-Konfiguration hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="b4dfd-110">To use a non-HTTP binding with WAS, the site binding must be added to the WAS configuration.</span></span> <span data-ttu-id="b4dfd-111">Die WAS-Konfiguration wird in der Datei applicationHost.config im Verzeichnis %windir%\system32\inetsrv\config gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b4dfd-111">The configuration store for WAS is the applicationHost.config file, located in the %windir%\system32\inetsrv\config directory.</span></span> <span data-ttu-id="b4dfd-112">Diese Konfigurationsdatei wird sowohl für WAS als auch für IIS&#160;7.0 genutzt.</span><span class="sxs-lookup"><span data-stu-id="b4dfd-112">This configuration store is shared by both WAS and IIS 7.0.</span></span>  
  
 <span data-ttu-id="b4dfd-113">Bei der Datei applicationHost.config handelt es sich um eine XML-Textdatei, die mit jedem Standardtexteditor (wie Editor) geöffnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="b4dfd-113">applicationHost.config is an XML text file that can be opened with any standard text editor (such as Notepad).</span></span> <span data-ttu-id="b4dfd-114">IIS 7.0 Befehlszeilen-Konfigurationstool (appcmd.exe) ist jedoch die bevorzugte Methode für nicht-HTTP-sitebindungen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b4dfd-114">However, the IIS 7.0 command-line configuration tool (appcmd.exe) is the preferred way to add non-HTTP site bindings.</span></span>  
  
 <span data-ttu-id="b4dfd-115">Mit dem folgenden Befehl wird mit appcmd.exe eine net.tcp-Sitebindung der Standardwebsite hinzugefügt (der gesamte Befehl wird in eine Zeile eingegeben).</span><span class="sxs-lookup"><span data-stu-id="b4dfd-115">The following command adds a net.tcp site binding to the default Web site using appcmd.exe (this command is entered as a single line).</span></span>  
  
```console  
appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']  
```  
  
 <span data-ttu-id="b4dfd-116">Mit dem folgenden Befehl wird die neue net.tcp-Sitebindung der Standardwebsite hinzugefügt, indem die unten dargestellte Zeile in die Datei „applicationHost.config“ eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="b4dfd-116">This command adds the new net.tcp binding to the default Web site by adding the line indicated below to the applicationHost.config file.</span></span>  
  
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
  
## <a name="enabling-an-application-to-use-non-http-protocols"></a><span data-ttu-id="b4dfd-117">Aktivieren der Verwendung von Nicht-HTTP-Protokollen auf Anwendungsebene</span><span class="sxs-lookup"><span data-stu-id="b4dfd-117">Enabling an Application to Use Non-HTTP Protocols</span></span>  
 <span data-ttu-id="b4dfd-118">Sie können aktivieren oder deaktivieren einzelne Protocolsat Anwendungsebene.</span><span class="sxs-lookup"><span data-stu-id="b4dfd-118">You can enable or disable individual network protocolsat the application level.</span></span> <span data-ttu-id="b4dfd-119">Der folgende Befehl veranschaulicht, wie die Protokolle HTTP und net.tcp für eine Anwendung aktiviert werden, die auf der `Default Web Site` ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b4dfd-119">The following command illustrates how to enable both the HTTP and net.tcp protocols for an application that runs in the `Default Web Site`.</span></span>  
  
```console  
appcmd.exe set app "Default Web Site/appOne" /enabledProtocols:net.tcp  
```  
  
 <span data-ttu-id="b4dfd-120">Die Liste aktivierter Protokolle kann auch festgelegt werden, der \<ApplicationDefaults >-Element der XML--Konfiguration des Standorts in der Datei "applicationHost.config" gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b4dfd-120">The list of enabled protocols can also be set in the \<applicationDefaults> element of the site’s XML configuration stored in ApplicationHost.config.</span></span>  
  
 <span data-ttu-id="b4dfd-121">Der folgende XML-Code aus applicationHost.config veranschaulicht eine Site, die sowohl an HTTP als auch an Nicht-HTTP-Protokolle gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="b4dfd-121">The following XML code from applicationHost.config illustrates a site bound to both HTTP and non-HTTP protocols.</span></span> <span data-ttu-id="b4dfd-122">Die zusätzliche Konfiguration, die zur Unterstützung von Nicht-HTTP-Protokollen erforderlich ist, wird durch Kommentare hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="b4dfd-122">The additional configuration required to support non-HTTP protocols is called out with comments.</span></span>  
  
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
  
 <span data-ttu-id="b4dfd-123">Wenn Sie versuchen, einen Dienst mithilfe von WAS zur Aktivierung von Nicht-HTTP-Protokollen zu aktivieren, und WAS nicht installiert und konfiguriert ist, erhalten Sie möglicherweise folgende Fehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="b4dfd-123">If you attempt to activate a service using WAS for Non-HTTP activation and you have not installed and configured WAS you may see the following error:</span></span>  
  
```output  
[InvalidOperationException: The protocol 'net.tcp' does not have an implementation of HostedTransportConfiguration type registered.]   System.ServiceModel.AsyncResult.End(IAsyncResult result) +15778592   System.ServiceModel.Activation.HostedHttpRequestAsyncResult.End(IAsyncResult result) +15698937   System.ServiceModel.Activation.HostedHttpRequestAsyncResult.ExecuteSynchronous(HttpApplication context, Boolean flowContext) +265   System.ServiceModel.Activation.HttpModule.ProcessRequest(Object sender, EventArgs e) +227   System.Web.SyncEventExecutionStep.System.Web.HttpApplication.IExecutionStep.Execute() +80   System.Web.HttpApplication.ExecuteStep(IExecutionStep step, Boolean& completedSynchronously) +171  
```  
  
 <span data-ttu-id="b4dfd-124">Wenn dieser Fehler angezeigt wird, stellen Sie sicher, dass WAS zur Aktivierung von Nicht-HTTP-Protokollen installiert und ordnungsgemäß konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="b4dfd-124">If you see this error ensure WAS for Non-HTTP Activation is installed and configured properly.</span></span> <span data-ttu-id="b4dfd-125">Weitere Informationen finden Sie unter [Vorgehensweise: Installieren und Konfigurieren von WCF-Aktivierungskomponenten](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md).</span><span class="sxs-lookup"><span data-stu-id="b4dfd-125">For more information, see [How to: Install and Configure WCF Activation Components](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md).</span></span>  
  
## <a name="building-a-wcf-service-that-uses-was-for-non-http-activation"></a><span data-ttu-id="b4dfd-126">Erstellen eines WCF-Diensts, der WAS zur Aktivierung von Nicht-HTTP-Protokollen verwendet</span><span class="sxs-lookup"><span data-stu-id="b4dfd-126">Building a WCF Service That Uses WAS for Non-HTTP activation</span></span>  
 <span data-ttu-id="b4dfd-127">Sobald Sie die Schritte zum Installieren und Konfigurieren von WAS (siehe [wie: Installieren und Konfigurieren von WCF-Aktivierungskomponenten](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md)), konfigurieren einen Dienst, um WAS für Aktivierung ähnelt der Konfiguration von einem gehosteten Diensts, in IIS zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b4dfd-127">Once you perform the steps to install and configure WAS (see [How to: Install and Configure WCF Activation Components](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md)), configuring a service to use WAS for activation is similar to configuring a service that is hosted in IIS.</span></span>  
  
 <span data-ttu-id="b4dfd-128">Ausführliche Anweisungen zum Erstellen eines WAS-aktivierten WCF-Diensts finden Sie unter [Vorgehensweise: Hosten eines WCF-Diensts in WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md).</span><span class="sxs-lookup"><span data-stu-id="b4dfd-128">For detailed instructions about building a WAS-activated WCF service, see [How to: Host a WCF Service in WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4dfd-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4dfd-129">See also</span></span>

- [<span data-ttu-id="b4dfd-130">Hosting in Windows Process Activation Service (Hosten im Windows-Prozessaktivierungsdienst)</span><span class="sxs-lookup"><span data-stu-id="b4dfd-130">Hosting in Windows Process Activation Service</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md)
- [<span data-ttu-id="b4dfd-131">Windows Server AppFabric-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="b4dfd-131">Windows Server App Fabric Hosting Features</span></span>](https://go.microsoft.com/fwlink/?LinkId=201276)
