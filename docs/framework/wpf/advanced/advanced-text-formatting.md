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
ms.openlocfilehash: 745d20e0bd4f877f9d4559f9fc7829b56689d35c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185943"
---
# <a name="advanced-text-formatting"></a>Erweiterte Textformatierung
Windows Presentation Foundation (WPF) bietet einen robusten Satz von APIs für die Einschlussvon Text in Ihre Anwendung. Layout [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] und APIs, <xref:System.Windows.Controls.TextBlock>z. B. , stellen die häufigsten und allgemein verwendenden Elemente für die Textpräsentation bereit. Zeichnungs-APIs, <xref:System.Windows.Media.GlyphRunDrawing> <xref:System.Windows.Media.FormattedText>z. B. und , bieten eine Möglichkeit, formatierten Text in Zeichnungen einzuschließen. Auf der fortschrittlichsten Ebene bietet WPF ein erweiterbares Textformatierungsmodul, um jeden Aspekt der Textpräsentation zu steuern, z. B. Textspeicherverwaltung, Formatierungsverwaltung für Textläufe und eingebettete Objektverwaltung.  
  
 Dieses Thema enthält eine Einführung in die WPF-Textformatierung. Der Schwerpunkt liegt auf der Clientimplementierung und der Verwendung des WPF-Textformatierungsmoduls.  
  
