---
title: TypeConverter und XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], TypeConverter class
ms.assetid: f6313e4d-e89d-497d-ac87-b43511a1ae4b
ms.openlocfilehash: 94cfce44d5702e0550310723ec56184096165436
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187296"
---
# <a name="typeconverters-and-xaml"></a>TypeConverter und XAML
In diesem Thema wird der Zweck der Typkonvertierung aus einer Zeichenfolge in eine allgemeinere Funktion der XAML-Sprache erläutert. In .NET Framework <xref:System.ComponentModel.TypeConverter> dient die Klasse einem bestimmten Zweck als Teil der Implementierung für eine verwaltete benutzerdefinierte Klasse, die als Eigenschaftswert in der XAML-Attributverwendung verwendet werden kann. Wenn Sie eine benutzerdefinierte Klasse schreiben und Instanzen Ihrer Klasse als XAML-Setzbare <xref:System.ComponentModel.TypeConverterAttribute> Attributwerte verwendet werden <xref:System.ComponentModel.TypeConverter> sollen, müssen Sie möglicherweise eine auf Ihre Klasse anwenden, eine benutzerdefinierte Klasse schreiben oder beides.  

## <a name="type-conversion-concepts"></a>Typkonvertierungskonzepte  
  
### <a name="xaml-and-string-values"></a>XAML- und Zeichenfolgenwerte  
 Wenn Sie einen Attributwert in einer XAML-Datei festlegen, ist der ursprüngliche Typ dieses Werts eine Zeichenfolge in reinem Text. Auch andere Primitive, <xref:System.Double> wie z. B. Anfangs Textzeichenfolgen zu einem XAML-Prozessor.  
  
 Ein XAML-Prozessor benötigt zwei Angaben, um einen Attributwert zu verarbeiten. Die erste Angabe ist der Werttyp der Eigenschaft, die festgelegt wird. Jede Zeichenfolge, die einen Attributwert definiert, und in XAML verarbeitet wird, muss schließlich umgewandelt werden oder zu einem Wert dieses Typs aufgelöst werden. Wenn es sich beim Wert um einen Primitiv handelt, den der XAML-Parser versteht (beispielsweise ein numerischer Wert), wird versucht, eine direkte Konvertierung der Zeichenfolge vorzunehmen. Wenn es sich bei dem Wert um eine Enumeration handelt, wird mithilfe der Zeichenfolge nach einer Namensübereinstimmung mit einer benannten Konstante in dieser Enumeration gesucht. Wenn es sich beim Wert weder um einen primitiven Typ handelt, den der Parser versteht, noch um eine Enumeration, muss der zutreffende Typ einen Typ oder Wert bereitstellen können, der auf einer konvertierten Zeichenfolge beruht. Dies erfolgt durch Angabe einer Typkonverterklasse. Der Typkonverter ist eine Hilfsklasse zum Bereitstellen von Werten einer anderen Klasse im XAML-Szenario und möglicherweise auch für Codeaufrufe in .NET-Code.  
  
