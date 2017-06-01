---
title: "Erweiterte Textformatierung | Microsoft Docs"
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
  - "Formatieren [WPF]"
  - "Text [WPF]"
  - "Typografie, Textformatierung"
ms.assetid: f0a7986e-f5b2-485c-a27d-f8e922022212
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Erweiterte Textformatierung
Die [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] stellt einen stabilen Satz von [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] zur Verfügung, mit denen Ihrer Anwendung Text hinzugefügt werden kann.  Layout und [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)], wie z. B. <xref:System.Windows.Controls.TextBlock>, stellen allgemeine und am häufigsten verwendete Elemente für die Textdarstellung bereit.  Zeichnungs\-[!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)], wie z. B. <xref:System.Windows.Media.GlyphRunDrawing> und <xref:System.Windows.Media.FormattedText>, stellen eine Methode zum Darstellen von formatiertem Text in Zeichnungen bereit.  Auf höchster Ebene stellt [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ein erweiterbares Textformatierungsmodul bereit, mit dem jeder Aspekt der Textdarstellung gesteuert werden kann, wie zum Beispiel die Textspeicherverwaltung, Verwaltung der Textausführungsformatierung und Verwaltung von eingebetteten Objekten.  
  
 Dieses Thema bietet eine Einführung in die [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Textformatierung.  Das Hauptaugenmerk liegt in diesem Thema auf der Clientimplementierung und Verwendung des [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Textformatierungsmoduls.  
  
> [!NOTE]
>  Alle in diesem Dokument aufgeführten Codebeispiele finden Sie unter [Beispiel für die erweiterte Textformatierung](http://go.microsoft.com/fwlink/?LinkID=159965).  
  
   
  
<a name="prereq"></a>   
## Vorbereitungsmaßnahmen  
 In diesem Thema wird davon ausgegangen, dass Sie mit den [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] höherer Ebene, die für die Textdarstellung verwendet werden, vertraut sind.  Für die meisten Benutzerszenarien werden die [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] für die erweiterte Textformatierung, die in diesem Thema erläutert werden, nicht benötigt.  Eine Einführung in die verschiedenen Text\-[!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] finden Sie unter [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md).  
  
<a name="section1"></a>   
## Erweiterte Textformatierung  
 Die Textlayout\- und [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]\-Steuerelemente in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] stellen Formatierungseigenschaften zur Verfügung, mit denen Sie auf einfache Weise formatierten Text in Ihre Anwendung einbeziehen können.  Diese Steuerelemente machen eine Reihe von Eigenschaften verfügbar, mit denen die Darstellung von Text gehandhabt werden kann, einschließlich Schriftart, Größe und Farbe.  Unter normalen Umständen können diese Steuerelemente den Großteil der Textdarstellung in Ihrer Anwendung verarbeiten.  Einige erweiterte Szenarien erfordern jedoch häufig auch die Steuerung des Textspeichers neben der Textdarstellung.  Zu diesem Zweck stellt [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ein erweitertes Textformatierungsmodul bereit.  
  
 Die von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] bereitgestellten erweiterten Funktionen für die Textformatierung umfassen ein Textformatierungsmodul, einen Textspeicher, Textausführungen und Formatierungseigenschaften.  Das Textformatierungsmodul <xref:System.Windows.Media.TextFormatting.TextFormatter> erstellt Textzeilen, die für die Darstellung verwendet werden können.  Dies wird durch die Initialisierung des Zeilenformatierungsprozesses und das Aufrufen von <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A> des Textformatierungsprogramms erreicht.  Das Textformatierungsprogramm ruft Textausführungen aus dem Textspeicher ab, indem die <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A>\-Methode des Speichers aufgerufen wird.  Die <xref:System.Windows.Media.TextFormatting.TextRun>\-Objekte werden dann vom Textformatierungsprogramm in <xref:System.Windows.Media.TextFormatting.TextLine>\-Objekte umgewandelt und an die Anwendung zur Überprüfung oder Anzeige weitergegeben.  
  
<a name="section2"></a>   
## Verwenden des Textformatierungsprogramms  
 <xref:System.Windows.Media.TextFormatting.TextFormatter> ist das Textformatierungsmodul von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] und stellt Dienste zum Formatieren und Umbrechen von Textzeilen zur Verfügung.  Das Textformatierungsprogramm kann verschiedene Textzeichenformate und Absatzstile verarbeiten und bietet Unterstützung für internationale Textlayouts.  
  
 Im Gegensatz zu einer herkömmlichen Text\-[!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] interagiert der <xref:System.Windows.Media.TextFormatting.TextFormatter> mit einem Textlayoutclient über eine Reihe von Rückrufmethoden.  Hierfür ist erforderlich, dass der Client diese Methoden in einer Implementierung der <xref:System.Windows.Media.TextFormatting.TextSource>\-Klasse bereitstellt.  Im folgenden Diagramm wird die Textlayoutinteraktion zwischen der Clientanwendung und <xref:System.Windows.Media.TextFormatting.TextFormatter> veranschaulicht.  
  
 ![Diagramm des Textlayout&#45;Clients und TextFormatter](../../../../docs/framework/wpf/advanced/media/textformatter01.png "TextFormatter01")  
Interaktion zwischen Anwendung und TextFormatter  
  
 Das Textformatierungsprogramm wird zum Abrufen formatierter Textzeilen aus dem Textspeicher verwendet, wobei es sich um die Implementierung von <xref:System.Windows.Media.TextFormatting.TextSource> handelt.  Hierzu wird zunächst eine Instanz des Textformatierungsprogramms mit der <xref:System.Windows.Media.TextFormatting.TextFormatter.Create%2A>\-Methode erstellt.  Diese Methode erstellt eine Instanz des Textformatierungsprogramms und legt Werte für die maximale Zeilenhöhe und \-breite fest.  Nachdem eine Instanz des Textformatierungsprogramms erstellt wurde, wird der Zeilenerstellungsvorgang gestartet, indem die <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A>\-Methode aufgerufen wird.  <xref:System.Windows.Media.TextFormatting.TextFormatter> ruft die Text\- und Formatierungsparameter für die Textausführungen, die eine Zeile bilden, erneut aus der Textquelle ab.  
  
 Im folgenden Beispiel wird dargestellt, wie ein Textspeicher formatiert wird.  Das <xref:System.Windows.Media.TextFormatting.TextFormatter>\-Objekt wird zum Abrufen von Textzeilen aus dem Textspeicher und zum anschließenden Formatieren der Textzeilen zum Zeichnen im <xref:System.Windows.Media.DrawingContext> verwendet.  
  
 [!code-csharp[TextFormatterExample#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextFormatterExample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextFormatterExample#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextFormatterExample/VisualBasic/Window1.xaml.vb#100)]  
  
<a name="section3"></a>   
## Implementieren des Clienttextspeichers  
 Wenn Sie das Textformatierungsmodul erweitern, müssen Sie alle Aspekte des Textspeichers implementieren und verwalten.  Dies ist keine einfache Aufgabe.  Der Textspeicher ist verantwortlich für die Nachverfolgung von Textausführungseigenschaften, Absatzeigenschaften, eingebetteten Objekten und anderem ähnlichen Inhalt.  Er stellt dem Textformatierungsprogramm außerdem einzelne <xref:System.Windows.Media.TextFormatting.TextRun>\-Objekte zur Verfügung, mit dem das Textformatierungsprogramm <xref:System.Windows.Media.TextFormatting.TextLine>\-Objekte erstellt.  
  
 Um die Virtualisierung des Textspeichers zu behandeln, muss der Textspeicher von der <xref:System.Windows.Media.TextFormatting.TextSource> abgeleitet werden.  <xref:System.Windows.Media.TextFormatting.TextSource> definiert die Methode, die vom Textformatierungsprogramm verwendet wird, um Textausführungen aus dem Textspeicher abzurufen.  <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> ist die Methode, die vom Textformatierungsprogramm zum Abrufen von Textausführungen für die Zeilenformatierung verwendet wird.  Das Textformatierungsprogramm ruft <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> wiederholt auf, bis eine der folgenden Bedingungen auftritt:  
  
-   Es wird <xref:System.Windows.Media.TextFormatting.TextEndOfLine> oder eine Unterklasse zurückgegeben.  
  
-   Die kumulierte Breite von Textausführungen überschreitet die maximale Zeilenbreite, die entweder im Aufruf zum Erstellen des Textformatierungsprogramms oder im Aufruf der <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A>\-Methode des Textformatierungsprogramms festgelegt ist.  
  
-   Es wird eine [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)]\-Zeilenumbruchsequenz wie "CF", "LF" oder "CRLF" zurückgegeben.  
  
<a name="section4"></a>   
## Bereitstellen von Textausführungen  
 Kern des Textformatierungsprozesses ist das Zusammenwirken von Textformatierungsprogramm und Textspeicher.  Ihre Implementierung von <xref:System.Windows.Media.TextFormatting.TextSource> liefert dem Textformatierungsprogramm die <xref:System.Windows.Media.TextFormatting.TextRun>\-Objekte und Eigenschaften, mit denen die Textausführungen formatiert werden sollen.  Diese Interaktion wird von der <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A>\-Methode behandelt, die vom Textformatierungsprogramm aufgerufen wird.  
  
 In der folgenden Tabelle sind einige der vordefinierten <xref:System.Windows.Media.TextFormatting.TextRun>\-Objekte aufgeführt.  
  
|TextRun\-Typ|Verwendung|  
|------------------|----------------|  
|<xref:System.Windows.Media.TextFormatting.TextCharacters>|Die spezialisierte Textausführung, die verwendet wird, um eine Darstellung von Zeichensymbolen an das Textformatierungsprogramm zu übergeben.|  
|<xref:System.Windows.Media.TextFormatting.TextEmbeddedObject>|Die spezialisierte Textausführung, die zum Bereitstellen von Inhalt verwendet wird, bei dem das Messen, der Treffertest und das Zeichnen in einem Schritt durchgeführt wird, wie z. B. eine Schaltfläche oder ein Bild im Text.|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfLine>|Die spezialisierte Textausführung, die zum Markieren des Zeilenendes verwendet wird.|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfParagraph>|Die spezialisierte Textausführung, die zum Markieren des Absatzendes verwendet wird.|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfSegment>|Die spezialisierte Textausführung, die zum Markieren des Segmentendes verwendet wird, wie z. B. das Ende des Bereichs, auf den sich eine vorherige <xref:System.Windows.Media.TextFormatting.TextModifier>\-Ausführung auswirkt.|  
|<xref:System.Windows.Media.TextFormatting.TextHidden>|Die spezialisierte Textausführung, die zum Markieren eines Bereichs mit verborgenen Zeichen verwendet wird.|  
|<xref:System.Windows.Media.TextFormatting.TextModifier>|Die spezialisierte Textausführung, die zum Ändern der Eigenschaften von Textausführungen in ihrem Bereich verwendet wird.  Der Bereich erstreckt sich bis zur nächsten entsprechenden <xref:System.Windows.Media.TextFormatting.TextEndOfSegment>\-Textausführung oder zum nächsten <xref:System.Windows.Media.TextFormatting.TextEndOfParagraph>.|  
  
 Jedes vordefinierte <xref:System.Windows.Media.TextFormatting.TextRun>\-Objekt kann als Unterklasse definiert werden.  Dies ermöglicht der Textquelle, dem Textformatierungsprogramm Textausführungen bereitzustellen, die benutzerdefinierte Daten enthalten.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A>\-Methode veranschaulicht.  Dieser Textspeicher gibt <xref:System.Windows.Media.TextFormatting.TextRun>\-Objekte zur Verarbeitung an das Textformatierungsprogramm zurück.  
  
 [!code-csharp[TextFormatterExample#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextFormatterExample/CSharp/CustomTextSource.cs#101)]
 [!code-vb[TextFormatterExample#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextFormatterExample/VisualBasic/CustomTextSource.vb#101)]  
  
> [!NOTE]
>  In diesem Beispiel stellt der Textspeicher dem gesamten Text die gleichen Texteigenschaften bereit.  Erweiterte Textspeicher müssten ihre eigene Abschnittsverwaltung implementieren, um zu ermöglichen, dass einzelne Zeichen über verschiedene Eigenschaften verfügen können.  
  
<a name="section5"></a>   
## Festlegen von Formatierungseigenschaften  
 <xref:System.Windows.Media.TextFormatting.TextRun>\-Objekte werden anhand der vom Textspeicher bereitgestellten Eigenschaften formatiert.  Es gibt zwei Arten dieser Eigenschaften: <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> und <xref:System.Windows.Media.TextFormatting.TextRunProperties>.  <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> verarbeiten nur auf Abschnitte bezogene Eigenschaften wie <xref:System.Windows.TextAlignment> und <xref:System.Windows.FlowDirection>.  <xref:System.Windows.Media.TextFormatting.TextRunProperties> sind Eigenschaften, die sich für jede Textausführung in einem Abschnitt unterscheiden können, wie zum Beispiel der Vordergrundpinsel, <xref:System.Windows.Media.Typeface> und Schriftgröße.  Um benutzerdefinierte Absatz\- und Textausführungs\-Eigenschaftentypen erstellen zu können, muss Ihre Anwendung Klassen erstellen, die sich von <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> bzw. <xref:System.Windows.Media.TextFormatting.TextRunProperties> ableiten.  
  
## Siehe auch  
 [Typografie in WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)   
 [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)