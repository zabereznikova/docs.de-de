---
title: "TypeConverter und XAML | Microsoft Docs"
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
  - "Klassen, TypeConverter"
  - "TypeConverter-Klasse"
  - "XAML, TypeConverter-Klasse"
ms.assetid: f6313e4d-e89d-497d-ac87-b43511a1ae4b
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# TypeConverter und XAML
Dieses Thema beschreibt zum ersten Mal, welchem Zweck die Typkonvertierung aus einer Zeichenfolge als allgemeines XAML\-Sprachfeature dient.  In .NET Framework ist die <xref:System.ComponentModel.TypeConverter>\-Klasse Teil der Implementierung für eine verwaltete benutzerdefinierte Klasse, die als Eigenschaftswert in der XAML\-Attributverwendung eingesetzt werden kann.  Wenn Sie eine benutzerdefinierte Klasse erstellen und möchten, dass Instanzen dieser Klasse als festlegbare XAML\-Attributwerte fungieren, müssen Sie unter Umständen ein <xref:System.ComponentModel.TypeConverterAttribute> auf die Klasse anwenden, eine benutzerdefinierte <xref:System.ComponentModel.TypeConverter>\-Klasse erstellen oder beides.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
## Typkonvertierungsbegriffe  
  
### XAML und Zeichenfolgenwerte  
 Wenn Sie einen Attributwert in einer XAML\-Datei festlegen, ist der ursprüngliche Typ dieses Werts eine Zeichenfolge in reinem Text.  Auch andere Primitive, z. B. <xref:System.Double>\-Elemente, sind anfänglich Textzeichenfolgen für einen XAML\-Prozessor.  
  
 XAML\-Prozessoren benötigen zum Verarbeiten eines Attributwerts zwei Informationen.  Die erste Information ist der Werttyp der Eigenschaft, die festgelegt wird.  Jede Zeichenfolge, die einen Attributwert definiert und in XAML verarbeitet wird, muss schließlich in einen Wert dieses Typs umgewandelt oder aufgelöst werden.  Wenn es sich bei dem Wert um einen primitiven Typ handelt, der vom XAML\-Parser verstanden wird \(z. B. ein numerischer Wert\), wird eine direkte Konvertierung der Zeichenfolge versucht.  Wenn der Wert eine Enumeration ist, wird die Zeichenfolge verwendet, um diese Enumeration auf eine Namensübereinstimmung mit einer benannten Konstante zu überprüfen.  Wenn es sich bei dem Wert weder um eine Primitive, die vom Parser verstanden wird, noch um eine Enumeration handelt, muss der betreffende Typ in der Lage sein, eine Instanz des Typs oder einen Wert basierend auf einer konvertierten Zeichenfolge bereitzustellen.  Dies erfolgt durch Angabe einer Typkonverterklasse.  Der Typkonverter ist effektiv eine Hilfsklasse zum Bereitstellen von Werten einer anderen Klasse für das XAML\-Szenario und möglicherweise auch für Codeaufrufe in .NET\-Code.  
  