### <a name="using-existing-type-conversion-behavior-in-xaml"></a>Verwenden von vorhandenem Typkonvertierungsverhalten in XAML  
 Je nach Ihren Vorkenntnissen der zugrunde liegenden XAML-Konzepte verwenden Sie möglicherweise bereits das Typkonvertierungsverhalten in der grundlegenden XAML-Anwendung, ohne es zu wissen. Beispielsweise definiert WPF buchstäblich Hunderte von Eigenschaften, die <xref:System.Windows.Point>einen Wert des Typs annehmen. A <xref:System.Windows.Point> ist ein Wert, der eine Koordinate in einem zweidimensionalen Koordinatenraum beschreibt, und er hat wirklich nur zwei wichtige Eigenschaften: <xref:System.Windows.Point.X%2A> und <xref:System.Windows.Point.Y%2A>. Wenn Sie einen Punkt in XAML angeben, geben Sie ihn als Zeichenfolge mit <xref:System.Windows.Point.X%2A> einem <xref:System.Windows.Point.Y%2A> Trennzeichen (in der Regel ein Komma) zwischen den und den von Ihnen angegebenen Werten an. Beispiel: `<LinearGradientBrush StartPoint="0,0" EndPoint="1,1"/>`  
  
 Selbst diese einfache <xref:System.Windows.Point> Art von und seine einfache Verwendung in XAML beinhalten einen Typkonverter. In diesem Fall ist <xref:System.Windows.PointConverter>dies die Klasse .  
  
 Der typkonverter <xref:System.Windows.Point> für definiert auf Klassenebene optimiert die Markupverwendungen aller Eigenschaften, die . <xref:System.Windows.Point> Ohne Typkonverter benötigen Sie das folgende, viel ausführlichere Markup für dasselbe zuvor gezeigte Beispiel:  

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
  
 Vorhandene Typkonverter können im Allgemeinen für WPF- und .NET Framework-Typen ermittelt werden, <xref:System.ComponentModel.TypeConverterAttribute>indem eine Klasse (oder Eigenschaft) auf das Vorhandensein einer angewendeten überprüft wird. Dieses Attribut benennt die Klasse, die den unterstützenden Typkonverter für Werte dieses Typs darstellt, für XAML-Zwecke sowie für mögliche andere Zwecke.  
  
### <a name="type-converters-and-markup-extensions"></a>Typkonverter und Markuperweiterungen  
 Markuperweiterungen und Typkonverter füllen orthogonale Rollen in Bezug auf das Verhalten des XAML-Prozessors und die Szenarios, auf die sie auf angewendet werden. Obwohl der Kontext für die Verwendung von Markuperweiterungen verfügbar ist, wird das Typkonvertierungsverhalten von Eigenschaften, bei denen eine Markuperweiterung einen Wert bereitstellt, in der Regel nicht in den Implementierungen der Markuperweiterung überprüft. Mit anderen Worten, selbst wenn eine Markuperweiterung `ProvideValue` eine Textzeichenfolge als Ausgabe zurückgibt, wird das Typkonvertierungsverhalten für diese Zeichenfolge, wie sie auf einen bestimmten Eigenschafts- oder Eigenschaftswerttyp angewendet wird, nicht aufgerufen.  
  
 Eine allgemeine Situation, in der eine Markuperweiterung statt einem Typkonverter erforderlich ist, besteht im Erstellen eines Verweises auf ein vorhandenes Objekt. Ein zustandsloser Typkonverter könnte bestenfalls nur eine neue Instanz genieren, die möglicherweise nicht gewünscht ist. Weitere Informationen über Markuperweiterungen finden Sie unter [Markuperweiterungen und WPF XAML](markup-extensions-and-wpf-xaml.md).  
  
### <a name="native-type-converters"></a>Systemeigene Typkonverter  
 In WPF- und .NET Framework-Implementierungen des XAML-Parsers gibt es bestimmte Typen, die über eine native Typkonvertierungsverarbeitung verfügen. Diese Typen werden jedoch herkömmlich nicht als primitive Typen angesehen. Ein Beispiel eines solchen Typs ist <xref:System.DateTime>. Der Grund dafür hängt von der Funktionsweise der .NET Framework-Architektur ab: Der Typ <xref:System.DateTime> wird in mscorlib, der grundlegendsten Bibliothek in .NET, definiert. <xref:System.DateTime>es ist nicht zulässig, mit einem Attribut zugeschrieben zu<xref:System.ComponentModel.TypeConverterAttribute> werden, das von einer anderen Assembly stammt, die eine Abhängigkeit (ist von System) einführt, sodass der übliche Typkonverterermittlungsmechanismus durch Attributierung nicht unterstützt werden kann. Stattdessen verfügt der XAML-Parser über eine Liste von Typen, für die diese native Verarbeitung erforderlich ist, und verarbeitet diese Typen ähnlich wie echte primitive Typen. (Im Falle <xref:System.DateTime> davon beinhaltet ein <xref:System.DateTime.Parse%2A>Aufruf an .)  
  
