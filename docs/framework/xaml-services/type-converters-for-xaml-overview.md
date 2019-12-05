---
title: Übersicht über Typkonverter für XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], type converters
- XAML [XAML Services], TypeConverter
- type conversion for XAML [XAML Services]
ms.assetid: 51a65860-efcb-4fe0-95a0-1c679cde66b7
ms.openlocfilehash: 65210d8224b145ab23c7bc9ed76997c0892a5f59
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837258"
---
# <a name="type-converters-for-xaml-overview"></a>Übersicht über Typkonverter für XAML
Typkonverter stellen die Logik für einen Objekt-Writer bereit, der die Konvertierung von einer Zeichenfolge im XAML-Markup in bestimmte Objekte in einem Objektdiagramm vornimmt. In .NET Framework XAML Services muss der Typkonverter eine Klasse sein, die aus <xref:System.ComponentModel.TypeConverter>abgeleitet wird. Einige Konverter unterstützen zudem den XAML-Speicherpfad und können zum Serialisieren eines Objekts in ein Zeichenfolgenformular im Serialisierungsmarkup verwendet werden. In diesem Thema wird beschrieben, wie und wann Typkonverter in XAML aufgerufen werden. Zudem enthält es Implementierungsratschläge für die Methodenüberschreibungen von <xref:System.ComponentModel.TypeConverter>.  
  
<a name="type_conversion_concepts"></a>   
## <a name="type-conversion-concepts"></a>Typkonvertierungskonzepte  
 Im folgenden Abschnitt werden die grundlegenden Konzepte dahingehend erläutert, wie XAML Zeichenfolgen verwendet und inwiefern Objekt-Writer in .NET Framework XAML Services Typkonverter verwenden, um einige der Zeichenfolgenwerte zu verarbeiten, die in einer XAML-Quelle ermittelt werden.  
  
### <a name="xaml-and-string-values"></a>XAML- und Zeichenfolgenwerte  
 Wenn Sie eine Attributwert in einer XAML-Datei festlegen, handelt es sich beim anfänglichen Typ dieses Werts um eine Zeichenfolge in einem allgemeinen Sinn und um einen Zeichenfolgenattributwert in einem XML-Sinn. Auch andere Primitive wie <xref:System.Double> sind anfängliche Zeichenfolgen für einen XAML-Prozessor.  
  
 In den meisten Fällen benötigt ein XAML-Prozessor zwei Angaben, um einen Attributwert zu verarbeiten. Die erste Angabe ist der Werttyp der Eigenschaft, die festgelegt wird. Jede Zeichenfolge, die einen Attributwert definiert, und in XAML verarbeitet wird, muss schließlich umgewandelt werden oder zu einem Wert dieses Typs aufgelöst werden. Wenn es sich beim Wert um einen Primitiv handelt, den der XAML-Parser versteht (beispielsweise ein numerischer Wert), wird versucht, eine direkte Konvertierung der Zeichenfolge vorzunehmen. Wenn der Wert für das Attribut eine Aufzählung referenziert, wird der Name der angegebenen Zeichenfolge mit einer benannten Konstante in dieser Aufzählung abgeglichen. Wenn es sich beim Wert weder um ein Primitiv handelt, den der Parser versteht, noch um einen Konstantennamen aus einer Aufzählung, muss der zutreffende Typ einen Wert oder Verweis bereitstellen können, der auf einer konvertierten Zeichenfolge beruht.  
  
> [!NOTE]
> XAML-Sprachdirektiven verwenden keine Typkonverter.  
  
### <a name="type-converters-and-markup-extensions"></a>Typkonverter und Markuperweiterungen  
 Markuperweiterungen müssen durch einen XAML-Prozessor verarbeitet werden, bevor die Überprüfung auf Eigenschaftstyp und andere Überlegungen erfolgt. Wenn beispielsweise eine als Attribut festzulegende Eigenschaft normalerweise eine Typkonvertierung aufweist, in einem bestimmten Fall jedoch durch eine Markuperweiterungsverwendung festgelegt wird, dann wird das Markuperweiterungsverhalten zuerst festgelegt. Eine allgemeine Situation, in der eine Markuperweiterung erforderlich ist, besteht im Erstellen eines Verweises auf ein vorhandenes Objekt. In diesem Szenario kann ein zustandsloser Typkonverter nur eine neue Instanz genieren, die möglicherweise nicht gewünscht ist. Weitere Informationen zur Markuperweiterungen finden Sie unter [Markup Extensions for XAML Overview](markup-extensions-for-xaml-overview.md).  
  
