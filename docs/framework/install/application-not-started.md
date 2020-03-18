---
title: Problembehandlung der Meldung „Diese Anwendung konnte nicht gestartet werden“
description: Erfahren Sie, wie vorzugehen ist, wenn das Dialogfeld „Diese Anwendung konnte nicht gestartet werden“ angezeigt wird.
ms.date: 09/05/2019
ms.openlocfilehash: 864c6ea23e9a048f060eee39d904bd4377be5084
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "76965905"
---
# <a name="troubleshooting-a-this-application-could-not-be-started-error-message"></a><span data-ttu-id="bd5e3-103">Problembehandlung der Fehlermeldung „Diese Anwendung konnte nicht gestartet werden“</span><span class="sxs-lookup"><span data-stu-id="bd5e3-103">Troubleshooting a 'This application could not be started' error message</span></span>

<span data-ttu-id="bd5e3-104">Für Anwendungen, die für .NET Framework entwickelt wurden, ist es in der Regel erforderlich, dass eine bestimmte Version von .NET Framework auf dem System installiert ist.</span><span class="sxs-lookup"><span data-stu-id="bd5e3-104">Applications that are developed for the .NET Framework typically require that a specific version of the .NET Framework be installed on your system.</span></span> <span data-ttu-id="bd5e3-105">In einigen Fällen können Sie versuchen, eine Anwendung auszuführen, ohne dass eine installierte Version oder die erwartete Version von .NET Framework vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="bd5e3-105">In some cases, you may attempt to run an application without either an installed version or the expected version of the .NET Framework present.</span></span> <span data-ttu-id="bd5e3-106">Dies führt häufig zu einem Fehlerdialogfeld wie dem folgenden:</span><span class="sxs-lookup"><span data-stu-id="bd5e3-106">This often produces an error dialog box like the following:</span></span>

![Diese Anwendung konnte nicht gestartet werden](media/application-not-started/app-could-not-be-started.png)

<span data-ttu-id="bd5e3-108">Dies weist in der Regel auf eine der folgenden Bedingungen hin:</span><span class="sxs-lookup"><span data-stu-id="bd5e3-108">This typically indicates one of the following conditions:</span></span>

- <span data-ttu-id="bd5e3-109">Eine .NET Framework-Installation auf Ihrem System ist beschädigt.</span><span class="sxs-lookup"><span data-stu-id="bd5e3-109">A .NET Framework installation on your system has become corrupted.</span></span>

- <span data-ttu-id="bd5e3-110">Die Version von .NET Framework, die von der Anwendung benötigt wird, konnte nicht erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="bd5e3-110">The version of the .NET Framework needed by your application cannot be detected.</span></span>

<span data-ttu-id="bd5e3-111">Gehen Sie folgendermaßen vor, um dieses Problem zu beheben, damit Sie die Anwendung ausführen können:</span><span class="sxs-lookup"><span data-stu-id="bd5e3-111">To address this issue so that you can run your application, do the following:</span></span>

