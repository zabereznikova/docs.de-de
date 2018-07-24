---
title: Developer-Eingabeaufforderung für Visual Studio.
ms.date: 06/18/2018
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
ms.openlocfilehash: 8e64facffd4face929b28d660ffd5210f127c3bd
ms.sourcegitcommit: c217b067985905cb21eafc5dd9a83568d7ff4e45
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2018
ms.locfileid: "36315224"
---
# <a name="developer-command-prompt-for-visual-studio"></a><span data-ttu-id="fcaa9-102">Developer-Eingabeaufforderung für Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fcaa9-102">Developer Command Prompt for Visual Studio</span></span>

<span data-ttu-id="fcaa9-103">Die Developer-Eingabeaufforderung für Visual Studio legt die Umgebungsvariablen, die Ihnen die einfache Nutzung von .NET Framework-Tools ermöglichen, automatisch fest.</span><span class="sxs-lookup"><span data-stu-id="fcaa9-103">The Developer Command Prompt for Visual Studio automatically sets the environment variables that enable you to easily use .NET Framework tools.</span></span> <span data-ttu-id="fcaa9-104">Die Developer-Eingabeaufforderung wird mit vollständigen oder Community-Editionen von Visual Studio installiert.</span><span class="sxs-lookup"><span data-stu-id="fcaa9-104">The Developer Command Prompt is installed with full or community editions of Visual Studio.</span></span> <span data-ttu-id="fcaa9-105">Sie wird nicht mit den Express-Versionen von Visual Studio installiert.</span><span class="sxs-lookup"><span data-stu-id="fcaa9-105">It isn't installed with the Express versions of Visual Studio.</span></span>