### Verwenden von vorhandenem Typkonvertierungsverhalten in XAML  
 Abhängig davon, wie vertraut Sie mit zugrunde liegenden XAML\-Konzepten sind, verwenden Sie möglicherweise bereits Typkonvertierungsverhalten in grundlegendem Anwendungs\-XAML, ohne es zu realisieren.  Zum Beispiel definiert WPF buchstäblich Hunderte von Eigenschaften, die einen Wert des Typs <xref:System.Windows.Point> annehmen.  Ein <xref:System.Windows.Point> ist ein Wert, der eine Koordinate in einem zweidimensionalen Koordinatenraum beschreibt, und es gibt wirklich nur zwei wichtige Eigenschaften: <xref:System.Windows.Point.X%2A> und <xref:System.Windows.Point.Y%2A>.  Wenn Sie in XAML einen Punkt angeben, geben Sie ihn als Zeichenfolge mit einem Trennzeichen \(in der Regel ein Komma\) zwischen den bereitgestellten <xref:System.Windows.Point.X%2A>\- und <xref:System.Windows.Point.Y%2A>\-Werten an.  Beispiel: `<LinearGradientBrush StartPoint="0,0" EndPoint="1,1">`.  
  
 Sogar für diesen einfachen <xref:System.Windows.Point>\-Typ und die einfache Verwendung in XAML wird ein Typkonverter eingesetzt.  In diesem Fall ist das die Klasse <xref:System.Windows.PointConverter>.  
  
 Der Typkonverter für <xref:System.Windows.Point>, der auf Klassenebene definiert ist, vereinfacht die Markupverwendungen aller Eigenschaften, die <xref:System.Windows.Point> annehmen.  Ohne Typkonverter wäre das folgende, viel ausführlichere Markup für das gleiche zuvor gezeigte Beispiel erforderlich:  
  
 `<LinearGradientBrush>`  
  
 `<LinearGradientBrush.StartPoint>`  
  
 `<Point X="0" Y="0"/>`  
  
 `</LinearGradientBrush.StartPoint>`  
  
 `<LinearGradientBrush.EndPoint>`  
  
 `<Point X="1" Y="1"/>`  
  
 `</LinearGradientBrush.EndPoint>`  
  
 `<LinearGradientBrush>`  
  
 Ob die Typkonvertierungszeichenfolge oder eine entsprechende ausführlichere Syntax verwendet wird, ist im Prinzip eine Frage des Codierungsstils  Der XAML\-Tool\-Workflow könnte auch beeinflussen, wie Werte festgelegt werden.  Einige XAML\-Tools neigen dazu, die ausführlichste Form des Markups auszugeben, da ein Roundtrip zu Designeransichten oder zum eigenen Serialisierungsmechanismus einfacher ist.  
  
 Vorhandene Typkonverter können im Allgemeinen für WPF\- und .NET Framework\-Typen ermittelt werden, indem eine Klasse \(oder Eigenschaft\) auf das Vorhandensein eines angewendeten <xref:System.ComponentModel.TypeConverterAttribute>\-Elements überprüft wird.  Dieses Attribut benennt die Klasse, die der unterstützende Typkonverter für Werte dieses Typs ist, für XAML sowie für potenzielle andere Zwecke.  
  
