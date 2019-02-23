---
title: 'Exemplarische Vorgehensweise: Hosting Direct3D9 Content in WPF'
ms.date: 03/30/2017
helpviewer_keywords:
- Direct3D9 [WPF interoperability], hosting Direct3D9 content
- WPF [WPF], hosting Direct3D9 content
ms.assetid: 60983736-0ab5-42cc-8b16-e9fbde261a43
ms.openlocfilehash: 8a298bdd9a78279f177b5891bf69d0197ec7c040
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2019
ms.locfileid: "56746706"
---
# <a name="walkthrough-hosting-direct3d9-content-in-wpf"></a><span data-ttu-id="2ba98-102">Exemplarische Vorgehensweise: Hosting Direct3D9 Content in WPF</span><span class="sxs-lookup"><span data-stu-id="2ba98-102">Walkthrough: Hosting Direct3D9 Content in WPF</span></span>
<span data-ttu-id="2ba98-103">Diese exemplarische Vorgehensweise veranschaulicht das Hosten von Direct3D9-Inhalt in einer Windows Presentation Foundation (WPF)-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="2ba98-103">This walkthrough shows how to host Direct3D9 content in a Windows Presentation Foundation (WPF) application.</span></span>  
  
 <span data-ttu-id="2ba98-104">Im Verlauf dieser exemplarischen Vorgehensweise führen Sie die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="2ba98-104">In this walkthrough, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="2ba98-105">Erstellen Sie ein WPF-Projekt zum Hosten von Direct3D9-Inhalt.</span><span class="sxs-lookup"><span data-stu-id="2ba98-105">Create a WPF project to host the Direct3D9 content.</span></span>  
  
-   <span data-ttu-id="2ba98-106">Importieren des Direct3D9-Inhalts.</span><span class="sxs-lookup"><span data-stu-id="2ba98-106">Import the Direct3D9 content.</span></span>  
  
-   <span data-ttu-id="2ba98-107">Zeigt den Direct3D9-Inhalt mithilfe der <xref:System.Windows.Interop.D3DImage> Klasse.</span><span class="sxs-lookup"><span data-stu-id="2ba98-107">Display the Direct3D9 content by using the <xref:System.Windows.Interop.D3DImage> class.</span></span>  
  
 <span data-ttu-id="2ba98-108">Wenn Sie fertig sind, wissen Sie, wie zum Hosten von Direct3D9-Inhalt in einer WPF-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="2ba98-108">When you are finished, you will know how to host Direct3D9 content in a WPF application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2ba98-109">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="2ba98-109">Prerequisites</span></span>  
 <span data-ttu-id="2ba98-110">Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="2ba98-110">You need the following components to complete this walkthrough:</span></span>  
  
-   <span data-ttu-id="2ba98-111">Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2ba98-111">Visual Studio.</span></span>  
  
-   <span data-ttu-id="2ba98-112">DirectX SDK 9 oder höher.</span><span class="sxs-lookup"><span data-stu-id="2ba98-112">DirectX SDK 9 or later.</span></span>  
  
