---
title: 'Gewusst wie: Erstellen eines Add-Ins, das eine Benutzeroberfläche ist'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating an add-in that is a UI [WPF]
- add-ins [WPF], UI
- creating UI add-ins [WPF]
- UI add-ins [WPF], creating
- implementing UI add-ins [WPF]
- pipeline segments [WPF], creating add-ins
ms.assetid: 86375525-282b-4039-8352-8680051a10ea
ms.openlocfilehash: 339231031b9e57b9f00a2aeb6fbbde8ad66c1ad9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141028"
---
# <a name="how-to-create-an-add-in-that-is-a-ui"></a>Gewusst wie: Erstellen eines Add-Ins, das eine Benutzeroberfläche ist
In diesem Beispiel wird gezeigt, wie Sie ein Add-In erstellen, bei dem es sich um eine Windows Presentation Foundation (WPF) handelt, die von einer eigenständigen WPF-Anwendung gehostet wird.  
  
 Das Add-In ist eine Benutzeroberfläche, die ein WPF-Benutzersteuerelement ist. Der Inhalt des Benutzersteuerelements ist eine einzelne Schaltfläche, bei der ein Meldungsfeld angezeigt wird, wenn Benutzer darauf klicken. Die eigenständige WPF-Anwendung hostet die Add-In-Benutzeroberfläche als Inhalt des Hauptanwendungsfensters.  
  
 **Voraussetzungen**  
  
 In diesem Beispiel werden die WPF-Erweiterungen des .NET Framework-Add-In-Modells hervorgehoben, die dieses Szenario aktivieren, und es wird Folgendes angenommen:  
  
- Kenntnisse des .NET Framework-Add-In-Modells, einschließlich Pipeline-, Add-In- und Hostentwicklung. Wenn Sie mit diesen Konzepten nicht vertraut sind, finden Sie weitere Informationen unter [Add-Ins und Erweiterbarkeit](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)). Ein Tutorial, das die Implementierung einer Pipeline, eines Add-Ins und einer Hostanwendung veranschaulicht, finden Sie unter [Exemplarische Vorgehensweise: Erstellen einer erweiterbaren Anwendung](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100)).  
  
- Kenntnisse der WPF-Erweiterungen des .NET Framework-Add-In-Modells. Siehe [WPF Add-Ins Übersicht](wpf-add-ins-overview.md).  
  
## <a name="example"></a>Beispiel  
 Zum Erstellen eines Add-Ins, bei dem es sich um eine WPF-Benutzeroberfläche handelt, ist für jedes Pipelinesegment, das Add-In und die Hostanwendung ein spezifischer Code erforderlich.  

<a name="Contract"></a>
## <a name="implementing-the-contract-pipeline-segment"></a>Implementieren des Vertragspipelinesegments

Wenn es sich bei einem Add-In um eine <xref:System.AddIn.Contract.INativeHandleContract>Benutzeroberfläche handelt, muss der Vertrag für das Add-In implementieren. Implementiert im `IWPFAddInContract` Beispiel <xref:System.AddIn.Contract.INativeHandleContract>, wie im folgenden Code gezeigt.  
  
