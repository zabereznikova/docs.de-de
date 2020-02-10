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
ms.openlocfilehash: 26ee3c2b8a431200c3dc04130deb2247b6c1446d
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095241"
---
# <a name="advanced-text-formatting"></a>Erweiterte Textformatierung
Windows Presentation Foundation (WPF) bietet einen robusten Satz von APIs zum Einschließen von Text in Ihre Anwendung. Layout-und [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]-APIs, z. b. <xref:System.Windows.Controls.TextBlock>, stellen die am häufigsten verwendeten und allgemeinen Elemente für die Textpräsentation bereit. Das Zeichnen von APIs, z. b. <xref:System.Windows.Media.GlyphRunDrawing> und <xref:System.Windows.Media.FormattedText>, bietet eine Möglichkeit, formatierten Text in Zeichnungen einzubeziehen. Auf der höchsten Ebene bietet WPF eine erweiterbare Textformatierungs-Engine, mit der jeder Aspekt der Textpräsentation gesteuert werden kann, z. b. die Verwaltung von Text speichern, die Formatierung von Text Lauf Formaten und die eingebettete Objekt Verwaltung.  
  
 Dieses Thema enthält eine Einführung in die WPF-Textformatierung. Er konzentriert sich auf die Client Implementierung und die Verwendung der WPF-Textformatierungs-Engine.  
  
