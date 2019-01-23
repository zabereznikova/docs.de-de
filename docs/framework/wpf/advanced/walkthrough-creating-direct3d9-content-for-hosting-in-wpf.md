---
title: 'Exemplarische Vorgehensweise: Erstellen von Direct3D9-Inhalten zum Hosten in WPF'
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- WPF [WPF], creating Direct3D9 content
- Direct3D9 [WPF interoperability], creating Direct3D9 content
ms.assetid: 286e98bc-1eaa-4b5e-923d-3490a9cca5fc
ms.openlocfilehash: 8e598b557381bf82b42ea87e2f020ebba4450929
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54520294"
---
# <a name="walkthrough-creating-direct3d9-content-for-hosting-in-wpf"></a><span data-ttu-id="5fa0b-102">Exemplarische Vorgehensweise: Erstellen von Direct3D9-Inhalten zum Hosten in WPF</span><span class="sxs-lookup"><span data-stu-id="5fa0b-102">Walkthrough: Creating Direct3D9 Content for Hosting in WPF</span></span>
<span data-ttu-id="5fa0b-103">Diese exemplarische Vorgehensweise veranschaulicht die Erstellung von Direct3D9-Inhalt, der für das Hosten in einer Windows Presentation Foundation (WPF)-Anwendung geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="5fa0b-103">This walkthrough shows how to create Direct3D9 content that is suitable for hosting in a Windows Presentation Foundation (WPF) application.</span></span> <span data-ttu-id="5fa0b-104">Weitere Informationen zum Hosten von Direct3D9-Inhalt in WPF-Anwendungen, finden Sie unter [zwischen WPF und Direct3D9](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="5fa0b-104">For more information on hosting Direct3D9 content in WPF applications, see [WPF and Direct3D9 Interoperation](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md).</span></span>

 <span data-ttu-id="5fa0b-105">Im Verlauf dieser exemplarischen Vorgehensweise führen Sie die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="5fa0b-105">In this walkthrough, you perform the following tasks:</span></span>

-   <span data-ttu-id="5fa0b-106">Erstellen Sie ein Direct3D9-Projekt.</span><span class="sxs-lookup"><span data-stu-id="5fa0b-106">Create a Direct3D9 project.</span></span>

-   <span data-ttu-id="5fa0b-107">Konfigurieren des Direct3D9-Projekts für das Hosten in einer WPF-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="5fa0b-107">Configure the Direct3D9 project for hosting in a WPF application.</span></span>

 <span data-ttu-id="5fa0b-108">Wenn Sie fertig sind, müssen Sie eine DLL, die Direct3D9-Inhalt für die Verwendung in einer WPF-Anwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="5fa0b-108">When you are finished, you will have a DLL that contains Direct3D9 content for use in a WPF application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5fa0b-109">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="5fa0b-109">Prerequisites</span></span>
 <span data-ttu-id="5fa0b-110">Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="5fa0b-110">You need the following components to complete this walkthrough:</span></span>

-   <span data-ttu-id="5fa0b-111">Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="5fa0b-111">Visual Studio 2010.</span></span>

-   <span data-ttu-id="5fa0b-112">DirectX SDK 9 oder höher.</span><span class="sxs-lookup"><span data-stu-id="5fa0b-112">DirectX SDK 9 or later.</span></span>

## <a name="creating-the-direct3d9-project"></a><span data-ttu-id="5fa0b-113">Erstellen des Projekts Direct3D9</span><span class="sxs-lookup"><span data-stu-id="5fa0b-113">Creating the Direct3D9 Project</span></span>
 <span data-ttu-id="5fa0b-114">Der erste Schritt ist zum Erstellen und konfigurieren Sie das Direct3D9-Projekt.</span><span class="sxs-lookup"><span data-stu-id="5fa0b-114">The first step is to create and configure the Direct3D9 project.</span></span>

#### <a name="to-create-the-direct3d9-project"></a><span data-ttu-id="5fa0b-115">Zum Erstellen des Projekts Direct3D9</span><span class="sxs-lookup"><span data-stu-id="5fa0b-115">To create the Direct3D9 project</span></span>

1.  <span data-ttu-id="5fa0b-116">Erstellen Sie ein neues Win32-Projekt in C++, die mit dem Namen `D3DContent`.</span><span class="sxs-lookup"><span data-stu-id="5fa0b-116">Create a new Win32 Project in C++ named `D3DContent`.</span></span>

     <span data-ttu-id="5fa0b-117">Die Win32-Anwendungsassistenten wird geöffnet und zeigt die Willkommensseite.</span><span class="sxs-lookup"><span data-stu-id="5fa0b-117">The Win32 Application Wizard opens and displays the Welcome screen.</span></span>

2.  <span data-ttu-id="5fa0b-118">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="5fa0b-118">Click **Next**.</span></span>

     <span data-ttu-id="5fa0b-119">Der Application Settings-Bildschirm angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="5fa0b-119">The Application Settings screen appears.</span></span>

3.  <span data-ttu-id="5fa0b-120">In der **Anwendungstyp:** wählen Sie im Abschnitt der **DLL** Option.</span><span class="sxs-lookup"><span data-stu-id="5fa0b-120">In the **Application type:** section, select the **DLL** option.</span></span>

4.  <span data-ttu-id="5fa0b-121">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="5fa0b-121">Click **Finish**.</span></span>

     <span data-ttu-id="5fa0b-122">Das Projekt D3DContent wird generiert.</span><span class="sxs-lookup"><span data-stu-id="5fa0b-122">The D3DContent project is generated.</span></span>

5.  <span data-ttu-id="5fa0b-123">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste in des D3DContent-Projekts, und wählen **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="5fa0b-123">In Solution Explorer, right-click the D3DContent project and select **Properties**.</span></span>

     <span data-ttu-id="5fa0b-124">Die **D3DContent Eigenschaftenseiten** Dialogfeld wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="5fa0b-124">The **D3DContent Property Pages** dialog box opens.</span></span>

6.  <span data-ttu-id="5fa0b-125">Wählen Sie die **C/C++-** Knoten.</span><span class="sxs-lookup"><span data-stu-id="5fa0b-125">Select the **C/C++** node.</span></span>

7.  <span data-ttu-id="5fa0b-126">In der **Additional Include Directories** geben der Speicherort des DirectX Ordner einschließen.</span><span class="sxs-lookup"><span data-stu-id="5fa0b-126">In the **Additional Include Directories** field, specify the location of the DirectX include folder.</span></span> <span data-ttu-id="5fa0b-127">Der Standardspeicherort für diesen Ordner ist: %ProgramFiles%\Microsoft DirectX SDK (*Version*) \include"-Unterverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="5fa0b-127">The default location for this folder is %ProgramFiles%\Microsoft DirectX SDK (*version*)\Include.</span></span>

8.  <span data-ttu-id="5fa0b-128">Doppelklicken Sie auf die **Linker** Knoten aus, um ihn zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="5fa0b-128">Double-click the **Linker** node to expand it.</span></span>

9. <span data-ttu-id="5fa0b-129">In der **Zusätzliche Bibliotheksverzeichnisse** geben den Speicherort des Ordners der DirectX-Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="5fa0b-129">In the **Additional Library Directories** field, specify the location of the DirectX libraries folder.</span></span> <span data-ttu-id="5fa0b-130">Der Standardspeicherort für diesen Ordner ist: %ProgramFiles%\Microsoft DirectX SDK (*Version*) \Lib\x86.</span><span class="sxs-lookup"><span data-stu-id="5fa0b-130">The default location for this folder is %ProgramFiles%\Microsoft DirectX SDK (*version*)\Lib\x86.</span></span>

10. <span data-ttu-id="5fa0b-131">Wählen Sie die **Eingabe** Knoten.</span><span class="sxs-lookup"><span data-stu-id="5fa0b-131">Select the **Input** node.</span></span>

11. <span data-ttu-id="5fa0b-132">In der **zusätzliche Abhängigkeiten** fügen die `d3d9.lib` und `d3dx9.lib` Dateien.</span><span class="sxs-lookup"><span data-stu-id="5fa0b-132">In the **Additional Dependencies** field, add the `d3d9.lib` and `d3dx9.lib` files.</span></span>

12. <span data-ttu-id="5fa0b-133">Fügen Sie im Projektmappen-Explorer eine neue Moduldefinitionsdatei (.def) mit dem Namen `D3DContent.def` zum Projekt.</span><span class="sxs-lookup"><span data-stu-id="5fa0b-133">In Solution Explorer, add a new module definition file (.def) named `D3DContent.def` to the project.</span></span>

## <a name="creating-the-direct3d9-content"></a><span data-ttu-id="5fa0b-134">Erstellen von Direct3D9-Inhalt</span><span class="sxs-lookup"><span data-stu-id="5fa0b-134">Creating the Direct3D9 Content</span></span>
 <span data-ttu-id="5fa0b-135">Um die bestmögliche Leistung zu erhalten, muss Ihre Direct3D9-Inhalt bestimmte Einstellungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="5fa0b-135">To get the best performance, your Direct3D9 content must use particular settings.</span></span> <span data-ttu-id="5fa0b-136">Der folgende Code zeigt, wie Sie eine Direct3D9-Oberfläche zu erstellen, die beste Leistungsmerkmale aufweist.</span><span class="sxs-lookup"><span data-stu-id="5fa0b-136">The following code shows how to create a Direct3D9 surface that has the best performance characteristics.</span></span> <span data-ttu-id="5fa0b-137">Weitere Informationen finden Sie unter [Leistungsüberlegungen hinsichtlich Direct3D9 und WPF-Interoperabilität](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="5fa0b-137">For more information, see [Performance Considerations for Direct3D9 and WPF Interoperability](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md).</span></span>

#### <a name="to-create-the-direct3d9-content"></a><span data-ttu-id="5fa0b-138">Die Direct3D9 Inhalte erstellen</span><span class="sxs-lookup"><span data-stu-id="5fa0b-138">To create the Direct3D9 content</span></span>

1.  <span data-ttu-id="5fa0b-139">Projektmappen-Explorer das Projekt mit dem Namen im folgenden drei C++-Klassen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5fa0b-139">Using Solution Explorer, add three C++ classes to the project named the following.</span></span>

     <span data-ttu-id="5fa0b-140">`CRenderer` (mit virtuellen Destruktor)</span><span class="sxs-lookup"><span data-stu-id="5fa0b-140">`CRenderer` (with virtual destructor)</span></span>

     `CRendererManager`

     `CTriangleRenderer`

2.  <span data-ttu-id="5fa0b-141">Öffnen Sie Renderer.h im Code-Editor, und Ersetzen Sie den automatisch generierten Code durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="5fa0b-141">Open Renderer.h in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#RendererH](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.h#rendererh)]

3.  <span data-ttu-id="5fa0b-142">Öffnen Sie Renderer.cpp im Code-Editor, und Ersetzen Sie den automatisch generierten Code durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="5fa0b-142">Open Renderer.cpp in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#RendererCPP](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderercpp)]

4.  <span data-ttu-id="5fa0b-143">Öffnen Sie RendererManager.h im Code-Editor, und Ersetzen Sie den automatisch generierten Code durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="5fa0b-143">Open RendererManager.h in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#RendererManagerH](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.h#renderermanagerh)]

5.  <span data-ttu-id="5fa0b-144">Öffnen Sie RendererManager.cpp im Code-Editor, und Ersetzen Sie den automatisch generierten Code durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="5fa0b-144">Open RendererManager.cpp in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#RendererManagerCPP](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanagercpp)]

6.  <span data-ttu-id="5fa0b-145">Öffnen Sie TriangleRenderer.h im Code-Editor, und Ersetzen Sie den automatisch generierten Code durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="5fa0b-145">Open TriangleRenderer.h in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#TriangleRendererH](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/trianglerenderer.h#trianglerendererh)]

7.  <span data-ttu-id="5fa0b-146">Öffnen Sie TriangleRenderer.cpp im Code-Editor, und Ersetzen Sie den automatisch generierten Code durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="5fa0b-146">Open TriangleRenderer.cpp in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#TriangleRendererCPP](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/trianglerenderer.cpp#trianglerenderercpp)]

8.  <span data-ttu-id="5fa0b-147">Öffnen Sie "stdafx.h" im Code-Editor, und Ersetzen Sie den automatisch generierten Code durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="5fa0b-147">Open stdafx.h in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#StdafxH](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/stdafx.h#stdafxh)]

9. <span data-ttu-id="5fa0b-148">Öffnen Sie dllmain.cpp im Code-Editor zu, und Ersetzen Sie den automatisch generierten Code durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="5fa0b-148">Open dllmain.cpp in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#DllMain](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/dllmain.cpp#dllmain)]

10. <span data-ttu-id="5fa0b-149">D3DContent.def im Code-Editor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="5fa0b-149">Open D3DContent.def in the code editor.</span></span>

11. <span data-ttu-id="5fa0b-150">Ersetzen Sie den automatisch generierten Code durch den folgenden Code ein.</span><span class="sxs-lookup"><span data-stu-id="5fa0b-150">Replace the automatically generated code with the following code.</span></span>

    ```
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

12. <span data-ttu-id="5fa0b-151">Erstellen Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="5fa0b-151">Build the project.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5fa0b-152">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="5fa0b-152">Next Steps</span></span>

-   <span data-ttu-id="5fa0b-153">Hosten Sie den Direct3D9-Inhalt in einer WPF-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="5fa0b-153">Host the Direct3D9 content in a WPF application.</span></span> <span data-ttu-id="5fa0b-154">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Hosten von Direct3D9-Inhalt in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-direct3d9-content-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="5fa0b-154">For more information, see [Walkthrough: Hosting Direct3D9 Content in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-direct3d9-content-in-wpf.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5fa0b-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5fa0b-155">See also</span></span>

- <xref:System.Windows.Interop.D3DImage>
- [<span data-ttu-id="5fa0b-156">Überlegungen zur Leistung für die Interoperabilität zwischen Direct3D9 und WPF</span><span class="sxs-lookup"><span data-stu-id="5fa0b-156">Performance Considerations for Direct3D9 and WPF Interoperability</span></span>](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md)
- [<span data-ttu-id="5fa0b-157">Exemplarische Vorgehensweise: Hosten von Direct3D9-Inhalt in WPF</span><span class="sxs-lookup"><span data-stu-id="5fa0b-157">Walkthrough: Hosting Direct3D9 Content in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-direct3d9-content-in-wpf.md)
