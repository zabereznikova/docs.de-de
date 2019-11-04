---
title: TypeConverter und XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], TypeConverter class
ms.assetid: f6313e4d-e89d-497d-ac87-b43511a1ae4b
ms.openlocfilehash: aac6c347886b2c29e599952d7642fbe76441b617
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458911"
---
# <a name="typeconverters-and-xaml"></a>TypeConverter und XAML
In diesem Thema wird der Zweck der Typkonvertierung aus einer Zeichenfolge in eine allgemeinere Funktion der XAML-Sprache erläutert. In der .NET Framework erfüllt die <xref:System.ComponentModel.TypeConverter>-Klasse einen bestimmten Zweck als Teil der Implementierung für eine verwaltete benutzerdefinierte Klasse, die als Eigenschafts Wert in der XAML-Attribut Verwendung verwendet werden kann. Wenn Sie eine benutzerdefinierte Klasse schreiben und Instanzen der Klasse als XAML-festleg Bare Attributwerte verwendet werden sollen, müssen Sie möglicherweise eine <xref:System.ComponentModel.TypeConverterAttribute> auf die Klasse anwenden, eine benutzerdefinierte <xref:System.ComponentModel.TypeConverter> Klasse schreiben oder beides.  

## <a name="type-conversion-concepts"></a>Typkonvertierungskonzepte  
  
### <a name="xaml-and-string-values"></a>XAML- und Zeichenfolgenwerte  
 Wenn Sie einen Attributwert in einer XAML-Datei festlegen, ist der ursprüngliche Typ dieses Werts eine Zeichenfolge in reinem Text. Auch andere primitive, z. b. <xref:System.Double>, sind Anfangstext Zeichenfolgen für einen XAML-Prozessor.  
  
 Ein XAML-Prozessor benötigt zwei Angaben, um einen Attributwert zu verarbeiten. Die erste Angabe ist der Werttyp der Eigenschaft, die festgelegt wird. Jede Zeichenfolge, die einen Attributwert definiert, und in XAML verarbeitet wird, muss schließlich umgewandelt werden oder zu einem Wert dieses Typs aufgelöst werden. Wenn es sich beim Wert um einen Primitiv handelt, den der XAML-Parser versteht (beispielsweise ein numerischer Wert), wird versucht, eine direkte Konvertierung der Zeichenfolge vorzunehmen. Wenn es sich bei dem Wert um eine Enumeration handelt, wird mithilfe der Zeichenfolge nach einer Namensübereinstimmung mit einer benannten Konstante in dieser Enumeration gesucht. Wenn es sich beim Wert weder um einen primitiven Typ handelt, den der Parser versteht, noch um eine Enumeration, muss der zutreffende Typ einen Typ oder Wert bereitstellen können, der auf einer konvertierten Zeichenfolge beruht. Dies erfolgt durch Angabe einer Typkonverterklasse. Der Typkonverter ist eine Hilfsklasse zum Bereitstellen von Werten einer anderen Klasse im XAML-Szenario und möglicherweise auch für Codeaufrufe in .NET-Code.  
  
