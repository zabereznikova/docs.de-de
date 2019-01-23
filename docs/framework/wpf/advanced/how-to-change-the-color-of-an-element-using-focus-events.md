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
ms.openlocfilehash: ad5ba8490f4b98512d539f5ae9c72b03333aca69
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54547013"
---
# <a name="how-to-change-the-color-of-an-element-using-focus-events"></a>Vorgehensweise: Ändern der Farbe eines Elements mithilfe von Fokusereignissen
In diesem Beispiel wird veranschaulicht, wie Sie die Farbe eines Elements ändern, erhält und den Fokus verliert, indem die <xref:System.Windows.UIElement.GotFocus> und <xref:System.Windows.UIElement.LostFocus> Ereignisse.  
  
 In diesem Beispiel besteht aus einem [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] und eine CodeBehind-Datei.  
  
## <a name="example"></a>Beispiel  
 Die folgenden [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] erstellt die Benutzeroberfläche besteht aus zwei <xref:System.Windows.Controls.Button> Objekte aus, und fügt Sie Ereignishandler für die <xref:System.Windows.UIElement.GotFocus> und <xref:System.Windows.UIElement.LostFocus> Ereignisse an die <xref:System.Windows.Controls.Button> Objekte.  
  
 [!code-xaml[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml#gotlostfocussamplexaml)]  
  
 Der folgende Code hinter erstellt die <xref:System.Windows.UIElement.GotFocus> und <xref:System.Windows.UIElement.LostFocus> -Ereignishandler.  Wenn die <xref:System.Windows.Controls.Button> Tastaturfokus erhält, die <xref:System.Windows.Controls.Control.Background%2A> von der <xref:System.Windows.Controls.Button> in Rot geändert wird.  Wenn die <xref:System.Windows.Controls.Button> den Tastaturfokus verliert, die <xref:System.Windows.Controls.Control.Background%2A> von der <xref:System.Windows.Controls.Button> wieder auf Weiß geändert wird.  
  
 [!code-csharp[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml.cs#gotlostfocussampleeventhandlers)]
 [!code-vb[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/VisualBasic/Window1.xaml.vb#gotlostfocussampleeventhandlers)]  
  
## <a name="see-also"></a>Siehe auch
- [Übersicht über die Eingabe](../../../../docs/framework/wpf/advanced/input-overview.md)
