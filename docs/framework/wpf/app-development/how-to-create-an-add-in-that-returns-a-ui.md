---
title: "Gewusst wie: Erstellen eines Add-Ins, das eine Benutzeroberfl&#228;che zur&#252;ckgibt | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Add-In [WPF], Gibt eine Benutzeroberfläche zurück"
  - "Erstellen eines Add-Ins zur Rückgabe einer Benutzeroberfläche [WPF]"
  - "Implementieren von Add-In-Pipelinesegmenten [WPF]"
ms.assetid: 57f274b7-4c66-4b72-92eb-81939a393776
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Gewusst wie: Erstellen eines Add-Ins, das eine Benutzeroberfl&#228;che zur&#252;ckgibt
Dieses Beispiel zeigt, wie Sie ein Add\-In erstellen, das eine [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]\-[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] für eine eigenständige [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Hostanwendung zurückgibt.  
  
 Das Add\-In gibt eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] zurück, bei der es sich um ein [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Benutzersteuerelement handelt.  Der Inhalt des Benutzersteuerelements ist eine einzelne Schaltfläche, bei der ein Meldungsfeld angezeigt wird, wenn Benutzer darauf klicken.  Die eigenständige [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Anwendung hostet das Add\-In und zeigt das \(vom Add\-In zurückgegebene\) Benutzersteuerelement als Inhalt des Hauptfensters der Anwendung an.  
  
 **Vorbereitungsmaßnahmen**  
  
 Dieses Beispiel zeigt die [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Erweiterungen des [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Add\-In\-Modells, die dieses Szenario ermöglichen. Dabei wird Folgendes vorausgesetzt:  
  
-   Kenntnis des [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Add\-In\-Modells, einschließlich Pipeline\-, Add\-In\- und Hostentwicklung.  Wenn Sie mit diesen Begriffen nicht vertraut sind, finden Sie weitere Informationen unter [Add\-Ins und Erweiterbarkeit](../../../../ml/index.xml).  Ein Lernprogramm, das die Implementierung einer Pipeline, eines Add\-Ins und einer Hostanwendung veranschaulicht, finden Sie unter [Exemplarische Vorgehensweise: Erstellen von erweiterbaren Anwendungen](../Topic/Walkthrough:%20Creating%20an%20Extensible%20Application.md).  
  
-   Kenntnis der [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Erweiterungen des [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Add\-In\-Modells. Informationen finden Sie unter: [Übersicht über WPF\-Add\-Ins](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md).  
  
## Beispiel  
 Zum Erstellen eines Add\-Ins, das eine [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] zurückgibt, ist spezieller Code für die einzelnen Pipelinesegmente, das Add\-In und die Hostanwendung erforderlich.  
  
   
  
<a name="Contract"></a>   
## Implementieren des Vertragspipelinesegments  
 Im Vertrag muss eine Methode zum Zurückgeben einer [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] festgelegt sein, und der Rückgabewert muss vom Typ <xref:System.AddIn.Contract.INativeHandleContract> sein.  Dies wird durch die `GetAddInUI`\-Methode des `IWPFAddInContract`\-Vertrags im folgenden Code veranschaulicht.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#ContractCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
 [!code-vb[SimpleAddInReturnsAUISample#ContractCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]  
  
<a name="AddInView"></a>   
## Implementieren des Add\-In\-Ansichtspipelinesegments  
 Da das Add\-In die [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] implementiert, die es als Unterklassen von <xref:System.Windows.FrameworkElement> bereitstellt, muss die Methode der Add\-In\-Ansicht, die mit `IWPFAddInView.GetAddInUI` verknüpft ist, einen Wert vom Typ <xref:System.Windows.FrameworkElement> zurückgeben.  Im folgenden Code wird die als Schnittstelle implementierte Add\-In\-Ansicht des Vertrags gezeigt.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInViewCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInViews/IWPFAddInView.cs#addinviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInViewCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInViews/IWPFAddInView.vb#addinviewcode)]  
  
<a name="AddInSideAdapter"></a>   
## Implementieren des Add\-In\-seitigen Adapterpipelinesegments  
 Durch die Vertragsmethode wird <xref:System.AddIn.Contract.INativeHandleContract> zurückgegeben, das Add\-In gibt jedoch <xref:System.Windows.FrameworkElement> zurück \(wie durch die Add\-In\-Ansicht festgelegt\).  Daher muss <xref:System.Windows.FrameworkElement> vor dem Überschreiten der Isolationsgrenze in <xref:System.AddIn.Contract.INativeHandleContract> umgewandelt werden.  Dieser Vorgang wird vom Add\-In\-seitigen Adapter durch Aufrufen von <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> ausgeführt, wie im folgenden Code gezeigt.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInSideAdapterCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInSideAdapterCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]  
  
<a name="HostView"></a>   
## Implementieren des Host\-Ansichtspipelinesegments  
 Da die Hostanwendung <xref:System.Windows.FrameworkElement> anzeigt, muss die Methode der Hostansicht, die mit `IWPFAddInHostView.GetAddInUI` verknüpft ist, einen Wert vom Typ <xref:System.Windows.FrameworkElement> zurückgeben.  Im folgenden Code wird die als Schnittstelle implementierte Hostansicht des Vertrags gezeigt.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostViewCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostViews/IWPFAddInHostView.cs#hostviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostViewCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostViews/IWPFAddInHostView.vb#hostviewcode)]  
  
<a name="HostSideAdapter"></a>   
## Implementieren des hostseitigen Adapterpipelinesegments  
 Durch die Vertragsmethode wird <xref:System.AddIn.Contract.INativeHandleContract> zurückgegeben, die Hostanwendung erwartet jedoch <xref:System.Windows.FrameworkElement> \(wie durch die Hostansicht festgelegt\).  Daher muss <xref:System.AddIn.Contract.INativeHandleContract> nach dem Überschreiten der Isolationsgrenze in <xref:System.Windows.FrameworkElement> umgewandelt werden.  Dieser Vorgang wird vom hostseitigen Adapter durch Aufrufen von <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> ausgeführt, wie im folgenden Code gezeigt.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostSideAdapterCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#hostsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostSideAdapterCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#hostsideadaptercode)]  
  
<a name="AddIn"></a>   
## Implementieren des Add\-Ins  
 Wenn der Add\-In\-seitige Adapter und die Add\-In\-Ansicht erstellt sind, muss das Add\-In \(`WPFAddIn1.AddIn`\) die `IWPFAddInView.GetAddInUI`\-Methode implementieren, um ein <xref:System.Windows.FrameworkElement>\-Objekt zurückzugeben \(in diesem Beispiel <xref:System.Windows.Controls.UserControl>\).  Der folgende Code zeigt die Implementierung von <xref:System.Windows.Controls.UserControl> \(`AddInUI`\).  
  
 [!code-xml[SimpleAddInReturnsAUISample#AddInUIMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml#addinuimarkup)]  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInUICodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#addinuicodebehind)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInUICodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#addinuicodebehind)]  
  
 Bei der Implementierung von `IWPFAddInView.GetAddInUI` über das Add\-In muss lediglich eine neue Instanz von `AddInUI` zurückgegeben werden. Dies ist im folgenden Code gezeigt.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddIn.cs#addincode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddIn.vb#addincode)]  
  
<a name="App"></a>   
## Implementieren der Hostanwendung  
 Sind der hostseitige Adapter und die Hostansicht erstellt, kann die Hostanwendung das Add\-In\-Modell von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] verwenden, um die Pipeline zu öffnen, eine Hostansicht des Add\-Ins abzurufen und die `IWPFAddInHostView.GetAddInUI`\-Methode aufzurufen.  Diese Schritte werden im folgenden Code gezeigt.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#GetUICode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Host/MainWindow.xaml.cs#getuicode)]
 [!code-vb[SimpleAddInReturnsAUISample#GetUICode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Host/MainWindow.xaml.vb#getuicode)]  
  
## Siehe auch  
 [Add\-Ins und Erweiterbarkeit](../../../../ml/index.xml)   
 [Übersicht über WPF\-Add\-Ins](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md)