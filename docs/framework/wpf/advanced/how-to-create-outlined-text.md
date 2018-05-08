---
title: 'Gewusst wie: Erstellen von Text mit Kontur'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], linear gradient brush
- outlined text [WPF]
- gradient brush [WPF]
- linear gradient brush [WPF]
- typography [WPF], outline effects
ms.assetid: 4aa3cf6e-1953-4f26-8230-7c1409e5f28d
ms.openlocfilehash: c79f5c1c6812b1175119133664e39995af29bd4f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-outlined-text"></a>Gewusst wie: Erstellen von Text mit Kontur
In den meisten Fällen, wenn Sie Textzeichenfolgen in Verzierung Hinzufügen Ihrer [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] -Anwendung können Sie Text im Hinblick auf eine Auflistung von diskreten Zeichen oder Symbole verwenden. Sie könnten z. B. einen linearen Farbverlaufspinsel erstellen und anwenden, die <xref:System.Windows.Controls.Control.Foreground%2A> Eigenschaft von einem <xref:System.Windows.Controls.TextBox> Objekt. Beim Anzeigen oder bearbeiten im Textfeld wird der lineare Farbverlaufspinsel automatisch auf den aktuellen Satz von Zeichen in der Textzeichenfolge angewendet.  
  
 ![Angezeigter Text mit einem linearen Farbverlaufspinsel](../../../../docs/framework/wpf/advanced/media/outlinedtext01.jpg "OutlinedText01")  
Beispiel für einen linearen Farbverlaufspinsel angewendet, um ein Textfeld  
  
 Allerdings können Sie auch Text in konvertieren <xref:System.Windows.Media.Geometry> Objekte, sodass Sie andere Arten von visuell rich-Text zu erstellen. Sie können z. B. Erstellen einer <xref:System.Windows.Media.Geometry> Objekt auf Grundlage der Gliederung einer Textzeichenfolge.  
  
 ![Textkontur mit einem linearen Farbverlaufspinsel](../../../../docs/framework/wpf/advanced/media/outlinedtext02.jpg "OutlinedText02")  
Beispiel für einen linearen Farbverlaufspinsel der Geometrie Gliederung des Texts angewendet  
  
 Wenn Text konvertiert wird, wird ein <xref:System.Windows.Media.Geometry> -Objekt, es ist nicht mehr eine Auflistung von Zeichen – die Zeichen in der Textzeichenfolge kann nicht geändert werden. Sie können jedoch die Darstellung des konvertierten Texts durch Ändern der Strich- und Füllungseigenschaften ändern. Der Strich bezieht sich auf die Kontur des konvertierten Texts und die Füllung auf den Bereich innerhalb der Kontur.  
  
 Die folgenden Beispiele veranschaulichen verschiedene Methoden zum Erstellen von visuellen Effekte durch Ändern des Strichs und Füllung der konvertierte Text.  
  
 ![Text mit unterschiedlichen Farben für Füllung und Strich](../../../../docs/framework/wpf/advanced/media/outlinedtext03.jpg "OutlinedText03")  
Beispiel für das Festlegen von unterschiedlichen Farben für Strich und Füllung  
  
 ![Text mit auf Strich angewendeten Bildpinsel](../../../../docs/framework/wpf/advanced/media/outlinedtext04.jpg "OutlinedText04")  
Beispiel für die Anwendung eines Bildpinsels auf den Strich  
  
 Es ist auch möglich, das umgebende Feld Rechteck oder in der Markierung, der den konvertierten Text zu ändern. Das folgende Beispiel veranschaulicht eine Möglichkeit zum Erstellen von visuellen Effekte durch Ändern des Strichs und die Markierung der konvertierte Text.  
  
 ![Text mit auf Strich angewendeten Bildpinsel](../../../../docs/framework/wpf/advanced/media/outlinedtext05.jpg "OutlinedText05")  
Beispiel für die Anwendung eines Bildpinsels auf den Strich und die Hervorhebung  
  
## <a name="example"></a>Beispiel  
 Der Schlüssel für die Konvertierung von Text, der eine <xref:System.Windows.Media.Geometry> Objekt ist die Verwendung der <xref:System.Windows.Media.FormattedText> Objekt. Nachdem Sie dieses Objekt erstellt haben, können Sie die <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> und <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> Methoden zum Konvertieren des Texts, der <xref:System.Windows.Media.Geometry> Objekte. Die erste Methode gibt die Geometrie des formatierten Text zurück. die zweite Methode gibt die Geometrie des formatierten Text im Feld umschließenden zurück. Das folgende Codebeispiel veranschaulicht das Erstellen einer <xref:System.Windows.Media.FormattedText> Objekt und zum Abrufen von Geometrien den formatierten Text und seine umgebenden Felds.  
  
 [!code-csharp[OutlineTextControlViewer#CreateText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#createtext)]
 [!code-vb[OutlineTextControlViewer#CreateText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#createtext)]  
  
 Um die abgerufenen anzuzeigen die <xref:System.Windows.Media.Geometry> -Objekte, müssen Sie den Zugriff auf die <xref:System.Windows.Media.DrawingContext> des Objekts, das den konvertierten Text angezeigt wird. In diesen Codebeispielen wird dies durch Erstellen eines benutzerdefinierten Steuerelements-Objekts, das von einer Klasse abgeleitet ist, die eine benutzerdefinierte Rendering unterstützt.  
  
 Anzuzeigende <xref:System.Windows.Media.Geometry> Objekte in das benutzerdefinierte Steuerelement geben Sie eine Außerkraftsetzung für die <xref:System.Windows.UIElement.OnRender%2A> Methode. Verwenden Sie die überschriebene Methode sollte die <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> Methode zum Zeichnen der <xref:System.Windows.Media.Geometry> Objekte.  
  
 [!code-csharp[OutlineTextControlViewer#OnRender](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#onrender)]
 [!code-vb[OutlineTextControlViewer#OnRender](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#onrender)]  
  
## <a name="see-also"></a>Siehe auch  
 [Zeichnen von formatiertem Text](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)