1. <span data-ttu-id="bd5e3-112">Laden Sie das [Reparaturtool für .NET Framework („NetFxRepairTool.exe“) ](https://www.microsoft.com/download/details.aspx?id=30135) herunter.</span><span class="sxs-lookup"><span data-stu-id="bd5e3-112">Download the [.NET Framework Repair Tool (NetFxRepairTool.exe)](https://www.microsoft.com/download/details.aspx?id=30135).</span></span> <span data-ttu-id="bd5e3-113">Das Tool wird automatisch ausgeführt, nachdem der Download abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="bd5e3-113">The tool runs automatically when the download completes.</span></span>

1. <span data-ttu-id="bd5e3-114">Wenn das Reparaturtool für .NET Framework weitere Aktionen empfiehlt, etwa die in der folgenden Abbildung gezeigten, wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="bd5e3-114">If the .NET Framework Repair Tool recommends any additional action, such as those shown in the following figure, select **Next**.</span></span>

   ![Empfohlene Änderungen](media/application-not-started/repair-tool-recommended-changes.png)

1. <span data-ttu-id="bd5e3-116">Das Reparaturtool für .NET Framework zeigt ein Dialogfeld an (siehe Abbildung unten), um anzugeben, dass die Änderungen abgeschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="bd5e3-116">The .NET Framework Repair Tools displays a dialog box shown in the following figure to indicate that changes are complete.</span></span> <span data-ttu-id="bd5e3-117">Lassen Sie das Dialogfeld geöffnet, während Sie versuchen, die Anwendung erneut auszuführen.</span><span class="sxs-lookup"><span data-stu-id="bd5e3-117">Leave the dialog box open while you to try rerun your application.</span></span> <span data-ttu-id="bd5e3-118">Dies sollte erfolgreich sein, wenn das Reparaturtool für .NET Framework eine beschädigte .NET Framework-Installation identifiziert und korrigiert hat.</span><span class="sxs-lookup"><span data-stu-id="bd5e3-118">This should succeed if the .NET Framework Repair Tool has identified and corrected a corrupted .NET Framework installation.</span></span>

   ![Empfohlene Änderungen](media/application-not-started/repair-tool-changes-complete.png)

1. <span data-ttu-id="bd5e3-120">Wenn die Anwendung erfolgreich ausgeführt wird, klicken Sie auf die Schaltfläche **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="bd5e3-120">If your application runs successfully, select the **Finish** button.</span></span> <span data-ttu-id="bd5e3-121">Wählen Sie andernfalls die Schaltfläche **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="bd5e3-121">Otherwise, select the **Next** button.</span></span>

1. <span data-ttu-id="bd5e3-122">Wenn Sie die Schaltfläche **Weiter** ausgewählt haben, zeigt das Reparaturtool für .NET Framework ein Dialogfeld an, das wie das folgende Beispiel aussieht.</span><span class="sxs-lookup"><span data-stu-id="bd5e3-122">If you selected the **Next** button, the .NET Framework Repair Tool displays a dialog box like the following.</span></span> <span data-ttu-id="bd5e3-123">Wählen Sie die Schaltfläche **Fertig stellen** aus, um Diagnoseinformationen an Microsoft zu senden.</span><span class="sxs-lookup"><span data-stu-id="bd5e3-123">Select the **Finish** button to send diagnostic information to Microsoft.</span></span>

   ![Das Problem kann nicht gelöst werden](media/application-not-started/repair-tool-no-resolution.png)

1. <span data-ttu-id="bd5e3-125">Wenn Sie die Anwendung immer noch nicht ausführen können, installieren Sie die neueste Version von .NET Framework, die von Ihrer Windows-Version unterstützt wird, wie in der folgenden Tabelle gezeigt.</span><span class="sxs-lookup"><span data-stu-id="bd5e3-125">If you still cannot run the application, install the latest version of the .NET Framework supported by your version of Windows, as shown in the following table.</span></span>

   |<span data-ttu-id="bd5e3-126">Windows-Version</span><span class="sxs-lookup"><span data-stu-id="bd5e3-126">Windows version</span></span>|<span data-ttu-id="bd5e3-127">.NET Framework-Installation</span><span class="sxs-lookup"><span data-stu-id="bd5e3-127">.NET Framework installation</span></span>|
   |---|---|
   |<span data-ttu-id="bd5e3-128">Windows 10 Anniversary Update und höhere Versionen</span><span class="sxs-lookup"><span data-stu-id="bd5e3-128">Windows 10 Anniversary Update and later versions</span></span>|[<span data-ttu-id="bd5e3-129">.NET Framework 4.8 Runtime</span><span class="sxs-lookup"><span data-stu-id="bd5e3-129">.NET Framework 4.8 Runtime</span></span>](https://dotnet.microsoft.com/download/dotnet-framework/net48)|
   |<span data-ttu-id="bd5e3-130">Windows 10, Windows 10-Update von November</span><span class="sxs-lookup"><span data-stu-id="bd5e3-130">Windows 10, Windows 10 November Update</span></span>|[<span data-ttu-id="bd5e3-131">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="bd5e3-131">.NET Framework 4.6.2</span></span>](https://dotnet.microsoft.com/download/dotnet-framework/net462)|
   |<span data-ttu-id="bd5e3-132">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="bd5e3-132">Windows 8.1</span></span>|[<span data-ttu-id="bd5e3-133">.NET Framework 4.8 Runtime</span><span class="sxs-lookup"><span data-stu-id="bd5e3-133">.NET Framework 4.8 Runtime</span></span>](https://dotnet.microsoft.com/download/dotnet-framework/net48)|
   |<span data-ttu-id="bd5e3-134">Windows 8</span><span class="sxs-lookup"><span data-stu-id="bd5e3-134">Windows 8</span></span>|[<span data-ttu-id="bd5e3-135">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="bd5e3-135">.NET Framework 4.6.1</span></span>](https://dotnet.microsoft.com/download/dotnet-framework/net461)|
   |<span data-ttu-id="bd5e3-136">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="bd5e3-136">Windows 7 SP1</span></span>|[<span data-ttu-id="bd5e3-137">.NET Framework 4.8 Runtime</span><span class="sxs-lookup"><span data-stu-id="bd5e3-137">.NET Framework 4.8 Runtime</span></span>](https://dotnet.microsoft.com/download/dotnet-framework/net48)|
   |<span data-ttu-id="bd5e3-138">Windows Vista SP2</span><span class="sxs-lookup"><span data-stu-id="bd5e3-138">Windows Vista SP2</span></span>|[<span data-ttu-id="bd5e3-139">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="bd5e3-139">.NET Framework 4.6</span></span>](https://dotnet.microsoft.com/download/dotnet-framework/net46)|

   > [!NOTE]
   > <span data-ttu-id="bd5e3-140">.NET Framework 4.8 ist im Windows 10-Update von Mai 2019 vorinstalliert.</span><span class="sxs-lookup"><span data-stu-id="bd5e3-140">.NET Framework 4.8 is preinstalled on Windows 10 May 2019 Update.</span></span>

1. <span data-ttu-id="bd5e3-141">Versuchen Sie, die Anwendung zu starten.</span><span class="sxs-lookup"><span data-stu-id="bd5e3-141">Attempt to launch the application.</span></span>

1. <span data-ttu-id="bd5e3-142">In einigen Fällen wird möglicherweise ein Dialogfeld wie das folgende angezeigt, in dem Sie aufgefordert werden, .NET Framework 3.5 zu installieren.</span><span class="sxs-lookup"><span data-stu-id="bd5e3-142">In some cases, you may see a dialog box like the following, which asks you to install the .NET Framework 3.5.</span></span> <span data-ttu-id="bd5e3-143">Wählen Sie **Feature herunterladen und installieren** aus, um .NET Framework 3.5 zu installieren, und starten Sie die Anwendung dann erneut.</span><span class="sxs-lookup"><span data-stu-id="bd5e3-143">Select **Download and install this feature** to install the .NET Framework 3.5, then launch the application again.</span></span>

   ![Das Problem kann nicht gelöst werden](media/application-not-started/install-3-5.png)

## <a name="see-also"></a><span data-ttu-id="bd5e3-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bd5e3-145">See also</span></span>

- [<span data-ttu-id="bd5e3-146">Systemanforderungen für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="bd5e3-146">.NET Framework System Requirements</span></span>](../get-started/system-requirements.md)
- [<span data-ttu-id="bd5e3-147">Leitfaden für die Installation von .NET Framework</span><span class="sxs-lookup"><span data-stu-id="bd5e3-147">.NET Framework installation guide</span></span>](index.md)
- [<span data-ttu-id="bd5e3-148">Problembehandlung bei blockierten Installationen und Deinstallationen von .NET Framework</span><span class="sxs-lookup"><span data-stu-id="bd5e3-148">Troubleshoot blocked .NET Framework installations and uninstallations</span></span>](troubleshoot-blocked-installations-and-uninstallations.md)