### <a name="using-existing-type-conversion-behavior-in-xaml"></a>Verwenden von vorhandenem Typkonvertierungsverhalten in XAML  
 Je nach Ihren Vorkenntnissen der zugrunde liegenden XAML-Konzepte verwenden Sie möglicherweise bereits das Typkonvertierungsverhalten in der grundlegenden XAML-Anwendung, ohne es zu wissen. WPF definiert beispielsweise buchstäblich hunderte von Eigenschaften, die einen Wert vom Typ <xref:System.Windows.Point>annehmen. Bei einem <xref:System.Windows.Point> handelt es sich um einen Wert, der eine Koordinate in einem zweidimensionalen Koordinatenraum beschreibt, und er verfügt über zwei wichtige Eigenschaften: <xref:System.Windows.Point.X%2A> und <xref:System.Windows.Point.Y%2A>. Wenn Sie einen Punkt in XAML angeben, geben Sie ihn als Zeichenfolge mit einem Trennzeichen (in der Regel ein Komma) zwischen den <xref:System.Windows.Point.X%2A> und <xref:System.Windows.Point.Y%2A> Werten an, die Sie angeben. Beispiel: `<LinearGradientBrush StartPoint="0,0" EndPoint="1,1"/>`.  
  
 Selbst diese einfache Art von <xref:System.Windows.Point> und die einfache Verwendung in XAML umfassen einen Typkonverter. In diesem Fall ist dies die-Klasse <xref:System.Windows.PointConverter>.  
  
 Der Typkonverter für <xref:System.Windows.Point>, der auf Klassenebene definiert ist, optimiert die Markup Verwendungen aller Eigenschaften, die <xref:System.Windows.Point>annehmen. Ohne Typkonverter benötigen Sie das folgende, viel ausführlichere Markup für dasselbe zuvor gezeigte Beispiel:  

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
  
 Vorhandene Typkonverter können in der Regel auf WPF-und .NET Framework Typen ermittelt werden, indem eine Klasse (oder Eigenschaft) auf das vorhanden sein eines angewendeten <xref:System.ComponentModel.TypeConverterAttribute>überprüft wird. Dieses Attribut benennt die Klasse, die den unterstützenden Typkonverter für Werte dieses Typs darstellt, für XAML-Zwecke sowie für mögliche andere Zwecke.  
  
### <a name="type-converters-and-markup-extensions"></a>Typkonverter und Markuperweiterungen  
 Markuperweiterungen und Typkonverter füllen orthogonale Rollen in Bezug auf das Verhalten des XAML-Prozessors und die Szenarios, auf die sie auf angewendet werden. Obwohl der Kontext für die Verwendung von Markuperweiterungen verfügbar ist, wird das Typkonvertierungsverhalten von Eigenschaften, bei denen eine Markuperweiterung einen Wert bereitstellt, in der Regel nicht in den Implementierungen der Markuperweiterung überprüft. Mit anderen Worten, auch wenn eine Markup Erweiterung eine Text Zeichenfolge als `ProvideValue` Ausgabe zurückgibt, wird das Typkonvertierungs Verhalten für diese Zeichenfolge, das auf eine bestimmte Eigenschaft oder denselben Eigenschafts Werttyp angewendet wird, nicht aufgerufen. in der Regel ist der Zweck einer Markup Erweiterung die Verarbeitung einer Zeichenfolge. und geben ein Objekt zurück, für das kein Typkonverter beteiligt ist.  
  
 Eine allgemeine Situation, in der eine Markuperweiterung statt einem Typkonverter erforderlich ist, besteht im Erstellen eines Verweises auf ein vorhandenes Objekt. Ein zustandsloser Typkonverter könnte bestenfalls nur eine neue Instanz genieren, die möglicherweise nicht gewünscht ist. Weitere Informationen über Markuperweiterungen finden Sie unter [Markuperweiterungen und WPF XAML](markup-extensions-and-wpf-xaml.md).  
  
### <a name="native-type-converters"></a>Systemeigene Typkonverter  
 In WPF- und .NET Framework-Implementierungen des XAML-Parsers gibt es bestimmte Typen, die über eine native Typkonvertierungsverarbeitung verfügen. Diese Typen werden jedoch herkömmlich nicht als primitive Typen angesehen. Ein Beispiel eines solchen Typs ist <xref:System.DateTime>. Der Grund hierfür ist die Funktionsweise der .NET Framework Architektur: der Typ <xref:System.DateTime> ist in mscorlib definiert, der grundlegendsten Bibliothek in .net. <xref:System.DateTime> darf nicht mit einem Attribut attributiert werden, das aus einer anderen Assembly stammt, die eine Abhängigkeit einführt (<xref:System.ComponentModel.TypeConverterAttribute> ist vom System), sodass der übliche Typkonverter-Ermittlungs Mechanismus durch die Attributierung nicht unterstützt werden kann. Stattdessen verfügt der XAML-Parser über eine Liste von Typen, für die diese native Verarbeitung erforderlich ist, und verarbeitet diese Typen ähnlich wie echte primitive Typen. (Im Fall von <xref:System.DateTime> umfasst dies einen Aufruf<xref:System.DateTime.Parse%2A>.)  
  
