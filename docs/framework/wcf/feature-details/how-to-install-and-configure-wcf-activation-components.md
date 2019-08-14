---
title: 'Vorgehensweise: Installieren und Konfigurieren von WCF-Aktivierungskomponenten'
ms.date: 03/30/2017
helpviewer_keywords:
- HTTP activation [WCF]
ms.assetid: 33a7054a-73ec-464d-83e5-b203aeded658
ms.openlocfilehash: aed6cb71ac3ccd7af5423cdb8ccc43133bbe5337
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972030"
---
# <a name="how-to-install-and-configure-wcf-activation-components"></a><span data-ttu-id="c9ceb-102">Vorgehensweise: Installieren und Konfigurieren von WCF-Aktivierungskomponenten</span><span class="sxs-lookup"><span data-stu-id="c9ceb-102">How to: Install and Configure WCF Activation Components</span></span>

<span data-ttu-id="c9ceb-103">In diesem Thema werden die Schritte beschrieben, die erforderlich sind, um den Windows-Prozess Aktivierungs Dienst ( [!INCLUDE[wv](../../../../includes/wv-md.md)] auch bekannt als was) auf zu hosten Windows Communication Foundation (WCF)-Dienste, die nicht über HTTP-Netzwerkprotokolle kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="c9ceb-103">This topic describes the steps required to set up Windows Process Activation Service (also known as WAS) on [!INCLUDE[wv](../../../../includes/wv-md.md)] to host Windows Communication Foundation (WCF) services that do not communicate over HTTP network protocols.</span></span> <span data-ttu-id="c9ceb-104">In den folgenden Abschnitten werden die für diese Konfiguration erforderlichen Schritte kurz beschrieben:</span><span class="sxs-lookup"><span data-stu-id="c9ceb-104">The following sections outline the steps for this configuration:</span></span>

- <span data-ttu-id="c9ceb-105">Installieren (oder bestätigen Sie die Installation von) der WCF-Aktivierungs Komponenten.</span><span class="sxs-lookup"><span data-stu-id="c9ceb-105">Install (or confirm the installation of) the WCF activation components.</span></span>

- <span data-ttu-id="c9ceb-106">Konfigurieren Sie WAS, sodass Nicht-HTTP-Protokolle unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="c9ceb-106">Configure WAS to support a non-HTTP protocol.</span></span> <span data-ttu-id="c9ceb-107">Mit den folgenden Schritten wird [!INCLUDE[wv](../../../../includes/wv-md.md)] für die TCP-Aktivierung konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="c9ceb-107">The following procedure configures [!INCLUDE[wv](../../../../includes/wv-md.md)] for TCP activation.</span></span>

<span data-ttu-id="c9ceb-108">Nach der Installation und Konfiguration von was [finden Sie unter Vorgehensweise: Hosten Sie einen WCF-](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md) Dienst in was für die Verfahren zum Erstellen eines WCF-Diensts, der einen nicht-HTTP-Endpunkt verfügbar macht, der was verwendet.</span><span class="sxs-lookup"><span data-stu-id="c9ceb-108">After installing and configuring WAS, see [How to: Host a WCF Service in WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md) for the procedures to create a WCF service that exposes an non-HTTP endpoint that employs WAS.</span></span>

## <a name="to-install-the-wcf-non-http-activation-components"></a><span data-ttu-id="c9ceb-109">So installieren Sie die WCF-Aktivierungskomponenten für andere Protokolle als HTTP</span><span class="sxs-lookup"><span data-stu-id="c9ceb-109">To install the WCF non-HTTP activation components</span></span>

1. <span data-ttu-id="c9ceb-110">Klicken Sie auf die Schaltfläche **Start** und dann auf **Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="c9ceb-110">Click the **Start** button, and then click **Control Panel**.</span></span>

2. <span data-ttu-id="c9ceb-111">Klicken Sie auf **Programme**und dann auf **Programme und Funktionen**.</span><span class="sxs-lookup"><span data-stu-id="c9ceb-111">Click **Programs**, and then click **Programs and Features**.</span></span>

3. <span data-ttu-id="c9ceb-112">Klicken Sie im Menü **Aufgaben** auf **Windows-Funktionen ein-oder ausschalten**.</span><span class="sxs-lookup"><span data-stu-id="c9ceb-112">On the **Tasks** menu, click **Turn Windows features on or off**.</span></span>

4. <span data-ttu-id="c9ceb-113">Suchen Sie den Knoten WinFX, wählen Sie ihn aus, und erweitern Sie ihn.</span><span class="sxs-lookup"><span data-stu-id="c9ceb-113">Find the WinFX node, select and then expand it.</span></span>

