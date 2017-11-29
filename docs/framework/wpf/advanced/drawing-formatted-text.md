---
title: Zeichnen von formatiertem Text
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF]
- typography [WPF], drawing formatted text
- formatted text [WPF]
- drawing [WPF], formatted text
ms.assetid: b1d851c1-331c-4814-9964-6fe769db6f1f
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cad79f26a48f3f5e905b2f2ac7de9191dd8539f8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="drawing-formatted-text"></a>Zeichnen von formatiertem Text
Dieses Thema bietet eine Übersicht über die Funktionen von der <xref:System.Windows.Media.FormattedText> Objekt. Dieses Objekt bietet die Steuerung auf niedriger Ebene für das Zeichnen von Text in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Anwendungen.  
  
  
## <a name="technology-overview"></a>Technologieübersicht  
 Die <xref:System.Windows.Media.FormattedText> Objekts können Sie mehrzeilige Zeichnen von Text, in dem jedes Zeichen im Text einzeln formatiert werden kann. Das folgende Beispiel zeigt Text mit mehreren angewendeten Formaten:  
  
 ![Mit dem FormattedText-Objekt angezeigter Text](../../../../docs/framework/wpf/advanced/media/formattedtext01.jpg "FormattedText01")  
Angezeigter Text mit der FormattedText-Methode  
  
