---
title: 'Vorgehensweise: Ändern des Cursortyps'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mouse pointer [WPF], cursor type
- cursor (mouse pointer)
ms.assetid: 08c945a7-8ab0-4320-acf3-0b4955a344c2
ms.openlocfilehash: 5c9e6931f6addb62a51e44b06a159d4e7b1e5f8a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59141205"
---
# <a name="how-to-change-the-cursor-type"></a>Vorgehensweise: Ändern des Cursortyps
Dieses Beispiel zeigt, wie Sie ändern die <xref:System.Windows.Input.Cursor> des Mauszeigers für ein bestimmtes Element, und für die Anwendung.  
  
 In diesem Beispiel besteht aus einem [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] -Datei und eine CodeBehind-Datei.  
  
## <a name="example"></a>Beispiel  
 Die Benutzeroberfläche wird erstellt, die besteht aus einer <xref:System.Windows.Controls.ComboBox> , wählen Sie die gewünschte <xref:System.Windows.Input.Cursor>, ein Paar von <xref:System.Windows.Controls.RadioButton> zu bestimmen, ob die Cursor Änderung für nur ein einzelnes Element gilt oder für die gesamte Anwendung gilt Objekte und eine <xref:System.Windows.Controls.Border> Hierbei handelt es sich um das Element, dem auf der neue Cursor angewendet wird.  
  
 [!code-xaml[cursors#ChangeCursorsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml#changecursorsxaml)]  
  
 Hinter der folgende Code erstellt eine <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> -Ereignishandler, der aufgerufen wird, wenn der Cursortyp, in geändert wurde der <xref:System.Windows.Controls.ComboBox>.  Eine Switch-Anweisung filtert auf den Cursornamen und legt die <xref:System.Windows.FrameworkElement.Cursor%2A> Eigenschaft für die <xref:System.Windows.Controls.Border> mit dem Namen *DisplayArea*.  
  
 Wenn die Änderung der Cursor auf "Gesamte Anwendung" festgelegt ist die <xref:System.Windows.Input.Mouse.OverrideCursor%2A> -Eigenschaftensatz auf die <xref:System.Windows.FrameworkElement.Cursor%2A> Eigenschaft der <xref:System.Windows.Controls.Border> Steuerelement.  Dies zwingt den Cursor für die gesamte Anwendung zu ändern.  
  
 [!code-csharp[cursors#ChangeCursorsSample](~/samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml.cs#changecursorssample)]
 [!code-vb[cursors#ChangeCursorsSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/cursors/VisualBasic/Window1.xaml.vb#changecursorssample)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über die Eingabe](input-overview.md)
