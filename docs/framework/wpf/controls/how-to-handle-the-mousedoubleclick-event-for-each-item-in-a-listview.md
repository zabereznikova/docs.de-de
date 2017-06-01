---
title: "Gewusst wie: Behandeln des MouseDoubleClick-Ereignisses f&#252;r die einzelnen ListView-Eintr&#228;ge | Microsoft Docs"
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
  - "ListView-Steuerelemente, MouseDoubleClick-Ereignis"
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Gewusst wie: Behandeln des MouseDoubleClick-Ereignisses f&#252;r die einzelnen ListView-Eintr&#228;ge
Um ein Ereignis für die einzelnen Einträge in einem <xref:System.Windows.Controls.ListView>\-Objekt zu behandeln, müssen Sie jedem <xref:System.Windows.Controls.ListViewItem>\-Objekt einen Ereignishandler hinzufügen.  Wenn ein <xref:System.Windows.Controls.ListView>\-Objekt an eine Datenquelle gebunden ist, erstellen Sie nicht explizit ein <xref:System.Windows.Controls.ListViewItem>\-Element, sondern behandeln das Ereignis für die einzelnen Einträge, indem Sie <xref:System.Windows.EventSetter> einem Stil eines <xref:System.Windows.Controls.ListViewItem>\-Elements hinzufügen.  
  
## Beispiel  
 Im folgenden Beispiel wird ein datengebundenes <xref:System.Windows.Controls.ListView>\-Objekt erstellt. Außerdem wird ein <xref:System.Windows.Style> erstellt, um jedem <xref:System.Windows.Controls.ListViewItem>\-Element einen Ereignishandler hinzuzufügen.  
  
 [!code-xml[ListViewHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xml[ListViewHowTos#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xml[ListViewHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 Im folgenden Beispiel wird das <xref:System.Windows.Controls.Control.MouseDoubleClick>\-Ereignis behandelt.  
  
 [!code-csharp[ListViewHowTos#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
>  Obwohl es die gängige Vorgehensweise ist, ein <xref:System.Windows.Controls.ListView>\-Objekt an eine Datenquelle zu binden, können Sie einen Stil verwenden, um jedem <xref:System.Windows.Controls.ListViewItem> eines nicht datengebundenen <xref:System.Windows.Controls.ListView>\-Objekts einen Ereignishandler hinzuzufügen. Dies gilt unabhängig davon, ob Sie explizit ein <xref:System.Windows.Controls.ListViewItem> erstellen.  Weitere Informationen zu explizit und implizit erstellten <xref:System.Windows.Controls.ListViewItem>\-Steuerelementen finden Sie unter <xref:System.Windows.Controls.ItemsControl>.  
  
## Siehe auch  
 <xref:System.Xml.XmlElement>   
 [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Binden an XML\-Daten mithilfe von XMLDataProvider und XPath\-Abfragen](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)   
 [Übersicht über ListView](../../../../docs/framework/wpf/controls/listview-overview.md)