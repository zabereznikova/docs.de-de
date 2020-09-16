---
title: Konfigurieren des Windows-Prozessaktivierungsdiensts zur Verwendung mit Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 1d50712e-53cd-4773-b8bc-a1e1aad66b78
ms.openlocfilehash: 7dccfea990afff1d2aacd5e9714472e733684c33
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556602"
---
# <a name="configuring-the-windows-process-activation-service-for-use-with-windows-communication-foundation"></a><span data-ttu-id="e956c-102">Konfigurieren des Windows-Prozessaktivierungsdiensts zur Verwendung mit Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="e956c-102">Configuring the Windows Process Activation Service for Use with Windows Communication Foundation</span></span>
<span data-ttu-id="e956c-103">In diesem Thema werden die Schritte beschrieben, die zum Einrichten von Windows Process Activation Service (auch bekannt als was) in Windows Vista erforderlich sind, um Windows Communication Foundation (WCF)-Dienste zu hosten, die nicht über HTTP-Netzwerkprotokolle kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="e956c-103">This topic describes the steps required to set up Windows Process Activation Service (also known as WAS) in Windows Vista to host Windows Communication Foundation (WCF) services that do not communicate over HTTP network protocols.</span></span> <span data-ttu-id="e956c-104">In den folgenden Abschnitten werden die für diese Konfiguration erforderlichen Schritte kurz beschrieben:</span><span class="sxs-lookup"><span data-stu-id="e956c-104">The following sections outline the steps for this configuration:</span></span>  
  
- <span data-ttu-id="e956c-105">Installieren Sie die erforderlichen WCF-Aktivierungs Komponenten (oder bestätigen Sie die Installation).</span><span class="sxs-lookup"><span data-stu-id="e956c-105">Install (or confirm the installation of) the WCF activation components required.</span></span>  
  
- <span data-ttu-id="e956c-106">Erstellen Sie eine WAS-Site mit den Netzwerkprotokollbindungen, die Sie verwenden möchten, oder fügen Sie einer vorhandenen Site eine neue Protokollbindung hinzu.</span><span class="sxs-lookup"><span data-stu-id="e956c-106">Create a WAS site with the network protocol bindings you wish to use, or add a new protocol binding to an existing site.</span></span>  
  
- <span data-ttu-id="e956c-107">Erstellen Sie eine Anwendung, die als Host der Dienste fungieren soll, und bereiten Sie diese Anwendung auf die Verwendung der erforderlichen Netzwerkprotokolle vor.</span><span class="sxs-lookup"><span data-stu-id="e956c-107">Create an application to host your services and enable that application to use the required network protocols.</span></span>  
  
- <span data-ttu-id="e956c-108">Erstellen Sie einen WCF-Dienst, der einen nicht-HTTP-Endpunkt verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="e956c-108">Build a WCF service that exposes a non-HTTP endpoint.</span></span>  
  
## <a name="configuring-a-site-with-non-http-bindings"></a><span data-ttu-id="e956c-109">Konfigurieren einer Site mit Nicht-HTTP-Bindungen</span><span class="sxs-lookup"><span data-stu-id="e956c-109">Configuring a Site with Non-HTTP bindings</span></span>  
 <span data-ttu-id="e956c-110">Damit eine Nicht-HTTP-Bindung in WAS verwendet werden kann, muss die Sitebindung der WAS-Konfiguration hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="e956c-110">To use a non-HTTP binding with WAS, the site binding must be added to the WAS configuration.</span></span> <span data-ttu-id="e956c-111">Die WAS-Konfiguration wird in der Datei applicationHost.config im Verzeichnis %windir%\system32\inetsrv\config gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e956c-111">The configuration store for WAS is the applicationHost.config file, located in the %windir%\system32\inetsrv\config directory.</span></span> <span data-ttu-id="e956c-112">Diese Konfigurationsdatei wird sowohl für WAS als auch für IIS&#160;7.0 genutzt.</span><span class="sxs-lookup"><span data-stu-id="e956c-112">This configuration store is shared by both WAS and IIS 7.0.</span></span>  
  
 <span data-ttu-id="e956c-113">Bei der Datei applicationHost.config handelt es sich um eine XML-Textdatei, die mit jedem Standardtexteditor (wie Editor) geöffnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="e956c-113">applicationHost.config is an XML text file that can be opened with any standard text editor (such as Notepad).</span></span> <span data-ttu-id="e956c-114">Das IIS 7,0-Befehlszeilen-Konfigurationstool (appcmd.exe) ist jedoch die bevorzugte Methode, um nicht-HTTP-Site Bindungen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="e956c-114">However, the IIS 7.0 command-line configuration tool (appcmd.exe) is the preferred way to add non-HTTP site bindings.</span></span>  
  
 <span data-ttu-id="e956c-115">Mit dem folgenden Befehl wird mit appcmd.exe eine net.tcp-Sitebindung der Standardwebsite hinzugefügt (der gesamte Befehl wird in eine Zeile eingegeben).</span><span class="sxs-lookup"><span data-stu-id="e956c-115">The following command adds a net.tcp site binding to the default Web site using appcmd.exe (this command is entered as a single line).</span></span>  
  