<a name="Implementing_a_Type_Converter"></a>   
## <a name="implementing-a-type-converter"></a>Implementieren eines Typkonverters  
  
### <a name="typeconverter"></a>TypeConverter  
 Im zuvor angegebenen <xref:System.Windows.Point> Beispiel wurde die-Klasse <xref:System.Windows.PointConverter> erwähnt. Für .net-Implementierungen von XAML sind alle Typkonverter, die für XAML-Zwecke verwendet werden, Klassen, die von der Basisklasse <xref:System.ComponentModel.TypeConverter>abgeleitet werden. Die <xref:System.ComponentModel.TypeConverter>-Klasse war in Versionen von .NET Framework vorhanden, die vor dem vorhanden sein von XAML liegen. eine der ursprünglichen Verwendungsmöglichkeiten bestand darin, die Zeichen folgen Konvertierung für Eigenschafts Dialogfelder in visuellen Designern bereitzustellen. Bei XAML wird die Rolle von <xref:System.ComponentModel.TypeConverter> erweitert, um die Basisklasse für die Konvertierung von Zeichen folgen-und Zeichen folgen Konvertierungen zu ermöglichen, die das Verarbeiten eines Zeichen folgen Attribut Werts und ggf. das Verarbeiten eines Lauf Zeitwerts einer bestimmten Objekt Eigenschaft zurück in eine Zeichenfolge für Serialisierung als Attribut.  
  
 <xref:System.ComponentModel.TypeConverter> definiert vier Member, die für die Umstellung von und aus Zeichen folgen für XAML-Verarbeitungszwecke relevant sind:  
  
- <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A>  
  
- <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A>  
  
- <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>  
  
- <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>  
  
 Dabei ist die wichtigste Methode <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>. Diese Methode konvertiert die Eingabezeichenfolge in den erforderlichen Objekttyp. Streng genommen könnte die <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>-Methode implementiert werden, um einen viel größeren Bereich von Typen in den gewünschten Zieltyp des Konverters zu konvertieren, und somit Zwecke verarbeiten, die über XAML hinausgehen, wie z. b. das unterstützen von Lauf Zeit Konvertierungen, aber für XAML-Zwecke ist es nur der Codepfad, mit dem eine <xref:System.String> Eingabe verarbeitet werden kann.  
  
 Die nächstwichtigste Methode ist <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>. Wenn eine Anwendung in eine Markup Darstellung konvertiert wird (wenn Sie beispielsweise in XAML als Datei gespeichert wird), ist <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> für die Erstellung einer Markup Darstellung verantwortlich. In diesem Fall ist der Codepfad, der für XAML wichtig ist, wenn Sie eine `destinationType` <xref:System.String> übergeben.  
  
 <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> und <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A> sind Unterstützungsmethoden, die verwendet werden, wenn ein Dienst die Funktionen der <xref:System.ComponentModel.TypeConverter> -Implementierung abfragt. Sie müssen diese Methoden implementieren, um `true` für typspezifische Klassen zurückzugeben, welche die entsprechenden Konvertierungsmethoden Ihres Konverters unterstützen. Für XAML-Zwecke bedeutet dies in der Regel den <xref:System.String> -Typ.  
  
