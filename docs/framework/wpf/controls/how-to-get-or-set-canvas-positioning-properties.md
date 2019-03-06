---
title: 'Vorgehensweise: Abrufen oder Festlegen von Canvas-Positionierungseigenschaften'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Canvas control [WPF], setting positioning properties
ms.assetid: 1636b950-2b5a-4507-8a10-c5034cc58b1c
ms.openlocfilehash: 9b280bf86f12b406582cb2f534edb85618515d76
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356324"
---
# <a name="how-to-get-or-set-canvas-positioning-properties"></a>Vorgehensweise: Abrufen oder Festlegen von Canvas-Positionierungseigenschaften
In diesem Beispiel wird gezeigt, wie die Positionierung Methoden der Verwendung der <xref:System.Windows.Controls.Canvas> Element, um untergeordneten Inhalt zu positionieren. Dieses Beispiel verwendet den Inhalt in einem <xref:System.Windows.Controls.ListBoxItem> zur Darstellung Positionierung Werte und konvertiert die Werte in Instanzen von <xref:System.Double>, dies ist ein erforderliches Argument für die Positionierung. Die Werte dann wieder in Zeichenfolgen konvertiert und als Text in eine <xref:System.Windows.Controls.TextBlock> -Element mithilfe der <xref:System.Windows.Controls.Canvas.GetLeft%2A> Methode.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine <xref:System.Windows.Controls.ListBox> Element, das elf ausgewählt verfügt <xref:System.Windows.Controls.ListBoxItem> Elemente. Die <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> Ereignistrigger das `ChangeLeft` benutzerdefinierte Methode, die des nachfolgenden Codeblocks definiert.  
  
 Jede <xref:System.Windows.Controls.ListBoxItem> stellt eine <xref:System.Double> -Wert, der eines der Argumente ist, die die <xref:System.Windows.Controls.Canvas.SetLeft%2A> -Methode der <xref:System.Windows.Controls.Canvas> akzeptiert. Um verwenden eine <xref:System.Windows.Controls.ListBoxItem> zur Darstellung einer Instanz von <xref:System.Double>, Sie müssen zuerst konvertieren die <xref:System.Windows.Controls.ListBoxItem> in den richtigen Datentyp.  
  
 [!code-xaml[CanvasPositioningProperties#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml#1)]  
  
 Wenn ein Benutzer ändert die <xref:System.Windows.Controls.ListBox> Auswahl, ruft er die `ChangeLeft` benutzerdefinierte Methode. Diese Methode übergibt der <xref:System.Windows.Controls.ListBoxItem> auf eine <xref:System.Windows.LengthConverter> -Objekt, das konvertiert die <xref:System.Windows.Controls.ContentControl.Content%2A> von eine <xref:System.Windows.Controls.ListBoxItem> mit einer Instanz von <xref:System.Double> (Beachten Sie, die diesen Wert bereits in konvertiert wurde eine <xref:System.String> mithilfe der <xref:System.Windows.Controls.Control.ToString%2A> (Methode). Dieser Wert wird dann zurück zum Übergeben der <xref:System.Windows.Controls.Canvas.SetLeft%2A> und <xref:System.Windows.Controls.Canvas.GetLeft%2A> Methoden der <xref:System.Windows.Controls.Canvas> um die Position des Ändern der `text1` Objekt.  
  
 [!code-csharp[CanvasPositioningProperties#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml.cs#2)]
 [!code-vb[CanvasPositioningProperties#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasPositioningProperties/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.ListBoxItem>
- <xref:System.Windows.LengthConverter>
- [Übersicht über Panel-Elemente](panels-overview.md)
