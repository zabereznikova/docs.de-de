---
title: Verwendung von Zeichencodierungsklassen in .NET
description: Lernen Sie die Verwendung von Zeichencodierungsklassen in .NET kennen.
ms.date: 12/22/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encoding, understanding
- encoding, choosing
- encoding, fallback strategy
ms.assetid: bf6d9823-4c2d-48af-b280-919c5af66ae9
ms.openlocfilehash: 8e0cf961f4d6b481c354bdc854806f971458ce21
ms.sourcegitcommit: e09dbff13f0b21b569a101f3b3c5efa174aec204
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/01/2020
ms.locfileid: "82624942"
---
# <a name="how-to-use-character-encoding-classes-in-net"></a>Verwendung von Zeichencodierungsklassen in .NET

In diesem Artikel wird erläutert, wie Sie die Klassen verwenden, die .NET für die Codierung und Decodierung von Text unter Verwendung verschiedener Codierungsschemas bereitstellt. In den Anweisungen in diesem Artikel wird vorausgesetzt, dass Sie die [Einführung in die Zeichencodierung in .NET](character-encoding-introduction.md) gelesen haben.

## <a name="encoders-and-decoders"></a>Encoder und Decoder

.NET stellt Codierungsklassen bereit, die Text mithilfe von Codierungssystemen codieren und decodieren. Beispielsweise beschreibt die Klasse <xref:System.Text.UTF8Encoding> die Regeln für die Codierung in und die Decodierung aus UTF-8. .NET verwendet die UTF-16-Codierung (repräsentiert durch die <xref:System.Text.UnicodeEncoding>-Klasse) für `string`-Instanzen. Encoder und Decoder können auch in anderen Codierungsschemas eingesetzt werden.

Die Codierung und Decodierung können auch eine Validierung beinhalten. Die <xref:System.Text.UnicodeEncoding>-Klasse prüft z. B. alle `char`-Instanzen im Ersatzzeichenbereich, um sicherzustellen, dass sie in gültigen Ersatzzeichenpaaren vorliegen. Eine Fallbackstrategie legt fest, wie ein Encoder ungültige Zeichen behandelt oder wie ein Decoder ungültige Bytes behandelt.

> [!WARNING]
> Die .NET-Codierungsklassen bieten eine Möglichkeit, Zeichendaten zu speichern und zu konvertieren. Sie sollten nicht verwendet werden, um Binärdaten im Zeichenfolgenformat zu speichern. Abhängig von der verwendeten Codierung kann das Konvertieren von Binärdaten in das Zeichenfolgenformat mithilfe der Codierungsklassen zu unerwartetem Verhalten und ungenauen oder beschädigten Daten führen. Um Binärdaten in ein Zeichenfolgenformat zu konvertieren, verwenden Sie die <xref:System.Convert.ToBase64String%2A?displayProperty=nameWithType> -Methode.

Alle Zeichencodierungsklassen in .NET erben von der abstrakten <xref:System.Text.Encoding?displayProperty=nameWithType>-Klasse, die die Funktionen definiert, die für alle Zeichencodierungen gleich sind. Um auf die einzelnen in .NET implementierten Codierungsobjekte zuzugreifen, gehen Sie wie folgt vor:

