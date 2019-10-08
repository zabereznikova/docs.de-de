---
title: 'Vorgehensweise: Ändern der Farbe eines Elements mithilfe von Fokusereignissen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- focus events [WPF], changing element color for
- colors of elements [WPF], changing
- elements [WPF], changing color of
ms.assetid: 7e246802-3625-47a7-ae9d-c8a2a40fd040
ms.openlocfilehash: 5c59dc5f2f8f26fac69933f9ef641a3a51306619
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004835"
---
# <a name="how-to-change-the-color-of-an-element-using-focus-events"></a>Vorgehensweise: Ändern der Farbe eines Elements mithilfe von Fokusereignissen
Dieses Beispiel zeigt, wie Sie die Farbe eines Elements ändern können, wenn es mit den Ereignissen <xref:System.Windows.UIElement.GotFocus> und <xref:System.Windows.UIElement.LostFocus> den Fokus erhält.  
  
 Dieses Beispiel besteht aus einer [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]-Datei und einer Code Behind-Datei.  
  
## <a name="example"></a>Beispiel  
 Der folgende XAML-Code erstellt die Benutzeroberfläche, die aus zwei <xref:System.Windows.Controls.Button>-Objekten besteht, und fügt Ereignishandler für die <xref:System.Windows.UIElement.GotFocus>-und <xref:System.Windows.UIElement.LostFocus>-Ereignisse an die <xref:System.Windows.Controls.Button>-Objekte an.  
  
 [!code-xaml[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml#gotlostfocussamplexaml)]  
  
 Der folgende Code Behind erstellt die Ereignishandler <xref:System.Windows.UIElement.GotFocus> und <xref:System.Windows.UIElement.LostFocus>.  Wenn die <xref:System.Windows.Controls.Button> den Tastaturfokus erhält, wird die <xref:System.Windows.Controls.Control.Background%2A> der <xref:System.Windows.Controls.Button> in rot geändert.  Wenn die <xref:System.Windows.Controls.Button> den Tastaturfokus verliert, wird die <xref:System.Windows.Controls.Control.Background%2A> der <xref:System.Windows.Controls.Button> wieder in weiß geändert.  
  
 [!code-csharp[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml.cs#gotlostfocussampleeventhandlers)]
 [!code-vb[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/VisualBasic/Window1.xaml.vb#gotlostfocussampleeventhandlers)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über die Eingabe](input-overview.md)
