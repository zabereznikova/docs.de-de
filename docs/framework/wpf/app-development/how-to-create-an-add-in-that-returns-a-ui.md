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
ms.openlocfilehash: 24b30d61553796840a44a869eacb33232a0b78d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-an-add-in-that-returns-a-ui"></a>Gewusst wie: Erstellen eines Add-Ins, das eine Benutzeroberfläche zurückgibt
In diesem Beispiel wird gezeigt, wie ein Add-in erstellen, die eine Windows Presentation Foundation (WPF) auf einem Host zurückgibt [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] eigenständige Anwendung.  
  
 Gibt das Add-in einen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] also ein [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Benutzersteuerelement. Der Inhalt des Benutzersteuerelements ist eine einzelne Schaltfläche, bei der ein Meldungsfeld angezeigt wird, wenn Benutzer darauf klicken. Die [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] eigenständige Anwendung hostet das Add-in und das Benutzersteuerelement (zurückgegeben durch das Add-in) zeigt, wie der Inhalt des Hauptfensters der Anwendung.  
  
 **Erforderliche Komponenten**  
  
 In diesem Beispiel hebt die [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] -Erweiterungen für die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Add-In-Modell, mit denen dieses Szenario, und setzt Folgendes voraus:  
  
-   Kenntnisse der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Add-In-Modell, einschließlich der Pipeline, add-Ins und Hostentwicklung. Wenn Sie mit diesen Konzepten nicht vertraut sind, finden Sie unter [Add-Ins und Erweiterbarkeit](../../../../docs/framework/add-ins/index.md). Ein Lernprogramm, das die Implementierung einer Pipeline, ein Add-in und eine hostanwendung veranschaulicht, finden Sie unter [Exemplarische Vorgehensweise: Erstellen einer erweiterbaren Anwendung](../../../../docs/framework/add-ins/walkthrough-create-extensible-app.md).  
  
-   Kenntnisse der [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] -Erweiterungen für die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Add-In-Modell, die sich hier befinden: [Übersicht über WPF-Add-Ins](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md).  
  
## <a name="example"></a>Beispiel  
 So erstellen ein Add-in, zurückgibt eine [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] speziellen Code für jedes Pipelinesegment, das Add-in und die hostanwendung erfordert.  
    
  
<a name="Contract"></a>   
## <a name="implementing-the-contract-pipeline-segment"></a>Implementieren des Vertragspipelinesegments  
 Eine Methode muss definiert werden, durch den Vertrag für die Rückgabe einer [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], und der Rückgabewert muss vom Typ <xref:System.AddIn.Contract.INativeHandleContract>. Dies wird dargestellt, indem die `GetAddInUI` Methode der `IWPFAddInContract` Vertrag im folgenden Code.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#ContractCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
 [!code-vb[SimpleAddInReturnsAUISample#ContractCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]  
  
<a name="AddInView"></a>   
## <a name="implementing-the-add-in-view-pipeline-segment"></a>Implementieren des Add-In-Ansichtspipelinesegments  
 Da das Add-In implementiert die [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] bietet als Unterklasse von <xref:System.Windows.FrameworkElement>, die Methode für die Add-in-Sicht, die mit korreliert `IWPFAddInView.GetAddInUI` muss einen Wert vom Typ zurückgeben <xref:System.Windows.FrameworkElement>. Im folgenden Code wird die als Schnittstelle implementierte Add-In-Ansicht des Vertrags gezeigt.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInViewCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInViews/IWPFAddInView.cs#addinviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInViewCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInViews/IWPFAddInView.vb#addinviewcode)]  
  
<a name="AddInSideAdapter"></a>   
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a>Implementieren des Add-In-seitigen Adapterpipelinesegments  
 Der Vertrag Methodenrückgabe ein <xref:System.AddIn.Contract.INativeHandleContract>, das Add-in gibt jedoch eine <xref:System.Windows.FrameworkElement> (nach den Angaben von der Add-In-Ansicht). Folglich die <xref:System.Windows.FrameworkElement> muss eine Konvertierung in eine <xref:System.AddIn.Contract.INativeHandleContract> vor dem Überschreiten der Isolationsgrenze. Dieser Vorgang wird durch Aufrufen der Add-In-seitiger Adapter ausgeführt <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, wie im folgenden Code gezeigt.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInSideAdapterCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInSideAdapterCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]  
  
<a name="HostView"></a>   
## <a name="implementing-the-host-view-pipeline-segment"></a>Implementieren des Host-Ansichtspipelinesegments  
 Da die Host-Anwendung angezeigt wird eine <xref:System.Windows.FrameworkElement>, die Methode in der Hostansicht, die mit korreliert `IWPFAddInHostView.GetAddInUI` muss einen Wert vom Typ zurückgeben <xref:System.Windows.FrameworkElement>. Im folgenden Code wird die als Schnittstelle implementierte Hostansicht des Vertrags gezeigt.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostViewCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostViews/IWPFAddInHostView.cs#hostviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostViewCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostViews/IWPFAddInHostView.vb#hostviewcode)]  
  
<a name="HostSideAdapter"></a>   
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a>Implementieren des hostseitigen Adapterpipelinesegments  
 Der Vertrag Methodenrückgabe ein <xref:System.AddIn.Contract.INativeHandleContract>, aber der hostanwendung erwartet, dass eine <xref:System.Windows.FrameworkElement> (wie in der Hostansicht angegeben). Folglich die <xref:System.AddIn.Contract.INativeHandleContract> muss eine Konvertierung in einen <xref:System.Windows.FrameworkElement> nach dem Überschreiten der Isolationsgrenze. Dieser Vorgang wird durch Aufrufen der hostseitige Adapter ausgeführt <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, wie im folgenden Code gezeigt.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostSideAdapterCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#hostsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostSideAdapterCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#hostsideadaptercode)]  
  
<a name="AddIn"></a>   
## <a name="implementing-the-add-in"></a>Implementieren des Add-Ins  
 Mit dem Add-In-seitiger Adapter und Add-In-Ansicht erstellt, das Add-in (`WPFAddIn1.AddIn`) implementieren muss die `IWPFAddInView.GetAddInUI` Methode, um zurückzugeben eine <xref:System.Windows.FrameworkElement> Objekt (eine <xref:System.Windows.Controls.UserControl> in diesem Beispiel). Die Implementierung der <xref:System.Windows.Controls.UserControl>, `AddInUI`, wird im folgenden Code gezeigt.  
  
 [!code-xaml[SimpleAddInReturnsAUISample#AddInUIMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml#addinuimarkup)]  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInUICodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#addinuicodebehind)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInUICodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#addinuicodebehind)]  
  
 Die Implementierung der `IWPFAddInView.GetAddInUI` durch das Add-in muss einfach eine neue Instanz der zurückzugebenden `AddInUI`, wie im folgenden Code gezeigt.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddIn.cs#addincode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddIn.vb#addincode)]  
  
<a name="App"></a>   
## <a name="implementing-the-host-application"></a>Implementieren der Hostanwendung  
 Mit dem hostseitige Adapter und die Hostansicht erstellt haben, können die hostanwendung die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Add-In-Modell, um die Pipeline zu öffnen, erhalten eine Hostansicht des Add-Ins, und rufen die `IWPFAddInHostView.GetAddInUI` Methode. Diese Schritte werden im folgenden Code gezeigt.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#GetUICode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Host/MainWindow.xaml.cs#getuicode)]
 [!code-vb[SimpleAddInReturnsAUISample#GetUICode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Host/MainWindow.xaml.vb#getuicode)]  
  
## <a name="see-also"></a>Siehe auch  
 [Add-Ins und Erweiterbarkeit](../../../../docs/framework/add-ins/index.md)  
 [Übersicht über WPF-Add-Ins](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md)
