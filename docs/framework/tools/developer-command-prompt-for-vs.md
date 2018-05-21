---
title: Developer-Eingabeaufforderung für Visual Studio.
ms.date: 03/30/2017
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
ms.openlocfilehash: d3ff897e37e3fa2f7202a54c05c8093ba05282c5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="developer-command-prompt-for-visual-studio"></a><span data-ttu-id="0af25-102">Developer-Eingabeaufforderung für Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0af25-102">Developer Command Prompt for Visual Studio</span></span>
<span data-ttu-id="0af25-103">Die Developer-Eingabeaufforderung für Visual Studio legt die Umgebungsvariablen, die Ihnen die einfache Nutzung von .NET Framework-Tools ermöglichen, automatisch fest.</span><span class="sxs-lookup"><span data-stu-id="0af25-103">The Developer Command Prompt for Visual Studio automatically sets the environment variables that enable you to easily use .NET Framework tools.</span></span> <span data-ttu-id="0af25-104">Die Developer-Eingabeaufforderung wird mit vollständigen oder Community-Editionen von Visual Studio installiert.</span><span class="sxs-lookup"><span data-stu-id="0af25-104">The Developer Command Prompt is installed with full or community editions of Visual Studio.</span></span> <span data-ttu-id="0af25-105">Sie wird nicht mit den Express-Versionen von Visual Studio installiert.</span><span class="sxs-lookup"><span data-stu-id="0af25-105">It is not installed with the Express versions of Visual Studio.</span></span>  
  
<a name="find"></a>   
## <a name="searching-for-the-command-prompt-on-your-machine"></a><span data-ttu-id="0af25-106">Suchen nach der Eingabeaufforderung auf Ihrem Computer</span><span class="sxs-lookup"><span data-stu-id="0af25-106">Searching for the Command Prompt on your machine</span></span>  
 <span data-ttu-id="0af25-107">Je nach Version von Visual Studio und den installierten zusätzlichen SDKs werden möglicherweise mehrere Eingabeaufforderungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0af25-107">You may see multiple command prompts, depending on the version of Visual Studio and any additional SDKs you've installed.</span></span> <span data-ttu-id="0af25-108">Beispielsweise stellen 64-Bit-Versionen von Visual Studio sowohl 32-Bit- als auch 64-Bit-Eingabeaufforderungen bereit.</span><span class="sxs-lookup"><span data-stu-id="0af25-108">For example, 64-bit versions of Visual Studio provide both 32-bit and 64-bit command prompts.</span></span> <span data-ttu-id="0af25-109">(Die 32-Bit- und 64-Bit-Versionen der meisten Tools sind identisch. Möglicherweise nehmen jedoch einige Tools bestimmte Änderungen an der 32-Bit- bzw. der 64-Bit-Umgebung vor.) Wenn die folgenden Schritte nicht funktionieren, können Sie die Aktion [Manuelles Suchen der Dateien auf Ihrem Computer](#alternative) oder [Ausführen der Eingabeaufforderung innerhalb von Visual Studio](#visualstudio) testweise ausführen.</span><span class="sxs-lookup"><span data-stu-id="0af25-109">(The 32-bit and 64-bit versions of most tools are identical; however, a few tools make changes specific to 32-bit and 64-bit environments.) If the steps below don't work, you can try [Manually locating the files on your machine](#alternative) or [Running command prompt from inside Visual Studio](#visualstudio).</span></span>  
  
 <span data-ttu-id="0af25-110">**Unter Windows 10**</span><span class="sxs-lookup"><span data-stu-id="0af25-110">**In Windows 10**</span></span>  
  
