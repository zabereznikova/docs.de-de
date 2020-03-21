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
# <a name="how-to-create-an-add-in-that-returns-a-ui"></a>Gewusst wie: Erstellen eines Add-Ins, das eine Benutzeroberfläche zurückgibt
In diesem Beispiel wird gezeigt, wie Sie ein Add-In erstellen, das eine Windows Presentation Foundation (WPF) an eine eigenständige Host-WPF-Anwendung zurückgibt.  
  
 Das Add-In gibt eine Benutzeroberfläche zurück, die ein WPF-Benutzersteuerelement ist. Der Inhalt des Benutzersteuerelements ist eine einzelne Schaltfläche, bei der ein Meldungsfeld angezeigt wird, wenn Benutzer darauf klicken. Die eigenständige WPF-Anwendung hostet das Add-In und zeigt das Benutzersteuerelement (vom Add-In zurückgegeben) als Inhalt des Hauptanwendungsfensters an.  
  
 **Voraussetzungen**  
  
 In diesem Beispiel werden die WPF-Erweiterungen des .NET Framework-Add-In-Modells hervorgehoben, die dieses Szenario aktivieren, und es wird Folgendes angenommen:  
  
- Kenntnisse des .NET Framework-Add-In-Modells, einschließlich Pipeline-, Add-In- und Hostentwicklung. Wenn Sie mit diesen Konzepten nicht vertraut sind, finden Sie weitere Informationen unter [Add-Ins und Erweiterbarkeit](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)). Ein Tutorial, das die Implementierung einer Pipeline, eines Add-Ins und einer Hostanwendung veranschaulicht, finden Sie unter [Exemplarische Vorgehensweise: Erstellen einer erweiterbaren Anwendung](/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100)).  
  
- Kenntnisse der WPF-Erweiterungen des .NET Framework-Add-In-Modells, die Hier zu finden sind: [WPF Add-Ins Overview](wpf-add-ins-overview.md).  
  
## <a name="example"></a>Beispiel  
 Zum Erstellen eines Add-Ins, das eine WPF-Benutzeroberfläche zurückgibt, ist für jedes Pipelinesegment, das Add-In und die Hostanwendung ein spezifischer Code erforderlich.  

<a name="Contract"></a>
## <a name="implementing-the-contract-pipeline-segment"></a>Implementieren des Vertragspipelinesegments  
 Eine Methode muss durch den Vertrag für die Rückgabe einer Benutzeroberfläche definiert werden, und ihr Rückgabewert muss vom Typ <xref:System.AddIn.Contract.INativeHandleContract>sein. Dies wird `GetAddInUI` durch die `IWPFAddInContract` Methode des Vertrags im folgenden Code demonstriert.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
 [!code-vb[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]  
  
<a name="AddInView"></a>
## <a name="implementing-the-add-in-view-pipeline-segment"></a>Implementieren des Add-In-Ansichtspipelinesegments  
 Da das Add-In die von ihm als <xref:System.Windows.FrameworkElement>Unterklassen von bereitstellten U-IIs `IWPFAddInView.GetAddInUI` implementiert, muss die <xref:System.Windows.FrameworkElement>Methode in der Add-In-Ansicht, die korreliert, einen Wert des Typs zurückgeben. Im folgenden Code wird die als Schnittstelle implementierte Add-In-Ansicht des Vertrags gezeigt.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInViews/IWPFAddInView.cs#addinviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInViews/IWPFAddInView.vb#addinviewcode)]  
  
<a name="AddInSideAdapter"></a>
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a>Implementieren des Add-In-seitigen Adapterpipelinesegments  
 Die Vertragsmethode <xref:System.AddIn.Contract.INativeHandleContract>gibt eine zurück, aber <xref:System.Windows.FrameworkElement> das Add-In gibt eine zurück (wie in der Add-In-Ansicht angegeben). Folglich muss <xref:System.Windows.FrameworkElement> die in <xref:System.AddIn.Contract.INativeHandleContract> eine umgewandelt werden, bevor die Isolationsgrenze überschritten wird. Diese Arbeit wird vom Add-in-Side-Adapter ausgeführt, indem er aufruft, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>wie im folgenden Code gezeigt.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]  
  
<a name="HostView"></a>
## <a name="implementing-the-host-view-pipeline-segment"></a>Implementieren des Host-Ansichtspipelinesegments  
 Da die Hostanwendung <xref:System.Windows.FrameworkElement>eine anzeigt, `IWPFAddInHostView.GetAddInUI` muss die Methode in der Hostansicht, mit der korreliert, einen Wert vom Typ <xref:System.Windows.FrameworkElement>zurückgeben. Im folgenden Code wird die als Schnittstelle implementierte Hostansicht des Vertrags gezeigt.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostViews/IWPFAddInHostView.cs#hostviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostViews/IWPFAddInHostView.vb#hostviewcode)]  
  
<a name="HostSideAdapter"></a>
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a>Implementieren des hostseitigen Adapterpipelinesegments  
 Die Vertragsmethode <xref:System.AddIn.Contract.INativeHandleContract>gibt eine zurück, <xref:System.Windows.FrameworkElement> aber die Hostanwendung erwartet eine (wie in der Hostansicht angegeben). Folglich muss <xref:System.AddIn.Contract.INativeHandleContract> die nach <xref:System.Windows.FrameworkElement> dem Überschreiten der Isolationsgrenze in eine umgewandelt werden. Diese Arbeit wird vom hostseitigen Adapter <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>ausgeführt, indem er aufruft, wie im folgenden Code gezeigt.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#hostsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#hostsideadaptercode)]  
  
<a name="AddIn"></a>
## <a name="implementing-the-add-in"></a>Implementieren des Add-Ins  
 Wenn der Add-in-Side-Adapter und die Add-In-Ansicht erstellt wurden, muss das Add-In (`WPFAddIn1.AddIn`) die `IWPFAddInView.GetAddInUI` Methode implementieren, um ein <xref:System.Windows.FrameworkElement> Objekt zurückzugeben (in <xref:System.Windows.Controls.UserControl> diesem Beispiel). Die Implementierung <xref:System.Windows.Controls.UserControl>von `AddInUI`, wird durch den folgenden Code angezeigt.  
  
 [!code-xaml[SimpleAddInReturnsAUISample#AddInUIMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml#addinuimarkup)]  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#addinuicodebehind)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#addinuicodebehind)]  
  
 Die Implementierung `IWPFAddInView.GetAddInUI` des durch das Add-In muss einfach `AddInUI`eine neue Instanz von zurückgeben, wie der folgende Code zeigt.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddIn.cs#addincode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddIn.vb#addincode)]  
  
<a name="App"></a>
## <a name="implementing-the-host-application"></a>Implementieren der Hostanwendung  
 Wenn der hostseitige Adapter und die Hostansicht erstellt wurden, kann die Hostanwendung das .NET Framework-Add-In-Modell verwenden, um die Pipeline zu öffnen, eine Hostansicht des Add-Ins zu erhalten und die `IWPFAddInHostView.GetAddInUI` Methode aufzurufen. Diese Schritte werden im folgenden Code gezeigt.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Host/MainWindow.xaml.cs#getuicode)]
 [!code-vb[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Host/MainWindow.xaml.vb#getuicode)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Add-Ins und Erweiterbarkeit](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))
- [Übersicht über WPF-Add-Ins](wpf-add-ins-overview.md)
