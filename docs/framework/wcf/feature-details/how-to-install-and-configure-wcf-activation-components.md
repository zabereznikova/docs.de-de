---
title: 'Gewusst wie: Installieren und Konfigurieren von WCF-Aktivierungskomponenten'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: HTTP activation [WCF]
ms.assetid: 33a7054a-73ec-464d-83e5-b203aeded658
caps.latest.revision: "16"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 77dec85ee12250080fc487d120749892a148ef17
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-install-and-configure-wcf-activation-components"></a><span data-ttu-id="d1e3e-102">Gewusst wie: Installieren und Konfigurieren von WCF-Aktivierungskomponenten</span><span class="sxs-lookup"><span data-stu-id="d1e3e-102">How to: Install and Configure WCF Activation Components</span></span>
<span data-ttu-id="d1e3e-103">In diesem Thema werden die Schritte vorgestellt, mit denen der Windows-Prozessaktivierungsdienst (auch WAS für Windows Process Activation Service genannt) in [!INCLUDE[wv](../../../../includes/wv-md.md)] als Host für [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Dienste, die nicht über HTTP-Netzwerkprotokolle kommunizieren, konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="d1e3e-103">This topic describes the steps required to set up Windows Process Activation Service (also known as WAS) on [!INCLUDE[wv](../../../../includes/wv-md.md)] to host [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] services that do not communicate over HTTP network protocols.</span></span> <span data-ttu-id="d1e3e-104">In den folgenden Abschnitten werden die für diese Konfiguration erforderlichen Schritte kurz beschrieben:</span><span class="sxs-lookup"><span data-stu-id="d1e3e-104">The following sections outline the steps for this configuration:</span></span>  
  
-   <span data-ttu-id="d1e3e-105">Installieren Sie die (oder bestätigen Sie die Installation der) [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Aktivierungskomponenten.</span><span class="sxs-lookup"><span data-stu-id="d1e3e-105">Install (or confirm the installation of) the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] activation components.</span></span>  
  
-   <span data-ttu-id="d1e3e-106">Konfigurieren Sie WAS, sodass Nicht-HTTP-Protokolle unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="d1e3e-106">Configure WAS to support a non-HTTP protocol.</span></span> <span data-ttu-id="d1e3e-107">Mit den folgenden Schritten wird [!INCLUDE[wv](../../../../includes/wv-md.md)] für die TCP-Aktivierung konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="d1e3e-107">The following procedure configures [!INCLUDE[wv](../../../../includes/wv-md.md)] for TCP activation.</span></span>  
  
 <span data-ttu-id="d1e3e-108">Nach dem Installieren und Konfigurieren von WAS, finden Sie unter [wie: Hosten eines WCF-Diensts in WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md) für die Vorgehensweise zum Erstellen einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Dienst, der einen nicht-HTTP-Endpunkt verfügbar macht, von dem WAS verwendet.</span><span class="sxs-lookup"><span data-stu-id="d1e3e-108">After installing and configuring WAS, see [How to: Host a WCF Service in WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md) for the procedures to create a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service that exposes an non-HTTP endpoint that employs WAS.</span></span>  
  
### <a name="to-install-the-wcf-non-http-activation-components"></a><span data-ttu-id="d1e3e-109">So installieren Sie die WCF-Aktivierungskomponenten für andere Protokolle als HTTP</span><span class="sxs-lookup"><span data-stu-id="d1e3e-109">To install the WCF non-HTTP activation components</span></span>  
  
1.  <span data-ttu-id="d1e3e-110">Klicken Sie auf die **starten** Schaltfläche aus, und klicken Sie dann auf **Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="d1e3e-110">Click the **Start** button, and then click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="d1e3e-111">Klicken Sie auf **Programme**, und klicken Sie dann auf **Programme und Funktionen**.</span><span class="sxs-lookup"><span data-stu-id="d1e3e-111">Click **Programs**, and then click **Programs and Features**.</span></span>  
  
3.  <span data-ttu-id="d1e3e-112">Auf der **Aufgaben** Menü klicken Sie auf **Windows-Funktionen ein- oder ausschalten**.</span><span class="sxs-lookup"><span data-stu-id="d1e3e-112">On the **Tasks** menu, click **Turn Windows features on or off**.</span></span>  
  
4.  <span data-ttu-id="d1e3e-113">Suchen Sie den [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)]-Knoten, markieren Sie ihn, und erweitern Sie ihn dann.</span><span class="sxs-lookup"><span data-stu-id="d1e3e-113">Find the [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] node, select and then expand it.</span></span>  
  
