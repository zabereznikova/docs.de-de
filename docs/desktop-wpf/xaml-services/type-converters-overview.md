---
title: Übersicht über Typkonverter für XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], type converters
- XAML [XAML Services], TypeConverter
- type conversion for XAML [XAML Services]
ms.assetid: 51a65860-efcb-4fe0-95a0-1c679cde66b7
ms.openlocfilehash: c3c69aebacd140a14e74545d601c0207cb8de681
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432869"
---
# <a name="overview-of-type-converters-for-xaml"></a>Übersicht über Typkonverter für XAML

Typkonverter stellen die Logik für einen Objekt-Writer bereit, der die Konvertierung von einer Zeichenfolge im XAML-Markup in bestimmte Objekte in einem Objektdiagramm vornimmt. In .NET XAML Services muss der Typkonverter eine <xref:System.ComponentModel.TypeConverter>Klasse sein, die von abstammt. Einige Konverter unterstützen zudem den XAML-Speicherpfad und können zum Serialisieren eines Objekts in ein Zeichenfolgenformular im Serialisierungsmarkup verwendet werden. In diesem Thema wird beschrieben, wie und wann Typkonverter in XAML aufgerufen werden. Zudem enthält es Implementierungsratschläge für die Methodenüberschreibungen von <xref:System.ComponentModel.TypeConverter>.

## <a name="type-conversion-concepts"></a>Typkonvertierungskonzepte

In den folgenden Abschnitten werden grundlegende Konzepte dazu erläutert, wie XAML Zeichenfolgen verwendet und wie Objektwriter in .NET XAML Services Typkonverter verwenden, um einige der Zeichenfolgenwerte zu verarbeiten, die in einer XAML-Quelle auftreten.

### <a name="xaml-and-string-values"></a>XAML- und Zeichenfolgenwerte

Wenn Sie eine Attributwert in einer XAML-Datei festlegen, handelt es sich beim anfänglichen Typ dieses Werts um eine Zeichenfolge in einem allgemeinen Sinn und um einen Zeichenfolgenattributwert in einem XML-Sinn. Auch andere Primitive wie <xref:System.Double> sind anfängliche Zeichenfolgen für einen XAML-Prozessor.

In den meisten Fällen benötigt ein XAML-Prozessor zwei Angaben, um einen Attributwert zu verarbeiten. Die erste Angabe ist der Werttyp der Eigenschaft, die festgelegt wird. Jede Zeichenfolge, die einen Attributwert definiert, und in XAML verarbeitet wird, muss schließlich umgewandelt werden oder zu einem Wert dieses Typs aufgelöst werden. Wenn es sich beim Wert um einen Primitiv handelt, den der XAML-Parser versteht (beispielsweise ein numerischer Wert), wird versucht, eine direkte Konvertierung der Zeichenfolge vorzunehmen. Wenn der Wert für das Attribut eine Aufzählung referenziert, wird der Name der angegebenen Zeichenfolge mit einer benannten Konstante in dieser Aufzählung abgeglichen. Wenn es sich bei dem Wert nicht um einen vom Parser verstandenen Primitiven oder einen konstanten Namen aus einer Enumeration handelt, muss der anwendbare Typ in der Lage sein, einen Wert oder Verweis bereitzustellen, der auf einer konvertierten Zeichenfolge basiert.

> [!NOTE]
> XAML-Sprachdirektiven verwenden keine Typkonverter.

### <a name="type-converters-and-markup-extensions"></a>Typkonverter und Markuperweiterungen

Markuperweiterungen müssen durch einen XAML-Prozessor verarbeitet werden, bevor die Überprüfung auf Eigenschaftstyp und andere Überlegungen erfolgt. Wenn beispielsweise eine als Attribut festzulegende Eigenschaft normalerweise eine Typkonvertierung aufweist, in einem bestimmten Fall jedoch durch eine Markuperweiterungsverwendung festgelegt wird, dann wird das Markuperweiterungsverhalten zuerst festgelegt. Eine allgemeine Situation, in der eine Markuperweiterung erforderlich ist, besteht im Erstellen eines Verweises auf ein vorhandenes Objekt. In diesem Szenario kann ein zustandsloser Typkonverter nur eine neue Instanz genieren, die möglicherweise nicht gewünscht ist. Weitere Informationen zur Markuperweiterungen finden Sie unter [Markup Extensions for XAML Overview](markup-extensions-overview.md).

