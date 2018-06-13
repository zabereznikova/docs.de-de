---
title: 'Gewusst wie: Auslösen einer Animation bei Änderung eines Eigenschaftswerts'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], starting when property values change
- triggering animation [WPF]
- Storyboards [WPF], starting when property values change
ms.assetid: 12399c21-0300-4f4f-9e3a-d92d9907e5f5
ms.openlocfilehash: f127f00445a587ee097faa6bed28e124690de10e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561316"
---
# <a name="how-to-trigger-an-animation-when-a-property-value-changes"></a>Gewusst wie: Auslösen einer Animation bei Änderung eines Eigenschaftswerts
Dieses Beispiel zeigt, wie eine <xref:System.Windows.Trigger> zum Starten einer <xref:System.Windows.Media.Animation.Storyboard> Wenn sich ein Eigenschaftswert ändert. Sie können eine <xref:System.Windows.Trigger> innerhalb einer <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, oder <xref:System.Windows.DataTemplate>.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Windows.Trigger> zum Animieren der <xref:System.Windows.UIElement.Opacity%2A> des eine <xref:System.Windows.Controls.Button> beim seine <xref:System.Windows.UIElement.IsMouseOver%2A> Eigenschaft `true`.  
  
 [!code-xaml[AnimatePropertyStoryboards#PropertyTriggerExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/PropertyTriggerExample.xaml#propertytriggerexample)]  
  
 Animationen, die von der Eigenschaft angewendet <xref:System.Windows.Trigger> Objekte verhalten sich in einer komplexeren Weise als <xref:System.Windows.EventTrigger> Animationen oder Animationen Schritte mit <xref:System.Windows.Media.Animation.Storyboard> Methoden.  Diese "Übergabe" mit Animationen definiert, die von anderen <xref:System.Windows.Trigger> Objekte, bilden jedoch mit <xref:System.Windows.EventTrigger> und Animationen Methode ausgelöst.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Trigger>  
 [Übersicht über die Verfahren zur Animation von Eigenschaften](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)  
 [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
