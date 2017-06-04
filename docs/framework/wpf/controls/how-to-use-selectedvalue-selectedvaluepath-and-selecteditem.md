---
title: "Gewusst wie: Verwendung von SelectedValue, SelectedValuePath und SelectedItem | Microsoft Docs"
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
  - "Control-Klasse, SelectedItem-Eigenschaften"
  - "Control-Klasse, SelectedValue-Eigenschaften"
  - "Control-Klasse, SelectedValuePath-Eigenschaften"
  - "Control-Klasse, TreeView-Eigenschaften"
  - "SelectedValue, SelectedItem-Eigenschaften"
  - "SelectedValue, SelectedValuePath-Eigenschaften"
  - "TreeView-Steuerelement, SelectedItem-Eigenschaften"
  - "TreeView-Steuerelement, SelectedValue-Eigenschaften"
  - "TreeView-Steuerelement, SelectedValuePath-Eigenschaften"
ms.assetid: 2fc92ad4-f02c-4f89-bbe9-d4978a7af0db
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Verwendung von SelectedValue, SelectedValuePath und SelectedItem
In diesem Beispiel wird dargestellt, wie die <xref:System.Windows.Controls.TreeView.SelectedValue%2A>\-Eigenschaft und die <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A>\-Eigenschaft verwendet werden, um einen Wert für das <xref:System.Windows.Controls.TreeView.SelectedItem%2A> einer <xref:System.Windows.Controls.TreeView> anzugeben.  
  
## Beispiel  
 Die <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A>\-Eigenschaft bietet eine Möglichkeit, einen <xref:System.Windows.Controls.TreeView.SelectedValue%2A> für das <xref:System.Windows.Controls.TreeView.SelectedItem%2A> in einer <xref:System.Windows.Controls.TreeView> anzugeben.  Das <xref:System.Windows.Controls.TreeView.SelectedItem%2A> stellt ein Objekt in der <xref:System.Windows.Controls.ItemsControl.Items%2A>\-Auflistung dar, und die <xref:System.Windows.Controls.TreeView> zeigt den Wert einer einzelnen Eigenschaft des ausgewählten Elements an.  Die <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A>\-Eigenschaft gibt den Pfad zu der Eigenschaft an, mit der der Wert der <xref:System.Windows.Controls.TreeView.SelectedValue%2A>\-Eigenschaft bestimmt wird.  In den Beispielen dieses Themas wird dieses Konzept veranschaulicht.  
  
 Im folgenden Beispiel wird ein <xref:System.Windows.Data.XmlDataProvider> gezeigt, der Mitarbeiterinformationen enthält.  
  
 [!code-xml[TreeViewSelectedValue#XMLDataProvider](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#xmldataprovider)]  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.HierarchicalDataTemplate> definiert, die `EmployeeName` und `EmployeeWorkDay` für den `Employee` anzeigt.  Beachten Sie, dass die <xref:System.Windows.HierarchicalDataTemplate> die `EmployeeNumber` nicht als Teil der Vorlage angibt.  
  
 [!code-xml[TreeViewSelectedValue#HierarchicalDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#hierarchicaldatatemplate)]  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Controls.TreeView> dargestellt, die die zuvor definierte <xref:System.Windows.HierarchicalDataTemplate> verwendet und die <xref:System.Windows.Controls.TreeView.SelectedValue%2A>\-Eigenschaft für die `EmployeeNumber` festlegt.  Wenn Sie ein `EmployeeName`\-Element in der <xref:System.Windows.Controls.TreeView> auswählen, gibt die <xref:System.Windows.Controls.TreeView.SelectedItem%2A>\-Eigenschaft das `EmployeeInfo`\-Datenelement zurück, das dem ausgewählten `EmployeeName`\-Element entspricht.  Da allerdings der <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> dieser <xref:System.Windows.Controls.TreeView> auf die `EmployeeNumber` festgelegt wird, wird der <xref:System.Windows.Controls.TreeView.SelectedValue%2A> auf die `EmployeeNumber` festgelegt.  
  
 [!code-xml[TreeViewSelectedValue#SelectedValuePath](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#selectedvaluepath)]  
  
## Siehe auch  
 <xref:System.Windows.Controls.TreeView>   
 <xref:System.Windows.Controls.TreeViewItem>   
 [Übersicht über TreeView](../../../../docs/framework/wpf/controls/treeview-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/controls/treeview-how-to-topics.md)