### <a name="native-type-converters"></a>Systemeigene Typkonverter

In den Implementierungen von Windows Presentation Foundation (WPF) und .NET XAML-Diensten gibt es bestimmte CLR-Typen, die über eine systemeigene Typkonvertierungsbehandlung verfügen. Diese CLR-Typen werden jedoch nicht konventionell als Primitive betrachtet. Ein Beispiel eines solchen Typs ist <xref:System.DateTime>. Ein Grund dafür besteht in der Funktionsweise der .NET Framework-Architektur: Der Typ <xref:System.DateTime> ist in „mscorlib“ definiert. Hierbei handelt es sich um die grundlegendste Bibliothek in .NET. <xref:System.DateTime>es ist nicht zulässig, mit einem Attribut zugeschrieben zu<xref:System.ComponentModel.TypeConverterAttribute> werden, das von einer anderen Assembly stammt, die eine Abhängigkeit einführt (ist von System). Daher kann der übliche Typkonverterermittlungsmechanismus durch Attributierung nicht unterstützt werden. Stattdessen verfügt der XAML-Parser über eine Liste von Typen, für die die systemeigene Verarbeitung erforderlich ist, und diese Typen werden ähnlich wie echte Primitive verarbeitet. Im Fall von <xref:System.DateTime>umfasst diese Verarbeitung einen Aufruf von <xref:System.DateTime.Parse%2A>.

## <a name="implementing-a-type-converter"></a>Implementieren eines Typkonverters

In den folgenden Abschnitten wird die API der <xref:System.ComponentModel.TypeConverter> -Klasse erläutert.

### <a name="typeconverter"></a>TypeConverter

Unter .NET XAML Services sind alle Typkonverter, die für XAML-Zwecke <xref:System.ComponentModel.TypeConverter>verwendet werden, Klassen, die von der Basisklasse abstammen. Die Klasse <xref:System.ComponentModel.TypeConverter> war in Versionen von .NET Framework vorhanden, als es XAML noch nicht gab. Eins der ursprünglichen <xref:System.ComponentModel.TypeConverter> -Szenarien bestand darin, die Zeichenfolgenkonvertierung für Eigenschafts-Editoren in visuellen Designern bereitzustellen.

Für XAML wird die Rolle von <xref:System.ComponentModel.TypeConverter> erweitert. Für XAML-Zwecke ist <xref:System.ComponentModel.TypeConverter> die Basisklasse für das Bereitstellen von Unterstützung für bestimmte To- und From-Zeichenfolgekonvertierungen. Die From-Zeichenfolge ermöglicht das Analysieren eines Zeichenfolgenattributwerts aus XAML. Die To-Zeichenfolge ermöglicht das erneute Verarbeiten eines Laufzeitwerts einer bestimmten Objekteigenschaft zurück in ein Attribut in XAML für die Serialisierung.

<xref:System.ComponentModel.TypeConverter> definiert vier Member, die für die Konvertierungen von to- und from-Zeichenfolgen für XAML-Verarbeitungszwecke relevant sind:

- <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A>

- <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A>

- <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>

- <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>

Unter diesen Member lautet die wichtigste Methode <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>. Diese wandelt die Eingabezeichenfolge in den erforderlichen Objekttyp um. Die <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> -Methode kann implementiert werden, um einen größeren Typbereich in den gewünschten Zieltyp des Konverters zu konvertieren. Daher kann sie Zwecke erfüllen, die über XAML hinausgehen wie das Unterstützen von Laufzeitkonvertierungen. Für die XAML-Verwendung ist jedoch nur der Codepfad wichtig, der eine <xref:System.String> -Eingabe verarbeiten kann.

