---
title: Developer-Eingabeaufforderung für Visual Studio.
ms.date: 01/05/2020
helpviewer_keywords:
- command prompt, Windows SDK
- Visual Studio command prompt
- command prompt, Visual Studio
- SDK command prompt
- tools [.NET Framework], setting environment variables
- environment variables, setting for tools
- developer command prompt
ms.assetid: 94fcf524-9045-4993-bfb2-e2d8bad44219
ms.openlocfilehash: f028281d477284acf3ac4dac63f5ddbbd79f5259
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715830"
---
# <a name="developer-command-prompt-for-visual-studio"></a><span data-ttu-id="93366-102">Developer-Eingabeaufforderung für Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="93366-102">Developer Command Prompt for Visual Studio</span></span>

<span data-ttu-id="93366-103">Mithilfe der Developer-Eingabeaufforderung für Visual Studio können Sie .NET Framework-Tools komfortabler verwenden.</span><span class="sxs-lookup"><span data-stu-id="93366-103">Developer Command Prompt for Visual Studio enables you to use .NET Framework tools more easily.</span></span> <span data-ttu-id="93366-104">Es handelt sich um eine Eingabeaufforderung, die automatisch bestimmte Umgebungsvariablen festlegt.</span><span class="sxs-lookup"><span data-stu-id="93366-104">It's a command prompt that automatically sets specific environment variables.</span></span> <span data-ttu-id="93366-105">Nachdem Sie die Developer-Eingabeaufforderung geöffnet haben, können Sie die Befehle für [.NET Framework-Tools](index.md) wie `ildasm` oder `clrver` eingeben.</span><span class="sxs-lookup"><span data-stu-id="93366-105">After opening Developer Command Prompt, you can enter the commands for [.NET Framework tools](index.md) such as `ildasm` or `clrver`.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="93366-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="93366-106">Prerequisites</span></span>

- [<span data-ttu-id="93366-107">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="93366-107">Visual Studio 2019</span></span>](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)

## <a name="search-for-the-command-prompt-on-your-machine"></a><span data-ttu-id="93366-108">Suchen nach der Eingabeaufforderung auf Ihrem Computer</span><span class="sxs-lookup"><span data-stu-id="93366-108">Search for the command prompt on your machine</span></span>

<span data-ttu-id="93366-109">Abhängig von der Version von Visual Studio und zusätzlich installierten SDKs und Workloads verfügen Sie möglicherweise über mehrere Eingabeaufforderungen.</span><span class="sxs-lookup"><span data-stu-id="93366-109">You may have multiple command prompts, depending on the version of Visual Studio and any additional SDKs and workloads you've installed.</span></span> <span data-ttu-id="93366-110">Wenn die folgenden Schritte nicht funktionieren, können Sie versuchen, [die Dateien manuell auf Ihrem Computer zu finden](#manually-locate-the-files-on-your-machine) oder [die Eingabeaufforderung innerhalb von Visual Studio zu starten](#start-the-command-prompt-from-inside-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="93366-110">If the following steps don't work, you can try to [manually locate the files on your machine](#manually-locate-the-files-on-your-machine) or [start the command prompt from inside Visual Studio](#start-the-command-prompt-from-inside-visual-studio).</span></span>

### <a name="windows-10"></a><span data-ttu-id="93366-111">Windows 10</span><span class="sxs-lookup"><span data-stu-id="93366-111">Windows 10</span></span>

1. <span data-ttu-id="93366-112">Wählen Sie **Start** ![Windows Logo-Taste auf der Tastatur starten aus](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png),</span><span class="sxs-lookup"><span data-stu-id="93366-112">Select **Start** ![Windows logo key on the keyboard.](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png)</span></span> <span data-ttu-id="93366-113">und scrollen Sie zum Buchstaben **V**.</span><span class="sxs-lookup"><span data-stu-id="93366-113">and scroll to the letter **V**.</span></span>

1. <span data-ttu-id="93366-114">Erweitern Sie den Ordner **Visual Studio 2019**.</span><span class="sxs-lookup"><span data-stu-id="93366-114">Expand the **Visual Studio 2019** folder.</span></span>

1. <span data-ttu-id="93366-115">Wählen Sie **Developer-Eingabeaufforderung für VS 2019** (oder die gewünschte Eingabeaufforderung) aus.</span><span class="sxs-lookup"><span data-stu-id="93366-115">Choose **Developer Command Prompt for VS 2019** (or the command prompt you want to use).</span></span>

   <span data-ttu-id="93366-116">Sie können auch beginnen, den Namen der Eingabeaufforderung in das Suchfeld auf der Taskleiste einzugeben, und das gewünschte Ergebnis auswählen, wenn die Ergebnisliste damit beginnt, um die Suchübereinstimmungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="93366-116">Alternatively, you can start typing the name of the command prompt in the search box on the taskbar, and choose the result you want as the result list starts to display the search matches.</span></span>

   ![Animierte GIF-Datei, die das Suchverhalten unter Windows 10 zeigt](./media/developer-command-prompt-for-vs/windows10-search.gif)

### <a name="windows-81"></a><span data-ttu-id="93366-118">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="93366-118">Windows 8.1</span></span>

1. <span data-ttu-id="93366-119">Wechseln Sie zum Bildschirm **Start**, indem Sie beispielsweise die Windows-Logo-Taste ![Windows-Logo-Taste auf der Tastatur](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png)</span><span class="sxs-lookup"><span data-stu-id="93366-119">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo key on the keyboard.](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png)</span></span> <span data-ttu-id="93366-120">auf der Tastatur drücken.</span><span class="sxs-lookup"><span data-stu-id="93366-120">on your keyboard for example.</span></span>