### <a name="native-type-converters"></a>Systemeigene Typkonverter  
 In den WPF-und .net XAML-Dienst Implementierungen gibt es bestimmte CLR-Typen, die über eine systemeigene Typkonvertierungs Verarbeitung verfügen. diese CLR-Typen werden jedoch nicht als primitive angesehen. Ein Beispiel eines solchen Typs ist <xref:System.DateTime>. Ein Grund dafür besteht in der Funktionsweise der .NET Framework-Architektur: Der Typ <xref:System.DateTime> ist in „mscorlib“ definiert. Hierbei handelt es sich um die grundlegendste Bibliothek in .NET. Es ist nicht zulässig,<xref:System.DateTime> mit einem Attribut zu attribuieren, das aus einer anderen Assembly stammt, wodurch eine Abhängigkeit erschaffen wird (<xref:System.ComponentModel.TypeConverterAttribute> stammt aus dem System). Daher kann der gewöhnliche Typkonverter-Ermittlungsmechanismus durch die Attributierung nicht unterstützt werden. Stattdessen verfügt der XAML-Parser über eine Liste von Typen, für die die systemeigene Verarbeitung erforderlich ist, und diese Typen werden ähnlich wie echte Primitive verarbeitet. Im Fall von <xref:System.DateTime>umfasst diese Verarbeitung einen Aufruf von <xref:System.DateTime.Parse%2A>.  
  
<a name="Implementing_a_Type_Converter"></a>   
## <a name="implementing-a-type-converter"></a>Implementieren eines Typkonverters  
 In den folgenden Abschnitten wird die API der <xref:System.ComponentModel.TypeConverter> -Klasse erläutert.  
  
### <a name="typeconverter"></a>TypeConverter  
 Unter .NET Framework XAML Services sind alle Typkonverter, die für XAML-Zwecke verwendet werden, Klassen, die von der Basisklasse <xref:System.ComponentModel.TypeConverter>abgeleitet werden. Die Klasse <xref:System.ComponentModel.TypeConverter> war in Versionen von .NET Framework vorhanden, als es XAML noch nicht gab. Eins der ursprünglichen <xref:System.ComponentModel.TypeConverter> -Szenarien bestand darin, die Zeichenfolgenkonvertierung für Eigenschafts-Editoren in visuellen Designern bereitzustellen.  
  
 Für XAML wird die Rolle von <xref:System.ComponentModel.TypeConverter> erweitert. Für XAML-Zwecke ist <xref:System.ComponentModel.TypeConverter> die Basisklasse für das Bereitstellen von Unterstützung für bestimmte To- und From-Zeichenfolgekonvertierungen. Die From-Zeichenfolge ermöglicht das Analysieren eines Zeichenfolgenattributwerts aus XAML. Die To-Zeichenfolge ermöglicht das erneute Verarbeiten eines Laufzeitwerts einer bestimmten Objekteigenschaft zurück in ein Attribut in XAML für die Serialisierung.  
  
 <xref:System.ComponentModel.TypeConverter> definiert vier Member, die für die Konvertierungen von to- und from-Zeichenfolgen für XAML-Verarbeitungszwecke relevant sind:  
  
- <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A>  
  
- <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A>  
  
- <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>  
  