Die zweitwichtigste Methode <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>ist . Wenn eine Anwendung in eine Markupdarstellung konvertiert wird (z. B. wenn <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> sie als Datei in XAML gespeichert wird), ist sie am größeren Szenario eines XAML-Textschreibers beteiligt, um eine Markupdarstellung zu erstellen. In diesem Fall besteht der wichtige Codepfad für XAML darin, wenn der Aufrufer einen `destinationType` von <xref:System.String>weitergibt.

<xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> und <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A> sind Unterstützungsmethoden, die verwendet werden, wenn ein Dienst die Funktionen der <xref:System.ComponentModel.TypeConverter> -Implementierung abfragt. Sie müssen diese Methoden implementieren, um `true` für typspezifische Klassen zurückzugeben, welche die entsprechenden Konvertierungsmethoden Ihres Konverters unterstützen. Für XAML-Zwecke bedeutet dies in der Regel den <xref:System.String> -Typ.

### <a name="culture-information-and-type-converters-for-xaml"></a>Kulturinformations- und Typkonverter für XAML

Jede <xref:System.ComponentModel.TypeConverter> -Implementierung kann eindeutig interpretieren, was eine gültige Zeichenfolge für eine Konvertierung ist, und sie kann zudem die Typbeschreibung, die als Parameter weitergegeben wird, verwenden oder ignorieren. Eine wichtige Überlegung in Bezug auf die Kultur- und XAML-Typkonvertierung lautet wie folgt: Auch wenn die Verwendung von lokalisierbaren Zeichenfolgen als Attributwerten durch XAML unterstützt wird, können Sie diese lokalisierbaren Zeichenfolgen nicht als Typkonvertereingabe mit bestimmten Kulturanforderungen verwenden. Diese Einschränkung besteht, da Typkonverter für XAML-Attributwerte ein zwangsläufig festes XAML-Sprachverarbeitungsverhalten umfassen, in dem die `en-US` -Kultur verwendet wird. Weitere Informationen zu den Entwurfsgründen für diese Einschränkung finden Sie in der XAML-Sprachspezifikation ([\[MS-XAML\]](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))) oder der [WPF-Globalisierungs- und Lokalisierungsübersicht](../../framework/wpf/advanced/wpf-globalization-and-localization-overview.md).

Beispielsweise können Kulturunterschiede in Kulturen ein Problem werden, in welchen anstelle eines Punkts als dezimales Trennzeichen ein Komma für die Zahlen im Zeichenfolgenformat verwendet wird. Diese Verwendung führt zu einem Konflikt mit dem Verhalten, das viele vorhandenen Typkonverter aufweisen, was in der Verwendung eines Kommas als Trennzeichen besteht. Das Weitergeben einer Kultur über `xml:lang` in der umgebenden XAML löst das Problem nicht.

### <a name="implementing-convertfrom"></a>Implementieren von ConvertFrom

Damit die <xref:System.ComponentModel.TypeConverter> -Methode für diesen Konverter als eine <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> -Implementierung verwendet werden kann, die XAML unterstützt, muss sie eine Zeichenfolge als den `value` -Parameter akzeptieren. Wenn die Zeichenfolge ein gültiges Format aufweist und durch die <xref:System.ComponentModel.TypeConverter> -Implementierung konvertiert werden kann, muss das zurückgegebene Objekt eine Umwandlung zum Typ unterstützen, der durch die Eigenschaft erwartet wird. Andernfalls muss die <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> -Implementierung `null`zurückgeben.

Jede <xref:System.ComponentModel.TypeConverter> -Implementierung kann eindeutig interpretieren, was eine gültige Zeichenfolge für eine Konvertierung ausmacht, und sie kann zudem die Typbeschreibung oder Kulturkontexte verwenden oder ignorieren, die als Parameter weitergegeben werden. Bei der WPF-XAML-Verarbeitung werden jedoch möglicherweise nicht in allen Fällen Werte an den Typbeschreibungskontext weitergegeben, und wird möglicherweise zudem nicht die Kultur auf Grundlage von `xml:lang`weitergegeben.