> [!div class="button"]
[<span data-ttu-id="fcaa9-106">Herunterladen von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fcaa9-106">Download Visual Studio</span></span>](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)

## <a name="searching-for-the-command-prompt-on-your-machine"></a><span data-ttu-id="fcaa9-107">Suchen nach der Eingabeaufforderung auf Ihrem Computer</span><span class="sxs-lookup"><span data-stu-id="fcaa9-107">Searching for the Command Prompt on your machine</span></span>

<span data-ttu-id="fcaa9-108">Je nach Version von Visual Studio und den installierten zusätzlichen SDKs werden möglicherweise mehrere Eingabeaufforderungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fcaa9-108">You may see many command prompts, depending on the version of Visual Studio and any additional SDKs you've installed.</span></span> <span data-ttu-id="fcaa9-109">Beispielsweise stellen 64-Bit-Versionen von Visual Studio sowohl 32-Bit- als auch 64-Bit-Eingabeaufforderungen bereit.</span><span class="sxs-lookup"><span data-stu-id="fcaa9-109">For example, 64-bit versions of Visual Studio provide both 32-bit and 64-bit command prompts.</span></span> <span data-ttu-id="fcaa9-110">(Die 32-Bit- und 64-Bit-Versionen der meisten Tools sind identisch. Möglicherweise nehmen jedoch einige Tools bestimmte Änderungen an der 32-Bit- bzw. der 64-Bit-Umgebung vor.) Wenn die folgenden Schritte nicht funktionieren, können Sie versuchen, [die Dateien manuell auf Ihrem Computer zu finden](#manually-locating-the-files-on-your-machine) oder [die Eingabeaufforderung innerhalb von Visual Studio auszuführen](#running-command-prompt-from-inside-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="fcaa9-110">(The 32-bit and 64-bit versions of most tools are the same; however, a few tools make changes specific to 32-bit and 64-bit environments.) If the following steps don't work, you can try [Manually locating the files on your machine](#manually-locating-the-files-on-your-machine) or [Running command prompt from inside Visual Studio](#running-command-prompt-from-inside-visual-studio).</span></span>

### <a name="in-windows-10"></a><span data-ttu-id="fcaa9-111">In Windows 10</span><span class="sxs-lookup"><span data-stu-id="fcaa9-111">In Windows 10</span></span>

1. <span data-ttu-id="fcaa9-112">Geben Sie den Namen des Tools im Suchfeld auf der Taskleiste ein, z.B. `dev` oder `developer command prompt`.</span><span class="sxs-lookup"><span data-stu-id="fcaa9-112">In the search box on the taskbar, start typing the name of the tool, such as `dev` or `developer command prompt`.</span></span> <span data-ttu-id="fcaa9-113">Dadurch wird eine Liste der installierten Apps angezeigt, die Ihrem Suchmuster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="fcaa9-113">This brings a list of installed apps that match your search pattern.</span></span> <span data-ttu-id="fcaa9-114">Wenn Sie nach einer anderen Eingabeaufforderung suchen, geben Sie einen anderen Suchbegriff als `prompt` ein.</span><span class="sxs-lookup"><span data-stu-id="fcaa9-114">If you're looking for a different command prompt, try entering a different search term such as `prompt`.</span></span>

2. <span data-ttu-id="fcaa9-115">Wählen Sie **Developer-Eingabeaufforderung** (oder die gewünschte Eingabeaufforderung) aus.</span><span class="sxs-lookup"><span data-stu-id="fcaa9-115">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>

### <a name="in-windows-81"></a><span data-ttu-id="fcaa9-116">Unter Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="fcaa9-116">In Windows 8.1</span></span>

1. <span data-ttu-id="fcaa9-117">Wechseln Sie zum Bildschirm **Start**, indem Sie beispielsweise die Windows-Logo-Taste ![Windows-Logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") auf der Tastatur drücken.</span><span class="sxs-lookup"><span data-stu-id="fcaa9-117">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>

2. <span data-ttu-id="fcaa9-118">Drücken Sie auf dem Bildschirm **Start** `CTRL + TAB`, um die Liste **Apps** zu öffnen, und geben Sie anschließend `V` ein.</span><span class="sxs-lookup"><span data-stu-id="fcaa9-118">On the **Start** screen, press `CTRL + TAB` to open the **Apps** list and then enter `V`.</span></span> <span data-ttu-id="fcaa9-119">Dadurch wird eine Liste angezeigt, die alle installierten Visual Studio-Eingabeaufforderungen enthält.</span><span class="sxs-lookup"><span data-stu-id="fcaa9-119">This brings a list that includes all installed Visual Studio command prompts.</span></span>

3. <span data-ttu-id="fcaa9-120">Wählen Sie **Developer-Eingabeaufforderung** (oder die gewünschte Eingabeaufforderung) aus.</span><span class="sxs-lookup"><span data-stu-id="fcaa9-120">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>

### <a name="in-windows-8"></a><span data-ttu-id="fcaa9-121">Unter Windows 8</span><span class="sxs-lookup"><span data-stu-id="fcaa9-121">In Windows 8</span></span>

1. <span data-ttu-id="fcaa9-122">Wechseln Sie zum Bildschirm **Start**, indem Sie beispielsweise die Windows-Logo-Taste ![Windows-Logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") auf der Tastatur drücken.</span><span class="sxs-lookup"><span data-stu-id="fcaa9-122">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>

2. <span data-ttu-id="fcaa9-123">Drücken Sie auf dem Bildschirm **Start** die Windows-Logo-Taste ![Windows-Logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`.</span><span class="sxs-lookup"><span data-stu-id="fcaa9-123">On the **Start** screen, press the Windows logo key ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`.</span></span>

3. <span data-ttu-id="fcaa9-124">Wählen Sie im unteren Bereich des Bildschirms das Symbol **Apps-Ansicht** aus, und geben Sie anschließend `V` ein.</span><span class="sxs-lookup"><span data-stu-id="fcaa9-124">Choose the **Apps view** icon at the bottom of the screen and then enter `V`.</span></span> <span data-ttu-id="fcaa9-125">Dadurch wird eine Liste angezeigt, die alle installierten Visual Studio-Eingabeaufforderungen enthält.</span><span class="sxs-lookup"><span data-stu-id="fcaa9-125">This brings a list that includes all installed Visual Studio command prompts.</span></span>

4. <span data-ttu-id="fcaa9-126">Wählen Sie **Developer-Eingabeaufforderung** (oder die gewünschte Eingabeaufforderung) aus.</span><span class="sxs-lookup"><span data-stu-id="fcaa9-126">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>

### <a name="in-windows-7"></a><span data-ttu-id="fcaa9-127">Unter Windows 7</span><span class="sxs-lookup"><span data-stu-id="fcaa9-127">In Windows 7</span></span>

1. <span data-ttu-id="fcaa9-128">Wählen Sie **Start** aus, erweitern Sie **Alle Programme**, und erweitern Sie anschließend **Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="fcaa9-128">Choose **Start**, expand **All Programs**, and then expand **Microsoft Visual Studio**.</span></span>

2. <span data-ttu-id="fcaa9-129">Wählen Sie abhängig von der installierten Visual Studio-Version **Visual Studio-Tools**, **Visual Studio-Eingabeaufforderung** oder die gewünschte Eingabeaufforderung aus.</span><span class="sxs-lookup"><span data-stu-id="fcaa9-129">Depending on the version of Visual Studio you've installed, choose  **Visual Studio Tools**, **Visual Studio Command Prompt**, or the command prompt you want to use.</span></span>

<span data-ttu-id="fcaa9-130">Wenn Sie andere SDKs wie das [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) oder [frühere Versionen](https://developer.microsoft.com/windows/downloads/sdk-archive) installiert haben, werden möglicherweise zusätzliche Eingabeaufforderungen für ARM-, x86- oder x64-Architekturen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fcaa9-130">If you have other SDKs installed such as the [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) or [previous versions](https://developer.microsoft.com/windows/downloads/sdk-archive) installed, you may see additional command prompts for ARM, x86, or x64 architectures.</span></span> <span data-ttu-id="fcaa9-131">Informationen dazu, welche Version der Eingabeaufforderung Sie verwenden sollten, finden Sie in der Dokumentation der einzelnen Tools.</span><span class="sxs-lookup"><span data-stu-id="fcaa9-131">Check the documentation for the individual tools to determine which version of the command prompt you should use.</span></span>

## <a name="manually-locating-the-files-on-your-machine"></a><span data-ttu-id="fcaa9-132">Manuelles Suchen der Dateien auf Ihrem Computer</span><span class="sxs-lookup"><span data-stu-id="fcaa9-132">Manually locating the files on your machine</span></span>

<span data-ttu-id="fcaa9-133">In der Regel werden die Tastenkombinationen für die installierten Eingabeaufforderungen im Ordner **Start Menu** für Visual Studio platziert, beispielsweise in „C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2017\Visual Studio Tools“.</span><span class="sxs-lookup"><span data-stu-id="fcaa9-133">Usually, the shortcuts for the command prompts you have installed are placed at the **Start Menu** folder for Visual Studio, such as in C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2017\Visual Studio Tools.</span></span> <span data-ttu-id="fcaa9-134">Wenn die Suche nach der Eingabeaufforderung jedoch nicht die erwarteten Ergebnisse liefert, können Sie versuchen, die Tastenkombination manuell auf Ihrem Computer zu finden.</span><span class="sxs-lookup"><span data-stu-id="fcaa9-134">But if for some reason, searching for the command prompt doesn't bring the expected results, you can try to manually locate the shortcut on your machine.</span></span> <span data-ttu-id="fcaa9-135">Suchen Sie z.B. den Namen der Eingabeaufforderungsdatei (z.B. *VsDevCmd.bat*), oder wechseln Sie zum Ordner „Tools“, z.B. unter „ C:\Programme (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools“ (der Pfad kann gemäß der Version, der Edition und des Speicherorts von Visual Studio von diesem Beispiel abweichen).</span><span class="sxs-lookup"><span data-stu-id="fcaa9-135">Try searching for the name of the command prompt file, such as *VsDevCmd.bat*, or go to the Tools folder such as C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools (path changes according to your Visual Studio version, edition, and installation location).</span></span>

## <a name="running-command-prompt-from-inside-visual-studio"></a><span data-ttu-id="fcaa9-136">Ausführen der Eingabeaufforderung innerhalb von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fcaa9-136">Running command prompt from inside Visual Studio</span></span>

<span data-ttu-id="fcaa9-137">Für den einfacheren Zugriff können Sie die Developer-Eingabeaufforderung von Visual Studio oder eine beliebige andere Eingabeaufforderung zum Menü „Extras“ in Visual Studio hinzufügen, indem Sie sie zur Liste der externen Tools hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fcaa9-137">For easier access, you can add the Visual Studio Developer Command Prompt  or any other command prompt to the Tools menu on Visual Studio, by adding it to the external tools list.</span></span> <span data-ttu-id="fcaa9-138">Dazu gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="fcaa9-138">This is how you can accomplish that:</span></span>

1. <span data-ttu-id="fcaa9-139">Öffnen Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fcaa9-139">Open Visual Studio.</span></span>

2. <span data-ttu-id="fcaa9-140">Wählen Sie das Menü **Extras** und anschließend **Externe Tools** aus.</span><span class="sxs-lookup"><span data-stu-id="fcaa9-140">Select the **Tools** menu and choose **External Tools**.</span></span>

3. <span data-ttu-id="fcaa9-141">Wählen Sie im Dialogfeld **Externe Tools** die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="fcaa9-141">On the **External Tools** dialog box, choose the **Add** button.</span></span> <span data-ttu-id="fcaa9-142">Ein neuer Eintrag wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fcaa9-142">A new entry appears.</span></span>

4. <span data-ttu-id="fcaa9-143">Geben Sie einen **Titel** für das neue Menüelement ein, z.B. `Command Prompt`.</span><span class="sxs-lookup"><span data-stu-id="fcaa9-143">Enter a **Title** for your new menu item such as `Command Prompt`.</span></span>

5. <span data-ttu-id="fcaa9-144">Geben Sie im Feld **Befehl** die Datei an, die Sie starten möchten, z.B. `%comspec%` oder `C:\Windows\System32\cmd.exe`.</span><span class="sxs-lookup"><span data-stu-id="fcaa9-144">In the **Command** field, specify the file you want to launch such as `%comspec%` or `C:\Windows\System32\cmd.exe`.</span></span>

6. <span data-ttu-id="fcaa9-145">Geben Sie im Feld **Argumente** an, wo diejenige Eingabeaufforderung, die Sie verwenden möchten, zu finden ist, z.B. `/k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools\VsDevCmd.bat"` (dieser Befehl startet die Developer-Eingabeaufforderung, die mit Visual Studio 2017 Enterprise installiert wurde).</span><span class="sxs-lookup"><span data-stu-id="fcaa9-145">In the **Arguments** field, specify where to find the specific command prompt you want to use such as `/k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools\VsDevCmd.bat"` (this command launches the Developer Command Prompt that is installed with Visual Studio 2017 Enterprise).</span></span> <span data-ttu-id="fcaa9-146">Ändern Sie diesen Wert entsprechend der Version, der Edition und dem Installationsspeicherort von Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fcaa9-146">Change this value according to your Visual Studio version, edition, and installation location.</span></span>

7. <span data-ttu-id="fcaa9-147">Wählen Sie einen Wert für das Feld **Ausgangsverzeichnis** aus, z.B. **Projektverzeichnis**.</span><span class="sxs-lookup"><span data-stu-id="fcaa9-147">Choose a value for the **Initial directory** field such as **Project Directory**.</span></span>

8. <span data-ttu-id="fcaa9-148">Klicken Sie auf die Schaltfläche **OK** .</span><span class="sxs-lookup"><span data-stu-id="fcaa9-148">Choose the **OK** button.</span></span>

<span data-ttu-id="fcaa9-149">Anschließend wird das neue Menüelement hinzugefügt, und Sie können über das Menü **Extras** auf die Eingabeaufforderung zugreifen.</span><span class="sxs-lookup"><span data-stu-id="fcaa9-149">After that, the new menu item is added and you can access the command prompt from the **Tools** menu.</span></span>

## <a name="see-also"></a><span data-ttu-id="fcaa9-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fcaa9-150">See also</span></span>

 [<span data-ttu-id="fcaa9-151">Extras</span><span class="sxs-lookup"><span data-stu-id="fcaa9-151">Tools</span></span>](../../../docs/framework/tools/index.md)  
 [<span data-ttu-id="fcaa9-152">Verwalten von externen Tools</span><span class="sxs-lookup"><span data-stu-id="fcaa9-152">Managing External Tools</span></span>](/visualstudio/ide/managing-external-tools)  
