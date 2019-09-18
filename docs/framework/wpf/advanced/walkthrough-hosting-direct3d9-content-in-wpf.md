---
title: 'Exemplarische Vorgehensweise: Hosten von Direct3D9-Inhalt in WPF'
ms.date: 03/30/2017
helpviewer_keywords:
- Direct3D9 [WPF interoperability], hosting Direct3D9 content
- WPF [WPF], hosting Direct3D9 content
ms.assetid: 60983736-0ab5-42cc-8b16-e9fbde261a43
ms.openlocfilehash: 2c31c044aa50a74255a61da1675037ab3d09f615
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053453"
---
# <a name="walkthrough-hosting-direct3d9-content-in-wpf"></a><span data-ttu-id="2d71d-102">Exemplarische Vorgehensweise: Hosten von Direct3D9-Inhalt in WPF</span><span class="sxs-lookup"><span data-stu-id="2d71d-102">Walkthrough: Hosting Direct3D9 Content in WPF</span></span>

<span data-ttu-id="2d71d-103">In dieser exemplarischen Vorgehensweise wird das Hosten von von Direct3D9-Inhalt in einer Windows Presentation Foundation (WPF)-Anwendung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="2d71d-103">This walkthrough shows how to host Direct3D9 content in a Windows Presentation Foundation (WPF) application.</span></span>

<span data-ttu-id="2d71d-104">Im Verlauf dieser exemplarischen Vorgehensweise führen Sie die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="2d71d-104">In this walkthrough, you perform the following tasks:</span></span>

- <span data-ttu-id="2d71d-105">Erstellen Sie ein WPF-Projekt zum Hosten des von Direct3D9-Inhalts.</span><span class="sxs-lookup"><span data-stu-id="2d71d-105">Create a WPF project to host the Direct3D9 content.</span></span>

- <span data-ttu-id="2d71d-106">Importieren Sie den von Direct3D9-Inhalt.</span><span class="sxs-lookup"><span data-stu-id="2d71d-106">Import the Direct3D9 content.</span></span>

- <span data-ttu-id="2d71d-107">Zeigen Sie den von Direct3D9-Inhalt mithilfe <xref:System.Windows.Interop.D3DImage> der-Klasse an.</span><span class="sxs-lookup"><span data-stu-id="2d71d-107">Display the Direct3D9 content by using the <xref:System.Windows.Interop.D3DImage> class.</span></span>

 <span data-ttu-id="2d71d-108">Wenn Sie fertig sind, wissen Sie, wie Sie von Direct3D9-Inhalte in einer WPF-Anwendung hosten.</span><span class="sxs-lookup"><span data-stu-id="2d71d-108">When you are finished, you will know how to host Direct3D9 content in a WPF application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2d71d-109">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="2d71d-109">Prerequisites</span></span>

<span data-ttu-id="2d71d-110">Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="2d71d-110">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="2d71d-111">Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2d71d-111">Visual Studio.</span></span>

- <span data-ttu-id="2d71d-112">DirectX SDK 9 oder höher.</span><span class="sxs-lookup"><span data-stu-id="2d71d-112">DirectX SDK 9 or later.</span></span>

- <span data-ttu-id="2d71d-113">Eine DLL, die von Direct3D9-Inhalt in einem WPF-kompatiblen Format enthält.</span><span class="sxs-lookup"><span data-stu-id="2d71d-113">A DLL that contains Direct3D9 content in a WPF-compatible format.</span></span> <span data-ttu-id="2d71d-114">Weitere Informationen finden Sie unter [WPF und von Direct3D9 Interoperation](wpf-and-direct3d9-interoperation.md) und [Exemplarische Vorgehensweise: Erstellen von von Direct3D9-Inhalt für das Hosting](walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)in WPF.</span><span class="sxs-lookup"><span data-stu-id="2d71d-114">For more information, see [WPF and Direct3D9 Interoperation](wpf-and-direct3d9-interoperation.md) and [Walkthrough: Creating Direct3D9 Content for Hosting in WPF](walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).</span></span>

## <a name="creating-the-wpf-project"></a><span data-ttu-id="2d71d-115">Erstellen des WPF-Projekts</span><span class="sxs-lookup"><span data-stu-id="2d71d-115">Creating the WPF Project</span></span>

<span data-ttu-id="2d71d-116">Der erste Schritt besteht darin, das Projekt für die WPF-Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2d71d-116">The first step is to create the project for the WPF application.</span></span>

### <a name="to-create-the-wpf-project"></a><span data-ttu-id="2d71d-117">So erstellen Sie das WPF-Projekt</span><span class="sxs-lookup"><span data-stu-id="2d71d-117">To create the WPF project</span></span>