> [!NOTE]
> Verwenden Sie nicht die{}geschweiften Klammern ( ), insbesondere die öffnende geschweifte geschweifte Klammer () als Element des Zeichenfolgenformats. Diese Zeichen sind als ein Eintrag reserviert und dienen dem Beenden einer Markuperweiterungssequenz.

Es empfiehlt sich, eine Ausnahme auszulösen, wenn der Typkonverter Zugriff auf einen XAML-Dienst von .NET XAML Services-Objektschreiber haben muss, aber der Aufruf, der <xref:System.IServiceProvider.GetService%2A> für den Kontext erfolgt, gibt diesen Dienst nicht zurück.

### <a name="implementing-convertto"></a>Implementieren von ConvertTo

<xref:System.ComponentModel.TypeConverter.ConvertTo%2A> wird möglicherweise für die Serialisierungsunterstützung verwendet. Die Serialisierungsunterstützung durch <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> für Ihren benutzerdefinierten Typ und dessen Typkonverter ist nicht unbedingt erforderlich. Wenn Sie jedoch ein Steuerelement implementieren oder die Serialisierung als Bestandteil der Features oder zum Entwerfen Ihrer Klasse verwenden, sollten Sie <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>implementieren.

Damit die Verwendung als eine <xref:System.ComponentModel.TypeConverter> -Implementierung erfolgen kann, die XAML unterstützt, muss die <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> -Methode für diesen Konverter eine Instanz des Typs (oder eines Werts) akzeptieren, die als der `value` -Parameter unterstützt wird. Wenn der Parameter `destinationType` vom Typ <xref:System.String>ist, muss das zurückgegebene Objekt in der Lage sein, als <xref:System.String>umgewandelt zu werden. Die zurückgegebene Zeichenfolge muss einen serialisierten Wert von `value`darstellen. Im Idealfall sollte das von Ihnen ausgewählte Serialisierungsformat in der Lage sein, den gleichen Wert zu generieren, als wenn die Zeichenfolge an die <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> -Implementierung desselben Konverters weitergegeben werden würde, und zwar ohne erhebliche Informationsverluste.

Wenn der Wert weder serialisiert werden kann noch der Konverter die Serialisierung unterstützt, muss die <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> -Implementierung `null` zurückgeben und kann eine Ausnahme auslösen. Wenn Sie jedoch Ausnahmen auslösen, sollten Sie die Unfähigkeit in Bezug auf die Verwendung dieser Konvertierung als Bestandteil Ihrer <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> -Implementierung melden, sodass die bewährte Vorgehensweise in Bezug auf die Überprüfung mit <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> zunächst darin besteht, dass die Vermeidung von Ausnahmen unterstützt wird.

Wenn der Parameter `destinationType` nicht vom Typ <xref:System.String>ist, können Sie Ihre eigene Konverterverarbeitung auswählen. Für gewöhnlich nehmen Sie eine Zurücksetzung auf die grundlegende Implementierungsverarbeitung vor, wodurch in der Basis <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> eine bestimmte Ausnahme ausgelöst wird.

Es empfiehlt sich, eine Ausnahme auszulösen, wenn der Typkonverter Zugriff auf einen XAML-Dienst von .NET XAML Services-Objektschreiber haben muss, aber der Aufruf, der <xref:System.IServiceProvider.GetService%2A> für den Kontext erfolgt, gibt diesen Dienst nicht zurück.

### <a name="implementing-canconvertfrom"></a>Implementieren von CanConvertFrom

Ihre Implementierung <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A> sollte `true` für `sourceType` vom Typ <xref:System.String> zurückgeben und andernfalls die grundlegende Implementierung ableiten. Lösen Sie keine Ausnahmen aus <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A> aus.

### <a name="implementing-canconvertto"></a>Implementieren von CanConvertTo

Ihre Implementierung <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> sollte `true` für `destinationType` vom Typ <xref:System.String>zurückgeben und andernfalls die grundlegende Implementierung ableiten. Lösen Sie keine Ausnahmen aus <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> aus.

## <a name="applying-the-typeconverterattribute"></a>Anwenden von TypeConverterAttribute

