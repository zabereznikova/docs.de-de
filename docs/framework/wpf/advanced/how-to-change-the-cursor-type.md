---
title: 'Gewusst wie: Ändern des Cursortyps'
description: Ändern Sie den Mauszeiger Cursor für ein Element und für eine Anwendung in Windows Presentation Foundation. Dieses Beispiel besteht aus XAML und einer Code Behind-Datei.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mouse pointer [WPF], cursor type
- cursor (mouse pointer)
ms.assetid: 08c945a7-8ab0-4320-acf3-0b4955a344c2
ms.openlocfilehash: ce0bc290948a0e52e85f76ceb62a330b49fd87ea
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165960"
---
# <a name="how-to-change-the-cursor-type"></a>Gewusst wie: Ändern des Cursortyps
In diesem Beispiel wird gezeigt, wie der <xref:System.Windows.Input.Cursor> des Mauszeigers für ein bestimmtes Element und für die Anwendung geändert wird.  
  
 Dieses Beispiel besteht aus einer [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Datei und einer Code Behind-Datei.  
  
## <a name="example"></a>Beispiel  
 Die Benutzeroberfläche wird erstellt. Diese besteht aus einem <xref:System.Windows.Controls.ComboBox> zum Auswählen der gewünschten <xref:System.Windows.Input.Cursor> , einem Paar von- <xref:System.Windows.Controls.RadioButton> Objekten, um zu bestimmen, ob die Cursor Änderung nur auf ein einzelnes Element angewendet wird oder auf die gesamte Anwendung angewendet wird, und ein-Element, auf das das Element angewendet wird, auf das <xref:System.Windows.Controls.Border> der neue Cursor angewendet wird.  
  
 [!code-xaml[cursors#ChangeCursorsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml#changecursorsxaml)]  
  
 Der folgende Code Behind erstellt einen- <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> Ereignishandler, der aufgerufen wird, wenn der Cursortyp in geändert wird <xref:System.Windows.Controls.ComboBox> .  Eine Switch-Anweisung filtert nach dem Cursor Namen und legt die- <xref:System.Windows.FrameworkElement.Cursor%2A> Eigenschaft auf dem-Objekt fest <xref:System.Windows.Controls.Border> , das den Namen *DisplayArea*hat.  
  
 Wenn die Cursor Änderung auf "gesamte Anwendung" festgelegt ist, <xref:System.Windows.Input.Mouse.OverrideCursor%2A> wird die-Eigenschaft auf die-Eigenschaft des-Steuer Elements festgelegt <xref:System.Windows.FrameworkElement.Cursor%2A> <xref:System.Windows.Controls.Border> .  Dadurch wird erzwungen, dass der Cursor für die gesamte Anwendung geändert wird.  
  
 [!code-csharp[cursors#ChangeCursorsSample](~/samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml.cs#changecursorssample)]
 [!code-vb[cursors#ChangeCursorsSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/cursors/VisualBasic/Window1.xaml.vb#changecursorssample)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über die Eingabe](input-overview.md)