### <a name="culture-information-and-type-converters-for-xaml"></a>Kulturinformations- und Typkonverter für XAML  
 Jede <xref:System.ComponentModel.TypeConverter>-Implementierung kann über eine eigene Interpretation der Bedeutung einer gültigen Zeichenfolge für eine Konvertierung verfügen. Außerdem kann Sie die Typbeschreibung, die als Parameter verwendet wird, verwenden oder ignorieren. Im Hinblick auf die Kultur und das Konvertieren von XAML-Typen gibt es eine wichtige Überlegung. Die Verwendung von lokalisierbaren Zeichenfolgen als Attributwerte wird von XAML vollständig unterstützt. Die Verwendung lokalisierbarer Zeichenfolgen als Typkonvertereingabe mit bestimmten kulturellen Anforderungen wird nicht unterstützt, weil Typkonverter für XAML-Attributwerte ein zwangsläufig festes Sprachverarbeitungsverhalten umfassen, in dem die `en-US`-Kultur verwendet wird. Weitere Informationen zu den Gründe für diese Einschränkung finden Sie in der XAML-Sprachspezifikation ([\[MS-XAML\]](https://go.microsoft.com/fwlink/?LinkId=114525)).  
  
 Da die Kultur ein Problem darstellen kann, verwenden einige Kulturen ein Komma als Dezimaltrennzeichen für Zahlen. Dies steht mit dem Verhalten in Konflikt, das viele der WPF XAML-Typkonverter aufweisen und darin besteht, ein Komma als Trennzeichen zu verwenden (auf Grundlage geschichtlicher Präzedenzfälle wie die allgemeine X,Y-Form oder durch Trennzeichen getrennte Listen). Sogar die Übergabe einer Kultur im umgebenden XAML (das Festlegen von `Language` oder `xml:lang` auf die Kultur `sl-SI`, ein Beispiel für eine Kultur, die ein Komma für Dezimalstellen so verwendet) löst das Problem nicht.  
  
### <a name="implementing-convertfrom"></a>Implementieren von ConvertFrom  
 Damit die <xref:System.ComponentModel.TypeConverter> -Methode für diesen Konverter als eine <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> -Implementierung verwendet werden kann, die XAML unterstützt, muss sie eine Zeichenfolge als den `value` -Parameter akzeptieren. Wenn die Zeichenfolge in einem gültigen Format vorliegt und von der <xref:System.ComponentModel.TypeConverter>-Implementierung konvertiert werden kann, muss das zurückgegebene Objekt eine Umwandlung in den von der-Eigenschaft erwarteten Typ unterstützen. Andernfalls muss die <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> -Implementierung `null`zurückgeben.  
  
 Jede <xref:System.ComponentModel.TypeConverter>-Implementierung kann eine eigene Interpretation davon aufweisen, was eine gültige Zeichenfolge für eine Konvertierung ausmacht, und kann auch die Typbeschreibung oder Kultur Kontexte verwenden oder ignorieren, die als Parameter verwendet werden. Bei der WPF-XAML-Verarbeitung werden jedoch möglicherweise nicht in allen Fällen Werte an den Kontext der Typbeschreibung weitergegeben. Die auf `xml:lang` basierende Kultur wird möglicherweise auch nicht weitergegeben.  
  
> [!NOTE]
> Verwenden Sie auf gar keinen Fall die geschweiften Klammern,vor allem { , als ein mögliches Element Ihres Zeichenfolgenformats. Diese Zeichen sind als ein Eintrag reserviert und dienen dem Beenden einer Markuperweiterungssequenz.  
  
### <a name="implementing-convertto"></a>Implementieren von ConvertTo  
 <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> wird möglicherweise für die Serialisierungsunterstützung verwendet. Die Serialisierungsunterstützung durch <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> für Ihren benutzerdefinierten Typ und dessen Typkonverter ist nicht unbedingt erforderlich. Wenn Sie jedoch ein Steuerelement implementieren oder die Serialisierung als Bestandteil der Features oder zum Entwerfen Ihrer Klasse verwenden, sollten Sie <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>implementieren.  
  
 Um als <xref:System.ComponentModel.TypeConverter>-Implementierung verwendet werden zu können, die XAML unterstützt, muss die <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>-Methode für diesen Konverter eine Instanz des Typs (oder eines Werts) akzeptieren, der als `value`-Parameter unterstützt wird. Wenn der `destinationType`-Parameter der Typ <xref:System.String>ist, muss das zurückgegebene Objekt in der Lage sein, als <xref:System.String>umgewandelt zu werden. Die zurückgegebene Zeichenfolge muss einen serialisierten Wert von `value` darstellen. Im Idealfall sollte das von Ihnen ausgewählte Serialisierungsformat in der Lage sein, den gleichen Wert zu erzeugen, wenn diese Zeichenfolge ohne erheblichen Verlust von Informationen an die <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> Implementierung desselben Konverters übermittelt wurde.  
  
 Wenn der Wert nicht serialisiert werden kann oder der Konverter die Serialisierung nicht unterstützt, muss die <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> Implementierung `null`zurückgeben. in diesem Fall ist es zulässig, eine Ausnahme auszulösen. Wenn Sie jedoch Ausnahmen auslösen, sollten Sie die Möglichkeit melden, diese Konvertierung nicht als Teil ihrer <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> Implementierung zu verwenden, sodass die bewährte Vorgehensweise bei der Überprüfung mit <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> zuerst unterstützt wird, um Ausnahmen zu vermeiden.  
  
 Wenn `destinationType` Parameter nicht vom Typ <xref:System.String>ist, können Sie Ihre eigene konverterverarbeitung auswählen. Normalerweise würden Sie die grundlegende Implementierungs Verarbeitung wiederherstellen, die im grundlegendsten-<xref:System.ComponentModel.TypeConverter.ConvertTo%2A> eine bestimmte Ausnahme auslöst.  
  
### <a name="implementing-canconvertto"></a>Implementieren von CanConvertTo  
 Ihre Implementierung <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> sollte `true` für `destinationType` vom Typ <xref:System.String>zurückgeben und andernfalls die grundlegende Implementierung ableiten.  
  
### <a name="implementing-canconvertfrom"></a>Implementieren von CanConvertFrom  
 Ihre Implementierung <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A> sollte `true` für `sourceType` vom Typ <xref:System.String>zurückgeben und andernfalls die grundlegende Implementierung ableiten.  
  
<a name="Applying_the_TypeConverterAttribute"></a>   
## <a name="applying-the-typeconverterattribute"></a>Anwenden von TypeConverterAttribute  
 Damit Ihr benutzerdefinierter Typkonverter als der aktive Typkonverter für eine benutzerdefinierte Klasse von einem XAML-Prozessor verwendet werden kann, müssen Sie den <xref:System.ComponentModel.TypeConverterAttribute> auf Ihre Klassendefinition anwenden. Beim <xref:System.ComponentModel.TypeConverterAttribute.ConverterTypeName%2A> , den Sie über das Attribut angeben, muss es sich um den Typnamen Ihres benutzerdefinierten Typkonverters handeln. Wenn ein XAML-Prozessor nach Anwendung dieses Attributs Werte verarbeitet, bei denen der Eigenschaftstyp Ihren benutzerdefinierten Klassentyp verwendet, kann es Zeichenfolgen eingeben und Objektinstanzen zurückgeben.  
  
 Sie können auch einen Typkonverter auf Grundlage einzelner Eigenschaften bereitstellen. Anstatt ein <xref:System.ComponentModel.TypeConverterAttribute> auf die Klassendefinition anzuwenden, wenden Sie es auf eine Eigenschafts Definition an (die Haupt Definition, nicht die `get`/`set` darin enthaltenen Implementierungen). Der Eigenschaftstyp muss mit dem Typ übereinstimmen, der durch Ihren benutzerdefinierten Typkonverter verarbeitet wird. Wenn dieses Attribut angewendet ist, wenn ein XAML-Prozessor Werte dieser Eigenschaft verarbeitet, kann es Eingabezeichenfolgen verarbeiten und Objektinstanzen zurückgeben. Die Typkonvertertechnik pro Eigenschaft ist besonders nützlich, wenn Sie einen Eigenschaftentyp aus Microsoft .NET Framework oder einer anderen Bibliothek verwenden möchten, in der Sie die Klassendefinition nicht steuern können und keine <xref:System.ComponentModel.TypeConverterAttribute> dort anwenden können.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ComponentModel.TypeConverter>
- [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md)
- [Ausführliche Erläuterung der XAML-Syntax](xaml-syntax-in-detail.md)