> [!NOTE]
> Alle Codebeispiele in diesem Dokument finden Sie im Beispiel für die [Erweiterte Text Formatierung](https://github.com/Microsoft/WPF-Samples/tree/master/PerMonitorDPI/TextFormatting).  

<a name="prereq"></a>   
## <a name="prerequisites"></a>Voraussetzungen  
 In diesem Thema wird davon ausgegangen, dass Sie mit den APIs auf höherer Ebene vertraut sind, die zur Textpräsentation verwendet werden In den meisten Benutzer Szenarien sind die in diesem Thema beschriebenen erweiterten Text Formatierungs-APIs nicht erforderlich. Eine Einführung in die verschiedenen Text-APIs finden Sie unter [Dokumente in WPF](documents-in-wpf.md).  
  
<a name="section1"></a>   
## <a name="advanced-text-formatting"></a>Erweiterte Textformatierung  
 Das Textlayout und [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Steuerelemente in WPF bieten Formatierungs Eigenschaften, mit denen Sie formatierten Text problemlos in Ihre Anwendung einschließen können. Diese Steuerelemente bieten eine Reihe von Eigenschaften, um die Darstellung von Text zu bearbeiten, u.a. dessen Schriftart, Größe und Farbe. Unter normalen Umständen können diese Steuerelemente den Großteil der Textdarstellung in Ihrer Anwendung behandeln. Einige erweiterten Szenarios erfordern jedoch das Steuerelement des Textspeichers sowie die Textdarstellung. WPF stellt hierfür eine erweiterbare Textformatierungs-Engine bereit.  
  
 Die in WPF gefundenen erweiterten Text Formatierungsfunktionen bestehen aus einer Textformatierungs-Engine, einem Text Speicher, Text Ausführungen und Formatierungs Eigenschaften. Die Textformatierungs-Engine, <xref:System.Windows.Media.TextFormatting.TextFormatter>, erstellt Textzeilen, die für die Darstellung verwendet werden sollen. Dies wird erreicht, indem der Zeilen Formatierungsprozess initiiert und die <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A>des textformatters aufgerufen wird. Der Textformatierer Ruft Text Ausführungen aus dem Text Speicher ab, indem er die <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A>-Methode des Stores aufruft. Die <xref:System.Windows.Media.TextFormatting.TextRun> Objekte werden dann vom Textformatierer in <xref:System.Windows.Media.TextFormatting.TextLine> Objekten gebildet und für die Überprüfung oder Anzeige an die Anwendung übergeben.  
  
<a name="section2"></a>   
## <a name="using-the-text-formatter"></a>Verwendung des Textformatierers  
 <xref:System.Windows.Media.TextFormatting.TextFormatter> ist die WPF-Textformatierungs-Engine und stellt Dienste zum Formatieren und Abbrechen von Textzeilen bereit. Der Textformatierer kann unterschiedliche Textzeichenformate und Absatzformatvorlagen verarbeiten und enthält Unterstützung für internationales Textlayout.  
  
 Im Gegensatz zu einer herkömmlichen Text-API interagiert der <xref:System.Windows.Media.TextFormatting.TextFormatter> mit einem Textlayoutclient durch eine Reihe von Rückruf Methoden. Der Client muss diese Methoden in einer Implementierung der <xref:System.Windows.Media.TextFormatting.TextSource>-Klasse bereitstellen. Das folgende Diagramm veranschaulicht die Text Layout-Interaktion zwischen der Client Anwendung und <xref:System.Windows.Media.TextFormatting.TextFormatter>.  
  
 ![Diagramm des Textlayout-Clients und TextFormatter](./media/advanced-text-formatting/text-layout-textformatter-interaction.png)  
  
 Der Textformatierer wird verwendet, um formatierte Textzeilen aus dem Text Speicher abzurufen, bei dem es sich um eine Implementierung von <xref:System.Windows.Media.TextFormatting.TextSource>handelt. Dies geschieht, indem zuerst eine Instanz des textformatierers mithilfe der <xref:System.Windows.Media.TextFormatting.TextFormatter.Create%2A>-Methode erstellt wird. Diese Methode erstellt eine Instanz des Textformatierungsprogramms und legt die maximalen Werte für Zeilenhöhe und -breite fest. Sobald eine Instanz des textformatierers erstellt wird, wird der Zeilen Erstellungs Vorgang durch Aufrufen der <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A>-Methode gestartet. <xref:System.Windows.Media.TextFormatting.TextFormatter> Ruft die Text Quelle zurück, um die Text-und Formatierungs Parameter für die Ausführungen von Text abzurufen, die eine Linie bilden.  
  
 Im folgenden Beispiel wird der Formatierungsprozess eines Textspeichers gezeigt. Das <xref:System.Windows.Media.TextFormatting.TextFormatter>-Objekt wird verwendet, um Textzeilen aus dem Text Speicher abzurufen und anschließend die Textzeile für das Zeichnen in den <xref:System.Windows.Media.DrawingContext>zu formatieren.  
  
 [!code-csharp[TextFormatterExample#100](~/samples/snippets/csharp/VS_Snippets_Wpf/TextFormatterExample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextFormatterExample#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextFormatterExample/VisualBasic/Window1.xaml.vb#100)]  
  
<a name="section3"></a>   
## <a name="implementing-the-client-text-store"></a>Implementieren des Clienttextspeichers  
 Wenn Sie die Textformatierungs-Engine erweitern, müssen Sie alle Aspekte des Textspeichers implementieren und verwalten. Dies ist keine einfache Aufgabe. Der Textspeicher ist für die Nachverfolgung von Lauftexteigenschaften, Absatzeigenschaften, für das Einbetten von Objekten und anderen ähnlichen Inhalt verantwortlich. Außerdem wird der Textformatierer mit einzelnen <xref:System.Windows.Media.TextFormatting.TextRun> Objekten bereitstellt, die der Textformatierer zum Erstellen von <xref:System.Windows.Media.TextFormatting.TextLine> Objekten verwendet.  
  
 Um die Virtualisierung des Text Stores zu verarbeiten, muss der Text Speicher von <xref:System.Windows.Media.TextFormatting.TextSource>abgeleitet werden. <xref:System.Windows.Media.TextFormatting.TextSource> definiert die Methode, die vom Textformatierer zum Abrufen von Text Ausführungen aus dem Text Speicher verwendet wird. <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> ist die Methode, die vom Textformatierer zum Abrufen von in der Zeilen Formatierung verwendeten Text Ausführungen verwendet wird. Der <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A>-Aufrufe wird vom Textformatierer wiederholt ausgeführt, bis eine der folgenden Bedingungen zutrifft:  
  
- Eine <xref:System.Windows.Media.TextFormatting.TextEndOfLine> oder eine Unterklasse wird zurückgegeben.  
  
- Die akkumulierte Breite von Textläufen überschreitet die maximale Zeilenbreite, die entweder im-Befehl zum Erstellen des textformatierers oder des Aufrufes der <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A>-Methode des textformatierers angegeben wurde.  
  
- Eine Unicode-Zeilenvorschub Sequenz, z. b. "CF", "LF" oder "CRLF", wird zurückgegeben.  
  
<a name="section4"></a>   
## <a name="providing-text-runs"></a>Bereitstellen von Lauftext  
 Der wichtigste Teil des Textformatierunsprozesses ist die Interaktion zwischen Textformatierer und Textspeicher. Bei der Implementierung von <xref:System.Windows.Media.TextFormatting.TextSource> wird der Textformatierer mit den <xref:System.Windows.Media.TextFormatting.TextRun> Objekten und den Eigenschaften, mit denen die Textläufe formatiert werden sollen, bereitstellt. Diese Interaktion wird durch die <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A>-Methode behandelt, die vom Textformatierer aufgerufen wird.  
  
 In der folgenden Tabelle werden einige der vordefinierten <xref:System.Windows.Media.TextFormatting.TextRun> Objekte gezeigt.  
  
|TextRun-Typ|Verwendung|  
|------------------|-----------|  
|<xref:System.Windows.Media.TextFormatting.TextCharacters>|Der spezialisierte Lauftext, der zum Übergeben einer Darstellung von Zeichensymbolen zurück an den Textformatierer verwendet wird|  
|<xref:System.Windows.Media.TextFormatting.TextEmbeddedObject>|Der spezialisierte Lauftext, der zum Bereitstellen von Inhalt verwendet wird, in dem Messungen, Treffertests und Zeichnungen komplett ausgeführt werden, z.B. eine Schaltfläche oder ein Bild im Text|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfLine>|Der spezialisierte Lauftext, der zum Kennzeichnen des Zeilenendes verwendet wird|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfParagraph>|Der spezialisierte Lauftext, der zum Kennzeichnen eines Absatzendes verwendet wird|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfSegment>|Der spezialisierte Lauftext, der zum Kennzeichnen des Endes eines Segments verwendet wird, z. b. zum Beenden des Bereichs, der von einer vorherigen <xref:System.Windows.Media.TextFormatting.TextModifier> ausgeführt wird.|  
|<xref:System.Windows.Media.TextFormatting.TextHidden>|Der spezialisierte Lauftext, der verwendet wird, um eine Reihe ausgeblendeter Zeichen zu kennzeichnen|  
|<xref:System.Windows.Media.TextFormatting.TextModifier>|Der spezialisierte Lauftext, der verwendet wird, um Eigenschaften der Lauftexte in deren Bereich zu ändern. Der Bereich erstreckt sich auf den nächsten übereinstimmenden <xref:System.Windows.Media.TextFormatting.TextEndOfSegment> Textlauf oder den nächsten <xref:System.Windows.Media.TextFormatting.TextEndOfParagraph>.|  
  
 Jedes der vordefinierten <xref:System.Windows.Media.TextFormatting.TextRun>-Objekte kann unter klassifiziert werden. Dadurch kann Ihre Textquelle den Textformatierer mit Lauftexten bereitstellen, die benutzerdefinierte Daten enthalten.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A>-Methode veranschaulicht. Dieser Text Speicher gibt <xref:System.Windows.Media.TextFormatting.TextRun> Objekte zur Verarbeitung an den Textformatierer zurück.  
  
 [!code-csharp[TextFormatterExample#101](~/samples/snippets/csharp/VS_Snippets_Wpf/TextFormatterExample/CSharp/CustomTextSource.cs#101)]
 [!code-vb[TextFormatterExample#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextFormatterExample/VisualBasic/CustomTextSource.vb#101)]  
  
> [!NOTE]
> In diesem Beispiel stellt der Textspeicher die gleichen Texteigenschaften für den gesamten Text bereit. Erweiterte Textspeicher müssen ihre eigene Verwaltung für Bereiche implementieren, damit einzelne Zeichen über unterschiedliche Eigenschaften verfügen können.  
  
<a name="section5"></a>   
## <a name="specifying-formatting-properties"></a>Angeben von Formatierungseigenschaften  
 <xref:System.Windows.Media.TextFormatting.TextRun> Objekte werden mithilfe von Eigenschaften formatiert, die vom Text Speicher bereitgestellt werden. Diese Eigenschaften sind in zwei Typen enthalten: <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> und <xref:System.Windows.Media.TextFormatting.TextRunProperties>. <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> handle-Inklusions Eigenschaften wie <xref:System.Windows.TextAlignment> und <xref:System.Windows.FlowDirection>verarbeiten. <xref:System.Windows.Media.TextFormatting.TextRunProperties> sind Eigenschaften, die für jeden innerhalb eines Absatzes ausgeführten Text unterschiedlich sein können, z. b. Vordergrund Pinsel, <xref:System.Windows.Media.Typeface>und Schrift Grad. Um benutzerdefinierte Absatz-und benutzerdefinierte Text Lauf Eigenschafts Typen zu implementieren, muss Ihre Anwendung Klassen erstellen, die von <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> bzw. <xref:System.Windows.Media.TextFormatting.TextRunProperties> abgeleitet werden.  
  
## <a name="see-also"></a>Weitere Informationen

- [Typografie in WPF](typography-in-wpf.md)
- [Dokumente in WPF](documents-in-wpf.md)