<a name="Implementing_a_Type_Converter"></a>
## <a name="implementing-a-type-converter"></a>Implementieren eines Typkonverters  
  
### <a name="typeconverter"></a>TypeConverter  
 Im <xref:System.Windows.Point> zuvor gegebenen Beispiel <xref:System.Windows.PointConverter> wurde die Klasse erwähnt. Für .NET-Implementierungen von XAML sind alle Typkonverter, die für XAML-Zwecke <xref:System.ComponentModel.TypeConverter>verwendet werden, Klassen, die von der Basisklasse abstammen. Die <xref:System.ComponentModel.TypeConverter> Klasse existierte in Versionen von .NET Framework, die der Existenz von XAML vorausgeht. Eine der ursprünglichen Verwendungen bestand darin, Zeichenfolgenkonvertierung für Eigenschaftendialogfelder in visuellen Designern bereitzustellen. Bei XAML wird <xref:System.ComponentModel.TypeConverter> die Rolle von um die Basisklasse für To-String- und From-String-Konvertierungen erweitert, die das Analysieren eines Zeichenfolgenattributwerts und möglicherweise die Verarbeitung eines Laufzeitwerts einer bestimmten Objekteigenschaft in eine Zeichenfolge für die Serialisierung als Attribut ermöglichen.  
  
 <xref:System.ComponentModel.TypeConverter>definiert vier Member, die für die Konvertierung in und von Zeichenfolgen für XAML-Verarbeitungszwecke relevant sind:  
  
- <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A>  
  
- <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A>  
  
- <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>  
  
- <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>  
  
 Die wichtigste Methode ist <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>. Diese Methode konvertiert die Eingabezeichenfolge in den erforderlichen Objekttyp. Streng genommen <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> könnte die Methode implementiert werden, um eine viel breitere Palette von Typen in den beabsichtigten Zieltyp des Konverters zu konvertieren, und somit Zwecken dienen, die <xref:System.String> über XAML hinausgehen, wie z. B. die Unterstützung von Laufzeitkonvertierungen, aber für XAML-Zwecke ist es nur der Codepfad, der eine Eingabe verarbeiten kann, die wichtig ist.  
  
 Die nächstwichtigste Methode <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>ist . Wenn eine Anwendung in eine Markupdarstellung konvertiert wird (z. B. wenn <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> sie in XAML als Datei gespeichert wird), ist sie für die Erstellung einer Markupdarstellung verantwortlich. In diesem Fall ist der Codepfad, der für `destinationType` XAML wichtig ist, wenn Sie eine von <xref:System.String> übergeben.  
  
 <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> und <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A> sind Unterstützungsmethoden, die verwendet werden, wenn ein Dienst die Funktionen der <xref:System.ComponentModel.TypeConverter> -Implementierung abfragt. Sie müssen diese Methoden implementieren, um `true` für typspezifische Klassen zurückzugeben, welche die entsprechenden Konvertierungsmethoden Ihres Konverters unterstützen. Für XAML-Zwecke bedeutet dies in der Regel den <xref:System.String> -Typ.  
  
