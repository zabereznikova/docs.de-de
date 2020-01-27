---
title: Von Direct3D9-Inhalt für Hosting Erstellen
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- WPF [WPF], creating Direct3D9 content
- Direct3D9 [WPF interoperability], creating Direct3D9 content
ms.assetid: 286e98bc-1eaa-4b5e-923d-3490a9cca5fc
ms.openlocfilehash: 847ee74da5b295c2c9d3824b3df74f94bc98a4db
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76727920"
---
# <a name="walkthrough-creating-direct3d9-content-for-hosting-in-wpf"></a><span data-ttu-id="583d8-102">Exemplarische Vorgehensweise: Erstellen von Direct3D9-Inhalten zum Hosten in WPF</span><span class="sxs-lookup"><span data-stu-id="583d8-102">Walkthrough: Creating Direct3D9 Content for Hosting in WPF</span></span>
<span data-ttu-id="583d8-103">In dieser exemplarischen Vorgehensweise wird gezeigt, wie von Direct3D9-Inhalte erstellt werden, die sich für das Hosting in einer Windows Presentation Foundation (WPF)-Anwendung eignen.</span><span class="sxs-lookup"><span data-stu-id="583d8-103">This walkthrough shows how to create Direct3D9 content that is suitable for hosting in a Windows Presentation Foundation (WPF) application.</span></span> <span data-ttu-id="583d8-104">Weitere Informationen zum Hosting von von Direct3D9-Inhalten in WPF-Anwendungen finden Sie unter [WPF und von Direct3D9 Interoperation](wpf-and-direct3d9-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="583d8-104">For more information on hosting Direct3D9 content in WPF applications, see [WPF and Direct3D9 Interoperation](wpf-and-direct3d9-interoperation.md).</span></span>

 <span data-ttu-id="583d8-105">Im Verlauf dieser exemplarischen Vorgehensweise führen Sie die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="583d8-105">In this walkthrough, you perform the following tasks:</span></span>

- <span data-ttu-id="583d8-106">Erstellen Sie ein von Direct3D9-Projekt.</span><span class="sxs-lookup"><span data-stu-id="583d8-106">Create a Direct3D9 project.</span></span>

- <span data-ttu-id="583d8-107">Konfigurieren Sie das von Direct3D9-Projekt für das Hosting in einer WPF-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="583d8-107">Configure the Direct3D9 project for hosting in a WPF application.</span></span>

 <span data-ttu-id="583d8-108">Wenn Sie fertig sind, verfügen Sie über eine DLL, die von Direct3D9-Inhalt für die Verwendung in einer WPF-Anwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="583d8-108">When you are finished, you will have a DLL that contains Direct3D9 content for use in a WPF application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="583d8-109">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="583d8-109">Prerequisites</span></span>
 <span data-ttu-id="583d8-110">Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="583d8-110">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="583d8-111">Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="583d8-111">Visual Studio 2010.</span></span>

- <span data-ttu-id="583d8-112">DirectX SDK 9 oder höher.</span><span class="sxs-lookup"><span data-stu-id="583d8-112">DirectX SDK 9 or later.</span></span>

## <a name="creating-the-direct3d9-project"></a><span data-ttu-id="583d8-113">Erstellen des von Direct3D9-Projekts</span><span class="sxs-lookup"><span data-stu-id="583d8-113">Creating the Direct3D9 Project</span></span>
 <span data-ttu-id="583d8-114">Der erste Schritt besteht darin, das von Direct3D9-Projekt zu erstellen und zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="583d8-114">The first step is to create and configure the Direct3D9 project.</span></span>

#### <a name="to-create-the-direct3d9-project"></a><span data-ttu-id="583d8-115">So erstellen Sie das von Direct3D9-Projekt</span><span class="sxs-lookup"><span data-stu-id="583d8-115">To create the Direct3D9 project</span></span>

1. <span data-ttu-id="583d8-116">Erstellen Sie ein neues Win32- C++ Projekt in mit dem Namen `D3DContent`.</span><span class="sxs-lookup"><span data-stu-id="583d8-116">Create a new Win32 Project in C++ named `D3DContent`.</span></span>

     <span data-ttu-id="583d8-117">Der Win32-Anwendungs-Assistent wird geöffnet und zeigt den Willkommensbildschirm an.</span><span class="sxs-lookup"><span data-stu-id="583d8-117">The Win32 Application Wizard opens and displays the Welcome screen.</span></span>

2. <span data-ttu-id="583d8-118">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="583d8-118">Click **Next**.</span></span>

     <span data-ttu-id="583d8-119">Der Bildschirm "Anwendungseinstellungen" wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="583d8-119">The Application Settings screen appears.</span></span>

3. <span data-ttu-id="583d8-120">Wählen Sie im Abschnitt **Anwendungstyp:** die **dll** -Option aus.</span><span class="sxs-lookup"><span data-stu-id="583d8-120">In the **Application type:** section, select the **DLL** option.</span></span>

4. <span data-ttu-id="583d8-121">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="583d8-121">Click **Finish**.</span></span>

     <span data-ttu-id="583d8-122">Das D3DContent-Projekt wird generiert.</span><span class="sxs-lookup"><span data-stu-id="583d8-122">The D3DContent project is generated.</span></span>

5. <span data-ttu-id="583d8-123">Klicken Sie in Projektmappen-Explorer mit der rechten Maustaste auf das Projekt D3DContent, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="583d8-123">In Solution Explorer, right-click the D3DContent project and select **Properties**.</span></span>

     <span data-ttu-id="583d8-124">Das Dialogfeld **D3DContent-Eigenschaften Seiten** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="583d8-124">The **D3DContent Property Pages** dialog box opens.</span></span>

6. <span data-ttu-id="583d8-125">Wählen Sie den Knoten **C/C++**  aus.</span><span class="sxs-lookup"><span data-stu-id="583d8-125">Select the **C/C++** node.</span></span>

7. <span data-ttu-id="583d8-126">Geben Sie im Feld **weitere Includeverzeichnisse** den Speicherort des DirectX Include-Ordners an.</span><span class="sxs-lookup"><span data-stu-id="583d8-126">In the **Additional Include Directories** field, specify the location of the DirectX include folder.</span></span> <span data-ttu-id="583d8-127">Der Standard Speicherort für diesen Ordner ist%ProgramFiles%\Microsoft DirectX SDK (*Version*) \Include.</span><span class="sxs-lookup"><span data-stu-id="583d8-127">The default location for this folder is %ProgramFiles%\Microsoft DirectX SDK (*version*)\Include.</span></span>

8. <span data-ttu-id="583d8-128">Doppelklicken Sie auf den **Linker** -Knoten, um ihn zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="583d8-128">Double-click the **Linker** node to expand it.</span></span>

9. <span data-ttu-id="583d8-129">Geben Sie im Feld " **zusätzliche Bibliotheks Verzeichnisse** " den Speicherort des Ordners "DirectX-Bibliotheken" an.</span><span class="sxs-lookup"><span data-stu-id="583d8-129">In the **Additional Library Directories** field, specify the location of the DirectX libraries folder.</span></span> <span data-ttu-id="583d8-130">Der Standard Speicherort für diesen Ordner ist%ProgramFiles%\Microsoft DirectX SDK (*Version*) \Lib\x86.</span><span class="sxs-lookup"><span data-stu-id="583d8-130">The default location for this folder is %ProgramFiles%\Microsoft DirectX SDK (*version*)\Lib\x86.</span></span>

10. <span data-ttu-id="583d8-131">Wählen Sie den **Eingabe** Knoten aus.</span><span class="sxs-lookup"><span data-stu-id="583d8-131">Select the **Input** node.</span></span>

11. <span data-ttu-id="583d8-132">Fügen Sie im Feld **Zusätzliche Abhängigkeiten** die Dateien `d3d9.lib` und `d3dx9.lib` hinzu.</span><span class="sxs-lookup"><span data-stu-id="583d8-132">In the **Additional Dependencies** field, add the `d3d9.lib` and `d3dx9.lib` files.</span></span>

12. <span data-ttu-id="583d8-133">Fügen Sie in Projektmappen-Explorer dem Projekt eine neue Modul Definitionsdatei (. def) mit dem Namen `D3DContent.def` hinzu.</span><span class="sxs-lookup"><span data-stu-id="583d8-133">In Solution Explorer, add a new module definition file (.def) named `D3DContent.def` to the project.</span></span>

## <a name="creating-the-direct3d9-content"></a><span data-ttu-id="583d8-134">Erstellen des von Direct3D9-Inhalts</span><span class="sxs-lookup"><span data-stu-id="583d8-134">Creating the Direct3D9 Content</span></span>
 <span data-ttu-id="583d8-135">Um die bestmögliche Leistung zu erzielen, müssen ihre von Direct3D9-Inhalte bestimmte Einstellungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="583d8-135">To get the best performance, your Direct3D9 content must use particular settings.</span></span> <span data-ttu-id="583d8-136">Der folgende Code zeigt, wie eine von Direct3D9-Oberfläche erstellt wird, die die besten Leistungsmerkmale aufweist.</span><span class="sxs-lookup"><span data-stu-id="583d8-136">The following code shows how to create a Direct3D9 surface that has the best performance characteristics.</span></span> <span data-ttu-id="583d8-137">Weitere Informationen finden Sie unter [Überlegungen zur Leistung bei der von Direct3D9-und WPF-Interoperabilität](performance-considerations-for-direct3d9-and-wpf-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="583d8-137">For more information, see [Performance Considerations for Direct3D9 and WPF Interoperability](performance-considerations-for-direct3d9-and-wpf-interoperability.md).</span></span>

#### <a name="to-create-the-direct3d9-content"></a><span data-ttu-id="583d8-138">So erstellen Sie den von Direct3D9-Inhalt</span><span class="sxs-lookup"><span data-stu-id="583d8-138">To create the Direct3D9 content</span></span>

1. <span data-ttu-id="583d8-139">Fügen Sie mit Projektmappen-Explorer dem C++ Projekt drei Klassen mit dem Namen hinzu.</span><span class="sxs-lookup"><span data-stu-id="583d8-139">Using Solution Explorer, add three C++ classes to the project named the following.</span></span>

     <span data-ttu-id="583d8-140">`CRenderer` (mit virtuellem Dekonstruktor)</span><span class="sxs-lookup"><span data-stu-id="583d8-140">`CRenderer` (with virtual destructor)</span></span>

     `CRendererManager`

     `CTriangleRenderer`

2. <span data-ttu-id="583d8-141">Öffnen Sie Renderer. h im Code-Editor, und ersetzen Sie den automatisch generierten Code durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="583d8-141">Open Renderer.h in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#RendererH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.h#rendererh)]

3. <span data-ttu-id="583d8-142">Öffnen Sie "Renderer. cpp" im Code-Editor, und ersetzen Sie den automatisch generierten Code durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="583d8-142">Open Renderer.cpp in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#RendererCPP](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderercpp)]

4. <span data-ttu-id="583d8-143">Öffnen Sie RendererManager. h im Code-Editor, und ersetzen Sie den automatisch generierten Code durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="583d8-143">Open RendererManager.h in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#RendererManagerH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.h#renderermanagerh)]

5. <span data-ttu-id="583d8-144">Öffnen Sie "RendererManager. cpp" im Code-Editor, und ersetzen Sie den automatisch generierten Code durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="583d8-144">Open RendererManager.cpp in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#RendererManagerCPP](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanagercpp)]

6. <span data-ttu-id="583d8-145">Öffnen Sie im Code-Editor die Datei "" im Code-Editor, und ersetzen Sie den automatisch generierten Code durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="583d8-145">Open TriangleRenderer.h in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#TriangleRendererH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/trianglerenderer.h#trianglerendererh)]

7. <span data-ttu-id="583d8-146">Öffnen Sie im Code-Editor die Datei "" im Code-Editor, und ersetzen Sie den automatisch generierten Code durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="583d8-146">Open TriangleRenderer.cpp in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#TriangleRendererCPP](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/trianglerenderer.cpp#trianglerenderercpp)]

8. <span data-ttu-id="583d8-147">Öffnen Sie "stdafx. h" im Code-Editor, und ersetzen Sie den automatisch generierten Code durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="583d8-147">Open stdafx.h in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#StdafxH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/stdafx.h#stdafxh)]

9. <span data-ttu-id="583d8-148">Öffnen Sie im Code-Editor die Datei "DllMain. cpp", und ersetzen Sie den automatisch generierten Code durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="583d8-148">Open dllmain.cpp in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#DllMain](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/dllmain.cpp#dllmain)]

10. <span data-ttu-id="583d8-149">Öffnen Sie D3DContent. def im Code-Editor.</span><span class="sxs-lookup"><span data-stu-id="583d8-149">Open D3DContent.def in the code editor.</span></span>

11. <span data-ttu-id="583d8-150">Ersetzen Sie den automatisch generierten Code durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="583d8-150">Replace the automatically generated code with the following code.</span></span>

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

12. <span data-ttu-id="583d8-151">Erstellen Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="583d8-151">Build the project.</span></span>

## <a name="next-steps"></a><span data-ttu-id="583d8-152">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="583d8-152">Next Steps</span></span>

- <span data-ttu-id="583d8-153">Hosten Sie den von Direct3D9-Inhalt in einer WPF-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="583d8-153">Host the Direct3D9 content in a WPF application.</span></span> <span data-ttu-id="583d8-154">Weitere Informationen finden Sie unter Exemplarische Vorgehensweise [: Hosting von Direct3D9 Content in WPF](walkthrough-hosting-direct3d9-content-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="583d8-154">For more information, see [Walkthrough: Hosting Direct3D9 Content in WPF](walkthrough-hosting-direct3d9-content-in-wpf.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="583d8-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="583d8-155">See also</span></span>

- <xref:System.Windows.Interop.D3DImage>
- [<span data-ttu-id="583d8-156">Überlegungen zur Leistung für die Interoperabilität zwischen Direct3D9 und WPF</span><span class="sxs-lookup"><span data-stu-id="583d8-156">Performance Considerations for Direct3D9 and WPF Interoperability</span></span>](performance-considerations-for-direct3d9-and-wpf-interoperability.md)
- [<span data-ttu-id="583d8-157">Exemplarische Vorgehensweise: Hosten von Direct3D9-Inhalt in WPF</span><span class="sxs-lookup"><span data-stu-id="583d8-157">Walkthrough: Hosting Direct3D9 Content in WPF</span></span>](walkthrough-hosting-direct3d9-content-in-wpf.md)
