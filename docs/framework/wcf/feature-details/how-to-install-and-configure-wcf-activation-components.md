---
title: 'Vorgehensweise: Installieren und Konfigurieren von WCF-Aktivierungskomponenten'
ms.date: 03/30/2017
helpviewer_keywords:
- HTTP activation [WCF]
ms.assetid: 33a7054a-73ec-464d-83e5-b203aeded658
ms.openlocfilehash: 1141bd8344887990ddd8646eba9d25c5d9a4287d
ms.sourcegitcommit: 2d42b7ae4252cfe1232777f501ea9ac97df31b63
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2019
ms.locfileid: "67487051"
---
# <a name="how-to-install-and-configure-wcf-activation-components"></a><span data-ttu-id="c263f-102">Vorgehensweise: Installieren und Konfigurieren von WCF-Aktivierungskomponenten</span><span class="sxs-lookup"><span data-stu-id="c263f-102">How to: Install and Configure WCF Activation Components</span></span>
<span data-ttu-id="c263f-103">Dieses Thema beschreibt die erforderlichen Schritte zum Einrichten der Windows Process Activation Service (auch bekannt als "WAS") auf [!INCLUDE[wv](../../../../includes/wv-md.md)] zum Hosten von Windows Communication Foundation (WCF) Dienste, die nicht über HTTP kommunizieren die Netzwerkprotokolle.</span><span class="sxs-lookup"><span data-stu-id="c263f-103">This topic describes the steps required to set up Windows Process Activation Service (also known as WAS) on [!INCLUDE[wv](../../../../includes/wv-md.md)] to host Windows Communication Foundation (WCF) services that do not communicate over HTTP network protocols.</span></span> <span data-ttu-id="c263f-104">In den folgenden Abschnitten werden die für diese Konfiguration erforderlichen Schritte kurz beschrieben:</span><span class="sxs-lookup"><span data-stu-id="c263f-104">The following sections outline the steps for this configuration:</span></span>  
  
- <span data-ttu-id="c263f-105">Installieren (oder bestätigen Sie die Installation von) die WCF-aktivierungskomponenten.</span><span class="sxs-lookup"><span data-stu-id="c263f-105">Install (or confirm the installation of) the WCF activation components.</span></span>  
  
- <span data-ttu-id="c263f-106">Konfigurieren Sie WAS, sodass Nicht-HTTP-Protokolle unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="c263f-106">Configure WAS to support a non-HTTP protocol.</span></span> <span data-ttu-id="c263f-107">Mit den folgenden Schritten wird [!INCLUDE[wv](../../../../includes/wv-md.md)] für die TCP-Aktivierung konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="c263f-107">The following procedure configures [!INCLUDE[wv](../../../../includes/wv-md.md)] for TCP activation.</span></span>  
  
 <span data-ttu-id="c263f-108">Nach der Installation und Konfiguration von WAS finden Sie [Vorgehensweise: Hosten eines WCF-Diensts in WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md) für die Prozeduren zum Erstellen eines WCF-Diensts, die einen nicht-HTTP-Endpunkt verfügbar macht, der mit WAS arbeitet.</span><span class="sxs-lookup"><span data-stu-id="c263f-108">After installing and configuring WAS, see [How to: Host a WCF Service in WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md) for the procedures to create a WCF service that exposes an non-HTTP endpoint that employs WAS.</span></span>  
  
### <a name="to-install-the-wcf-non-http-activation-components"></a><span data-ttu-id="c263f-109">So installieren Sie die WCF-Aktivierungskomponenten für andere Protokolle als HTTP</span><span class="sxs-lookup"><span data-stu-id="c263f-109">To install the WCF non-HTTP activation components</span></span>  
  
1. <span data-ttu-id="c263f-110">Klicken Sie auf die **starten** Schaltfläche, und klicken Sie dann auf **Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="c263f-110">Click the **Start** button, and then click **Control Panel**.</span></span>  
  
2. <span data-ttu-id="c263f-111">Klicken Sie auf **Programme**, und klicken Sie dann auf **Programme und Funktionen**.</span><span class="sxs-lookup"><span data-stu-id="c263f-111">Click **Programs**, and then click **Programs and Features**.</span></span>  
  
3. <span data-ttu-id="c263f-112">Auf der **Aufgaben** Menü klicken Sie auf **Aktivieren von Windows-Funktionen ein- oder ausschalten**.</span><span class="sxs-lookup"><span data-stu-id="c263f-112">On the **Tasks** menu, click **Turn Windows features on or off**.</span></span>  
  