- <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>  
  
 Unter diesen Member lautet die wichtigste Methode <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>. Diese wandelt die Eingabezeichenfolge in den erforderlichen Objekttyp um. Die <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> -Methode kann implementiert werden, um einen größeren Typbereich in den gewünschten Zieltyp des Konverters zu konvertieren. Daher kann sie Zwecke erfüllen, die über XAML hinausgehen wie das Unterstützen von Laufzeitkonvertierungen. Für die XAML-Verwendung ist jedoch nur der Codepfad wichtig, der eine <xref:System.String> -Eingabe verarbeiten kann.  
  
 Die zweitwichtigste Methode ist <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>. Wenn eine Anwendung in eine Markupdarstellung (beispielsweise wenn die Speicherung in XAML als Datei erfolgt) umgewandelt wird, wird <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> im größeren Szenario eines XAML-Texts einbezogen, der von Writern in einer Markupdarstellung erstellt wird. In diesem Fall besteht der wichtige Codepfad für XAML darin, wenn der Aufrufer einen `destinationType` von <xref:System.String>weitergibt.  
  
 <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> und <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A> sind Unterstützungsmethoden, die verwendet werden, wenn ein Dienst die Funktionen der <xref:System.ComponentModel.TypeConverter> -Implementierung abfragt. Sie müssen diese Methoden implementieren, um `true` für typspezifische Klassen zurückzugeben, welche die entsprechenden Konvertierungsmethoden Ihres Konverters unterstützen. Für XAML-Zwecke bedeutet dies in der Regel den <xref:System.String> -Typ.  
  
### <a name="culture-information-and-type-converters-for-xaml"></a>Kulturinformations- und Typkonverter für XAML  
 Jede <xref:System.ComponentModel.TypeConverter> -Implementierung kann eindeutig interpretieren, was eine gültige Zeichenfolge für eine Konvertierung ist, und sie kann zudem die Typbeschreibung, die als Parameter weitergegeben wird, verwenden oder ignorieren. Eine wichtige Überlegung in Bezug auf die Kultur- und XAML-Typkonvertierung lautet wie folgt: Auch wenn die Verwendung von lokalisierbaren Zeichenfolgen als Attributwerten durch XAML unterstützt wird, können Sie diese lokalisierbaren Zeichenfolgen nicht als Typkonvertereingabe mit bestimmten Kulturanforderungen verwenden. Diese Einschränkung besteht, da Typkonverter für XAML-Attributwerte ein zwangsläufig festes XAML-Sprachverarbeitungsverhalten umfassen, in dem die `en-US` -Kultur verwendet wird. Weitere Informationen zu den Entwurfs Gründen für diese Einschränkung finden Sie in der Übersicht über die XAML-Sprachspezifikation ([\[MS-XAML\]](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))) oder unter [Übersicht über WPF-Globalisierung und-Lokalisierung](../wpf/advanced/wpf-globalization-and-localization-overview.md).  
  
 Beispielsweise können Kulturunterschiede in Kulturen ein Problem werden, in welchen anstelle eines Punkts als dezimales Trennzeichen ein Komma für die Zahlen im Zeichenfolgenformat verwendet wird. Diese Verwendung führt zu einem Konflikt mit dem Verhalten, das viele vorhandenen Typkonverter aufweisen, was in der Verwendung eines Kommas als Trennzeichen besteht. Das Weitergeben einer Kultur über `xml:lang` in der umgebenden XAML löst das Problem nicht.  
  
### <a name="implementing-convertfrom"></a>Implementieren von ConvertFrom  
 Damit die <xref:System.ComponentModel.TypeConverter> -Methode für diesen Konverter als eine <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> -Implementierung verwendet werden kann, die XAML unterstützt, muss sie eine Zeichenfolge als den `value` -Parameter akzeptieren. Wenn die Zeichenfolge ein gültiges Format aufweist und durch die <xref:System.ComponentModel.TypeConverter> -Implementierung konvertiert werden kann, muss das zurückgegebene Objekt eine Umwandlung zum Typ unterstützen, der durch die Eigenschaft erwartet wird. Andernfalls muss die <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> -Implementierung `null`zurückgeben.  
  
 Jede <xref:System.ComponentModel.TypeConverter> -Implementierung kann eindeutig interpretieren, was eine gültige Zeichenfolge für eine Konvertierung ausmacht, und sie kann zudem die Typbeschreibung oder Kulturkontexte verwenden oder ignorieren, die als Parameter weitergegeben werden. Bei der WPF-XAML-Verarbeitung werden jedoch möglicherweise nicht in allen Fällen Werte an den Typbeschreibungskontext weitergegeben, und wird möglicherweise zudem nicht die Kultur auf Grundlage von `xml:lang`weitergegeben.  
  
