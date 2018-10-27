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
ms.openlocfilehash: 046ce6519e55e5782db0fe8adbc2a956251e12e4
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50088779"
---
# <a name="how-to-create-outlined-text"></a>Gewusst wie: Erstellen von Text mit Kontur
In den meisten Fällen, wenn Sie Textzeichenfolgen in Verzierung Hinzufügen Ihrer [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] -Anwendung können Sie Text im Hinblick auf eine Auflistung von diskreten Zeichen oder Symbole verwenden. Beispielsweise Sie Pinsels mit linearem Farbverlauf zu erstellen und anwenden, können die <xref:System.Windows.Controls.Control.Foreground%2A> Eigenschaft eine <xref:System.Windows.Controls.TextBox> Objekt. Wenn Sie anzeigen oder bearbeiten das Textfeld ein, wird Pinsels mit linearem Farbverlauf automatisch auf den aktuellen Satz von Zeichen in der Textzeichenfolge angewendet.  
  
 ![Angezeigter Text mit einem linearen Farbverlaufspinsel](../../../../docs/framework/wpf/advanced/media/outlinedtext01.jpg "OutlinedText01")  
Beispiel für einen Pinsel mit linearem Farbverlauf auf das Textfeld angewendet  
  
 Sie können aber auch konvertieren, Text in <xref:System.Windows.Media.Geometry> Objekte, die Ihnen ermöglichen, andere Arten von visuell rich-Text zu erstellen. Sie können z. B. Erstellen einer <xref:System.Windows.Media.Geometry> Objekt auf Grundlage der Gliederung einer Textzeichenfolge.  
  
 ![Textkontur mit einem linearen Farbverlaufspinsel](../../../../docs/framework/wpf/advanced/media/outlinedtext02.jpg "OutlinedText02")  
Beispiel für einen Pinsel mit linearem Farbverlauf auf die Geometrie Gliederung des Texts angewendet  
  
 Wenn in Text konvertiert wird eine <xref:System.Windows.Media.Geometry> Objekt, es ist nicht mehr eine Sammlung von Zeichen, die Zeichen in der Textzeichenfolge kann nicht geändert werden. Sie können jedoch die Darstellung des konvertierten Texts durch Ändern der Strich- und Füllungseigenschaften ändern. Der Strich bezieht sich auf die Kontur des konvertierten Texts und die Füllung auf den Bereich innerhalb der Kontur.  
  
 Die folgenden Beispiele zeigen verschiedene Möglichkeiten zum Erstellen von visuellen Effekten durch Ändern von Strich und Füllung des konvertierten Texts.  
  
 ![Text mit unterschiedlichen Farben für Füllung und Strich](../../../../docs/framework/wpf/advanced/media/outlinedtext03.jpg "OutlinedText03")  
Beispiel für das Festlegen von unterschiedlichen Farben für Strich und Füllung  
  
 ![Text mit auf Strich angewendetem Bildpinsel](../../../../docs/framework/wpf/advanced/media/outlinedtext04.jpg "OutlinedText04")  
Beispiel für die Anwendung eines Bildpinsels auf den Strich  
  
 Es ist auch möglich, die umgebende Rechteckfeld oder die Hervorhebung des konvertierten Texts zu ändern. Das folgende Beispiel veranschaulicht eine Möglichkeit zum Erstellen visueller Effekte durch Ändern des Strichs und Hervorhebung des konvertierten Texts.  
  
 ![Text mit auf Strich angewendetem Bildpinsel](../../../../docs/framework/wpf/advanced/media/outlinedtext05.jpg "OutlinedText05")  
Beispiel für die Anwendung eines Bildpinsels auf den Strich und die Hervorhebung  
  
## <a name="example"></a>Beispiel  
 Der Schlüssel für die Konvertierung von Text in einem <xref:System.Windows.Media.Geometry> Objekt ist die Verwendung der <xref:System.Windows.Media.FormattedText> Objekt. Nachdem Sie dieses Objekt erstellt haben, können Sie mithilfe der <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> und <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> Methoden für die Konvertierung des Texts, der <xref:System.Windows.Media.Geometry> Objekte. Die erste Methode gibt die Geometrie des formatierten Texts zurück. die zweite Methode gibt zurück, dass die Geometrie des formatierten Texts umgebenden Felds des. Im folgenden Codebeispiel wird veranschaulicht, wie zum Erstellen einer <xref:System.Windows.Media.FormattedText> Objekt und die Geometrien, der den formatierten Text und die umgebende Feld abrufen.  
  
 [!code-csharp[OutlineTextControlViewer#CreateText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#createtext)]
 [!code-vb[OutlineTextControlViewer#CreateText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#createtext)]  
  
 Zum Anzeigen der abgerufenen der <xref:System.Windows.Media.Geometry> -Objekte, müssen Sie den Zugriff auf die <xref:System.Windows.Media.DrawingContext> des Objekts, das den konvertierten Text angezeigt wird. In diesen Codebeispielen erfolgt dies durch Erstellen eines benutzerdefinierten Steuerelements-Objekts, das von einer Klasse abgeleitet ist, die eine benutzerdefinierte Darstellung unterstützt.  
  
 Anzuzeigende <xref:System.Windows.Media.Geometry> Objekte in das benutzerdefinierte Steuerelement, geben Sie eine Außerkraftsetzung für die <xref:System.Windows.UIElement.OnRender%2A> Methode. Ihre überschriebene Methode verwenden, sollten die <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> -Methode zum Zeichnen der <xref:System.Windows.Media.Geometry> Objekte.  
  
 [!code-csharp[OutlineTextControlViewer#OnRender](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#onrender)]
 [!code-vb[OutlineTextControlViewer#OnRender](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#onrender)]  
  
  Die Quelle des Objekts Beispiel benutzerdefiniertes Steuerelement, finden Sie unter [OutlineTextControl.cs für C# ](https://github.com/dotnet/samples/blob/master/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs) und [OutlineTextControl.vb für Visual Basic](https://github.com/dotnet/samples/blob/master/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb). 
  
## <a name="see-also"></a>Siehe auch  
 [Zeichnen von formatiertem Text](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)