### Typkonverter und Markuperweiterungen  
 Markuperweiterungen und Typkonverter füllen hinsichtlich des XAML\-Prozessorverhaltens und der Szenarien, für die sie übernommen werden, orthogonale Rollen aus.  Obwohl für Markuperweiterungen Kontext verfügbar ist, wird das Typkonvertierungsverhalten von Eigenschaften, bei denen eine Markuperweiterung einen Wert bereitstellt, im Allgemeinen nicht in den Markuperweiterungsimplementierungen überprüft.  Anders ausgedrückt: Auch wenn eine Markuperweiterung eine Textzeichenfolge als `ProvideValue`\-Element zurückgibt, wird das Typkonvertierungsverhalten für diese Zeichenfolge entsprechend der Anwendung bei bestimmten Eigenschafts\- oder Eigenschaftswerttypen nicht aufgerufen. Im Allgemeinen ist der Zweck einer Markuperweiterung die Verarbeitung einer Zeichenfolge und die Rückgabe eines Objekts ohne Typkonverter.  
  
 Eine allgemeine Situation, in der eine Markuperweiterung statt einem Typkonverter erforderlich ist, ist das Erstellen eines Verweises auf ein bereits vorhandenes Objekt.  Ein zustandsloser Typkonverter könnte bestenfalls eine neue Instanz generieren, die nicht erwünscht sein könnte.  Weitere Informationen über Markuperweiterungen finden Sie unter [Markuperweiterungen und WPF\-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
### Systemeigene Typkonverter  
 In der WPF\- und der .NET Framework\-Implementierung des XAML\-Parsers gibt es bestimmte Typen, die über eine systemeigene Typkonvertierung verfügen. Dabei handelt es sich jedoch nicht um Typen, die normalerweise als Primitive angesehen werden.  Ein Beispiel für einen solchen Typ ist <xref:System.DateTime>.  Der Grund dafür liegt an der Funktionsweise von der .NET Framework\-Architektur: Der Typ <xref:System.DateTime> wird in mscorlib definiert, der grundlegendsten Bibliothek in .NET.  <xref:System.DateTime> darf kein Attribut zugeschrieben werden, das aus einer anderen Assembly stammt, die eine Abhängigkeit einführt \(<xref:System.ComponentModel.TypeConverterAttribute> stammt aus System\), sodass der übliche  Erkennungsmechanismus des Typkonverters durch Attributieren nicht unterstützt werden kann.  Stattdessen verfügt der XAML\-Parser über eine Liste mit Typen, die diese systemeigene Verarbeitung erfordern, und verarbeitet diese auf ähnliche Weise, wie die echten Primitiven verarbeitet werden.  \(Im Fall von <xref:System.DateTime> umfasst das einen Aufruf an <xref:System.DateTime.Parse%2A>.  
  
<a name="Implementing_a_Type_Converter"></a>   
## Implementieren eines Typkonverters  
  
### TypeConverter  
 Im vorherigen <xref:System.Windows.Point>\-Beispiel wurde die <xref:System.Windows.PointConverter>\-Klasse erwähnt.  Bei den .NET\-Implementierungen von XAML sind alle Typkonverter, die für XAML\-Zwecke verwendet werden, von der <xref:System.ComponentModel.TypeConverter>\-Basisklasse abgeleitete Klassen.  Die <xref:System.ComponentModel.TypeConverter>\-Klasse war in Versionen von .NET Framework vorhanden, als es noch kein XAML gab: Zu den ursprünglichen Verwendungen gehörte die Bereitstellung der Zeichenfolgenkonvertierung für Eigenschaftendialogfelder in visuellen Designern.  Für XAML wird die <xref:System.ComponentModel.TypeConverter>\-Rolle um Folgendes erweitert: Basisklasse für Konvertierungen in Zeichenfolgen und aus Zeichenfolgen, die das Analysieren eines Zeichenfolgen\-Attributwerts und möglicherweise die Rückkonvertierung eines Laufzeitwerts einer bestimmten Objekteigenschaft in eine Zeichenfolge für die Serialisierung als Attribut ermöglichen.  
  
 Das <xref:System.ComponentModel.TypeConverter>\-Element definiert vier Member, die für die Konvertierung von und in Zeichenfolgen für XAML\-Verarbeitungszwecke relevant sind:  
  
-   <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A>  
  
-   <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A>  
  
-   <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>  
  
-   <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>  
  
 Die wichtigste Methode ist <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>.  Diese Methode wandelt die Eingabezeichenfolge in den erforderlichen Objekttyp um.  Genau genommen könnte die <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>\-Methode für die Konvertierung einer viel größeren Vielzahl von Typen in den beabsichtigten Zieltyp des Konverters implementiert werden und so Zwecken dienen, die über XAML hinausgehen, z. B. die Unterstützung von Laufzeitkonvertierungen. Aber für XAML\-Zwecke ist nur der Codepfad, der eine <xref:System.String>\-Eingabe verarbeiten kann, wichtig.  
  
 Die nächste wichtigste Methode ist <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>.  Wenn eine Anwendung in eine Markupdarstellung umgewandelt wird \(wenn sie z. B. in XAML als Datei gespeichert wird\), ist die <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>\-Methode verantwortlich für die Erstellung einer Markupdarstellung.  In diesem Fall ist der Codepfad, der für XAML wichtig ist, wenn Sie einen `destinationType` von <xref:System.String> übergeben.  
  
 <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> und <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A> sind Unterstützungsmethoden, die verwendet werden, wenn ein Dienst die Funktionen der <xref:System.ComponentModel.TypeConverter>\-Implementierung abfragt.  Sie müssen diese Methoden implementieren, um für typspezifische Fälle, die von den entsprechenden Konvertierungsmethoden Ihres Konverters unterstützt werden, `true` zurückzugeben.  Für XAML\-Zwecke ist das im Allgemeinen der <xref:System.String>\-Typ.  
  
### Kulturinformationen und Typkonverter für XAML  
 Jede <xref:System.ComponentModel.TypeConverter>\-Implementierung kann ihre eigene Interpretation einer gültigen Zeichenfolge für eine Umwandlung haben und kann auch die Typbeschreibung, die als Parameter übergeben wird, verwenden oder ignorieren.  Es gibt einen wichtigen Aspekt hinsichtlich der Kultur und XAML\-Typkonvertierung.  Die Verwendung von lokalisierbaren Zeichenfolgen als Attributwerte wird von XAML vollständig unterstützt.  Aber die Verwendung dieser lokalisierbaren Zeichenfolge als Typkonvertereingabe mit bestimmten Kulturanforderungen wird nicht unterstützt, da Typkonverter für XAML\-Attributwerte ein Analyseverhalten umfassen, für das eine Sprache festgelegt sein muss, wobei die `en-US`\-Kultur verwendet wird.  Weitere Informationen über die entwicklungsspezifischen Gründe für diese Einschränkung finden Sie in der XAML\-Sprachspezifikation \([\[MS\-XAML\]](http://go.microsoft.com/fwlink/?LinkId=114525)\).  
  
 Ein Beispiel dafür, dass die Kultur ein Problem darstellen kann, ist, dass einige Kulturen ein Komma als Dezimaltrennzeichen für Zahlen verwenden.  Das führt zu einem Konflikt mit dem Verhalten vieler WPF\-XAML\-Typkonverter, die ein Komma als Trennzeichen verwenden \(basierend auf historischen Präzedenzfällen, z. B. das allgemeine X, Y\-Modell oder durch Komma getrennte Listen\).  Sogar die Übergabe einer Kultur im umgebenden XAML \(`Language` oder `xml:lang` wird auf die `sl-SI`\-Kultur festgelegt, die ein Beispiel für eine Kultur ist, die Kommas auf diese Weise für Dezimalzahlen verwendet\) löst das Problem nicht.  
  
### Implementieren von ConvertFrom  
 Die <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>\-Methode für diesen Konverter muss eine Zeichenfolge als `value`\-Parameter akzeptieren, um als <xref:System.ComponentModel.TypeConverter>\-Implementierung mit XAML\-Unterstützung verwendet werden zu können.  Wenn die Zeichenfolge in einem gültigen Format vorliegt und von der <xref:System.ComponentModel.TypeConverter>\-Implementierung umgewandelt werden kann, muss das zurückgegebene Objekt eine Umwandlung in den von der Eigenschaft erwarteten Typ unterstützen.  Andernfalls muss die <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>\-Implementierung `null` zurückgeben.  
  
 Jede <xref:System.ComponentModel.TypeConverter>\-Implementierung kann ihre eigene Interpretation einer gültigen Zeichenfolge für eine Umwandlung haben und kann auch die Typbeschreibungs\- oder Kulturkontexte, die als Parameter übergeben werden, verwenden oder ignorieren.  Die WPF XAML\-Verarbeitung übergibt jedoch unter Umständen nicht in allen Fällen Werte an den Typbeschreibungskontext und außerdem keine auf `xml:lang` basierende Kultur.  
  
> [!NOTE]
>  Verwenden Sie die geschweiften Klammerzeichen nicht als Element des Zeichenfolgenformats, insbesondere nicht {,.  Diese Zeichen sind für den Beginn und das Ende einer Markuperweiterungssequenz reserviert.  
  
### Implementieren von ConvertTo  
 <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> wird möglicherweise für die Serialisierungsunterstützung verwendet.  Die Serialisierungsunterstützung für Ihren benutzerdefinierten Typ und seinen Typkonverter durch die <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>\-Methode ist keine absolute Anforderung.  Wenn Sie jedoch ein Steuerelement implementieren oder eine Serialisierung als Teil der Features oder der Gestaltung Ihrer Klasse verwenden, sollten Sie <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> implementieren.  
  
 Um als <xref:System.ComponentModel.TypeConverter>\-Implementierung verwendet werden zu können, die XAML unterstützt, muss die <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>\-Methode für diesen Konverter eine Instanz des Typs \(oder einen Wert\) akzeptieren, der als `value`\-Parameter unterstützt wird.  Wenn der `destinationType`\-Parameter vom Typ <xref:System.String> ist, muss das zurückgegebene Objekt in <xref:System.String> umwandelbar sein.  Die zurückgegebene Zeichenfolge muss einen serialisierten Wert von `value` darstellen.  Das von Ihnen gewählte Serialisierungsformat sollte ohne bedeutenden Informationsverlust ermöglichen, den gleichen Wert zu generieren, der generiert wird, wenn diese Zeichenfolge an die <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>\-Implementierung desselben Konverters übergeben wird.  
  
 Wenn der Wert nicht serialisiert werden kann oder der Konverter die Serialisierung nicht unterstützt, muss die <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>\-Implementierung `null` zurückgeben und kann in diesem Fall eine Ausnahme ausgeben.  Wenn Sie jedoch Ausnahmen auslösen, sollten Sie melden, dass es nicht möglich ist, diese Konvertierung als Teil der <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A>\-Implementierung zu verwenden, sodass die Best Practice unterstützt wird, zuerst eine Überprüfung mit <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> durchzuführen, um Ausnahmen zu vermeiden.  
  
 Wenn der `destinationType`\-Parameter nicht vom Typ <xref:System.String> ist, können Sie eine eigene Konverterbehandlung auswählen.  In der Regel stellen Sie die Basisimplementierungsbehandlung wieder her, die in der <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> eine bestimmte Ausnahme auslöst.  
  
### Implementieren von CanConvertTo  
 Ihre <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A>\-Implementierung sollte `true` für `destinationType` vom Typ <xref:System.String> zurückgeben und andernfalls auf die Basisimplementierung zurückgreifen.  
  
### Implementieren von CanConvertFrom  
 Ihre <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A>\-Implementierung sollte `true` für `sourceType` vom Typ <xref:System.String> zurückgeben und andernfalls auf die Basisimplementierung zurückgreifen.  
  
<a name="Applying_the_TypeConverterAttribute"></a>   
## Übernehmen des TypeConverterAttribute  
 Damit der benutzerdefinierte Typkonverter als aktiver Typkonverter für eine benutzerdefinierte Klasse von einem XAML\-Prozessor verwendet werden kann, müssen Sie das [!INCLUDE[TLA#tla_netframewkattr](../../../../includes/tlasharptla-netframewkattr-md.md)] <xref:System.ComponentModel.TypeConverterAttribute> auf Ihre Klassendefinition anwenden.  Der <xref:System.ComponentModel.TypeConverterAttribute.ConverterTypeName%2A>, den Sie über das Attribut angeben, muss der Typname des benutzerdefinierten Typkonverters sein.  Bei Anwendung dieses Attributs können Zeichenfolgen eingegeben und Objektinstanzen zurückgegeben werden, wenn ein XAML\-Prozessor Werte verarbeitet, sofern der Eigenschaftentyp Ihren benutzerdefinierten Klassentyp verwendet.  
  
 Sie können auch einen Typkonverter auf Eigenschaftenbasis bereitstellen.  Anstatt ein [!INCLUDE[TLA#tla_netframewkattr](../../../../includes/tlasharptla-netframewkattr-md.md)] <xref:System.ComponentModel.TypeConverterAttribute> auf die Klassendefinition anzuwenden, sollten Sie es auf eine Eigenschaftendefinition anwenden \(die Hauptdefinition, nicht die darin enthaltenen `get`\/`set`\-Implementierungen\).  Der Typ der Eigenschaft muss dem Typ entsprechen, der von Ihrem benutzerdefinierten Typkonverter verarbeitet wird.  Bei Anwendung dieses Attributs können Zeichenfolgen verarbeitet und Objektinstanzen zurückgegeben werden, wenn ein XAML\-Prozessor Werte dieser Eigenschaft verarbeitet.  Die Typkonvertertechnik auf Eigenschaftenbasis ist vor allem dann hilfreich, wenn Sie einen Eigenschaftentyp von [!INCLUDE[TLA#tla_netframewk](../../../../includes/tlasharptla-netframewk-md.md)] oder einer anderen Bibliothek verwenden, bei dem Sie die Klassendefinition nicht steuern können und kein <xref:System.ComponentModel.TypeConverterAttribute> anwenden können.  
  
## Siehe auch  
 <xref:System.ComponentModel.TypeConverter>   
 [Übersicht über XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Markuperweiterungen und WPF\-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)   
 [Ausführliche Erläuterung der XAML\-Syntax](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)