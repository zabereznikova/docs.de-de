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
ms.openlocfilehash: 2330cdd3be35dc4e4b555db6401dd55d9946ed1f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54745050"
---
# <a name="how-to-change-the-cursor-type"></a>Vorgehensweise: Ändern des Cursortyps
Dieses Beispiel zeigt, wie Sie ändern die <xref:System.Windows.Input.Cursor> des Mauszeigers für ein bestimmtes Element, und für die Anwendung.  
  
 In diesem Beispiel besteht aus einem [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] -Datei und eine CodeBehind-Datei.  
  
## <a name="example"></a>Beispiel  
 Die Benutzeroberfläche wird erstellt, die besteht aus einer <xref:System.Windows.Controls.ComboBox> , wählen Sie die gewünschte <xref:System.Windows.Input.Cursor>, ein Paar von <xref:System.Windows.Controls.RadioButton> zu bestimmen, ob die Cursor Änderung für nur ein einzelnes Element gilt oder für die gesamte Anwendung gilt Objekte und eine <xref:System.Windows.Controls.Border> Hierbei handelt es sich um das Element, dem auf der neue Cursor angewendet wird.  
  
 [!code-xaml[cursors#ChangeCursorsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml#changecursorsxaml)]  
  
 Hinter der folgende Code erstellt eine <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> -Ereignishandler, der aufgerufen wird, wenn der Cursortyp, in geändert wurde der <xref:System.Windows.Controls.ComboBox>.  Eine Switch-Anweisung filtert auf den Cursornamen und legt die <xref:System.Windows.FrameworkElement.Cursor%2A> Eigenschaft für die <xref:System.Windows.Controls.Border> mit dem Namen *DisplayArea*.  
  
 Wenn die Änderung der Cursor auf "Gesamte Anwendung" festgelegt ist die <xref:System.Windows.Input.Mouse.OverrideCursor%2A> -Eigenschaftensatz auf die <xref:System.Windows.FrameworkElement.Cursor%2A> Eigenschaft der <xref:System.Windows.Controls.Border> Steuerelement.  Dies zwingt den Cursor für die gesamte Anwendung zu ändern.  
  
 [!code-csharp[cursors#ChangeCursorsSample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml.cs#changecursorssample)]
 [!code-vb[cursors#ChangeCursorsSample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/cursors/VisualBasic/Window1.xaml.vb#changecursorssample)]  
  
## <a name="see-also"></a>Siehe auch
- [Übersicht über die Eingabe](../../../../docs/framework/wpf/advanced/input-overview.md)
