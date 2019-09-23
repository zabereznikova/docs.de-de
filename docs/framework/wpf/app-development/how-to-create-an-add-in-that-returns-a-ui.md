---
title: 'Vorgehensweise: Gewusst wie: Erstellen eines Add-Ins, das eine Benutzeroberfläche zurückgibt'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating an add-in that returns a UI [WPF]
- implementing add-in pipeline segments [WPF]
- add-in [WPF], returns a UI
ms.assetid: 57f274b7-4c66-4b72-92eb-81939a393776
ms.openlocfilehash: 1886703e089ed538f68a7221906d815a8ae72076
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2019
ms.locfileid: "71182673"
---
# <a name="how-to-create-an-add-in-that-returns-a-ui"></a>Vorgehensweise: Gewusst wie: Erstellen eines Add-Ins, das eine Benutzeroberfläche zurückgibt
Dieses Beispiel zeigt, wie Sie ein Add-in erstellen, das eine Windows Presentation Foundation (WPF) an eine eigenständige WPF-Host Anwendung zurückgibt.  
  
 Das Add-in gibt eine Benutzeroberfläche zurück, die ein WPF-Benutzer Steuerelement ist. Der Inhalt des Benutzersteuerelements ist eine einzelne Schaltfläche, bei der ein Meldungsfeld angezeigt wird, wenn Benutzer darauf klicken. Die eigenständige WPF-Anwendung hostet das Add-in und zeigt das Benutzer Steuerelement (das vom Add-in zurückgegeben wird) als Inhalt des Hauptfensters der Anwendung an.  
  
 **Erforderliche Komponenten**  
  
 In diesem Beispiel werden die WPF-Erweiterungen für das .NET Framework Add-in-Modell hervorgehoben, das dieses Szenario ermöglicht, und es wird Folgendes vorausgesetzt:  
  
- Kenntnisse des .NET Framework Add-in-Modells, einschließlich Pipeline, Add-in und Host Entwicklung. Wenn Sie mit diesen Konzepten nicht vertraut sind, finden Sie weitere Informationen unter [Add-Ins und Erweiterbarkeit](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)). Ein Tutorial, in dem die Implementierung einer Pipeline, ein Add-in und eine Host Anwendung veranschaulicht wird, finden [Sie unter Exemplarische Vorgehensweise: Erstellen einer erweiterbaren Anwendung](../../add-ins/walkthrough-create-extensible-app.md).  
  
- Informationen zu den WPF-Erweiterungen für das .NET Framework Add-in-Modell finden Sie hier: [Übersicht über WPF-Add-ins](wpf-add-ins-overview.md).  
  
## <a name="example"></a>Beispiel  
 Zum Erstellen eines Add-Ins, das eine WPF-Benutzeroberfläche zurückgibt, ist bestimmter Code für jedes Pipeline Segment, das Add-in und die Host Anwendung erforderlich.  

<a name="Contract"></a>   
## <a name="implementing-the-contract-pipeline-segment"></a>Implementieren des Vertragspipelinesegments  
 Eine Methode muss vom Vertrag zum Zurückgeben einer Benutzeroberfläche definiert werden, und der Rückgabewert muss vom Typ <xref:System.AddIn.Contract.INativeHandleContract>sein. Dies wird durch die `GetAddInUI` -Methode `IWPFAddInContract` des-Vertrags im folgenden Code veranschaulicht.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
 [!code-vb[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]  
  
<a name="AddInView"></a>   
## <a name="implementing-the-add-in-view-pipeline-segment"></a>Implementieren des Add-In-Ansichtspipelinesegments  
 Da das Add-in das implementiert [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] , das als Unterklassen von <xref:System.Windows.FrameworkElement>bereitstellt, muss die-Methode in der Add-in- `IWPFAddInView.GetAddInUI` Ansicht, die mit korreliert <xref:System.Windows.FrameworkElement>, einen Wert vom Typ zurückgeben. Im folgenden Code wird die als Schnittstelle implementierte Add-In-Ansicht des Vertrags gezeigt.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInViews/IWPFAddInView.cs#addinviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInViews/IWPFAddInView.vb#addinviewcode)]  
  
<a name="AddInSideAdapter"></a>   
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a>Implementieren des Add-In-seitigen Adapterpipelinesegments  
 Die Contract-Methode gibt <xref:System.AddIn.Contract.INativeHandleContract>einen zurück, aber das Add-in <xref:System.Windows.FrameworkElement> gibt eine zurück (wie von der Add-in-Ansicht angegeben). Folglich muss vor dem Überschreiten der Isolations Grenze in eine <xref:System.AddIn.Contract.INativeHandleContract> konvertiert werden. <xref:System.Windows.FrameworkElement> Diese Arbeit wird vom Add-in-seitigen Adapter durch Aufrufen <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>von ausgeführt, wie im folgenden Code gezeigt.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]  
  
