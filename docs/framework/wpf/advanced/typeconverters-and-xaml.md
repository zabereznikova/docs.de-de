---
title: TypeConverter und XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], TypeConverter class
ms.assetid: f6313e4d-e89d-497d-ac87-b43511a1ae4b
ms.openlocfilehash: ec6eaadae1dd7a7db84538c24e396a14db1a65a4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59164986"
---
# <a name="typeconverters-and-xaml"></a>TypeConverter und XAML
In diesem Thema wird der Zweck der Typkonvertierung aus einer Zeichenfolge in eine allgemeinere Funktion der XAML-Sprache erläutert. In .NET Framework die <xref:System.ComponentModel.TypeConverter> Klasse einen bestimmten Zweck dient, als Teil der Implementierung für eine verwaltete benutzerdefinierte Klasse, die als Eigenschaftswert in der XAML-Attributverwendung verwendet werden kann. Wenn Sie eine benutzerdefinierte Klasse schreiben und Instanzen dieser Klasse als festlegbare XAML-Attributwerte verwendet werden sollen, müssen Sie möglicherweise Anwenden einer <xref:System.ComponentModel.TypeConverterAttribute> in Ihrer Klasse schreiben Sie eine benutzerdefinierte <xref:System.ComponentModel.TypeConverter> Klasse oder beides.  

## <a name="type-conversion-concepts"></a>Typkonvertierungskonzepte  
  
### <a name="xaml-and-string-values"></a>XAML- und Zeichenfolgenwerte  
 Wenn Sie einen Attributwert in einer XAML-Datei festlegen, ist der ursprüngliche Typ dieses Werts eine Zeichenfolge in reinem Text. Auch andere Primitive wie z. B. <xref:System.Double> sind anfänglich Textzeichenfolgen für einen XAML-Prozessor.  
  
 Ein XAML-Prozessor benötigt zwei Angaben, um einen Attributwert zu verarbeiten. Die erste Angabe ist der Werttyp der Eigenschaft, die festgelegt wird. Jede Zeichenfolge, die einen Attributwert definiert, und in XAML verarbeitet wird, muss schließlich umgewandelt werden oder zu einem Wert dieses Typs aufgelöst werden. Wenn es sich beim Wert um einen Primitiv handelt, den der XAML-Parser versteht (beispielsweise ein numerischer Wert), wird versucht, eine direkte Konvertierung der Zeichenfolge vorzunehmen. Wenn es sich bei dem Wert um eine Enumeration handelt, wird mithilfe der Zeichenfolge nach einer Namensübereinstimmung mit einer benannten Konstante in dieser Enumeration gesucht. Wenn es sich beim Wert weder um einen primitiven Typ handelt, den der Parser versteht, noch um eine Enumeration, muss der zutreffende Typ einen Typ oder Wert bereitstellen können, der auf einer konvertierten Zeichenfolge beruht. Dies erfolgt durch Angabe einer Typkonverterklasse. Der Typkonverter ist eine Hilfsklasse zum Bereitstellen von Werten einer anderen Klasse im XAML-Szenario und möglicherweise auch für Codeaufrufe in .NET-Code.  
  
### <a name="using-existing-type-conversion-behavior-in-xaml"></a>Verwenden von vorhandenem Typkonvertierungsverhalten in XAML  
 Je nach Ihren Vorkenntnissen der zugrunde liegenden XAML-Konzepte verwenden Sie möglicherweise bereits das Typkonvertierungsverhalten in der grundlegenden XAML-Anwendung, ohne es zu wissen. WPF definiert z.B. buchstäblich Hunderte von Eigenschaften, die einen Wert vom Typ akzeptieren <xref:System.Windows.Point>. Ein <xref:System.Windows.Point> ist ein Wert, der eine Koordinate in einem zweidimensionalen Koordinatenraum beschreibt, und es eigentlich nur zwei wichtige Eigenschaften hat: <xref:System.Windows.Point.X%2A> und <xref:System.Windows.Point.Y%2A>. Wenn Sie einen Punkt in XAML angeben, geben Sie ihn als eine Zeichenfolge mit einem Trennzeichen (in der Regel ein Komma) zwischen den <xref:System.Windows.Point.X%2A> und <xref:System.Windows.Point.Y%2A> Werte, die Sie bereitstellen. Beispiel: `<LinearGradientBrush StartPoint="0,0" EndPoint="1,1"/>`.  
  
 Auch dieser einfache Typ von <xref:System.Windows.Point> und dessen einfache Verwendung in XAML erfordern einen Typkonverter. In diesem Fall ist, die die Klasse <xref:System.Windows.PointConverter>.  
  
 Der Typkonverter für <xref:System.Windows.Point> definiert die Klasse auf optimiert die Verwendungsmöglichkeiten von Markup von allen Eigenschaften, die annehmen <xref:System.Windows.Point>. Ohne Typkonverter benötigen Sie das folgende, viel ausführlichere Markup für dasselbe zuvor gezeigte Beispiel:  

