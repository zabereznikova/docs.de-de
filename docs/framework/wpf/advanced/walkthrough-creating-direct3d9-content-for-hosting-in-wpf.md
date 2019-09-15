---
title: 'Exemplarische Vorgehensweise: Erstellen von Direct3D9-Inhalten zum Hosten in WPF'
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- WPF [WPF], creating Direct3D9 content
- Direct3D9 [WPF interoperability], creating Direct3D9 content
ms.assetid: 286e98bc-1eaa-4b5e-923d-3490a9cca5fc
ms.openlocfilehash: 462220b526db90d3acfa90a28f9bfd56dbe813e2
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991399"
---
# <a name="walkthrough-creating-direct3d9-content-for-hosting-in-wpf"></a><span data-ttu-id="372a0-102">Exemplarische Vorgehensweise: Erstellen von Direct3D9-Inhalten zum Hosten in WPF</span><span class="sxs-lookup"><span data-stu-id="372a0-102">Walkthrough: Creating Direct3D9 Content for Hosting in WPF</span></span>
<span data-ttu-id="372a0-103">In dieser exemplarischen Vorgehensweise wird gezeigt, wie von Direct3D9-Inhalte erstellt werden, die sich für das Hosting in einer Windows Presentation Foundation (WPF)-Anwendung eignen.</span><span class="sxs-lookup"><span data-stu-id="372a0-103">This walkthrough shows how to create Direct3D9 content that is suitable for hosting in a Windows Presentation Foundation (WPF) application.</span></span> <span data-ttu-id="372a0-104">Weitere Informationen zum Hosting von von Direct3D9-Inhalten in WPF-Anwendungen finden Sie unter [WPF und von Direct3D9 Interoperation](wpf-and-direct3d9-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="372a0-104">For more information on hosting Direct3D9 content in WPF applications, see [WPF and Direct3D9 Interoperation](wpf-and-direct3d9-interoperation.md).</span></span>

 <span data-ttu-id="372a0-105">Im Verlauf dieser exemplarischen Vorgehensweise führen Sie folgende Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="372a0-105">In this walkthrough, you perform the following tasks:</span></span>

- <span data-ttu-id="372a0-106">Erstellen Sie ein von Direct3D9-Projekt.</span><span class="sxs-lookup"><span data-stu-id="372a0-106">Create a Direct3D9 project.</span></span>

- <span data-ttu-id="372a0-107">Konfigurieren Sie das von Direct3D9-Projekt für das Hosting in einer WPF-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="372a0-107">Configure the Direct3D9 project for hosting in a WPF application.</span></span>

 <span data-ttu-id="372a0-108">Wenn Sie fertig sind, verfügen Sie über eine DLL, die von Direct3D9-Inhalt für die Verwendung in einer WPF-Anwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="372a0-108">When you are finished, you will have a DLL that contains Direct3D9 content for use in a WPF application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="372a0-109">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="372a0-109">Prerequisites</span></span>
 <span data-ttu-id="372a0-110">Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="372a0-110">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="372a0-111">Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="372a0-111">Visual Studio 2010.</span></span>

- <span data-ttu-id="372a0-112">DirectX SDK 9 oder höher.</span><span class="sxs-lookup"><span data-stu-id="372a0-112">DirectX SDK 9 or later.</span></span>

## <a name="creating-the-direct3d9-project"></a><span data-ttu-id="372a0-113">Erstellen des von Direct3D9-Projekts</span><span class="sxs-lookup"><span data-stu-id="372a0-113">Creating the Direct3D9 Project</span></span>
 <span data-ttu-id="372a0-114">Der erste Schritt besteht darin, das von Direct3D9-Projekt zu erstellen und zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="372a0-114">The first step is to create and configure the Direct3D9 project.</span></span>

#### <a name="to-create-the-direct3d9-project"></a><span data-ttu-id="372a0-115">So erstellen Sie das von Direct3D9-Projekt</span><span class="sxs-lookup"><span data-stu-id="372a0-115">To create the Direct3D9 project</span></span>

1. <span data-ttu-id="372a0-116">Erstellen Sie ein neues Win32- C++ Projekt `D3DContent`in mit dem Namen.</span><span class="sxs-lookup"><span data-stu-id="372a0-116">Create a new Win32 Project in C++ named `D3DContent`.</span></span>

     <span data-ttu-id="372a0-117">Der Win32-Anwendungs-Assistent wird geöffnet und zeigt den Willkommensbildschirm an.</span><span class="sxs-lookup"><span data-stu-id="372a0-117">The Win32 Application Wizard opens and displays the Welcome screen.</span></span>

2. <span data-ttu-id="372a0-118">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="372a0-118">Click **Next**.</span></span>

     <span data-ttu-id="372a0-119">Der Bildschirm "Anwendungseinstellungen" wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="372a0-119">The Application Settings screen appears.</span></span>

3. <span data-ttu-id="372a0-120">Wählen Sie im Abschnitt **Anwendungstyp:** die **dll** -Option aus.</span><span class="sxs-lookup"><span data-stu-id="372a0-120">In the **Application type:** section, select the **DLL** option.</span></span>

4. <span data-ttu-id="372a0-121">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="372a0-121">Click **Finish**.</span></span>

     <span data-ttu-id="372a0-122">Das D3DContent-Projekt wird generiert.</span><span class="sxs-lookup"><span data-stu-id="372a0-122">The D3DContent project is generated.</span></span>

5. <span data-ttu-id="372a0-123">Klicken Sie in Projektmappen-Explorer mit der rechten Maustaste auf das Projekt D3DContent, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="372a0-123">In Solution Explorer, right-click the D3DContent project and select **Properties**.</span></span>

     <span data-ttu-id="372a0-124">Das Dialogfeld **D3DContent-Eigenschaften Seiten** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="372a0-124">The **D3DContent Property Pages** dialog box opens.</span></span>

6. <span data-ttu-id="372a0-125">Wählen Sie den Knoten **C/C++**  aus.</span><span class="sxs-lookup"><span data-stu-id="372a0-125">Select the **C/C++** node.</span></span>

7. <span data-ttu-id="372a0-126">Geben Sie im Feld **weitere Includeverzeichnisse** den Speicherort des DirectX Include-Ordners an.</span><span class="sxs-lookup"><span data-stu-id="372a0-126">In the **Additional Include Directories** field, specify the location of the DirectX include folder.</span></span> <span data-ttu-id="372a0-127">Der Standard Speicherort für diesen Ordner ist%ProgramFiles%\Microsoft DirectX SDK (*Version*) \Include.</span><span class="sxs-lookup"><span data-stu-id="372a0-127">The default location for this folder is %ProgramFiles%\Microsoft DirectX SDK (*version*)\Include.</span></span>

8. <span data-ttu-id="372a0-128">Doppelklicken Sie auf den **Linker** -Knoten, um ihn zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="372a0-128">Double-click the **Linker** node to expand it.</span></span>

9. <span data-ttu-id="372a0-129">Geben Sie im Feld " **zusätzliche Bibliotheks Verzeichnisse** " den Speicherort des Ordners "DirectX-Bibliotheken" an.</span><span class="sxs-lookup"><span data-stu-id="372a0-129">In the **Additional Library Directories** field, specify the location of the DirectX libraries folder.</span></span> <span data-ttu-id="372a0-130">Der Standard Speicherort für diesen Ordner ist%ProgramFiles%\Microsoft DirectX SDK (*Version*) \Lib\x86.</span><span class="sxs-lookup"><span data-stu-id="372a0-130">The default location for this folder is %ProgramFiles%\Microsoft DirectX SDK (*version*)\Lib\x86.</span></span>

10. <span data-ttu-id="372a0-131">Wählen Sie den **Eingabe** Knoten aus.</span><span class="sxs-lookup"><span data-stu-id="372a0-131">Select the **Input** node.</span></span>

11. <span data-ttu-id="372a0-132">Fügen Sie im Feld **Zusätzliche Abhängigkeiten** die `d3d9.lib` -und `d3dx9.lib` -Dateien hinzu.</span><span class="sxs-lookup"><span data-stu-id="372a0-132">In the **Additional Dependencies** field, add the `d3d9.lib` and `d3dx9.lib` files.</span></span>

12. <span data-ttu-id="372a0-133">Fügen Sie in Projektmappen-Explorer dem Projekt eine neue Modul Definitionsdatei (. def `D3DContent.def` ) mit dem Namen hinzu.</span><span class="sxs-lookup"><span data-stu-id="372a0-133">In Solution Explorer, add a new module definition file (.def) named `D3DContent.def` to the project.</span></span>

## <a name="creating-the-direct3d9-content"></a><span data-ttu-id="372a0-134">Erstellen des von Direct3D9-Inhalts</span><span class="sxs-lookup"><span data-stu-id="372a0-134">Creating the Direct3D9 Content</span></span>
 <span data-ttu-id="372a0-135">Um die bestmögliche Leistung zu erzielen, müssen ihre von Direct3D9-Inhalte bestimmte Einstellungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="372a0-135">To get the best performance, your Direct3D9 content must use particular settings.</span></span> <span data-ttu-id="372a0-136">Der folgende Code zeigt, wie eine von Direct3D9-Oberfläche erstellt wird, die die besten Leistungsmerkmale aufweist.</span><span class="sxs-lookup"><span data-stu-id="372a0-136">The following code shows how to create a Direct3D9 surface that has the best performance characteristics.</span></span> <span data-ttu-id="372a0-137">Weitere Informationen finden Sie unter [Überlegungen zur Leistung bei der von Direct3D9-und WPF-Interoperabilität](performance-considerations-for-direct3d9-and-wpf-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="372a0-137">For more information, see [Performance Considerations for Direct3D9 and WPF Interoperability](performance-considerations-for-direct3d9-and-wpf-interoperability.md).</span></span>

#### <a name="to-create-the-direct3d9-content"></a><span data-ttu-id="372a0-138">So erstellen Sie den von Direct3D9-Inhalt</span><span class="sxs-lookup"><span data-stu-id="372a0-138">To create the Direct3D9 content</span></span>

1. <span data-ttu-id="372a0-139">Fügen Sie mit Projektmappen-Explorer dem C++ Projekt drei Klassen mit dem Namen hinzu.</span><span class="sxs-lookup"><span data-stu-id="372a0-139">Using Solution Explorer, add three C++ classes to the project named the following.</span></span>

     <span data-ttu-id="372a0-140">`CRenderer`(mit virtuellem Dekonstruktor)</span><span class="sxs-lookup"><span data-stu-id="372a0-140">`CRenderer` (with virtual destructor)</span></span>

     `CRendererManager`

     `CTriangleRenderer`

2. <span data-ttu-id="372a0-141">Öffnen Sie Renderer. h im Code-Editor, und ersetzen Sie den automatisch generierten Code durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="372a0-141">Open Renderer.h in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#RendererH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.h#rendererh)]

3. <span data-ttu-id="372a0-142">Öffnen Sie "Renderer. cpp" im Code-Editor, und ersetzen Sie den automatisch generierten Code durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="372a0-142">Open Renderer.cpp in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#RendererCPP](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderercpp)]

4. <span data-ttu-id="372a0-143">Öffnen Sie RendererManager. h im Code-Editor, und ersetzen Sie den automatisch generierten Code durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="372a0-143">Open RendererManager.h in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#RendererManagerH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.h#renderermanagerh)]

5. <span data-ttu-id="372a0-144">Öffnen Sie "RendererManager. cpp" im Code-Editor, und ersetzen Sie den automatisch generierten Code durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="372a0-144">Open RendererManager.cpp in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#RendererManagerCPP](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanagercpp)]

6. <span data-ttu-id="372a0-145">Öffnen Sie im Code-Editor die Datei "" im Code-Editor, und ersetzen Sie den automatisch generierten Code durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="372a0-145">Open TriangleRenderer.h in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#TriangleRendererH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/trianglerenderer.h#trianglerendererh)]

7. <span data-ttu-id="372a0-146">Öffnen Sie im Code-Editor die Datei "" im Code-Editor, und ersetzen Sie den automatisch generierten Code durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="372a0-146">Open TriangleRenderer.cpp in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#TriangleRendererCPP](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/trianglerenderer.cpp#trianglerenderercpp)]

8. <span data-ttu-id="372a0-147">Öffnen Sie "stdafx. h" im Code-Editor, und ersetzen Sie den automatisch generierten Code durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="372a0-147">Open stdafx.h in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#StdafxH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/stdafx.h#stdafxh)]

9. <span data-ttu-id="372a0-148">Öffnen Sie im Code-Editor die Datei "DllMain. cpp", und ersetzen Sie den automatisch generierten Code durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="372a0-148">Open dllmain.cpp in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#DllMain](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/dllmain.cpp#dllmain)]

10. <span data-ttu-id="372a0-149">Öffnen Sie D3DContent. def im Code-Editor.</span><span class="sxs-lookup"><span data-stu-id="372a0-149">Open D3DContent.def in the code editor.</span></span>

11. <span data-ttu-id="372a0-150">Ersetzen Sie den automatisch generierten Code durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="372a0-150">Replace the automatically generated code with the following code.</span></span>

    ```cpp
    LIBRARY "D3DContent"

    EXPORTS

    SetSize
    SetAlpha
    SetNumDesiredSamples
    SetAdapter

    GetBackBufferNoRef
    Render
    Destroy
    ```

12. <span data-ttu-id="372a0-151">Erstellen Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="372a0-151">Build the project.</span></span>

## <a name="next-steps"></a><span data-ttu-id="372a0-152">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="372a0-152">Next Steps</span></span>

- <span data-ttu-id="372a0-153">Hosten Sie den von Direct3D9-Inhalt in einer WPF-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="372a0-153">Host the Direct3D9 content in a WPF application.</span></span> <span data-ttu-id="372a0-154">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Hosting von von Direct3D9-Inhalten in](walkthrough-hosting-direct3d9-content-in-wpf.md)WPF.</span><span class="sxs-lookup"><span data-stu-id="372a0-154">For more information, see [Walkthrough: Hosting Direct3D9 Content in WPF](walkthrough-hosting-direct3d9-content-in-wpf.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="372a0-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="372a0-155">See also</span></span>

- <xref:System.Windows.Interop.D3DImage>
- [<span data-ttu-id="372a0-156">Überlegungen zur Leistung für die Interoperabilität zwischen Direct3D9 und WPF</span><span class="sxs-lookup"><span data-stu-id="372a0-156">Performance Considerations for Direct3D9 and WPF Interoperability</span></span>](performance-considerations-for-direct3d9-and-wpf-interoperability.md)
- [<span data-ttu-id="372a0-157">Exemplarische Vorgehensweise: Hosting von Direct3D9 Inhalt in WPF</span><span class="sxs-lookup"><span data-stu-id="372a0-157">Walkthrough: Hosting Direct3D9 Content in WPF</span></span>](walkthrough-hosting-direct3d9-content-in-wpf.md)
