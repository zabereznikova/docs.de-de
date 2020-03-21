---
title: 'Gewusst wie: Erstellen eines Add-Ins, das eine Benutzeroberfläche zurückgibt'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating an add-in that returns a UI [WPF]
- implementing add-in pipeline segments [WPF]
- add-in [WPF], returns a UI
ms.assetid: 57f274b7-4c66-4b72-92eb-81939a393776
ms.openlocfilehash: f8323fe35555a56d39c1efed649c2aa3fcf17e43
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174588"
---
# <a name="how-to-create-an-add-in-that-returns-a-ui"></a><span data-ttu-id="53554-102">Gewusst wie: Erstellen eines Add-Ins, das eine Benutzeroberfläche zurückgibt</span><span class="sxs-lookup"><span data-stu-id="53554-102">How to: Create an Add-In That Returns a UI</span></span>
<span data-ttu-id="53554-103">In diesem Beispiel wird gezeigt, wie Sie ein Add-In erstellen, das eine Windows Presentation Foundation (WPF) an eine eigenständige Host-WPF-Anwendung zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="53554-103">This example shows how to create an add-in that returns a Windows Presentation Foundation (WPF) to a host WPF standalone application.</span></span>  
  
 <span data-ttu-id="53554-104">Das Add-In gibt eine Benutzeroberfläche zurück, die ein WPF-Benutzersteuerelement ist.</span><span class="sxs-lookup"><span data-stu-id="53554-104">The add-in returns a UI that is a WPF user control.</span></span> <span data-ttu-id="53554-105">Der Inhalt des Benutzersteuerelements ist eine einzelne Schaltfläche, bei der ein Meldungsfeld angezeigt wird, wenn Benutzer darauf klicken.</span><span class="sxs-lookup"><span data-stu-id="53554-105">The content of the user control is a single button that, when clicked, displays a message box.</span></span> <span data-ttu-id="53554-106">Die eigenständige WPF-Anwendung hostet das Add-In und zeigt das Benutzersteuerelement (vom Add-In zurückgegeben) als Inhalt des Hauptanwendungsfensters an.</span><span class="sxs-lookup"><span data-stu-id="53554-106">The WPF standalone application hosts the add-in and displays the user control (returned by the add-in) as the content of the main application window.</span></span>  
  
 <span data-ttu-id="53554-107">**Voraussetzungen**</span><span class="sxs-lookup"><span data-stu-id="53554-107">**Prerequisites**</span></span>  
  
 <span data-ttu-id="53554-108">In diesem Beispiel werden die WPF-Erweiterungen des .NET Framework-Add-In-Modells hervorgehoben, die dieses Szenario aktivieren, und es wird Folgendes angenommen:</span><span class="sxs-lookup"><span data-stu-id="53554-108">This example highlights the WPF extensions to the .NET Framework add-in model that enable this scenario, and assumes the following:</span></span>  
  
- <span data-ttu-id="53554-109">Kenntnisse des .NET Framework-Add-In-Modells, einschließlich Pipeline-, Add-In- und Hostentwicklung.</span><span class="sxs-lookup"><span data-stu-id="53554-109">Knowledge of the .NET Framework add-in model, including pipeline, add-in, and host development.</span></span> <span data-ttu-id="53554-110">Wenn Sie mit diesen Konzepten nicht vertraut sind, finden Sie weitere Informationen unter [Add-Ins und Erweiterbarkeit](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)).</span><span class="sxs-lookup"><span data-stu-id="53554-110">If you are unfamiliar with these concepts, see [Add-ins and Extensibility](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)).</span></span> <span data-ttu-id="53554-111">Ein Tutorial, das die Implementierung einer Pipeline, eines Add-Ins und einer Hostanwendung veranschaulicht, finden Sie unter [Exemplarische Vorgehensweise: Erstellen einer erweiterbaren Anwendung](/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100)).</span><span class="sxs-lookup"><span data-stu-id="53554-111">For a tutorial that demonstrates the implementation of a pipeline, an add-in, and a host application, see [Walkthrough: Creating an Extensible Application](/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100)).</span></span>  
  
