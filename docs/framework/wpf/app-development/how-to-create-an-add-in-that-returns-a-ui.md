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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947835"
---
# <a name="how-to-create-an-add-in-that-returns-a-ui"></a>Vorgehensweise: Erstellen eines Add-Ins, das eine Benutzeroberfläche zurückgibt
Dieses Beispiel zeigt, wie Sie ein Add-in erstellen, die eine Windows Presentation Foundation (WPF) auf einem Host eigenständige WPF-Anwendung zurückgibt.  
  
 Gibt das Add-in eine Benutzeroberfläche, die ein WPF-Benutzersteuerelement ist. Der Inhalt des Benutzersteuerelements ist eine einzelne Schaltfläche, bei der ein Meldungsfeld angezeigt wird, wenn Benutzer darauf klicken. Die eigenständige WPF-Anwendung hostet das Add-in und das Benutzersteuerelement (zurückgegeben durch das Add-in) zeigt, wie der Inhalt des Hauptfensters der Anwendung.  
  
 **Erforderliche Komponenten**  
  
 In diesem Beispiel hebt die WPF-Erweiterungen für die Add-In-Modell von .NET Framework, die dieses Szenario zu aktivieren, und es wird Folgendes vorausgesetzt:  
  
- Kenntnisse in Bezug auf die Add-In-Modell von .NET Framework, einschließlich der Pipeline, add-Ins und Hostentwicklung. Wenn Sie mit diesen Begriffen nicht vertraut sind, finden Sie unter [Add-Ins und Erweiterbarkeit](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)). Ein Lernprogramm, das die Implementierung einer Pipeline, ein Add-in und einer hostanwendung veranschaulicht, finden Sie unter [Exemplarische Vorgehensweise: Erstellen von erweiterbaren Anwendungen](../../add-ins/walkthrough-create-extensible-app.md).  
  
- Kenntnisse über die WPF-Erweiterungen für das .NET Framework-add-in verwendet, das finden Sie hier: [Übersicht über das WPF-Add-Ins](wpf-add-ins-overview.md).  
  
## <a name="example"></a>Beispiel  
 Um ein Add-in zu erstellen, die eine WPF-UI zurückgibt ist spezieller Code für die einzelnen Pipelinesegmente, das Add-in und die hostanwendung erforderlich.  

<a name="Contract"></a>   
## <a name="implementing-the-contract-pipeline-segment"></a>Implementieren des Vertragspipelinesegments  
 Eine Methode muss durch den Vertrag für die Rückgabe einer Benutzeroberflächenautomatisierungs definiert werden, und der Rückgabewert muss vom Typ <xref:System.AddIn.Contract.INativeHandleContract>. Dies wird veranschaulicht, durch die `GetAddInUI` Methode der `IWPFAddInContract` Datenvertrag in den folgenden Code.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
 [!code-vb[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]  
  
<a name="AddInView"></a>   
## <a name="implementing-the-add-in-view-pipeline-segment"></a>Implementieren des Add-In-Ansichtspipelinesegments  
 Da das Add-in implementiert die [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] bietet als Unterklassen von <xref:System.Windows.FrameworkElement>, die Methode für die Add-In-Ansicht, die mit korreliert `IWPFAddInView.GetAddInUI` muss einen Wert vom Typ zurückgeben <xref:System.Windows.FrameworkElement>. Im folgenden Code wird die als Schnittstelle implementierte Add-In-Ansicht des Vertrags gezeigt.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInViews/IWPFAddInView.cs#addinviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInViews/IWPFAddInView.vb#addinviewcode)]  
  
<a name="AddInSideAdapter"></a>   
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a>Implementieren des Add-In-seitigen Adapterpipelinesegments  
 Gibt zurück, durch die Vertragsmethode ein <xref:System.AddIn.Contract.INativeHandleContract>, das Add-in gibt jedoch eine <xref:System.Windows.FrameworkElement> (gemäß der Add-In-Ansicht). Daher die <xref:System.Windows.FrameworkElement> konvertiert werden muss, um eine <xref:System.AddIn.Contract.INativeHandleContract> vor dem Überschreiten der Isolationsgrenze. Dieser Vorgang wird ausgeführt, durch den Add-In-seitigen Adapter durch Aufrufen von <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, wie im folgenden Code gezeigt.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]  
  
<a name="HostView"></a>   
## <a name="implementing-the-host-view-pipeline-segment"></a>Implementieren des Host-Ansichtspipelinesegments  
 Da in die hostanwendung angezeigt wird eine <xref:System.Windows.FrameworkElement>, die Methode der Hostansicht, die mit korreliert `IWPFAddInHostView.GetAddInUI` muss einen Wert vom Typ zurückgeben <xref:System.Windows.FrameworkElement>. Im folgenden Code wird die als Schnittstelle implementierte Hostansicht des Vertrags gezeigt.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostViews/IWPFAddInHostView.cs#hostviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostViews/IWPFAddInHostView.vb#hostviewcode)]  
  
<a name="HostSideAdapter"></a>   
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a>Implementieren des hostseitigen Adapterpipelinesegments  
 Gibt zurück, durch die Vertragsmethode ein <xref:System.AddIn.Contract.INativeHandleContract>, die hostanwendung erwartet jedoch eine <xref:System.Windows.FrameworkElement> (wie durch die Hostansicht festgelegt). Daher die <xref:System.AddIn.Contract.INativeHandleContract> konvertiert werden muss, um eine <xref:System.Windows.FrameworkElement> nach dem Überschreiten der Isolationsgrenze. Dieser Vorgang wird vom hostseitigen Adapter ausgeführt, durch den Aufruf <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, wie im folgenden Code gezeigt.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#hostsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#hostsideadaptercode)]  
  
<a name="AddIn"></a>   
## <a name="implementing-the-add-in"></a>Implementieren des Add-Ins  
 Mit dem Add-In-seitige Adapter und Add-In-Ansicht erstellt, das Add-in (`WPFAddIn1.AddIn`) implementieren müssen die `IWPFAddInView.GetAddInUI` -Methode zur Rückgabe einer <xref:System.Windows.FrameworkElement> Objekt (ein <xref:System.Windows.Controls.UserControl> in diesem Beispiel). Die Implementierung der <xref:System.Windows.Controls.UserControl>, `AddInUI`, mit dem folgenden Code gezeigt wird.  
  
 [!code-xaml[SimpleAddInReturnsAUISample#AddInUIMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml#addinuimarkup)]  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#addinuicodebehind)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#addinuicodebehind)]  
  
 Die Implementierung der `IWPFAddInView.GetAddInUI` durch das Add-in muss einfach eine neue Instanz der zurückzugebenden `AddInUI`, wie im folgenden Code gezeigt.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddIn.cs#addincode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddIn.vb#addincode)]  
  
<a name="App"></a>   
## <a name="implementing-the-host-application"></a>Implementieren der Hostanwendung  
 Der hostseitige Adapter und die Hostansicht erstellt wurden, kann die hostanwendung die Add-In-Modell von .NET Framework verwenden, die Pipeline zu öffnen, erhalten eine Hostansicht des Add-Ins, und rufen die `IWPFAddInHostView.GetAddInUI` Methode. Diese Schritte werden im folgenden Code gezeigt.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Host/MainWindow.xaml.cs#getuicode)]
 [!code-vb[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Host/MainWindow.xaml.vb#getuicode)]  
  
## <a name="see-also"></a>Siehe auch

- [Add-Ins und Erweiterbarkeit](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))
- [Übersicht über WPF-Add-Ins](wpf-add-ins-overview.md)
