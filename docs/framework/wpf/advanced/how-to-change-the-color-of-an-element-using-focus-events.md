---
title: 'Gewusst wie: Ändern der Farbe eines Elements mithilfe von Fokusereignissen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- focus events [WPF], changing element color for
- colors of elements [WPF], changing
- elements [WPF], changing color of
ms.assetid: 7e246802-3625-47a7-ae9d-c8a2a40fd040
ms.openlocfilehash: d8d8a3e8b24021cf8a5f916ce3f291a3b66d9411
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543113"
---
# <a name="how-to-change-the-color-of-an-element-using-focus-events"></a>Gewusst wie: Ändern der Farbe eines Elements mithilfe von Fokusereignissen
In diesem Beispiel wird gezeigt, wie die Farbe eines Elements ändern, wenn er erhält und verliert den Fokus mit der <xref:System.Windows.UIElement.GotFocus> und <xref:System.Windows.UIElement.LostFocus> Ereignisse.  
  
 In diesem Beispiel besteht aus einem [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] und eine Code-Behind-Datei.  
  
## <a name="example"></a>Beispiel  
 Die folgenden [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] erstellt die Benutzeroberfläche, die aus zwei <xref:System.Windows.Controls.Button> -Objekte und fügt der Ereignishandler für die <xref:System.Windows.UIElement.GotFocus> und <xref:System.Windows.UIElement.LostFocus> Ereignisse an die <xref:System.Windows.Controls.Button> Objekte.  
  
 [!code-xaml[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml#gotlostfocussamplexaml)]  
  
 Der folgende Code-behind erstellt die <xref:System.Windows.UIElement.GotFocus> und <xref:System.Windows.UIElement.LostFocus> -Ereignishandler.  Wenn die <xref:System.Windows.Controls.Button> Tastaturfokus erhält, die <xref:System.Windows.Controls.Control.Background%2A> von der <xref:System.Windows.Controls.Button> in Rot geändert wird.  Wenn die <xref:System.Windows.Controls.Button> den Tastaturfokus verliert, der <xref:System.Windows.Controls.Control.Background%2A> von der <xref:System.Windows.Controls.Button> nicht wieder in Weiß geändert wird.  
  
 [!code-csharp[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml.cs#gotlostfocussampleeventhandlers)]
 [!code-vb[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/VisualBasic/Window1.xaml.vb#gotlostfocussampleeventhandlers)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Eingabe](../../../../docs/framework/wpf/advanced/input-overview.md)
