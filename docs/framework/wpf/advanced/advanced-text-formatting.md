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
ms.openlocfilehash: 469c62691ff38a8c5a01bec3ddfd7b324bab7eca
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969068"
---
# <a name="advanced-text-formatting"></a>Erweiterte Textformatierung
Der Windows Presentation Foundation (WPF) bietet einen robusten Satz von APIs zum Einschließen von Text in Ihre Anwendung. Layout und [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]APIs, <xref:System.Windows.Controls.TextBlock>wie z. b., stellen die gängigsten und allgemeineren Verwendungs Elemente für die Textpräsentation bereit. Das Zeichnen von APIs, <xref:System.Windows.Media.GlyphRunDrawing> wie <xref:System.Windows.Media.FormattedText>z. b. und, bietet eine Möglichkeit, formatierten Text in Zeichnungen einzubeziehen. Auf der höchsten Ebene [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] bietet eine erweiterbare Textformatierungs-Engine, mit der jeder Aspekt der Textpräsentation gesteuert werden kann, z. b. die Verwaltung von Text speichern, die Formatierung von Text Lauf Formaten und die eingebettete Objekt Verwaltung.  
  
 Dieses Thema enthält eine Einführung in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] die Textformatierung. Er konzentriert sich auf die Client Implementierung und die [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Verwendung der Textformatierungs-Engine.  
  
> [!NOTE]
> Alle Codebeispiele in diesem Dokument finden Sie im Beispiel für die [Erweiterte Text Formatierung](https://go.microsoft.com/fwlink/?LinkID=159965).  

<a name="prereq"></a>   
## <a name="prerequisites"></a>Erforderliche Komponenten  
 In diesem Thema wird davon ausgegangen, dass Sie mit den APIs auf höherer Ebene vertraut sind, die zur Textpräsentation verwendet werden In den meisten Benutzer Szenarien sind die in diesem Thema beschriebenen erweiterten Text Formatierungs-APIs nicht erforderlich. Eine Einführung in die verschiedenen Text-APIs finden Sie unter [Dokumente in WPF](documents-in-wpf.md).  
  
<a name="section1"></a>   
## <a name="advanced-text-formatting"></a>Erweiterte Textformatierung  
 Das Text Layout und [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] die Steuer [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Elemente in bieten Formatierungs Eigenschaften, mit denen Sie formatierten Text problemlos in Ihre Anwendung einschließen können. Diese Steuerelemente bieten eine Reihe von Eigenschaften, um die Darstellung von Text zu bearbeiten, u.a. dessen Schriftart, Größe und Farbe. Unter normalen Umständen können diese Steuerelemente den Großteil der Textdarstellung in Ihrer Anwendung behandeln. Einige erweiterten Szenarios erfordern jedoch das Steuerelement des Textspeichers sowie die Textdarstellung. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] stellt eine erweiterbare Textformatierungs-Engine für diesen Zweck bereit.  
  
 Die in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] gefundenen erweiterten Text Formatierungsfunktionen bestehen aus einer Textformatierungs-Engine, einem Text Speicher, Text Ausführungen und Formatierungs Eigenschaften. Die Text Formatierungs- <xref:System.Windows.Media.TextFormatting.TextFormatter>Engine erstellt Textzeilen, die für die Darstellung verwendet werden sollen. Dies wird erreicht, indem der Zeilen Formatierungsprozess initiiert und der Text Formatierer <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A>aufgerufen wird. Der Textformatierer Ruft Text Ausführungen aus dem Text Speicher ab, indem er die- <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> Methode des Stores aufruft. Die <xref:System.Windows.Media.TextFormatting.TextRun> Objekte werden dann vom Textformatierer in <xref:System.Windows.Media.TextFormatting.TextLine> Objekte gebildet und zur Überprüfung oder Anzeige an die Anwendung übergeben.  
  
<a name="section2"></a>   
## <a name="using-the-text-formatter"></a>Verwendung des Textformatierers  
 <xref:System.Windows.Media.TextFormatting.TextFormatter>ist die [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Textformatierungs-Engine und stellt Dienste zum Formatieren und Abbrechen von Textzeilen bereit. Der Textformatierer kann unterschiedliche Textzeichenformate und Absatzformatvorlagen verarbeiten und enthält Unterstützung für internationales Textlayout.  
  
 Im Gegensatz zu einer herkömmlichen Text- <xref:System.Windows.Media.TextFormatting.TextFormatter> API interagiert die mit einem Textlayoutclient über einen Satz von Rückruf Methoden. Der Client muss diese Methoden in einer Implementierung der <xref:System.Windows.Media.TextFormatting.TextSource> -Klasse bereitstellen. Das folgende Diagramm veranschaulicht die Text Layout-Interaktion zwischen der Client Anwendung <xref:System.Windows.Media.TextFormatting.TextFormatter>und.  
  
 ![Diagramm des Textlayout-Clients und TextFormatter](./media/advanced-text-formatting/text-layout-textformatter-interaction.png)  
  
 Der Textformatierer wird verwendet, um formatierte Textzeilen aus dem Text Speicher abzurufen, bei dem es <xref:System.Windows.Media.TextFormatting.TextSource>sich um eine Implementierung von handelt. Dies geschieht, indem zuerst mithilfe der <xref:System.Windows.Media.TextFormatting.TextFormatter.Create%2A> -Methode eine Instanz des textformatierers erstellt wird. Diese Methode erstellt eine Instanz des Textformatierungsprogramms und legt die maximalen Werte für Zeilenhöhe und -breite fest. Sobald eine Instanz des textformatierers erstellt wird, wird der Zeilen Erstellungs Vorgang durch Aufrufen der <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A> -Methode gestartet. <xref:System.Windows.Media.TextFormatting.TextFormatter>Ruft die Text Quelle zurück, um die Text-und Formatierungs Parameter für die Ausführungen von Text abzurufen, die eine Linie bilden.  
  
 Im folgenden Beispiel wird der Formatierungsprozess eines Textspeichers gezeigt. Das <xref:System.Windows.Media.TextFormatting.TextFormatter> -Objekt wird verwendet, um Textzeilen aus dem Text Speicher abzurufen und anschließend die Textzeile für das <xref:System.Windows.Media.DrawingContext>zeichnen in zu formatieren.  
  
 [!code-csharp[TextFormatterExample#100](~/samples/snippets/csharp/VS_Snippets_Wpf/TextFormatterExample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextFormatterExample#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextFormatterExample/VisualBasic/Window1.xaml.vb#100)]  
  
<a name="section3"></a>   
## <a name="implementing-the-client-text-store"></a>Implementieren des Clienttextspeichers  
 Wenn Sie die Textformatierungs-Engine erweitern, müssen Sie alle Aspekte des Textspeichers implementieren und verwalten. Dies ist keine einfache Aufgabe. Der Textspeicher ist für die Nachverfolgung von Lauftexteigenschaften, Absatzeigenschaften, für das Einbetten von Objekten und anderen ähnlichen Inhalt verantwortlich. Außerdem wird der Textformatierer mit einzelnen <xref:System.Windows.Media.TextFormatting.TextRun> Objekten bereitstellt, die der Textformatierer zum Erstellen <xref:System.Windows.Media.TextFormatting.TextLine> von-Objekten verwendet.  
  
 Um die Virtualisierung des Text Stores zu verarbeiten, muss der Text Speicher von <xref:System.Windows.Media.TextFormatting.TextSource>abgeleitet werden. <xref:System.Windows.Media.TextFormatting.TextSource>definiert die Methode, die der Textformatierer verwendet, um Textläufe aus dem Text Speicher abzurufen. <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A>die vom Textformatierer verwendete Methode zum Abrufen von Textläufen, die bei der Zeilen Formatierung verwendet werden. Der-Vorgang <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> wird vom Textformatierer wiederholt ausgeführt, bis eine der folgenden Bedingungen zutrifft:  
  
- Eine <xref:System.Windows.Media.TextFormatting.TextEndOfLine> -oder eine-Unterklasse wird zurückgegeben.  
  
- Die akkumulierte Breite von Textläufen überschreitet die maximale Linienstärke, die entweder im-Befehl zum Erstellen des textformatierers oder des Aufrufes der-Methode des textformatierers <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A> angegeben wurde.  
  
- Eine [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] Zeilenvorschub Sequenz, z. b. "CF", "LF" oder "CRLF", wird zurückgegeben.  
  
<a name="section4"></a>   
## <a name="providing-text-runs"></a>Bereitstellen von Lauftext  
 Der wichtigste Teil des Textformatierunsprozesses ist die Interaktion zwischen Textformatierer und Textspeicher. Ihre Implementierung von <xref:System.Windows.Media.TextFormatting.TextSource> stellt dem Textformatierer <xref:System.Windows.Media.TextFormatting.TextRun> die-Objekte und die-Eigenschaften zur Verfügung, mit denen die Textläufe formatiert werden. Diese Interaktion wird von der <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> -Methode behandelt, die vom Textformatierer aufgerufen wird.  
  
 In der folgenden Tabelle werden einige der vordefinierten <xref:System.Windows.Media.TextFormatting.TextRun> Objekte gezeigt.  
  
|TextRun-Typ|Verwendung|  
|------------------|-----------|  
|<xref:System.Windows.Media.TextFormatting.TextCharacters>|Der spezialisierte Lauftext, der zum Übergeben einer Darstellung von Zeichensymbolen zurück an den Textformatierer verwendet wird|  
|<xref:System.Windows.Media.TextFormatting.TextEmbeddedObject>|Der spezialisierte Lauftext, der zum Bereitstellen von Inhalt verwendet wird, in dem Messungen, Treffertests und Zeichnungen komplett ausgeführt werden, z.B. eine Schaltfläche oder ein Bild im Text|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfLine>|Der spezialisierte Lauftext, der zum Kennzeichnen des Zeilenendes verwendet wird|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfParagraph>|Der spezialisierte Lauftext, der zum Kennzeichnen eines Absatzendes verwendet wird|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfSegment>|Der spezialisierte Lauftext, der verwendet wird, um das Ende eines Segments zu markieren, z. b., um <xref:System.Windows.Media.TextFormatting.TextModifier> den von einer vorherigen Testlauf betroffenen Bereich zu beenden.|  
|<xref:System.Windows.Media.TextFormatting.TextHidden>|Der spezialisierte Lauftext, der verwendet wird, um eine Reihe ausgeblendeter Zeichen zu kennzeichnen|  
|<xref:System.Windows.Media.TextFormatting.TextModifier>|Der spezialisierte Lauftext, der verwendet wird, um Eigenschaften der Lauftexte in deren Bereich zu ändern. Der Bereich erstreckt sich auf den nächsten <xref:System.Windows.Media.TextFormatting.TextEndOfSegment> übereinstimmenden Textlauf oder <xref:System.Windows.Media.TextFormatting.TextEndOfParagraph>den nächsten.|  
  
 Jedes der vordefinierten <xref:System.Windows.Media.TextFormatting.TextRun> Objekte kann unter klassifiziert werden. Dadurch kann Ihre Textquelle den Textformatierer mit Lauftexten bereitstellen, die benutzerdefinierte Daten enthalten.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> -Methode veranschaulicht. Dieser Text Speicher gibt <xref:System.Windows.Media.TextFormatting.TextRun> Objekte zur Verarbeitung an den Textformatierer zurück.  
  
 [!code-csharp[TextFormatterExample#101](~/samples/snippets/csharp/VS_Snippets_Wpf/TextFormatterExample/CSharp/CustomTextSource.cs#101)]
 [!code-vb[TextFormatterExample#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextFormatterExample/VisualBasic/CustomTextSource.vb#101)]  
  
> [!NOTE]
> In diesem Beispiel stellt der Textspeicher die gleichen Texteigenschaften für den gesamten Text bereit. Erweiterte Textspeicher müssen ihre eigene Verwaltung für Bereiche implementieren, damit einzelne Zeichen über unterschiedliche Eigenschaften verfügen können.  
  
<a name="section5"></a>   
## <a name="specifying-formatting-properties"></a>Angeben von Formatierungseigenschaften  
 <xref:System.Windows.Media.TextFormatting.TextRun>-Objekte werden mithilfe von Eigenschaften formatiert, die vom Text Speicher bereitgestellt werden. Diese Eigenschaften sind in zwei Typen enthalten <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> : <xref:System.Windows.Media.TextFormatting.TextRunProperties>und. <xref:System.Windows.Media.TextFormatting.TextParagraphProperties>behandeln Sie inklusive Absatz Eigenschaften, <xref:System.Windows.TextAlignment> z <xref:System.Windows.FlowDirection>. b. und. <xref:System.Windows.Media.TextFormatting.TextRunProperties>sind Eigenschaften, die für jeden innerhalb eines Absatzes ausgeführten Text unterschiedlich sein können, z. <xref:System.Windows.Media.Typeface>b. Vordergrund Pinsel, und Schrift Grad. Um benutzerdefinierte Absatz-und benutzerdefinierte Text Lauf Eigenschafts Typen zu implementieren, muss Ihre Anwendung <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> Klassen <xref:System.Windows.Media.TextFormatting.TextRunProperties> erstellen, die von bzw. abgeleitet werden.  
  
## <a name="see-also"></a>Siehe auch

- [Typografie in WPF](typography-in-wpf.md)
- [Dokumente in WPF](documents-in-wpf.md)
