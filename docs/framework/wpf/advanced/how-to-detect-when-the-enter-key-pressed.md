---
title: 'Vorgehensweise: Erkennen, wenn die EINGABETASTE gedrückt wurde'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Enter key [WPF], detecting
- keys [WPF], Enter
ms.assetid: a66f39d2-ef4a-43a5-b454-a4ea0fe88655
ms.openlocfilehash: e2337826077c836696937f91541d6d261f1270aa
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004824"
---
# <a name="how-to-detect-when-the-enter-key-pressed"></a>Vorgehensweise: Erkennen, wenn die EINGABETASTE gedrückt wurde
Dieses Beispiel zeigt, wie Sie erkennen können, wenn die <xref:System.Windows.Input.Key.Enter>-Taste auf der Tastatur gedrückt wird.  
  
 Dieses Beispiel besteht aus einer [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]-Datei und einer Code Behind-Datei.  
  
## <a name="example"></a>Beispiel  
 Wenn der Benutzer den <xref:System.Windows.Input.Key.Enter>-Schlüssel im <xref:System.Windows.Controls.TextBox> drückt, wird die Eingabe im Textfeld in einem anderen Bereich des [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] angezeigt.  
  
 Der folgende XAML-Code erstellt die Benutzeroberfläche, die aus einer <xref:System.Windows.Controls.StackPanel>, einer <xref:System.Windows.Controls.TextBlock> und einem <xref:System.Windows.Controls.TextBox> besteht.  
  
 [!code-xaml[keydown#KeyDownUI](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 Der folgende Code Behind erstellt den <xref:System.Windows.UIElement.KeyDown>-Ereignishandler.  Wenn die gedrückte Taste der <xref:System.Windows.Input.Key.Enter>-Taste ist, wird eine Meldung in der <xref:System.Windows.Controls.TextBlock> angezeigt.  
  
 [!code-csharp[keydown#KeyDownSample](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über die Eingabe](input-overview.md)
- [Übersicht über Routingereignisse](routed-events-overview.md)
