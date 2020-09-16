---
title: 'Vorgehensweise: Installieren und Konfigurieren von WCF-Aktivierungskomponenten'
description: Erfahren Sie, wie Sie den Windows-Prozess Aktivierungs Dienst (was) unter Windows Vista einrichten, um WCF-Dienste zu hosten, die nicht über HTTP kommunizieren.
ms.date: 03/30/2017
helpviewer_keywords:
- HTTP activation [WCF]
ms.assetid: 33a7054a-73ec-464d-83e5-b203aeded658
ms.openlocfilehash: 085a69421f0aa7b763bd2222820ced4b4a7e1c81
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557865"
---
# <a name="how-to-install-and-configure-wcf-activation-components"></a><span data-ttu-id="e9bcc-103">Vorgehensweise: Installieren und Konfigurieren von WCF-Aktivierungskomponenten</span><span class="sxs-lookup"><span data-stu-id="e9bcc-103">How to: Install and Configure WCF Activation Components</span></span>

<span data-ttu-id="e9bcc-104">In diesem Thema werden die Schritte beschrieben, die zum Einrichten von Windows Process Activation Service (auch bekannt als was) unter Windows Vista erforderlich sind, um Windows Communication Foundation (WCF)-Dienste zu hosten, die nicht über HTTP-Netzwerkprotokolle kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="e9bcc-104">This topic describes the steps required to set up Windows Process Activation Service (also known as WAS) on Windows Vista to host Windows Communication Foundation (WCF) services that do not communicate over HTTP network protocols.</span></span> <span data-ttu-id="e9bcc-105">In den folgenden Abschnitten werden die für diese Konfiguration erforderlichen Schritte kurz beschrieben:</span><span class="sxs-lookup"><span data-stu-id="e9bcc-105">The following sections outline the steps for this configuration:</span></span>

- <span data-ttu-id="e9bcc-106">Installieren (oder bestätigen Sie die Installation von) der WCF-Aktivierungs Komponenten.</span><span class="sxs-lookup"><span data-stu-id="e9bcc-106">Install (or confirm the installation of) the WCF activation components.</span></span>

- <span data-ttu-id="e9bcc-107">Konfigurieren Sie WAS, sodass Nicht-HTTP-Protokolle unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="e9bcc-107">Configure WAS to support a non-HTTP protocol.</span></span> <span data-ttu-id="e9bcc-108">Mit dem folgenden Verfahren wird Windows Vista für die TCP-Aktivierung konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="e9bcc-108">The following procedure configures Windows Vista for TCP activation.</span></span>

<span data-ttu-id="e9bcc-109">Nach der Installation und Konfiguration von was finden Sie unter Gewusst [wie: Hosten eines WCF-Diensts in was](how-to-host-a-wcf-service-in-was.md) die Verfahren zum Erstellen eines WCF-Diensts, der einen nicht-HTTP-Endpunkt bereitstellt, der was verwendet.</span><span class="sxs-lookup"><span data-stu-id="e9bcc-109">After installing and configuring WAS, see [How to: Host a WCF Service in WAS](how-to-host-a-wcf-service-in-was.md) for the procedures to create a WCF service that exposes an non-HTTP endpoint that employs WAS.</span></span>

## <a name="to-install-the-wcf-non-http-activation-components"></a><span data-ttu-id="e9bcc-110">So installieren Sie die WCF-Aktivierungskomponenten für andere Protokolle als HTTP</span><span class="sxs-lookup"><span data-stu-id="e9bcc-110">To install the WCF non-HTTP activation components</span></span>

1. <span data-ttu-id="e9bcc-111">Klicken Sie auf die Schaltfläche **Start** und dann auf **Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="e9bcc-111">Click the **Start** button, and then click **Control Panel**.</span></span>

2. <span data-ttu-id="e9bcc-112">Klicken Sie auf **Programme** und dann auf **Programme und Funktionen**.</span><span class="sxs-lookup"><span data-stu-id="e9bcc-112">Click **Programs**, and then click **Programs and Features**.</span></span>

3. <span data-ttu-id="e9bcc-113">Klicken Sie im Menü **Aufgaben** auf **Windows-Funktionen ein-oder ausschalten**.</span><span class="sxs-lookup"><span data-stu-id="e9bcc-113">On the **Tasks** menu, click **Turn Windows features on or off**.</span></span>

4. <span data-ttu-id="e9bcc-114">Suchen Sie den Knoten WinFX, wählen Sie ihn aus, und erweitern Sie ihn.</span><span class="sxs-lookup"><span data-stu-id="e9bcc-114">Find the WinFX node, select and then expand it.</span></span>

