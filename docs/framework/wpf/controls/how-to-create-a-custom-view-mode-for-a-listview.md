---
title: "Gewusst wie: Erstellen eines benutzerdefinierten Ansichtsmodus f&#252;r eine ListView | Microsoft Docs"
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
  - "ListView-Steuerelemente, Erstellen eines benutzerdefinierten Ansichtsmodus"
ms.assetid: 71077349-eeb9-4344-ab29-b5df96df3314
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Erstellen eines benutzerdefinierten Ansichtsmodus f&#252;r eine ListView
Dieses Beispiel zeigt, wie Sie einen benutzerdefinierten <xref:System.Windows.Controls.ListView.View%2A>\-Modus für ein <xref:System.Windows.Controls.ListView>\-Steuerelement erstellen.  
  
## Beispiel  
 Sie müssen die <xref:System.Windows.Controls.ViewBase>\-Klasse verwenden, wenn Sie eine benutzerdefinierte Ansicht für das <xref:System.Windows.Controls.ListView>\-Steuerelement erstellen.  Das folgende Beispiel zeigt einen Ansichtsmodus mit dem Namen `PlainView`, der von der <xref:System.Windows.Controls.ViewBase>\-Klasse abgeleitet wurde.  
  
 [!code-csharp[ListViewCustomView#PlainView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/PlainView.cs#plainview)]
 [!code-vb[ListViewCustomView#PlainView](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/plainview.vb#plainview)]  
  
 Mit der <xref:System.Windows.Style>\-Klasse können Sie der benutzerdefinierten Ansicht einen Stil hinzufügen.  Im folgenden Beispiel wird ein <xref:System.Windows.Style> für den `PlainView`\-Ansichtsmodus festgelegt.  Im vorigen Beispiel wird dieser Stil als Wert der <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A>\-Eigenschaft festgelegt, die für `PlainView` definiert ist.  
  
 [!code-xml[ListViewCustomView#PlainViewStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Themes/Generic.xaml#plainviewstyle)]  
  
 Zum Festlegen des Datenlayouts in einem benutzerdefinierten Ansichtsmodus müssen Sie ein <xref:System.Windows.DataTemplate>\-Objekt definieren.  Im folgenden Beispiel wird eine <xref:System.Windows.DataTemplate> definiert, die zur Anzeige von Daten im `PlainView`\-Ansichtsmodus verwendet werden kann.  
  
 [!code-xml[ListViewCustomView#PlainViewDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewdatatemplate)]  
  
 Das folgende Beispiel zeigt, wie Sie einen <xref:System.Windows.ResourceKey> für den `PlainView`\-Ansichtsmodus definieren, der die im vorigen Beispiel definierte <xref:System.Windows.DataTemplate> verwendet.  
  
 [!code-xml[ListViewCustomView#PlainViewtileView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewtileview)]  
  
 Ein <xref:System.Windows.Controls.ListView>\-Steuerelement kann eine benutzerdefinierte Ansicht verwenden, wenn Sie die <xref:System.Windows.Controls.ListView.View%2A>\-Eigenschaft auf den Ressourcenschlüssel setzen.  Das folgende Beispiel zeigt, wie Sie `PlainView` als Ansichtsmodus für eine <xref:System.Windows.Controls.ListView> angeben.  
  
 [!code-csharp[ListViewCustomView#ListViewtileViewmode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml.cs#listviewtileviewmode)]
 [!code-vb[ListViewCustomView#ListViewtileViewmode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/window1.xaml.vb#listviewtileviewmode)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für eine ListView mit mehreren Ansichten](http://go.microsoft.com/fwlink/?LinkID=160013).  
  
## Siehe auch  
 <xref:System.Windows.Controls.ListView>   
 <xref:System.Windows.Controls.GridView>   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)   
 [Übersicht über ListView](../../../../docs/framework/wpf/controls/listview-overview.md)   
 [Übersicht über GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)