5. <span data-ttu-id="c9ceb-114">Aktivieren Sie das Kontrollkästchen **WCF-nicht-http-Aktivierungs Komponenten** , und speichern Sie die Einstellung.</span><span class="sxs-lookup"><span data-stu-id="c9ceb-114">Select the **WCF Non-Http Activation Components** box and save the setting.</span></span>

## <a name="to-configure-the-was-to-support-tcp-activation"></a><span data-ttu-id="c9ceb-115">So konfigurieren Sie den WAS, sodass die TCP-Aktivierung unterstützt wird</span><span class="sxs-lookup"><span data-stu-id="c9ceb-115">To configure the WAS to support TCP activation</span></span>

1. <span data-ttu-id="c9ceb-116">Zur Unterstützung der net.tcp-Aktivierung muss die Standardwebsite zuerst an einen net.tcp-Port gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="c9ceb-116">To support net.tcp activation, the default Web site must first be bound to a net.tcp port.</span></span> <span data-ttu-id="c9ceb-117">Hierfür können Sie Appcmd. exe verwenden, das mit dem IIS 7,0-Verwaltungs Toolset installiert wird.</span><span class="sxs-lookup"><span data-stu-id="c9ceb-117">You can do this by using Appcmd.exe, which is installed with the IIS 7.0 management toolset.</span></span> <span data-ttu-id="c9ceb-118">Führen Sie in einem Eingabeaufforderungsfenster auf Administratorebene den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="c9ceb-118">In an administrator-level Command Prompt window, run the following command.</span></span>

    ```
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']
    ```

    > [!NOTE]
    > <span data-ttu-id="c9ceb-119">Dieser Befehl ist eine einzelne Textzeile.</span><span class="sxs-lookup"><span data-stu-id="c9ceb-119">This command is a single line of text.</span></span> <span data-ttu-id="c9ceb-120">Mit dem Befehl wird eine neue net.tcp-Sitebindung der Standardwebsite hinzugefügt, die TCP-Anschluss 808 mit jedem beliebigen Hostnamen überwacht.</span><span class="sxs-lookup"><span data-stu-id="c9ceb-120">This command adds a net.tcp site binding to the default Web site listening on TCP port 808 with any host name.</span></span>

