---
title: Erweiterte Textformatierung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- formatting [WPF]
- text [WPF]
- typography [WPF], text formatting
ms.assetid: f0a7986e-f5b2-485c-a27d-f8e922022212
ms.openlocfilehash: e8347f1a82c70f1ce8aa7cc05841bc869abbcc33
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43787667"
---
# <a name="advanced-text-formatting"></a>Erweiterte Textformatierung
Die Windows Presentation Foundation (WPF) bietet eine Reihe zuverlässiger [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] zum Einschließen von Text in Ihrer Anwendung. Layout und [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)], z. B. <xref:System.Windows.Controls.TextBlock>, geben Sie die häufigsten und allgemeinsten Elemente für die Textdarstellung. Zeichnen von [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)], z. B. <xref:System.Windows.Media.GlyphRunDrawing> und <xref:System.Windows.Media.FormattedText>, bieten eine Möglichkeit zum Einschließen von formatierten Texts in Zeichnungen bereit. Auf der höchsten Ebene [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] bietet eine erweiterbare textformatierungs-Engine, um jeden Aspekt der Textdarstellung an, wie z. B. Speicherverwaltung für Text, die formatierungsverwaltung des Lauftexts und die Verwaltung eingebetteter Objekte steuern.  
  
 Dieses Thema enthält eine Einführung in die [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] textformatierung. Der Schwerpunkt liegt auf Clientimplementierung und Verwendung von der [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] textformatierungs-Engine.  
  
> [!NOTE]
>  Alle Codebeispiele in diesem Dokument finden Sie in der [Advanced Text Formatting Sample](https://go.microsoft.com/fwlink/?LinkID=159965).  
  

  
<a name="prereq"></a>   
## <a name="prerequisites"></a>Erforderliche Komponenten  
 In diesem Thema wird davon ausgegangen, dass Sie mit der höheren Ebene vertraut sind [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] für die Textdarstellung verwendet. Die meisten Benutzerszenarios erfordern nicht die erweiterten textformatierungs- [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] in diesem Thema erläutert. Eine Einführung in die verschiedenen Text- [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)], finden Sie unter [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md).  
  
<a name="section1"></a>   
## <a name="advanced-text-formatting"></a>Erweiterte Textformatierung  
 Das Textlayout und [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] -Steuerelemente in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] angeben von Formatierungseigenschaften, mit denen Sie einfach formatierten Text in der Anwendung einschließen können. Diese Steuerelemente bieten eine Reihe von Eigenschaften, um die Darstellung von Text zu bearbeiten, u.a. dessen Schriftart, Größe und Farbe. Unter normalen Umständen können diese Steuerelemente den Großteil der Textdarstellung in Ihrer Anwendung behandeln. Einige erweiterten Szenarios erfordern jedoch das Steuerelement des Textspeichers sowie die Textdarstellung. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] stellt eine erweiterbare Textformatierungs-Engine für diesen Zweck bereit.  
  
 Finden Sie in der erweiterten Funktionen zur textformatierung [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] bestehen aus einem Text-Formatierung-Engine, einem Textspeicher, Lauftexten und Formatierungseigenschaften. Die textformatierungs-Engine, <xref:System.Windows.Media.TextFormatting.TextFormatter>, erstellt Textzeilen für die Darstellung verwendet werden. Dies wird durch Initiierung des Zeilenformatierungsprozesses und Aufrufen des textformatierers erreicht <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A>. Der textformatierer Lauftexte aus Ihrem Textspeicher durch Aufrufen des Geschäfts <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> Methode. Die <xref:System.Windows.Media.TextFormatting.TextRun> Objekte werden dann in gebildet <xref:System.Windows.Media.TextFormatting.TextLine> Objekte mithilfe des textformatierers, und Ihre Anwendung zur Untersuchung oder Anzeige.  
  
<a name="section2"></a>   
## <a name="using-the-text-formatter"></a>Verwendung des Textformatierers  
 <xref:System.Windows.Media.TextFormatting.TextFormatter> ist die [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] textformatierungs-engine und bietet Dienste zum Formatieren und Umbrechen von Textzeilen. Der Textformatierer kann unterschiedliche Textzeichenformate und Absatzformatvorlagen verarbeiten und enthält Unterstützung für internationales Textlayout.  
  
 Im Gegensatz zu einer herkömmlichen Text- [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)], <xref:System.Windows.Media.TextFormatting.TextFormatter> interagiert mit einem Textlayoutclient durch eine Reihe von Rückrufmethoden. Der Client muss diese Methoden in einer Implementierung der Bereitstellen der <xref:System.Windows.Media.TextFormatting.TextSource> Klasse. Das folgende Diagramm veranschaulicht die Textlayoutinteraktion zwischen der Clientanwendung und <xref:System.Windows.Media.TextFormatting.TextFormatter>.  
  
 ![Diagramm des Textlayout-Clients und TextFormatter](../../../../docs/framework/wpf/advanced/media/textformatter01.png "TextFormatter01")  
