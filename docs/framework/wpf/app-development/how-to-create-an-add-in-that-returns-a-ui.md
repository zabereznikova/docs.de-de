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
ms.openlocfilehash: d799c91b9abdf7882a0fcd3f0b656eac553b188c
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460149"
---
# <a name="how-to-create-an-add-in-that-returns-a-ui"></a><span data-ttu-id="867ae-102">Gewusst wie: Erstellen eines Add-Ins, das eine Benutzeroberfläche zurückgibt</span><span class="sxs-lookup"><span data-stu-id="867ae-102">How to: Create an Add-In That Returns a UI</span></span>
<span data-ttu-id="867ae-103">Dieses Beispiel zeigt, wie Sie ein Add-in erstellen, das eine Windows Presentation Foundation (WPF) an eine eigenständige WPF-Host Anwendung zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="867ae-103">This example shows how to create an add-in that returns a Windows Presentation Foundation (WPF) to a host WPF standalone application.</span></span>  
  
 <span data-ttu-id="867ae-104">Das Add-in gibt eine Benutzeroberfläche zurück, die ein WPF-Benutzer Steuerelement ist.</span><span class="sxs-lookup"><span data-stu-id="867ae-104">The add-in returns a UI that is a WPF user control.</span></span> <span data-ttu-id="867ae-105">Der Inhalt des Benutzersteuerelements ist eine einzelne Schaltfläche, bei der ein Meldungsfeld angezeigt wird, wenn Benutzer darauf klicken.</span><span class="sxs-lookup"><span data-stu-id="867ae-105">The content of the user control is a single button that, when clicked, displays a message box.</span></span> <span data-ttu-id="867ae-106">Die eigenständige WPF-Anwendung hostet das Add-in und zeigt das Benutzer Steuerelement (das vom Add-in zurückgegeben wird) als Inhalt des Hauptfensters der Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="867ae-106">The WPF standalone application hosts the add-in and displays the user control (returned by the add-in) as the content of the main application window.</span></span>  
  
 <span data-ttu-id="867ae-107">**Erforderliche Komponenten**</span><span class="sxs-lookup"><span data-stu-id="867ae-107">**Prerequisites**</span></span>  
  
 <span data-ttu-id="867ae-108">In diesem Beispiel werden die WPF-Erweiterungen für das .NET Framework Add-in-Modell hervorgehoben, das dieses Szenario ermöglicht, und es wird Folgendes vorausgesetzt:</span><span class="sxs-lookup"><span data-stu-id="867ae-108">This example highlights the WPF extensions to the .NET Framework add-in model that enable this scenario, and assumes the following:</span></span>  
  
- <span data-ttu-id="867ae-109">Kenntnisse des .NET Framework Add-in-Modells, einschließlich Pipeline, Add-in und Host Entwicklung.</span><span class="sxs-lookup"><span data-stu-id="867ae-109">Knowledge of the .NET Framework add-in model, including pipeline, add-in, and host development.</span></span> <span data-ttu-id="867ae-110">Wenn Sie mit diesen Konzepten nicht vertraut sind, finden Sie weitere Informationen unter [Add-Ins und Erweiterbarkeit](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)).</span><span class="sxs-lookup"><span data-stu-id="867ae-110">If you are unfamiliar with these concepts, see [Add-ins and Extensibility](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)).</span></span> <span data-ttu-id="867ae-111">Ein Tutorial, in dem die Implementierung einer Pipeline, ein Add-in und eine Host Anwendung veranschaulicht wird, finden Sie unter Exemplarische Vorgehensweise [: Erstellen einer erweiterbaren Anwendung](/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100)).</span><span class="sxs-lookup"><span data-stu-id="867ae-111">For a tutorial that demonstrates the implementation of a pipeline, an add-in, and a host application, see [Walkthrough: Creating an Extensible Application](/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100)).</span></span>  
  