4. <span data-ttu-id="c263f-113">Suchen Sie den WinFX-Knoten, wählen aus, und erweitern Sie ihn dann.</span><span class="sxs-lookup"><span data-stu-id="c263f-113">Find the WinFX node, select and then expand it.</span></span>  
  
5. <span data-ttu-id="c263f-114">Wählen Sie die **WCF-Aktivierungskomponenten für nicht-HTTP-** und speichern Sie die Einstellung.</span><span class="sxs-lookup"><span data-stu-id="c263f-114">Select the **WCF Non-Http Activation Components** box and save the setting.</span></span>  
  
### <a name="to-configure-the-was-to-support-tcp-activation"></a><span data-ttu-id="c263f-115">So konfigurieren Sie den WAS, sodass die TCP-Aktivierung unterstützt wird</span><span class="sxs-lookup"><span data-stu-id="c263f-115">To configure the WAS to support TCP activation</span></span>  
  
1. <span data-ttu-id="c263f-116">Zur Unterstützung der net.tcp-Aktivierung muss die Standardwebsite zuerst an einen net.tcp-Port gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="c263f-116">To support net.tcp activation, the default Web site must first be bound to a net.tcp port.</span></span> <span data-ttu-id="c263f-117">Sie erreichen dies, indem Sie Appcmd.exe, die mit der IIS 7.0-verwaltungstoolset installiert wird.</span><span class="sxs-lookup"><span data-stu-id="c263f-117">You can do this by using Appcmd.exe, which is installed with the IIS 7.0 management toolset.</span></span> <span data-ttu-id="c263f-118">Führen Sie in einem Eingabeaufforderungsfenster auf Administratorebene den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="c263f-118">In an administrator-level Command Prompt window, run the following command.</span></span>  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="c263f-119">Dieser Befehl ist eine einzelne Textzeile.</span><span class="sxs-lookup"><span data-stu-id="c263f-119">This command is a single line of text.</span></span> <span data-ttu-id="c263f-120">Mit dem Befehl wird eine neue net.tcp-Sitebindung der Standardwebsite hinzugefügt, die TCP-Anschluss 808 mit jedem beliebigen Hostnamen überwacht.</span><span class="sxs-lookup"><span data-stu-id="c263f-120">This command adds a net.tcp site binding to the default Web site listening on TCP port 808 with any host name.</span></span>  
  
2. <span data-ttu-id="c263f-121">Alle Anwendungen innerhalb einer Site nutzen zwar eine gemeinsame net.tcp-Bindung, aber jede Anwendung kann die net.tcp-Unterstützung unabhängig von den anderen Anwendungen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c263f-121">Although all applications within a site share a common net.tcp binding, each application can enable net.tcp support individually.</span></span> <span data-ttu-id="c263f-122">Um net.tcp für die Anwendung zu aktivieren, führen Sie den folgenden Befehl in einem Eingabeaufforderungsfenster auf Administratorebene aus.</span><span class="sxs-lookup"><span data-stu-id="c263f-122">To enable net.tcp for the application, run the following command from an administrator-level command prompt.</span></span>  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set app   
    "Default Web Site/<WCF Application>" /enabledProtocols:http,net.tcp  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="c263f-123">Dieser Befehl ist eine einzelne Textzeile.</span><span class="sxs-lookup"><span data-stu-id="c263f-123">This command is a single line of text.</span></span> <span data-ttu-id="c263f-124">Mit diesem Befehl wird die /\<*WCF-Anwendung*> Anwendung zugegriffen werden kann mit beiden `http://localhost/<WCF Application>` und `net.tcp://localhost/<WCF Application>`.</span><span class="sxs-lookup"><span data-stu-id="c263f-124">This command enables the /\<*WCF Application*> application to be accessed using both `http://localhost/<WCF Application>` and `net.tcp://localhost/<WCF Application>`.</span></span>
  
     <span data-ttu-id="c263f-125">Entfernen Sie die net.tcp-Sitebindung, die für dieses Beispiel hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="c263f-125">Remove the net.tcp site binding you added for this sample.</span></span>  
  
     <span data-ttu-id="c263f-126">Zur Vereinfachung sind die folgenden beiden Schritte in einer Batchdatei namens RemoveNetTcpSiteBinding.cmd implementiert, die sich im Beispielverzeichnis befindet.</span><span class="sxs-lookup"><span data-stu-id="c263f-126">As a convenience, the following two steps are implemented in a batch file called RemoveNetTcpSiteBinding.cmd located in the sample directory.</span></span>  
  
    1. <span data-ttu-id="c263f-127">Entfernen Sie net.tcp aus der Liste aktivierter Protokolle, indem Sie den folgenden Befehl in einem Eingabeaufforderungsfenster auf Administratorebene ausführen.</span><span class="sxs-lookup"><span data-stu-id="c263f-127">Remove net.tcp from the list of enabled protocols by running the following command in an administrator-level Command Prompt window.</span></span>  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set app   
        "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="c263f-128">Dieser Befehl ist eine einzelne Textzeile.</span><span class="sxs-lookup"><span data-stu-id="c263f-128">This command is a single line of text.</span></span>  
  
    2. <span data-ttu-id="c263f-129">Entfernen Sie die net.tcp-Sitebindung, indem Sie den folgenden Befehl in einem Eingabeaufforderungsfenster auf Administratorebene ausführen:</span><span class="sxs-lookup"><span data-stu-id="c263f-129">Remove the net.tcp site binding by running the following command in an elevated Command Prompt window:</span></span>  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
        --bindings.[protocol='net.tcp',bindingInformation='808:*']  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="c263f-130">Dieser Befehl ist eine einzelne Textzeile.</span><span class="sxs-lookup"><span data-stu-id="c263f-130">This command is a single line of text.</span></span>  
  