1.  <span data-ttu-id="0af25-111">Öffnen Sie das Menü **Start**, indem Sie beispielsweise die Windows-Logo-Taste ![Windows-Logo](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") auf der Tastatur drücken.</span><span class="sxs-lookup"><span data-stu-id="0af25-111">Open the **Start** menu, by pressing the Windows logo key ![Windows logo](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>  
  
2.  <span data-ttu-id="0af25-112">Geben Sie im Menü**Start** `dev` ein.</span><span class="sxs-lookup"><span data-stu-id="0af25-112">On the **Start** menu, enter `dev`.</span></span> <span data-ttu-id="0af25-113">Dadurch wird eine Liste der installierten Apps angezeigt, die Ihrem Suchmuster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="0af25-113">This will bring a list of installed apps that match your search pattern.</span></span> <span data-ttu-id="0af25-114">Wenn Sie nach einer anderen Eingabeaufforderung suchen, geben Sie einen anderen Suchbegriff als `prompt` ein.</span><span class="sxs-lookup"><span data-stu-id="0af25-114">If you're looking for a different command prompt, try entering a different search term such as `prompt`.</span></span>  
  
3.  <span data-ttu-id="0af25-115">Wählen Sie **Developer-Eingabeaufforderung** (oder die gewünschte Eingabeaufforderung) aus.</span><span class="sxs-lookup"><span data-stu-id="0af25-115">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>  
  
 <span data-ttu-id="0af25-116">**Unter Windows 8.1**</span><span class="sxs-lookup"><span data-stu-id="0af25-116">**In Windows 8.1**</span></span>  
  
1.  <span data-ttu-id="0af25-117">Wechseln Sie zum Bildschirm **Start**, indem Sie beispielsweise die Windows-Logo-Taste ![Windows-Logo](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") auf der Tastatur drücken.</span><span class="sxs-lookup"><span data-stu-id="0af25-117">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>  
  
2.  <span data-ttu-id="0af25-118">Drücken Sie auf dem Bildschirm **Start** `CTRL + TAB`, um die Liste **Apps** zu öffnen, und geben Sie anschließend `V` ein.</span><span class="sxs-lookup"><span data-stu-id="0af25-118">On the **Start** screen, press `CTRL + TAB` to open the **Apps** list and then enter `V`.</span></span> <span data-ttu-id="0af25-119">Dadurch wird eine Liste angezeigt, die alle installierten Visual Studio-Eingabeaufforderungen enthält.</span><span class="sxs-lookup"><span data-stu-id="0af25-119">This will bring a list that includes all installed Visual Studio command prompts.</span></span>  
  
3.  <span data-ttu-id="0af25-120">Wählen Sie **Developer-Eingabeaufforderung** (oder die gewünschte Eingabeaufforderung) aus.</span><span class="sxs-lookup"><span data-stu-id="0af25-120">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>  
  
 <span data-ttu-id="0af25-121">**Unter Windows 8**</span><span class="sxs-lookup"><span data-stu-id="0af25-121">**In Windows 8**</span></span>  
  
1.  <span data-ttu-id="0af25-122">Wechseln Sie zum Bildschirm **Start**, indem Sie beispielsweise die Windows-Logo-Taste ![Windows-Logo](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") auf der Tastatur drücken.</span><span class="sxs-lookup"><span data-stu-id="0af25-122">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>  
  
2.  <span data-ttu-id="0af25-123">Drücken Sie auf dem Bildschirm **Start** die Windows-Logo-Taste ![Windows-Logo](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`.</span><span class="sxs-lookup"><span data-stu-id="0af25-123">On the **Start** screen, press the Windows logo key ![Windows logo](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`.</span></span>  
  
3.  <span data-ttu-id="0af25-124">Wählen Sie im unteren Bereich des Bildschirms das Symbol **Apps-Ansicht** aus, und geben Sie anschließend `V` ein.</span><span class="sxs-lookup"><span data-stu-id="0af25-124">Choose the **Apps view** icon at the bottom of the screen and then enter `V`.</span></span> <span data-ttu-id="0af25-125">Dadurch wird eine Liste angezeigt, die alle installierten Visual Studio-Eingabeaufforderungen enthält.</span><span class="sxs-lookup"><span data-stu-id="0af25-125">This will bring a list that includes all installed Visual Studio command prompts.</span></span>  
  
4.  <span data-ttu-id="0af25-126">Wählen Sie **Developer-Eingabeaufforderung** (oder die gewünschte Eingabeaufforderung) aus.</span><span class="sxs-lookup"><span data-stu-id="0af25-126">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>  
  
 <span data-ttu-id="0af25-127">**Unter Windows 7**</span><span class="sxs-lookup"><span data-stu-id="0af25-127">**In Windows 7**</span></span>  
  
1.  <span data-ttu-id="0af25-128">Wählen Sie **Start** aus, erweitern Sie **Alle Programme**, und erweitern Sie anschließend **Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="0af25-128">Choose **Start**, expand **All Programs**, and then expand **Microsoft Visual Studio**.</span></span>  
  
2.  <span data-ttu-id="0af25-129">Wählen Sie abhängig von der installierten Visual Studio-Version **Visual Studio-Tools**, **Visual Studio-Eingabeaufforderung** oder die gewünschte Eingabeaufforderung aus.</span><span class="sxs-lookup"><span data-stu-id="0af25-129">Depending on the version of Visual Studio you have installed, choose  **Visual Studio Tools**, **Visual Studio Command Prompt**, or the command prompt you want to use.</span></span>  
  
 <span data-ttu-id="0af25-130">Wenn Sie das [Windows SDK](http://msdn.microsoft.com/windows/desktop/aa904949) oder [Windows Phone SDK](https://dev.windowsphone.com/downloadsdk) installiert haben, sehen Sie möglicherweise zusätzliche Eingabeaufforderungen für ARM-, x86- oder x64-Architekturen.</span><span class="sxs-lookup"><span data-stu-id="0af25-130">If you have the [Windows SDK](http://msdn.microsoft.com/windows/desktop/aa904949) or [Windows Phone SDK](https://dev.windowsphone.com/downloadsdk) installed, you may see additional command prompts for ARM, x86, or x64 architectures.</span></span> <span data-ttu-id="0af25-131">Informationen dazu, welche Version der Eingabeaufforderung Sie verwenden sollten, finden Sie in der Dokumentation der einzelnen Tools.</span><span class="sxs-lookup"><span data-stu-id="0af25-131">Check the documentation for the individual tools to determine which version of the command prompt you should use.</span></span>  
  
<a name="alternative"></a>   
## <a name="manually-locating-the-files-on-your-machine"></a><span data-ttu-id="0af25-132">Manuelles Suchen der Dateien auf Ihrem Computer</span><span class="sxs-lookup"><span data-stu-id="0af25-132">Manually locating the files on your machine</span></span>  
  <span data-ttu-id="0af25-133">In der Regel werden die Tastenkombinationen für die installierten Eingabeaufforderungen im Ordner **Start menu** für Visual Studio platziert, beispielsweise in „C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2015\Visual Studio Tools“.</span><span class="sxs-lookup"><span data-stu-id="0af25-133">Usually, the shortcuts for the command prompts you have installed will be placed at the **Start Menu** folder for Visual Studio, such as in C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2015\Visual Studio Tools.</span></span>    <span data-ttu-id="0af25-134">Wenn die Suche nach einer Eingabeaufforderung jedoch nicht die erwarteten Ergebnisse liefert, können Sie versuchen, die Tastenkombination manuell auf Ihrem Computer zu finden, um sie zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="0af25-134">But if for some reason, searching for the command prompt doesn't yield the expected results, you can try to manually locate the shortcut on your machine in order to use it.</span></span>   <span data-ttu-id="0af25-135">Suchen Sie z. B. den Namen der Eingabeaufforderungsdatei (z. B.„VsDevCmd.bat“), oder wechseln Sie zum Ordner „Tools“, z. B. „C:\Program Files (X 86) \Microsoft Visual Studio 14.0\Common7\Tools“ (gemäß der Version und des Installationspfads von Visual Studio kann der Pfad von diesem Beispiel abweichen).</span><span class="sxs-lookup"><span data-stu-id="0af25-135">Try searching for the name of the command prompt file such as VsDevCmd.bat or go to the Tools folder such as C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\Tools (path will change according to your Visual Studio version and installation location).</span></span>  
  
<a name="visualstudio"></a>   
## <a name="running-command-prompt-from-inside-visual-studio"></a><span data-ttu-id="0af25-136">Ausführen der Eingabeaufforderung innerhalb von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0af25-136">Running command prompt from inside Visual Studio</span></span>  
 <span data-ttu-id="0af25-137">Für den einfacheren Zugriff können Sie die Developer-Eingabeaufforderung von Visual Studio oder eine beliebige andere Eingabeaufforderung zum Menü „Extras“ in Visual Studio hinzufügen, indem Sie sie zur Liste der externen Tools hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0af25-137">For easier access, you can add the Visual Studio Developer Command Prompt  or any other command prompt to the Tools menu on Visual Studio, by adding it to the external tools list.</span></span> <span data-ttu-id="0af25-138">Dazu gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="0af25-138">This is how you can accomplish that:</span></span>  
  
1.  <span data-ttu-id="0af25-139">Öffnen Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0af25-139">Open Visual Studio.</span></span>  
  
2.  <span data-ttu-id="0af25-140">Wählen Sie das Menü **Tools** und anschließend **Externe Tools...** aus.</span><span class="sxs-lookup"><span data-stu-id="0af25-140">Select the **Tools** menu and choose **External Tools...**.</span></span>  
  
3.  <span data-ttu-id="0af25-141">Wählen Sie im Dialogfeld **Externe Tools** die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="0af25-141">On the **External Tools** dialog box, choose the **Add** button.</span></span> <span data-ttu-id="0af25-142">Ein neuer Eintrag wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0af25-142">A new entry appears</span></span>  
  
4.  <span data-ttu-id="0af25-143">Geben Sie einen **Titel** für das neue Menüelement ein, z.B. `Command Prompt`.</span><span class="sxs-lookup"><span data-stu-id="0af25-143">Enter a **Title** for your new menu item such as `Command Prompt`.</span></span>  
  
5.  <span data-ttu-id="0af25-144">Geben Sie im Feld **Befehl** die Datei an, die Sie starten möchten, z.B. `%comspec%` oder `C:\Windows\System32\cmd.exe`.</span><span class="sxs-lookup"><span data-stu-id="0af25-144">In the **Command** field, specify the file you want to launch such as `%comspec%` or `C:\Windows\System32\cmd.exe` .</span></span>  
  
6.  <span data-ttu-id="0af25-145">Geben Sie im Feld **Argumente** an, wo Sie die bestimmte Eingabeaufforderung finden, die Sie verwenden möchten, z.B. `/k "C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\Tools\VsDevCmd.bat"` (hierdurch wird die Developer-Eingabeaufforderung mit [!INCLUDE[vs_dev14](../../../includes/vs-dev14-md.md)] installiert).</span><span class="sxs-lookup"><span data-stu-id="0af25-145">In the **Arguments** field, specify where to find the specific command prompt you want to use such as `/k "C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\Tools\VsDevCmd.bat"` (this will launch the Developer Command Prompt installed with [!INCLUDE[vs_dev14](../../../includes/vs-dev14-md.md)]).</span></span> <span data-ttu-id="0af25-146">Dieser Wert muss entsprechend der Visual Studio-Version und des Installationspfads geändert werden.</span><span class="sxs-lookup"><span data-stu-id="0af25-146">This value needs to be changed according to your Visual Studio version and installation location.</span></span>  
  
7.  <span data-ttu-id="0af25-147">Wählen Sie einen Wert für das Feld **Ausgangsverzeichnis** aus, z.B. **Projektverzeichnis**.</span><span class="sxs-lookup"><span data-stu-id="0af25-147">Choose a value for the **Initial directory** field such as **Project Directory** .</span></span>  
  
8.  <span data-ttu-id="0af25-148">Klicken Sie auf die Schaltfläche **OK** .</span><span class="sxs-lookup"><span data-stu-id="0af25-148">Choose the **OK** button.</span></span>  
  
 <span data-ttu-id="0af25-149">Anschließend wird das neue Menüelement hinzugefügt, und Sie können über das Menü **Extras** auf die Eingabeaufforderung zugreifen.</span><span class="sxs-lookup"><span data-stu-id="0af25-149">After that, the new menu item is added and you can access the command prompt from the **Tools** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0af25-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0af25-150">See Also</span></span>  
 [<span data-ttu-id="0af25-151">Extras</span><span class="sxs-lookup"><span data-stu-id="0af25-151">Tools</span></span>](../../../docs/framework/tools/index.md)  
 [<span data-ttu-id="0af25-152">Verwalten von externen Tools</span><span class="sxs-lookup"><span data-stu-id="0af25-152">Managing External Tools</span></span>](/visualstudio/ide/managing-external-tools)