5. <span data-ttu-id="e9bcc-115">Aktivieren Sie das Kontrollkästchen **WCF-nicht-http-Aktivierungs Komponenten** , und speichern Sie die Einstellung.</span><span class="sxs-lookup"><span data-stu-id="e9bcc-115">Select the **WCF Non-Http Activation Components** box and save the setting.</span></span>

## <a name="to-configure-the-was-to-support-tcp-activation"></a><span data-ttu-id="e9bcc-116">So konfigurieren Sie den WAS, sodass die TCP-Aktivierung unterstützt wird</span><span class="sxs-lookup"><span data-stu-id="e9bcc-116">To configure the WAS to support TCP activation</span></span>

1. <span data-ttu-id="e9bcc-117">Zur Unterstützung der net.tcp-Aktivierung muss die Standardwebsite zuerst an einen net.tcp-Port gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="e9bcc-117">To support net.tcp activation, the default Web site must first be bound to a net.tcp port.</span></span> <span data-ttu-id="e9bcc-118">Hierfür können Sie Appcmd.exe verwenden, die mit dem IIS 7,0-Verwaltungs Toolset installiert wird.</span><span class="sxs-lookup"><span data-stu-id="e9bcc-118">You can do this by using Appcmd.exe, which is installed with the IIS 7.0 management toolset.</span></span> <span data-ttu-id="e9bcc-119">Führen Sie in einem Eingabeaufforderungsfenster auf Administratorebene den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="e9bcc-119">In an administrator-level Command Prompt window, run the following command.</span></span>

    ```console
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']
    ```

    > [!NOTE]
    > <span data-ttu-id="e9bcc-120">Dieser Befehl ist eine einzelne Textzeile.</span><span class="sxs-lookup"><span data-stu-id="e9bcc-120">This command is a single line of text.</span></span> <span data-ttu-id="e9bcc-121">Mit dem Befehl wird eine neue net.tcp-Sitebindung der Standardwebsite hinzugefügt, die TCP-Anschluss 808 mit jedem beliebigen Hostnamen überwacht.</span><span class="sxs-lookup"><span data-stu-id="e9bcc-121">This command adds a net.tcp site binding to the default Web site listening on TCP port 808 with any host name.</span></span>

2. <span data-ttu-id="e9bcc-122">Alle Anwendungen innerhalb einer Site nutzen zwar eine gemeinsame net.tcp-Bindung, aber jede Anwendung kann die net.tcp-Unterstützung unabhängig von den anderen Anwendungen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e9bcc-122">Although all applications within a site share a common net.tcp binding, each application can enable net.tcp support individually.</span></span> <span data-ttu-id="e9bcc-123">Um net.tcp für die Anwendung zu aktivieren, führen Sie den folgenden Befehl in einem Eingabeaufforderungsfenster auf Administratorebene aus.</span><span class="sxs-lookup"><span data-stu-id="e9bcc-123">To enable net.tcp for the application, run the following command from an administrator-level command prompt.</span></span>

    ```console
    %windir%\system32\inetsrv\appcmd.exe set app
    "Default Web Site/<WCF Application>" /enabledProtocols:http,net.tcp
    ```

    > [!NOTE]
    > <span data-ttu-id="e9bcc-124">Dieser Befehl ist eine einzelne Textzeile.</span><span class="sxs-lookup"><span data-stu-id="e9bcc-124">This command is a single line of text.</span></span> <span data-ttu-id="e9bcc-125">Dieser Befehl ermöglicht den Zugriff auf die/- \<*WCF Application*> Anwendung mithilfe von `http://localhost/<WCF Application>` und `net.tcp://localhost/<WCF Application>` .</span><span class="sxs-lookup"><span data-stu-id="e9bcc-125">This command enables the /\<*WCF Application*> application to be accessed using both `http://localhost/<WCF Application>` and `net.tcp://localhost/<WCF Application>`.</span></span>

     <span data-ttu-id="e9bcc-126">Entfernen Sie die net.tcp-Sitebindung, die für dieses Beispiel hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="e9bcc-126">Remove the net.tcp site binding you added for this sample.</span></span>

     <span data-ttu-id="e9bcc-127">Zur Vereinfachung sind die folgenden beiden Schritte in einer Batchdatei namens RemoveNetTcpSiteBinding.cmd implementiert, die sich im Beispielverzeichnis befindet.</span><span class="sxs-lookup"><span data-stu-id="e9bcc-127">As a convenience, the following two steps are implemented in a batch file called RemoveNetTcpSiteBinding.cmd located in the sample directory.</span></span>

    1. <span data-ttu-id="e9bcc-128">Entfernen Sie net.tcp aus der Liste aktivierter Protokolle, indem Sie den folgenden Befehl in einem Eingabeaufforderungsfenster auf Administratorebene ausführen.</span><span class="sxs-lookup"><span data-stu-id="e9bcc-128">Remove net.tcp from the list of enabled protocols by running the following command in an administrator-level Command Prompt window.</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set app
        "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http
        ```

        > [!NOTE]
        > <span data-ttu-id="e9bcc-129">Dieser Befehl ist eine einzelne Textzeile.</span><span class="sxs-lookup"><span data-stu-id="e9bcc-129">This command is a single line of text.</span></span>

    2. <span data-ttu-id="e9bcc-130">Entfernen Sie die net.tcp-Sitebindung, indem Sie den folgenden Befehl in einem Eingabeaufforderungsfenster auf Administratorebene ausführen:</span><span class="sxs-lookup"><span data-stu-id="e9bcc-130">Remove the net.tcp site binding by running the following command in an elevated Command Prompt window:</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"
        --bindings.[protocol='net.tcp',bindingInformation='808:*']
        ```

        > [!NOTE]
        > <span data-ttu-id="e9bcc-131">Dieser Befehl ist eine einzelne Textzeile.</span><span class="sxs-lookup"><span data-stu-id="e9bcc-131">This command is a single line of text.</span></span>

