---
title: "Gewusst wie: Formatieren eines ListView-Steuerelements mit einem GridView mithilfe von Vorlagen | Microsoft Docs"
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
  - "ListView-Steuerelemente, Formatierung"
ms.assetid: 94bf964b-96c8-4bdf-a0c3-f5271b7cb565
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Formatieren eines ListView-Steuerelements mit einem GridView mithilfe von Vorlagen
Im folgenden Beispiel wird erläutert, wie das <xref:System.Windows.DataTemplate>\-Objekt und das <xref:System.Windows.Style>\-Objekt zum Angeben der Darstellung eines <xref:System.Windows.Controls.ListView>\-Steuerelements mit dem <xref:System.Windows.Controls.GridView>\-Ansichtsmodus verwendet werden.  
  
## Beispiel  
 Im folgenden Beispiel werden <xref:System.Windows.Style>\-Objekte und <xref:System.Windows.DataTemplate>\-Objekte veranschaulicht, mit denen die Darstellung eines Spaltenheaders für eine <xref:System.Windows.Controls.GridViewColumn> angepasst werden kann.  
  
 [!code-xml[ListViewTemplate#GridViewHeaderStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheaderstyle)]  
  
 [!code-xml[ListViewTemplate#GridViewHeaderTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheadertemplate)]  
  
 Im folgenden Beispiel wird dargestellt, wie das <xref:System.Windows.Style>\-Objekt und das <xref:System.Windows.DataTemplate>\-Objekt verwendet werden, um die <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A>\-Eigenschaft und die <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A>\-Eigenschaft einer <xref:System.Windows.Controls.GridViewColumn> festzulegen.  Die <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>\-Eigenschaft definiert den Inhalt der Spaltenzellen.  
  
 [!code-xml[ListViewTemplate#GridViewColumnTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcolumntemplate)]  
  
 <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> und <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> sind nur zwei von mehreren Eigenschaften, die zum Anpassen der Darstellung eines Spaltenheaders für ein <xref:System.Windows.Controls.GridView>\-Steuerelement verwendet werden können.  Weitere Informationen finden Sie unter [Übersicht über GridView\-Spaltenheaderstile und \-Spaltenheadervorlagen](../../../../docs/framework/wpf/controls/gridview-column-header-styles-and-templates-overview.md).  
  
 Im folgenden Beispiel wird das Definieren eines <xref:System.Windows.DataTemplate>\-Objekts erläutert, mit dem die Darstellung der Zellen in einer <xref:System.Windows.Controls.GridViewColumn> angepasst werden kann.  
  
 [!code-xml[ListViewTemplate#GridViewCellTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 Im folgenden Beispiel wird veranschaulicht, wie dieses <xref:System.Windows.DataTemplate>\-Objekt verwendet wird, um den Inhalt einer <xref:System.Windows.Controls.GridViewColumn>\-Zelle zu definieren.  Diese Vorlage wird anstelle der <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>\-Eigenschaft aus dem vorherigen <xref:System.Windows.Controls.GridViewColumn>\-Beispiel verwendet.  
  
 [!code-xml[ListViewTemplate#CellTemplateProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
## Siehe auch  
 <xref:System.Windows.Controls.ListView>   
 <xref:System.Windows.Controls.GridView>   
 [Übersicht über GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)   
 [Übersicht über ListView](../../../../docs/framework/wpf/controls/listview-overview.md)