5.  <span data-ttu-id="d1e3e-114">Wählen Sie die **WCF-Aktivierungskomponenten für nicht-HTTP-** und speichern Sie die Einstellung.</span><span class="sxs-lookup"><span data-stu-id="d1e3e-114">Select the **WCF Non-Http Activation Components** box and save the setting.</span></span>  
  
### <a name="to-configure-the-was-to-support-tcp-activation"></a><span data-ttu-id="d1e3e-115">So konfigurieren Sie den WAS, sodass die TCP-Aktivierung unterstützt wird</span><span class="sxs-lookup"><span data-stu-id="d1e3e-115">To configure the WAS to support TCP activation</span></span>  
  
1.  <span data-ttu-id="d1e3e-116">Zur Unterstützung der net.tcp-Aktivierung muss die Standardwebsite zuerst an einen net.tcp-Port gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="d1e3e-116">To support net.tcp activation, the default Web site must first be bound to a net.tcp port.</span></span> <span data-ttu-id="d1e3e-117">Sie können hierzu das Tool Appcmd.exe verwenden, das mit dem [!INCLUDE[iisver](../../../../includes/iisver-md.md)]-Verwaltungstoolset installiert wird.</span><span class="sxs-lookup"><span data-stu-id="d1e3e-117">You can do this by using Appcmd.exe, which is installed with the [!INCLUDE[iisver](../../../../includes/iisver-md.md)] management toolset.</span></span> <span data-ttu-id="d1e3e-118">Führen Sie in einem Eingabeaufforderungsfenster auf Administratorebene den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="d1e3e-118">In an administrator-level Command Prompt window, run the following command.</span></span>  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="d1e3e-119">Dieser Befehl ist eine einzelne Textzeile.</span><span class="sxs-lookup"><span data-stu-id="d1e3e-119">This command is a single line of text.</span></span> <span data-ttu-id="d1e3e-120">Mit dem Befehl wird eine neue net.tcp-Sitebindung der Standardwebsite hinzugefügt, die TCP-Anschluss 808 mit jedem beliebigen Hostnamen überwacht.</span><span class="sxs-lookup"><span data-stu-id="d1e3e-120">This command adds a net.tcp site binding to the default Web site listening on TCP port 808 with any host name.</span></span>  
  
2.  <span data-ttu-id="d1e3e-121">Alle Anwendungen innerhalb einer Site nutzen zwar eine gemeinsame net.tcp-Bindung, aber jede Anwendung kann die net.tcp-Unterstützung unabhängig von den anderen Anwendungen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="d1e3e-121">Although all applications within a site share a common net.tcp binding, each application can enable net.tcp support individually.</span></span> <span data-ttu-id="d1e3e-122">Um net.tcp für die Anwendung zu aktivieren, führen Sie den folgenden Befehl in einem Eingabeaufforderungsfenster auf Administratorebene aus.</span><span class="sxs-lookup"><span data-stu-id="d1e3e-122">To enable net.tcp for the application, run the following command from an administrator-level command prompt.</span></span>  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set app   
    "Default Web Site/<WCF Application>" /enabledProtocols:http,net.tcp  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="d1e3e-123">Dieser Befehl ist eine einzelne Textzeile.</span><span class="sxs-lookup"><span data-stu-id="d1e3e-123">This command is a single line of text.</span></span> <span data-ttu-id="d1e3e-124">Dieser Befehl aktiviert die /\<*WCF-Anwendung*> Anwendung darauf zugegriffen werden beide http://localhost*/\<WCF-Anwendung >* und net.tcp:// "localhost" /*\<WCF-Anwendung >*.</span><span class="sxs-lookup"><span data-stu-id="d1e3e-124">This command enables the /\<*WCF Application*> application to be accessed using both http://localhost*/\<WCF Application>* and net.tcp://localhost/*\<WCF Application>*.</span></span>  
  
     <span data-ttu-id="d1e3e-125">Entfernen Sie die net.tcp-Sitebindung, die für dieses Beispiel hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="d1e3e-125">Remove the net.tcp site binding you added for this sample.</span></span>  
  
     <span data-ttu-id="d1e3e-126">Zur Vereinfachung sind die folgenden beiden Schritte in einer Batchdatei namens RemoveNetTcpSiteBinding.cmd implementiert, die sich im Beispielverzeichnis befindet.</span><span class="sxs-lookup"><span data-stu-id="d1e3e-126">As a convenience, the following two steps are implemented in a batch file called RemoveNetTcpSiteBinding.cmd located in the sample directory.</span></span>  
  
    1.  <span data-ttu-id="d1e3e-127">Entfernen Sie net.tcp aus der Liste aktivierter Protokolle, indem Sie den folgenden Befehl in einem Eingabeaufforderungsfenster auf Administratorebene ausführen.</span><span class="sxs-lookup"><span data-stu-id="d1e3e-127">Remove net.tcp from the list of enabled protocols by running the following command in an administrator-level Command Prompt window.</span></span>  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set app   
        "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="d1e3e-128">Dieser Befehl ist eine einzelne Textzeile.</span><span class="sxs-lookup"><span data-stu-id="d1e3e-128">This command is a single line of text.</span></span>  
  
    2.  <span data-ttu-id="d1e3e-129">Entfernen Sie die net.tcp-Sitebindung, indem Sie den folgenden Befehl in einem Eingabeaufforderungsfenster auf Administratorebene ausführen:</span><span class="sxs-lookup"><span data-stu-id="d1e3e-129">Remove the net.tcp site binding by running the following command in an elevated Command Prompt window:</span></span>  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
        --bindings.[protocol='net.tcp',bindingInformation='808:*']  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="d1e3e-130">Dieser Befehl ist eine einzelne Textzeile.</span><span class="sxs-lookup"><span data-stu-id="d1e3e-130">This command is a single line of text.</span></span>  
  
