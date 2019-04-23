---
title: 'Vorgehensweise: Erstellen eines Add-Ins, das eine Benutzeroberfläche zurückgibt'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating an add-in that returns a UI [WPF]
- implementing add-in pipeline segments [WPF]
- add-in [WPF], returns a UI
ms.assetid: 57f274b7-4c66-4b72-92eb-81939a393776
ms.openlocfilehash: faed11bb02037ea42b31402d431e1bcdd8b70339
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59115751"
---
# <a name="how-to-create-an-add-in-that-returns-a-ui"></a><span data-ttu-id="90f18-102">Vorgehensweise: Erstellen eines Add-Ins, das eine Benutzeroberfläche zurückgibt</span><span class="sxs-lookup"><span data-stu-id="90f18-102">How to: Create an Add-In That Returns a UI</span></span>
<span data-ttu-id="90f18-103">Dieses Beispiel zeigt, wie Sie ein Add-in erstellen, die eine Windows Presentation Foundation (WPF) auf einem Host eigenständige WPF-Anwendung zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="90f18-103">This example shows how to create an add-in that returns a Windows Presentation Foundation (WPF) to a host WPF standalone application.</span></span>  
  
 <span data-ttu-id="90f18-104">Gibt das Add-in eine Benutzeroberfläche, die ein WPF-Benutzersteuerelement ist.</span><span class="sxs-lookup"><span data-stu-id="90f18-104">The add-in returns a UI that is a WPF user control.</span></span> <span data-ttu-id="90f18-105">Der Inhalt des Benutzersteuerelements ist eine einzelne Schaltfläche, bei der ein Meldungsfeld angezeigt wird, wenn Benutzer darauf klicken.</span><span class="sxs-lookup"><span data-stu-id="90f18-105">The content of the user control is a single button that, when clicked, displays a message box.</span></span> <span data-ttu-id="90f18-106">Die eigenständige WPF-Anwendung hostet das Add-in und das Benutzersteuerelement (zurückgegeben durch das Add-in) zeigt, wie der Inhalt des Hauptfensters der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="90f18-106">The WPF standalone application hosts the add-in and displays the user control (returned by the add-in) as the content of the main application window.</span></span>  
  
 <span data-ttu-id="90f18-107">**Erforderliche Komponenten**</span><span class="sxs-lookup"><span data-stu-id="90f18-107">**Prerequisites**</span></span>  
  
 <span data-ttu-id="90f18-108">In diesem Beispiel hebt die WPF-Erweiterungen für die Add-In-Modell von .NET Framework, die dieses Szenario zu aktivieren, und es wird Folgendes vorausgesetzt:</span><span class="sxs-lookup"><span data-stu-id="90f18-108">This example highlights the WPF extensions to the .NET Framework add-in model that enable this scenario, and assumes the following:</span></span>  
  
-   <span data-ttu-id="90f18-109">Kenntnisse in Bezug auf die Add-In-Modell von .NET Framework, einschließlich der Pipeline, add-Ins und Hostentwicklung.</span><span class="sxs-lookup"><span data-stu-id="90f18-109">Knowledge of the .NET Framework add-in model, including pipeline, add-in, and host development.</span></span> <span data-ttu-id="90f18-110">Wenn Sie mit diesen Begriffen nicht vertraut sind, finden Sie unter [Add-Ins und Erweiterbarkeit](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)).</span><span class="sxs-lookup"><span data-stu-id="90f18-110">If you are unfamiliar with these concepts, see [Add-ins and Extensibility](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)).</span></span> <span data-ttu-id="90f18-111">Ein Lernprogramm, das die Implementierung einer Pipeline, ein Add-in und einer hostanwendung veranschaulicht, finden Sie unter [Exemplarische Vorgehensweise: Erstellen von erweiterbaren Anwendungen](../../add-ins/walkthrough-create-extensible-app.md).</span><span class="sxs-lookup"><span data-stu-id="90f18-111">For a tutorial that demonstrates the implementation of a pipeline, an add-in, and a host application, see [Walkthrough: Creating an Extensible Application](../../add-ins/walkthrough-create-extensible-app.md).</span></span>  
  