-   <span data-ttu-id="2ba98-113">Eine DLL, die von Direct3D9-Inhalt in einem WPF-kompatiblen Format enthält.</span><span class="sxs-lookup"><span data-stu-id="2ba98-113">A DLL that contains Direct3D9 content in a WPF-compatible format.</span></span> <span data-ttu-id="2ba98-114">Weitere Informationen finden Sie unter [zwischen WPF und Direct3D9](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md) und [Exemplarische Vorgehensweise: Erstellen von Direct3D9-Inhalten zum Hosten in WPF](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="2ba98-114">For more information, see [WPF and Direct3D9 Interoperation](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md) and [Walkthrough: Creating Direct3D9 Content for Hosting in WPF](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).</span></span>  
  
## <a name="creating-the-wpf-project"></a><span data-ttu-id="2ba98-115">Erstellen des WPF-Projekts</span><span class="sxs-lookup"><span data-stu-id="2ba98-115">Creating the WPF Project</span></span>  
 <span data-ttu-id="2ba98-116">Der erste Schritt ist die Erstellung des Projekts für die WPF-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="2ba98-116">The first step is to create the project for the WPF application.</span></span>  
  
#### <a name="to-create-the-wpf-project"></a><span data-ttu-id="2ba98-117">So erstellen Sie das WPF-Projekt</span><span class="sxs-lookup"><span data-stu-id="2ba98-117">To create the WPF project</span></span>  
  
-   <span data-ttu-id="2ba98-118">Erstellen Sie ein neues WPF-Anwendungsprojekt in Visual c# mit dem Namen `D3DHost`.</span><span class="sxs-lookup"><span data-stu-id="2ba98-118">Create a new WPF Application project in Visual C# named `D3DHost`.</span></span> <span data-ttu-id="2ba98-119">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span><span class="sxs-lookup"><span data-stu-id="2ba98-119">For more information, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>  
  
     <span data-ttu-id="2ba98-120">Datei "MainWindow.xaml" wird geöffnet, der [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ba98-120">MainWindow.xaml opens in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
## <a name="importing-the-direct3d9-content"></a><span data-ttu-id="2ba98-121">Importieren des Direct3D9-Inhalts</span><span class="sxs-lookup"><span data-stu-id="2ba98-121">Importing the Direct3D9 Content</span></span>  
 <span data-ttu-id="2ba98-122">Importieren Sie den Direct3D9-Inhalt aus einer nicht verwalteten DLL mithilfe der `DllImport` Attribut.</span><span class="sxs-lookup"><span data-stu-id="2ba98-122">You import the Direct3D9 content from an unmanaged DLL by using the `DllImport` attribute.</span></span>  
  
#### <a name="to-import-direct3d9-content"></a><span data-ttu-id="2ba98-123">Zum Importieren von Direct3D9-Inhalt</span><span class="sxs-lookup"><span data-stu-id="2ba98-123">To import Direct3D9 content</span></span>  
  
1.  <span data-ttu-id="2ba98-124">Öffnen Sie "MainWindow.Xaml.cs" im Code-Editor.</span><span class="sxs-lookup"><span data-stu-id="2ba98-124">Open MainWindow.xaml.cs in the Code Editor.</span></span>  
  
2.  <span data-ttu-id="2ba98-125">Ersetzen Sie den automatisch generierten Code durch den folgenden Code ein.</span><span class="sxs-lookup"><span data-stu-id="2ba98-125">Replace the automatically generated code with the following code.</span></span>  
  
     [!code-csharp[System.Windows.Interop.D3DImage#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml.cs#1)]  
  
## <a name="hosting-the-direct3d9-content"></a><span data-ttu-id="2ba98-126">Hosten von Direct3D9-Inhalt</span><span class="sxs-lookup"><span data-stu-id="2ba98-126">Hosting the Direct3D9 Content</span></span>  
 <span data-ttu-id="2ba98-127">Verwenden Sie abschließend die <xref:System.Windows.Interop.D3DImage> -Klasse zum Hosten von Direct3D9-Inhalt.</span><span class="sxs-lookup"><span data-stu-id="2ba98-127">Finally, use the <xref:System.Windows.Interop.D3DImage> class to host the Direct3D9 content.</span></span>  
  
#### <a name="to-host-the-direct3d9-content"></a><span data-ttu-id="2ba98-128">Zum Hosten von Direct3D9-Inhalt</span><span class="sxs-lookup"><span data-stu-id="2ba98-128">To host the Direct3D9 content</span></span>  
  
1.  <span data-ttu-id="2ba98-129">Ersetzen Sie in "MainWindow.xaml" die automatisch generierte XAML mit dem folgenden XAML.</span><span class="sxs-lookup"><span data-stu-id="2ba98-129">In MainWindow.xaml, replace the automatically generated XAML with the following XAML.</span></span>  
  
     [!code-xaml[System.Windows.Interop.D3DImage#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml#10)]  
  
2.  <span data-ttu-id="2ba98-130">Erstellen Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="2ba98-130">Build the project.</span></span>  
  
3.  <span data-ttu-id="2ba98-131">Kopieren Sie die DLL mit dem Direct3D9-Inhalt in den Ordner "bin" / Debug ist.</span><span class="sxs-lookup"><span data-stu-id="2ba98-131">Copy the DLL that contains the Direct3D9 content to the bin/Debug folder.</span></span>  
  
4.  <span data-ttu-id="2ba98-132">Drücken Sie F5, um das Projekt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2ba98-132">Press F5 to run the project.</span></span>  
  
     <span data-ttu-id="2ba98-133">Der Direct3D9-Inhalt wird innerhalb der WPF-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="2ba98-133">The Direct3D9 content appears within the WPF application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ba98-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ba98-134">See also</span></span>
- <xref:System.Windows.Interop.D3DImage>
- [<span data-ttu-id="2ba98-135">Überlegungen zur Leistung für die Interoperabilität zwischen Direct3D9 und WPF</span><span class="sxs-lookup"><span data-stu-id="2ba98-135">Performance Considerations for Direct3D9 and WPF Interoperability</span></span>](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md)