Damit Ihr benutzerdefinierter Typkonverter als fungierender Typkonverter für eine benutzerdefinierte Klasse von <xref:System.ComponentModel.TypeConverterAttribute> .NET XAML Services verwendet werden kann, müssen Sie die auf Ihre Klassendefinition anwenden. Beim <xref:System.ComponentModel.TypeConverterAttribute.ConverterTypeName%2A> , den Sie über das Attribut angeben, muss es sich um den Typnamen Ihres benutzerdefinierten Typkonverters handeln. Beim Anwenden dieses Attributs, wenn ein XAML-Prozessor Werte verarbeitet, bei denen der Eigenschaftstyp Ihren benutzerdefinierten Klassentyp verwendet, kann es Zeichenfolgen eingeben und Objektinstanzen zurückgeben.

Sie können auch einen Typkonverter auf Grundlage einzelner Eigenschaften bereitstellen. <xref:System.ComponentModel.TypeConverterAttribute> Anstatt eine auf die Klassendefinition anzuwenden, wenden Sie sie auf `get` / `set` eine Eigenschaftsdefinition an (die Hauptdefinition, nicht die Implementierungen darin). Der Eigenschaftstyp muss mit dem Typ übereinstimmen, der durch Ihren benutzerdefinierten Typkonverter verarbeitet wird. Wenn dieses Attribut angewendet ist, wenn ein XAML-Prozessor Werte dieser Eigenschaft verarbeitet, kann es Eingabezeichenfolgen verarbeiten und Objektinstanzen zurückgeben. Die Methode des Typkonverters pro Eigenschaft ist nützlich, wenn Sie einen Eigenschaftstyp aus Microsoft .NET Framework <xref:System.ComponentModel.TypeConverterAttribute> oder einer anderen Bibliothek verwenden, in der Sie die Klassendefinition nicht steuern und dort keine anwenden können.

Wenden Sie zum Bereitstellen eines Typkonvertierungsverhaltens für ein benutzerdefiniertes angefügtes Member <xref:System.ComponentModel.TypeConverterAttribute> auf die `Get` -Accessor-Methode des Implementierungsmusters für das angefügte Member an.

## <a name="accessing-service-provider-context-from-a-markup-extension-implementation"></a>Zugriff auf den Dienstanbieterkontext über eine Markuperweiterungsimplementierung

Die verfügbaren Dienste sind für jeden Wertkonverter gleich. Der Unterschied besteht darin, wie jeder Wertkonverter den Dienstkontext empfängt. Der Zugriff auf Dienste und die verfügbaren Dienste wird im Thema [Type Converters and Markup Extensions for XAML](type-converters-and-markup-extensions.md)beschrieben.

## <a name="type-converters-in-the-xaml-node-stream"></a>Typkonverter im XAML-Knotenstream

Beim Verwenden eines XAML-Knotenstreams wurde weder die Aktion noch das Endergebnis eines Typkonverters bis dato ausgeführt. In einem Ladepfad muss die Attributzeichenfolge schließlich typkonvertiert werden, um Reste als ein Textwert im Start- und End-Member zu laden. Der schließlich für diesen Vorgang benötigte Typkonverter kann anhand der Eigenschaft <xref:System.Xaml.XamlMember.TypeConverter%2A?displayProperty=nameWithType> ermittelt werden. Das Abrufen eines gültigen Werts von <xref:System.Xaml.XamlMember.TypeConverter%2A?displayProperty=nameWithType> verlangt jedoch, über einen XAML-Schemakontext zu verfügen, worüber auf diese Informationen über das zugrunde liegende Member oder den Typ des Objektwerts, den das Member verwendet, zugegriffen werden kann. Für das Aufrufen des Typkonvertierungsverhaltens ist zudem der XAML-Schemakontext erforderlich, da dafür die Typzuordnung und das Erstellen einer Konverterinstanz erforderlich sind.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.ComponentModel.TypeConverterAttribute>
- [Typkonverter und Markuperweiterungen für XAML](type-converters-and-markup-extensions.md)
- [Übersicht über XAML (WPF)](../fundamentals/xaml.md)