<a name="HostView"></a>   
## <a name="implementing-the-host-view-pipeline-segment"></a>Implementieren des Host-Ansichtspipelinesegments  
 Da die Host Anwendung eine <xref:System.Windows.FrameworkElement>anzeigt, muss die Methode in der Host Ansicht, die mit `IWPFAddInHostView.GetAddInUI` korreliert, einen Wert vom Typ <xref:System.Windows.FrameworkElement>zurückgeben. Im folgenden Code wird die als Schnittstelle implementierte Hostansicht des Vertrags gezeigt.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostViews/IWPFAddInHostView.cs#hostviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostViews/IWPFAddInHostView.vb#hostviewcode)]  
  
<a name="HostSideAdapter"></a>   
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a>Implementieren des hostseitigen Adapterpipelinesegments  
 Die Contract-Methode gibt <xref:System.AddIn.Contract.INativeHandleContract>einen zurück, aber die Host Anwendung <xref:System.Windows.FrameworkElement> erwartet einen (wie in der Host Ansicht angegeben). Folglich muss nach dem Überschreiten der Isolations Grenze in eine <xref:System.Windows.FrameworkElement> konvertiert werden. <xref:System.AddIn.Contract.INativeHandleContract> Diese Arbeit wird vom Host seitigen Adapter durch Aufrufen <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>von ausgeführt, wie im folgenden Code gezeigt.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#hostsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#hostsideadaptercode)]  
  
<a name="AddIn"></a>   
## <a name="implementing-the-add-in"></a>Implementieren des Add-Ins  
 Wenn der Add-in-seitige Adapter und die Add-in-Ansicht erstellt wurden, muss das`WPFAddIn1.AddIn`Add-in ( `IWPFAddInView.GetAddInUI` ) die-Methode <xref:System.Windows.FrameworkElement> implementieren, um ein-Objekt zurückzugeben (in diesem Beispiel). <xref:System.Windows.Controls.UserControl> Die Implementierung des <xref:System.Windows.Controls.UserControl>, `AddInUI`, wird durch den folgenden Code dargestellt.  
  
 [!code-xaml[SimpleAddInReturnsAUISample#AddInUIMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml#addinuimarkup)]  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#addinuicodebehind)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#addinuicodebehind)]  
  
 Die Implementierung von `IWPFAddInView.GetAddInUI` durch das Add-in muss einfach eine neue Instanz von `AddInUI`zurückgeben, wie im folgenden Code gezeigt.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddIn.cs#addincode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddIn.vb#addincode)]  
  
<a name="App"></a>   
## <a name="implementing-the-host-application"></a>Implementieren der Hostanwendung  
 Wenn der Host seitige Adapter und die Host Ansicht erstellt wurden, kann die Host Anwendung das .NET Framework Add-in-Modell verwenden, um die Pipeline zu öffnen, eine Host Ansicht des Add-Ins abzurufen und `IWPFAddInHostView.GetAddInUI` die Methode aufzurufen. Diese Schritte werden im folgenden Code gezeigt.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Host/MainWindow.xaml.cs#getuicode)]
 [!code-vb[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Host/MainWindow.xaml.vb#getuicode)]  
  
## <a name="see-also"></a>Siehe auch

- [Add-Ins und Erweiterbarkeit](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))
- [Übersicht über WPF-Add-Ins](wpf-add-ins-overview.md)
