---
title: "Gewusst wie: &#196;ndern des Cursortyps | Microsoft Docs"
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
  - "Cursor (Mauszeiger)"
  - "Mauszeiger (Cursor), Cursortyp"
ms.assetid: 08c945a7-8ab0-4320-acf3-0b4955a344c2
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: &#196;ndern des Cursortyps
In diesem Beispiel wird veranschaulicht, wie der <xref:System.Windows.Input.Cursor> des Mauszeigers für ein bestimmtes Element und für die Anwendung geändert wird.  
  
 Dieses Beispiel besteht aus einer [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]\-Datei und einer Code\-Behind\-Datei.  
  
## Beispiel  
 Die erstellte Benutzeroberfläche enthält ein <xref:System.Windows.Controls.ComboBox> zur Auswahl des gewünschten <xref:System.Windows.Input.Cursor>, zwei <xref:System.Windows.Controls.RadioButton>\-Objekte zum Festlegen, ob die Cursoränderung auf ein einzelnes Element oder die gesamte Anwendung angewendet werden soll, und einen <xref:System.Windows.Controls.Border>, der das Element, auf das der neue Cursor angewendet wird, kennzeichnet.  
  
 [!code-xml[cursors#ChangeCursorsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml#changecursorsxaml)]  
  
 Der folgende Code\-Behind erstellt einen <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>\-Ereignishandler, der bei einer Änderung des Cursortyps in dem <xref:System.Windows.Controls.ComboBox> aufgerufen wird.  Eine switch\-Anweisung filtert nach dem Cursornamen und legt die <xref:System.Windows.FrameworkElement.Cursor%2A>\-Eigenschaft auf dem <xref:System.Windows.Controls.Border> mit dem Namen *DisplayArea* fest.  
  
 Wenn die Cursoränderung auf die gesamte Anwendung angewendet wird, wird für die <xref:System.Windows.Input.Mouse.OverrideCursor%2A>\-Eigenschaft die <xref:System.Windows.FrameworkElement.Cursor%2A>\-Eigenschaft des <xref:System.Windows.Controls.Border>\-Steuerelements festgelegt.  Hierdurch wird der Cursor für die gesamte Anwendung geändert.  
  
 [!code-csharp[cursors#ChangeCursorsSample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml.cs#changecursorssample)]
 [!code-vb[cursors#ChangeCursorsSample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/cursors/VisualBasic/Window1.xaml.vb#changecursorssample)]  
  
## Siehe auch  
 [Übersicht über die Eingabe](../../../../docs/framework/wpf/advanced/input-overview.md)