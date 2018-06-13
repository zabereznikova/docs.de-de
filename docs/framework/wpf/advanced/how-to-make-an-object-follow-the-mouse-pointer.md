---
title: 'Gewusst wie: Konfigurieren eines Objekts zum Folgen des Mauszeigers'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- following the mouse pointer (cursor)
- mouse pointer (cursor), making objects follow
- cursor (mouse pointer), making objects follow
ms.assetid: 50b20415-14bc-405c-baf3-2fb254fffde3
ms.openlocfilehash: 860b42f4dc068bc3063001e25e8b012c50b59213
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543871"
---
# <a name="how-to-make-an-object-follow-the-mouse-pointer"></a>Gewusst wie: Konfigurieren eines Objekts zum Folgen des Mauszeigers
Dieses Beispiel zeigt, wie die Dimensionen eines Objekts ändern, wenn der Mauszeiger auf dem Bildschirm bewegt wird.  
  
 Das Beispiel umfasst ein [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] -Datei, erstellt die [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] und ein Code-Behind-Datei, die der Ereignishandler erstellt.  
  
## <a name="example"></a>Beispiel  
 Die folgenden [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] erstellt die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], besteht aus dem ein <xref:System.Windows.Shapes.Ellipse> innerhalb eines eine <xref:System.Windows.Controls.StackPanel>, und fügt den Ereignishandler für die <xref:System.Windows.UIElement.MouseMove> Ereignis.  
  
 [!code-xaml[mouseMoveWithPointer#MouseMoveWithPointerXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml#mousemovewithpointerxaml)]  
  
 Der folgende Code-behind erstellt die <xref:System.Windows.UIElement.MouseMove> -Ereignishandler.  Wenn der Mauszeiger bewegt wird, der die Höhe und die Breite des der <xref:System.Windows.Shapes.Ellipse> erhöht und gesenkt werden.  
  
 [!code-csharp[mouseMoveWithPointer#MouseMovePointerGetPosition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml.cs#mousemovepointergetposition)]
 [!code-vb[mouseMoveWithPointer#MouseMovePointerGetPosition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/mouseMoveWithPointer/VisualBasic/Window1.xaml.vb#mousemovepointergetposition)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Eingabe](../../../../docs/framework/wpf/advanced/input-overview.md)
