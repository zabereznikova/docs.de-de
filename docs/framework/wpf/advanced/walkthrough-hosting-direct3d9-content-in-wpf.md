---
title: 'Exemplarische Vorgehensweise: Hosten von Direct3D9-Inhalt in WPF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Direct3D9 [WPF interoperability], hosting Direct3D9 content
- WPF [WPF], hosting Direct3D9 content
ms.assetid: 60983736-0ab5-42cc-8b16-e9fbde261a43
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ec80eed37777fc7b17b435e1bef63ecbb94bdf46
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-hosting-direct3d9-content-in-wpf"></a><span data-ttu-id="fc913-102">Exemplarische Vorgehensweise: Hosten von Direct3D9-Inhalt in WPF</span><span class="sxs-lookup"><span data-stu-id="fc913-102">Walkthrough: Hosting Direct3D9 Content in WPF</span></span>
<span data-ttu-id="fc913-103">In dieser exemplarischen Vorgehensweise zeigt, wie Direct3D9-Inhalt in eine Windows Presentation Foundation (WPF)-Anwendung gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="fc913-103">This walkthrough shows how to host Direct3D9 content in a Windows Presentation Foundation (WPF) application.</span></span>  
  
 <span data-ttu-id="fc913-104">Im Verlauf dieser exemplarischen Vorgehensweise führen Sie die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="fc913-104">In this walkthrough, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="fc913-105">Erstellen Sie ein WPF-Projekt, um den Direct3D9-Inhalt hosten.</span><span class="sxs-lookup"><span data-stu-id="fc913-105">Create a WPF project to host the Direct3D9 content.</span></span>  
  
-   <span data-ttu-id="fc913-106">Importieren Sie den Direct3D9-Inhalt.</span><span class="sxs-lookup"><span data-stu-id="fc913-106">Import the Direct3D9 content.</span></span>  
  
-   <span data-ttu-id="fc913-107">Zeigt den Inhalt der Direct3D9 mithilfe der <xref:System.Windows.Interop.D3DImage> Klasse.</span><span class="sxs-lookup"><span data-stu-id="fc913-107">Display the Direct3D9 content by using the <xref:System.Windows.Interop.D3DImage> class.</span></span>  
  
 <span data-ttu-id="fc913-108">Wenn Sie fertig sind, wissen Sie, wie Direct3D9-Inhalt in einer WPF-Anwendung gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="fc913-108">When you are finished, you will know how to host Direct3D9 content in a WPF application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fc913-109">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="fc913-109">Prerequisites</span></span>  
 <span data-ttu-id="fc913-110">Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="fc913-110">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]<span data-ttu-id="fc913-111">.</span><span class="sxs-lookup"><span data-stu-id="fc913-111">.</span></span>  
  
-   <span data-ttu-id="fc913-112">DirectX SDK 9 oder höher.</span><span class="sxs-lookup"><span data-stu-id="fc913-112">DirectX SDK 9 or later.</span></span>  
  
