---
title: "Gewusst wie: &#196;ndern der horizontalen Ausrichtung einer Spalte in einem ListView-Element | Microsoft Docs"
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
  - "ListView-Steuerelemente, Horizontale Ausrichtung"
ms.assetid: b9573e44-9dad-4d14-939c-7859ca372758
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# Gewusst wie: &#196;ndern der horizontalen Ausrichtung einer Spalte in einem ListView-Element
Standardmäßig ist der Inhalt jeder Spalte in einem <xref:System.Windows.Controls.ListViewItem> linksbündig ausgerichtet.  Sie können die Ausrichtungen der einzelnen Spalten ändern, indem Sie eine <xref:System.Windows.DataTemplate> bereitstellen und die <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>\-Eigenschaft des Elements in der <xref:System.Windows.DataTemplate> festlegen.  In diesem Thema wird beschrieben, wie ein <xref:System.Windows.Controls.ListView>\-Element seinen Inhalt standardmäßig ausrichtet und wie Sie die Ausrichtung einer Spalte in einem <xref:System.Windows.Controls.ListView>\-Element ändern.  
  
## Beispiel  
 Im folgenden Beispiel sind die Daten in den Spalten `Title` und `ISBN` linksbündig ausgerichtet.  
  
 [!code-xml[ListViewHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xml[ListViewHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 Um die Ausrichtung der Spalte `ISBN` zu ändern, müssen Sie angeben, dass die <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>\-Eigenschaft der einzelnen <xref:System.Windows.Controls.ListViewItem>\-Elemente auf <xref:System.Windows.HorizontalAlignment> festgelegt ist, so dass die Einträge in den einzelnen <xref:System.Windows.Controls.ListViewItem>\-Elementen jeweils die gesamte Breite der Spalte einnehmen können.  Da das <xref:System.Windows.Controls.ListView>\-Element an eine Datenquelle gebunden ist, müssen Sie einen Stil erstellen, der <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> festlegt.  Danach müssen Sie eine <xref:System.Windows.DataTemplate> verwenden, um den Inhalt anzuzeigen, anstatt die <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>\-Eigenschaft zu verwenden.  Um den `ISBN`\-Wert für die einzelnen Vorlagen anzuzeigen, kann die <xref:System.Windows.DataTemplate> einfach einen <xref:System.Windows.Controls.TextBlock> enthalten, dessen <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>\-Eigenschaft auf <xref:System.Windows.HorizontalAlignment> gesetzt ist.  
  
 Das folgende Beispiel definiert den Stil und die <xref:System.Windows.DataTemplate>, die zum rechtsbündigen Ausrichten der Spalte `ISBN` erforderlich sind, und ändert die <xref:System.Windows.Controls.GridViewColumn>, damit sie auf die <xref:System.Windows.DataTemplate> verweist.  
  
 [!code-xml[ListViewHowTos#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#3)]  
[!code-xml[ListViewHowTos#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#4)]  
  
## Siehe auch  
 [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Übersicht über Datenvorlagen](../../../../docs/framework/wpf/data/data-templating-overview.md)   
 [Binden an XML\-Daten mithilfe von XMLDataProvider und XPath\-Abfragen](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)   
 [Übersicht über ListView](../../../../docs/framework/wpf/controls/listview-overview.md)