### <a name="to-remove-nettcp-from-the-list-of-enabled-protocols"></a><span data-ttu-id="c263f-131">So entfernen Sie net.tcp aus der Liste aktivierter Protokolle</span><span class="sxs-lookup"><span data-stu-id="c263f-131">To remove net.tcp from the list of enabled protocols</span></span>  
  
1. <span data-ttu-id="c263f-132">Um net.tcp aus der Liste aktivierter Protokolle zu entfernen, führen Sie den folgenden Befehl in einem Eingabeaufforderungsfenster auf Administratorebene aus.</span><span class="sxs-lookup"><span data-stu-id="c263f-132">To remove net.tcp from the list of enabled protocols, run the following command in an administrator-level Command Prompt window.</span></span>  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="c263f-133">Dieser Befehl ist eine einzelne Textzeile.</span><span class="sxs-lookup"><span data-stu-id="c263f-133">This command is a single line of text.</span></span>  
  
### <a name="to-remove-the-nettcp-site-binding"></a><span data-ttu-id="c263f-134">So entfernen Sie die net.tcp-Bindung</span><span class="sxs-lookup"><span data-stu-id="c263f-134">To remove the net.tcp site binding</span></span>  
  
1. <span data-ttu-id="c263f-135">Um die net.tcp-Sitebindung zu entfernen, führen Sie den folgenden Befehl in einem Eingabeaufforderungsfenster auf Administratorebene aus.</span><span class="sxs-lookup"><span data-stu-id="c263f-135">To remove the net.tcp site binding run the following command in an administrator-level Command Prompt window.</span></span>  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
    -bindings.[protocol='net.tcp',bindingInformation='808:*']  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="c263f-136">Dieser Befehl ist eine einzelne Textzeile.</span><span class="sxs-lookup"><span data-stu-id="c263f-136">This command is a single line of text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c263f-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c263f-137">See also</span></span>

- [<span data-ttu-id="c263f-138">TCP-Aktivierung</span><span class="sxs-lookup"><span data-stu-id="c263f-138">TCP Activation</span></span>](../../../../docs/framework/wcf/samples/tcp-activation.md)
- [<span data-ttu-id="c263f-139">MSMQ-Aktivierung</span><span class="sxs-lookup"><span data-stu-id="c263f-139">MSMQ Activation</span></span>](../../../../docs/framework/wcf/samples/msmq-activation.md)
- [<span data-ttu-id="c263f-140">NamedPipe-Aktivierung</span><span class="sxs-lookup"><span data-stu-id="c263f-140">NamedPipe Activation</span></span>](../../../../docs/framework/wcf/samples/namedpipe-activation.md)
- [<span data-ttu-id="c263f-141">Windows Server AppFabric-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="c263f-141">Windows Server App Fabric Hosting Features</span></span>](https://go.microsoft.com/fwlink/?LinkId=201276)
