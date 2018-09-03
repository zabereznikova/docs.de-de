---
title: Developer-Eingabeaufforderung für Visual Studio.
ms.date: 08/14/2018
helpviewer_keywords:
- command prompt, Windows SDK
- Visual Studio command prompt
- command prompt, Visual Studio
- SDK command prompt
- tools [.NET Framework], setting environment variables
- environment variables, setting for tools
- developer command prompt
ms.assetid: 94fcf524-9045-4993-bfb2-e2d8bad44219
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4c95074190419dd3e984c7659ede917b83b97f08
ms.sourcegitcommit: a1e35d4e94edab384a63406c0a5438306873031b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2018
ms.locfileid: "42754260"
---
# <a name="developer-command-prompt-for-visual-studio"></a><span data-ttu-id="2e56c-102">Developer-Eingabeaufforderung für Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2e56c-102">Developer Command Prompt for Visual Studio</span></span>

<span data-ttu-id="2e56c-103">Die Developer-Eingabeaufforderung für Visual Studio legt die Umgebungsvariablen, die Ihnen die einfache Nutzung von .NET Framework-Tools ermöglichen, automatisch fest.</span><span class="sxs-lookup"><span data-stu-id="2e56c-103">The Developer Command Prompt for Visual Studio automatically sets the environment variables that enable you to easily use .NET Framework tools.</span></span>

