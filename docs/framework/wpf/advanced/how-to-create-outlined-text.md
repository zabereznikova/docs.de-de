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
ms.openlocfilehash: d0ce46b9895589fd4635b567136204368a6431ad
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186859"
---
# <a name="how-to-create-outlined-text"></a>Gewusst wie: Erstellen von Text mit Kontur
In den meisten Fällen verwenden Sie Text in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Form einer Sammlung diskreter Zeichen oder Glyphen, wenn Sie Textzeichenfolgen zu Textzeichenfolgen hinzufügen. Sie können z. B. einen linearen <xref:System.Windows.Controls.Control.Foreground%2A> Verlaufspinsel <xref:System.Windows.Controls.TextBox> erstellen und ihn auf die Eigenschaft eines Objekts anwenden. Wenn Sie das Textfeld anzeigen oder bearbeiten, wird der lineare Farbverlaufspinsel automatisch auf den aktuellen Zeichensatz in der Textzeichenfolge angewendet.  
  
 ![Angezeigter Text mit einem linearen Farbverlaufspinsel](./media/how-to-create-outlined-text/text-linear-gradient.jpg)
  
 Sie können jedoch auch <xref:System.Windows.Media.Geometry> Text in Objekte konvertieren, sodass Sie andere Arten von visuell reichem Text erstellen können. Sie können z. <xref:System.Windows.Media.Geometry> B. ein Objekt basierend auf der Gliederung einer Textzeichenfolge erstellen.  
  
 ![Textkontur mit einem linearen Farbverlaufspinsel](./media/how-to-create-outlined-text/text-outline-linear-gradient.jpg)  
  
 Wenn Text in <xref:System.Windows.Media.Geometry> ein Objekt konvertiert wird, handelt es sich nicht mehr um eine Sammlung von Zeichen – Sie können die Zeichen in der Textzeichenfolge nicht ändern. Sie können jedoch die Darstellung des konvertierten Texts durch Ändern der Strich- und Füllungseigenschaften ändern. Der Strich bezieht sich auf die Kontur des konvertierten Texts und die Füllung auf den Bereich innerhalb der Kontur.  
  
 Die folgenden Beispiele veranschaulichen verschiedene Möglichkeiten zum Erstellen visueller Effekte, indem Sie den Strich und die Füllung von konvertiertem Text ändern.  
  
 ![Text mit unterschiedlichen Farben für Füllung und Strich](./media/how-to-create-outlined-text/fill-stroke-text-effect.jpg)  
  
 ![Text mit auf Strich angewendeten Bildpinsel](./media/how-to-create-outlined-text/image-brush-application.jpg)
  
 Es ist auch möglich, das Begrenzungsrahmenrechteck des konvertierten Textes zu ändern oder hervorzuheben. Das folgende Beispiel veranschaulicht eine Möglichkeit zum Erstellen visueller Effekte, indem Sie den Strich und die Hervorhebung von konvertiertem Text ändern.  
  
 ![Text mit Bildpinsel, der auf Strich und Hervorhebung angewendet wird](./media/how-to-create-outlined-text/image-brush-text-application.jpg)

## <a name="example"></a>Beispiel  
 Der Schlüssel zum Konvertieren <xref:System.Windows.Media.Geometry> von Text in <xref:System.Windows.Media.FormattedText> ein Objekt ist die Verwendung des Objekts. Nachdem Sie dieses Objekt erstellt haben, <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> können Sie die <xref:System.Windows.Media.Geometry> <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> und Methoden verwenden, um den Text in Objekte zu konvertieren. Die erste Methode gibt die Geometrie des formatierten Textes zurück. Die zweite Methode gibt die Geometrie des Begrenzungsrahmens des formatierten Textes zurück. Das folgende Codebeispiel zeigt, <xref:System.Windows.Media.FormattedText> wie ein Objekt erstellt und die Geometrien des formatierten Textes und seines Begrenzungsrahmens abgerufen werden.  
  
 [!code-csharp[OutlineTextControlViewer#CreateText](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#createtext)]
 [!code-vb[OutlineTextControlViewer#CreateText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#createtext)]  
  
 Um die abgerufenen <xref:System.Windows.Media.Geometry> Objekte anzuzeigen, müssen <xref:System.Windows.Media.DrawingContext> Sie auf das Objekt zugreifen, das den konvertierten Text anzeigt. In diesen Codebeispielen wird dies durch Erstellen eines benutzerdefinierten Steuerelementobjekts erfolgen, das von einer Klasse abgeleitet wird, die benutzerdefiniertes Rendern unterstützt.  
  
 Um <xref:System.Windows.Media.Geometry> Objekte im benutzerdefinierten Steuerelement anzuzeigen, <xref:System.Windows.UIElement.OnRender%2A> geben Sie eine Außerkraftsetzung für die Methode an. Die überschriebene Methode <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> sollte die <xref:System.Windows.Media.Geometry> Methode zum Zeichnen der Objekte verwenden.  
  
 [!code-csharp[OutlineTextControlViewer#OnRender](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#onrender)]
 [!code-vb[OutlineTextControlViewer#OnRender](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#onrender)]  
  
  Informationen zur Quelle des benutzerdefinierten Benutzersteuerelementobjekts finden Sie unter [OutlineTextControl.cs für C-](https://github.com/dotnet/samples/blob/master/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs) und [OutlineTextControl.vb für Visual Basic](https://github.com/dotnet/samples/blob/master/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb).
  
## <a name="see-also"></a>Weitere Informationen

- [Zeichnen von formatiertem Text](drawing-formatted-text.md)