### <a name="culture-information-and-type-converters-for-xaml"></a>Kulturinformations- und Typkonverter für XAML  

 Jede <xref:System.ComponentModel.TypeConverter> Implementierung kann eine eigene Interpretation dessen haben, was eine gültige Zeichenfolge für eine Konvertierung darstellt, und kann auch die als Parameter übergebene Typbeschreibung verwenden oder ignorieren. Im Hinblick auf die Kultur und das Konvertieren von XAML-Typen gibt es eine wichtige Überlegung. Die Verwendung von lokalisierbaren Zeichenfolgen als Attributwerte wird von XAML vollständig unterstützt. Die Verwendung lokalisierbarer Zeichenfolgen als Typkonvertereingabe mit bestimmten kulturellen Anforderungen wird nicht unterstützt, weil Typkonverter für XAML-Attributwerte ein zwangsläufig festes Sprachverarbeitungsverhalten umfassen, in dem die `en-US`-Kultur verwendet wird. Weitere Informationen zu den Entwurfsgründen für diese Einschränkung finden Sie in der XAML-Sprachspezifikation ([\[MS-XAML\]](https://download.microsoft.com/download/0/A/6/0A6F7755-9AF5-448B-907D-13985ACCF53E/[MS-XAML].pdf).  
  
 Da die Kultur ein Problem darstellen kann, verwenden einige Kulturen ein Komma als Dezimaltrennzeichen für Zahlen. Dies steht mit dem Verhalten in Konflikt, das viele der WPF XAML-Typkonverter aufweisen und darin besteht, ein Komma als Trennzeichen zu verwenden (auf Grundlage geschichtlicher Präzedenzfälle wie die allgemeine X,Y-Form oder durch Trennzeichen getrennte Listen). Sogar die Übergabe einer Kultur im umgebenden XAML (das Festlegen von `Language` oder `xml:lang` auf die Kultur `sl-SI`, ein Beispiel für eine Kultur, die ein Komma für Dezimalstellen so verwendet) löst das Problem nicht.  
  
### <a name="implementing-convertfrom"></a>Implementieren von ConvertFrom  
 Damit die <xref:System.ComponentModel.TypeConverter> -Methode für diesen Konverter als eine <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> -Implementierung verwendet werden kann, die XAML unterstützt, muss sie eine Zeichenfolge als den `value` -Parameter akzeptieren. Wenn die Zeichenfolge im gültigen Format war <xref:System.ComponentModel.TypeConverter> und von der Implementierung konvertiert werden kann, muss das zurückgegebene Objekt eine Umwandlung in den von der Eigenschaft erwarteten Typ unterstützen. Andernfalls muss die <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> -Implementierung `null`zurückgeben.  
  
 Jede <xref:System.ComponentModel.TypeConverter> Implementierung kann eine eigene Interpretation dessen haben, was eine gültige Zeichenfolge für eine Konvertierung darstellt, und kann auch die Typbeschreibung oder Kulturkontexte verwenden oder ignorieren, die als Parameter übergeben werden. Bei der WPF-XAML-Verarbeitung werden jedoch möglicherweise nicht in allen Fällen Werte an den Kontext der Typbeschreibung weitergegeben. Die auf `xml:lang` basierende Kultur wird möglicherweise auch nicht weitergegeben.  
  
> [!NOTE]
> Verwenden Sie auf gar keinen Fall die geschweiften Klammern,vor allem { , als ein mögliches Element Ihres Zeichenfolgenformats. Diese Zeichen sind als ein Eintrag reserviert und dienen dem Beenden einer Markuperweiterungssequenz.  
  
### <a name="implementing-convertto"></a>Implementieren von ConvertTo  
 <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> wird möglicherweise für die Serialisierungsunterstützung verwendet. Die Serialisierungsunterstützung durch <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> für Ihren benutzerdefinierten Typ und dessen Typkonverter ist nicht unbedingt erforderlich. Wenn Sie jedoch ein Steuerelement implementieren oder die Serialisierung als Bestandteil der Features oder zum Entwerfen Ihrer Klasse verwenden, sollten Sie <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>implementieren.  
  
 Um als <xref:System.ComponentModel.TypeConverter> Implementierung verwendet zu werden, <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> die XAML unterstützt, muss die Methode für diesen Konverter `value` eine Instanz des Typs (oder eines Werts) akzeptieren, die als Parameter unterstützt wird. Wenn `destinationType` der Parameter <xref:System.String>der Typ ist, muss das zurückgegebene Objekt als <xref:System.String>umgegossen werden können. Die zurückgegebene Zeichenfolge muss einen serialisierten Wert von `value`darstellen. Im Idealfall sollte das von Ihnen gewählte Serialisierungsformat in der <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> Lage sein, denselben Wert zu generieren, wenn diese Zeichenfolge an die Implementierung desselben Konverters übergeben wurde, ohne dass ein erheblicher Informationsverlust zu verursachen ist.  
  
 Wenn der Wert nicht serialisiert werden kann oder der <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> Konverter `null`die Serialisierung nicht unterstützt, muss die Implementierung zurückgegeben werden und darf in diesem Fall eine Ausnahme auslösen. Wenn Sie jedoch Ausnahmen auslösen, sollten Sie die Unfähigkeit melden, <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> diese Konvertierung als Teil Ihrer <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> Implementierung zu verwenden, damit die bewährte Methode unterstützt wird, zuerst zu überprüfen, um Ausnahmen zu vermeiden.  
  
 Wenn `destinationType` der Parameter <xref:System.String>nicht vom Typ ist, können Sie Ihre eigene Konverterbehandlung auswählen. In der Regel kehren Sie zur Basisimplementierungsbehandlung <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> zurück, die in der Basis eine bestimmte Ausnahme auslöst.  
  
### <a name="implementing-canconvertto"></a>Implementieren von CanConvertTo  
 Ihre Implementierung <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> sollte `true` für `destinationType` vom Typ <xref:System.String>zurückgeben und andernfalls die grundlegende Implementierung ableiten.  
  
### <a name="implementing-canconvertfrom"></a>Implementieren von CanConvertFrom  
 Ihre Implementierung <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A> sollte `true` für `sourceType` vom Typ <xref:System.String>zurückgeben und andernfalls die grundlegende Implementierung ableiten.  
  
<a name="Applying_the_TypeConverterAttribute"></a>
## <a name="applying-the-typeconverterattribute"></a>Anwenden von TypeConverterAttribute  
 Damit Ihr benutzerdefinierter Typkonverter von einem XAML-Prozessor als funktionierender Typkonverter für <xref:System.ComponentModel.TypeConverterAttribute> eine benutzerdefinierte Klasse verwendet werden kann, müssen Sie die auf Ihre Klassendefinition anwenden. Beim <xref:System.ComponentModel.TypeConverterAttribute.ConverterTypeName%2A> , den Sie über das Attribut angeben, muss es sich um den Typnamen Ihres benutzerdefinierten Typkonverters handeln. Wenn ein XAML-Prozessor nach Anwendung dieses Attributs Werte verarbeitet, bei denen der Eigenschaftstyp Ihren benutzerdefinierten Klassentyp verwendet, kann es Zeichenfolgen eingeben und Objektinstanzen zurückgeben.  
  
 Sie können auch einen Typkonverter auf Grundlage einzelner Eigenschaften bereitstellen. <xref:System.ComponentModel.TypeConverterAttribute> Anstatt eine auf die Klassendefinition anzuwenden, wenden Sie sie auf `get` / `set` eine Eigenschaftsdefinition an (die Hauptdefinition, nicht die Implementierungen darin). Der Eigenschaftstyp muss mit dem Typ übereinstimmen, der durch Ihren benutzerdefinierten Typkonverter verarbeitet wird. Wenn dieses Attribut angewendet ist, wenn ein XAML-Prozessor Werte dieser Eigenschaft verarbeitet, kann es Eingabezeichenfolgen verarbeiten und Objektinstanzen zurückgeben. Die Methode des Typkonverters pro Eigenschaft ist besonders nützlich, wenn Sie einen Eigenschaftstyp aus Microsoft .NET Framework <xref:System.ComponentModel.TypeConverterAttribute> oder einer anderen Bibliothek verwenden, in der Sie die Klassendefinition nicht steuern und dort keine anwenden können.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ComponentModel.TypeConverter>
- [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md)
- [Ausführliche Erläuterung der XAML-Syntax](xaml-syntax-in-detail.md)
