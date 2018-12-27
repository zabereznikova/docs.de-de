---
title: 'Vorgehensweise: Gewusst wie: Erstellen eines Add-Ins, das eine Benutzeroberfläche ist'
ms.date: 03/30/2017
helpviewer_keywords:
- creating an add-in that is a UI [WPF]
- add-ins [WPF], UI
- creating UI add-ins [WPF]
- UI add-ins [WPF], creating
- implementing UI add-ins [WPF]
- pipeline segments [WPF], creating add-ins
ms.assetid: 86375525-282b-4039-8352-8680051a10ea
ms.openlocfilehash: 848e1b2064d89607a93f5ac20fede495e0c61c43
ms.sourcegitcommit: 49af435bfdd41faf26d38c20c5b0cc07e87bea60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/14/2018
ms.locfileid: "53396720"
---
# <a name="how-to-create-an-add-in-that-is-a-ui"></a>Vorgehensweise: Gewusst wie: Erstellen eines Add-Ins, das eine Benutzeroberfläche ist
Dieses Beispiel zeigt, wie Sie ein Add-in erstellen, die eine Windows Presentation Foundation (WPF) ist der von der eine eigenständige WPF-Anwendung gehostet wird.  
  
 Ist das Add-in eine Benutzeroberfläche, die ein WPF-Benutzersteuerelement ist. Der Inhalt des Benutzersteuerelements ist eine einzelne Schaltfläche, bei der ein Meldungsfeld angezeigt wird, wenn Benutzer darauf klicken. Die eigenständige WPF-Anwendung hostet den Benutzeroberflächen-Add-in als Inhalt des Hauptfensters der Anwendung.  
  
 **Erforderliche Komponenten**  
  
 In diesem Beispiel hebt die WPF-Erweiterungen für die Add-In-Modell von .NET Framework, die dieses Szenario zu aktivieren, und es wird Folgendes vorausgesetzt:  
  
-   Kenntnisse in Bezug auf die Add-In-Modell von .NET Framework, einschließlich der Pipeline, add-Ins und Hostentwicklung. Wenn Sie mit diesen Begriffen nicht vertraut sind, finden Sie unter [Add-Ins und Erweiterbarkeit](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)). Ein Lernprogramm, das die Implementierung einer Pipeline, ein Add-in und einer hostanwendung veranschaulicht, finden Sie unter [Exemplarische Vorgehensweise: Erstellen von erweiterbaren Anwendungen](/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100)).  
  
-   Kenntnisse in Bezug auf die WPF-Erweiterungen für die Add-In-Modell von .NET Framework. Finden Sie unter [Übersicht über das WPF-Add-Ins](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md).  
  
## <a name="example"></a>Beispiel  
 Um ein Add-in zu erstellen, die eine WPF-UI ist spezieller Code für die einzelnen Pipelinesegmente, das Add-in und die hostanwendung erforderlich.  
    
  