Interaktion zwischen Anwendung und TextFormatter  
  
 Das Textformatierungsprogramm wird verwendet, um formatierte Textzeilen aus dem Textspeicher abzurufen. Dies ist eine Implementierung von <xref:System.Windows.Media.TextFormatting.TextSource>. Dies erfolgt durch den ersten Erstellen einer Instanz des Textformatierungsprogramms mit der <xref:System.Windows.Media.TextFormatting.TextFormatter.Create%2A> Methode. Diese Methode erstellt eine Instanz des Textformatierungsprogramms und legt die maximalen Werte für Zeilenhöhe und -breite fest. Sobald eine Instanz des textformatierers erstellt wird, wird der zeilenerstellungsprozess durch den Aufruf gestartet der <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A> Methode. <xref:System.Windows.Media.TextFormatting.TextFormatter> einen Rückruf an die Textquelle zum Abrufen von Text und Formatierungsparameter für die Ausführungen von Text, bilden eine Linie.  
  
 Im folgenden Beispiel wird der Formatierungsprozess eines Textspeichers gezeigt. Die <xref:System.Windows.Media.TextFormatting.TextFormatter> Objekt wird zum Abrufen von Textzeilen aus dem Textspeicher und formatieren Sie dann die Textzeile, die zum Zeichnen in der <xref:System.Windows.Media.DrawingContext>.  
  
 [!code-csharp[TextFormatterExample#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextFormatterExample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextFormatterExample#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextFormatterExample/VisualBasic/Window1.xaml.vb#100)]  
  
<a name="section3"></a>   
## <a name="implementing-the-client-text-store"></a>Implementieren des Clienttextspeichers  
 Wenn Sie die Textformatierungs-Engine erweitern, müssen Sie alle Aspekte des Textspeichers implementieren und verwalten. Dies ist keine einfache Aufgabe. Der Textspeicher ist für die Nachverfolgung von Lauftexteigenschaften, Absatzeigenschaften, für das Einbetten von Objekten und anderen ähnlichen Inhalt verantwortlich. Bietet auch den textformatierer mit einzelnen <xref:System.Windows.Media.TextFormatting.TextRun> Objekte, die der textformatierer benutzt, um erstellen <xref:System.Windows.Media.TextFormatting.TextLine> Objekte.  
  
 Um die Virtualisierung von Textspeicher behandeln zu können, muss der Textspeicher von abgeleitet werden <xref:System.Windows.Media.TextFormatting.TextSource>. <xref:System.Windows.Media.TextFormatting.TextSource> definiert die Methode, die der textformatierer benutzt, um Lauftext aus dem Textspeicher abzurufen. <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> ist, dass die Methode, die vom textformatierer verwendet wird, zum Abrufen von Text in der zeilenformatierung verwendeten ausgeführt wird. Der Aufruf von <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> erfolgt wiederholt vom Textformatierungsprogramm, bis eines der folgenden Bedingungen eintritt:  
  
-   Ein <xref:System.Windows.Media.TextFormatting.TextEndOfLine> oder eine Unterklasse wird zurückgegeben.  
  
-   Die kumulierte Breite des Lauftexts überschreitet die maximale Zeilenbreite, die entweder im Aufruf zum Erstellen des textformatierers oder der Aufruf an des textformatierers angegeben <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A> Methode.  
  
-   Ein [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] zeilenvorschubsequenz, z.B. "CF", "LF" oder "CRLF" wird zurückgegeben.  
  
<a name="section4"></a>   
## <a name="providing-text-runs"></a>Bereitstellen von Lauftext  
 Der wichtigste Teil des Textformatierunsprozesses ist die Interaktion zwischen Textformatierer und Textspeicher. Die Implementierung von <xref:System.Windows.Media.TextFormatting.TextSource> bietet den textformatierer die <xref:System.Windows.Media.TextFormatting.TextRun> Objekte und die Eigenschaften, die mit dem zum Formatieren des Texts ausgeführt wird. Dies erfolgt durch die <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> -Methode, die vom Textformatierungsprogramm aufgerufen wird.  
  
 Die folgende Tabelle zeigt einige der vordefinierten <xref:System.Windows.Media.TextFormatting.TextRun> Objekte.  
  
|TextRun-Typ|Verwendung|  
|------------------|-----------|  
|<xref:System.Windows.Media.TextFormatting.TextCharacters>|Der spezialisierte Lauftext, der zum Übergeben einer Darstellung von Zeichensymbolen zurück an den Textformatierer verwendet wird|  
|<xref:System.Windows.Media.TextFormatting.TextEmbeddedObject>|Der spezialisierte Lauftext, der zum Bereitstellen von Inhalt verwendet wird, in dem Messungen, Treffertests und Zeichnungen komplett ausgeführt werden, z.B. eine Schaltfläche oder ein Bild im Text|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfLine>|Der spezialisierte Lauftext, der zum Kennzeichnen des Zeilenendes verwendet wird|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfParagraph>|Der spezialisierte Lauftext, der zum Kennzeichnen eines Absatzendes verwendet wird|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfSegment>|Der spezialisierte Lauftext verwendet, um das Ende eines Segments, z. B. zu markieren, beenden Sie den Bereich von einer vorherigen betroffen sind <xref:System.Windows.Media.TextFormatting.TextModifier> ausführen.|  
|<xref:System.Windows.Media.TextFormatting.TextHidden>|Der spezialisierte Lauftext, der verwendet wird, um eine Reihe ausgeblendeter Zeichen zu kennzeichnen|  
|<xref:System.Windows.Media.TextFormatting.TextModifier>|Der spezialisierte Lauftext, der verwendet wird, um Eigenschaften der Lauftexte in deren Bereich zu ändern. Der Bereich reicht bis zum nächsten übereinstimmenden <xref:System.Windows.Media.TextFormatting.TextEndOfSegment> Lauftext oder dem nächsten <xref:System.Windows.Media.TextFormatting.TextEndOfParagraph>.|  
  
 Der vordefinierten <xref:System.Windows.Media.TextFormatting.TextRun> Objekte können in Unterklassen unterteilt werden kann. Dadurch kann Ihre Textquelle den Textformatierer mit Lauftexten bereitstellen, die benutzerdefinierte Daten enthalten.  
  
 Das folgende Beispiel zeigt eine <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> Methode. Dieser Textspeicher gibt <xref:System.Windows.Media.TextFormatting.TextRun> Objekte an den textformatierer zur Verarbeitung.  
  
 [!code-csharp[TextFormatterExample#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextFormatterExample/CSharp/CustomTextSource.cs#101)]
 [!code-vb[TextFormatterExample#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextFormatterExample/VisualBasic/CustomTextSource.vb#101)]  
  
> [!NOTE]
>  In diesem Beispiel stellt der Textspeicher die gleichen Texteigenschaften für den gesamten Text bereit. Erweiterte Textspeicher müssen ihre eigene Verwaltung für Bereiche implementieren, damit einzelne Zeichen über unterschiedliche Eigenschaften verfügen können.  
  
<a name="section5"></a>   
## <a name="specifying-formatting-properties"></a>Angeben von Formatierungseigenschaften  
 <xref:System.Windows.Media.TextFormatting.TextRun> Objekte werden mithilfe der im Textspeicher bereitgestellte Eigenschaften formatiert. Diese Eigenschaften sind in zwei Arten <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> und <xref:System.Windows.Media.TextFormatting.TextRunProperties>. <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> Behandeln Sie die Eigenschaften, die z. B. <xref:System.Windows.TextAlignment> und <xref:System.Windows.FlowDirection>. <xref:System.Windows.Media.TextFormatting.TextRunProperties> Eigenschaften, die für jeden Lauftext mit einem Absatz ist, z.B. Vordergrundpinsel, unterschiedlich sein können <xref:System.Windows.Media.Typeface>, und den Schriftgrad. Um benutzerdefinierte Absatz- und Lauftext-Eigenschaftentypen zu implementieren, muss Ihre Anwendung zu erstellen von abgeleiteten Klassen <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> und <xref:System.Windows.Media.TextFormatting.TextRunProperties> bzw.  
  
## <a name="see-also"></a>Siehe auch  
 [Typografie in WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)  
 [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)
