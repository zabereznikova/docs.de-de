---
title: "Zeichnen von formatiertem Text | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Zeichnen, Formatierter Text"
  - "Formatierter Text [WPF]"
  - "Text [WPF]"
  - "Typografie, Zeichnen von formatierten Text"
ms.assetid: b1d851c1-331c-4814-9964-6fe769db6f1f
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Zeichnen von formatiertem Text
Dieses Thema enthält eine Übersicht über die Features des <xref:System.Windows.Media.FormattedText>\-Objekts.  Dieses Objekt bietet eine Steuerung auf niedriger Ebene zum Zeichnen von Text in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Anwendungen.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="technology_overview"></a>   
## Übersicht über die Technologie  
 Das <xref:System.Windows.Media.FormattedText>\-Objekt ermöglicht das Zeichnen von mehrzeiligem Text, in dem jedes Zeichen einzeln formatiert werden kann.  Im folgenden Beispiel wird Text veranschaulicht, auf den mehrere Formate angewendet wurden.  
  
 ![Mit dem FormattedText&#45;Objekt angezeigter Text](../../../../docs/framework/wpf/advanced/media/formattedtext01.png "FormattedText01")  
Angezeigter Text mit FormattedText\-Methode  
  
> [!NOTE]
>  Für Entwickler, die von der [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]\-API migrieren, enthält die Tabelle im Abschnitt [Win32\-Migration](#win32_migration) eine Auflistung der [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]\-DrawText\-Flags und die jeweilige Entsprechung in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
### Gründe für das Verwenden von formatiertem Text  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] enthält mehrere Steuerelemente, um Text auf dem Bildschirm zeichnen zu können.  Jedes Steuerelement richtet sich an ein anderes Szenario und verfügt über seine individuellen Features und Einschränkungen.  Im Allgemeinen sollte das <xref:System.Windows.Controls.TextBlock>\-Element verwendet werden, wenn eine eingeschränkte Textunterstützung erforderlich ist, z. B. ein kurzer Satz in einer [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  <xref:System.Windows.Controls.Label> kann verwendet werden, wenn nur ein Minimum an Textunterstützung erforderlich ist.  Weitere Informationen finden Sie unter [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md).  
  
 Das <xref:System.Windows.Media.FormattedText>\-Objekt bietet umfassendere Textformatierungsfeatures als [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Textsteuerelemente und kann hilfreich sein, wenn Sie Text als dekoratives Element verwenden möchten. Weitere Informationen finden Sie im folgenden Abschnitt [Konvertieren von formatiertem Text in eine Geometrie](#converting_formatted_text).  
  
 Zusätzlich ist das <xref:System.Windows.Media.FormattedText>\-Objekt hilfreich beim Erstellen textorientierter, vom <xref:System.Windows.Media.DrawingVisual>\-Element abgeleiteter Objekte.  <xref:System.Windows.Media.DrawingVisual> ist eine Lightweight\-Zeichnungsklasse zum Rendern von Formen, Bildern oder Text.  Weitere Informationen finden Sie unter [Beispiel für Treffertests mit "DrawingVisuals"](http://go.microsoft.com/fwlink/?LinkID=159994).  
  
<a name="using_the_formattedtext_object"></a>   
## Verwenden des FormattedText\-Objekts  
 Wenn Sie formatierten Text erstellen möchten, rufen Sie den <xref:System.Windows.Media.FormattedText.%23ctor%2A>\-Konstruktor auf, um ein <xref:System.Windows.Media.FormattedText>\-Objekt zu erstellen.  Nachdem Sie die formatierte Anfangs\-Textzeichenfolge erstellt haben, können Sie eine Reihe von Formatierungsstilen anwenden.  
  
 Verwenden Sie die <xref:System.Windows.Media.FormattedText.MaxTextWidth%2A>\-Eigenschaft, um den Text auf eine bestimmte Breite zu begrenzen.  Der Text wird automatisch umgebrochen, damit vermieden wird, dass er die angegebene Breite überschreitet.  Verwenden Sie die <xref:System.Windows.Media.FormattedText.MaxTextHeight%2A>\-Eigenschaft, um den Text auf eine bestimmte Höhe zu begrenzen.  Der Text zeigt Auslassungspunkte \(...\) für den Text an, der die angegebene Höhe überschreitet.  
  
 ![Mit dem FormattedText&#45;Objekt angezeigter Text](../../../../docs/framework/wpf/advanced/media/formattedtext02.png "FormattedText02")  
Angezeigter Text mit Zeilenumbruch und Auslassungspunkten  
  
 Sie können mehrere Formatierungsstile auf ein oder mehrere Zeichen anwenden.  Sie könnten z. B. sowohl die <xref:System.Windows.Media.FormattedText.SetFontSize%2A>\-Methode als auch die <xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A>\-Methode aufrufen, um die Formatierung der ersten fünf Zeichen im Text zu ändern.  
  
 Im folgenden Codebeispiel wird ein <xref:System.Windows.Media.FormattedText>\-Objekt erstellt, und anschließend werden mehrere Formatierungsstile auf den Text angewendet.  
  
 [!code-csharp[FormattedTextSnippets#FormattedTextSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets1)]
 [!code-vb[FormattedTextSnippets#FormattedTextSnippets1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets1)]  
  
### Schriftgradmaßeinheit  
 Wie andere Textobjekte in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Anwendungen muss auch das <xref:System.Windows.Media.FormattedText>\-Objekt geräteunabhängige Pixel als Maßeinheit verwenden.  Die meisten [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]\-Anwendungen verwenden jedoch Punkte als Maßeinheit.  Wenn Sie Anzeigetext in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Anwendungen in Punkteinheiten verwenden möchten, müssen Sie [!INCLUDE[TLA#tla_dipixel#plural](../../../../includes/tlasharptla-dipixelsharpplural-md.md)] in Punkte konvertieren.  Im folgenden Codebeispiel wird gezeigt, wie diese Konvertierung ausgeführt wird.  
  
 [!code-csharp[FormattedTextSnippets#FormattedTextSnippets2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets2)]
 [!code-vb[FormattedTextSnippets#FormattedTextSnippets2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets2)]  
  
<a name="converting_formatted_text"></a>   
### Konvertieren von formatiertem Text in eine Geometrie  
 Formatierter Text kann in <xref:System.Windows.Media.Geometry>\-Objekte umgewandelt werden, sodass Sie andere visuell interessante Textarten erstellen können.  Sie können beispielsweise auf Grundlage der Gliederung einer Textzeichenfolge ein <xref:System.Windows.Media.Geometry>\-Objekt erstellen.  
  
 ![Textkontur mit einem linearen Farbverlaufspinsel](../../../../docs/framework/wpf/advanced/media/outlinedtext02.png "OutlinedText02")  
  
        Textgliederung mit einem Pinsel für linearen Farbverlauf  
  
 Im folgenden Beispiel werden mehrere Möglichkeiten zum Erstellen interessanter visueller Effekte durch Ändern von Strichen, Füllung und Hervorhebung des konvertierten Texts veranschaulicht.  
  
 ![Text mit unterschiedlichen Farben für Füllung und Strich](../../../../docs/framework/wpf/advanced/media/outlinedtext03.png "OutlinedText03")  
  
        Beispiel für das Festlegen von verschiedenen Farben für Striche und Füllung  
  
 ![Text mit auf Strich angewendeten Bildpinsel](../../../../docs/framework/wpf/advanced/media/outlinedtext04.png "OutlinedText04")  
  
        Beispiel für die Anwendung eines Bildpinsels auf den Strich  
  
 ![Text mit auf Strich angewendeten Bildpinsel](../../../../docs/framework/wpf/advanced/media/outlinedtext05.png "OutlinedText05")  
Beispiel für die Anwendung eines Bildpinsels auf den Strich und die Hervorhebung  
  
 Wenn Text in ein <xref:System.Windows.Media.Geometry>\-Objekt konvertiert wird, handelt es sich nicht mehr um eine Auflistung von Zeichen. Sie können die Zeichen in der Zeichenfolge nicht mehr ändern.  Sie können jedoch die Darstellung des konvertierten Texts beeinflussen, indem Sie dessen Stricheigenschaften und Fülleigenschaften ändern.  Der Strich bezieht sich auf die Kontur des konvertierten Texts und die Füllung auf den Bereich innerhalb der Kontur des konvertierten Texts.  Weitere Informationen finden Sie unter [Erstellen von Text mit Kontur](../../../../docs/framework/wpf/advanced/how-to-create-outlined-text.md).  
  
 Sie können auch formatierten Text in ein <xref:System.Windows.Media.PathGeometry>\-Objekt konvertieren und das Objekt zum Hervorheben des Texts verwenden.  Sie können z. B. eine Animation auf das <xref:System.Windows.Media.PathGeometry>\-Objekt anwenden, sodass die Animation der Kontur des formatierten Texts folgt.  
  
 Im folgenden Beispiel wird formatierter Text angezeigt, der in ein <xref:System.Windows.Media.PathGeometry>\-Objekt konvertiert wurde.  Eine animierte Ellipse folgt den Strichen des gerenderten Texts.  
  
 ![Kugel, die der Pfadgeometrie des Textes folgt](../../../../docs/framework/wpf/advanced/media/textpathgeometry01.png "TextPathGeometry01")  
Sphäre, die der Pfadgeometrie des Texts folgt  
  
 Weitere Informationen finden Sie unter [How to: Create a PathGeometry Animation for Text](http://msdn.microsoft.com/de-de/29f8051e-798a-463f-a926-a099a99e9c67).  
  
 Sie können weitere interessante Verwendungsmöglichkeiten für formatierten Text erstellen, sobald dieser in ein <xref:System.Windows.Media.PathGeometry>\-Objekt konvertiert wurde.  So kann er z. B. für die Anzeige von Videos verwendet werden.  
  
 ![Video, das in der Pfadgeometrie von Text angezeigt wird](../../../../docs/framework/wpf/advanced/media/videotextdemo01.png "VideoTextDemo01")  
Video, das in der Pfadgeometrie des Texts angezeigt wird  
  
<a name="win32_migration"></a>   
## Win32\-Migration  
 Die Features von <xref:System.Windows.Media.FormattedText> für das Zeichnen von Text ähneln den Features der [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]\-DrawText\-Funktion.  Für Entwickler, die von der [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]\-API migrieren, enthält die folgende Tabelle eine Auflistung der [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]\-DrawText\-Flags und die jeweilige Entsprechung in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
|DrawText\-Flag|WPF\-Entsprechung|Hinweise|  
|--------------------|-----------------------|--------------|  
|DT\_BOTTOM|<xref:System.Windows.Media.FormattedText.Height%2A>|Verwenden Sie die <xref:System.Windows.Media.FormattedText.Height%2A>\-Eigenschaft, um eine entsprechende [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]\-DrawText\-'y'\-Position zu berechnen.|  
|DT\_CALCRECT|<xref:System.Windows.Media.FormattedText.Height%2A>, <xref:System.Windows.Media.FormattedText.Width%2A>|Verwenden Sie die <xref:System.Windows.Media.FormattedText.Height%2A>\-Eigenschaft und die <xref:System.Windows.Media.FormattedText.Width%2A>\-Eigenschaft, um das Ausgaberechteck zu berechnen.|  
|DT\_CENTER|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Verwenden Sie die <xref:System.Windows.Media.FormattedText.TextAlignment%2A>\-Eigenschaft, wobei der Wert auf <xref:System.Windows.TextAlignment> festgelegt ist.|  
|DT\_EDITCONTROL|None|Nicht erforderlich.  Leerzeichenbreite und letztes Linienrendering entsprechen denen im Framework\-Bearbeitungssteuerelement.|  
|DT\_END\_ELLIPSIS|<xref:System.Windows.Media.FormattedText.Trimming%2A>|Verwenden Sie die <xref:System.Windows.Media.FormattedText.Trimming%2A>\-Eigenschaft, wobei der Wert auf <xref:System.Windows.TextTrimming> festgelegt ist.<br /><br /> Verwenden Sie <xref:System.Windows.TextTrimming>, um [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] DT\_END\_ELLIPSIS mit DT\_WORD\_ELIPSIS\-Endellipse zu erhalten. In diesem Fall tritt die Zeichenellipse nur auf Wörtern auf, die nicht in eine Zeile passen.|  
|DT\_EXPAND\_TABS|None|Nicht erforderlich.  Registerkarten werden automatisch erweitert, sodass sie alle 4 em einen Haltepunkt aufweisen. Dies entspricht in etwa der Breite 8 sprachunabhängiger Zeichen.|  
|DT\_EXTERNALLEADING|None|Nicht erforderlich.  Der externe Abstand ist immer im Zeilenabstand enthalten.  Verwenden Sie die <xref:System.Windows.Media.FormattedText.LineHeight%2A>\-Eigenschaft, um einen benutzerdefinierten Zeilenabstand zu erstellen.|  
|DT\_HIDEPREFIX|None|Wird nicht unterstützt.  Entfernen Sie vor dem Erstellen des <xref:System.Windows.Media.FormattedText>\-Objekts das &\-Zeichen aus der Zeichenfolge.|  
|DT\_LEFT|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Dies ist die Standardtextausrichtung.  Verwenden Sie die <xref:System.Windows.Media.FormattedText.TextAlignment%2A>\-Eigenschaft mit dem Wert <xref:System.Windows.TextAlignment>.  \(Nur WPF\)|  
|DT\_MODIFYSTRING|None|Wird nicht unterstützt.|  
|DT\_NOCLIP|<xref:System.Windows.Media.Visual.VisualClip%2A>|Clipping geschieht nicht automatisch.  Wenn Sie Text zurechtschneiden möchten, verwenden Sie die <xref:System.Windows.Media.Visual.VisualClip%2A>\-Eigenschaft.|  
|DT\_NOFULLWIDTHCHARBREAK|None|Wird nicht unterstützt.|  
|DT\_NOPREFIX|None|Nicht erforderlich.  Das &\-Zeichen in Zeichenfolgen wird immer als normales Zeichen behandelt.|  
|DT\_PATHELLIPSIS|None|Verwenden Sie die <xref:System.Windows.Media.FormattedText.Trimming%2A>\-Eigenschaft, wobei der Wert auf <xref:System.Windows.TextTrimming> festgelegt ist.|  
|DT\_PREFIX|None|Wird nicht unterstützt.  Wenn Sie Unterstriche für Text verwenden möchten, beispielsweise eine Tastenkombination oder einen Link, verwenden Sie die <xref:System.Windows.Media.FormattedText.SetTextDecorations%2A>\-Methode.|  
|DT\_PREFIXONLY|None|Wird nicht unterstützt.|  
|DT\_RIGHT|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Verwenden Sie die <xref:System.Windows.Media.FormattedText.TextAlignment%2A>\-Eigenschaft mit dem Wert <xref:System.Windows.TextAlignment>.  \(Nur WPF\)|  
|DT\_RTLREADING|<xref:System.Windows.Media.FormattedText.FlowDirection%2A>|Legen Sie die <xref:System.Windows.Media.FormattedText.FlowDirection%2A>\-Eigenschaft auf <xref:System.Windows.FlowDirection> fest.|  
|DT\_SINGLELINE|None|Nicht erforderlich.  <xref:System.Windows.Media.FormattedText>\-Objekte verhalten sich wie einzeilige Steuerelemente, es sei denn, die <xref:System.Windows.Media.FormattedText.MaxTextWidth%2A>\-Eigenschaft ist aktiviert oder der Text enthält einen Wagenrücklauf\/Zeilenvorschub \(CR\/LF\).|  
|DT\_TABSTOP|None|Keine Unterstützung für benutzerdefinierte Tabstopppositionen.|  
|DT\_TOP|<xref:System.Windows.Media.FormattedText.Height%2A>|Nicht erforderlich.  Obere Ausrichtung ist der Standard.  Andere vertikale Positionierungswerte können definiert werden, indem die <xref:System.Windows.Media.FormattedText.Height%2A>\-Eigenschaft zur Berechnung einer entsprechenden [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]\-DrawText\-'y'\-Position verwendet wird.|  
|DT\_VCENTER|<xref:System.Windows.Media.FormattedText.Height%2A>|Verwenden Sie die <xref:System.Windows.Media.FormattedText.Height%2A>\-Eigenschaft, um eine entsprechende [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]\-DrawText\-'y'\-Position zu berechnen.|  
|DT\_WORDBREAK|None|Nicht erforderlich.  Die Worttrennung geschieht bei <xref:System.Windows.Media.FormattedText>\-Objekten automatisch.  Sie können sie nicht deaktivieren.|  
|DT\_WORD\_ELLIPSIS|<xref:System.Windows.Media.FormattedText.Trimming%2A>|Verwenden Sie die <xref:System.Windows.Media.FormattedText.Trimming%2A>\-Eigenschaft, wobei der Wert auf <xref:System.Windows.TextTrimming> festgelegt ist.|  
  
## Siehe auch  
 <xref:System.Windows.Media.FormattedText>   
 [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [Typografie in WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)   
 [Erstellen von Text mit Kontur](../../../../docs/framework/wpf/advanced/how-to-create-outlined-text.md)   
 [How to: Create a PathGeometry Animation for Text](http://msdn.microsoft.com/de-de/29f8051e-798a-463f-a926-a099a99e9c67)