1. <span data-ttu-id="93366-121">Drücken Sie auf dem Bildschirm **Start** die Tastenkombination **STRG**+**TAB**, um die Liste **Apps** zu öffnen, und drücken Sie dann **V**. Dadurch wird eine Liste angezeigt, die alle installierten Visual Studio-Eingabeaufforderungen enthält.</span><span class="sxs-lookup"><span data-stu-id="93366-121">On the **Start** screen, press **Ctrl**+**Tab** to open the **Apps** list, and then press **V**. This brings up a list that includes all installed Visual Studio command prompts.</span></span>

1. <span data-ttu-id="93366-122">Wählen Sie **Developer-Eingabeaufforderung für VS 2019** (oder die gewünschte Eingabeaufforderung) aus.</span><span class="sxs-lookup"><span data-stu-id="93366-122">Choose **Developer Command Prompt for VS 2019** (or the command prompt you want to use).</span></span>

### <a name="windows-7"></a><span data-ttu-id="93366-123">Windows 7</span><span class="sxs-lookup"><span data-stu-id="93366-123">Windows 7</span></span>

1. <span data-ttu-id="93366-124">Wählen Sie **Start** aus, und erweitern Sie dann **Alle Programme**.</span><span class="sxs-lookup"><span data-stu-id="93366-124">Choose **Start** and then expand **All Programs**.</span></span>

1. <span data-ttu-id="93366-125">Wählen Sie die **Visual Studio 2019** > **Visual Studio-Tools** > **Developer-Eingabeaufforderung für VS 2019** oder die gewünschte Eingabeaufforderung aus.</span><span class="sxs-lookup"><span data-stu-id="93366-125">Choose **Visual Studio 2019** > **Visual Studio Tools** > **Developer Command Prompt for VS 2019**, or the command prompt you want to use.</span></span>

   ![Windows 7-Startmenü mit hervorgehobener Eingabeaufforderung](./media/developer-command-prompt-for-vs/windows7-menu.png)