### <a name="to-remove-nettcp-from-the-list-of-enabled-protocols"></a><span data-ttu-id="d1e3e-131">So entfernen Sie net.tcp aus der Liste aktivierter Protokolle</span><span class="sxs-lookup"><span data-stu-id="d1e3e-131">To remove net.tcp from the list of enabled protocols</span></span>  
  
1.  <span data-ttu-id="d1e3e-132">Um net.tcp aus der Liste aktivierter Protokolle zu entfernen, führen Sie den folgenden Befehl in einem Eingabeaufforderungsfenster auf Administratorebene aus.</span><span class="sxs-lookup"><span data-stu-id="d1e3e-132">To remove net.tcp from the list of enabled protocols, run the following command in an administrator-level Command Prompt window.</span></span>  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="d1e3e-133">Dieser Befehl ist eine einzelne Textzeile.</span><span class="sxs-lookup"><span data-stu-id="d1e3e-133">This command is a single line of text.</span></span>  
  
### <a name="to-remove-the-nettcp-site-binding"></a><span data-ttu-id="d1e3e-134">So entfernen Sie die net.tcp-Bindung</span><span class="sxs-lookup"><span data-stu-id="d1e3e-134">To remove the net.tcp site binding</span></span>  
  
1.  <span data-ttu-id="d1e3e-135">Um die net.tcp-Sitebindung zu entfernen, führen Sie den folgenden Befehl in einem Eingabeaufforderungsfenster auf Administratorebene aus.</span><span class="sxs-lookup"><span data-stu-id="d1e3e-135">To remove the net.tcp site binding run the following command in an administrator-level Command Prompt window.</span></span>  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
    -bindings.[protocol='net.tcp',bindingInformation='808:*']  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="d1e3e-136">Dieser Befehl ist eine einzelne Textzeile.</span><span class="sxs-lookup"><span data-stu-id="d1e3e-136">This command is a single line of text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1e3e-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d1e3e-137">See Also</span></span>  
 [<span data-ttu-id="d1e3e-138">TCP-Aktivierung</span><span class="sxs-lookup"><span data-stu-id="d1e3e-138">TCP Activation</span></span>](../../../../docs/framework/wcf/samples/tcp-activation.md)  
 [<span data-ttu-id="d1e3e-139">MSMQ-Aktivierung</span><span class="sxs-lookup"><span data-stu-id="d1e3e-139">MSMQ Activation</span></span>](../../../../docs/framework/wcf/samples/msmq-activation.md)  
 [<span data-ttu-id="d1e3e-140">NamedPipe-Aktivierung</span><span class="sxs-lookup"><span data-stu-id="d1e3e-140">NamedPipe Activation</span></span>](../../../../docs/framework/wcf/samples/namedpipe-activation.md)  
 [<span data-ttu-id="d1e3e-141">Windows Server AppFabric-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="d1e3e-141">Windows Server App Fabric Hosting Features</span></span>](http://go.microsoft.com/fwlink/?LinkId=201276)