```xaml
<LinearGradientBrush>
  <LinearGradientBrush.StartPoint>
    <Point X="0" Y="0"/>
  </LinearGradientBrush.StartPoint>
  <LinearGradientBrush.EndPoint>
    <Point X="1" Y="1"/>
  </LinearGradientBrush.EndPoint>
</LinearGradientBrush>
 ```
  
 Die Verwendung der Zeichenfolge für die Typkonvertierung oder die einer ausführlicheren entsprechenden Syntax ist eine Stilfrage beim Programmieren. Der XAML-Tool-Workflow könnte auch beeinflussen, wie Werte festgelegt werden. Einige XAML-Tools neigen dazu, die ausführlichste Form von Markup auszugeben, da ein Roundtrip zu Designeransichten oder zum eigenen Serialisierungsmechanismus einfacher ist.  
  
 Vorhandenen Typkonverter können in der Regel auf WPF- und .NET Framework-Typen ermittelt werden, durch Prüfen auf eine Klasse (oder Eigenschaft) das Vorhandensein einer angewendeten <xref:System.ComponentModel.TypeConverterAttribute>. Dieses Attribut benennt die Klasse, die den unterstützenden Typkonverter für Werte dieses Typs darstellt, für XAML-Zwecke sowie für mögliche andere Zwecke.  
  
### <a name="type-converters-and-markup-extensions"></a>Typkonverter und Markuperweiterungen  
 Markuperweiterungen und Typkonverter füllen orthogonale Rollen in Bezug auf das Verhalten des XAML-Prozessors und die Szenarios, auf die sie auf angewendet werden. Obwohl der Kontext für die Verwendung von Markuperweiterungen verfügbar ist, wird das Typkonvertierungsverhalten von Eigenschaften, bei denen eine Markuperweiterung einen Wert bereitstellt, in der Regel nicht in den Implementierungen der Markuperweiterung überprüft. Das heißt, auch wenn eine Markuperweiterung eine Textzeichenfolge als zurückgibt seine `ProvideValue` auszugeben, Typkonvertierungsverhalten für diese Zeichenfolge entsprechend der auf eine bestimmte Eigenschaft oder der Werttyp der Eigenschaft angewendet wird nicht aufgerufen, in der Regel wird des Zwecks einer Markuperweiterung an Prozess ein Zeichenfolge und ein Objekt ohne beteiligten Typkonverter zurück.  
  
 Eine allgemeine Situation, in der eine Markuperweiterung statt einem Typkonverter erforderlich ist, besteht im Erstellen eines Verweises auf ein vorhandenes Objekt. Ein zustandsloser Typkonverter könnte bestenfalls nur eine neue Instanz genieren, die möglicherweise nicht gewünscht ist. Weitere Informationen über Markuperweiterungen finden Sie unter [Markuperweiterungen und WPF XAML](markup-extensions-and-wpf-xaml.md).  
  