> [!div class="button"]
[<span data-ttu-id="2e56c-104">Herunterladen von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2e56c-104">Download Visual Studio</span></span>](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)

## <a name="searching-for-the-command-prompt-on-your-machine"></a><span data-ttu-id="2e56c-105">Suchen nach der Eingabeaufforderung auf Ihrem Computer</span><span class="sxs-lookup"><span data-stu-id="2e56c-105">Searching for the command prompt on your machine</span></span>

<span data-ttu-id="2e56c-106">Abhängig von der Version von Visual Studio und jeglichen zusätzlichen installierten SDKs verfügen Sie möglicherweise über mehrere Eingabeaufforderungen.</span><span class="sxs-lookup"><span data-stu-id="2e56c-106">You may have multiple command prompts, depending on the version of Visual Studio and any additional SDKs you've installed.</span></span> <span data-ttu-id="2e56c-107">Beispielsweise stellen 64-Bit-Versionen von Visual Studio sowohl 32-Bit- als auch 64-Bit-Eingabeaufforderungen bereit.</span><span class="sxs-lookup"><span data-stu-id="2e56c-107">For example, 64-bit versions of Visual Studio provide both 32-bit and 64-bit command prompts.</span></span> <span data-ttu-id="2e56c-108">(Die 32-Bit- und 64-Bit-Versionen der meisten Tools sind identisch. Möglicherweise nehmen jedoch einige Tools bestimmte Änderungen an der 32-Bit- bzw. der 64-Bit-Umgebung vor.) Wenn die folgenden Schritte nicht funktionieren, können Sie versuchen, [die Dateien manuell auf Ihrem Computer zu finden](#manually-locating-the-files-on-your-machine) oder [die Eingabeaufforderung innerhalb von Visual Studio auszuführen](#running-command-prompt-from-inside-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="2e56c-108">(The 32-bit and 64-bit versions of most tools are the same; however, a few tools make changes specific to 32-bit and 64-bit environments.) If the following steps don't work, you can try [Manually locating the files on your machine](#manually-locating-the-files-on-your-machine) or [Running the command prompt from inside Visual Studio](#running-command-prompt-from-inside-visual-studio).</span></span>

### <a name="in-windows-10"></a><span data-ttu-id="2e56c-109">In Windows 10</span><span class="sxs-lookup"><span data-stu-id="2e56c-109">In Windows 10</span></span>

1. <span data-ttu-id="2e56c-110">Geben Sie den Namen des Tools im Suchfeld auf der Taskleiste ein, z.B. `dev` oder `developer command prompt`.</span><span class="sxs-lookup"><span data-stu-id="2e56c-110">In the search box on the taskbar, start typing the name of the tool, such as `dev` or `developer command prompt`.</span></span> <span data-ttu-id="2e56c-111">Dadurch wird eine Liste der installierten Apps angezeigt, die Ihrem Suchmuster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e56c-111">This brings up a list of installed apps that match your search pattern.</span></span> <span data-ttu-id="2e56c-112">Wenn Sie nach einer anderen Eingabeaufforderung suchen, geben Sie einen anderen Suchbegriff als `prompt` ein.</span><span class="sxs-lookup"><span data-stu-id="2e56c-112">If you're looking for a different command prompt, try entering a different search term such as `prompt`.</span></span>

2. <span data-ttu-id="2e56c-113">Wählen Sie **Developer-Eingabeaufforderung** (oder die gewünschte Eingabeaufforderung) aus.</span><span class="sxs-lookup"><span data-stu-id="2e56c-113">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>

### <a name="in-windows-81"></a><span data-ttu-id="2e56c-114">Unter Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="2e56c-114">In Windows 8.1</span></span>

1. <span data-ttu-id="2e56c-115">Wechseln Sie zum Bildschirm **Start**, indem Sie beispielsweise die Windows-Logo-Taste ![Windows-Logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") auf der Tastatur drücken.</span><span class="sxs-lookup"><span data-stu-id="2e56c-115">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>

2. <span data-ttu-id="2e56c-116">Drücken Sie auf dem Bildschirm **Start** `CTRL + TAB`, um die Liste **Apps** zu öffnen, und geben Sie anschließend `V` ein.</span><span class="sxs-lookup"><span data-stu-id="2e56c-116">On the **Start** screen, press `CTRL + TAB` to open the **Apps** list and then enter `V`.</span></span> <span data-ttu-id="2e56c-117">Dadurch wird eine Liste angezeigt, die alle installierten Visual Studio-Eingabeaufforderungen enthält.</span><span class="sxs-lookup"><span data-stu-id="2e56c-117">This brings a list that includes all installed Visual Studio command prompts.</span></span>

3. <span data-ttu-id="2e56c-118">Wählen Sie **Developer-Eingabeaufforderung** (oder die gewünschte Eingabeaufforderung) aus.</span><span class="sxs-lookup"><span data-stu-id="2e56c-118">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>

### <a name="in-windows-8"></a><span data-ttu-id="2e56c-119">Unter Windows 8</span><span class="sxs-lookup"><span data-stu-id="2e56c-119">In Windows 8</span></span>

1. <span data-ttu-id="2e56c-120">Wechseln Sie zum Bildschirm **Start**, indem Sie beispielsweise die Windows-Logo-Taste ![Windows-Logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") auf der Tastatur drücken.</span><span class="sxs-lookup"><span data-stu-id="2e56c-120">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>

2. <span data-ttu-id="2e56c-121">Drücken Sie auf dem Bildschirm **Start** die Windows-Logo-Taste ![Windows-Logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`.</span><span class="sxs-lookup"><span data-stu-id="2e56c-121">On the **Start** screen, press the Windows logo key ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`.</span></span>

3. <span data-ttu-id="2e56c-122">Wählen Sie im unteren Bereich des Bildschirms das Symbol **Apps-Ansicht** aus, und geben Sie anschließend `V` ein.</span><span class="sxs-lookup"><span data-stu-id="2e56c-122">Choose the **Apps view** icon at the bottom of the screen and then enter `V`.</span></span> <span data-ttu-id="2e56c-123">Dadurch wird eine Liste angezeigt, die alle installierten Visual Studio-Eingabeaufforderungen enthält.</span><span class="sxs-lookup"><span data-stu-id="2e56c-123">This brings a list that includes all installed Visual Studio command prompts.</span></span>

4. <span data-ttu-id="2e56c-124">Wählen Sie **Developer-Eingabeaufforderung** (oder die gewünschte Eingabeaufforderung) aus.</span><span class="sxs-lookup"><span data-stu-id="2e56c-124">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>

### <a name="in-windows-7"></a><span data-ttu-id="2e56c-125">Unter Windows 7</span><span class="sxs-lookup"><span data-stu-id="2e56c-125">In Windows 7</span></span>

1. <span data-ttu-id="2e56c-126">Wählen Sie **Start** aus, erweitern Sie **Alle Programme**, und erweitern Sie anschließend **Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="2e56c-126">Choose **Start**, expand **All Programs**, and then expand **Microsoft Visual Studio**.</span></span>

2. <span data-ttu-id="2e56c-127">Wählen Sie abhängig von der installierten Visual Studio-Version **Visual Studio-Tools**, **Visual Studio-Eingabeaufforderung** oder die gewünschte Eingabeaufforderung aus.</span><span class="sxs-lookup"><span data-stu-id="2e56c-127">Depending on the version of Visual Studio you've installed, choose  **Visual Studio Tools**, **Visual Studio Command Prompt**, or the command prompt you want to use.</span></span>

<span data-ttu-id="2e56c-128">Wenn Sie andere SDKs installiert haben, z.B. das [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) oder [frühere Versionen](https://developer.microsoft.com/windows/downloads/sdk-archive), werden Ihnen möglicherweise zusätzliche Eingabeaufforderungen für ARM-, x86- oder x64-Architekturen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2e56c-128">If you have other SDKs installed, such as the [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) or [previous versions](https://developer.microsoft.com/windows/downloads/sdk-archive), you may see additional command prompts for ARM, x86, or x64 architectures.</span></span> <span data-ttu-id="2e56c-129">Informationen dazu, welche Version der Eingabeaufforderung Sie verwenden sollten, finden Sie in der Dokumentation der einzelnen Tools.</span><span class="sxs-lookup"><span data-stu-id="2e56c-129">Check the documentation for the individual tools to determine which version of the command prompt you should use.</span></span>

## <a name="manually-locate-the-files-on-your-machine"></a><span data-ttu-id="2e56c-130">Manuelles Suchen der Dateien auf Ihrem Computer</span><span class="sxs-lookup"><span data-stu-id="2e56c-130">Manually locate the files on your machine</span></span>

<span data-ttu-id="2e56c-131">In der Regel werden die Tastenkombinationen für die installierten Eingabeaufforderungen im Ordner **Start Menu** für Visual Studio platziert, beispielsweise in „C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2017\Visual Studio Tools“.</span><span class="sxs-lookup"><span data-stu-id="2e56c-131">Usually, the shortcuts for the command prompts you have installed are placed at the **Start Menu** folder for Visual Studio, such as in C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2017\Visual Studio Tools.</span></span> <span data-ttu-id="2e56c-132">Wenn die Suche nach der Eingabeaufforderung jedoch nicht die erwarteten Ergebnisse liefert, können Sie versuchen, die Tastenkombination manuell auf Ihrem Computer zu finden.</span><span class="sxs-lookup"><span data-stu-id="2e56c-132">But if for some reason, searching for the command prompt doesn't bring the expected results, you can try to manually locate the shortcut on your machine.</span></span> <span data-ttu-id="2e56c-133">Suchen Sie z.B. den Namen der Eingabeaufforderungsdatei (z.B. *VsDevCmd.bat*), oder wechseln Sie zum Ordner „Tools“, z.B. unter „ C:\Programme (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools“ (der Pfad kann gemäß der Version, der Edition und des Speicherorts von Visual Studio von diesem Beispiel abweichen).</span><span class="sxs-lookup"><span data-stu-id="2e56c-133">Try searching for the name of the command prompt file, such as *VsDevCmd.bat*, or go to the Tools folder such as C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools (path changes according to your Visual Studio version, edition, and installation location).</span></span>

## <a name="run-command-prompt-from-inside-visual-studio"></a><span data-ttu-id="2e56c-134">Ausführen der Eingabeaufforderung innerhalb von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2e56c-134">Run command prompt from inside Visual Studio</span></span>

<span data-ttu-id="2e56c-135">Für den einfacheren Zugriff können Sie die Developer-Eingabeaufforderung von Visual Studio oder eine beliebige andere Eingabeaufforderung zum Menü **Extras** in Visual Studio hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="2e56c-135">For easier access, you can add the Visual Studio Developer Command Prompt, or any other command prompt, to the **Tools** menu in Visual Studio.</span></span> <span data-ttu-id="2e56c-136">Fügen Sie das Tool der Liste externer Tools hinzu, damit Sie auf dieses zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="2e56c-136">To make the tool available, add it to the external tools list.</span></span> <span data-ttu-id="2e56c-137">Folgende Schritte müssen ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="2e56c-137">Here are the steps:</span></span>

1. <span data-ttu-id="2e56c-138">Öffnen Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2e56c-138">Open Visual Studio.</span></span>

2. <span data-ttu-id="2e56c-139">Klicken Sie auf das Menü **Extras**, und wählen Sie dann **Externe Tools** aus.</span><span class="sxs-lookup"><span data-stu-id="2e56c-139">Select the **Tools** menu, and then choose **External Tools**.</span></span>

3. <span data-ttu-id="2e56c-140">Wählen Sie im Dialogfeld **Externe Tools** die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="2e56c-140">On the **External Tools** dialog box, choose the **Add** button.</span></span> <span data-ttu-id="2e56c-141">Ein neuer Eintrag wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2e56c-141">A new entry appears.</span></span>

4. <span data-ttu-id="2e56c-142">Geben Sie einen **Titel** für das neue Menüelement ein, z.B. `Command Prompt`.</span><span class="sxs-lookup"><span data-stu-id="2e56c-142">Enter a **Title** for your new menu item such as `Command Prompt`.</span></span>

5. <span data-ttu-id="2e56c-143">Geben Sie im Feld **Befehl** die Datei an, die Sie starten möchten, z.B. `%comspec%` oder `C:\Windows\System32\cmd.exe`.</span><span class="sxs-lookup"><span data-stu-id="2e56c-143">In the **Command** field, specify the file you want to launch, such as `%comspec%` or `C:\Windows\System32\cmd.exe`.</span></span>

6. <span data-ttu-id="2e56c-144">Geben Sie im Feld **Argumente** an, wo diejenige Eingabeaufforderung, die Sie verwenden möchten, zu finden ist, z.B. `/k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools\VsDevCmd.bat"` (dieser Befehl startet die Developer-Eingabeaufforderung, die mit Visual Studio 2017 Enterprise installiert wurde).</span><span class="sxs-lookup"><span data-stu-id="2e56c-144">In the **Arguments** field, specify where to find the specific command prompt you want to use such as `/k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools\VsDevCmd.bat"` (this command launches the Developer Command Prompt that is installed with Visual Studio 2017 Enterprise).</span></span> <span data-ttu-id="2e56c-145">Ändern Sie diesen Wert entsprechend der Version, der Edition und dem Installationsspeicherort von Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2e56c-145">Change this value according to your Visual Studio version, edition, and installation location.</span></span>

7. <span data-ttu-id="2e56c-146">Wählen Sie einen Wert für das Feld **Ausgangsverzeichnis** aus, z.B. **Projektverzeichnis**.</span><span class="sxs-lookup"><span data-stu-id="2e56c-146">Choose a value for the **Initial directory** field, such as **Project Directory**.</span></span>

8. <span data-ttu-id="2e56c-147">Klicken Sie auf die Schaltfläche **OK** .</span><span class="sxs-lookup"><span data-stu-id="2e56c-147">Choose the **OK** button.</span></span>

   <span data-ttu-id="2e56c-148">Das neue Menüelement wird hinzugefügt, und Sie können über das Menü **Extras** auf die Eingabeaufforderung zugreifen.</span><span class="sxs-lookup"><span data-stu-id="2e56c-148">The new menu item is added, and you can access the command prompt from the **Tools** menu.</span></span>

## <a name="see-also"></a><span data-ttu-id="2e56c-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e56c-149">See also</span></span>

- [<span data-ttu-id="2e56c-150">Extras</span><span class="sxs-lookup"><span data-stu-id="2e56c-150">Tools</span></span>](../../../docs/framework/tools/index.md)
- [<span data-ttu-id="2e56c-151">Verwalten von externen Tools</span><span class="sxs-lookup"><span data-stu-id="2e56c-151">Managing External Tools</span></span>](/visualstudio/ide/managing-external-tools)
