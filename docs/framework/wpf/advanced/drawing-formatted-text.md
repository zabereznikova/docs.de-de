---
title: Zeichnen von formatiertem Text
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF]
- typography [WPF], drawing formatted text
- formatted text [WPF]
- drawing [WPF], formatted text
ms.assetid: b1d851c1-331c-4814-9964-6fe769db6f1f
ms.openlocfilehash: 1e82795afbdd5b1b0a05f95600ebdb92fc134b7d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186565"
---
# <a name="drawing-formatted-text"></a>Zeichnen von formatiertem Text
Dieses Thema bietet einen Überblick <xref:System.Windows.Media.FormattedText> über die Features des Objekts. Dieses Objekt bietet die Steuerung auf niedriger Ebene für das Zeichnen von Text in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Anwendungen.  

## <a name="technology-overview"></a>Technologieübersicht  
 Mit <xref:System.Windows.Media.FormattedText> dem Objekt können Sie mehrzeiligen Text zeichnen, in dem jedes Zeichen im Text individuell formatiert werden kann. Das folgende Beispiel zeigt Text mit mehreren angewendeten Formaten:  
  
 ![Mit dem FormattedText-Objekt angezeigter Text](./media/typography-in-wpf/text-formatted-linear-gradient.jpg)  
  
> [!NOTE]
> Für Entwickler, die von der Win32-API migrieren, werden in der Tabelle im Abschnitt [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] [Win32-Migration](#win32_migration) die Win32 DrawText-Flags und das ungefähre Äquivalent in aufgeführt.  
  
### <a name="reasons-for-using-formatted-text"></a>Gründe für das Verwenden von formatiertem Text  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] enthält zahlreiche Steuerelemente zum Zeichnen von Text auf dem Bildschirm. Jedes Steuerelement ist einem bestimmten Szenario zugeordnet und besitzt eine eigene Liste von Funktionen und Einschränkungen. Im Allgemeinen <xref:System.Windows.Controls.TextBlock> sollte das Element verwendet werden, wenn eine eingeschränkte [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]Textunterstützung erforderlich ist, z. B. ein kurzer Satz in einem . <xref:System.Windows.Controls.Label>kann verwendet werden, wenn minimale Textunterstützung erforderlich ist. Weitere Informationen finden Sie unter [Dokumente in WPF](documents-in-wpf.md).  
  
 Das <xref:System.Windows.Media.FormattedText> Objekt bietet größere [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Textformatierungsfeatures als Textsteuerelemente und kann in Fällen nützlich sein, in denen Sie Text als dekoratives Element verwenden möchten. Weitere Informationen finden Sie im folgenden Abschnitt [Konvertieren von formatiertem Text in eine Geometrie](#converting_formatted_text).  
  
 Darüber hinaus <xref:System.Windows.Media.FormattedText> ist das Objekt nützlich <xref:System.Windows.Media.DrawingVisual>zum Erstellen textorientierter -abgeleiteter Objekte. <xref:System.Windows.Media.DrawingVisual>ist eine einfache Zeichnungsklasse, die zum Rendern von Formen, Bildern oder Text verwendet wird. Weitere Informationen finden Sie unter [Beispiel für Treffertests mit DrawingVisuals](https://github.com/Microsoft/WPF-Samples/tree/master/Visual%20Layer/DrawingVisual).  
  
## <a name="using-the-formattedtext-object"></a>Verwenden des FormattedText-Objekts  
 Um formatierten Text zu <xref:System.Windows.Media.FormattedText.%23ctor%2A> erstellen, rufen <xref:System.Windows.Media.FormattedText> Sie den Konstruktor auf, um ein Objekt zu erstellen. Nachdem Sie die Anfangszeichenfolge für formatierten Text erstellt haben, können Sie eine Reihe von Formatvorlagen anwenden.  
  
 Verwenden <xref:System.Windows.Media.FormattedText.MaxTextWidth%2A> Sie die Eigenschaft, um den Text auf eine bestimmte Breite zu beschränken. Der Text wird automatisch umgebrochen, um die angegebene Breite nicht zu überschreiten. Verwenden <xref:System.Windows.Media.FormattedText.MaxTextHeight%2A> Sie die Eigenschaft, um den Text auf eine bestimmte Höhe zu beschränken. Der Text zeigt Auslassungspunkte „...“ an, wenn die angegebene Höhe überschritten wird.  
  
 ![Text, der mit Wortumbruch und Auslassungspunkte angezeigt wird.](./media/drawing-formatted-text/formatted-text-wordwrap-ellipsis.png)
  
 Sie können mehrere Formatvorlagen auf ein oder mehrere Zeichen anwenden. Sie können z. B. <xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A> sowohl die als auch Methoden <xref:System.Windows.Media.FormattedText.SetFontSize%2A> aufrufen, um die Formatierung der ersten fünf Zeichen im Text zu ändern.  
  
 Im folgenden Codebeispiel <xref:System.Windows.Media.FormattedText> wird ein Objekt erstellt und dann mehrere Formatierungsstile auf den Text angewendet.  
  
 [!code-csharp[FormattedTextSnippets#FormattedTextSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets1)]
 [!code-vb[FormattedTextSnippets#FormattedTextSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets1)]  
  
### <a name="font-size-unit-of-measure"></a>Maßeinheit für den Schriftgrad  
 Wie bei anderen [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Textobjekten <xref:System.Windows.Media.FormattedText> in Anwendungen verwendet das Objekt geräteunabhängige Pixel als Maßeinheit. Die meisten Win32-Anwendungen verwenden jedoch Punkte als Maßeinheit. Wenn Sie Anzeigetext in Punkteeinheiten [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] in Anwendungen verwenden möchten, müssen Sie geräteunabhängige Einheiten (1/96 Zoll pro Einheit) in Punkte konvertieren. Der folgende Code veranschaulicht diese Konvertierung:  
  
 [!code-csharp[FormattedTextSnippets#FormattedTextSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets2)]
 [!code-vb[FormattedTextSnippets#FormattedTextSnippets2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets2)]  
  
<a name="converting_formatted_text"></a>
### <a name="converting-formatted-text-to-a-geometry"></a>Konvertieren von formatiertem Text in eine Geometrie  
 Sie können formatierten <xref:System.Windows.Media.Geometry> Text in Objekte konvertieren, sodass Sie andere Arten von visuell interessantem Text erstellen können. Sie können z. <xref:System.Windows.Media.Geometry> B. ein Objekt basierend auf der Gliederung einer Textzeichenfolge erstellen.  
  
 ![Textkontur mit einem linearen Farbverlaufspinsel](./media/typography-in-wpf/text-outline-linear-gradient.jpg)
  
 Die folgenden Beispiele zeigen verschiedene Möglichkeiten zum Erstellen von visuell interessanten Effekten durch Ändern von Strich, Füllung und Hervorhebung des konvertierten Texts.  
  
 ![Text mit unterschiedlichen Farben für Füllung und Strich](./media/typography-in-wpf/fill-stroke-text-effect.jpg)  
  
 ![Text mit auf Strich angewendeten Bildpinsel](./media/typography-in-wpf/image-brush-application.jpg)
  
 ![Text mit Bildpinsel, der auf Strich und Hervorhebung angewendet wird](./media/typography-in-wpf/image-brush-text-application.jpg)
  
 Wenn Text in <xref:System.Windows.Media.Geometry> ein Objekt konvertiert wird, handelt es sich nicht mehr um eine Sammlung von Zeichen – Sie können die Zeichen in der Textzeichenfolge nicht ändern. Sie können jedoch die Darstellung des konvertierten Texts durch Ändern der Strich- und Füllungseigenschaften ändern. Der Strich bezieht sich auf die Kontur des konvertierten Texts und die Füllung auf den Bereich innerhalb der Kontur. Weitere Informationen finden Sie unter [Erstellen von Text mit Kontur](how-to-create-outlined-text.md).  
  
 Sie können auch formatierten <xref:System.Windows.Media.PathGeometry> Text in ein Objekt konvertieren und das Objekt zum Hervorheben des Textes verwenden. Sie können z. B. <xref:System.Windows.Media.PathGeometry> eine Animation auf das Objekt anwenden, sodass die Animation der Umrisslinie des formatierten Textes folgt.  
  
 Das folgende Beispiel zeigt formatierten Text, <xref:System.Windows.Media.PathGeometry> der in ein Objekt konvertiert wurde. Eine animierte Ellipse folgt dem Strichpfad des gerenderten Texts.  
  
 ![Kugel, die der Pfadgeometrie des Textes folgt](./media/drawing-formatted-text/sphere-following-geometry-path.gif)  
Kugel, die der Pfadgeometrie des Textes folgt  
  
 Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen einer PathGeometry-Animation für Text](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms743610(v=vs.100)).  
  
 Sie können weitere interessante Verwendungen für formatierten Text <xref:System.Windows.Media.PathGeometry> erstellen, nachdem er in ein Objekt konvertiert wurde. So können Sie beispielsweise ein zugeschnittenes Video darin anzeigen.  
  
 ![Video, das in der Pfadgeometrie von Text angezeigt wird](./media/drawing-formatted-text/video-displaying-text-path-geometry.png)
  
<a name="win32_migration"></a>
## <a name="win32-migration"></a>Win32-Migration  
 Die Features <xref:System.Windows.Media.FormattedText> von zum Zeichnen von Text ähneln den Features der Win32 DrawText-Funktion. Für Entwickler, die von der Win32-API migrieren, werden in der [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]folgenden Tabelle die Win32 DrawText-Flags und das ungefähre Äquivalent in aufgeführt.  
  
|DrawText-Flag|WPF-Entsprechung|Notizen|  
|-------------------|--------------------|-----------|  
|DT_BOTTOM|<xref:System.Windows.Media.FormattedText.Height%2A>|Verwenden <xref:System.Windows.Media.FormattedText.Height%2A> Sie die Eigenschaft, um eine entsprechende Win32 DrawText 'y'-Position zu berechnen.|  
|DT_CALCRECT|<xref:System.Windows.Media.FormattedText.Height%2A>, <xref:System.Windows.Media.FormattedText.Width%2A>|Verwenden <xref:System.Windows.Media.FormattedText.Height%2A> Sie <xref:System.Windows.Media.FormattedText.Width%2A> die und Eigenschaften, um das Ausgaberechteck zu berechnen.|  
|DT_CENTER|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Verwenden <xref:System.Windows.Media.FormattedText.TextAlignment%2A> Sie die Eigenschaft <xref:System.Windows.TextAlignment.Center>mit dem Wert , der auf festgelegt ist.|  
|DT_EDITCONTROL|Keine|Nicht erforderlich. Rendern von Abstandsbreite und letzter Zeile sind identisch mit dem Edit-Steuerelement für Framework.|  
|DT_END_ELLIPSIS|<xref:System.Windows.Media.FormattedText.Trimming%2A>|Verwenden <xref:System.Windows.Media.FormattedText.Trimming%2A> Sie die <xref:System.Windows.TextTrimming.CharacterEllipsis>Eigenschaft mit dem Wert .<br /><br /> Verwenden <xref:System.Windows.TextTrimming.WordEllipsis> Sie diese Verwendung, um Win32-DT_END_ELLIPSIS mit DT_WORD_ELIPSIS End-Ellipsen zu erhalten – in diesem Fall tritt die Auslassung von Zeichen nur bei Wörtern auf, die nicht in eine einzelne Zeile passen.|  
|DT_EXPAND_TABS|Keine|Nicht erforderlich. Registerkarten werden automatisch auf Zwischenstopps nach jeweils 4 em erweitert. Dies entspricht etwa der Breite von 8 sprachunabhängigen Zeichen.|  
|DT_EXTERNALLEADING|Keine|Nicht erforderlich. Der externe Abstand ist immer im Zeilenabstand enthalten. Verwenden <xref:System.Windows.Media.FormattedText.LineHeight%2A> Sie die Eigenschaft, um benutzerdefinierte Zeilenabstände zu erstellen.|  
|DT_HIDEPREFIX|Keine|Wird nicht unterstützt. Entfernen Sie die '&' aus <xref:System.Windows.Media.FormattedText> der Zeichenfolge, bevor Sie das Objekt erstellen.|  
|DT_LEFT|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Dies ist die standardmäßige Textausrichtung. Verwenden <xref:System.Windows.Media.FormattedText.TextAlignment%2A> Sie die Eigenschaft <xref:System.Windows.TextAlignment.Left>mit dem Wert , der auf festgelegt ist. (nur für WPF)|  
|DT_MODIFYSTRING|Keine|Wird nicht unterstützt.|  
|DT_NOCLIP|<xref:System.Windows.Media.Visual.VisualClip%2A>|Clipping geschieht nicht automatisch. Wenn Sie Text beschneiden <xref:System.Windows.Media.Visual.VisualClip%2A> möchten, verwenden Sie die Eigenschaft.|  
|DT_NOFULLWIDTHCHARBREAK|Keine|Wird nicht unterstützt.|  
|DT_NOPREFIX|Keine|Nicht erforderlich. Das &-Zeichen innerhalb der Zeichenfolgen wird immer als normales Zeichen behandelt.|  
|DT_PATHELLIPSIS|Keine|Verwenden <xref:System.Windows.Media.FormattedText.Trimming%2A> Sie die <xref:System.Windows.TextTrimming.WordEllipsis>Eigenschaft mit dem Wert .|  
|DT_PREFIX|Keine|Wird nicht unterstützt. Wenn Sie Unterstriche für Text verwenden möchten, z. <xref:System.Windows.Media.FormattedText.SetTextDecorations%2A> B. einen Beschleunigerschlüssel oder link, verwenden Sie die Methode.|  
|DT_PREFIXONLY|Keine|Wird nicht unterstützt.|  
|DT_RIGHT|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Verwenden <xref:System.Windows.Media.FormattedText.TextAlignment%2A> Sie die Eigenschaft <xref:System.Windows.TextAlignment.Right>mit dem Wert , der auf festgelegt ist. (nur für WPF)|  
|DT_RTLREADING|<xref:System.Windows.Media.FormattedText.FlowDirection%2A>|Setzen Sie die <xref:System.Windows.Media.FormattedText.FlowDirection%2A>-Eigenschaft auf <xref:System.Windows.FlowDirection.RightToLeft>.|  
|DT_SINGLELINE|Keine|Nicht erforderlich. <xref:System.Windows.Media.FormattedText>Objekte verhalten sich als einzelnes Liniensteuerelement, es sei denn, die <xref:System.Windows.Media.FormattedText.MaxTextWidth%2A> Eigenschaft ist festgelegt oder der Text enthält einen Wagenrücklauf/Zeilenvorschub (CR/LF).|  
|DT_TABSTOP|Keine|Keine Unterstützung für benutzerdefinierte Tabstopppositionen.|  
|DT_TOP|<xref:System.Windows.Media.FormattedText.Height%2A>|Nicht erforderlich. Obere Ausrichtung ist die Standardeinstellung. Andere vertikale Positionierungswerte können <xref:System.Windows.Media.FormattedText.Height%2A> mithilfe der Eigenschaft definiert werden, um eine geeignete Win32 DrawText 'y'-Position zu berechnen.|  
|DT_VCENTER|<xref:System.Windows.Media.FormattedText.Height%2A>|Verwenden <xref:System.Windows.Media.FormattedText.Height%2A> Sie die Eigenschaft, um eine entsprechende Win32 DrawText 'y'-Position zu berechnen.|  
|DT_WORDBREAK|Keine|Nicht erforderlich. Word Breaking erfolgt <xref:System.Windows.Media.FormattedText> automatisch mit Objekten. Sie kann nicht deaktiviert werden.|  
|DT_WORD_ELLIPSIS|<xref:System.Windows.Media.FormattedText.Trimming%2A>|Verwenden <xref:System.Windows.Media.FormattedText.Trimming%2A> Sie die <xref:System.Windows.TextTrimming.WordEllipsis>Eigenschaft mit dem Wert .|  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Media.FormattedText>
- [Dokumente in WPF](documents-in-wpf.md)
- [Typografie in WPF](typography-in-wpf.md)
- [Erstellen von Text mit Kontur](how-to-create-outlined-text.md)
- [Vorgehensweise: Erstellen einer PathGeometry-Animation für Text](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms743610(v=vs.100))