### <a name="native-type-converters"></a>Systemeigene Typkonverter  
 In WPF- und .NET Framework-Implementierungen des XAML-Parsers gibt es bestimmte Typen, die über eine native Typkonvertierungsverarbeitung verfügen. Diese Typen werden jedoch herkömmlich nicht als primitive Typen angesehen. Ein Beispiel eines solchen Typs ist <xref:System.DateTime>. Der Grund dafür basiert auf der Funktionsweise der .NET Framework-Architektur: der Typ <xref:System.DateTime> in "mscorlib", die grundlegendste Bibliothek in .NET definiert ist. <xref:System.DateTime> darf nicht mit einem Attribut zu attribuieren, die aus einer anderen Assembly stammt, eine Abhängigkeit einführt (<xref:System.ComponentModel.TypeConverterAttribute> stammt aus dem System), damit der gewöhnliche Typkonverter-Ermittlungsmechanismus durch die Attributierung nicht unterstützt wird. Stattdessen verfügt der XAML-Parser über eine Liste von Typen, für die diese native Verarbeitung erforderlich ist, und verarbeitet diese Typen ähnlich wie echte primitive Typen. (Im Fall von <xref:System.DateTime> Dies umfasst einen Aufruf von <xref:System.DateTime.Parse%2A>.)  
  
<a name="Implementing_a_Type_Converter"></a>   
## <a name="implementing-a-type-converter"></a>Implementieren eines Typkonverters  
  
### <a name="typeconverter"></a>TypeConverter  
 In der <xref:System.Windows.Point> im bereits erwähnten Beispiel, die Klasse <xref:System.Windows.PointConverter> erwähnt wurde. Für .NET-Implementierungen von XAML, sind alle Typkonverter für XAML-Zwecke verwendet werden, die von der Basisklasse abgeleitete Klassen <xref:System.ComponentModel.TypeConverter>. Die <xref:System.ComponentModel.TypeConverter> -Klasse gab es in .NET Framework-Versionen, die das Vorhandensein des XAML vorausgehen, eines der ursprünglichen Verwendungsweisen bestand darin die zeichenfolgenkonvertierung für Eigenschaftendialogfelder in visuellen Designern bereitzustellen. Für XAML, die Rolle des <xref:System.ComponentModel.TypeConverter> wird erweitert, damit die Basisklasse für Konvertierungen aus to- und from-Zeichenfolge, mit denen möglicherweise einen Run-Time-Wert, der einer bestimmten Objekteigenschaft zurück in eine Zeichenfolge für das Verarbeiten und Analysieren eines Zeichenfolgenattributwerts die Serialisierung als Attribut.  
  
 <xref:System.ComponentModel.TypeConverter> definiert vier Member, die für die Konvertierung in und aus Zeichenfolgen für XAML-Verarbeitungszwecke relevant sind:  
  
-   <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A>  
  
-   <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A>  
  
-   <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>  
  
-   <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>  
  
 Die wichtigste Methode ist <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>. Diese Methode konvertiert die Eingabezeichenfolge in den erforderlichen Objekttyp. Streng genommen ist der <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> -Methode kann implementiert werden, um eine viel breitere Palette von Typen in den vom Konverter beabsichtigten Zieltyp zu konvertieren, und somit für Zwecke, die über XAML hinausgehen werden sollen, z.B. die Unterstützung von Konvertierungen zur Laufzeit, sondern für XAML-Zwecke Es ist nur der Codepfad, der verarbeiten kann eine <xref:System.String> Eingabe, die wichtig ist.  
  
 Die nächste wichtigste Methode ist <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>. Wenn eine Anwendung in eine Markupdarstellung umgewandelt wird (z. B. Wenn sie in XAML als Datei gespeichert ist), <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> ist verantwortlich für die Erstellung einer Markupdarstellung. In diesem Fall der Codepfad, der für XAML wichtig ist, wenn Sie übergeben eine `destinationType` von <xref:System.String> .  
  
 <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> und <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A> sind Unterstützungsmethoden, die verwendet werden, wenn ein Dienst die Funktionen von Abfragen die <xref:System.ComponentModel.TypeConverter> Implementierung. Sie müssen diese Methoden implementieren, um `true` für typspezifische Klassen zurückzugeben, welche die entsprechenden Konvertierungsmethoden Ihres Konverters unterstützen. Für XAML-Zwecke bedeutet dies in der Regel den <xref:System.String> -Typ.  
  
