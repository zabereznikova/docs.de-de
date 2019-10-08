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
ms.openlocfilehash: 4ef3028b6c71b94a593d168ad6570c4aec12b86b
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005065"
---
# <a name="how-to-make-an-object-follow-the-mouse-pointer"></a>Vorgehensweise: Konfigurieren eines Objekts zum Folgen des Mauszeigers
In diesem Beispiel wird gezeigt, wie die Dimensionen eines Objekts geändert werden, wenn der Mauszeiger auf dem Bildschirm bewegt wird.  
  
 Das Beispiel enthält eine [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]-Datei, mit der die [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] und eine Code-Behind-Datei erstellt werden, die den-Ereignishandler erstellt.  
  
## <a name="example"></a>Beispiel  
 Mit dem folgenden XAML-Code wird die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] erstellt, die aus einem <xref:System.Windows.Shapes.Ellipse> innerhalb eines <xref:System.Windows.Controls.StackPanel> besteht und den Ereignishandler für das <xref:System.Windows.UIElement.MouseMove>-Ereignis anfügt.  
  
 [!code-xaml[mouseMoveWithPointer#MouseMoveWithPointerXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml#mousemovewithpointerxaml)]  
  
 Der folgende Code Behind erstellt den <xref:System.Windows.UIElement.MouseMove>-Ereignishandler.  Wenn der Mauszeiger bewegt wird, werden die Höhe und die Breite des <xref:System.Windows.Shapes.Ellipse> erhöht und verringert.  
  
 [!code-csharp[mouseMoveWithPointer#MouseMovePointerGetPosition](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml.cs#mousemovepointergetposition)]
 [!code-vb[mouseMoveWithPointer#MouseMovePointerGetPosition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseMoveWithPointer/VisualBasic/Window1.xaml.vb#mousemovepointergetposition)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über die Eingabe](input-overview.md)