<span data-ttu-id="2d71d-118">Erstellen Sie ein neues WPF-Anwendungsprojekt C# im `D3DHost`visuellen Element mit dem Namen.</span><span class="sxs-lookup"><span data-stu-id="2d71d-118">Create a new WPF Application project in Visual C# named `D3DHost`.</span></span> <span data-ttu-id="2d71d-119">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Meine erste WPF-Desktop](../getting-started/walkthrough-my-first-wpf-desktop-application.md)Anwendung.</span><span class="sxs-lookup"><span data-stu-id="2d71d-119">For more information, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

<span data-ttu-id="2d71d-120">Die [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]Datei "MainWindow. XAML" wird im geöffnet.</span><span class="sxs-lookup"><span data-stu-id="2d71d-120">MainWindow.xaml opens in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>

## <a name="importing-the-direct3d9-content"></a><span data-ttu-id="2d71d-121">Importieren des von Direct3D9-Inhalts</span><span class="sxs-lookup"><span data-stu-id="2d71d-121">Importing the Direct3D9 Content</span></span>

<span data-ttu-id="2d71d-122">Der von Direct3D9-Inhalt wird mithilfe des `DllImport` -Attributs aus einer nicht verwalteten DLL importiert.</span><span class="sxs-lookup"><span data-stu-id="2d71d-122">You import the Direct3D9 content from an unmanaged DLL by using the `DllImport` attribute.</span></span>

### <a name="to-import-direct3d9-content"></a><span data-ttu-id="2d71d-123">So importieren Sie von Direct3D9-Inhalt</span><span class="sxs-lookup"><span data-stu-id="2d71d-123">To import Direct3D9 content</span></span>

1. <span data-ttu-id="2d71d-124">Öffnen Sie MainWindow.XAML.cs im Code-Editor.</span><span class="sxs-lookup"><span data-stu-id="2d71d-124">Open MainWindow.xaml.cs in the Code Editor.</span></span>

2. <span data-ttu-id="2d71d-125">Ersetzen Sie den automatisch generierten Code durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="2d71d-125">Replace the automatically generated code with the following code.</span></span>

    [!code-csharp[System.Windows.Interop.D3DImage#1](~/samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml.cs#1)]

## <a name="hosting-the-direct3d9-content"></a><span data-ttu-id="2d71d-126">Hosting des von Direct3D9-Inhalts</span><span class="sxs-lookup"><span data-stu-id="2d71d-126">Hosting the Direct3D9 Content</span></span>

<span data-ttu-id="2d71d-127">Verwenden Sie abschließend die <xref:System.Windows.Interop.D3DImage> -Klasse, um den von Direct3D9-Inhalt zu hosten.</span><span class="sxs-lookup"><span data-stu-id="2d71d-127">Finally, use the <xref:System.Windows.Interop.D3DImage> class to host the Direct3D9 content.</span></span>

### <a name="to-host-the-direct3d9-content"></a><span data-ttu-id="2d71d-128">So hosten Sie den von Direct3D9-Inhalt</span><span class="sxs-lookup"><span data-stu-id="2d71d-128">To host the Direct3D9 content</span></span>

1. <span data-ttu-id="2d71d-129">Ersetzen Sie in "MainWindow. XAML" den automatisch generierten XAML-Code durch den folgenden XAML-Code.</span><span class="sxs-lookup"><span data-stu-id="2d71d-129">In MainWindow.xaml, replace the automatically generated XAML with the following XAML.</span></span>

    [!code-xaml[System.Windows.Interop.D3DImage#10](~/samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml#10)]

2. <span data-ttu-id="2d71d-130">Erstellen Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="2d71d-130">Build the project.</span></span>

3. <span data-ttu-id="2d71d-131">Kopieren Sie die dll, die den von Direct3D9-Inhalt enthält, in den Ordner bin/Debug.</span><span class="sxs-lookup"><span data-stu-id="2d71d-131">Copy the DLL that contains the Direct3D9 content to the bin/Debug folder.</span></span>

4. <span data-ttu-id="2d71d-132">Drücken Sie F5, um das Projekt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2d71d-132">Press F5 to run the project.</span></span>

    <span data-ttu-id="2d71d-133">Der von Direct3D9-Inhalt wird in der WPF-Anwendung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2d71d-133">The Direct3D9 content appears within the WPF application.</span></span>

## <a name="see-also"></a><span data-ttu-id="2d71d-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2d71d-134">See also</span></span>

- <xref:System.Windows.Interop.D3DImage>
- [<span data-ttu-id="2d71d-135">Überlegungen zur Leistung für die Interoperabilität zwischen Direct3D9 und WPF</span><span class="sxs-lookup"><span data-stu-id="2d71d-135">Performance Considerations for Direct3D9 and WPF Interoperability</span></span>](performance-considerations-for-direct3d9-and-wpf-interoperability.md)