-   <span data-ttu-id="fc913-113">Eine DLL, die Direct3D9-Inhalt in einem WPF-kompatiblen Format enthält.</span><span class="sxs-lookup"><span data-stu-id="fc913-113">A DLL that contains Direct3D9 content in a WPF-compatible format.</span></span> <span data-ttu-id="fc913-114">Weitere Informationen finden Sie unter [WPF und Direct3D9 Interoperation](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md) und [Exemplarische Vorgehensweise: Erstellen von Direct3D9 Content for Hosting in WPF](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="fc913-114">For more information, see [WPF and Direct3D9 Interoperation](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md) and [Walkthrough: Creating Direct3D9 Content for Hosting in WPF](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).</span></span>  
  
## <a name="creating-the-wpf-project"></a><span data-ttu-id="fc913-115">Erstellen des WPF-Projekts</span><span class="sxs-lookup"><span data-stu-id="fc913-115">Creating the WPF Project</span></span>  
 <span data-ttu-id="fc913-116">Der erste Schritt ist zum Erstellen des Projekts für die WPF-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="fc913-116">The first step is to create the project for the WPF application.</span></span>  
  
#### <a name="to-create-the-wpf-project"></a><span data-ttu-id="fc913-117">So erstellen Sie das WPF-Projekt</span><span class="sxs-lookup"><span data-stu-id="fc913-117">To create the WPF project</span></span>  
  
-   <span data-ttu-id="fc913-118">Erstellen ein neues WPF-Anwendungsprojekts in Visual c# mit dem Namen `D3DHost`.</span><span class="sxs-lookup"><span data-stu-id="fc913-118">Create a new WPF Application project in Visual C# named `D3DHost`.</span></span> <span data-ttu-id="fc913-119">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines neuen WPF-Anwendungsprojekts](http://msdn.microsoft.com/en-us/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span><span class="sxs-lookup"><span data-stu-id="fc913-119">For more information, see [How to: Create a New WPF Application Project](http://msdn.microsoft.com/en-us/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span></span>  
  
     <span data-ttu-id="fc913-120">"MainWindow.xaml" wird geöffnet, der [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fc913-120">MainWindow.xaml opens in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
## <a name="importing-the-direct3d9-content"></a><span data-ttu-id="fc913-121">Importieren den Direct3D9-Inhalt</span><span class="sxs-lookup"><span data-stu-id="fc913-121">Importing the Direct3D9 Content</span></span>  
 <span data-ttu-id="fc913-122">Sie importieren die Direct3D9-Inhalte aus einer nicht verwalteten DLL mithilfe der `DllImport` Attribut.</span><span class="sxs-lookup"><span data-stu-id="fc913-122">You import the Direct3D9 content from an unmanaged DLL by using the `DllImport` attribute.</span></span>  
  
#### <a name="to-import-direct3d9-content"></a><span data-ttu-id="fc913-123">So importieren Sie Direct3D9-Inhalt</span><span class="sxs-lookup"><span data-stu-id="fc913-123">To import Direct3D9 content</span></span>  
  
1.  <span data-ttu-id="fc913-124">Öffnen Sie "MainWindow.Xaml.cs" im Code-Editor.</span><span class="sxs-lookup"><span data-stu-id="fc913-124">Open MainWindow.xaml.cs in the Code Editor.</span></span>  
  
2.  <span data-ttu-id="fc913-125">Ersetzen Sie den automatisch generierten Code durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="fc913-125">Replace the automatically generated code with the following code.</span></span>  
  
     [!code-csharp[System.Windows.Interop.D3DImage#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml.cs#1)]  
  
## <a name="hosting-the-direct3d9-content"></a><span data-ttu-id="fc913-126">Hosten des Inhalts Direct3D9</span><span class="sxs-lookup"><span data-stu-id="fc913-126">Hosting the Direct3D9 Content</span></span>  
 <span data-ttu-id="fc913-127">Verwenden Sie abschließend die <xref:System.Windows.Interop.D3DImage> Klasse zum Hosten des Direct3D9-Inhalts.</span><span class="sxs-lookup"><span data-stu-id="fc913-127">Finally, use the <xref:System.Windows.Interop.D3DImage> class to host the Direct3D9 content.</span></span>  
  
#### <a name="to-host-the-direct3d9-content"></a><span data-ttu-id="fc913-128">Zum Hosten des Inhalts Direct3D9</span><span class="sxs-lookup"><span data-stu-id="fc913-128">To host the Direct3D9 content</span></span>  
  
1.  <span data-ttu-id="fc913-129">Ersetzen Sie in "MainWindow.xaml" den automatisch generierten XAML-Code durch Folgendes XAML.</span><span class="sxs-lookup"><span data-stu-id="fc913-129">In MainWindow.xaml, replace the automatically generated XAML with the following XAML.</span></span>  
  
     [!code-xaml[System.Windows.Interop.D3DImage#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml#10)]  
  
2.  <span data-ttu-id="fc913-130">Erstellen Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="fc913-130">Build the project.</span></span>  
  
3.  <span data-ttu-id="fc913-131">Kopieren Sie die DLL, die den Direct3D9-Inhalt in den Ordner "bin" / Debug enthält.</span><span class="sxs-lookup"><span data-stu-id="fc913-131">Copy the DLL that contains the Direct3D9 content to the bin/Debug folder.</span></span>  
  
4.  <span data-ttu-id="fc913-132">Drücken Sie F5, um das Projekt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="fc913-132">Press F5 to run the project.</span></span>  
  
     <span data-ttu-id="fc913-133">Der Direct3D9-Inhalt in der WPF-Anwendung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="fc913-133">The Direct3D9 content appears within the WPF application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc913-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc913-134">See Also</span></span>  
 <xref:System.Windows.Interop.D3DImage>  
 [<span data-ttu-id="fc913-135">Überlegungen zur Leistung für die Interoperabilität zwischen Direct3D9 und WPF</span><span class="sxs-lookup"><span data-stu-id="fc913-135">Performance Considerations for Direct3D9 and WPF Interoperability</span></span>](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md)