```console  
appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']  
```  
  
 <span data-ttu-id="e956c-116">Mit dem folgenden Befehl wird die neue net.tcp-Sitebindung der Standardwebsite hinzugefügt, indem die unten dargestellte Zeile in die Datei „applicationHost.config“ eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="e956c-116">This command adds the new net.tcp binding to the default Web site by adding the line indicated below to the applicationHost.config file.</span></span>  
  
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
  
## <a name="enabling-an-application-to-use-non-http-protocols"></a><span data-ttu-id="e956c-117">Aktivieren der Verwendung von Nicht-HTTP-Protokollen auf Anwendungsebene</span><span class="sxs-lookup"><span data-stu-id="e956c-117">Enabling an Application to Use Non-HTTP Protocols</span></span>  
 <span data-ttu-id="e956c-118">Sie können einzelne Netzwerkprotokolle auf Anwendungsebene aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e956c-118">You can enable or disable individual network protocolsat the application level.</span></span> <span data-ttu-id="e956c-119">Der folgende Befehl veranschaulicht, wie die Protokolle HTTP und net.tcp für eine Anwendung aktiviert werden, die auf der `Default Web Site` ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e956c-119">The following command illustrates how to enable both the HTTP and net.tcp protocols for an application that runs in the `Default Web Site`.</span></span>  
  
```console  
appcmd.exe set app "Default Web Site/appOne" /enabledProtocols:net.tcp  
```  
  
 <span data-ttu-id="e956c-120">Die Liste der aktivierten Protokolle kann auch im \<applicationDefaults> -Element der in ApplicationHost.config gespeicherten XML-Konfiguration der Site festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="e956c-120">The list of enabled protocols can also be set in the \<applicationDefaults> element of the site’s XML configuration stored in ApplicationHost.config.</span></span>  
  
 <span data-ttu-id="e956c-121">Der folgende XML-Code aus applicationHost.config veranschaulicht eine Site, die sowohl an HTTP als auch an Nicht-HTTP-Protokolle gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="e956c-121">The following XML code from applicationHost.config illustrates a site bound to both HTTP and non-HTTP protocols.</span></span> <span data-ttu-id="e956c-122">Die zusätzliche Konfiguration, die zur Unterstützung von Nicht-HTTP-Protokollen erforderlich ist, wird durch Kommentare hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="e956c-122">The additional configuration required to support non-HTTP protocols is called out with comments.</span></span>  
  
```xml  
<sites>  
    <site name="Default Web Site" id="1">  
      <application path="/">  
        <virtualDirectory path="/" physicalPath="D:\inetpub\wwwroot" />  
      </application>  
      <bindings>  
            <!-- The following two lines are added by the command. -->
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
      <!-- The following line is inserted by the command. -->
      enabledProtocols="http, net.tcp" />  
    <virtualDirectoryDefaults allowSubDirConfig="true" />  
</sites>  
```  
  
 <span data-ttu-id="e956c-123">Wenn Sie versuchen, einen Dienst mithilfe von WAS zur Aktivierung von Nicht-HTTP-Protokollen zu aktivieren, und WAS nicht installiert und konfiguriert ist, erhalten Sie möglicherweise folgende Fehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="e956c-123">If you attempt to activate a service using WAS for Non-HTTP activation and you have not installed and configured WAS you may see the following error:</span></span>  
  