## <a name="to-remove-nettcp-from-the-list-of-enabled-protocols"></a><span data-ttu-id="e9bcc-132">So entfernen Sie net.tcp aus der Liste aktivierter Protokolle</span><span class="sxs-lookup"><span data-stu-id="e9bcc-132">To remove net.tcp from the list of enabled protocols</span></span>

1. <span data-ttu-id="e9bcc-133">Um net.tcp aus der Liste aktivierter Protokolle zu entfernen, führen Sie den folgenden Befehl in einem Eingabeaufforderungsfenster auf Administratorebene aus.</span><span class="sxs-lookup"><span data-stu-id="e9bcc-133">To remove net.tcp from the list of enabled protocols, run the following command in an administrator-level Command Prompt window.</span></span>

    ```console
    %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http
    ```

    > [!NOTE]
    > <span data-ttu-id="e9bcc-134">Dieser Befehl ist eine einzelne Textzeile.</span><span class="sxs-lookup"><span data-stu-id="e9bcc-134">This command is a single line of text.</span></span>

## <a name="to-remove-the-nettcp-site-binding"></a><span data-ttu-id="e9bcc-135">So entfernen Sie die net.tcp-Bindung</span><span class="sxs-lookup"><span data-stu-id="e9bcc-135">To remove the net.tcp site binding</span></span>

1. <span data-ttu-id="e9bcc-136">Um die net.tcp-Sitebindung zu entfernen, führen Sie den folgenden Befehl in einem Eingabeaufforderungsfenster auf Administratorebene aus.</span><span class="sxs-lookup"><span data-stu-id="e9bcc-136">To remove the net.tcp site binding run the following command in an administrator-level Command Prompt window.</span></span>

    ```console
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"
    -bindings.[protocol='net.tcp',bindingInformation='808:*']
    ```

    > [!NOTE]
    > <span data-ttu-id="e9bcc-137">Dieser Befehl ist eine einzelne Textzeile.</span><span class="sxs-lookup"><span data-stu-id="e9bcc-137">This command is a single line of text.</span></span>

## <a name="see-also"></a><span data-ttu-id="e9bcc-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9bcc-138">See also</span></span>

- [<span data-ttu-id="e9bcc-139">TCP-Aktivierung</span><span class="sxs-lookup"><span data-stu-id="e9bcc-139">TCP Activation</span></span>](../samples/tcp-activation.md)
- [<span data-ttu-id="e9bcc-140">MSMQ-Aktivierung</span><span class="sxs-lookup"><span data-stu-id="e9bcc-140">MSMQ Activation</span></span>](../samples/msmq-activation.md)
- [<span data-ttu-id="e9bcc-141">NamedPipe-Aktivierung</span><span class="sxs-lookup"><span data-stu-id="e9bcc-141">NamedPipe Activation</span></span>](../samples/namedpipe-activation.md)
- <span data-ttu-id="e9bcc-142">[Windows Server AppFabric-Hostingfunktionen](/previous-versions/appfabric/ee677189(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="e9bcc-142">[Windows Server App Fabric Hosting Features](/previous-versions/appfabric/ee677189(v=azure.10))</span></span>