> [!NOTE]
>  Für Entwickler, die von der [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]-API migrieren, listet die Tabelle im [Win32-Migration](#win32_migration)-Abschnitt die [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]-DrawText-Flags und deren ungefähre Entsprechung in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] auf.  
  
### <a name="reasons-for-using-formatted-text"></a>Gründe für das Verwenden von formatiertem Text  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] enthält zahlreiche Steuerelemente für das Zeichnen von Text auf dem Bildschirm. Jedes Steuerelement ist einem bestimmten Szenario zugeordnet und besitzt eine eigene Liste von Funktionen und Einschränkungen. Im Allgemeinen die <xref:System.Windows.Controls.TextBlock> -Element sollte verwendet werden, wenn begrenzte-Text-Unterstützung erforderlich sind, z. B. eine kurze Satzes im wird eine [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. <xref:System.Windows.Controls.Label>kann verwendet werden, wenn wenig Text-Unterstützung erforderlich ist. Weitere Informationen finden Sie unter [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md).  
  
 Die <xref:System.Windows.Media.FormattedText> Objekt bietet umfassendere Funktionen als [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Textsteuerelemente, und kann hilfreich in Fällen, in denen Text als dekorativen Element verwendet werden soll. Weitere Informationen finden Sie im folgenden Abschnitt [Konvertieren von formatiertem Text in eine Geometrie](#converting_formatted_text).  
  
 Darüber hinaus die <xref:System.Windows.Media.FormattedText> Objekt ist nützlich zum Erstellen von textorientierte <xref:System.Windows.Media.DrawingVisual>--abgeleitete Objekte. <xref:System.Windows.Media.DrawingVisual>ist eine einfache zeichnen-Klasse, die zum Rendern von Formen, Bildern oder Text verwendet wird. Weitere Informationen finden Sie unter [Beispiel für Treffertests mit DrawingVisuals](http://go.microsoft.com/fwlink/?LinkID=159994).  
  
## <a name="using-the-formattedtext-object"></a>Verwenden des FormattedText-Objekts  
 Um formatierten Text zu erstellen, rufen Sie die <xref:System.Windows.Media.FormattedText.%23ctor%2A> Konstruktor zur Erstellung einer <xref:System.Windows.Media.FormattedText> Objekt. Nachdem Sie die Anfangszeichenfolge für formatierten Text erstellt haben, können Sie eine Reihe von Formatvorlagen anwenden.  
  
 Verwenden der <xref:System.Windows.Media.FormattedText.MaxTextWidth%2A> Eigenschaft, die den Text an einer bestimmten Breite zu beschränken. Der Text wird automatisch umgebrochen, um die angegebene Breite nicht zu überschreiten. Verwenden der <xref:System.Windows.Media.FormattedText.MaxTextHeight%2A> Eigenschaft, die den Text an einer bestimmten Höhe zu beschränken. Der Text zeigt Auslassungspunkte „...“ an, wenn die angegebene Höhe überschritten wird.  
  
 ![Mit dem FormattedText-Objekt angezeigter Text](../../../../docs/framework/wpf/advanced/media/formattedtext02.png "FormattedText02")  
Angezeigter Text mit Zeilenumbruch und Auslassungspunkten  
  
 Sie können mehrere Formatvorlagen auf ein oder mehrere Zeichen anwenden. Sie können z. B. Aufrufen sowohl die <xref:System.Windows.Media.FormattedText.SetFontSize%2A> und <xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A> Methoden, um die Formatierung der ersten fünf Zeichen im Text ändern.  
  
 Das folgende Codebeispiel erstellt eine <xref:System.Windows.Media.FormattedText> Objekt, und klicken Sie dann mehrere Formatierungsstile auf den Text angewendet.  
  
 [!code-csharp[FormattedTextSnippets#FormattedTextSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets1)]
 [!code-vb[FormattedTextSnippets#FormattedTextSnippets1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets1)]  
  
### <a name="font-size-unit-of-measure"></a>Maßeinheit für den Schriftgrad  
 Wie bei anderen Textobjekten in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Anwendungen, die <xref:System.Windows.Media.FormattedText> Objekt geräteunabhängige Pixel als Maßeinheit verwendet. Die meisten [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]-Anwendungen verwenden jedoch Punkte als Maßeinheit. Möchten Sie in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Anwendungen Punkte als Maßeinheit für angezeigten Text verwenden, müssen Sie [!INCLUDE[TLA#tla_dipixel#plural](../../../../includes/tlasharptla-dipixelsharpplural-md.md)] in Punkte konvertieren. Der folgende Code veranschaulicht diese Konvertierung:  
  
 [!code-csharp[FormattedTextSnippets#FormattedTextSnippets2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets2)]
 [!code-vb[FormattedTextSnippets#FormattedTextSnippets2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets2)]  
  
<a name="converting_formatted_text"></a>   
### <a name="converting-formatted-text-to-a-geometry"></a>Konvertieren von formatiertem Text in eine Geometrie  
 Sie können auch formatierten Text in konvertieren <xref:System.Windows.Media.Geometry> Objekte, sodass Sie andere Arten von visuell interessante Text zu erstellen. Sie können z. B. Erstellen einer <xref:System.Windows.Media.Geometry> Objekt auf Grundlage der Gliederung einer Textzeichenfolge.  
  
 ![Textkontur mit einem linearen Farbverlaufspinsel](../../../../docs/framework/wpf/advanced/media/outlinedtext02.jpg "OutlinedText02")  
Textkontur mit einem linearen Farbverlaufspinsel  
  
 Die folgenden Beispiele zeigen verschiedene Möglichkeiten zum Erstellen von visuell interessanten Effekten durch Ändern von Strich, Füllung und Hervorhebung des konvertierten Texts.  
  
 ![Text mit unterschiedlichen Farben für Füllung und Strich](../../../../docs/framework/wpf/advanced/media/outlinedtext03.jpg "OutlinedText03")  
Beispiel für das Festlegen von unterschiedlichen Farben für Strich und Füllung  
  
 ![Text mit auf Strich angewendeten Bildpinsel](../../../../docs/framework/wpf/advanced/media/outlinedtext04.jpg "OutlinedText04")  
Beispiel für die Anwendung eines Bildpinsels auf den Strich  
  
 ![Text mit auf Strich angewendeten Bildpinsel](../../../../docs/framework/wpf/advanced/media/outlinedtext05.jpg "OutlinedText05")  
Beispiel für die Anwendung eines Bildpinsels auf den Strich und die Hervorhebung  
  
 Wenn Text konvertiert wird, wird ein <xref:System.Windows.Media.Geometry> -Objekt, es ist nicht mehr eine Auflistung von Zeichen – die Zeichen in der Textzeichenfolge kann nicht geändert werden. Sie können jedoch die Darstellung des konvertierten Texts durch Ändern der Strich- und Füllungseigenschaften ändern. Der Strich bezieht sich auf die Kontur des konvertierten Texts und die Füllung auf den Bereich innerhalb der Kontur. Weitere Informationen finden Sie unter [Erstellen von Text mit Kontur](../../../../docs/framework/wpf/advanced/how-to-create-outlined-text.md).  
  
 Sie können auch formatierten Text zum Konvertieren einer <xref:System.Windows.Media.PathGeometry> -Objekt und das Objekt zum Hervorheben des Texts verwenden. Sie konnten z. B. Animation Anwenden der <xref:System.Windows.Media.PathGeometry> Objekt, sodass die Animation die Kontur des formatierten Text folgt.  
  
 Das folgende Beispiel zeigt der formatierte Text, der in konvertiert wurde ein <xref:System.Windows.Media.PathGeometry> Objekt. Eine animierte Ellipse folgt dem Strichpfad des gerenderten Texts.  
  
 ![Kugel, die der Pfadgeometrie des Textes folgt](../../../../docs/framework/wpf/advanced/media/textpathgeometry01.gif "TextPathGeometry01")  
Kugel, die der Pfadgeometrie des Textes folgt  
  
 Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen einer PathGeometry-Animation für Text](http://msdn.microsoft.com/en-us/29f8051e-798a-463f-a926-a099a99e9c67).  
  
 Sie können weitere interessanten Verwendungsmöglichkeiten für formatierten Text erstellen, sobald es in konvertiert wurde ein <xref:System.Windows.Media.PathGeometry> Objekt. So können Sie beispielsweise ein zugeschnittenes Video darin anzeigen.  
  
 ![Video anzeigen, in der Pfadgeometrie des Textes](../../../../docs/framework/wpf/advanced/media/videotextdemo01.png "VideoTextDemo01")  
Video, das in der Pfadgeometrie von Text angezeigt wird  
  
<a name="win32_migration"></a>   
## <a name="win32-migration"></a>Win32-Migration  
 Die Funktionen von <xref:System.Windows.Media.FormattedText> zum Zeichnen von Text ähneln die Funktionen von der [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] DrawText-Funktion. Für Entwickler, die von der [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]-API migrieren, listet die folgende Tabelle die [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]-DrawText-Flags und deren ungefähre Entsprechung in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] auf.  
  
|DrawText-Flag|WPF-Entsprechung|Notizen|  
|-------------------|--------------------|-----------|  
|DT_BOTTOM|<xref:System.Windows.Media.FormattedText.Height%2A>|Verwenden der <xref:System.Windows.Media.FormattedText.Height%2A> Eigenschaft zur Berechnung einer entsprechenden [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] DrawText 'y'-Position.|  
|DT_CALCRECT|<xref:System.Windows.Media.FormattedText.Height%2A>, <xref:System.Windows.Media.FormattedText.Width%2A>|Verwenden der <xref:System.Windows.Media.FormattedText.Height%2A> und <xref:System.Windows.Media.FormattedText.Width%2A> Eigenschaften, um das Ausgaberechteck zu berechnen.|  
|DT_CENTER|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Verwenden der <xref:System.Windows.Media.FormattedText.TextAlignment%2A> Eigenschaft mit dem Wert <xref:System.Windows.TextAlignment.Center>.|  
|DT_EDITCONTROL|Keine|Nicht erforderlich Rendern von Abstandsbreite und letzter Zeile sind identisch mit dem Edit-Steuerelement für Framework.|  
|DT_END_ELLIPSIS|<xref:System.Windows.Media.FormattedText.Trimming%2A>|Verwenden der <xref:System.Windows.Media.FormattedText.Trimming%2A> Eigenschaft mit dem Wert <xref:System.Windows.TextTrimming.CharacterEllipsis>.<br /><br /> Verwendung <xref:System.Windows.TextTrimming.WordEllipsis> abzurufenden [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] DT_END_ELLIPSIS mit DT_WORD_ELIPSIS enden mit den Auslassungspunkten – in diesem Fall Zeichen mit den Auslassungspunkten tritt nur auf Wörter, die nicht groß genug ist in einer einzelnen Zeile.|  
|DT_EXPAND_TABS|Keine|Nicht erforderlich Registerkarten werden automatisch auf Zwischenstopps nach jeweils 4 em erweitert. Dies entspricht etwa der Breite von 8 sprachunabhängigen Zeichen.|  
|DT_EXTERNALLEADING|Keine|Nicht erforderlich Der externe Abstand ist immer im Zeilenabstand enthalten. Verwenden der <xref:System.Windows.Media.FormattedText.LineHeight%2A> Eigenschaft zum Erstellen von benutzerdefinierten Zeilenabstand.|  
|DT_HIDEPREFIX|Keine|Wird nicht unterstützt. Entfernen Sie die "&" aus der Zeichenfolge vor der Erstellung der <xref:System.Windows.Media.FormattedText> Objekt.|  
|DT_LEFT|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Dies ist die standardmäßige Textausrichtung. Verwenden der <xref:System.Windows.Media.FormattedText.TextAlignment%2A> Eigenschaft mit dem Wert <xref:System.Windows.TextAlignment.Left>. (nur für WPF)|  
|DT_MODIFYSTRING|Keine|Wird nicht unterstützt.|  
|DT_NOCLIP|<xref:System.Windows.Media.Visual.VisualClip%2A>|Clipping geschieht nicht automatisch. Verwenden Sie nach Bedarf Clip-Text, der <xref:System.Windows.Media.Visual.VisualClip%2A> Eigenschaft.|  
|DT_NOFULLWIDTHCHARBREAK|Keine|Wird nicht unterstützt.|  
|DT_NOPREFIX|Keine|Nicht erforderlich Das &-Zeichen innerhalb der Zeichenfolgen wird immer als normales Zeichen behandelt.|  
|DT_PATHELLIPSIS|Keine|Verwenden der <xref:System.Windows.Media.FormattedText.Trimming%2A> Eigenschaft mit dem Wert <xref:System.Windows.TextTrimming.WordEllipsis>.|  
|DT_PREFIX|Keine|Wird nicht unterstützt. Verwenden Sie, wenn Sie Unterstriche für Text, z. B. eine Zugriffstaste oder Link verwenden möchten die <xref:System.Windows.Media.FormattedText.SetTextDecorations%2A> Methode.|  
|DT_PREFIXONLY|Keine|Wird nicht unterstützt.|  
|DT_RIGHT|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Verwenden der <xref:System.Windows.Media.FormattedText.TextAlignment%2A> Eigenschaft mit dem Wert <xref:System.Windows.TextAlignment.Right>. (nur für WPF)|  
|DT_RTLREADING|<xref:System.Windows.Media.FormattedText.FlowDirection%2A>|Legen Sie die <xref:System.Windows.Media.FormattedText.FlowDirection%2A>-Eigenschaft auf <xref:System.Windows.FlowDirection.RightToLeft> fest.|  
|DT_SINGLELINE|Keine|Nicht erforderlich <xref:System.Windows.Media.FormattedText>Objekte verhalten sich wie ein einzeiliges Steuerelement, es sei denn, entweder die <xref:System.Windows.Media.FormattedText.MaxTextWidth%2A> Eigenschaft festgelegt ist, oder den Text enthält, einen Wagenrücklauf/Zeilenvorschub (CR/LF).|  
|DT_TABSTOP|Keine|Keine Unterstützung für benutzerdefinierte Tabstopppositionen.|  
|DT_TOP|<xref:System.Windows.Media.FormattedText.Height%2A>|Nicht erforderlich Obere Ausrichtung ist die Standardeinstellung. Andere Werte für vertikale Positionierung können definiert werden, indem die <xref:System.Windows.Media.FormattedText.Height%2A> Eigenschaft zur Berechnung einer entsprechenden [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] DrawText 'y'-Position.|  
|DT_VCENTER|<xref:System.Windows.Media.FormattedText.Height%2A>|Verwenden der <xref:System.Windows.Media.FormattedText.Height%2A> Eigenschaft zur Berechnung einer entsprechenden [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] DrawText 'y'-Position.|  
|DT_WORDBREAK|Keine|Nicht erforderlich Worttrennung geschieht automatisch bei <xref:System.Windows.Media.FormattedText> Objekte. Sie kann nicht deaktiviert werden.|  
|DT_WORD_ELLIPSIS|<xref:System.Windows.Media.FormattedText.Trimming%2A>|Verwenden der <xref:System.Windows.Media.FormattedText.Trimming%2A> Eigenschaft mit dem Wert <xref:System.Windows.TextTrimming.WordEllipsis>.|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.FormattedText>  
 [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [Typografie in WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)  
 [Erstellen von Text mit Kontur](../../../../docs/framework/wpf/advanced/how-to-create-outlined-text.md)  
 [Vorgehensweise: Erstellen einer PathGeometry-Animation für Text](http://msdn.microsoft.com/en-us/29f8051e-798a-463f-a926-a099a99e9c67)