[!code-csharp[SimpleAddInIsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
[!code-vb[SimpleAddInIsAUISample#ContractCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]

<a name="AddInViewPipeline"></a>
## <a name="implementing-the-add-in-view-pipeline-segment"></a>Implementieren des Add-In-Ansichtspipelinesegments

Da das Add-In als Unterklasse <xref:System.Windows.FrameworkElement> des Typs implementiert ist, muss <xref:System.Windows.FrameworkElement>die Add-In-Ansicht auch unterklasse sein. Der folgende Code zeigt die Add-In-Ansicht `WPFAddInView` des Vertrags, der als Klasse implementiert ist.  
  
[!code-csharp[SimpleAddInIsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInViews/WPFAddInView.cs#addinviewcode)]  
[!code-vb[SimpleAddInIsAUISample#AddInViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/AddInViews/WPFAddInView.vb#AddInViewCode)]  
  
Hier wird die Add-In-Ansicht von <xref:System.Windows.Controls.UserControl>abgeleitet. Folglich sollte die Add-In-Benutzeroberfläche <xref:System.Windows.Controls.UserControl>auch von ableiten.  
  
<a name="AddInSideAdapter"></a>
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a>Implementieren des Add-In-seitigen Adapterpipelinesegments

Während der Vertrag <xref:System.AddIn.Contract.INativeHandleContract>ein ist, ist <xref:System.Windows.FrameworkElement> das Add-In ein (wie durch das Pipelinesegment der Add-In-Ansicht angegeben). Daher muss <xref:System.Windows.FrameworkElement> der in <xref:System.AddIn.Contract.INativeHandleContract> ein konvertiert werden, bevor die Isolationsgrenze überschritten wird. Diese Arbeit wird vom Add-in-Side-Adapter ausgeführt, indem er aufruft, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>wie im folgenden Code gezeigt.  
  
[!code-csharp[SimpleAddInIsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]  
[!code-vb[SimpleAddInIsAUISample#AddInSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]

Im Add-In-Modell, in dem ein Add-In eine Benutzeroberfläche zurückgibt (siehe [Erstellen eines Add-Ins, das eine Benutzeroberfläche zurückgibt),](how-to-create-an-add-in-that-returns-a-ui.md)konvertierte der Add-In-Adapter <xref:System.Windows.FrameworkElement> die in eine <xref:System.AddIn.Contract.INativeHandleContract> durch Aufrufen <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>. <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>muss auch in diesem Modell aufgerufen werden, obwohl Sie eine Methode implementieren müssen, von der sie den Code zum Aufrufen des Codes schreiben müssen. Dazu <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> überschreiben und implementieren Sie den <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> Code, der <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> aufruft, <xref:System.AddIn.Contract.INativeHandleContract>wenn der Aufgerufene Code eine erwartet. In diesem Fall ist der Aufrufer der hostseitige Adapter, der in einem nachfolgenden Unterabschnitt behandelt wird.  
  
> [!NOTE]
> Sie müssen auch <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> in diesem Modell überschreiben, um das Tabing zwischen der Benutzeroberfläche der Hostanwendung und der Add-In-Benutzeroberfläche zu aktivieren. Weitere Informationen finden Sie unter "WPF-Add-In-Einschränkungen" in der [WPF-Add-Ins-Übersicht](wpf-add-ins-overview.md).  
  
Da der Add-in-Side-Adapter eine Schnittstelle implementiert, die von <xref:System.AddIn.Contract.INativeHandleContract> <xref:System.AddIn.Contract.INativeHandleContract.GetHandle%2A>ableitet, müssen <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> Sie auch implementieren, obwohl dies ignoriert wird, wenn sie überschrieben wird.  
  
<a name="HostViewPipeline"></a>
## <a name="implementing-the-host-view-pipeline-segment"></a>Implementieren des Host-Ansichtspipelinesegments

In diesem Modell erwartet die Hostanwendung in <xref:System.Windows.FrameworkElement> der Regel, dass die Hostansicht eine Unterklasse ist. Der hostseitige Adapter muss <xref:System.AddIn.Contract.INativeHandleContract> die <xref:System.Windows.FrameworkElement> in <xref:System.AddIn.Contract.INativeHandleContract> a konvertieren, nachdem die Isolationsgrenze überschritten wurde. Da eine Methode nicht von der Hostanwendung aufgerufen <xref:System.Windows.FrameworkElement>wird, um die abrufen, muss die Hostansicht die <xref:System.Windows.FrameworkElement> "zurückgeben", indem sie sie enthält. Folglich muss die Hostansicht von einer <xref:System.Windows.FrameworkElement> Unterklasse stammen, die andere <xref:System.Windows.Controls.UserControl>Unklassungszeichen enthalten kann, z. B. . Der folgende Code zeigt die Hostansicht des `WPFAddInHostView` Vertrags, der als Klasse implementiert ist.  

[!code-csharp[WPFAddInHostView class](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/HostViews/WPFAddInHostView.cs#HostViewCode)]
[!code-vb[WPFAddInHostView class](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/HostViews/WPFAddInHostView.vb#HostViewCode)]

<a name="HostSideAdapter"></a>
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a>Implementieren des hostseitigen Adapterpipelinesegments

Während der Vertrag <xref:System.AddIn.Contract.INativeHandleContract>ein ist, <xref:System.Windows.Controls.UserControl> erwartet die Hostanwendung eine (wie in der Hostansicht angegeben). Folglich muss <xref:System.AddIn.Contract.INativeHandleContract> der nach <xref:System.Windows.FrameworkElement> dem Überschreiten der Isolationsgrenze in ein konvertiert werden, bevor <xref:System.Windows.Controls.UserControl>er als Inhalt der Hostansicht festgelegt wird (die von ableitet).  
  
Dieser Vorgang wird vom hostseitigen Adapter ausgeführt, wie im folgenden Code gezeigt.  

[!code-csharp[Host-side adapter](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#HostSideAdapterCode)]
[!code-vb[Host-side adapter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#HostSideAdapterCode)]

Wie Sie sehen können, erfasst der <xref:System.AddIn.Contract.INativeHandleContract> hostseitige Adapter die, indem er <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> die Methode des Add-in-Side-Adapters aufruft (dies ist der Punkt, an dem die <xref:System.AddIn.Contract.INativeHandleContract> Isolationsgrenze überschritten wird).  
  
Der hostseitige Adapter konvertiert <xref:System.AddIn.Contract.INativeHandleContract> dann <xref:System.Windows.FrameworkElement> den <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>in a, indem er aufruft. Schließlich wird <xref:System.Windows.FrameworkElement> der als Inhalt der Hostansicht festgelegt.  
  
<a name="AddIn"></a>
## <a name="implementing-the-add-in"></a>Implementieren des Add-Ins

Sind der Add-In-seitige Adapter und die Add-In-Ansicht eingerichtet, kann das Add-In durch Ableiten von der Add-In-Ansicht implementiert werden, wie in folgendem Code gezeigt.  

[!code-csharp[Add-in implementation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#AddInCodeBehind)]
[!code-vb[Add-in implementation](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#AddInCodeBehind)]

In diesem Beispiel sehen Sie einen interessanten Vorteil dieses Modells: Add-In-Entwickler müssen nur das Add-In implementieren (da es sich ebenfalls um die Benutzeroberfläche handelt), und nicht sowohl eine Add-In-Klasse als auch eine Add-In-Benutzeroberfläche.  
  
<a name="HostApp"></a>
## <a name="implementing-the-host-application"></a>Implementieren der Hostanwendung

Wenn der hostseitige Adapter und die Hostansicht erstellt wurden, kann die Hostanwendung das .NET Framework-Add-In-Modell verwenden, um die Pipeline zu öffnen und eine Hostansicht des Add-Ins zu erhalten. Diese Schritte werden im folgenden Code gezeigt.  

[!code-csharp[Acquiring a host view of the add-in](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Host/MainWindow.xaml.cs#GetUICode)]
[!code-vb[Acquiring a host view of the add-in](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/Host/MainWindow.xaml.vb#GetUICode)]

Die Hostanwendung verwendet typischen .NET Framework-Add-In-Modellcode, um das Add-In zu aktivieren, wodurch die Hostansicht implizit an die Hostanwendung zurückgegeben wird. Die Hostanwendung zeigt anschließend die Hostansicht (die a <xref:System.Windows.Controls.UserControl>) aus einer <xref:System.Windows.Controls.Grid>anzeigt.  
  
 Der Code zum Verarbeiten von Interaktionen mit der Add-In-Benutzeroberfläche wird in der Anwendungsdomäne des Add-Ins ausgeführt. Diese Interaktionen umfassen Folgendes:  
  
- Behandeln <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.Click> des Ereignisses.  
  
- Zeigt <xref:System.Windows.MessageBox>die an.  
  
 Diese Aktivität ist von der Hostanwendung vollständig isoliert.  
  
## <a name="see-also"></a>Weitere Informationen

- [Add-Ins und Erweiterbarkeit](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))
- [Übersicht über WPF-Add-Ins](wpf-add-ins-overview.md)