- Verwenden Sie die statischen Eigenschaften der <xref:System.Text.Encoding>-Klasse, die Objekte zurückgibt, die die in .NET verfügbaren Standardzeichencodierungen darstellen (ASCII, UTF-7, UTF-8, UTF-16 und UTF-32). Zum Beispiel gibt die <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> -Eigenschaft ein <xref:System.Text.UnicodeEncoding> -Objekt zurück. Jedes Objekt verwendet einen Ersatzfallback für die Behandlung von Zeichenfolgen, die nicht codiert werden können, und von Bytes, die nicht decodiert werden können. Weitere Informationen finden Sie im Abschnitt [Replacement Fallback](../../../docs/standard/base-types/character-encoding.md#Replacement).

- Rufen Sie den Klassenkonstruktor der Codierung auf. Objekte für ASCII-, UTF-7-, UTF-8-, UTF-16- und UTF-32-Codierungen können auf diese Weise instanziiert werden. Standardmäßig verwendet jedes Objekt den Ersatzfallback zur Behandlung von Zeichenfolgen, die nicht codiert werden können, und von Bytes, die nicht decodiert werden können. Sie können aber angeben, dass stattdessen eine Ausnahme ausgelöst werden soll. Weitere Informationen finden Sie in [Replacement Fallback](../../../docs/standard/base-types/character-encoding.md#Replacement) und [Exception Fallback](../../../docs/standard/base-types/character-encoding.md#Exception).

- Rufen Sie den <xref:System.Text.Encoding.%23ctor%28System.Int32%29> -Konstruktor auf, und übergeben Sie eine ganze Zahl, die die Codierung darstellt. Standardcodierungsobjekte verwenden den Ersatzfallback, und Codepage- und DBCS (Doppelbyte-Zeichensatz)-Codierungsobjekte verwenden den Fallback mit ähnlichen Zeichen zur Behandlung von Zeichenfolgen, die nicht codiert werden können, und von Bytes, die nicht decodiert werden können. Weitere Informationen finden Sie in [Best-Fit Fallback](../../../docs/standard/base-types/character-encoding.md#BestFit).

- Rufen Sie die <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType>-Methode auf, die jede in .NET verfügbare Standard-, Codepage- oder DBCS-Codierung zurückgibt. Mithilfe von Überladungen können Sie sowohl für den Encoder als auch den Decoder ein Fallbackobjekt angeben.

Sie können Informationen über alle in .NET verfügbaren Codierungen abrufen, indem Sie die <xref:System.Text.Encoding.GetEncodings%2A?displayProperty=nameWithType>-Methode aufrufen. .NET unterstützt die in der folgenden Tabelle aufgeführten Zeichencodierungssysteme.

|Codierungsklasse|Beschreibung|
|--------------|-----------|
|[ASCII](xref:System.Text.ASCIIEncoding)|Codiert einen begrenzten Bereich von Zeichen mithilfe der unteren sieben Bits eines Bytes. Da diese Codierung nur Zeichenwerte von U+0000 bis U+007F unterstützt, ist sie in den meisten Fällen für weltweit einsetzbare Anwendungen nicht geeignet.|
|[UTF-7](xref:System.Text.UTF7Encoding)|Stellt Zeichen als Sequenzen von 7-Bit-ASCII-Zeichen dar. Nicht-ASCII-Unicode-Zeichen werden durch eine Escapesequenz von ASCII-Zeichen dargestellt. UTF-7 unterstützt Protokolle wie E-Mail und Newsgroup. UTF-7 ist jedoch nicht besonders sicher oder robust. In einigen Fällen kann die Änderung eines Bits die Interpretation einer gesamten UTF-7-Zeichenfolge radikal ändern. In anderen Fällen können verschiedene UTF-7-Zeichenfolgen denselben Text codieren. Bei Sequenzen, die Nicht-ASCII-Zeichen enthalten, benötigt UTF-7 mehr Speicherplatz als UTF-8, und auch die Codierung/Decodierung erfolgt langsamer. Daher sollten Sie nach Möglichkeit UTF-8 anstelle von UTF-7 verwenden.|
|[UTF-8](xref:System.Text.UTF8Encoding)|Stellt jeden Unicode-Codepunkt als eine Folge von einem bis vier Bytes dar. UTF-8 unterstützt 8-Bit-Datengrößen und funktioniert mit vielen vorhandenen Betriebssystemen. Im ASCII-Zeichenbereich ist UTF-8 mit der ASCII-Codierung identisch und ermöglicht einen umfangreicheren Zeichensatz. Für CJK-Skripts (Chinesisch, Japanisch, Koreanisch) können bei UTF-8 jedoch drei Bytes für jedes Zeichen erforderlich sein, sodass größere Datenmengen als bei UTF-16 entstehen. Manchmal wird die größere Datenmenge für den CJK-Bereich jedoch durch die Menge an ASCII-Daten, z. B. HTML-Tags, gerechtfertigt.|
|[UTF-16](xref:System.Text.UnicodeEncoding)|Stellt jeden Unicode-Codepunkt als Folge von einer oder zwei 16-Bit-Ganzzahlen dar. Die meisten allgemeinen Unicode-Zeichen erfordern nur einen UTF-16-Codepunkt. Ergänzende Unicode-Zeichen (U+10000 und höher) erfordern allerdings zwei UTF-16-Ersatzzeichen-Codepunkte. Sowohl Little-Endian- als auch Big-Endian-Bytereihenfolgen werden unterstützt. Die UTF-16-Codierung wird von der Common Language Runtime zur Darstellung von <xref:System.Char> -Werten und <xref:System.String> -Werten und vom Windows-Betriebssystem zur Darstellung von `WCHAR` -Werten verwendet.|
|[UTF-32](xref:System.Text.UTF32Encoding)|Stellt jeden Unicode-Codepunkt als 32-Bit-Ganzzahl dar. Sowohl Little-Endian- als auch Big-Endian-Bytereihenfolgen werden unterstützt. Die UTF-32-Codierung wird verwendet, wenn Anwendungen das Verhalten mit Ersatzzeichen-Codepunkten der UTF-16-Codierung unter Betriebssystemen vermeiden möchten, bei denen codierter Speicherplatz von zu großer Bedeutung ist. Einzelne Symbole, die in einer Anzeige gerendert werden, können dennoch mit mehr als einem UTF-32-Zeichen codiert werden.|
|ANSI/ISO-Codierung|Bietet Unterstützung für eine Vielzahl von Codepages. Unter Windows-Betriebssystemen werden Codepages verwendet, um eine bestimmte Sprache oder Sprachgruppe zu unterstützen. Eine Tabelle, in der die von .NET unterstützten Codepages aufgeführt werden, finden Sie unter der <xref:System.Text.Encoding>-Klasse. Sie können ein Codierungsobjekt für eine bestimmte Codepage abrufen, indem Sie die <xref:System.Text.Encoding.GetEncoding%28System.Int32%29?displayProperty=nameWithType> -Methode aufrufen. Eine Codepage enthält 256 Codepunkte und ist nullbasiert. Bei den meisten Codepages stellen die Codepunkte 0 bis 127 den ASCII-Zeichensatz dar. Die Codepunkte 128 bis 255 weichen zwischen den Codepages erheblich voneinander ab. Die Codepage 1252 enthält beispielsweise die Zeichen für lateinische Schreibsysteme, einschließlich Englisch, Deutsch und Französisch. Die letzten 128 Codepunkte der Codepage 1252 enthalten die Akzentzeichen. Die Codepage 1253 enthält die Zeichencodes für das griechische Schreibsystem. Die letzten 128 Codepunkte der Codepage 1253 enthalten die griechischen Zeichen. Daher kann eine auf ANSI-Codepages beruhende Anwendung Griechisch und Deutsch nicht in demselben Textstream speichern, sofern kein Bezeichner eingeschlossen ist, der die referenzierte Codepage angibt.|
|DBCS-Codierungen (Double-Byte Character Set, Doppelbyte-Zeichensatz)|Unterstützt Sprachen wie Chinesisch, Japanisch und Koreanisch, die mehr als 256 Zeichen enthalten. In einem DBCS wird jedes Zeichen durch ein Paar Codepunkte (ein Doppelbyte) dargestellt. Die <xref:System.Text.Encoding.IsSingleByte%2A?displayProperty=nameWithType> -Eigenschaft gibt für DBCS-Codierungen `false` zurück. Sie können ein Codierungsobjekt für einen bestimmten Doppelbyte-Zeichensatz abrufen, indem Sie die <xref:System.Text.Encoding.GetEncoding%28System.Int32%29?displayProperty=nameWithType> -Methode aufrufen. Wenn eine Anwendung DBCS-Daten behandelt, wird das erste Byte eines DBCS-Zeichens (das führende Byte) in Kombination mit dem unmittelbar nachfolgenden Byte verarbeitet. Da ein einzelnes Paar von DBCS-Codepunkten je nach Codepage unterschiedliche Zeichen darstellen kann, lässt auch dieses Schema keine Kombination zweier Sprachen wie Japanisch und Chinesisch in einem Datenstream zu.|

Diese Codierungen ermöglichen Ihnen die Verwendung von Unicode-Zeichen und von Codierungen, die in älteren Anwendungen am häufigsten verwendet werden. Außerdem können Sie eine benutzerdefinierte Codierung erstellen, indem Sie eine von <xref:System.Text.Encoding> erbende Klasse definieren und deren Member überschreiben.

## <a name="net-core-encoding-support"></a>.NET Core-Codierungsunterstützung

Standardmäßig stellt .NET Core keine anderen Codepagecodierungen als Codepage 28591 und Unicode-Codierungen (z.B. UTF-8 und UTF-16) bereit. Allerdings können Sie Ihrer App die Codepagecodierungen hinzufügen, die in Standard-Windows-Apps verwendet werden, die .NET als Ziel nutzen. Weitere Informationen finden Sie im Thema <xref:System.Text.CodePagesEncodingProvider>.

<a name="Selecting"></a>

## <a name="selecting-an-encoding-class"></a>Auswählen einer Encoding-Klasse

Wenn Sie die Möglichkeit haben, die von der Anwendung verwendete Codierung auszuwählen, sollten Sie eine Unicode-Codierung verwenden, vorzugsweise <xref:System.Text.UTF8Encoding> oder <xref:System.Text.UnicodeEncoding>. (.NET unterstützt auch eine dritte Unicode-Codierung, <xref:System.Text.UTF32Encoding>.)

Wenn Sie eine ASCII-Codierung (<xref:System.Text.ASCIIEncoding>) verwenden möchten, wählen Sie stattdessen <xref:System.Text.UTF8Encoding> . Die beiden Codierungen sind für den ASCII-Zeichensatz identisch. <xref:System.Text.UTF8Encoding> bietet allerdings die folgenden Vorteile:

- Alle Unicode-Zeichen können dargestellt werden, während <xref:System.Text.ASCIIEncoding> nur die Unicode-Zeichenwerte zwischen U+0000 und U+007F unterstützt.

- Weitere Vorteile sind die Fehlererkennung und die verbesserte Sicherheit.

- Die Geschwindigkeit wurde optimiert und sollte schneller sein als jede andere Codierung. Selbst bei Inhalten, bei denen es sich um reine ASCII-Daten handelt, erfolgen mit <xref:System.Text.UTF8Encoding> durchgeführte Operationen schneller als mit <xref:System.Text.ASCIIEncoding>durchgeführte Operationen.

Sie sollten daher in Erwägung ziehen, <xref:System.Text.ASCIIEncoding> nur für ältere Anwendungen zu verwenden. Allerdings kann <xref:System.Text.UTF8Encoding> auch für ältere Anwendungen aus folgenden Gründen die bessere Wahl sein (ausgehend von den Standardeinstellungen):

- Wenn die Anwendung Inhalte, die keine reinen ASCII-Daten sind, mit <xref:System.Text.ASCIIEncoding>codiert, wird jedes Nicht-ASCII-Zeichen als Fragezeichen (?) codiert. Wenn die Anwendung diese Daten anschließend decodiert, gehen die Informationen verloren.

- Wenn die Anwendung Inhalte, die keine reinen ASCII-Daten sind, mit <xref:System.Text.UTF8Encoding>codiert und als ASCII-Daten interpretiert, erscheint das Ergebnis unverständlich. Wenn die Anwendung dann jedoch einen UTF-8-Decoder verwendet, um diese Daten zu decodieren, durchlaufen sie einen erfolgreichen Roundtrip.

In einer Webanwendung sollten die Zeichen, die als Antwort auf eine Webanforderung an den Client gesendet werden, die auf dem Client verwendete Codierung widerspiegeln. In den meisten Fällen sollten Sie die <xref:System.Web.HttpResponse.ContentEncoding%2A?displayProperty=nameWithType> -Eigenschaft auf den Wert festlegen, der von der <xref:System.Web.HttpRequest.ContentEncoding%2A?displayProperty=nameWithType> -Eigenschaft zurückgegeben wird, um Text in der vom Benutzer erwarteten Codierung anzuzeigen.

<a name="Using"></a>

## <a name="using-an-encoding-object"></a>Verwenden eines Codierungsobjekts

Ein Codierer konvertiert eine Zeichenfolge (meistens Unicode-Zeichen) in die numerische Entsprechung (Byte). Beispielsweise können Sie einen ASCII-Encoder verwenden, um Unicode-Zeichen in ASCII zu konvertieren, damit sie in der Konsole angezeigt werden können. Um die Konvertierung auszuführen, rufen Sie die <xref:System.Text.Encoding.GetBytes%2A?displayProperty=nameWithType> -Methode auf. Wenn Sie vor Ausführung der Codierung ermitteln möchten, wie viele Bytes zum Speichern der codierten Zeichen benötigt werden, können Sie die <xref:System.Text.Encoding.GetByteCount%2A> -Methode aufrufen.

Im folgenden Beispiel wird ein einzelnes Bytearray verwendet, um Zeichenfolgen in zwei separaten Vorgängen zu codieren. Ein verwalteter Index gibt die Anfangsposition im Bytearray für die nächste Gruppe von ASCII-codierten Bytes an. Die <xref:System.Text.ASCIIEncoding.GetByteCount%28System.String%29?displayProperty=nameWithType> -Methode wird aufgerufen, um sicherzustellen, dass das Bytearray groß genug für die codierte Zeichenfolge ist. Dann wird die <xref:System.Text.ASCIIEncoding.GetBytes%28System.String%2CSystem.Int32%2CSystem.Int32%2CSystem.Byte%5B%5D%2CSystem.Int32%29?displayProperty=nameWithType> -Methode aufgerufen, um die Zeichen in der Zeichenfolge zu codieren.

[!code-csharp[Conceptual.Encoding#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.encoding/cs/getbytes1.cs#8)]
[!code-vb[Conceptual.Encoding#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.encoding/vb/getbytes1.vb#8)]

Ein Decoder konvertiert ein Bytearray, das eine spezifische Zeichencodierung darstellt, in einen Satz von Zeichen, d. h. entweder in ein Zeichenarray oder in eine Zeichenfolge. Um ein Bytearray in ein Zeichenarray zu decodieren, rufen Sie die <xref:System.Text.Encoding.GetChars%2A?displayProperty=nameWithType> -Methode auf. Um ein Bytearray in eine Zeichenfolge zu decodieren, rufen Sie die <xref:System.Text.Encoding.GetString%2A> -Methode auf. Wenn Sie vor Ausführung der Decodierung ermitteln möchten, wie viele Zeichen zum Speichern der decodierten Bytes benötigt werden, können Sie die <xref:System.Text.Encoding.GetCharCount%2A> -Methode aufrufen.

Im folgenden Beispiel werden drei Zeichenfolgen codiert und dann in einzelnes Array von Zeichen decodiert. Ein verwalteter Index gibt die Anfangsposition im Zeichenarray für die nächste Gruppe von decodierten Zeichen an. Die <xref:System.Text.ASCIIEncoding.GetCharCount%2A> -Methode wird aufgerufen, um sicherzustellen, dass das Zeichenarray groß genug für alle decodierten Zeichen ist. Dann wird die <xref:System.Text.ASCIIEncoding.GetChars%28System.Byte%5B%5D%2CSystem.Int32%2CSystem.Int32%2CSystem.Char%5B%5D%2CSystem.Int32%29?displayProperty=nameWithType> -Methode aufgerufen, um das Bytearray zu decodieren.

[!code-csharp[Conceptual.Encoding#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.encoding/cs/getchars1.cs#9)]
[!code-vb[Conceptual.Encoding#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.encoding/vb/getchars1.vb#9)]

Die Codierungs- und Decodierungsmethoden einer von <xref:System.Text.Encoding> abgeleiteten Klasse sind für die Behandlung eines vollständigen Satzes von Daten vorgesehen, d. h., alle zu codierenden oder decodierenden Daten werden in einem einzelnen Methodenaufruf angegeben. In einigen Fällen sind Daten jedoch in einem Stream verfügbar, und die zu codierenden und decodierenden Daten sind möglicherweise nur über separate Lesevorgänge verfügbar. Der Codierungs- oder Decodierungsvorgang muss hierbei jeden gespeicherten Zustand aus dem vorherigen Aufruf speichern. Methoden von Klassen, die von <xref:System.Text.Encoder> und <xref:System.Text.Decoder> abgeleitet sind, können Codierungs- und Decodierungsvorgänge behandeln, die mehrere Methodenaufrufe umfassen.

Ein <xref:System.Text.Encoder> -Objekt für eine bestimmte Codierung ist über die <xref:System.Text.Encoding.GetEncoder%2A?displayProperty=nameWithType> -Eigenschaft dieser Codierung verfügbar. Ein <xref:System.Text.Decoder> -Objekt für eine bestimmte Codierung ist über die <xref:System.Text.Encoding.GetDecoder%2A?displayProperty=nameWithType> -Eigenschaft dieser Codierung verfügbar. Bei Decodierungsvorgängen beinhalten die von <xref:System.Text.Decoder> abgeleiteten Klassen eine <xref:System.Text.Decoder.GetChars%2A?displayProperty=nameWithType> -Methode, jedoch keine Methode, die <xref:System.Text.Encoding.GetString%2A?displayProperty=nameWithType>entspricht.

Das folgende Beispiel veranschaulicht den Unterschied zwischen der Verwendung der <xref:System.Text.Encoding.GetString%2A?displayProperty=nameWithType> -Methode und der <xref:System.Text.Decoder.GetChars%2A?displayProperty=nameWithType> -Methode zum Decodieren eines Unicode-Bytearrays. Im Beispiel wird eine Zeichenfolge, die einige Unicode-Zeichen enthält, in eine Datei codiert. Anschließend werden die Zeichen mithilfe der zwei Decodierungsmethoden immer um je zehn Bytes decodiert. Da im zehnten und elften Byte ein Ersatzzeichenpaar auftritt, erfolgt die Decodierung mit separaten Methodenaufrufen. Die Ausgabe zeigt, dass die <xref:System.Text.Encoding.GetString%2A?displayProperty=nameWithType> -Methode die Bytes nicht ordnungsgemäß decodieren kann und sie stattdessen durch U+FFFD (REPLACEMENT CHARACTER) ersetzt. Die <xref:System.Text.Decoder.GetChars%2A?displayProperty=nameWithType> -Methode kann das Bytearray hingegen erfolgreich decodieren, um die ursprüngliche Zeichenfolge abzurufen.

[!code-csharp[Conceptual.Encoding#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.encoding/cs/stream1.cs#10)]
[!code-vb[Conceptual.Encoding#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.encoding/vb/stream1.vb#10)]

<a name="FallbackStrategy"></a>

## <a name="choosing-a-fallback-strategy"></a>Auswählen einer Fallbackstrategie

Wenn eine Methode versucht, ein Zeichen zu codieren oder zu decodieren, aber keine Zuordnung vorhanden ist, muss eine Fallbackstrategie implementiert werden. Diese legt fest, wie die fehlende Zuordnung behandelt werden soll. Es gibt drei Arten von Fallbackstrategien:

- Best-Fit Fallback

- Replacement Fallback

- Exception Fallback

> [!IMPORTANT]
> Bei Codierungsvorgängen treten Probleme am häufigsten dann auf, wenn ein Unicode-Zeichen keiner bestimmten Codepagecodierung zugeordnet werden kann. Zu den am häufigsten auftretenden Problem bei Decodierungsvorgängen gehört es, wenn ungültige Bytefolgen nicht in gültige Unicode-Zeichen übersetzt werden können. Aus diesen Gründen sollten Sie wissen, welche Fallbackstrategien von bestimmten Codierungsobjekten verwendet werden. Nach Möglichkeit sollten Sie die von einem Codierungsobjekt verwendete Fallbackstrategie beim Instanziieren des Objekts festlegen.

<a name="BestFit"></a>

### <a name="best-fit-fallback"></a>Best-Fit Fallback

Wenn ein Zeichen nicht über eine genaue Entsprechung in der Zielcodierung verfügt, kann der Encoder versuchen, eine Zuordnung zu einem ähnlichen Zeichen zu erstellen. (Ein Fallback mit ähnlichen Zeichen ist meist vielmehr ein Codierungs- als ein Decodierungsproblem. Es gibt sehr wenige Codepages, die Zeichen enthalten, die in Unicode nicht erfolgreich zugeordnet werden können.) Der Fallback mit ähnlichen Zeichen ist die Standardeinstellung für Codepage- und DBCS-Codierungen, die von der <xref:System.Text.Encoding.GetEncoding%28System.Int32%29?displayProperty=nameWithType>-Überladung und der <xref:System.Text.Encoding.GetEncoding%28System.String%29?displayProperty=nameWithType>-Überladung abgerufen werden.

> [!NOTE]
> Theoretisch unterstützen die in .NET bereitgestellten Unicode-Codierungsklassen (<xref:System.Text.UTF8Encoding>, <xref:System.Text.UnicodeEncoding> und <xref:System.Text.UTF32Encoding>) alle Zeichen in jedem Zeichensatz, sodass sie verwendet werden können, um Probleme beim Fallback mit ähnlichen Zeichen zu vermeiden.

Strategien mit ähnlichen Zeichen variieren für unterschiedliche Codepages. Beispielsweise werden bei einigen Codepages lateinische Zeichen in voller Breite den gängigeren halbbreiten lateinischen Zeichen zugeordnet. Bei anderen Codepages hingegen erfolgt diese Zuordnung nicht. Selbst bei einer aggressiven Strategie mit ähnlichen Zeichen besteht in einigen Codierungen für manche Zeichen keine denkbare Zuordnung. Ein chinesisches ideografisches Zeichen hat z. B. keine angemessene Zuordnung in der Codepage 1252. Im diesem Fall wird eine Ersatzzeichenfolge verwendet. Standardmäßig handelt es sich bei dieser Zeichenfolge um ein einzelnes QUESTION MARK (Fragezeichen, U+003F).

> [!NOTE]
> Strategien mit ähnlichen Zeichen sind nicht detailliert dokumentiert. Einige Codepages sind jedoch auf der Website des [Unicode-Konsortiums](https://www.unicode.org/Public/MAPPINGS/VENDORS/MICSFT/WindowsBestFit/) dokumentiert. Lesen Sie die **readme.txt**-Datei in diesem Ordner, um zu erfahren, wie die Zuordnungsdateien interpretiert werden.

Im folgenden Beispiel wird die Codepage 1252 (Windows-Codepage für westeuropäische Sprachen) verwendet, um eine Zuordnung mit ähnlichen Zeichen und deren Nachteile zu veranschaulichen. Die <xref:System.Text.Encoding.GetEncoding%28System.Int32%29?displayProperty=nameWithType> -Methode wird verwendet, um ein Codierungsobjekt für Codepage 1252 abzurufen. Standardmäßig wird eine Zuordnung mit ähnlichen Zeichen für nicht unterstützte Unicode-Zeichen verwendet. Im Beispiel wird eine Zeichenfolge instanziiert, die drei durch Leerzeichen getrennte Nicht-ASCII-Zeichen enthält: CIRCLED LATIN CAPITAL LETTER S (eingekreister lateinischer Großbuchstabe S, U+24C8), SUPERSCRIPT FIVE (hochgestellte Fünf, U+2075) und INFINITY (Unendlichkeit, U+221E). Die Ausgabe im Beispiel zeigt, dass die drei ursprünglichen Nicht-Leerzeichen bei der Codierung der Zeichenfolge durch QUESTION MARK (Fragezeichen, U+003F), DIGIT FIVE (Ziffer Fünf, U+0035) und DIGIT EIGHT (Ziffer Acht, U+0038) ersetzt. Insbesondere DIGIT EIGHT (Ziffer Acht) ist ein ungeeigneter Ersatz für das nicht unterstützte INFINITY-Zeichen (Unendlichkeit), und QUESTION MARK (Fragezeichen) weist darauf hin, dass für das ursprüngliche Zeichen keine Zuordnung verfügbar war.

[!code-csharp[Conceptual.Encoding#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.encoding/cs/bestfit1.cs#1)]
[!code-vb[Conceptual.Encoding#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.encoding/vb/bestfit1.vb#1)]

Die Zuordnung mit ähnlichen Zeichen ist das Standardverhalten für ein <xref:System.Text.Encoding> -Objekt, das Unicode-Daten in Codepagedaten codiert. Es gibt ältere Anwendungen, die auf diesem Verhalten basieren. In den meisten neuen Anwendungen sollte dieses Verhalten jedoch aus Sicherheitsgründen vermieden werden. Durch eine Codierung mit ähnlichen Zeichen sollten Anwendungen z. B. keinen Domänennamen ausdrücken.

> [!NOTE]
> Sie können für eine Codierung auch eine benutzerdefinierte Zuordnung mit einem Fallback mit ähnlichen Zeichen implementieren. Weitere Informationen finden Sie im Abschnitt [Implementing a Custom Fallback Strategy](../../../docs/standard/base-types/character-encoding.md#Custom) .

Wenn der Fallback mit ähnlichen Zeichen die Standardeinstellung für ein Codierungsobjekt ist, können Sie eine andere Fallbackstrategie auswählen, wenn Sie ein <xref:System.Text.Encoding> -Objekt abrufen, indem Sie die <xref:System.Text.Encoding.GetEncoding%28System.Int32%2CSystem.Text.EncoderFallback%2CSystem.Text.DecoderFallback%29?displayProperty=nameWithType> -Überladung aufrufen oder die <xref:System.Text.Encoding.GetEncoding%28System.String%2CSystem.Text.EncoderFallback%2CSystem.Text.DecoderFallback%29?displayProperty=nameWithType> -Überladung aufrufen. Der folgende Abschnitt enthält ein Beispiel, in dem jedes Zeichen, das Codepage 1252 nicht zugeordnet werden kann, durch ein Sternchen (*) ersetzt wird.

[!code-csharp[Conceptual.Encoding#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.encoding/cs/bestfit1a.cs#3)]
[!code-vb[Conceptual.Encoding#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.encoding/vb/bestfit1a.vb#3)]

<a name="Replacement"></a>

### <a name="replacement-fallback"></a>Replacement Fallback

Wenn ein Zeichen nicht über eine genaue Entsprechung im Zielschema verfügt und kein entsprechendes Zeichen für eine Zuordnung vorhanden ist, kann die Anwendung ein Ersatzzeichen oder eine Ersatzzeichenfolge angeben. Dies ist das Standardverhalten für den Unicode-Decoder, der jede 2-Byte-Sequenz ersetzt, die nicht mit REPLACEMENT_CHARACTER (Ersatzzeichen, U+FFFD) decodiert werden kann. Dies ist auch das Standardverhalten der <xref:System.Text.ASCIIEncoding> -Klasse, die jedes Zeichen, das nicht codiert oder decodiert werden kann, durch ein Fragezeichen ersetzt. Das folgende Beispiel veranschaulicht das Ersetzen von Zeichen für die Unicode-Zeichenfolge aus dem vorherigen Beispiel. Wie die Ausgabe zeigt, wird jedes Zeichen, das nicht in einen ASCII-Bytewert decodiert werden kann, durch 0x3F ersetzt, dem ASCII-Code für ein Fragezeichen.

[!code-csharp[Conceptual.Encoding#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.encoding/cs/replacementascii.cs#2)]
[!code-vb[Conceptual.Encoding#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.encoding/vb/replacementascii.vb#2)]

.NET enthält die <xref:System.Text.EncoderReplacementFallback>-Klasse und die <xref:System.Text.DecoderReplacementFallback>-Klasse, die eine Ersatzzeichenfolge verwenden, wenn in einem Codierungs- oder Decodierungsvorgang keine genaue Zuordnung für ein Zeichen möglich ist. Standardmäßig ist diese Ersatzzeichenfolge ein Fragezeichen. Sie können jedoch eine Klassenkonstruktorüberladung aufrufen, um eine andere Zeichenfolge auszuwählen. In der Regel handelt es sich bei der Ersatzzeichenfolge um ein einzelnes Zeichen. Dies ist aber nicht erforderlich. Im folgenden Beispiel wird das Verhalten des Encoders für Codepage 1252 geändert, indem ein <xref:System.Text.EncoderReplacementFallback> -Objekt instanziiert wird, das ein Sternchen (*) als Ersatzzeichenfolge verwendet.

[!code-csharp[Conceptual.Encoding#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.encoding/cs/bestfit1a.cs#3)]
[!code-vb[Conceptual.Encoding#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.encoding/vb/bestfit1a.vb#3)]

> [!NOTE]
> Sie können für eine Codierung auch eine Ersatzklasse implementieren. Weitere Informationen finden Sie im Abschnitt [Implementing a Custom Fallback Strategy](../../../docs/standard/base-types/character-encoding.md#Custom) .

Zusätzlich zu QUESTION MARK (Fragezeichen, U+003F) wird in der Regel REPLACEMENT CHARACTER (Unicode-Ersatzzeichen, U+FFFD) als Ersatzzeichenfolge verwendet, insbesondere bei der Decodierung von Bytesequenzen, die nicht erfolgreich in Unicode-Zeichen übersetzt werden können. Allerdings können Sie eine beliebige Ersatzzeichenfolge auswählen, die mehrere Zeichen enthalten kann.

<a name="Exception"></a>

### <a name="exception-fallback"></a>Exception Fallback

Anstatt einen Fallback mit ähnlichen Zeichen oder eine Ersatzzeichenfolge bereitzustellen, kann ein Encoder eine <xref:System.Text.EncoderFallbackException> auslösen, wenn die Codierung eines Satzes von Zeichen nicht möglich ist, und ein Decoder kann eine <xref:System.Text.DecoderFallbackException> auslösen, wenn ein Bytearray nicht decodiert werden kann. Um eine Ausnahme in Codierungs- und Decodierungsvorgängen auszulösen, übergeben Sie ein <xref:System.Text.EncoderExceptionFallback> -Objekt bzw. ein <xref:System.Text.DecoderExceptionFallback> -Objekt an die <xref:System.Text.Encoding.GetEncoding%28System.String%2CSystem.Text.EncoderFallback%2CSystem.Text.DecoderFallback%29?displayProperty=nameWithType> -Methode. Im folgenden Beispiel wird ein Ausnahmefallback mit der <xref:System.Text.ASCIIEncoding> -Klasse veranschaulicht.

[!code-csharp[Conceptual.Encoding#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.encoding/cs/exceptionascii.cs#4)]
[!code-vb[Conceptual.Encoding#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.encoding/vb/exceptionascii.vb#4)]

> [!NOTE]
> Sie können für einen Codierungsvorgang auch einen benutzerdefinierten Ausnahmehandler implementieren. Weitere Informationen finden Sie im Abschnitt [Implementing a Custom Fallback Strategy](../../../docs/standard/base-types/character-encoding.md#Custom) .

Das <xref:System.Text.EncoderFallbackException> -Objekt und das <xref:System.Text.DecoderFallbackException> -Objekt stellen die folgenden Informationen über die Bedingung bereit, durch die die Ausnahme ausgelöst wurde:

- Das <xref:System.Text.EncoderFallbackException> -Objekt enthält eine <xref:System.Text.EncoderFallbackException.IsUnknownSurrogate%2A> -Methode, die angibt, ob die Zeichen, die nicht codiert werden können, ein unbekanntes Ersatzzeichenpaar darstellen (in diesem Fall gibt die Methode `true`zurück) oder ob sie ein unbekanntes einzelnes Zeichen darstellen (in diesem Fall gibt die Methode `false`zurück). Die Zeichen im Ersatzzeichenpaar sind über die <xref:System.Text.EncoderFallbackException.CharUnknownHigh%2A?displayProperty=nameWithType> -Eigenschaft und die <xref:System.Text.EncoderFallbackException.CharUnknownLow%2A?displayProperty=nameWithType> -Eigenschaft verfügbar. Das unbekannte einzelne Zeichen ist über die <xref:System.Text.EncoderFallbackException.CharUnknown%2A?displayProperty=nameWithType> -Eigenschaft verfügbar. Die <xref:System.Text.EncoderFallbackException.Index%2A?displayProperty=nameWithType> -Eigenschaft gibt die Position in der Zeichenfolge an, an der das erste Zeichen gefunden wurde, das nicht codiert werden kann.

- Das <xref:System.Text.DecoderFallbackException> -Objekt enthält eine <xref:System.Text.DecoderFallbackException.BytesUnknown%2A> -Eigenschaft, die ein Bytearray zurückgibt, das nicht decodiert werden kann. Die <xref:System.Text.DecoderFallbackException.Index%2A?displayProperty=nameWithType> -Eigenschaft gibt die Anfangsposition der unbekannten Bytes an.

Obwohl das <xref:System.Text.EncoderFallbackException> -Objekt und das <xref:System.Text.DecoderFallbackException> -Objekt angemessene Diagnoseinformationen zu der Ausnahme bereitstellen, ermöglichen sie keinen Zugriff auf den Codierungs- oder Decodierungspuffer. Daher ist es nicht möglich, innerhalb der Codierungs- oder Decodierungsmethode ungültige Daten zu ersetzen oder zu korrigieren.

<a name="Custom"></a>

## <a name="implementing-a-custom-fallback-strategy"></a>Implementing a Custom Fallback Strategy

Neben der Zuordnung mit ähnlichen Zeichen, die intern von Codepages implementiert wird, beinhaltet .NET die folgenden Klassen für die Implementierung einer Fallbackstrategie:

- Verwenden Sie <xref:System.Text.EncoderReplacementFallback> und <xref:System.Text.EncoderReplacementFallbackBuffer> , um Zeichen in Codierungsvorgängen zu ersetzen.

- Verwenden Sie <xref:System.Text.DecoderReplacementFallback> und <xref:System.Text.DecoderReplacementFallbackBuffer> , um Zeichen in Decodierungsvorgängen zu ersetzen.

- Verwenden Sie <xref:System.Text.EncoderExceptionFallback> und <xref:System.Text.EncoderExceptionFallbackBuffer> , um eine <xref:System.Text.EncoderFallbackException> auszulösen, wenn ein Zeichen nicht codiert werden kann.

- Verwenden Sie <xref:System.Text.DecoderExceptionFallback> und <xref:System.Text.DecoderExceptionFallbackBuffer> , um eine <xref:System.Text.DecoderFallbackException> auszulösen, wenn ein Zeichen nicht decodiert werden kann.

Darüber hinaus können Sie eine benutzerdefinierte Lösung implementieren, die den Fallback mit ähnlichen Zeichen, den Ersatzfallback oder den Ausnahmefallback verwendet. Führen Sie hierzu folgende Schritte aus:

1. Leiten Sie für Codierungsvorgänge eine Klasse von <xref:System.Text.EncoderFallback> und für Decodierungsvorgänge eine Klasse von <xref:System.Text.DecoderFallback> ab.

2. Leiten Sie für Codierungsvorgänge eine Klasse von <xref:System.Text.EncoderFallbackBuffer> und für Decodierungsvorgänge eine Klasse von <xref:System.Text.DecoderFallbackBuffer> ab.

3. Wenn die vordefinierte <xref:System.Text.EncoderFallbackException> -Klasse und die vordefinierte <xref:System.Text.DecoderFallbackException> -Klasse für Ausnahmefallbacks nicht Ihren Anforderungen entspricht, leiten Sie eine Klasse von einem Ausnahmeobjekt ab, z. B. <xref:System.Exception> oder <xref:System.ArgumentException>.

### <a name="deriving-from-encoderfallback-or-decoderfallback"></a>Ableiten von EncoderFallback oder DecoderFallback

Um eine benutzerdefinierte Fallbacklösung zu implementieren, müssen Sie für Codierungsvorgänge eine Klasse erstellen, die von <xref:System.Text.EncoderFallback> erbt. Für Decodierungsvorgänge erstellen Sie eine Klasse, die von <xref:System.Text.DecoderFallback> erbt. Instanzen dieser Klassen werden an die <xref:System.Text.Encoding.GetEncoding%28System.String%2CSystem.Text.EncoderFallback%2CSystem.Text.DecoderFallback%29?displayProperty=nameWithType> -Methode übergeben und dienen als Vermittler zwischen der Codierungsklasse und der Fallbackimplementierung.

Beim Erstellen einer benutzerdefinierten Fallbacklösung für einen Encoder oder einen Decoder müssen Sie die folgenden Member implementieren:

- Die <xref:System.Text.EncoderFallback.MaxCharCount%2A?displayProperty=nameWithType> -Eigenschaft oder die <xref:System.Text.DecoderFallback.MaxCharCount%2A?displayProperty=nameWithType> -Eigenschaft, die die höchstmögliche Anzahl von Zeichen zurückgibt, die der Fallback mit ähnlichen Zeichen, der Ersatz- oder der Ausnahmefallback zurückgeben kann, um ein einzelnes Zeichen zu ersetzen. Für einen benutzerdefinierten Ausnahmefallback ist der Wert Null.

- Die <xref:System.Text.EncoderFallback.CreateFallbackBuffer%2A?displayProperty=nameWithType> -Methode oder die <xref:System.Text.DecoderFallback.CreateFallbackBuffer%2A?displayProperty=nameWithType> -Methode, die die benutzerdefinierte <xref:System.Text.EncoderFallbackBuffer> -Implementierung oder die benutzerdefinierte <xref:System.Text.DecoderFallbackBuffer> -Implementierung zurückgibt. Die Methode wird vom Encoder aufgerufen, wenn das erste Zeichen erkannt wird, das nicht erfolgreich codiert werden kann, oder vom Decoder, wenn das erste Byte erkannt wird, das nicht erfolgreich decodiert werden kann.

### <a name="deriving-from-encoderfallbackbuffer-or-decoderfallbackbuffer"></a>Ableiten von EncoderFallbackBuffer oder DecoderFallbackBuffer

Um eine benutzerdefinierte Fallbacklösung zu implementieren, müssen Sie für Codierungsvorgänge außerdem eine Klasse erstellen, die von <xref:System.Text.EncoderFallbackBuffer> erbt. Für Decodierungsvorgänge erstellen Sie eine Klasse, die von <xref:System.Text.DecoderFallbackBuffer> erbt. Instanzen dieser Klasse werden von der <xref:System.Text.EncoderFallback.CreateFallbackBuffer%2A> -Methode der <xref:System.Text.EncoderFallback> -Klasse und der <xref:System.Text.DecoderFallback> -Klasse zurückgegeben. Die <xref:System.Text.EncoderFallback.CreateFallbackBuffer%2A?displayProperty=nameWithType> -Methode wird vom Encoder aufgerufen, wenn das erste Zeichen erkannt wird, das nicht codiert werden kann. Die <xref:System.Text.DecoderFallback.CreateFallbackBuffer%2A?displayProperty=nameWithType> -Methode wird vom Decoder aufgerufen, wenn ein oder mehrere Bytes erkannt werden, die nicht decodiert werden können. Die <xref:System.Text.EncoderFallbackBuffer> -Klasse und die <xref:System.Text.DecoderFallbackBuffer> -Klasse stellen die Fallbackimplementierung bereit. Jede Instanz stellt einen Puffer dar, der die Fallbackzeichen enthält, die das Zeichen ersetzen, das nicht codiert werden kann, bzw. die die Bytesequenz ersetzen, die nicht decodiert werden kann.

Beim Erstellen einer benutzerdefinierten Fallbacklösung für einen Encoder oder einen Decoder müssen Sie die folgenden Member implementieren:

- <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> oder die <xref:System.Text.DecoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> -Methode. <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> wird vom Encoder aufgerufen, um dem Fallbackpuffer Informationen über das Zeichen bereitzustellen, das nicht codiert werden kann. Da das zu codierende Zeichen möglicherweise ein Ersatzzeichenpaar ist, wird diese Methode überladen. Einer Überladung werden das zu codierende Zeichen und der zugehörige Index in der Zeichenfolge übergeben. Der zweiten Überladung werden das hohe und das niedrige Ersatzzeichen zusammen mit dem Index in der Zeichenfolge übergeben. Die <xref:System.Text.DecoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> -Methode wird vom Decoder aufgerufen, um dem Fallbackpuffer Informationen über die Bytes bereitzustellen, die nicht decodiert werden können. Dieser Methode wird zusammen mit dem Index des ersten Bytes ein Bytearray übergeben, das nicht decodiert werden kann. Die Fallbackmethode sollte `true` zurückgeben, wenn der Fallbackpuffer ein ähnliches Zeichen oder ein bzw. mehrere Ersatzzeichen bereitstellen kann. Andernfalls sollte sie `false`zurückgeben. Bei einem Ausnahmefallback sollte die Fallbackmethode eine Ausnahme auslösen.

- Die <xref:System.Text.EncoderFallbackBuffer.GetNextChar%2A?displayProperty=nameWithType> -Methode oder die <xref:System.Text.DecoderFallbackBuffer.GetNextChar%2A?displayProperty=nameWithType> -Methode, die wiederholt vom Encoder oder Decoder aufgerufen wird, um das nächste Zeichen aus dem Fallbackpuffer abzurufen. Wenn alle Fallbackzeichen zurückgegeben wurden, sollte die Methode U+0000 zurückgeben.

- Die <xref:System.Text.EncoderFallbackBuffer.Remaining%2A?displayProperty=nameWithType> -Eigenschaft oder die <xref:System.Text.DecoderFallbackBuffer.Remaining%2A?displayProperty=nameWithType> -Eigenschaft, die die Anzahl der Zeichen zurückgibt, die im Fallbackpuffer verbleiben.

- Die <xref:System.Text.EncoderFallbackBuffer.MovePrevious%2A?displayProperty=nameWithType> -Methode oder die <xref:System.Text.DecoderFallbackBuffer.MovePrevious%2A?displayProperty=nameWithType> -Methode, die die aktuelle Position im Fallbackpuffer zum vorangehenden Zeichen verschiebt.

- Die <xref:System.Text.EncoderFallbackBuffer.Reset%2A?displayProperty=nameWithType> -Methode oder die <xref:System.Text.DecoderFallbackBuffer.Reset%2A?displayProperty=nameWithType> -Methode, die den Fallbackpuffer erneut initialisiert.

Wenn es sich bei der Fallbackimplementierung um einen Fallback mit ähnlichen Zeichen oder einen Ersatzfallback handelt, enthalten die von <xref:System.Text.EncoderFallbackBuffer> und <xref:System.Text.DecoderFallbackBuffer> abgeleiteten Klassen außerdem zwei private Instanzfelder: die genaue Anzahl von Zeichen im Puffer und der Index des nächsten Zeichens im Puffer, das zurückgegeben werden soll.

### <a name="an-encoderfallback-example"></a>Ein EncoderFallback-Beispiel

In einem früheren Beispiel wurde ein Ersatzfallback verwendet, um Unicode-Zeichen, die keinen ASCII-Zeichen entsprachen, durch ein Sternchen (*) zu ersetzen. Im folgenden Beispiel wird stattdessen eine benutzerdefinierte Implementierung mit ähnlichen Zeichen verwendet, um eine bessere Zuordnung von Nicht-ASCII-Zeichen zu ermöglichen.

Der folgende Code definiert eine von `CustomMapper` abgeleitete Klasse mit dem Namen <xref:System.Text.EncoderFallback> , um die Zuordnung mit ähnlichen Zeichen für Nicht-ASCII-Zeichen zu behandeln. Die `CreateFallbackBuffer` -Methode gibt ein `CustomMapperFallbackBuffer` -Objekt zurück, das die <xref:System.Text.EncoderFallbackBuffer> -Implementierung bereitstellt. Die `CustomMapper` -Klasse verwendet ein <xref:System.Collections.Generic.Dictionary%602> -Objekt, um die Zuordnungen von nicht unterstützten Unicode-Zeichen (Schlüsselwert) und den entsprechenden 8-Bit-Zeichen (die in zwei aufeinander folgenden Bytes in einer 64-Bit-Ganzzahl gespeichert sind) zu speichern. Um dem Fallbackpuffer diese Zuordnung zur Verfügung zu stellen, wird die `CustomMapper` -Instanz als Parameter an den `CustomMapperFallbackBuffer` -Klassenkonstruktor übergeben. Da die längste Zuordnung die Zeichenfolge "INF" für das Unicode-Zeichen U+221E ist, gibt die `MaxCharCount` -Eigenschaft 3 zurück.

[!code-csharp[Conceptual.Encoding#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.encoding/cs/custom1.cs#5)]
[!code-vb[Conceptual.Encoding#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.encoding/vb/custom1.vb#5)]

Der folgende Code definiert die `CustomMapperFallbackBuffer` -Klasse, die von <xref:System.Text.EncoderFallbackBuffer>abgeleitet wird. Das Wörterbuch, das die Zuordnung mit ähnlichen Zeichen enthält und in der `CustomMapper` -Instanz definiert ist, ist über den Klassenkonstruktor verfügbar. Die `Fallback` -Methode gibt `true` zurück, wenn eines der Unicode-Zeichen, das der ASCII-Encoder nicht codieren kann, im Zuordnungswörterbuch definiert ist. Andernfalls wird `false`zurückgegeben. Bei jedem Fallback gibt die private `count` -Variable die Anzahl von Zeichen an, die noch zurückgegeben werden. Die private `index` -Variable gibt die Position im Zeichenfolgenpuffer ( `charsToReturn`) des nächsten zurückzugebenden Zeichens an.

[!code-csharp[Conceptual.Encoding#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.encoding/cs/custom1.cs#6)]
[!code-vb[Conceptual.Encoding#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.encoding/vb/custom1.vb#6)]

Dann instanziiert der folgende Code das `CustomMapper` -Objekt und übergibt eine Instanz dieses Objekts an die <xref:System.Text.Encoding.GetEncoding%28System.String%2CSystem.Text.EncoderFallback%2CSystem.Text.DecoderFallback%29?displayProperty=nameWithType> -Methode. Die Ausgabe zeigt, dass die Fallbackimplementierung mit ähnlichen Zeichen die drei Nicht-ASCII-Zeichen in der ursprünglichen Zeichenfolge erfolgreich behandelt.

[!code-csharp[Conceptual.Encoding#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.encoding/cs/custom1.cs#7)]
[!code-vb[Conceptual.Encoding#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.encoding/vb/custom1.vb#7)]

## <a name="see-also"></a>Siehe auch

- [Einführung in die Zeichencodierung in .NET](character-encoding-introduction.md)
- <xref:System.Text.Encoder>
- <xref:System.Text.Decoder>
- <xref:System.Text.DecoderFallback>
- <xref:System.Text.Encoding>
- <xref:System.Text.EncoderFallback>
- [Globalisierung und Lokalisierung](../../../docs/standard/globalization-localization/index.md)