### <a name="culture-information-and-type-converters-for-xaml"></a>Kulturinformations- und Typkonverter für XAML  
 Jede <xref:System.ComponentModel.TypeConverter> Implementierung kann über eine eigene Interpretation von was eine gültige Zeichenfolge für eine Konvertierung ausmacht und können auch verwenden oder die als Parameter übergebene typbeschreibung ignorieren. Im Hinblick auf die Kultur und das Konvertieren von XAML-Typen gibt es eine wichtige Überlegung. Die Verwendung von lokalisierbaren Zeichenfolgen als Attributwerte wird von XAML vollständig unterstützt. Die Verwendung lokalisierbarer Zeichenfolgen als Typkonvertereingabe mit bestimmten kulturellen Anforderungen wird nicht unterstützt, weil Typkonverter für XAML-Attributwerte ein zwangsläufig festes Sprachverarbeitungsverhalten umfassen, in dem die `en-US`-Kultur verwendet wird. Weitere Informationen zu den Gründe für diese Einschränkung finden Sie in der XAML-Sprachspezifikation ([\[MS-XAML\]](https://go.microsoft.com/fwlink/?LinkId=114525)).  
  
 Da die Kultur ein Problem darstellen kann, verwenden einige Kulturen ein Komma als Dezimaltrennzeichen für Zahlen. Dies steht mit dem Verhalten in Konflikt, das viele der WPF XAML-Typkonverter aufweisen und darin besteht, ein Komma als Trennzeichen zu verwenden (auf Grundlage geschichtlicher Präzedenzfälle wie die allgemeine X,Y-Form oder durch Trennzeichen getrennte Listen). Sogar die Übergabe einer Kultur im umgebenden XAML (das Festlegen von `Language` oder `xml:lang` auf die Kultur `sl-SI`, ein Beispiel für eine Kultur, die ein Komma für Dezimalstellen so verwendet) löst das Problem nicht.  
  
### <a name="implementing-convertfrom"></a>Implementieren von ConvertFrom  
 Damit die <xref:System.ComponentModel.TypeConverter> -Methode für diesen Konverter als eine <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> -Implementierung verwendet werden kann, die XAML unterstützt, muss sie eine Zeichenfolge als den `value` -Parameter akzeptieren. Wenn die Zeichenfolge in einem gültigen formatieren, und konvertiert werden kann, indem die <xref:System.ComponentModel.TypeConverter> -Implementierung, und klicken Sie dann auf das zurückgegebene Objekt muss eine Umwandlung in den von der Eigenschaft erwarteten Typ unterstützen. Andernfalls muss die <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> -Implementierung `null`zurückgeben.  
  
 Jede <xref:System.ComponentModel.TypeConverter> Implementierung kann über eine eigene Interpretation von was eine gültige Zeichenfolge für eine Konvertierung ausmacht und können auch verwenden oder ignorieren Sie den Typ typbeschreibung oder kulturkontexte als Parameter übergeben. Bei der WPF-XAML-Verarbeitung werden jedoch möglicherweise nicht in allen Fällen Werte an den Kontext der Typbeschreibung weitergegeben. Die auf `xml:lang` basierende Kultur wird möglicherweise auch nicht weitergegeben.  
  
> [!NOTE]
>  Verwenden Sie auf gar keinen Fall die geschweiften Klammern,vor allem { , als ein mögliches Element Ihres Zeichenfolgenformats. Diese Zeichen sind als ein Eintrag reserviert und dienen dem Beenden einer Markuperweiterungssequenz.  
  
### <a name="implementing-convertto"></a>Implementieren von ConvertTo  
 <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> wird möglicherweise für die Serialisierungsunterstützung verwendet. Die Serialisierungsunterstützung durch <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> für Ihren benutzerdefinierten Typ und dessen Typkonverter ist nicht unbedingt erforderlich. Wenn Sie jedoch ein Steuerelement implementieren oder die Serialisierung als Bestandteil der Features oder zum Entwerfen Ihrer Klasse verwenden, sollten Sie <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>implementieren.  
  
 Verwendet werden kann als eine <xref:System.ComponentModel.TypeConverter> -Implementierung, XAML, unterstützt, die <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> -Methode für diesen Konverter muss eine Instanz vom Typ (oder einen Wert) unterstützt akzeptieren, als die `value` Parameter. Wenn die `destinationType` Parameter ist der Typ <xref:System.String>, und klicken Sie dann das zurückgegebene Objekt umgewandelt werden kann muss <xref:System.String>. Die zurückgegebene Zeichenfolge muss einen serialisierten Wert von `value`darstellen. Im Idealfall muss das Serialisierungsformat, das Sie auswählen, den gleichen Wert zu generieren, wenn diese Zeichenfolge übergeben wurden, kann die <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> -Implementierung desselben Konverters, ohne erhebliche Informationsverluste.  
  
 Wenn der Wert kann nicht serialisiert werden, oder der Konverter keine Serialisierung unterstützt die <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> Implementierung muss zurückgeben `null`, und darf in diesem Fall einer Ausnahme. Aber wenn Sie Ausnahmen auslösen, sollten Sie melden, dass die Unfähigkeit, diese Konvertierung als Teil Ihrer <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> Implementierung, damit die bewährte Methode eine Überprüfung mit <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> zuerst zum Vermeiden von Ausnahmen werden unterstützt.  
  
 Wenn `destinationType` Parameter ist nicht vom Typ <xref:System.String>, Sie können Ihre eigene konverterverarbeitung auswählen. Sie würden in der Regel wiederherstellen, die grundlegende implementierungsverarbeitung vor, die in den grundlegendsten <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> eine bestimmte Ausnahme auslöst.  
  
### <a name="implementing-canconvertto"></a>Implementieren von CanConvertTo  
 Ihre Implementierung <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> sollte `true` für `destinationType` vom Typ <xref:System.String>zurückgeben und andernfalls die grundlegende Implementierung ableiten.  
  
### <a name="implementing-canconvertfrom"></a>Implementieren von CanConvertFrom  
 Ihre Implementierung <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A> sollte `true` für `sourceType` vom Typ <xref:System.String>zurückgeben und andernfalls die grundlegende Implementierung ableiten.  
  
<a name="Applying_the_TypeConverterAttribute"></a>   
## <a name="applying-the-typeconverterattribute"></a>Anwenden von TypeConverterAttribute  
 In der Reihenfolge für Ihr benutzerdefinierter Typkonverter als der agierende Typkonverter für eine benutzerdefinierte Klasse von einem XAML-Prozessor, müssen Sie anwenden, die [!INCLUDE[TLA#tla_netframewkattr](../../../../includes/tlasharptla-netframewkattr-md.md)] <xref:System.ComponentModel.TypeConverterAttribute> auf Ihre Klassendefinition. Beim <xref:System.ComponentModel.TypeConverterAttribute.ConverterTypeName%2A> , den Sie über das Attribut angeben, muss es sich um den Typnamen Ihres benutzerdefinierten Typkonverters handeln. Wenn ein XAML-Prozessor nach Anwendung dieses Attributs Werte verarbeitet, bei denen der Eigenschaftstyp Ihren benutzerdefinierten Klassentyp verwendet, kann es Zeichenfolgen eingeben und Objektinstanzen zurückgeben.  
  
 Sie können auch einen Typkonverter auf Grundlage einzelner Eigenschaften bereitstellen. Anstelle ein [!INCLUDE[TLA#tla_netframewkattr](../../../../includes/tlasharptla-netframewkattr-md.md)] <xref:System.ComponentModel.TypeConverterAttribute> auf die Klassendefinition anzuwenden, wenden Sie es auf eine Eigenschaftsdefinition (die Hauptdefinition, nicht die darin enthaltenen `get`/`set` -Implementierungen) an. Der Eigenschaftstyp muss mit dem Typ übereinstimmen, der durch Ihren benutzerdefinierten Typkonverter verarbeitet wird. Wenn dieses Attribut angewendet ist, wenn ein XAML-Prozessor Werte dieser Eigenschaft verarbeitet, kann es Eingabezeichenfolgen verarbeiten und Objektinstanzen zurückgeben. Die Typkonvertertechnik auf Grundlage einzelner Eigenschaften ist besonders nützlich, wenn Sie einen Eigenschaftentyp aus Microsoft .NET Framework oder eine andere Bibliothek auch, in dem Sie die Klassendefinition weder steuern und können nicht angewendet werden, verwenden eine <xref:System.ComponentModel.TypeConverterAttribute> vorhanden.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ComponentModel.TypeConverter>
- [Übersicht über XAML (WPF)](xaml-overview-wpf.md)
- [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md)
- [Ausführliche Erläuterung der XAML-Syntax](xaml-syntax-in-detail.md)
