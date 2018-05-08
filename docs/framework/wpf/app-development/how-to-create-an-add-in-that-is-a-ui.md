---
title: 'Gewusst wie: Erstellen eines Add-Ins, das eine Benutzeroberfläche ist'
ms.date: 03/30/2017
helpviewer_keywords:
- creating an add-in that is a UI [WPF]
- add-ins [WPF], UI
- creating UI add-ins [WPF]
- UI add-ins [WPF], creating
- implementing UI add-ins [WPF]
- pipeline segments [WPF], creating add-ins
ms.assetid: 86375525-282b-4039-8352-8680051a10ea
ms.openlocfilehash: 4bd03c2f879ecab83306bb68552c044a33f2e6e4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-an-add-in-that-is-a-ui"></a>Gewusst wie: Erstellen eines Add-Ins, das eine Benutzeroberfläche ist
In diesem Beispiel wird gezeigt, wie ein Add-in erstellen, die eine Windows Presentation Foundation (WPF) ist der von gehostet wird eine [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] eigenständige Anwendung.  
  
 Das Add-in ist eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] also ein [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Benutzersteuerelement. Der Inhalt des Benutzersteuerelements ist eine einzelne Schaltfläche, bei der ein Meldungsfeld angezeigt wird, wenn Benutzer darauf klicken. Die [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] eigenständige Anwendung hostet, das Add-in [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] als Inhalt des Hauptfensters der Anwendung.  
  
 **Erforderliche Komponenten**  
  
 In diesem Beispiel hebt die [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] -Erweiterungen für die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Add-In-Modell, mit denen dieses Szenario, und setzt Folgendes voraus:  
  
-   Kenntnisse der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Add-In-Modell, einschließlich der Pipeline, add-Ins und Hostentwicklung. Wenn Sie mit diesen Konzepten nicht vertraut sind, finden Sie unter [Add-Ins und Erweiterbarkeit](../../../../docs/framework/add-ins/index.md). Ein Lernprogramm, das die Implementierung einer Pipeline, ein Add-in und eine hostanwendung veranschaulicht, finden Sie unter [Exemplarische Vorgehensweise: Erstellen einer erweiterbaren Anwendung](../../../../docs/framework/add-ins/walkthrough-create-extensible-app.md).  
  
-   Kenntnisse der [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] -Erweiterungen für die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Add-In-Modell, die sich hier befinden: [Übersicht über WPF-Add-Ins](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md).  
  
## <a name="example"></a>Beispiel  
 Um ein Add-in erstellen, ist ein [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] speziellen Code für jedes Pipelinesegment, das Add-in und die hostanwendung erfordert.  
    
  
<a name="Contract"></a>   
## <a name="implementing-the-contract-pipeline-segment"></a>Implementieren des Vertragspipelinesegments  
 Wenn ein Add-in ist eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], muss der Vertrag für das Add-in implementieren <xref:System.AddIn.Contract.INativeHandleContract>. Im Beispiel `IWPFAddInContract` implementiert <xref:System.AddIn.Contract.INativeHandleContract>, wie im folgenden Code gezeigt.  
  
 [!code-csharp[SimpleAddInIsAUISample#ContractCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]  
  
<a name="AddInViewPipeline"></a>   
## <a name="implementing-the-add-in-view-pipeline-segment"></a>Implementieren des Add-In-Ansichtspipelinesegments  
 Da das Add-in, als eine Unterklasse von implementiert wird der <xref:System.Windows.FrameworkElement> Typ, der Add-in-Sicht muss auch als Unterklasse <xref:System.Windows.FrameworkElement>. Der folgende Code zeigt die Add-In-Ansicht des Vertrags, der als implementiert die `WPFAddInView` Klasse.  
  
 [!code-csharp[SimpleAddInIsAUISample#AddInViewCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInViews/WPFAddInView.cs#addinviewcode)]  
  
 Hier wird die Add-In-Ansicht von abgeleitet <xref:System.Windows.Controls.UserControl>. Daher das Add-in [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] sollte auch abgeleitet <xref:System.Windows.Controls.UserControl>.  
  
<a name="AddInSideAdapter"></a>   
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a>Implementieren des Add-In-seitigen Adapterpipelinesegments  
 Während der Vertrag ist eine <xref:System.AddIn.Contract.INativeHandleContract>, das Add-in ist eine <xref:System.Windows.FrameworkElement> (wie durch das Anzeigen von Add-in-Pipeline-Segment angegeben). Aus diesem Grund die <xref:System.Windows.FrameworkElement> muss eine Konvertierung in eine <xref:System.AddIn.Contract.INativeHandleContract> vor dem Überschreiten der Isolationsgrenze. Dieser Vorgang wird durch Aufrufen der Add-In-seitiger Adapter ausgeführt <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, wie im folgenden Code gezeigt.  
  
 [!code-csharp[SimpleAddInIsAUISample#AddInSideAdapterCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]  
  
 In der Add-In-Modell, in dem ein Add-in gibt, eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] (finden Sie unter [erstellen Sie ein Add-in, dass gibt eine Benutzeroberfläche](../../../../docs/framework/wpf/app-development/how-to-create-an-add-in-that-returns-a-ui.md)), konvertiert der Add-in-Adapter die <xref:System.Windows.FrameworkElement> zu ein <xref:System.AddIn.Contract.INativeHandleContract> durch Aufrufen <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>. <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> muss auch in diesem Modell aufgerufen werden, obwohl Sie eine Methode aus der der Code zum Aufrufen schreiben implementieren müssen. Hierzu überschreiben <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> und den aufrufende Code implementieren <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> Wenn der Code, der den Aufruf <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> erwartet ein <xref:System.AddIn.Contract.INativeHandleContract>. In diesem Fall ist der Aufrufer der hostseitige Adapter, der in einem nachfolgenden Unterabschnitt behandelt wird.  
  
> [!NOTE]
>  Sie müssen auch überschreiben <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> in diesem Modell so aktivieren Sie die TAB-Taste zwischen hostanwendung [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] und add-in [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Weitere Informationen finden Sie unter "WPF-Add-In-Einschränkungen" in [Übersicht über WPF-Add-Ins](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md).  
  
 Da der Add-In-seitiger Adapter eine Schnittstelle implementiert, die abgeleitet <xref:System.AddIn.Contract.INativeHandleContract>, müssen Sie auch implementieren <xref:System.AddIn.Contract.INativeHandleContract.GetHandle%2A>, obwohl dies ignoriert beim <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> überschrieben wird.  
  
<a name="HostViewPipeline"></a>   
## <a name="implementing-the-host-view-pipeline-segment"></a>Implementieren des Host-Ansichtspipelinesegments  
 In diesem Modell die hostanwendung in der Regel die Hostansicht werden erwartet eine <xref:System.Windows.FrameworkElement> Unterklasse. Der hostseitige Adapter muss Umwandeln der <xref:System.AddIn.Contract.INativeHandleContract> auf eine <xref:System.Windows.FrameworkElement> nach der <xref:System.AddIn.Contract.INativeHandleContract> schneidet die Isolationsgrenze überwinden. Wenn eine Methode von der hostanwendung abzurufenden aufgerufen wird, ist nicht der <xref:System.Windows.FrameworkElement>, die Hostansicht muss vom Typ "return" die <xref:System.Windows.FrameworkElement> durch, die sie enthält. Daher leiten die Hostansicht einer Unterklasse von <xref:System.Windows.FrameworkElement> enthalten können andere [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)], wie z. B. <xref:System.Windows.Controls.UserControl>. Der folgende Code zeigt die Hostansicht des Vertrags, der als implementiert die `WPFAddInHostView` Klasse.  
  
  
  
<a name="HostSideAdapter"></a>   
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a>Implementieren des hostseitigen Adapterpipelinesegments  
 Während der Vertrag ist eine <xref:System.AddIn.Contract.INativeHandleContract>, erwartet die hostanwendung eine <xref:System.Windows.Controls.UserControl> (wie in der Hostansicht angegeben). Folglich die <xref:System.AddIn.Contract.INativeHandleContract> muss eine Konvertierung in einen <xref:System.Windows.FrameworkElement> nach dem Überschreiten der Isolationsgrenze, bevor er als Inhalt der Hostansicht festgelegt (die sich daraus ableitet <xref:System.Windows.Controls.UserControl>).  
  
 Dieser Vorgang wird vom hostseitigen Adapter ausgeführt, wie im folgenden Code gezeigt.  
  
  
  
 Wie Sie sehen können, erhält der hostseitige Adapter die <xref:System.AddIn.Contract.INativeHandleContract> durch Aufrufen des Add-In-seitiger Adapters <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> Methode (Dies ist der Punkt, in denen die <xref:System.AddIn.Contract.INativeHandleContract> schneidet die Isolationsgrenze überwinden).  
  
 Der hostseitige Adapter dann konvertiert die <xref:System.AddIn.Contract.INativeHandleContract> auf eine <xref:System.Windows.FrameworkElement> durch Aufrufen von <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>. Schließlich die <xref:System.Windows.FrameworkElement> als Inhalt der Hostansicht festgelegt ist.  
  
<a name="AddIn"></a>   
## <a name="implementing-the-add-in"></a>Implementieren des Add-Ins  
 Sind der Add-In-seitige Adapter und die Add-In-Ansicht eingerichtet, kann das Add-In durch Ableiten von der Add-In-Ansicht implementiert werden, wie in folgendem Code gezeigt.  
  
  
  
  
  
 Aus diesem Beispiel sehen Sie einen interessanten Vorteil dieses Modells: Add-In-Entwickler müssen nur das Add-In implementieren (da es sich handelt der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] sowie), anstatt eine Add-in-Klasse und ein Add-in [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
<a name="HostApp"></a>   
## <a name="implementing-the-host-application"></a>Implementieren der Hostanwendung  
 Mit dem hostseitige Adapter und die Hostansicht erstellt haben, können die hostanwendung die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Add-In-Modell zum Öffnen der Pipelines und eine Hostansicht des Add-Ins zu erwerben. Diese Schritte werden im folgenden Code gezeigt.  
  
  
  
 Verwendet die hostanwendung typische [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Code Add-In-Modell, aktivieren Sie das Add-in, die implizit die Hostansicht zur hostanwendung zurückgibt. Die hostanwendung wird anschließend die Hostansicht angezeigt (also eine <xref:System.Windows.Controls.UserControl>) aus einer <xref:System.Windows.Controls.Grid>.  
  
 Der Code für die Verarbeitung von Interaktionen mit dem Add-in [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] in das Add-in Anwendungsdomäne ausgeführt. Diese Interaktionen umfassen Folgendes:  
  
-   Behandlung von der <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis.  
  
-   Zeigt die <xref:System.Windows.MessageBox>.  
  
 Diese Aktivität ist von der Hostanwendung vollständig isoliert.  
  
## <a name="see-also"></a>Siehe auch  
 [Add-Ins und Erweiterbarkeit](../../../../docs/framework/add-ins/index.md)  
 [Übersicht über WPF-Add-Ins](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md)