- <span data-ttu-id="53554-112">Kenntnisse der WPF-Erweiterungen des .NET Framework-Add-In-Modells, die Hier zu finden sind: [WPF Add-Ins Overview](wpf-add-ins-overview.md).</span><span class="sxs-lookup"><span data-stu-id="53554-112">Knowledge of the WPF extensions to the .NET Framework add-in model, which can be found here: [WPF Add-Ins Overview](wpf-add-ins-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="53554-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="53554-113">Example</span></span>  
 <span data-ttu-id="53554-114">Zum Erstellen eines Add-Ins, das eine WPF-Benutzeroberfläche zurückgibt, ist für jedes Pipelinesegment, das Add-In und die Hostanwendung ein spezifischer Code erforderlich.</span><span class="sxs-lookup"><span data-stu-id="53554-114">To create an add-in that returns a WPF UI requires specific code for each pipeline segment, the add-in, and the host application.</span></span>  

<a name="Contract"></a>
## <a name="implementing-the-contract-pipeline-segment"></a><span data-ttu-id="53554-115">Implementieren des Vertragspipelinesegments</span><span class="sxs-lookup"><span data-stu-id="53554-115">Implementing the Contract Pipeline Segment</span></span>  
 <span data-ttu-id="53554-116">Eine Methode muss durch den Vertrag für die Rückgabe einer Benutzeroberfläche definiert werden, und ihr Rückgabewert muss vom Typ <xref:System.AddIn.Contract.INativeHandleContract>sein.</span><span class="sxs-lookup"><span data-stu-id="53554-116">A method must be defined by the contract for returning a UI, and its return value must be of type <xref:System.AddIn.Contract.INativeHandleContract>.</span></span> <span data-ttu-id="53554-117">Dies wird `GetAddInUI` durch die `IWPFAddInContract` Methode des Vertrags im folgenden Code demonstriert.</span><span class="sxs-lookup"><span data-stu-id="53554-117">This is demonstrated by the `GetAddInUI` method of the `IWPFAddInContract` contract in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
 [!code-vb[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]  
  
<a name="AddInView"></a>
## <a name="implementing-the-add-in-view-pipeline-segment"></a><span data-ttu-id="53554-118">Implementieren des Add-In-Ansichtspipelinesegments</span><span class="sxs-lookup"><span data-stu-id="53554-118">Implementing the Add-In View Pipeline Segment</span></span>  
 <span data-ttu-id="53554-119">Da das Add-In die von ihm als <xref:System.Windows.FrameworkElement>Unterklassen von bereitstellten U-IIs `IWPFAddInView.GetAddInUI` implementiert, muss die <xref:System.Windows.FrameworkElement>Methode in der Add-In-Ansicht, die korreliert, einen Wert des Typs zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="53554-119">Because the add-in implements the UIs it provides as subclasses of <xref:System.Windows.FrameworkElement>, the method on the add-in view that correlates to `IWPFAddInView.GetAddInUI` must return a value of type <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="53554-120">Im folgenden Code wird die als Schnittstelle implementierte Add-In-Ansicht des Vertrags gezeigt.</span><span class="sxs-lookup"><span data-stu-id="53554-120">The following code shows the add-in view of the contract, implemented as an interface.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInViews/IWPFAddInView.cs#addinviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInViews/IWPFAddInView.vb#addinviewcode)]  
  
<a name="AddInSideAdapter"></a>
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a><span data-ttu-id="53554-121">Implementieren des Add-In-seitigen Adapterpipelinesegments</span><span class="sxs-lookup"><span data-stu-id="53554-121">Implementing the Add-In-Side Adapter Pipeline Segment</span></span>  
 <span data-ttu-id="53554-122">Die Vertragsmethode <xref:System.AddIn.Contract.INativeHandleContract>gibt eine zurück, aber <xref:System.Windows.FrameworkElement> das Add-In gibt eine zurück (wie in der Add-In-Ansicht angegeben).</span><span class="sxs-lookup"><span data-stu-id="53554-122">The contract method returns an <xref:System.AddIn.Contract.INativeHandleContract>, but the add-in returns a <xref:System.Windows.FrameworkElement> (as specified by the add-in view).</span></span> <span data-ttu-id="53554-123">Folglich muss <xref:System.Windows.FrameworkElement> die in <xref:System.AddIn.Contract.INativeHandleContract> eine umgewandelt werden, bevor die Isolationsgrenze überschritten wird.</span><span class="sxs-lookup"><span data-stu-id="53554-123">Consequently, the <xref:System.Windows.FrameworkElement> must be converted to an <xref:System.AddIn.Contract.INativeHandleContract> before crossing the isolation boundary.</span></span> <span data-ttu-id="53554-124">Diese Arbeit wird vom Add-in-Side-Adapter ausgeführt, indem er aufruft, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="53554-124">This work is performed by the add-in-side adapter by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, as shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]  
  
<a name="HostView"></a>
## <a name="implementing-the-host-view-pipeline-segment"></a><span data-ttu-id="53554-125">Implementieren des Host-Ansichtspipelinesegments</span><span class="sxs-lookup"><span data-stu-id="53554-125">Implementing the Host View Pipeline Segment</span></span>  
 <span data-ttu-id="53554-126">Da die Hostanwendung <xref:System.Windows.FrameworkElement>eine anzeigt, `IWPFAddInHostView.GetAddInUI` muss die Methode in der Hostansicht, mit der korreliert, einen Wert vom Typ <xref:System.Windows.FrameworkElement>zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="53554-126">Because the host application will display a <xref:System.Windows.FrameworkElement>, the method on the host view that correlates to `IWPFAddInHostView.GetAddInUI` must return a value of type <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="53554-127">Im folgenden Code wird die als Schnittstelle implementierte Hostansicht des Vertrags gezeigt.</span><span class="sxs-lookup"><span data-stu-id="53554-127">The following code shows the host view of the contract, implemented as an interface.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostViews/IWPFAddInHostView.cs#hostviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostViews/IWPFAddInHostView.vb#hostviewcode)]  
  
<a name="HostSideAdapter"></a>
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a><span data-ttu-id="53554-128">Implementieren des hostseitigen Adapterpipelinesegments</span><span class="sxs-lookup"><span data-stu-id="53554-128">Implementing the Host-Side Adapter Pipeline Segment</span></span>  
 <span data-ttu-id="53554-129">Die Vertragsmethode <xref:System.AddIn.Contract.INativeHandleContract>gibt eine zurück, <xref:System.Windows.FrameworkElement> aber die Hostanwendung erwartet eine (wie in der Hostansicht angegeben).</span><span class="sxs-lookup"><span data-stu-id="53554-129">The contract method returns an <xref:System.AddIn.Contract.INativeHandleContract>, but the host application expects a <xref:System.Windows.FrameworkElement> (as specified by the host view).</span></span> <span data-ttu-id="53554-130">Folglich muss <xref:System.AddIn.Contract.INativeHandleContract> die nach <xref:System.Windows.FrameworkElement> dem Überschreiten der Isolationsgrenze in eine umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="53554-130">Consequently, the <xref:System.AddIn.Contract.INativeHandleContract> must be converted to a <xref:System.Windows.FrameworkElement> after crossing the isolation boundary.</span></span> <span data-ttu-id="53554-131">Diese Arbeit wird vom hostseitigen Adapter <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>ausgeführt, indem er aufruft, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="53554-131">This work is performed by the host-side adapter by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, as shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#hostsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#hostsideadaptercode)]  
  
<a name="AddIn"></a>
## <a name="implementing-the-add-in"></a><span data-ttu-id="53554-132">Implementieren des Add-Ins</span><span class="sxs-lookup"><span data-stu-id="53554-132">Implementing the Add-In</span></span>  
 <span data-ttu-id="53554-133">Wenn der Add-in-Side-Adapter und die Add-In-Ansicht erstellt wurden, muss das Add-In (`WPFAddIn1.AddIn`) die `IWPFAddInView.GetAddInUI` Methode implementieren, um ein <xref:System.Windows.FrameworkElement> Objekt zurückzugeben (in <xref:System.Windows.Controls.UserControl> diesem Beispiel).</span><span class="sxs-lookup"><span data-stu-id="53554-133">With the add-in-side adapter and add-in view created, the add-in (`WPFAddIn1.AddIn`) must implement the `IWPFAddInView.GetAddInUI` method to return a <xref:System.Windows.FrameworkElement> object (a <xref:System.Windows.Controls.UserControl> in this example).</span></span> <span data-ttu-id="53554-134">Die Implementierung <xref:System.Windows.Controls.UserControl>von `AddInUI`, wird durch den folgenden Code angezeigt.</span><span class="sxs-lookup"><span data-stu-id="53554-134">The implementation of the <xref:System.Windows.Controls.UserControl>, `AddInUI`, is shown by the following code.</span></span>  
  
 [!code-xaml[SimpleAddInReturnsAUISample#AddInUIMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml#addinuimarkup)]  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#addinuicodebehind)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#addinuicodebehind)]  
  
 <span data-ttu-id="53554-135">Die Implementierung `IWPFAddInView.GetAddInUI` des durch das Add-In muss einfach `AddInUI`eine neue Instanz von zurückgeben, wie der folgende Code zeigt.</span><span class="sxs-lookup"><span data-stu-id="53554-135">The implementation of the `IWPFAddInView.GetAddInUI` by the add-in simply needs to return a new instance of `AddInUI`, as shown by the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddIn.cs#addincode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddIn.vb#addincode)]  
  
<a name="App"></a>
## <a name="implementing-the-host-application"></a><span data-ttu-id="53554-136">Implementieren der Hostanwendung</span><span class="sxs-lookup"><span data-stu-id="53554-136">Implementing the Host Application</span></span>  
 <span data-ttu-id="53554-137">Wenn der hostseitige Adapter und die Hostansicht erstellt wurden, kann die Hostanwendung das .NET Framework-Add-In-Modell verwenden, um die Pipeline zu öffnen, eine Hostansicht des Add-Ins zu erhalten und die `IWPFAddInHostView.GetAddInUI` Methode aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="53554-137">With the host-side adapter and host view created, the host application can use the .NET Framework add-in model to open the pipeline, acquire a host view of the add-in, and call the `IWPFAddInHostView.GetAddInUI` method.</span></span> <span data-ttu-id="53554-138">Diese Schritte werden im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="53554-138">These steps are shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Host/MainWindow.xaml.cs#getuicode)]
 [!code-vb[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Host/MainWindow.xaml.vb#getuicode)]  
  
## <a name="see-also"></a><span data-ttu-id="53554-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="53554-139">See also</span></span>

- <span data-ttu-id="53554-140">[Add-Ins und Erweiterbarkeit](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))</span><span class="sxs-lookup"><span data-stu-id="53554-140">[Add-ins and Extensibility](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))</span></span>
- [<span data-ttu-id="53554-141">Übersicht über WPF-Add-Ins</span><span class="sxs-lookup"><span data-stu-id="53554-141">WPF Add-Ins Overview</span></span>](wpf-add-ins-overview.md)
