---
title: 'Vorgehensweise: Konfigurieren eines Objekts zum Folgen des Mauszeigers'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- following the mouse pointer (cursor)
- mouse pointer (cursor), making objects follow
- cursor (mouse pointer), making objects follow
ms.assetid: 50b20415-14bc-405c-baf3-2fb254fffde3
ms.openlocfilehash: b9b13b4eec3e42744ba2be6031ec841fb5f215e3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051597"
---
# <a name="how-to-make-an-object-follow-the-mouse-pointer"></a>Vorgehensweise: Konfigurieren eines Objekts zum Folgen des Mauszeigers
Dieses Beispiel zeigt, wie Sie die Dimensionen eines Objekts ändern, wenn der Mauszeiger bewegt, auf dem Bildschirm wird.  
  
 Das Beispiel enthält eine [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] -Datei, erstellt die [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] und eine Code-Behind-Datei, die der Ereignishandler erstellt.  
  
## <a name="example"></a>Beispiel  
 Die folgenden [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] erstellt die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], bestehend ein <xref:System.Windows.Shapes.Ellipse> innerhalb von einer <xref:System.Windows.Controls.StackPanel>, und fügt den Ereignishandler für die <xref:System.Windows.UIElement.MouseMove> Ereignis.  
  
 [!code-xaml[mouseMoveWithPointer#MouseMoveWithPointerXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml#mousemovewithpointerxaml)]  
  
 Der folgende Code hinter erstellt die <xref:System.Windows.UIElement.MouseMove> -Ereignishandler.  Wenn der Mauszeiger bewegt wird, die Höhe und Breite des der <xref:System.Windows.Shapes.Ellipse> erhöht und gesenkt werden.  
  
 [!code-csharp[mouseMoveWithPointer#MouseMovePointerGetPosition](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml.cs#mousemovepointergetposition)]
 [!code-vb[mouseMoveWithPointer#MouseMovePointerGetPosition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseMoveWithPointer/VisualBasic/Window1.xaml.vb#mousemovepointergetposition)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über die Eingabe](input-overview.md)
