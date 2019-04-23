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
ms.openlocfilehash: cc88106a54a00b4b12e5043da7961791a98102c0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59344363"
---
# <a name="developer-command-prompt-for-visual-studio"></a><span data-ttu-id="7960b-102">Developer-Eingabeaufforderung für Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7960b-102">Developer Command Prompt for Visual Studio</span></span>

<span data-ttu-id="7960b-103">Mithilfe der Developer-Eingabeaufforderung für Visual Studio können Sie .NET Framework-Tools komfortabler verwenden.</span><span class="sxs-lookup"><span data-stu-id="7960b-103">The Developer Command Prompt for Visual Studio enables you to use .NET Framework tools more easily.</span></span> <span data-ttu-id="7960b-104">Es handelt sich um eine Eingabeaufforderung, die automatisch bestimmte Umgebungsvariablen festlegt.</span><span class="sxs-lookup"><span data-stu-id="7960b-104">It is a command prompt that automatically sets specific environment variables.</span></span>

> [!div class="button"]
> [<span data-ttu-id="7960b-105">Herunterladen von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7960b-105">Download Visual Studio</span></span>](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)

## <a name="search-for-the-command-prompt-on-your-machine"></a><span data-ttu-id="7960b-106">Suchen nach der Eingabeaufforderung auf Ihrem Computer</span><span class="sxs-lookup"><span data-stu-id="7960b-106">Search for the command prompt on your machine</span></span>

<span data-ttu-id="7960b-107">Abhängig von der Version von Visual Studio und jeglichen zusätzlichen installierten SDKs verfügen Sie möglicherweise über mehrere Eingabeaufforderungen.</span><span class="sxs-lookup"><span data-stu-id="7960b-107">You may have multiple command prompts, depending on the version of Visual Studio and any additional SDKs you've installed.</span></span> <span data-ttu-id="7960b-108">Beispielsweise stellen 64-Bit-Versionen von Visual Studio sowohl 32-Bit- als auch 64-Bit-Eingabeaufforderungen bereit.</span><span class="sxs-lookup"><span data-stu-id="7960b-108">For example, 64-bit versions of Visual Studio provide both 32-bit and 64-bit command prompts.</span></span> <span data-ttu-id="7960b-109">(Die 32-Bit- und 64-Bit-Versionen der meisten Tools sind identisch. Möglicherweise nehmen jedoch einige Tools bestimmte Änderungen an der 32-Bit- bzw. der 64-Bit-Umgebung vor.) Wenn die folgenden Schritte nicht funktionieren, können Sie versuchen, [die Dateien manuell auf Ihrem Computer zu finden](#manually-locate-the-files-on-your-machine) oder [die Eingabeaufforderung innerhalb von Visual Studio auszuführen](#run-the-command-prompt-from-inside-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="7960b-109">(The 32-bit and 64-bit versions of most tools are the same; however, a few tools make changes specific to 32-bit and 64-bit environments.) If the following steps don't work, you can try [Manually locate the files on your machine](#manually-locate-the-files-on-your-machine) or [Run the command prompt from inside Visual Studio](#run-the-command-prompt-from-inside-visual-studio).</span></span>

### <a name="in-windows-10"></a><span data-ttu-id="7960b-110">In Windows 10</span><span class="sxs-lookup"><span data-stu-id="7960b-110">In Windows 10</span></span>

1. <span data-ttu-id="7960b-111">Geben Sie den Namen des Tools im Suchfeld auf der Taskleiste ein, z.B. `dev` oder `developer command prompt`.</span><span class="sxs-lookup"><span data-stu-id="7960b-111">In the search box on the taskbar, start typing the name of the tool, such as `dev` or `developer command prompt`.</span></span> <span data-ttu-id="7960b-112">Dadurch wird eine Liste der installierten Apps angezeigt, die Ihrem Suchmuster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="7960b-112">This brings up a list of installed apps that match your search pattern.</span></span> <span data-ttu-id="7960b-113">Wenn Sie nach einer anderen Eingabeaufforderung suchen, geben Sie einen anderen Suchbegriff als `prompt` ein.</span><span class="sxs-lookup"><span data-stu-id="7960b-113">If you're looking for a different command prompt, try entering a different search term such as `prompt`.</span></span>

2. <span data-ttu-id="7960b-114">Wählen Sie die **Developer-Eingabeaufforderung für Visual Studio** (oder die gewünschte Eingabeaufforderung) aus.</span><span class="sxs-lookup"><span data-stu-id="7960b-114">Choose the **Developer Command Prompt for Visual Studio** (or the command prompt you want to use).</span></span>

### <a name="in-windows-81"></a><span data-ttu-id="7960b-115">Unter Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="7960b-115">In Windows 8.1</span></span>

1. <span data-ttu-id="7960b-116">Wechseln Sie zum Bildschirm **Start**, indem Sie beispielsweise die Windows-Logo-Taste ![Windows-Logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") auf der Tastatur drücken.</span><span class="sxs-lookup"><span data-stu-id="7960b-116">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>

2. <span data-ttu-id="7960b-117">Drücken Sie auf dem Bildschirm **Start** die Tastenkombination **STRG**+**TAB**, um die Liste **Apps** zu öffnen, und geben Sie dann `V` ein.</span><span class="sxs-lookup"><span data-stu-id="7960b-117">On the **Start** screen, press **Ctrl**+**Tab** to open the **Apps** list, and then enter `V`.</span></span> <span data-ttu-id="7960b-118">Dadurch wird eine Liste angezeigt, die alle installierten Visual Studio-Eingabeaufforderungen enthält.</span><span class="sxs-lookup"><span data-stu-id="7960b-118">This brings a list that includes all installed Visual Studio command prompts.</span></span>

3. <span data-ttu-id="7960b-119">Wählen Sie **Developer-Eingabeaufforderung** (oder die gewünschte Eingabeaufforderung) aus.</span><span class="sxs-lookup"><span data-stu-id="7960b-119">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>

### <a name="in-windows-8"></a><span data-ttu-id="7960b-120">Unter Windows 8</span><span class="sxs-lookup"><span data-stu-id="7960b-120">In Windows 8</span></span>

1. <span data-ttu-id="7960b-121">Wechseln Sie zum Bildschirm **Start**, indem Sie beispielsweise die Windows-Logo-Taste ![Windows-Logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") auf der Tastatur drücken.</span><span class="sxs-lookup"><span data-stu-id="7960b-121">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>

2. <span data-ttu-id="7960b-122">Drücken Sie auf dem Bildschirm **Start** die Windows-Logo-Taste ![Windows-Logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`.</span><span class="sxs-lookup"><span data-stu-id="7960b-122">On the **Start** screen, press the Windows logo key ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`.</span></span>

3. <span data-ttu-id="7960b-123">Wählen Sie im unteren Bereich des Bildschirms das Symbol **Apps-Ansicht** aus, und geben Sie anschließend `V` ein.</span><span class="sxs-lookup"><span data-stu-id="7960b-123">Choose the **Apps view** icon at the bottom of the screen and then enter `V`.</span></span> <span data-ttu-id="7960b-124">Dadurch wird eine Liste angezeigt, die alle installierten Visual Studio-Eingabeaufforderungen enthält.</span><span class="sxs-lookup"><span data-stu-id="7960b-124">This brings a list that includes all installed Visual Studio command prompts.</span></span>

4. <span data-ttu-id="7960b-125">Wählen Sie **Developer-Eingabeaufforderung** (oder die gewünschte Eingabeaufforderung) aus.</span><span class="sxs-lookup"><span data-stu-id="7960b-125">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>

### <a name="in-windows-7"></a><span data-ttu-id="7960b-126">Unter Windows 7</span><span class="sxs-lookup"><span data-stu-id="7960b-126">In Windows 7</span></span>

1. <span data-ttu-id="7960b-127">Wählen Sie **Start** aus, erweitern Sie **Alle Programme**, und erweitern Sie anschließend **Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="7960b-127">Choose **Start**, expand **All Programs**, and then expand **Microsoft Visual Studio**.</span></span>

2. <span data-ttu-id="7960b-128">Wählen Sie abhängig von der installierten Visual Studio-Version **Visual Studio-Tools**, **Visual Studio-Eingabeaufforderung** oder die gewünschte Eingabeaufforderung aus.</span><span class="sxs-lookup"><span data-stu-id="7960b-128">Depending on the version of Visual Studio you've installed, choose  **Visual Studio Tools**, **Visual Studio Command Prompt**, or the command prompt you want to use.</span></span>

<span data-ttu-id="7960b-129">Wenn Sie andere SDKs installiert haben, z.B. das [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) oder [frühere Versionen](https://developer.microsoft.com/windows/downloads/sdk-archive), werden Ihnen möglicherweise zusätzliche Eingabeaufforderungen für ARM-, x86- oder x64-Architekturen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7960b-129">If you have other SDKs installed, such as the [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) or [previous versions](https://developer.microsoft.com/windows/downloads/sdk-archive), you may see additional command prompts for ARM, x86, or x64 architectures.</span></span> <span data-ttu-id="7960b-130">Informationen dazu, welche Version der Eingabeaufforderung Sie verwenden sollten, finden Sie in der Dokumentation der einzelnen Tools.</span><span class="sxs-lookup"><span data-stu-id="7960b-130">Check the documentation for the individual tools to determine which version of the command prompt you should use.</span></span>

## <a name="manually-locate-the-files-on-your-machine"></a><span data-ttu-id="7960b-131">Manuelles Suchen der Dateien auf Ihrem Computer</span><span class="sxs-lookup"><span data-stu-id="7960b-131">Manually locate the files on your machine</span></span>

<span data-ttu-id="7960b-132">In der Regel werden die Tastenkombinationen für die installierten Eingabeaufforderungen im Ordner **Start Menu** für Visual Studio platziert, beispielsweise in „C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2017\Visual Studio Tools“.</span><span class="sxs-lookup"><span data-stu-id="7960b-132">Usually, the shortcuts for the command prompts you have installed are placed at the **Start Menu** folder for Visual Studio, such as in C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2017\Visual Studio Tools.</span></span> <span data-ttu-id="7960b-133">Wenn die Suche nach der Eingabeaufforderung jedoch nicht die erwarteten Ergebnisse liefert, können Sie versuchen, die Tastenkombination manuell auf Ihrem Computer zu finden.</span><span class="sxs-lookup"><span data-stu-id="7960b-133">But if for some reason, searching for the command prompt doesn't bring the expected results, you can try to manually locate the shortcut on your machine.</span></span> <span data-ttu-id="7960b-134">Suchen Sie z.B. den Namen der Eingabeaufforderungsdatei (z.B. *VsDevCmd.bat*), oder wechseln Sie zum Ordner „Tools“, z.B. unter „ C:\Programme (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools“ (der Pfad kann gemäß der Version, der Edition und des Speicherorts von Visual Studio von diesem Beispiel abweichen).</span><span class="sxs-lookup"><span data-stu-id="7960b-134">Try searching for the name of the command prompt file, such as *VsDevCmd.bat*, or go to the Tools folder such as C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools (path changes according to your Visual Studio version, edition, and installation location).</span></span>

## <a name="run-the-command-prompt-from-inside-visual-studio"></a><span data-ttu-id="7960b-135">Ausführen der Eingabeaufforderung innerhalb von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7960b-135">Run the command prompt from inside Visual Studio</span></span>

<span data-ttu-id="7960b-136">Für den einfacheren Zugriff können Sie die Developer-Eingabeaufforderung von Visual Studio oder eine beliebige andere Eingabeaufforderung zum Menü **Extras** in Visual Studio hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="7960b-136">For easier access, you can add the Visual Studio Developer Command Prompt, or any other command prompt, to the **Tools** menu in Visual Studio.</span></span> <span data-ttu-id="7960b-137">Fügen Sie das Tool der Liste externer Tools hinzu, damit Sie auf dieses zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="7960b-137">To make the tool available, add it to the external tools list.</span></span> <span data-ttu-id="7960b-138">Folgende Schritte müssen ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="7960b-138">Here are the steps:</span></span>

1. <span data-ttu-id="7960b-139">Öffnen Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7960b-139">Open Visual Studio.</span></span>

2. <span data-ttu-id="7960b-140">Klicken Sie auf das Menü **Extras**, und wählen Sie dann **Externe Tools** aus.</span><span class="sxs-lookup"><span data-stu-id="7960b-140">Select the **Tools** menu, and then choose **External Tools**.</span></span>

3. <span data-ttu-id="7960b-141">Wählen Sie im Dialogfeld **Externe Tools** die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="7960b-141">On the **External Tools** dialog box, choose the **Add** button.</span></span> <span data-ttu-id="7960b-142">Ein neuer Eintrag wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7960b-142">A new entry appears.</span></span>

4. <span data-ttu-id="7960b-143">Geben Sie einen **Titel** für das neue Menüelement ein, z.B. `Command Prompt`.</span><span class="sxs-lookup"><span data-stu-id="7960b-143">Enter a **Title** for your new menu item such as `Command Prompt`.</span></span>

5. <span data-ttu-id="7960b-144">Geben Sie im Feld **Befehl** die Datei an, die Sie starten möchten, z.B. `%comspec%` oder `C:\Windows\System32\cmd.exe`.</span><span class="sxs-lookup"><span data-stu-id="7960b-144">In the **Command** field, specify the file you want to launch, such as `%comspec%` or `C:\Windows\System32\cmd.exe`.</span></span>

6. <span data-ttu-id="7960b-145">Geben Sie im Feld **Argumente** an, wo diejenige Eingabeaufforderung, die Sie verwenden möchten, zu finden ist, z.B. `/k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools\VsDevCmd.bat"` (dieser Befehl startet die Developer-Eingabeaufforderung, die mit Visual Studio 2017 Enterprise installiert wurde).</span><span class="sxs-lookup"><span data-stu-id="7960b-145">In the **Arguments** field, specify where to find the specific command prompt you want to use such as `/k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools\VsDevCmd.bat"` (this command launches the Developer Command Prompt that is installed with Visual Studio 2017 Enterprise).</span></span> <span data-ttu-id="7960b-146">Ändern Sie diesen Wert entsprechend der Version, der Edition und dem Installationsspeicherort von Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7960b-146">Change this value according to your Visual Studio version, edition, and installation location.</span></span>

7. <span data-ttu-id="7960b-147">Wählen Sie einen Wert für das Feld **Ausgangsverzeichnis** aus, z.B. **Projektverzeichnis**.</span><span class="sxs-lookup"><span data-stu-id="7960b-147">Choose a value for the **Initial directory** field, such as **Project Directory**.</span></span>

8. <span data-ttu-id="7960b-148">Klicken Sie auf die Schaltfläche **OK** .</span><span class="sxs-lookup"><span data-stu-id="7960b-148">Choose the **OK** button.</span></span>

   <span data-ttu-id="7960b-149">Das neue Menüelement wird hinzugefügt, und Sie können über das Menü **Extras** auf die Eingabeaufforderung zugreifen.</span><span class="sxs-lookup"><span data-stu-id="7960b-149">The new menu item is added, and you can access the command prompt from the **Tools** menu.</span></span>

   ![Menüelement „Eingabeaufforderung“ in Visual Studio](media/command-prompt-vs-menu.png)

## <a name="see-also"></a><span data-ttu-id="7960b-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7960b-151">See also</span></span>

- [<span data-ttu-id="7960b-152">Extras</span><span class="sxs-lookup"><span data-stu-id="7960b-152">Tools</span></span>](../../../docs/framework/tools/index.md)
- [<span data-ttu-id="7960b-153">Verwalten von externen Tools</span><span class="sxs-lookup"><span data-stu-id="7960b-153">Managing External Tools</span></span>](/visualstudio/ide/managing-external-tools)