-   <span data-ttu-id="90f18-112">Kenntnisse über die WPF-Erweiterungen für das .NET Framework-add-in verwendet, das finden Sie hier: [Übersicht über das WPF-Add-Ins](wpf-add-ins-overview.md).</span><span class="sxs-lookup"><span data-stu-id="90f18-112">Knowledge of the WPF extensions to the .NET Framework add-in model, which can be found here: [WPF Add-Ins Overview](wpf-add-ins-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="90f18-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="90f18-113">Example</span></span>  
 <span data-ttu-id="90f18-114">Um ein Add-in zu erstellen, die eine WPF-UI zurückgibt ist spezieller Code für die einzelnen Pipelinesegmente, das Add-in und die hostanwendung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="90f18-114">To create an add-in that returns a WPF UI requires specific code for each pipeline segment, the add-in, and the host application.</span></span>  

<a name="Contract"></a>   
## <a name="implementing-the-contract-pipeline-segment"></a><span data-ttu-id="90f18-115">Implementieren des Vertragspipelinesegments</span><span class="sxs-lookup"><span data-stu-id="90f18-115">Implementing the Contract Pipeline Segment</span></span>  
 <span data-ttu-id="90f18-116">Eine Methode muss durch den Vertrag für die Rückgabe einer Benutzeroberflächenautomatisierungs definiert werden, und der Rückgabewert muss vom Typ <xref:System.AddIn.Contract.INativeHandleContract>.</span><span class="sxs-lookup"><span data-stu-id="90f18-116">A method must be defined by the contract for returning a UI, and its return value must be of type <xref:System.AddIn.Contract.INativeHandleContract>.</span></span> <span data-ttu-id="90f18-117">Dies wird veranschaulicht, durch die `GetAddInUI` Methode der `IWPFAddInContract` Datenvertrag in den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="90f18-117">This is demonstrated by the `GetAddInUI` method of the `IWPFAddInContract` contract in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
 [!code-vb[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]  
  
<a name="AddInView"></a>   
## <a name="implementing-the-add-in-view-pipeline-segment"></a><span data-ttu-id="90f18-118">Implementieren des Add-In-Ansichtspipelinesegments</span><span class="sxs-lookup"><span data-stu-id="90f18-118">Implementing the Add-In View Pipeline Segment</span></span>  
 <span data-ttu-id="90f18-119">Da das Add-in implementiert die [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] bietet als Unterklassen von <xref:System.Windows.FrameworkElement>, die Methode für die Add-In-Ansicht, die mit korreliert `IWPFAddInView.GetAddInUI` muss einen Wert vom Typ zurückgeben <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="90f18-119">Because the add-in implements the [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] it provides as subclasses of <xref:System.Windows.FrameworkElement>, the method on the add-in view that correlates to `IWPFAddInView.GetAddInUI` must return a value of type <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="90f18-120">Im folgenden Code wird die als Schnittstelle implementierte Add-In-Ansicht des Vertrags gezeigt.</span><span class="sxs-lookup"><span data-stu-id="90f18-120">The following code shows the add-in view of the contract, implemented as an interface.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInViews/IWPFAddInView.cs#addinviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInViews/IWPFAddInView.vb#addinviewcode)]  
  
<a name="AddInSideAdapter"></a>   
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a><span data-ttu-id="90f18-121">Implementieren des Add-In-seitigen Adapterpipelinesegments</span><span class="sxs-lookup"><span data-stu-id="90f18-121">Implementing the Add-In-Side Adapter Pipeline Segment</span></span>  
 <span data-ttu-id="90f18-122">Gibt zurück, durch die Vertragsmethode ein <xref:System.AddIn.Contract.INativeHandleContract>, das Add-in gibt jedoch eine <xref:System.Windows.FrameworkElement> (gemäß der Add-In-Ansicht).</span><span class="sxs-lookup"><span data-stu-id="90f18-122">The contract method returns an <xref:System.AddIn.Contract.INativeHandleContract>, but the add-in returns a <xref:System.Windows.FrameworkElement> (as specified by the add-in view).</span></span> <span data-ttu-id="90f18-123">Daher die <xref:System.Windows.FrameworkElement> konvertiert werden muss, um eine <xref:System.AddIn.Contract.INativeHandleContract> vor dem Überschreiten der Isolationsgrenze.</span><span class="sxs-lookup"><span data-stu-id="90f18-123">Consequently, the <xref:System.Windows.FrameworkElement> must be converted to an <xref:System.AddIn.Contract.INativeHandleContract> before crossing the isolation boundary.</span></span> <span data-ttu-id="90f18-124">Dieser Vorgang wird ausgeführt, durch den Add-In-seitigen Adapter durch Aufrufen von <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="90f18-124">This work is performed by the add-in-side adapter by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, as shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]  
  
<a name="HostView"></a>   
## <a name="implementing-the-host-view-pipeline-segment"></a><span data-ttu-id="90f18-125">Implementieren des Host-Ansichtspipelinesegments</span><span class="sxs-lookup"><span data-stu-id="90f18-125">Implementing the Host View Pipeline Segment</span></span>  
 <span data-ttu-id="90f18-126">Da in die hostanwendung angezeigt wird eine <xref:System.Windows.FrameworkElement>, die Methode der Hostansicht, die mit korreliert `IWPFAddInHostView.GetAddInUI` muss einen Wert vom Typ zurückgeben <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="90f18-126">Because the host application will display a <xref:System.Windows.FrameworkElement>, the method on the host view that correlates to `IWPFAddInHostView.GetAddInUI` must return a value of type <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="90f18-127">Im folgenden Code wird die als Schnittstelle implementierte Hostansicht des Vertrags gezeigt.</span><span class="sxs-lookup"><span data-stu-id="90f18-127">The following code shows the host view of the contract, implemented as an interface.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostViews/IWPFAddInHostView.cs#hostviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostViews/IWPFAddInHostView.vb#hostviewcode)]  
  
<a name="HostSideAdapter"></a>   
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a><span data-ttu-id="90f18-128">Implementieren des hostseitigen Adapterpipelinesegments</span><span class="sxs-lookup"><span data-stu-id="90f18-128">Implementing the Host-Side Adapter Pipeline Segment</span></span>  
 <span data-ttu-id="90f18-129">Gibt zurück, durch die Vertragsmethode ein <xref:System.AddIn.Contract.INativeHandleContract>, die hostanwendung erwartet jedoch eine <xref:System.Windows.FrameworkElement> (wie durch die Hostansicht festgelegt).</span><span class="sxs-lookup"><span data-stu-id="90f18-129">The contract method returns an <xref:System.AddIn.Contract.INativeHandleContract>, but the host application expects a <xref:System.Windows.FrameworkElement> (as specified by the host view).</span></span> <span data-ttu-id="90f18-130">Daher die <xref:System.AddIn.Contract.INativeHandleContract> konvertiert werden muss, um eine <xref:System.Windows.FrameworkElement> nach dem Überschreiten der Isolationsgrenze.</span><span class="sxs-lookup"><span data-stu-id="90f18-130">Consequently, the <xref:System.AddIn.Contract.INativeHandleContract> must be converted to a <xref:System.Windows.FrameworkElement> after crossing the isolation boundary.</span></span> <span data-ttu-id="90f18-131">Dieser Vorgang wird vom hostseitigen Adapter ausgeführt, durch den Aufruf <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="90f18-131">This work is performed by the host-side adapter by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, as shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#hostsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#hostsideadaptercode)]  
  
<a name="AddIn"></a>   
## <a name="implementing-the-add-in"></a><span data-ttu-id="90f18-132">Implementieren des Add-Ins</span><span class="sxs-lookup"><span data-stu-id="90f18-132">Implementing the Add-In</span></span>  
 <span data-ttu-id="90f18-133">Mit dem Add-In-seitige Adapter und Add-In-Ansicht erstellt, das Add-in (`WPFAddIn1.AddIn`) implementieren müssen die `IWPFAddInView.GetAddInUI` -Methode zur Rückgabe einer <xref:System.Windows.FrameworkElement> Objekt (ein <xref:System.Windows.Controls.UserControl> in diesem Beispiel).</span><span class="sxs-lookup"><span data-stu-id="90f18-133">With the add-in-side adapter and add-in view created, the add-in (`WPFAddIn1.AddIn`) must implement the `IWPFAddInView.GetAddInUI` method to return a <xref:System.Windows.FrameworkElement> object (a <xref:System.Windows.Controls.UserControl> in this example).</span></span> <span data-ttu-id="90f18-134">Die Implementierung der <xref:System.Windows.Controls.UserControl>, `AddInUI`, mit dem folgenden Code gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="90f18-134">The implementation of the <xref:System.Windows.Controls.UserControl>, `AddInUI`, is shown by the following code.</span></span>  
  
 [!code-xaml[SimpleAddInReturnsAUISample#AddInUIMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml#addinuimarkup)]  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#addinuicodebehind)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#addinuicodebehind)]  
  
 <span data-ttu-id="90f18-135">Die Implementierung der `IWPFAddInView.GetAddInUI` durch das Add-in muss einfach eine neue Instanz der zurückzugebenden `AddInUI`, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="90f18-135">The implementation of the `IWPFAddInView.GetAddInUI` by the add-in simply needs to return a new instance of `AddInUI`, as shown by the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddIn.cs#addincode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddIn.vb#addincode)]  
  
<a name="App"></a>   
## <a name="implementing-the-host-application"></a><span data-ttu-id="90f18-136">Implementieren der Hostanwendung</span><span class="sxs-lookup"><span data-stu-id="90f18-136">Implementing the Host Application</span></span>  
 <span data-ttu-id="90f18-137">Der hostseitige Adapter und die Hostansicht erstellt wurden, kann die hostanwendung die Add-In-Modell von .NET Framework verwenden, die Pipeline zu öffnen, erhalten eine Hostansicht des Add-Ins, und rufen die `IWPFAddInHostView.GetAddInUI` Methode.</span><span class="sxs-lookup"><span data-stu-id="90f18-137">With the host-side adapter and host view created, the host application can use the .NET Framework add-in model to open the pipeline, acquire a host view of the add-in, and call the `IWPFAddInHostView.GetAddInUI` method.</span></span> <span data-ttu-id="90f18-138">Diese Schritte werden im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="90f18-138">These steps are shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Host/MainWindow.xaml.cs#getuicode)]
 [!code-vb[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Host/MainWindow.xaml.vb#getuicode)]  
  
## <a name="see-also"></a><span data-ttu-id="90f18-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90f18-139">See also</span></span>

- <span data-ttu-id="90f18-140">[Add-Ins und Erweiterbarkeit](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))</span><span class="sxs-lookup"><span data-stu-id="90f18-140">[Add-ins and Extensibility](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))</span></span>
- [<span data-ttu-id="90f18-141">Übersicht über WPF-Add-Ins</span><span class="sxs-lookup"><span data-stu-id="90f18-141">WPF Add-Ins Overview</span></span>](wpf-add-ins-overview.md)