<a name="Contract"></a>   
## <a name="implementing-the-contract-pipeline-segment"></a>Implementieren des Vertragspipelinesegments  
 Wenn ein Add-in eine Benutzeroberfläche ist, muss der Vertrag für das Add-in implementieren <xref:System.AddIn.Contract.INativeHandleContract>. Im Beispiel `IWPFAddInContract` implementiert <xref:System.AddIn.Contract.INativeHandleContract>, wie im folgenden Code gezeigt.  
  
 [!code-csharp[SimpleAddInIsAUISample#ContractCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]  
  
<a name="AddInViewPipeline"></a>   
## <a name="implementing-the-add-in-view-pipeline-segment"></a>Implementieren des Add-In-Ansichtspipelinesegments  
 Da das Add-in, als eine Unterklasse von implementiert wird der <xref:System.Windows.FrameworkElement> Typ, der Add-In-Ansicht muss auch als Unterklasse <xref:System.Windows.FrameworkElement>. Der folgende Code zeigt die Add-In-Ansicht des Vertrags, als implementiert die `WPFAddInView` Klasse.  
  
 [!code-csharp[SimpleAddInIsAUISample#AddInViewCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInViews/WPFAddInView.cs#addinviewcode)]  
  
 Hier wird die Add-In-Ansicht von abgeleitet <xref:System.Windows.Controls.UserControl>. Die Benutzeroberflächen-Add-in sollte daher auch leiten Sie von <xref:System.Windows.Controls.UserControl>.  
  
<a name="AddInSideAdapter"></a>   
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a>Implementieren des Add-In-seitigen Adapterpipelinesegments  
 Während der Vertrag ist eine <xref:System.AddIn.Contract.INativeHandleContract>, ist das Add-in eine <xref:System.Windows.FrameworkElement> (wie durch die Add-In-Ansichtspipelinesegment angegeben). Aus diesem Grund die <xref:System.Windows.FrameworkElement> konvertiert werden muss, um eine <xref:System.AddIn.Contract.INativeHandleContract> vor dem Überschreiten der Isolationsgrenze. Dieser Vorgang wird ausgeführt, durch den Add-In-seitigen Adapter durch Aufrufen von <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, wie im folgenden Code gezeigt.  
  
 [!code-csharp[SimpleAddInIsAUISample#AddInSideAdapterCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]  
  
 In der Add-In-Modell gibt, in dem ein Add-in eine Benutzeroberfläche zurück (finden Sie unter [Erstellen einer Add-In, dass eine Benutzeroberfläche zurückgibt](../../../../docs/framework/wpf/app-development/how-to-create-an-add-in-that-returns-a-ui.md)), konvertiert der Add-in Adapter die <xref:System.Windows.FrameworkElement> auf ein <xref:System.AddIn.Contract.INativeHandleContract> durch Aufrufen von <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>. <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> muss auch in diesem Modell aufgerufen werden, obwohl Sie implementieren eine Methode, von dem Sie den Code für den Aufruf schreiben müssen. Hierzu überschreiben <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> und Implementieren des aufrufende Codes <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> Wenn der Code, der aufgerufen wird <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> erwartet eine <xref:System.AddIn.Contract.INativeHandleContract>. In diesem Fall ist der Aufrufer der hostseitige Adapter, der in einem nachfolgenden Unterabschnitt behandelt wird.  
  
> [!NOTE]
>  Sie müssen auch überschreiben <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> in diesem Modell, aktivieren die TAB-Taste zwischen der Benutzeroberfläche der hostanwendung und Add-in-Benutzeroberfläche. Weitere Informationen finden Sie unter "WPF-Add-In-Einschränkungen" in [Übersicht über WPF-Add-Ins](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md).  
  
 Da der Add-In-seitige Adapter eine Schnittstelle, die implementiert von abgeleitet <xref:System.AddIn.Contract.INativeHandleContract>, müssen Sie auch implementieren <xref:System.AddIn.Contract.INativeHandleContract.GetHandle%2A>, obwohl dies ignoriert beim <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> überschrieben wird.  
  
<a name="HostViewPipeline"></a>   
## <a name="implementing-the-host-view-pipeline-segment"></a>Implementieren des Host-Ansichtspipelinesegments  
 In diesem Modell wird die hostanwendung erwartet in der Regel werden die Hostansicht eine <xref:System.Windows.FrameworkElement> Unterklasse. Der hostseitige Adapter muss konvertieren die <xref:System.AddIn.Contract.INativeHandleContract> auf eine <xref:System.Windows.FrameworkElement> nach der <xref:System.AddIn.Contract.INativeHandleContract> überschreitet die Isolationsgrenze hinweg. Da von der hostanwendung zum Abrufen eine Methode aufgerufen wird die <xref:System.Windows.FrameworkElement>, der die Hostansicht muss vom Typ "return" die <xref:System.Windows.FrameworkElement> indem es darin enthalten. Daher muss die hostanwendung die Hostansicht abgeleitet, von einer Unterklasse von <xref:System.Windows.FrameworkElement> enthalten können andere [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)], z. B. <xref:System.Windows.Controls.UserControl>. Der folgende Code zeigt die hostanwendung die Hostansicht des Vertrags, als implementiert die `WPFAddInHostView` Klasse.  
  
  
  
<a name="HostSideAdapter"></a>   
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a>Implementieren des hostseitigen Adapterpipelinesegments  
 Während der Vertrag ist eine <xref:System.AddIn.Contract.INativeHandleContract>, die hostanwendung erwartet eine <xref:System.Windows.Controls.UserControl> (wie durch die Hostansicht festgelegt). Daher die <xref:System.AddIn.Contract.INativeHandleContract> konvertiert werden muss, um eine <xref:System.Windows.FrameworkElement> nach dem Überschreiten der Isolationsgrenze, bevor er als Inhalt der Hostansicht festgelegt (die sich daraus ableitet <xref:System.Windows.Controls.UserControl>).  
  
 Dieser Vorgang wird vom hostseitigen Adapter ausgeführt, wie im folgenden Code gezeigt.  
  
  
  
 Wie Sie sehen, ruft der hostseitige Adapter die <xref:System.AddIn.Contract.INativeHandleContract> durch Aufrufen des Add-In-seitigen Adapters <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> Methode (Dies ist der Punkt, in denen die <xref:System.AddIn.Contract.INativeHandleContract> überschreitet die Isolationsgrenze hinweg).  
  
 Der hostseitige Adapter anschließend konvertiert der <xref:System.AddIn.Contract.INativeHandleContract> auf eine <xref:System.Windows.FrameworkElement> durch Aufrufen von <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>. Zum Schluss die <xref:System.Windows.FrameworkElement> als Inhalt der Hostansicht festgelegt ist.  
  
<a name="AddIn"></a>   
## <a name="implementing-the-add-in"></a>Implementieren des Add-Ins  
 Sind der Add-In-seitige Adapter und die Add-In-Ansicht eingerichtet, kann das Add-In durch Ableiten von der Add-In-Ansicht implementiert werden, wie in folgendem Code gezeigt.  
  
  
  
  
  
 In diesem Beispiel sehen Sie einen interessanten Vorteil dieses Modells: Add-In-Entwickler müssen nur das Add-in (da es auch die Benutzeroberfläche ist), anstatt eine Add-in-Klasse sowohl eine Add-in-Benutzeroberfläche zu implementieren.  
  
<a name="HostApp"></a>   
## <a name="implementing-the-host-application"></a>Implementieren der Hostanwendung  
 Der hostseitige Adapter und die Hostansicht erstellt wurden, können die hostanwendung die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Add-In-Modell, um die Pipeline zu öffnen und eine Hostansicht des Add-Ins abzurufen. Diese Schritte werden im folgenden Code gezeigt.  
  
  
  
 Die hostanwendung verwendet typischen Code von .NET Framework-Add-in-Modell, aktivieren Sie das Add-in, das die hostanwendung die Hostansicht implizit an die hostanwendung zurückgibt. Die hostanwendung zeigt anschließend die Hostansicht (d.h. eine <xref:System.Windows.Controls.UserControl>) aus einer <xref:System.Windows.Controls.Grid>.  
  
 Der Code zum Verarbeiten von Interaktionen mit der Add-in-Benutzeroberfläche, die in das Add-in der Anwendungsdomäne ausgeführt werden. Diese Interaktionen umfassen Folgendes:  
  
-   Behandeln der <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis.  
  
-   Zeigt die <xref:System.Windows.MessageBox>.  
  
 Diese Aktivität ist von der Hostanwendung vollständig isoliert.  
  
## <a name="see-also"></a>Siehe auch  
 [Add-Ins und Erweiterbarkeit](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))  
 [Übersicht über WPF-Add-Ins](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md)