<span data-ttu-id="93366-127">Wenn Sie andere SDKs installiert haben, z. B. das [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) oder [frühere Versionen](https://developer.microsoft.com/windows/downloads/sdk-archive), werden Ihnen möglicherweise zusätzliche Eingabeaufforderungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="93366-127">If you have other SDKs installed, such as the [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) or [previous versions](https://developer.microsoft.com/windows/downloads/sdk-archive), you may see additional command prompts.</span></span> <span data-ttu-id="93366-128">Informationen dazu, welche Version der Eingabeaufforderung Sie verwenden sollten, finden Sie in der Dokumentation der einzelnen Tools.</span><span class="sxs-lookup"><span data-stu-id="93366-128">Check the documentation for the individual tools to determine which version of the command prompt you should use.</span></span>

## <a name="manually-locate-the-files-on-your-machine"></a><span data-ttu-id="93366-129">Manuelles Suchen der Dateien auf Ihrem Computer</span><span class="sxs-lookup"><span data-stu-id="93366-129">Manually locate the files on your machine</span></span>

<span data-ttu-id="93366-130">In der Regel werden die Tastenkombinationen für die installierten Eingabeaufforderungen im Ordner **Start Menu** für Visual Studio platziert, beispielsweise in *%:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2019\Visual Studio Tools*.</span><span class="sxs-lookup"><span data-stu-id="93366-130">Usually, the shortcuts for the command prompts you have installed are placed at the **Start Menu** folder for Visual Studio, such as in *%ProgramData%\Microsoft\Windows\Start Menu\Programs\Visual Studio 2019\Visual Studio Tools*.</span></span> <span data-ttu-id="93366-131">Wenn die Suche nach der Eingabeaufforderung jedoch nicht die erwarteten Ergebnisse liefert, können Sie versuchen, die Tastenkombination manuell auf Ihrem Computer zu finden.</span><span class="sxs-lookup"><span data-stu-id="93366-131">But if, for some reason, searching for the command prompt doesn't produce the expected results, you can try to manually locate the shortcut on your machine.</span></span> <span data-ttu-id="93366-132">Suchen Sie z. B. den Namen der Eingabeaufforderungsdatei (z. B. *VsDevCmd.bat*), oder navigieren Sie zum Ordner „Tools“, z. B. unter *%Programme (x86)\Microsoft Visual Studio\2019\Community\Common7\Tools* (der Pfad kann gemäß der Version, der Edition und des Speicherorts von Visual Studio von diesem Beispiel abweichen).</span><span class="sxs-lookup"><span data-stu-id="93366-132">Try searching for the name of the command prompt file, such as *VsDevCmd.bat*, or go to the Tools folder, such as *%ProgramFiles(x86)%\Microsoft Visual Studio\2019\Community\Common7\Tools* (path changes according to your Visual Studio version, edition, and installation location).</span></span>

## <a name="start-the-command-prompt-from-inside-visual-studio"></a><span data-ttu-id="93366-133">Starten der Eingabeaufforderung aus Visual Studio</span><span class="sxs-lookup"><span data-stu-id="93366-133">Start the command prompt from inside Visual Studio</span></span>

<span data-ttu-id="93366-134">Für den einfacheren Zugriff können Sie dem Menü „Extras“ in Visual Studio die Developer-Eingabeaufforderung oder eine beliebige andere Eingabeaufforderung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="93366-134">For easier access, you can add Developer Command Prompt, or any other command prompt, to the Tools menu in Visual Studio.</span></span> <span data-ttu-id="93366-135">Fügen Sie das Tool der Liste externer Tools hinzu, damit Sie auf dieses zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="93366-135">To make the tool available, add it to the external tools list.</span></span> <span data-ttu-id="93366-136">Folgende Schritte müssen ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="93366-136">Here are the steps:</span></span>

1. <span data-ttu-id="93366-137">Öffnen Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="93366-137">Open Visual Studio.</span></span>

1. <span data-ttu-id="93366-138">Wählen Sie im Startfenster **Ohne Code fortfahren** aus.</span><span class="sxs-lookup"><span data-stu-id="93366-138">On the start window, choose **Continue without code**.</span></span>

1. <span data-ttu-id="93366-139">Klicken Sie in der Menüleiste auf **Extras** > **Externe Tools**.</span><span class="sxs-lookup"><span data-stu-id="93366-139">On the menu bar, choose **Tools** > **External Tools**.</span></span>

1. <span data-ttu-id="93366-140">Wählen Sie im Dialogfeld **Externe Tools** die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="93366-140">On the **External Tools** dialog box, choose the **Add** button.</span></span> <span data-ttu-id="93366-141">Ein neuer Eintrag wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="93366-141">A new entry appears.</span></span>

1. <span data-ttu-id="93366-142">Geben Sie einen **Titel** für das neue Menüelement ein, z.B. `Command Prompt`.</span><span class="sxs-lookup"><span data-stu-id="93366-142">Enter a **Title** for your new menu item such as `Command Prompt`.</span></span>

1. <span data-ttu-id="93366-143">Geben Sie im Feld **Befehl** die Datei an, die Sie starten möchten, z.B. `%comspec%` oder `C:\Windows\System32\cmd.exe`.</span><span class="sxs-lookup"><span data-stu-id="93366-143">In the **Command** field, specify the file you want to launch, such as `%comspec%` or `C:\Windows\System32\cmd.exe`.</span></span>

1. <span data-ttu-id="93366-144">Geben Sie im Feld **Argumente** an, wo sich die bestimmte Eingabeaufforderung befindet, die Sie verwenden möchten, z. B. `/k "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\Common7\Tools\VsDevCmd.bat"`.</span><span class="sxs-lookup"><span data-stu-id="93366-144">In the **Arguments** field, specify where to find the specific command prompt you want to use, such as `/k "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\Common7\Tools\VsDevCmd.bat"`.</span></span> <span data-ttu-id="93366-145">Mit diesem Befehl wird die Developer-Eingabeaufforderung gestartet, die mit Visual Studio 2019 Community installiert wird.</span><span class="sxs-lookup"><span data-stu-id="93366-145">This command launches the Developer Command Prompt that's installed with Visual Studio 2019 Community.</span></span> <span data-ttu-id="93366-146">Ändern Sie diesen Wert entsprechend der Version, der Edition und dem Installationsspeicherort von Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="93366-146">Change this value according to your Visual Studio version, edition, and installation location.</span></span>

1. <span data-ttu-id="93366-147">Geben Sie im Feld **Ausgangsverzeichnis** das Verzeichnis an, in dem die Eingabeaufforderung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="93366-147">In the **Initial directory** field, specify the directory in which the command prompt will start.</span></span> <span data-ttu-id="93366-148">Wählen Sie einen Wert wie **Projektverzeichnis** aus, indem Sie den Pfeil neben dem Feld auswählen.</span><span class="sxs-lookup"><span data-stu-id="93366-148">Choose a value such as **Project Directory** by selecting the arrow next to the field.</span></span>

1. <span data-ttu-id="93366-149">Klicken Sie auf die Schaltfläche **OK** .</span><span class="sxs-lookup"><span data-stu-id="93366-149">Choose the **OK** button.</span></span>

   ![Dialogfeld „Externe Tools“ mit ausgefüllten Feldwerten.](./media/developer-command-prompt-for-vs/add-external-tool.png)

   <span data-ttu-id="93366-151">Das neue Menüelement wird hinzugefügt, und Sie können über das Menü „Extras“ auf die Eingabeaufforderung zugreifen.</span><span class="sxs-lookup"><span data-stu-id="93366-151">The new menu item is added, and you can access the command prompt from the Tools menu.</span></span>

   ![Menüelement „Eingabeaufforderung“ in Visual Studio](./media/developer-command-prompt-for-vs/command-prompt-vs-menu.png)

## <a name="see-also"></a><span data-ttu-id="93366-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="93366-153">See also</span></span>

- [<span data-ttu-id="93366-154">.NET Framework-Tools</span><span class="sxs-lookup"><span data-stu-id="93366-154">.NET Framework Tools</span></span>](index.md)
- [<span data-ttu-id="93366-155">Verwalten von externen Tools</span><span class="sxs-lookup"><span data-stu-id="93366-155">Managing External Tools</span></span>](/visualstudio/ide/managing-external-tools)
- [<span data-ttu-id="93366-156">Verwenden des Microsoft C++-Toolsets in der Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="93366-156">Use the Microsoft C++ toolset from the command line</span></span>](/cpp/build/building-on-the-command-line)