- <span data-ttu-id="867ae-112">Informationen zu den WPF-Erweiterungen für das .NET Framework Add-in-Modell finden Sie hier: [Übersicht über WPF-Add-ins](wpf-add-ins-overview.md).</span><span class="sxs-lookup"><span data-stu-id="867ae-112">Knowledge of the WPF extensions to the .NET Framework add-in model, which can be found here: [WPF Add-Ins Overview](wpf-add-ins-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="867ae-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="867ae-113">Example</span></span>  
 <span data-ttu-id="867ae-114">Zum Erstellen eines Add-Ins, das eine WPF-Benutzeroberfläche zurückgibt, ist bestimmter Code für jedes Pipeline Segment, das Add-in und die Host Anwendung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="867ae-114">To create an add-in that returns a WPF UI requires specific code for each pipeline segment, the add-in, and the host application.</span></span>  

<a name="Contract"></a>   
## <a name="implementing-the-contract-pipeline-segment"></a><span data-ttu-id="867ae-115">Implementieren des Vertragspipelinesegments</span><span class="sxs-lookup"><span data-stu-id="867ae-115">Implementing the Contract Pipeline Segment</span></span>  
 <span data-ttu-id="867ae-116">Eine Methode muss durch den Vertrag zum Zurückgeben einer Benutzeroberfläche definiert werden, und der Rückgabewert muss vom Typ "<xref:System.AddIn.Contract.INativeHandleContract>" sein.</span><span class="sxs-lookup"><span data-stu-id="867ae-116">A method must be defined by the contract for returning a UI, and its return value must be of type <xref:System.AddIn.Contract.INativeHandleContract>.</span></span> <span data-ttu-id="867ae-117">Dies wird durch die `GetAddInUI`-Methode des `IWPFAddInContract`-Vertrags im folgenden Code veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="867ae-117">This is demonstrated by the `GetAddInUI` method of the `IWPFAddInContract` contract in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
 [!code-vb[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]  
  
<a name="AddInView"></a>   
## <a name="implementing-the-add-in-view-pipeline-segment"></a><span data-ttu-id="867ae-118">Implementieren des Add-In-Ansichtspipelinesegments</span><span class="sxs-lookup"><span data-stu-id="867ae-118">Implementing the Add-In View Pipeline Segment</span></span>  
 <span data-ttu-id="867ae-119">Da das Add-in die UIs implementiert, die es als Unterklassen von <xref:System.Windows.FrameworkElement>bereitstellt, muss die-Methode in der Add-in-Ansicht, die `IWPFAddInView.GetAddInUI` korreliert, einen Wert vom Typ <xref:System.Windows.FrameworkElement>zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="867ae-119">Because the add-in implements the UIs it provides as subclasses of <xref:System.Windows.FrameworkElement>, the method on the add-in view that correlates to `IWPFAddInView.GetAddInUI` must return a value of type <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="867ae-120">Im folgenden Code wird die als Schnittstelle implementierte Add-In-Ansicht des Vertrags gezeigt.</span><span class="sxs-lookup"><span data-stu-id="867ae-120">The following code shows the add-in view of the contract, implemented as an interface.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInViews/IWPFAddInView.cs#addinviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInViews/IWPFAddInView.vb#addinviewcode)]  
  
<a name="AddInSideAdapter"></a>   
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a><span data-ttu-id="867ae-121">Implementieren des Add-In-seitigen Adapterpipelinesegments</span><span class="sxs-lookup"><span data-stu-id="867ae-121">Implementing the Add-In-Side Adapter Pipeline Segment</span></span>  
 <span data-ttu-id="867ae-122">Die Contract-Methode gibt einen <xref:System.AddIn.Contract.INativeHandleContract>zurück, aber das Add-in gibt eine <xref:System.Windows.FrameworkElement> zurück (wie von der Add-in-Ansicht angegeben).</span><span class="sxs-lookup"><span data-stu-id="867ae-122">The contract method returns an <xref:System.AddIn.Contract.INativeHandleContract>, but the add-in returns a <xref:System.Windows.FrameworkElement> (as specified by the add-in view).</span></span> <span data-ttu-id="867ae-123">Folglich muss die <xref:System.Windows.FrameworkElement> vor dem Überschreiten der Isolations Grenze in eine <xref:System.AddIn.Contract.INativeHandleContract> konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="867ae-123">Consequently, the <xref:System.Windows.FrameworkElement> must be converted to an <xref:System.AddIn.Contract.INativeHandleContract> before crossing the isolation boundary.</span></span> <span data-ttu-id="867ae-124">Diese Arbeit wird vom Add-in-seitigen Adapter durch Aufrufen von <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>ausgeführt, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="867ae-124">This work is performed by the add-in-side adapter by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, as shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]  
  
<a name="HostView"></a>   
## <a name="implementing-the-host-view-pipeline-segment"></a><span data-ttu-id="867ae-125">Implementieren des Host-Ansichtspipelinesegments</span><span class="sxs-lookup"><span data-stu-id="867ae-125">Implementing the Host View Pipeline Segment</span></span>  
 <span data-ttu-id="867ae-126">Da die Host Anwendung eine <xref:System.Windows.FrameworkElement>anzeigt, muss die Methode in der Host Ansicht, die `IWPFAddInHostView.GetAddInUI` korreliert, einen Wert vom Typ <xref:System.Windows.FrameworkElement>zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="867ae-126">Because the host application will display a <xref:System.Windows.FrameworkElement>, the method on the host view that correlates to `IWPFAddInHostView.GetAddInUI` must return a value of type <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="867ae-127">Im folgenden Code wird die als Schnittstelle implementierte Hostansicht des Vertrags gezeigt.</span><span class="sxs-lookup"><span data-stu-id="867ae-127">The following code shows the host view of the contract, implemented as an interface.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostViews/IWPFAddInHostView.cs#hostviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostViews/IWPFAddInHostView.vb#hostviewcode)]  
  
<a name="HostSideAdapter"></a>   
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a><span data-ttu-id="867ae-128">Implementieren des hostseitigen Adapterpipelinesegments</span><span class="sxs-lookup"><span data-stu-id="867ae-128">Implementing the Host-Side Adapter Pipeline Segment</span></span>  
 <span data-ttu-id="867ae-129">Die Contract-Methode gibt einen <xref:System.AddIn.Contract.INativeHandleContract>zurück, die Host Anwendung erwartet jedoch eine <xref:System.Windows.FrameworkElement> (wie von der Host Ansicht angegeben).</span><span class="sxs-lookup"><span data-stu-id="867ae-129">The contract method returns an <xref:System.AddIn.Contract.INativeHandleContract>, but the host application expects a <xref:System.Windows.FrameworkElement> (as specified by the host view).</span></span> <span data-ttu-id="867ae-130">Folglich muss die <xref:System.AddIn.Contract.INativeHandleContract> nach dem Überschreiten der Isolations Grenze in eine <xref:System.Windows.FrameworkElement> konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="867ae-130">Consequently, the <xref:System.AddIn.Contract.INativeHandleContract> must be converted to a <xref:System.Windows.FrameworkElement> after crossing the isolation boundary.</span></span> <span data-ttu-id="867ae-131">Diese Arbeit wird vom Host seitigen Adapter durch Aufrufen von <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>ausgeführt, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="867ae-131">This work is performed by the host-side adapter by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, as shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#hostsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#hostsideadaptercode)]  
  
<a name="AddIn"></a>   
## <a name="implementing-the-add-in"></a><span data-ttu-id="867ae-132">Implementieren des Add-Ins</span><span class="sxs-lookup"><span data-stu-id="867ae-132">Implementing the Add-In</span></span>  
 <span data-ttu-id="867ae-133">Wenn der Add-in-seitige Adapter und die Add-in-Ansicht erstellt wurden, muss das Add-in (`WPFAddIn1.AddIn`) die `IWPFAddInView.GetAddInUI`-Methode implementieren, um ein <xref:System.Windows.FrameworkElement> Objekt zurückzugeben (in diesem Beispiel ein <xref:System.Windows.Controls.UserControl>).</span><span class="sxs-lookup"><span data-stu-id="867ae-133">With the add-in-side adapter and add-in view created, the add-in (`WPFAddIn1.AddIn`) must implement the `IWPFAddInView.GetAddInUI` method to return a <xref:System.Windows.FrameworkElement> object (a <xref:System.Windows.Controls.UserControl> in this example).</span></span> <span data-ttu-id="867ae-134">Der folgende Code zeigt die Implementierung der <xref:System.Windows.Controls.UserControl>, `AddInUI`.</span><span class="sxs-lookup"><span data-stu-id="867ae-134">The implementation of the <xref:System.Windows.Controls.UserControl>, `AddInUI`, is shown by the following code.</span></span>  
  
 [!code-xaml[SimpleAddInReturnsAUISample#AddInUIMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml#addinuimarkup)]  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#addinuicodebehind)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#addinuicodebehind)]  
  
 <span data-ttu-id="867ae-135">Die Implementierung des-`IWPFAddInView.GetAddInUI` durch das Add-in muss einfach eine neue Instanz von `AddInUI`zurückgeben, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="867ae-135">The implementation of the `IWPFAddInView.GetAddInUI` by the add-in simply needs to return a new instance of `AddInUI`, as shown by the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddIn.cs#addincode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddIn.vb#addincode)]  
  
<a name="App"></a>   
## <a name="implementing-the-host-application"></a><span data-ttu-id="867ae-136">Implementieren der Hostanwendung</span><span class="sxs-lookup"><span data-stu-id="867ae-136">Implementing the Host Application</span></span>  
 <span data-ttu-id="867ae-137">Wenn der Host seitige Adapter und die Host Ansicht erstellt wurden, kann die Host Anwendung das .NET Framework Add-in-Modell verwenden, um die Pipeline zu öffnen, eine Host Ansicht des Add-Ins abzurufen und die `IWPFAddInHostView.GetAddInUI`-Methode aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="867ae-137">With the host-side adapter and host view created, the host application can use the .NET Framework add-in model to open the pipeline, acquire a host view of the add-in, and call the `IWPFAddInHostView.GetAddInUI` method.</span></span> <span data-ttu-id="867ae-138">Diese Schritte werden im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="867ae-138">These steps are shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Host/MainWindow.xaml.cs#getuicode)]
 [!code-vb[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Host/MainWindow.xaml.vb#getuicode)]  
  
## <a name="see-also"></a><span data-ttu-id="867ae-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="867ae-139">See also</span></span>

- <span data-ttu-id="867ae-140">[Add-Ins und Erweiterbarkeit](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))</span><span class="sxs-lookup"><span data-stu-id="867ae-140">[Add-ins and Extensibility](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))</span></span>
- [<span data-ttu-id="867ae-141">Übersicht über WPF-Add-Ins</span><span class="sxs-lookup"><span data-stu-id="867ae-141">WPF Add-Ins Overview</span></span>](wpf-add-ins-overview.md)
