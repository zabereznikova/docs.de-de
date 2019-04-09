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
ms.openlocfilehash: a61031c36dea84449ad07175287bf834544df886
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59129089"
---
# <a name="drawing-formatted-text"></a>Zeichnen von formatiertem Text
Dieses Thema enthält eine Übersicht über die Funktionen von der <xref:System.Windows.Media.FormattedText> Objekt. Dieses Objekt bietet die Steuerung auf niedriger Ebene für das Zeichnen von Text in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Anwendungen.  

## <a name="technology-overview"></a>Übersicht über die Technologie  
 Die <xref:System.Windows.Media.FormattedText> Objekt können Sie mehrzeiligen Text zu zeichnen, in dem jedes Zeichen im Text einzeln formatiert werden kann. Das folgende Beispiel zeigt Text mit mehreren angewendeten Formaten:  
  
 ![Mit dem FormattedText-Objekt angezeigter Text](./media/typography-in-wpf/text-formatted-linear-gradient.jpg)  
  
> [!NOTE]
>  Für Entwickler, die von der [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]-API migrieren, listet die Tabelle im [Win32-Migration](#win32_migration)-Abschnitt die [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]-DrawText-Flags und deren ungefähre Entsprechung in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] auf.  
  
### <a name="reasons-for-using-formatted-text"></a>Gründe für das Verwenden von formatiertem Text  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] enthält mehrere Steuerelemente, die zum Zeichnen von Text auf dem Bildschirm. Jedes Steuerelement ist einem bestimmten Szenario zugeordnet und besitzt eine eigene Liste von Funktionen und Einschränkungen. Im Allgemeinen die <xref:System.Windows.Controls.TextBlock> Element sollte verwendet werden, wenn nur eingeschränkte Textelemente-Unterstützung erforderlich ist, z. B. einem kurzen Satz in einem [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. <xref:System.Windows.Controls.Label> kann verwendet werden, wenn nur minimale textunterstützung erforderlich ist. Weitere Informationen finden Sie unter [Dokumente in WPF](documents-in-wpf.md).  
  
 Die <xref:System.Windows.Media.FormattedText> -Objekt bietet umfassendere Textformatierungsfunktionen als [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Textsteuerelementtyp entspricht, und können nützlich sein, in Fällen, in denen Text als dekoratives Element verwendet werden sollen. Weitere Informationen finden Sie im folgenden Abschnitt [Konvertieren von formatiertem Text in eine Geometrie](#converting_formatted_text).  
  
 Darüber hinaus die <xref:System.Windows.Media.FormattedText> Objekt ist nützlich zum Erstellen von textorientierten <xref:System.Windows.Media.DrawingVisual>--abgeleitete Objekte. <xref:System.Windows.Media.DrawingVisual> ist eine einfache Zeichnungsklasse, die zum Rendern von Formen, Bildern oder Text verwendet wird. Weitere Informationen finden Sie unter [Beispiel für Treffertests mit DrawingVisuals](https://go.microsoft.com/fwlink/?LinkID=159994).  
  
## <a name="using-the-formattedtext-object"></a>Verwenden des FormattedText-Objekts  
 Um formatierten Text erstellen möchten, rufen die <xref:System.Windows.Media.FormattedText.%23ctor%2A> Konstruktor zur Erstellung einer <xref:System.Windows.Media.FormattedText> Objekt. Nachdem Sie die Anfangszeichenfolge für formatierten Text erstellt haben, können Sie eine Reihe von Formatvorlagen anwenden.  
  
 Verwenden der <xref:System.Windows.Media.FormattedText.MaxTextWidth%2A> Eigenschaft, um den Text auf eine bestimmte Breite zu begrenzen. Der Text wird automatisch umgebrochen, um die angegebene Breite nicht zu überschreiten. Verwenden der <xref:System.Windows.Media.FormattedText.MaxTextHeight%2A> Eigenschaft, um den Text auf eine bestimmte Höhe zu begrenzen. Der Text zeigt Auslassungspunkte „...“ an, wenn die angegebene Höhe überschritten wird.  
  
 ![Text mit Wordwrap und mit den Auslassungszeichen angezeigt.](./media/drawing-formatted-text/formatted-text-wordwrap-ellipsis.png)    
  
 Sie können mehrere Formatvorlagen auf ein oder mehrere Zeichen anwenden. Sie können z. B. Aufrufen sowohl die <xref:System.Windows.Media.FormattedText.SetFontSize%2A> und <xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A> Methoden zum Ändern der Formatierung der ersten fünf Zeichen im Text.  
  
 Das folgende Codebeispiel erstellt eine <xref:System.Windows.Media.FormattedText> Objekt aus, und anschließend mehrere Formatvorlagen auf den Text angewendet.  
  
 [!code-csharp[FormattedTextSnippets#FormattedTextSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets1)]
 [!code-vb[FormattedTextSnippets#FormattedTextSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets1)]  
  
### <a name="font-size-unit-of-measure"></a>Maßeinheit für den Schriftgrad  
 Wie andere Textobjekte in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Anwendungen, die <xref:System.Windows.Media.FormattedText> Objekt verwendet geräteunabhängige Pixel als Maßeinheit an. Die meisten [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]-Anwendungen verwenden jedoch Punkte als Maßeinheit. Möchten Sie in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Anwendungen Punkte als Maßeinheit für angezeigten Text verwenden, müssen Sie [!INCLUDE[TLA#tla_dipixel#plural](../../../../includes/tlasharptla-dipixelsharpplural-md.md)] in Punkte konvertieren. Der folgende Code veranschaulicht diese Konvertierung:  
  
 [!code-csharp[FormattedTextSnippets#FormattedTextSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets2)]
 [!code-vb[FormattedTextSnippets#FormattedTextSnippets2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets2)]  
  
<a name="converting_formatted_text"></a>   
### <a name="converting-formatted-text-to-a-geometry"></a>Konvertieren von formatiertem Text in eine Geometrie  
 Sie können formatierten Text in konvertieren <xref:System.Windows.Media.Geometry> Objekte, die Ihnen ermöglichen, andere Arten von visuell interessantem Text erstellen. Sie können z. B. Erstellen einer <xref:System.Windows.Media.Geometry> Objekt auf Grundlage der Gliederung einer Textzeichenfolge.  
  
 ![Textkontur mit einem linearen Farbverlaufspinsel](./media/typography-in-wpf/text-outline-linear-gradient.jpg)    
  
 Die folgenden Beispiele zeigen verschiedene Möglichkeiten zum Erstellen von visuell interessanten Effekten durch Ändern von Strich, Füllung und Hervorhebung des konvertierten Texts.  
  
 ![Text mit unterschiedlichen Farben für Füllung und Strich](./media/typography-in-wpf/fill-stroke-text-effect.jpg)  
  
 ![Text mit auf Strich angewendeten Bildpinsel](./media/typography-in-wpf/image-brush-application.jpg)
  
 ![Text mit Bildpinsel angewendet, um zu zeichnen, und markieren](./media/typography-in-wpf/image-brush-text-application.jpg)
  
 Wenn in Text konvertiert wird eine <xref:System.Windows.Media.Geometry> Objekt, es ist nicht mehr eine Sammlung von Zeichen, die Zeichen in der Textzeichenfolge kann nicht geändert werden. Sie können jedoch die Darstellung des konvertierten Texts durch Ändern der Strich- und Füllungseigenschaften ändern. Der Strich bezieht sich auf die Kontur des konvertierten Texts und die Füllung auf den Bereich innerhalb der Kontur. Weitere Informationen finden Sie unter [Erstellen von Text mit Kontur](how-to-create-outlined-text.md).  
  
 Sie können auch formatierten Text zum Konvertieren einer <xref:System.Windows.Media.PathGeometry> -Objekt und verwenden Sie das Objekt zum Hervorheben des Texts. Sie können z. B. eine Animation Anwenden der <xref:System.Windows.Media.PathGeometry> Objekts, sodass die Animation die Kontur des formatierten Texts folgt.  
  
 Das folgende Beispiel zeigt formatierten Text, der in konvertiert wurde eine <xref:System.Windows.Media.PathGeometry> Objekt. Eine animierte Ellipse folgt dem Strichpfad des gerenderten Texts.  
  
 ![Kugel, die der Pfadgeometrie des Textes folgt](./media/drawing-formatted-text/sphere-following-geometry-path.gif)  
Kugel, die der Pfadgeometrie des Textes folgt  
  
 Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eine PathGeometry-Animation für Text](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms743610(v=vs.100)).  
  
 Sie können weitere interessanten Verwendungsmöglichkeiten für formatierten Text erstellen, sobald er in konvertiert wurde eine <xref:System.Windows.Media.PathGeometry> Objekt. So können Sie beispielsweise ein zugeschnittenes Video darin anzeigen.  
  
 ![Video, das in der Pfadgeometrie von Text angezeigt wird](./media/drawing-formatted-text/video-displaying-text-path-geometry.png)
  
<a name="win32_migration"></a>   
## <a name="win32-migration"></a>Win32-Migration  
 Die Funktionen von <xref:System.Windows.Media.FormattedText> zum Zeichnen von Text ähneln den Funktionen von der [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] DrawText-Funktion. Für Entwickler, die von der [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]-API migrieren, listet die folgende Tabelle die [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]-DrawText-Flags und deren ungefähre Entsprechung in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] auf.  
  
|DrawText-Flag|WPF-Entsprechung|Hinweise|  
|-------------------|--------------------|-----------|  
|DT_BOTTOM|<xref:System.Windows.Media.FormattedText.Height%2A>|Verwenden der <xref:System.Windows.Media.FormattedText.Height%2A> -Eigenschaft zur Berechnung einer entsprechenden [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] DrawText-y-Position.|  
|DT_CALCRECT|<xref:System.Windows.Media.FormattedText.Height%2A>, <xref:System.Windows.Media.FormattedText.Width%2A>|Verwenden der <xref:System.Windows.Media.FormattedText.Height%2A> und <xref:System.Windows.Media.FormattedText.Width%2A> Eigenschaften des ausgaberechtecks.|  
|DT_CENTER|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Verwenden der <xref:System.Windows.Media.FormattedText.TextAlignment%2A> Eigenschaft mit dem der Wert festgelegt, <xref:System.Windows.TextAlignment.Center>.|  
|DT_EDITCONTROL|Keiner|Nicht erforderlich Rendern von Abstandsbreite und letzter Zeile sind identisch mit dem Edit-Steuerelement für Framework.|  
|DT_END_ELLIPSIS|<xref:System.Windows.Media.FormattedText.Trimming%2A>|Verwenden der <xref:System.Windows.Media.FormattedText.Trimming%2A> Eigenschaft mit dem Wert <xref:System.Windows.TextTrimming.CharacterEllipsis>.<br /><br /> Verwenden <xref:System.Windows.TextTrimming.WordEllipsis> abzurufenden [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] DT_END_ELLIPSIS mit DT_WORD_ELIPSIS-Endellipse — in diesem Fall zeichenellipse nur auf Wörtern, die nicht in einer einzelnen Zeile auftritt.|  
|DT_EXPAND_TABS|Keiner|Nicht erforderlich Registerkarten werden automatisch auf Zwischenstopps nach jeweils 4 em erweitert. Dies entspricht etwa der Breite von 8 sprachunabhängigen Zeichen.|  
|DT_EXTERNALLEADING|Keiner|Nicht erforderlich Der externe Abstand ist immer im Zeilenabstand enthalten. Verwenden der <xref:System.Windows.Media.FormattedText.LineHeight%2A> Eigenschaft, um eine benutzerdefinierte Zeilenabstand zu erstellen.|  
|DT_HIDEPREFIX|Keiner|Wird nicht unterstützt. Entfernen Sie die '&' aus der Zeichenfolge vor der Erstellung der <xref:System.Windows.Media.FormattedText> Objekt.|  
|DT_LEFT|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Dies ist die standardmäßige Textausrichtung. Verwenden der <xref:System.Windows.Media.FormattedText.TextAlignment%2A> Eigenschaft mit dem der Wert festgelegt, <xref:System.Windows.TextAlignment.Left>. (nur für WPF)|  
|DT_MODIFYSTRING|Keiner|Wird nicht unterstützt.|  
|DT_NOCLIP|<xref:System.Windows.Media.Visual.VisualClip%2A>|Clipping geschieht nicht automatisch. Wenn Sie Beschneiden von Text möchten, verwenden Sie die <xref:System.Windows.Media.Visual.VisualClip%2A> Eigenschaft.|  
|DT_NOFULLWIDTHCHARBREAK|Keiner|Wird nicht unterstützt.|  
|DT_NOPREFIX|Keiner|Nicht erforderlich Das &-Zeichen innerhalb der Zeichenfolgen wird immer als normales Zeichen behandelt.|  
|DT_PATHELLIPSIS|Keiner|Verwenden der <xref:System.Windows.Media.FormattedText.Trimming%2A> Eigenschaft mit dem Wert <xref:System.Windows.TextTrimming.WordEllipsis>.|  
|DT_PREFIX|Keiner|Wird nicht unterstützt. Wenn Unterstriche für Text, z. B. eine Zugriffstaste oder Link verwendet werden sollen. verwenden Sie die <xref:System.Windows.Media.FormattedText.SetTextDecorations%2A> Methode.|  
|DT_PREFIXONLY|Keiner|Wird nicht unterstützt.|  
|DT_RIGHT|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Verwenden der <xref:System.Windows.Media.FormattedText.TextAlignment%2A> Eigenschaft mit dem der Wert festgelegt, <xref:System.Windows.TextAlignment.Right>. (nur für WPF)|  
|DT_RTLREADING|<xref:System.Windows.Media.FormattedText.FlowDirection%2A>|Legen Sie die <xref:System.Windows.Media.FormattedText.FlowDirection%2A> -Eigenschaft auf <xref:System.Windows.FlowDirection.RightToLeft>fest.|  
|DT_SINGLELINE|Keiner|Nicht erforderlich <xref:System.Windows.Media.FormattedText> Objekte verhalten sich als einzelne Zeile-Steuerelement, es sei denn, entweder die <xref:System.Windows.Media.FormattedText.MaxTextWidth%2A> Eigenschaft festgelegt ist, oder den Text enthält, einen Wagenrücklauf/Zeilenvorschub (CR/LF).|  
|DT_TABSTOP|Keiner|Keine Unterstützung für benutzerdefinierte Tabstopppositionen.|  
|DT_TOP|<xref:System.Windows.Media.FormattedText.Height%2A>|Nicht erforderlich Obere Ausrichtung ist die Standardeinstellung. Andere vertikale Positionierungswerte können definiert werden, indem die <xref:System.Windows.Media.FormattedText.Height%2A> -Eigenschaft zur Berechnung einer entsprechenden [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] DrawText-y-Position.|  
|DT_VCENTER|<xref:System.Windows.Media.FormattedText.Height%2A>|Verwenden der <xref:System.Windows.Media.FormattedText.Height%2A> -Eigenschaft zur Berechnung einer entsprechenden [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] DrawText-y-Position.|  
|DT_WORDBREAK|Keiner|Nicht erforderlich Die wörtertrennung geschieht automatisch mit <xref:System.Windows.Media.FormattedText> Objekte. Sie kann nicht deaktiviert werden.|  
|DT_WORD_ELLIPSIS|<xref:System.Windows.Media.FormattedText.Trimming%2A>|Verwenden der <xref:System.Windows.Media.FormattedText.Trimming%2A> Eigenschaft mit dem Wert <xref:System.Windows.TextTrimming.WordEllipsis>.|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.FormattedText>
- [Dokumente in WPF](documents-in-wpf.md)
- [Typografie in WPF](typography-in-wpf.md)
- [Erstellen von Text mit Kontur](how-to-create-outlined-text.md)
- [Vorgehensweise: Erstellen einer PathGeometry-Animation für Text](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms743610(v=vs.100))
