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
ms.openlocfilehash: c786137a471e0199a8ac60f8d82b4ce440e33b7e
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740401"
---
# <a name="drawing-formatted-text"></a>Zeichnen von formatiertem Text
Dieses Thema enthält eine Übersicht über die Funktionen des <xref:System.Windows.Media.FormattedText> Objekts. Dieses Objekt bietet die Steuerung auf niedriger Ebene für das Zeichnen von Text in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Anwendungen.  

## <a name="technology-overview"></a>Übersicht über die Technologie  
 Das <xref:System.Windows.Media.FormattedText>-Objekt ermöglicht das Zeichnen von mehrzeiligen Text, in dem jedes Zeichen im Text einzeln formatiert werden kann. Das folgende Beispiel zeigt Text mit mehreren angewendeten Formaten:  
  
 ![Mit dem FormattedText-Objekt angezeigter Text](./media/typography-in-wpf/text-formatted-linear-gradient.jpg)  
  
> [!NOTE]
> Für Entwickler, die von der Win32-API migrieren, werden in der Tabelle im Abschnitt [Win32-Migration](#win32_migration) die Win32-DrawText-Flags und die ungefähre Entsprechung in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]aufgelistet.  
  
### <a name="reasons-for-using-formatted-text"></a>Gründe für das Verwenden von formatiertem Text  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] enthält zahlreiche Steuerelemente zum Zeichnen von Text auf dem Bildschirm. Jedes Steuerelement ist einem bestimmten Szenario zugeordnet und besitzt eine eigene Liste von Funktionen und Einschränkungen. Im Allgemeinen sollte das <xref:System.Windows.Controls.TextBlock>-Element verwendet werden, wenn eingeschränkte Textunterstützung erforderlich ist, z. b. ein kurzer Satz in einer [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. <xref:System.Windows.Controls.Label> kann verwendet werden, wenn nur minimale Textunterstützung erforderlich ist. Weitere Informationen finden Sie unter [Dokumente in WPF](documents-in-wpf.md).  
  
 Das <xref:System.Windows.Media.FormattedText>-Objekt bietet mehr Text Formatierungsfunktionen als [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Text-Steuerelemente und kann in Fällen nützlich sein, in denen Sie Text als dekoratives Element verwenden möchten. Weitere Informationen finden Sie im folgenden Abschnitt [Konvertieren von formatiertem Text in eine Geometrie](#converting_formatted_text).  
  
 Außerdem eignet sich das <xref:System.Windows.Media.FormattedText> Objekt zum Erstellen Text orientierter <xref:System.Windows.Media.DrawingVisual>abgeleiteter Objekte. <xref:System.Windows.Media.DrawingVisual> ist eine vereinfachte Zeichnungs Klasse, die zum Rendering von Formen, Bildern oder Text verwendet wird. Weitere Informationen finden Sie unter [Beispiel für Treffertests mit DrawingVisuals](https://go.microsoft.com/fwlink/?LinkID=159994).  
  
## <a name="using-the-formattedtext-object"></a>Verwenden des FormattedText-Objekts  
 Um formatierten Text zu erstellen, rufen Sie den <xref:System.Windows.Media.FormattedText.%23ctor%2A>-Konstruktor auf, um ein <xref:System.Windows.Media.FormattedText> Objekt zu erstellen. Nachdem Sie die Anfangszeichenfolge für formatierten Text erstellt haben, können Sie eine Reihe von Formatvorlagen anwenden.  
  
 Verwenden Sie die <xref:System.Windows.Media.FormattedText.MaxTextWidth%2A>-Eigenschaft, um den Text auf eine bestimmte Breite einzuschränken. Der Text wird automatisch umgebrochen, um die angegebene Breite nicht zu überschreiten. Verwenden Sie die <xref:System.Windows.Media.FormattedText.MaxTextHeight%2A>-Eigenschaft, um den Text auf eine bestimmte Höhe einzuschränken. Der Text zeigt Auslassungspunkte „...“ an, wenn die angegebene Höhe überschritten wird.  
  
 ![Mit "WordWrap" und "Ellipsis" angezeigter Text](./media/drawing-formatted-text/formatted-text-wordwrap-ellipsis.png)    
  
 Sie können mehrere Formatvorlagen auf ein oder mehrere Zeichen anwenden. Beispielsweise können Sie die Methoden <xref:System.Windows.Media.FormattedText.SetFontSize%2A> und <xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A> aufzurufen, um die Formatierung der ersten fünf Zeichen im Text zu ändern.  
  
 Im folgenden Codebeispiel wird ein <xref:System.Windows.Media.FormattedText> Objekt erstellt und dann mehrere Formatierungs Stile auf den Text angewendet.  
  
 [!code-csharp[FormattedTextSnippets#FormattedTextSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets1)]
 [!code-vb[FormattedTextSnippets#FormattedTextSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets1)]  
  
### <a name="font-size-unit-of-measure"></a>Maßeinheit für den Schriftgrad  
 Wie andere Textobjekte in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Anwendungen verwendet das <xref:System.Windows.Media.FormattedText>-Objekt geräteunabhängige Pixel als Maßeinheit. Die meisten Win32-Anwendungen verwenden jedoch Punkte als Maßeinheit. Wenn Sie in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Anwendungen Anzeige Text in Einheiten Einheiten verwenden möchten, müssen Sie geräteunabhängige Einheiten (1/96 Zoll pro Einheit) in Punkte konvertieren. Der folgende Code veranschaulicht diese Konvertierung:  
  
 [!code-csharp[FormattedTextSnippets#FormattedTextSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets2)]
 [!code-vb[FormattedTextSnippets#FormattedTextSnippets2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets2)]  
  
<a name="converting_formatted_text"></a>   
### <a name="converting-formatted-text-to-a-geometry"></a>Konvertieren von formatiertem Text in eine Geometrie  
 Sie können formatierten Text in <xref:System.Windows.Media.Geometry> Objekte konvertieren, sodass Sie andere Arten von visuell interessantem Text erstellen können. Beispielsweise können Sie ein <xref:System.Windows.Media.Geometry>-Objekt auf Grundlage der Gliederung einer Text Zeichenfolge erstellen.  
  
 ![Textkontur mit einem linearen Farbverlaufspinsel](./media/typography-in-wpf/text-outline-linear-gradient.jpg)    
  
 Die folgenden Beispiele zeigen verschiedene Möglichkeiten zum Erstellen von visuell interessanten Effekten durch Ändern von Strich, Füllung und Hervorhebung des konvertierten Texts.  
  
 ![Text mit unterschiedlichen Farben für Füllung und Strich](./media/typography-in-wpf/fill-stroke-text-effect.jpg)  
  
 ![Text mit auf Strich angewendeten Bildpinsel](./media/typography-in-wpf/image-brush-application.jpg)
  
 ![Text mit angewendetem Bild Pinsel auf Strich und Hervorhebung](./media/typography-in-wpf/image-brush-text-application.jpg)
  
 Wenn Text in ein <xref:System.Windows.Media.Geometry> Objekt konvertiert wird, handelt es sich nicht mehr um eine Auflistung von Zeichen – Sie können die Zeichen in der Text Zeichenfolge nicht mehr ändern. Sie können jedoch die Darstellung des konvertierten Texts durch Ändern der Strich- und Füllungseigenschaften ändern. Der Strich bezieht sich auf die Kontur des konvertierten Texts und die Füllung auf den Bereich innerhalb der Kontur. Weitere Informationen finden Sie unter [Erstellen von Text mit Kontur](how-to-create-outlined-text.md).  
  
 Sie können formatierten Text auch in ein <xref:System.Windows.Media.PathGeometry> Objekt konvertieren und das-Objekt verwenden, um den Text hervorzuheben. Beispielsweise können Sie eine Animation auf das <xref:System.Windows.Media.PathGeometry> Objekt anwenden, sodass die Animation der Kontur des formatierten Texts folgt.  
  
 Das folgende Beispiel zeigt formatierten Text, der in ein <xref:System.Windows.Media.PathGeometry> Objekt konvertiert wurde. Eine animierte Ellipse folgt dem Strichpfad des gerenderten Texts.  
  
 ![Kugel, die der Pfadgeometrie des Textes folgt](./media/drawing-formatted-text/sphere-following-geometry-path.gif)  
Kugel, die der Pfadgeometrie des Textes folgt  
  
 Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen einer PathGeometry-Animation für Text](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms743610(v=vs.100)).  
  
 Sie können weitere interessante Verwendungsmöglichkeiten für formatierten Text erstellen, nachdem er in ein <xref:System.Windows.Media.PathGeometry> Objekt konvertiert wurde. So können Sie beispielsweise ein zugeschnittenes Video darin anzeigen.  
  
 ![Video, das in der Pfadgeometrie von Text angezeigt wird](./media/drawing-formatted-text/video-displaying-text-path-geometry.png)
  
<a name="win32_migration"></a>   
## <a name="win32-migration"></a>Win32-Migration  
 Die Funktionen von <xref:System.Windows.Media.FormattedText> zum Zeichnen von Text ähneln den Funktionen der Win32-DrawText-Funktion. Für Entwickler, die von der Win32-API migrieren, werden in der folgenden Tabelle die Win32-DrawText-Flags und die ungefähre Entsprechung in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]aufgelistet.  
  
|DrawText-Flag|WPF-Entsprechung|Hinweise|  
|-------------------|--------------------|-----------|  
|DT_BOTTOM|<xref:System.Windows.Media.FormattedText.Height%2A>|Verwenden Sie die <xref:System.Windows.Media.FormattedText.Height%2A>-Eigenschaft, um eine entsprechende Win32-DrawText-y-Position zu berechnen.|  
|DT_CALCRECT|<xref:System.Windows.Media.FormattedText.Height%2A>, <xref:System.Windows.Media.FormattedText.Width%2A>|Verwenden Sie die Eigenschaften <xref:System.Windows.Media.FormattedText.Height%2A> und <xref:System.Windows.Media.FormattedText.Width%2A>, um das Ausgabe Rechteck zu berechnen.|  
|DT_CENTER|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Verwenden Sie die <xref:System.Windows.Media.FormattedText.TextAlignment%2A>-Eigenschaft, wobei der Wert auf <xref:System.Windows.TextAlignment.Center>festgelegt ist.|  
|DT_EDITCONTROL|Keine|Nicht erforderlich Rendern von Abstandsbreite und letzter Zeile sind identisch mit dem Edit-Steuerelement für Framework.|  
|DT_END_ELLIPSIS|<xref:System.Windows.Media.FormattedText.Trimming%2A>|Verwenden Sie die <xref:System.Windows.Media.FormattedText.Trimming%2A>-Eigenschaft mit dem Wert <xref:System.Windows.TextTrimming.CharacterEllipsis>.<br /><br /> Verwenden Sie <xref:System.Windows.TextTrimming.WordEllipsis>, um Win32-DT_END_ELLIPSIS mit DT_WORD_ELIPSIS End-Ellipsen zu erhalten – in diesem Fall treten Zeichen Auslassungs Zeichen nur bei Wörtern auf, die nicht in eine einzelne Zeile passen.|  
|DT_EXPAND_TABS|Keine|Nicht erforderlich Registerkarten werden automatisch auf Zwischenstopps nach jeweils 4 em erweitert. Dies entspricht etwa der Breite von 8 sprachunabhängigen Zeichen.|  
|DT_EXTERNALLEADING|Keine|Nicht erforderlich Der externe Abstand ist immer im Zeilenabstand enthalten. Verwenden Sie die <xref:System.Windows.Media.FormattedText.LineHeight%2A>-Eigenschaft, um einen benutzerdefinierten Zeilenabstand zu erstellen.|  
|DT_HIDEPREFIX|Keine|Wird nicht unterstützt. Entfernen Sie das "&" aus der Zeichenfolge, bevor Sie das <xref:System.Windows.Media.FormattedText> Objekt erstellen.|  
|DT_LEFT|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Dies ist die standardmäßige Textausrichtung. Verwenden Sie die <xref:System.Windows.Media.FormattedText.TextAlignment%2A>-Eigenschaft, wobei der Wert auf <xref:System.Windows.TextAlignment.Left>festgelegt ist. (nur für WPF)|  
|DT_MODIFYSTRING|Keine|Wird nicht unterstützt.|  
|DT_NOCLIP|<xref:System.Windows.Media.Visual.VisualClip%2A>|Clipping geschieht nicht automatisch. Wenn Sie Text ausschneiden möchten, verwenden Sie die <xref:System.Windows.Media.Visual.VisualClip%2A>-Eigenschaft.|  
|DT_NOFULLWIDTHCHARBREAK|Keine|Wird nicht unterstützt.|  
|DT_NOPREFIX|Keine|Nicht erforderlich Das &-Zeichen innerhalb der Zeichenfolgen wird immer als normales Zeichen behandelt.|  
|DT_PATHELLIPSIS|Keine|Verwenden Sie die <xref:System.Windows.Media.FormattedText.Trimming%2A>-Eigenschaft mit dem Wert <xref:System.Windows.TextTrimming.WordEllipsis>.|  
|DT_PREFIX|Keine|Wird nicht unterstützt. Wenn Sie Unterstriche für Text verwenden möchten, z. b. eine Zugriffstaste oder einen Link, verwenden Sie die <xref:System.Windows.Media.FormattedText.SetTextDecorations%2A>-Methode.|  
|DT_PREFIXONLY|Keine|Wird nicht unterstützt.|  
|DT_RIGHT|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Verwenden Sie die <xref:System.Windows.Media.FormattedText.TextAlignment%2A>-Eigenschaft, wobei der Wert auf <xref:System.Windows.TextAlignment.Right>festgelegt ist. (nur für WPF)|  
|DT_RTLREADING|<xref:System.Windows.Media.FormattedText.FlowDirection%2A>|Legen Sie die <xref:System.Windows.Media.FormattedText.FlowDirection%2A> -Eigenschaft auf <xref:System.Windows.FlowDirection.RightToLeft>fest.|  
|DT_SINGLELINE|Keine|Nicht erforderlich <xref:System.Windows.Media.FormattedText> Objekte verhalten sich als einzeilige Steuerelemente, es sei denn, die <xref:System.Windows.Media.FormattedText.MaxTextWidth%2A>-Eigenschaft ist festgelegt, oder der Text enthält einen Wagen Rücklauf/Zeilenvorschub (CR/LF).|  
|DT_TABSTOP|Keine|Keine Unterstützung für benutzerdefinierte Tabstopppositionen.|  
|DT_TOP|<xref:System.Windows.Media.FormattedText.Height%2A>|Nicht erforderlich Obere Ausrichtung ist die Standardeinstellung. Andere vertikale Positionierungs Werte können mit der <xref:System.Windows.Media.FormattedText.Height%2A>-Eigenschaft definiert werden, um eine entsprechende Win32-DrawText-y-Position zu berechnen.|  
|DT_VCENTER|<xref:System.Windows.Media.FormattedText.Height%2A>|Verwenden Sie die <xref:System.Windows.Media.FormattedText.Height%2A>-Eigenschaft, um eine entsprechende Win32-DrawText-y-Position zu berechnen.|  
|DT_WORDBREAK|Keine|Nicht erforderlich Die Wörter Trennung erfolgt automatisch mit <xref:System.Windows.Media.FormattedText>-Objekten. Sie kann nicht deaktiviert werden.|  
|DT_WORD_ELLIPSIS|<xref:System.Windows.Media.FormattedText.Trimming%2A>|Verwenden Sie die <xref:System.Windows.Media.FormattedText.Trimming%2A>-Eigenschaft mit dem Wert <xref:System.Windows.TextTrimming.WordEllipsis>.|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.FormattedText>
- [Dokumente in WPF](documents-in-wpf.md)
- [Typografie in WPF](typography-in-wpf.md)
- [Erstellen von Text mit Kontur](how-to-create-outlined-text.md)
- [Vorgehensweise: Erstellen einer PathGeometry-Animation für Text](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms743610(v=vs.100))