```output  
[InvalidOperationException: The protocol 'net.tcp' does not have an implementation of HostedTransportConfiguration type registered.]   System.ServiceModel.AsyncResult.End(IAsyncResult result) +15778592   System.ServiceModel.Activation.HostedHttpRequestAsyncResult.End(IAsyncResult result) +15698937   System.ServiceModel.Activation.HostedHttpRequestAsyncResult.ExecuteSynchronous(HttpApplication context, Boolean flowContext) +265   System.ServiceModel.Activation.HttpModule.ProcessRequest(Object sender, EventArgs e) +227   System.Web.SyncEventExecutionStep.System.Web.HttpApplication.IExecutionStep.Execute() +80   System.Web.HttpApplication.ExecuteStep(IExecutionStep step, Boolean& completedSynchronously) +171  
```  
  
 <span data-ttu-id="e956c-124">Wenn dieser Fehler angezeigt wird, stellen Sie sicher, dass WAS zur Aktivierung von Nicht-HTTP-Protokollen installiert und ordnungsgemäß konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="e956c-124">If you see this error ensure WAS for Non-HTTP Activation is installed and configured properly.</span></span> <span data-ttu-id="e956c-125">Weitere Informationen finden Sie unter Gewusst [wie: Installieren und Konfigurieren von WCF-Aktivierungs Komponenten](how-to-install-and-configure-wcf-activation-components.md).</span><span class="sxs-lookup"><span data-stu-id="e956c-125">For more information, see [How to: Install and Configure WCF Activation Components](how-to-install-and-configure-wcf-activation-components.md).</span></span>  
  
## <a name="building-a-wcf-service-that-uses-was-for-non-http-activation"></a><span data-ttu-id="e956c-126">Erstellen eines WCF-Diensts, der WAS zur Aktivierung von Nicht-HTTP-Protokollen verwendet</span><span class="sxs-lookup"><span data-stu-id="e956c-126">Building a WCF Service That Uses WAS for Non-HTTP activation</span></span>  
 <span data-ttu-id="e956c-127">Nachdem Sie die Schritte zum Installieren und Konfigurieren von was (siehe Gewusst [wie: Installieren und Konfigurieren von WCF-Aktivierungs Komponenten](how-to-install-and-configure-wcf-activation-components.md)) ausgeführt haben, ähnelt das Konfigurieren eines Dienstanbieter für die Aktivierung von was dem Konfigurieren eines Dienstanbieter, der in IIS gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="e956c-127">Once you perform the steps to install and configure WAS (see [How to: Install and Configure WCF Activation Components](how-to-install-and-configure-wcf-activation-components.md)), configuring a service to use WAS for activation is similar to configuring a service that is hosted in IIS.</span></span>  
  
 <span data-ttu-id="e956c-128">Ausführliche Anweisungen zum Aufbau eines was-aktivierten WCF-Diensts finden Sie unter Gewusst [wie: Hosten eines WCF-Diensts in was](how-to-host-a-wcf-service-in-was.md).</span><span class="sxs-lookup"><span data-stu-id="e956c-128">For detailed instructions about building a WAS-activated WCF service, see [How to: Host a WCF Service in WAS](how-to-host-a-wcf-service-in-was.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e956c-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e956c-129">See also</span></span>

- [<span data-ttu-id="e956c-130">Hosten in WAS (Windows Process Activation Service)</span><span class="sxs-lookup"><span data-stu-id="e956c-130">Hosting in Windows Process Activation Service</span></span>](hosting-in-windows-process-activation-service.md)
- <span data-ttu-id="e956c-131">[Windows Server AppFabric-Hostingfunktionen](/previous-versions/appfabric/ee677189(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="e956c-131">[Windows Server App Fabric Hosting Features](/previous-versions/appfabric/ee677189(v=azure.10))</span></span>