2. <span data-ttu-id="c9ceb-121">Alle Anwendungen innerhalb einer Site nutzen zwar eine gemeinsame net.tcp-Bindung, aber jede Anwendung kann die net.tcp-Unterstützung unabhängig von den anderen Anwendungen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c9ceb-121">Although all applications within a site share a common net.tcp binding, each application can enable net.tcp support individually.</span></span> <span data-ttu-id="c9ceb-122">Um net.tcp für die Anwendung zu aktivieren, führen Sie den folgenden Befehl in einem Eingabeaufforderungsfenster auf Administratorebene aus.</span><span class="sxs-lookup"><span data-stu-id="c9ceb-122">To enable net.tcp for the application, run the following command from an administrator-level command prompt.</span></span>

    ```
    %windir%\system32\inetsrv\appcmd.exe set app
    "Default Web Site/<WCF Application>" /enabledProtocols:http,net.tcp
    ```

    > [!NOTE]
    > <span data-ttu-id="c9ceb-123">Dieser Befehl ist eine einzelne Textzeile.</span><span class="sxs-lookup"><span data-stu-id="c9ceb-123">This command is a single line of text.</span></span> <span data-ttu-id="c9ceb-124">Mit diesem Befehl\< `net.tcp://localhost/<WCF Application>` `http://localhost/<WCF Application>` wird der Zugriff auf die Anwendung/*WCF-Anwendung*> mithilfe von und ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="c9ceb-124">This command enables the /\<*WCF Application*> application to be accessed using both `http://localhost/<WCF Application>` and `net.tcp://localhost/<WCF Application>`.</span></span>

     <span data-ttu-id="c9ceb-125">Entfernen Sie die net.tcp-Sitebindung, die für dieses Beispiel hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="c9ceb-125">Remove the net.tcp site binding you added for this sample.</span></span>

     <span data-ttu-id="c9ceb-126">Zur Vereinfachung sind die folgenden beiden Schritte in einer Batchdatei namens RemoveNetTcpSiteBinding.cmd implementiert, die sich im Beispielverzeichnis befindet.</span><span class="sxs-lookup"><span data-stu-id="c9ceb-126">As a convenience, the following two steps are implemented in a batch file called RemoveNetTcpSiteBinding.cmd located in the sample directory.</span></span>

    1. <span data-ttu-id="c9ceb-127">Entfernen Sie net.tcp aus der Liste aktivierter Protokolle, indem Sie den folgenden Befehl in einem Eingabeaufforderungsfenster auf Administratorebene ausführen.</span><span class="sxs-lookup"><span data-stu-id="c9ceb-127">Remove net.tcp from the list of enabled protocols by running the following command in an administrator-level Command Prompt window.</span></span>

        ```
        %windir%\system32\inetsrv\appcmd.exe set app
        "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http
        ```

        > [!NOTE]
        > <span data-ttu-id="c9ceb-128">Dieser Befehl ist eine einzelne Textzeile.</span><span class="sxs-lookup"><span data-stu-id="c9ceb-128">This command is a single line of text.</span></span>

    2. <span data-ttu-id="c9ceb-129">Entfernen Sie die net.tcp-Sitebindung, indem Sie den folgenden Befehl in einem Eingabeaufforderungsfenster auf Administratorebene ausführen:</span><span class="sxs-lookup"><span data-stu-id="c9ceb-129">Remove the net.tcp site binding by running the following command in an elevated Command Prompt window:</span></span>

        ```
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"
        --bindings.[protocol='net.tcp',bindingInformation='808:*']
        ```

        > [!NOTE]
        > <span data-ttu-id="c9ceb-130">Dieser Befehl ist eine einzelne Textzeile.</span><span class="sxs-lookup"><span data-stu-id="c9ceb-130">This command is a single line of text.</span></span>

## <a name="to-remove-nettcp-from-the-list-of-enabled-protocols"></a><span data-ttu-id="c9ceb-131">So entfernen Sie net.tcp aus der Liste aktivierter Protokolle</span><span class="sxs-lookup"><span data-stu-id="c9ceb-131">To remove net.tcp from the list of enabled protocols</span></span>

1. <span data-ttu-id="c9ceb-132">Um net.tcp aus der Liste aktivierter Protokolle zu entfernen, führen Sie den folgenden Befehl in einem Eingabeaufforderungsfenster auf Administratorebene aus.</span><span class="sxs-lookup"><span data-stu-id="c9ceb-132">To remove net.tcp from the list of enabled protocols, run the following command in an administrator-level Command Prompt window.</span></span>

    ```
    %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http
    ```

    > [!NOTE]
    > <span data-ttu-id="c9ceb-133">Dieser Befehl ist eine einzelne Textzeile.</span><span class="sxs-lookup"><span data-stu-id="c9ceb-133">This command is a single line of text.</span></span>

## <a name="to-remove-the-nettcp-site-binding"></a><span data-ttu-id="c9ceb-134">So entfernen Sie die net.tcp-Bindung</span><span class="sxs-lookup"><span data-stu-id="c9ceb-134">To remove the net.tcp site binding</span></span>

1. <span data-ttu-id="c9ceb-135">Um die net.tcp-Sitebindung zu entfernen, führen Sie den folgenden Befehl in einem Eingabeaufforderungsfenster auf Administratorebene aus.</span><span class="sxs-lookup"><span data-stu-id="c9ceb-135">To remove the net.tcp site binding run the following command in an administrator-level Command Prompt window.</span></span>

    ```
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"
    -bindings.[protocol='net.tcp',bindingInformation='808:*']
    ```

    > [!NOTE]
    > <span data-ttu-id="c9ceb-136">Dieser Befehl ist eine einzelne Textzeile.</span><span class="sxs-lookup"><span data-stu-id="c9ceb-136">This command is a single line of text.</span></span>

## <a name="see-also"></a><span data-ttu-id="c9ceb-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c9ceb-137">See also</span></span>

- [<span data-ttu-id="c9ceb-138">TCP-Aktivierung</span><span class="sxs-lookup"><span data-stu-id="c9ceb-138">TCP Activation</span></span>](../../../../docs/framework/wcf/samples/tcp-activation.md)
- [<span data-ttu-id="c9ceb-139">MSMQ-Aktivierung</span><span class="sxs-lookup"><span data-stu-id="c9ceb-139">MSMQ Activation</span></span>](../../../../docs/framework/wcf/samples/msmq-activation.md)
- [<span data-ttu-id="c9ceb-140">NamedPipe-Aktivierung</span><span class="sxs-lookup"><span data-stu-id="c9ceb-140">NamedPipe Activation</span></span>](../../../../docs/framework/wcf/samples/namedpipe-activation.md)
- [<span data-ttu-id="c9ceb-141">Windows Server AppFabric-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="c9ceb-141">Windows Server App Fabric Hosting Features</span></span>](https://go.microsoft.com/fwlink/?LinkId=201276)