> [!NOTE]
> Alle Codebeispiele in diesem Dokument finden Sie im Beispiel für [erweiterte Textformatierung](https://github.com/Microsoft/WPF-Samples/tree/master/PerMonitorDPI/TextFormatting).  

<a name="prereq"></a>
## <a name="prerequisites"></a>Voraussetzungen  
 In diesem Thema wird davon ausgegangen, dass Sie mit den APIs auf höherer Ebene vertraut sind, die für die Textpräsentation verwendet werden. Für die meisten Benutzerszenarien sind die in diesem Thema erläuterten erweiterten Textformatierungs-APIs nicht erforderlich. Eine Einführung in die verschiedenen Text-APIs finden Sie unter [Dokumente in WPF](documents-in-wpf.md).  
  
<a name="section1"></a>
## <a name="advanced-text-formatting"></a>Erweiterte Textformatierung  
 Das Textlayout [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] und die Steuerelemente in WPF stellen Formatierungseigenschaften bereit, mit denen Sie formatierten Text problemlos in Ihre Anwendung einschließen können. Diese Steuerelemente bieten eine Reihe von Eigenschaften, um die Darstellung von Text zu bearbeiten, u.a. dessen Schriftart, Größe und Farbe. Unter normalen Umständen können diese Steuerelemente den Großteil der Textdarstellung in Ihrer Anwendung behandeln. Einige erweiterten Szenarios erfordern jedoch das Steuerelement des Textspeichers sowie die Textdarstellung. WPF stellt zu diesem Zweck ein erweiterbares Textformatierungsmodul bereit.  
  
 Die erweiterten Textformatierungsfeatures in WPF bestehen aus einem Textformatierungsmodul, einem Textspeicher, Textausführungen und Formatierungseigenschaften. Das Textformatierungsmodul , , erstellt Textzeilen, <xref:System.Windows.Media.TextFormatting.TextFormatter>die für die Präsentation verwendet werden sollen. Dies wird erreicht, indem der Zeilenformatierungsprozess in ganggeleitet <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A>und der Textformatierungsvorgang aufgerufen wird. Der Textformataton ruft Textläufe aus dem Textspeicher ab, indem die Methode des Informationsspeichers <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> aufgerufen wird. Die <xref:System.Windows.Media.TextFormatting.TextRun> Objekte werden <xref:System.Windows.Media.TextFormatting.TextLine> dann durch den Textformatatoihrer zu Objekten geformt und Ihrer Anwendung zur Prüfung oder Anzeige übergeben.  
  
<a name="section2"></a>
## <a name="using-the-text-formatter"></a>Verwendung des Textformatierers  
 <xref:System.Windows.Media.TextFormatting.TextFormatter>ist das WPF-Textformatierungsmodul und bietet Dienste zum Formatieren und Umteilen von Textzeilen. Der Textformatierer kann unterschiedliche Textzeichenformate und Absatzformatvorlagen verarbeiten und enthält Unterstützung für internationales Textlayout.  
  
 Im Gegensatz zu einer <xref:System.Windows.Media.TextFormatting.TextFormatter> herkömmlichen Text-API interagiert der mit einem Textlayoutclient über eine Reihe von Rückrufmethoden. Der Client muss diese Methoden in einer <xref:System.Windows.Media.TextFormatting.TextSource> Implementierung der Klasse bereitstellen. Das folgende Diagramm veranschaulicht die Textlayoutinteraktion <xref:System.Windows.Media.TextFormatting.TextFormatter>zwischen der Clientanwendung und .  
  
 ![Diagramm des Textlayout-Clients und TextFormatter](./media/advanced-text-formatting/text-layout-textformatter-interaction.png)  
  
 Der Textformataton wird verwendet, um formatierte Textzeilen aus <xref:System.Windows.Media.TextFormatting.TextSource>dem Textspeicher abzurufen, bei dem es sich um eine Implementierung von handelt. Dies geschieht, indem zuerst eine Instanz des <xref:System.Windows.Media.TextFormatting.TextFormatter.Create%2A> Textformataums mithilfe der Methode erstellt wird. Diese Methode erstellt eine Instanz des Textformatierungsprogramms und legt die maximalen Werte für Zeilenhöhe und -breite fest. Sobald eine Instanz des Textformataums erstellt wird, wird der <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A> Zeilenerstellungsprozess durch Aufrufen der Methode gestartet. <xref:System.Windows.Media.TextFormatting.TextFormatter>ruft an die Textquelle zurück, um die Text- und Formatierungsparameter für die Durchläufe von Text, die eine Zeile bilden, abzurufen.  
  
 Im folgenden Beispiel wird der Formatierungsprozess eines Textspeichers gezeigt. Das <xref:System.Windows.Media.TextFormatting.TextFormatter> Objekt wird verwendet, um Textzeilen aus dem Textspeicher abzurufen und dann die Textzeile für das Zeichnen in die <xref:System.Windows.Media.DrawingContext>zu formatieren.  
  
 [!code-csharp[TextFormatterExample#100](~/samples/snippets/csharp/VS_Snippets_Wpf/TextFormatterExample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextFormatterExample#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextFormatterExample/VisualBasic/Window1.xaml.vb#100)]  
  
<a name="section3"></a>
## <a name="implementing-the-client-text-store"></a>Implementieren des Clienttextspeichers  
 Wenn Sie die Textformatierungs-Engine erweitern, müssen Sie alle Aspekte des Textspeichers implementieren und verwalten. Dies ist keine einfache Aufgabe. Der Textspeicher ist für die Nachverfolgung von Lauftexteigenschaften, Absatzeigenschaften, für das Einbetten von Objekten und anderen ähnlichen Inhalt verantwortlich. Außerdem wird der Textformatatoihrer mit einzelnen <xref:System.Windows.Media.TextFormatting.TextRun> Objekten <xref:System.Windows.Media.TextFormatting.TextLine> ausgeliefert, die der Textformatatoihrer zum Erstellen von Objekten verwendet.  
  
 Um die Virtualisierung des Textspeichers zu verarbeiten, <xref:System.Windows.Media.TextFormatting.TextSource>muss der Textspeicher von abgeleitet werden. <xref:System.Windows.Media.TextFormatting.TextSource>definiert die Methode, die der Textformatatol zum Abrufen von Textläufen aus dem Textspeicher verwendet. <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A>ist die Methode, die vom Textformatierungsformatverwendet zum Abrufen von Textläufen verwendet wird, die in der Zeilenformatierung verwendet werden. Der Aufruf <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> wird wiederholt vom Textformatformatausgeführt ausgeführt, bis eine der folgenden Bedingungen eintritt:  
  
- Eine <xref:System.Windows.Media.TextFormatting.TextEndOfLine> oder eine Unterklasse wird zurückgegeben.  
  
- Die akkumulierte Breite der Textläufe überschreitet die maximale Zeilenbreite, die entweder im Aufruf zum <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A> Erstellen des Textformataums oder beim Aufruf der Textformatatoganzmethode angegeben ist.  
  
- Eine Unicode-Newline-Sequenz, z. B. "CF", "LF" oder "CRLF", wird zurückgegeben.  
  
<a name="section4"></a>
## <a name="providing-text-runs"></a>Bereitstellen von Lauftext  
 Der wichtigste Teil des Textformatierunsprozesses ist die Interaktion zwischen Textformatierer und Textspeicher. Ihre Implementierung <xref:System.Windows.Media.TextFormatting.TextSource> von stellt den <xref:System.Windows.Media.TextFormatting.TextRun> Textformatformatmitteil mit den Objekten und den Eigenschaften bereit, mit denen der Text formatiert werden soll. Diese Interaktion wird von <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> der Methode verarbeitet, die vom Textformataton aufgerufen wird.  
  
 Die folgende Tabelle zeigt einige <xref:System.Windows.Media.TextFormatting.TextRun> der vordefinierten Objekte.  
  
|TextRun-Typ|Verwendung|  
|------------------|-----------|  
|<xref:System.Windows.Media.TextFormatting.TextCharacters>|Der spezialisierte Lauftext, der zum Übergeben einer Darstellung von Zeichensymbolen zurück an den Textformatierer verwendet wird|  
|<xref:System.Windows.Media.TextFormatting.TextEmbeddedObject>|Der spezialisierte Lauftext, der zum Bereitstellen von Inhalt verwendet wird, in dem Messungen, Treffertests und Zeichnungen komplett ausgeführt werden, z.B. eine Schaltfläche oder ein Bild im Text|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfLine>|Der spezialisierte Lauftext, der zum Kennzeichnen des Zeilenendes verwendet wird|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfParagraph>|Der spezialisierte Lauftext, der zum Kennzeichnen eines Absatzendes verwendet wird|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfSegment>|Die spezialisierte Textausführung, die verwendet wird, um das Ende eines <xref:System.Windows.Media.TextFormatting.TextModifier> Segments zu markieren, z. B. um den Bereich zu beenden, der von einer vorherigen Ausführung betroffen ist.|  
|<xref:System.Windows.Media.TextFormatting.TextHidden>|Der spezialisierte Lauftext, der verwendet wird, um eine Reihe ausgeblendeter Zeichen zu kennzeichnen|  
|<xref:System.Windows.Media.TextFormatting.TextModifier>|Der spezialisierte Lauftext, der verwendet wird, um Eigenschaften der Lauftexte in deren Bereich zu ändern. Der Bereich erstreckt sich <xref:System.Windows.Media.TextFormatting.TextEndOfSegment> auf den nächsten <xref:System.Windows.Media.TextFormatting.TextEndOfParagraph>übereinstimmenden Textlauf oder den nächsten .|  
  
 Jedes der vordefinierten <xref:System.Windows.Media.TextFormatting.TextRun> Objekte kann unterklassifiziert werden. Dadurch kann Ihre Textquelle den Textformatierer mit Lauftexten bereitstellen, die benutzerdefinierte Daten enthalten.  
  
 Im folgenden Beispiel <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> wird eine Methode veranschaulicht. Dieser Textspeicher <xref:System.Windows.Media.TextFormatting.TextRun> gibt Objekte zur Verarbeitung an den Textformatierungsobjekt zurück.  
  
 [!code-csharp[TextFormatterExample#101](~/samples/snippets/csharp/VS_Snippets_Wpf/TextFormatterExample/CSharp/CustomTextSource.cs#101)]
 [!code-vb[TextFormatterExample#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextFormatterExample/VisualBasic/CustomTextSource.vb#101)]  
  
> [!NOTE]
> In diesem Beispiel stellt der Textspeicher die gleichen Texteigenschaften für den gesamten Text bereit. Erweiterte Textspeicher müssen ihre eigene Verwaltung für Bereiche implementieren, damit einzelne Zeichen über unterschiedliche Eigenschaften verfügen können.  
  
<a name="section5"></a>
## <a name="specifying-formatting-properties"></a>Angeben von Formatierungseigenschaften  
 <xref:System.Windows.Media.TextFormatting.TextRun>Objekte werden mithilfe von Eigenschaften formatiert, die vom Textspeicher bereitgestellt werden. Diese Eigenschaften sind in <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> <xref:System.Windows.Media.TextFormatting.TextRunProperties>zwei Typen und . <xref:System.Windows.Media.TextFormatting.TextParagraphProperties>Absatz-inklusive-Eigenschaften <xref:System.Windows.TextAlignment> wie <xref:System.Windows.FlowDirection>und behandeln <xref:System.Windows.Media.TextFormatting.TextRunProperties>sind Eigenschaften, die für jeden Text, der innerhalb eines <xref:System.Windows.Media.Typeface>Absatzes ausgeführt wird, unterschiedlich sein können, z. B. Vordergrundpinsel, , und Schriftgröße. Um benutzerdefinierte Absatz- und benutzerdefinierte Textausführungseigenschaftentypen zu <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> <xref:System.Windows.Media.TextFormatting.TextRunProperties> implementieren, muss die Anwendung Klassen erstellen, die jeweils von bzw. von ihnen stammen.  
  
## <a name="see-also"></a>Weitere Informationen

- [Typografie in WPF](typography-in-wpf.md)
- [Dokumente in WPF](documents-in-wpf.md)