> [!NOTE]
> Verwenden Sie die geschweiften Klammern ({}), insbesondere die öffnende geschweifte Klammer ({), nicht als Element Ihres Zeichen folgen Formats. Diese Zeichen sind als ein Eintrag reserviert und dienen dem Beenden einer Markuperweiterungssequenz.  
  
 Es ist angemessen, eine Ausnahme auszulösen, wenn Ihr Typkonverter über Zugriff auf einen XAML-Dienst vom .NET Framework XAML Services-Objekt-Writer verfügen muss, der <xref:System.IServiceProvider.GetService%2A> -Aufruf, der für den Kontext ausgeführt wird, jedoch keinen Kontext für diesen Dienst zurückgibt.  
  
### <a name="implementing-convertto"></a>Implementieren von ConvertTo  
 <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> wird möglicherweise für die Serialisierungsunterstützung verwendet. Die Serialisierungsunterstützung durch <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> für Ihren benutzerdefinierten Typ und dessen Typkonverter ist nicht unbedingt erforderlich. Wenn Sie jedoch ein Steuerelement implementieren oder die Serialisierung als Bestandteil der Features oder zum Entwerfen Ihrer Klasse verwenden, sollten Sie <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>implementieren.  
  
 Damit die Verwendung als eine <xref:System.ComponentModel.TypeConverter> -Implementierung erfolgen kann, die XAML unterstützt, muss die <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> -Methode für diesen Konverter eine Instanz des Typs (oder eines Werts) akzeptieren, die als der `value` -Parameter unterstützt wird. Wenn der Parameter `destinationType` vom Typ <xref:System.String>ist, muss das zurückgegebene Objekt in der Lage sein, als <xref:System.String>umgewandelt zu werden. Die zurückgegebene Zeichenfolge muss einen serialisierten Wert von `value` darstellen. Im Idealfall sollte das von Ihnen ausgewählte Serialisierungsformat in der Lage sein, den gleichen Wert zu generieren, als wenn die Zeichenfolge an die <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> -Implementierung desselben Konverters weitergegeben werden würde, und zwar ohne erhebliche Informationsverluste.  
  
 Wenn der Wert weder serialisiert werden kann noch der Konverter die Serialisierung unterstützt, muss die <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> -Implementierung `null` zurückgeben und kann eine Ausnahme auslösen. Wenn Sie jedoch Ausnahmen auslösen, sollten Sie die Unfähigkeit in Bezug auf die Verwendung dieser Konvertierung als Bestandteil Ihrer <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> -Implementierung melden, sodass die bewährte Vorgehensweise in Bezug auf die Überprüfung mit <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> zunächst darin besteht, dass die Vermeidung von Ausnahmen unterstützt wird.  
  
 Wenn der Parameter `destinationType` nicht vom Typ <xref:System.String>ist, können Sie Ihre eigene Konverterverarbeitung auswählen. Für gewöhnlich nehmen Sie eine Zurücksetzung auf die grundlegende Implementierungsverarbeitung vor, wodurch in der Basis <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> eine bestimmte Ausnahme ausgelöst wird.  
  
 Es ist angemessen, eine Ausnahme auszulösen, wenn Ihr Typkonverter über Zugriff auf einen XAML-Dienst vom .NET Framework XAML Services-Objekt-Writer verfügen muss, der <xref:System.IServiceProvider.GetService%2A> -Aufruf, der für den Kontext ausgeführt wird, jedoch keinen Kontext für diesen Dienst zurückgibt.  
  
### <a name="implementing-canconvertfrom"></a>Implementieren von CanConvertFrom  
 Ihre Implementierung <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A> sollte `true` für `sourceType` vom Typ <xref:System.String> zurückgeben und andernfalls die grundlegende Implementierung ableiten. Lösen Sie keine Ausnahmen aus <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A> aus.  
  
### <a name="implementing-canconvertto"></a>Implementieren von CanConvertTo  
 Ihre Implementierung <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> sollte `true` für `destinationType` vom Typ <xref:System.String>zurückgeben und andernfalls die grundlegende Implementierung ableiten. Lösen Sie keine Ausnahmen aus <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> aus.  
  
<a name="Applying_the_TypeConverterAttribute"></a>   
## <a name="applying-the-typeconverterattribute"></a>Anwenden von TypeConverterAttribute  
 Damit Ihr benutzerdefinierter Typkonverter als der handelende Typkonverter für eine benutzerdefinierte Klasse durch .NET Framework XAML-Dienste verwendet werden kann, müssen Sie die <xref:System.ComponentModel.TypeConverterAttribute> auf Ihre Klassendefinition anwenden. Beim <xref:System.ComponentModel.TypeConverterAttribute.ConverterTypeName%2A> , den Sie über das Attribut angeben, muss es sich um den Typnamen Ihres benutzerdefinierten Typkonverters handeln. Beim Anwenden dieses Attributs, wenn ein XAML-Prozessor Werte verarbeitet, bei denen der Eigenschaftstyp Ihren benutzerdefinierten Klassentyp verwendet, kann es Zeichenfolgen eingeben und Objektinstanzen zurückgeben.  
  
 Sie können auch einen Typkonverter auf Grundlage einzelner Eigenschaften bereitstellen. Anstatt ein <xref:System.ComponentModel.TypeConverterAttribute> auf die Klassendefinition anzuwenden, wenden Sie es auf eine Eigenschafts Definition an (die Haupt Definition, nicht die `get`/`set` darin enthaltenen Implementierungen). Der Eigenschaftstyp muss mit dem Typ übereinstimmen, der durch Ihren benutzerdefinierten Typkonverter verarbeitet wird. Wenn dieses Attribut angewendet ist, wenn ein XAML-Prozessor Werte dieser Eigenschaft verarbeitet, kann es Eingabezeichenfolgen verarbeiten und Objektinstanzen zurückgeben. Die Typkonvertertechnik pro Eigenschaft ist besonders nützlich, wenn Sie einen Eigenschaftentyp aus Microsoft .NET Framework oder einer anderen Bibliothek verwenden möchten, in der Sie die Klassendefinition nicht steuern können und keine <xref:System.ComponentModel.TypeConverterAttribute> dort anwenden können.  
  
 Wenden Sie zum Bereitstellen eines Typkonvertierungsverhaltens für ein benutzerdefiniertes angefügtes Member <xref:System.ComponentModel.TypeConverterAttribute> auf die `Get` -Accessor-Methode des Implementierungsmusters für das angefügte Member an.  
  
<a name="accessing_service_provider_context_from_a_markup_extension_implementation"></a>   
## <a name="accessing-service-provider-context-from-a-markup-extension-implementation"></a>Zugriff auf den Dienstanbieterkontext über eine Markuperweiterungsimplementierung  
 Die verfügbaren Dienste sind für jeden Wertkonverter gleich. Der Unterschied besteht darin, wie jeder Wertkonverter den Dienstkontext empfängt. Der Zugriff auf Dienste und die verfügbaren Dienste werden im Thema [Type Converters and Markup Extensions for XAML](type-converters-and-markup-extensions-for-xaml.md)beschrieben.  
  
<a name="type_converters_in_the_xaml_node_stream"></a>   
## <a name="type-converters-in-the-xaml-node-stream"></a>Typkonverter im XAML-Knotenstream  
 Beim Verwenden eines XAML-Knotenstreams wurde weder die Aktion noch das Endergebnis eines Typkonverters bis dato ausgeführt. In einem Ladepfad muss die Attributzeichenfolge schließlich typkonvertiert werden, um Reste als ein Textwert im Start- und End-Member zu laden. Der schließlich für diesen Vorgang benötigte Typkonverter kann anhand der Eigenschaft <xref:System.Xaml.XamlMember.TypeConverter%2A?displayProperty=nameWithType> ermittelt werden. Das Abrufen eines gültigen Werts von <xref:System.Xaml.XamlMember.TypeConverter%2A?displayProperty=nameWithType> verlangt jedoch, über einen XAML-Schemakontext zu verfügen, worüber auf diese Informationen über das zugrunde liegende Member oder den Typ des Objektwerts, den das Member verwendet, zugegriffen werden kann. Für das Aufrufen des Typkonvertierungsverhaltens ist zudem der XAML-Schemakontext erforderlich, da dafür die Typzuordnung und das Erstellen einer Konverterinstanz erforderlich sind.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ComponentModel.TypeConverterAttribute>
- [Typkonverter und Markuperweiterungen für XAML](type-converters-and-markup-extensions-for-xaml.md)
- [Übersicht über XAML (WPF)](../../desktop-wpf/fundamentals/xaml.md)
