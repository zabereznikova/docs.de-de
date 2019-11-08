---
title: Grundlagen zu XAML-Knotenstreamstrukturen und -konzepten
ms.date: 03/30/2017
helpviewer_keywords:
- XAML node streams [XAML Services]
- nodes [XAML Services], XAML node stream
- XAML [XAML Services], XAML node streams
ms.assetid: 7c11abec-1075-474c-9d9b-778e5dab21c3
ms.openlocfilehash: 2c8093c3ef497bd836427f71098e62626f228e24
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73733393"
---
# <a name="understanding-xaml-node-stream-structures-and-concepts"></a>Grundlagen zu XAML-Knotenstreamstrukturen und -konzepten

Die in .NET Framework-XAML-Diensten implementierten XAML-Reader und XAML-Writer basieren auf dem Entwurfskonzept eines XAML-Knotenstreams. Der XAML-Knotenstream ist eine Konzeptualisierung eines Satzes von XAML-Knoten. In dieser Konzeptualisierung arbeitet ein XAML-Prozessor die Struktur der Knotenbeziehungen in der XAML einzeln ab. Dabei ist immer nur ein aktueller Datensatz oder eine aktuelle Position in einem geöffneten XAML-Knotenstream vorhanden, und viele Aspekte der APIs melden nur die von dieser Position verfügbaren Informationen. Der aktuelle Knoten in einem XAML-Knotenstream kann als Objekt, Member oder Wert beschrieben werden. Indem Sie XAML als einen XAML-Knotenstream behandeln, können XAML-Reader mit XAML-Writern kommunizieren und ein Programm aktivieren, um die Inhalte eines XAML-Knotenstreams während eines Ladepfad- oder Speicherpfadvorgangs, an dem XAML beteiligt ist, anzuzeigen, mit diesen zu interagieren oder sie zu verändern. Das XAML-Reader-und Writer-API-Design und das XAML-knotenstreamkonzept ähneln früheren verwandten Reader-und writerentwürfen und-Konzepten, wie z. b. dem XML-Dokumentobjektmodell (DOM) und der <xref:System.Xml.XmlReader>-und <xref:System.Xml.XmlWriter>-Klasse. In diesem Thema werden XAML-Knotenstreamkonzepte erläutert, und es wird beschrieben, wie Sie Routinen schreiben können, die mit XAML-Darstellungen auf XAML-Knotenebene interagieren.

<a name="loading_into_a_xaml_reader"></a>

## <a name="loading-xaml-into-a-xaml-reader"></a>Laden von XAML in einen XAML-Reader

Die <xref:System.Xaml.XamlReader> -Basisklasse deklariert kein bestimmtes Verfahren zum Laden der anfänglichen XAML in einen XAML-Reader. Stattdessen deklariert und implementiert eine abgeleitete Klasse die Ladetechnik, einschließlich der allgemeinen Eigenschaften und Einschränkungen der Eingabequelle für XAML. Ein <xref:System.Xaml.XamlObjectReader> liest z. B. ein Objektdiagramm beginnend mit der Eingabequelle eines einzelnen Objekts, das den Stamm oder die Basis darstellt. Anschließend erzeugt der <xref:System.Xaml.XamlObjectReader> einen XAML-Knotenstream aus dem Objektdiagramm.

Die bekannteste von .NET Framework-XAML-Diensten definierte <xref:System.Xaml.XamlReader> -Unterklasse ist <xref:System.Xaml.XamlXmlReader>. Der<xref:System.Xaml.XamlXmlReader> lädt die anfängliche XAML, indem eine Textdatei direkt über einen Stream oder Dateipfad oder indirekt über eine zugehörige Readerklasse wie <xref:System.IO.TextReader>geladen wird. Der <xref:System.Xaml.XamlReader> enthält somit die gesamte XAML-Eingabequelle, nachdem diese geladen wurde. Die <xref:System.Xaml.XamlReader> -Basis-API ist jedoch so aufgebaut, dass der Reader mit einem einzelnen Knoten der XAML interagiert. Beim erstmaligen Laden ist der erste gefundene einzelne Knoten der Stamm der XAML und das zugehörige Startobjekt.

### <a name="the-xaml-node-stream-concept"></a>XAML-Knotenstreamkonzept

Wenn Sie generell besser mit einem DOM-, strukturmetapher- oder abfragebasierten Ansatz für den Zugriff auf XML-basierte Technologien vertraut sind, ist es hilfreich, sich einen XAML-Knotenstream wie im Folgenden beschrieben vorzustellen. Stellen Sie sich vor, dass die geladene XAML ein DOM oder eine Struktur ist, in dem bzw. der jeder mögliche Knoten vollständig erweitert und anschließend linear dargestellt wird. Wenn Sie die Knoten durchlaufen, begegnen Ihnen möglicherweise Ebenen, die bei einem DOM relevant wären, vom XAML-Knotenstream aber nicht explizit verfolgt werden, weil diese Ebenenkonzepte für einen Knotenstream nicht relevant sind. Der Knotenstream hat eine "aktuelle" Position. Sofern Sie andere Teile des Streams jedoch nicht selbst als Verweise gespeichert haben, sind alle Aspekte des Knotenstreams mit Ausnahme der aktuellen Knotenposition nicht sichtbar.

Das XAML-Knotenstreamkonzept bietet den wichtigen Vorteil, dass Sie sicher sein können, dass die gesamte XAML-Darstellung verarbeitet wurde, wenn Sie den ganzen Knotenstream durchlaufen. Sie müssen sich keine Gedanken machen, dass bei einer Abfrage, einem DOM-Vorgang oder einem anderen nicht linearen Ansatz der Informationsverarbeitung ein Teil der vollständigen XAML-Darstellung übersehen wurde. Aus diesem Grund ist die Darstellung eines XAML-Knotenstreams sowohl für die Verbindung von XAML-Readern und XAML-Writern als auch die Bereitstellung eines Systems, in dem Sie Ihren eigenen, zwischen den Lese- und Schreibphasen eines XAML-Verarbeitungsvorgangs eingesetzten Prozess einfügen können, ideal geeignet. In vielen Fällen wird die Reihenfolge von Knoten im XAML-Knotenstream gegenüber der möglichen Reihenfolge im Quelltext, in der Binärdatei oder im Objektdiagramm bewusst von XAML-Readern optimiert oder neu geordnet. Durch dieses Verhalten wird eine XAML-Verarbeitungsarchitektur erzwungen, in der XAML-Writer nie im Knotenstream zurückgehen müssen. Im Idealfall sollten alle XAML-Schreibvorgänge in der Lage sein, basierend auf dem Schemakontext und der aktuellen Position des Knotenstreams zu arbeiten.

<a name="a_basic_reading_node_loop"></a>

## <a name="a-basic-reading-node-loop"></a>Grundlegende Leseknotenschleife

Eine grundlegende Leseknotenschleife zum Untersuchen eines XAML-Knotenstreams besteht aus den folgenden Konzepten. Bei den in diesem Thema erläuterten Knotenschleifen wird davon ausgegangen, dass Sie eine textbasierte, lesbare XAML-Datei mit <xref:System.Xaml.XamlXmlReader>lesen. Die Links in diesem Abschnitt verweisen auf die von <xref:System.Xaml.XamlXmlReader>implementierte XAML-Knotenschleifen-API.

- Stellen Sie sicher, dass Sie sich nicht am Ende des XAML-Knotenstreams befinden (überprüfen Sie <xref:System.Xaml.XamlXmlReader.IsEof%2A>, oder verwenden Sie den <xref:System.Xaml.XamlXmlReader.Read%2A> -Rückgabewert). Wenn Sie sich am Ende des Streams befinden, gibt es keinen aktuellen Knoten, und Sie sollten den Stream beenden.

- Überprüfen Sie, welchen Knotentyp der XAML-Knotenstream gerade bereitstellt, indem Sie <xref:System.Xaml.XamlXmlReader.NodeType%2A>aufrufen.

- Wenn Sie über einen zugehörigen, direkt verbundenen XAML-Objektwriter verfügen, rufen Sie an dieser Stelle im Allgemeinen <xref:System.Xaml.XamlWriter.WriteNode%2A> auf.

- Verwenden Sie abhängig davon, welcher <xref:System.Xaml.XamlNodeType> als aktueller Knoten oder aktueller Datensatz gemeldet wird, einen der folgenden Aufrufe, um Informationen zum Knoteninhalt zu erhalten:

  - Lautet der <xref:System.Xaml.XamlXmlReader.NodeType%2A> <xref:System.Xaml.XamlNodeType.StartMember> oder <xref:System.Xaml.XamlNodeType.EndMember>, rufen Sie <xref:System.Xaml.XamlXmlReader.Member%2A> auf, um <xref:System.Xaml.XamlMember> -Informationen zu einem Member zu erhalten. Da der Member eine <xref:System.Xaml.XamlDirective>sein könnte, ist er nicht zwingend ein konventioneller Member mit definiertem Typ des vorherigen Objekts. Ein auf ein Objekt angewendeter `x:Name` wird z. B. als XAML-Member angezeigt, bei dem <xref:System.Xaml.XamlMember.IsDirective%2A> "true" und der <xref:System.Xaml.XamlMember.Name%2A> des Members `Name`ist und andere Eigenschaften angeben, dass diese Direktive im XAML-Namespace der XAML-Sprache enthalten ist.

  - Lautet der <xref:System.Xaml.XamlXmlReader.NodeType%2A> <xref:System.Xaml.XamlNodeType.StartObject> oder <xref:System.Xaml.XamlNodeType.EndObject>, rufen Sie <xref:System.Xaml.XamlXmlReader.Type%2A> auf, um <xref:System.Xaml.XamlType> -Informationen zu einem Objekt zu erhalten.

  - Lautet der <xref:System.Xaml.XamlXmlReader.NodeType%2A> <xref:System.Xaml.XamlNodeType.Value>, rufen Sie <xref:System.Xaml.XamlXmlReader.Value%2A>auf. Ein Knoten ist nur ein Wert, wenn er der einfachste Ausdruck eines Werts für einen Member oder der Initialisierungstext für ein Objekt ist (dabei ist jedoch das weiter unten in diesem Thema beschriebene Typkonvertierungsverhalten zu beachten).

  - Lautet der <xref:System.Xaml.XamlXmlReader.NodeType%2A> <xref:System.Xaml.XamlNodeType.NamespaceDeclaration>, rufen Sie <xref:System.Xaml.XamlXmlReader.Namespace%2A> auf, um Namespaceinformationen für einen Namespaceknoten zu erhalten.

- Rufen Sie <xref:System.Xaml.XamlXmlReader.Read%2A> auf, um den XAML-Reader auf den nächsten Knoten im XAML-Knotenstream zu setzen, und wiederholen Sie die Schritte.

Der von XAML-Readern der .NET Framework-XAML-Dienste bereitgestellte XAML-Knotenstream stellt immer einen vollständigen, tiefen Durchlauf aller möglichen Knoten bereit. Typische Flusssteuerungstechniken für eine XAML-Knotenschleife umfassen die Definition eines Texts in `while (reader.Read())`und das Aktivieren von <xref:System.Xaml.XamlXmlReader.NodeType%2A> an jedem Knotenpunkt in der Knotenschleife.

Wenn sich der Knotenstream am Dateiende befindet, ist der aktuelle Knoten null.

Das folgende Beispiel zeigt die einfachste Schleife mit einem Reader und Writer.

```csharp
XamlXmlReader xxr = new XamlXmlReader(new StringReader(xamlStringToLoad));
//where xamlStringToLoad is a string of well formed XAML
XamlObjectWriter xow = new XamlObjectWriter(xxr.SchemaContext);
while (xxr.Read()) {
  xow.WriteNode(xxr);
}
```

In diesem grundlegenden Beispiel für eine Ladepfad-XAML-Knotenschleife werden XAML-Reader und XAML-Writer verbunden. Dies entspricht der Verwendung von <xref:System.Xaml.XamlServices.Parse%2A?displayProperty=nameWithType>. Aber diese grundlegende Struktur wird anschließend dem Lese- oder Schreibeszenario entsprechend erweitert. Im Folgenden sind einige mögliche Szenarien angegeben:

- <xref:System.Xaml.XamlXmlReader.NodeType%2A>aktivieren. Unterschiedliche Aktionen abhängig vom gelesenen Knotentyp ausführen.

- <xref:System.Xaml.XamlWriter.WriteNode%2A> nicht in jedem Fall aufrufen. <xref:System.Xaml.XamlWriter.WriteNode%2A> nur in einigen <xref:System.Xaml.XamlXmlReader.NodeType%2A> -Fällen aufrufen.

- Innerhalb der Logik für einen bestimmten Knotentyp die Einzelheiten dieses Knotens analysieren und entsprechend reagieren. Zum Beispiel könnten nur Objekte geschrieben werden, die von einem bestimmten XAML-Namespace stammen, und anschließend alle Objekte ausgelassen oder zurückgestellt werden, die nicht von diesem XAML-Namespace stammen. Es könnten auch beliebige XAML-Direktiven, die das XAML-System nicht als Teil der Memberverarbeitung unterstützt, ausgelassen oder andernfalls erneut verarbeitet werden.

- Ein benutzerdefiniertes <xref:System.Xaml.XamlObjectWriter> -Element definieren, von dem `Write*` -Methoden überschrieben werden und möglicherweise eine Typzuordnung ausgeführt wird, die den XAML-Schemakontext umgeht.

- Den <xref:System.Xaml.XamlXmlReader> mit einem nicht standardmäßigen XAML-Schemakontext erstellen, sodass benutzerdefinierte Unterschiede im XAML-Verhalten sowohl vom Reader als auch vom Writer verwendet werden.

### <a name="accessing-xaml-beyond-the-node-loop-concept"></a>Zugreifen auf XAML außerhalb des Knotenschleifenkonzepts

Es gibt andere Möglichkeiten als eine XAML-Knotenschleife, um mit einer XAML-Darstellung zu arbeiten. Es könnte z. B. ein XAML-Reader vorhanden sein, der einen indizierten Knoten lesen kann oder insbesondere direkt über `x:Name`, über `x:Uid`oder über andere Bezeichner auf Knoten zugreift. .NET Framework-XAML-Dienste bieten keine vollständige Implementierung, sondern stellen ein vorgeschlagenes Muster über Dienste und Unterstützungstypen bereit. Weitere Informationen finden Sie unter <xref:System.Xaml.IXamlIndexingReader> und <xref:System.Xaml.XamlNodeList>.

<a name="working_with_the_current_node"></a>

## <a name="working-with-the-current-node"></a>Arbeiten mit dem aktuellen Code

Bei den meisten Szenarien mit einer XAML-Knotenschleife werden die Knoten nicht nur gelesen. In den meisten Szenarien werden aktuelle Knoten verarbeitet, und jeder Knoten wird einzeln an eine Implementierung von <xref:System.Xaml.XamlWriter>übergeben.

Im typischen Ladepfadszenario erzeugt ein <xref:System.Xaml.XamlXmlReader> einen XAML-Knotenstream. Die XAML-Knoten werden entsprechend der Logik und dem XAML-Schemakontext verarbeitet und an einen <xref:System.Xaml.XamlObjectWriter>übergeben. Anschließend integrieren Sie das resultierende Objektdiagramm in die Anwendung oder das Framework.

In einem typischen Speicherpfadszenario liest ein <xref:System.Xaml.XamlObjectReader> das Objektdiagramm, einzelne XAML-Knoten werden verarbeitet, und ein <xref:System.Xaml.XamlXmlWriter> gibt das serialisierte Ergebnis als XAML-Textdatei aus. Der wichtigste Aspekt dabei ist, dass bei beiden Pfaden und Szenarien jeweils mit genau einem XAML-Knoten gearbeitet wird und die XAML-Knoten für die standardisierte Behandlung verfügbar sind, die im XAML-Typsystem und den .NET Framework-XAML-Dienste-APIs definiert ist.

### <a name="frames-and-scope"></a>Frames und Bereich

Eine XAML-Knotenschleife durchläuft einen XAML-Knotenstream linear. Der Knotenstream durchläuft Objekte, Member, die andere Objekte enthalten, usw. Oft ist es hilfreich, den Bereich innerhalb des XAML-Knotenstreams durch Implementieren eines Frame- und Stapelkonzepts nachzuverfolgen. Dies gilt besonders, wenn Sie den Knotenstream aktiv anpassen, währen Sie sich darin befinden. Die Frame- und Stapelunterstützung, die Sie als Teil der Knotenschleifenlogik implementieren, könnte die Bereiche `StartObject` (oder `GetObject`) und `EndObject` zählen, während Sie eine XAML-Knotenstruktur – bei Betrachtung aus der DOM-Perspektive – nach unten durchlaufen.

<a name="traversing_and_entering_object_nodes"></a>

## <a name="traversing-and-entering-object-nodes"></a>Durchlaufen und Eingeben von Objektknoten

Der erste von einem XAML-Reader geöffnete Knoten in einem Knotenstream ist der Startobjektknoten des Stammobjekts. Definitionsgemäß ist dieses Objekt immer ein einzelner Objektknoten ohne Peers. In einem realen XAML-Beispiel wird das Stammobjekt so definiert, dass es über eine oder mehrere Eigenschaften verfügt, die mehrere Objekte enthalten, und diese Eigenschaften verfügen über Memberknoten. Die Memberknoten verfügen dann über mindestens einen Objektknoten oder könnten stattdessen auch in einem Wertknoten beendet werden. Das Stammobjekt definiert normalerweise XAML-Namensbereiche, die syntaktisch als Attribute im XAML-Textmarkup zugewiesen werden, aber einem `Namescope` -Knotentyp in der XAML-Knotenstreamdarstellung entsprechen.

Sehen Sie sich das folgende XAML-Beispiel an (dies ist beliebige XAML, die von in .NET Framework vorhandenen Typen nicht unterstützt wird). Angenommen, in diesem Objektmodell gilt Folgendes: `FavorCollection` ist `List<T>` von `Favor`, `Balloon` und `NoiseMaker` können `Favor`zugewiesen werden, die `Balloon.Color` -Eigenschaft wird von einem `Color` -Objekt unterstützt (ähnlich der WPF-Definition von Farben als bekannte Farbnamen), und `Color` unterstützt einen Typkonverter für die Attributsyntax.

|XAML-Markup|Sich ergebender XAML-Knotenstream|
|-----------------|--------------------------------|
|`<Party`|`Namespace` -Knoten für `Party`|
|`xmlns="PartyXamlNamespace">`|`StartObject` -Knoten für `Party`|
|`<Party.Favors>`|`StartMember` -Knoten für `Party.Favors`|
||`StartObject` -Knoten für implizite `FavorCollection`|
||`StartMember` -Knoten für implizite `FavorCollection` -Elementeigenschaft|
|`<Balloon`|`StartObject` -Knoten für `Balloon`|
|`Color="Red"`|`StartMember` -Knoten für `Color`<br /><br /> `Value` -Knoten für Attributwertzeichenfolge `"Red"`<br /><br /> `EndMember` für `Color`|
|`HasHelium="True"`|`StartMember` -Knoten für `HasHelium`<br /><br /> `Value` -Knoten für Attributwertzeichenfolge `"True"`<br /><br /> `EndMember` für `HasHelium`|
|`>`|`EndObject` für `Balloon`|
|`<NoiseMaker>Loudest</NoiseMaker>`|`StartObject` -Knoten für `NoiseMaker`<br /><br /> `StartMember` -Knoten für `_Initialization`<br /><br /> `Value` -Knoten für Initialisierungswertzeichenfolge `"Loudest"`<br /><br /> `EndMember` -Knoten für `_Initialization`<br /><br /> `EndObject` für `NoiseMaker`|
||`EndMember` -Knoten für implizite `FavorCollection` -Elementeigenschaft|
||`EndObject` -Knoten für implizite `FavorCollection`|
|`</Party.Favors>`|`EndMember` für `Favors`|
|`</Party>`|`EndObject` für `Party`|

Im XAML-Knotenstream wird das folgende Verhalten verwendet:

- Wenn ein `Namespace` -Knoten vorhanden ist, wird er dem Stream unmittelbar vor dem `StartObject` hinzugefügt, von dem der XAML-Namespace mit `xmlns`deklariert wurde. Werfen Sie erneut einen Blick auf die vorherige Tabelle mit der XAML und dem Beispielknotenstream. Beachten Sie, dass die `StartObject` - und `Namespace` -Knoten im Vergleich zu ihren Deklarationspositionen im Textmarkup versetzt zu sein scheinen. Dies entspricht dem Verhalten, bei dem die Namespaceknoten immer vor dem Knoten angezeigt werden, für den sie im Knotenstream gelten. Dieser Entwurf begründet sich dadurch, dass die Namespaceinformationen für Objektwriter unerlässlich sind und bekannt sein müssen, bevor der Objektwriter versucht, die Typzuordnung auszuführen oder das Objekt anderweitig zu verarbeiten. Indem die XAML-Namespaceinformationen im Stream vor ihrem Anwendungsbereich platziert werden, ist es leichter, den Knotenstream immer in der dargestellten Reihenfolge zu verarbeiten.

- Wie bereits dargelegt, wird in den meisten realen Markupfällen zuerst mindestens ein `Namespace` -Knoten gelesen, wenn Knoten vom Start und nicht vom `StartObject` des Stamms durchlaufen werden.

- Einem `StartObject` -Knoten kann `StartMember`, `Value`oder direkt `EndObject`folgen. Ihm folgt nie sofort ein weiteres `StartObject`.

- Einem `StartMember` -Element kann `StartObject`, `Value`oder direkt `EndMember`folgen. Bei Membern, bei denen der Wert aus einem vorhandenen Wert des übergeordneten Objekts und nicht aus einem `GetObject`stammt, das einen neuen Wert instanziieren würde, kann ihm `StartObject` folgen. Ihm kann auch ein `Namespace` -Knoten folgen, der für ein späteres `StartObject`gilt. Ihm folgt nie sofort ein weiteres `StartMember`.

- Ein `Value` -Knoten stellt den Wert selbst dar. Es gibt kein "EndValue"-Element. Ihm kann nur ein `EndMember`folgen.

  - Der XAML-Initialisierungstext des Objekts, wie er von der Konstruktion verwendet werden könnte, führt nicht zu einer Object-Value-Struktur. Stattdessen wird ein dedizierter Memberknoten für einen Member mit dem Namen `_Initialization` erstellt und dieser Memberknoten enthält die Initialisierungswertzeichenfolge. Falls vorhanden, ist `_Initialization` immer der erste `StartMember`. `_Initialization` wird in einigen XAML-Dienst-Darstellungen möglicherweise mit dem XAML-Namensbereich der XAML-Sprache qualifiziert, um klarzustellen, dass `_Initialization` keine definierte Eigenschaft in Unterstützungstypen ist.

  - Eine Member-Wert-Kombination stellt eine Attributeinstellung des Werts dar. An der Verarbeitung dieses Werts kann ein Wertkonverter beteiligt sein, und der Wert ist eine einfache Zeichenfolge. Das wird jedoch erst ausgewertet, wenn ein XAML-Objektwriter diesen Knotenstream verarbeitet. Der XAML-Objektwriter besitzt den notwendigen XAML-Schemakontext, die Typsystemzuordnung und andere Unterstützung, die für Wertkonvertierungen benötigt wird.

- Einem `EndMember` -Knoten kann ein `StartMember` -Knoten für einen nachfolgenden Member oder ein `EndObject` -Knoten für den Memberbesitzer folgen.

- Einem `EndObject` -Knoten kann ein `EndMember` -Knoten folgen. In Fällen, in denen Objekte Peers in den Elementen einer Auflistung sind, kann ihm auch ein `StartObject` -Knoten folgen. Ihm kann auch ein `Namespace` -Knoten folgen, der für ein späteres `StartObject`gilt.

  - In dem besonderen Fall, dass ein gesamter Knotenstream geschlossen wird, folgt dem `EndObject` -Element des Stamms kein weiteres Element. Der Reader befindet sich jetzt am Dateiende, und <xref:System.Xaml.XamlReader.Read%2A> gibt `false`zurück.

<a name="value_converters_and_the_xaml_node_stream"></a>

## <a name="value-converters-and-the-xaml-node-stream"></a>Wertkonverter und der XAML-Knotenstream

Ein Wertkonverter ist ein allgemeiner Begriff für eine Markuperweiterung, einen Typkonverter (einschließlich Wertserialisierungsprogrammen) oder eine andere dedizierte Klasse, die über das XAML-Typsystem als Wertkonverter gemeldet wird. Im XAML-Knotenstream werden eine Typkonverterverwendung und eine Markuperweiterungsverwendung sehr unterschiedlich dargestellt.

### <a name="type-converters-in-the-xaml-node-stream"></a>Typkonverter im XAML-Knotenstream

Ein festgelegtes Attribut, das schließlich zu einer Typkonverterverwendung führt, wird im XAML-Knotenstream als Wert eines Members gemeldet. Der XAML-Knotenstream versucht nicht, ein Typkonverterinstanzobjekt zu erzeugen und den Wert an dieses Objekt zu übergeben. Zur Verwendung einer Konvertierungsimplementierung des Typkonverters muss der XAML-Schemakontext aufgerufen und zur Typzuordnung verwendet werden. Selbst die Bestimmung, welche Typkonverterklasse zum Verarbeiten des Werts verwendet werden soll, erfordert indirekt den XAML-Schemakontext. Wenn Sie den XAML-Standardschemakontext verwenden, sind diese Informationen im XAML-Typsystem verfügbar. Falls Sie die Informationen zur Typkonverterklasse auf der XAML-Knotenstreamebene vor der Verbindung mit einem XAML-Writer benötigen, können Sie sie aus den <xref:System.Xaml.XamlMember> -Informationen des festgelegten Members abrufen. Andernfalls sollte die Typkonvertereingabe im XAML-Knotenstream als einfacher Wert beibehalten werden, bis die übrigen Vorgänge, die das Typzuordnungssystem und den XAML-Schemakontext erfordern (z. B. die Objekterstellung durch einen XAML-Objektwriter), ausgeführt wurden.

Werfen Sie z. B. einen Blick auf die folgende Klassendefinitionsgliederung und die entsprechende XAML-Verwendung:

```csharp
public class BoardSizeConverter : TypeConverter {
  //converts from string to an int[2] by splitting on an "x" char
}
public class GameBoard {
  [TypeConverter(typeof(BoardSizeConverter))]
  public int[] BoardSize; //2x2 array, initialization not shown
}
```

```xaml
<GameBoard BoardSize="8x8"/>
```

Eine Textdarstellung des XAML-Knotenstreams für diese Verwendung könnte folgendermaßen aussehen:

Ein`StartObject` -Element mit <xref:System.Xaml.XamlType> , das `GameBoard`darstellt.

Ein`StartMember` -Element mit <xref:System.Xaml.XamlMember> , das `BoardSize`darstellt.

`Value` -Knoten mit Textzeichenfolge "`8x8`".

`EndMember` stimmt mit `BoardSize`

`EndObject` stimmt mit `GameBoard`

Beachten Sie, dass es keine Typkonverterinstanz in diesem Knotenstream gibt. Sie können Typkonverterinformationen jedoch abrufen, indem Sie <xref:System.Xaml.XamlMember.TypeConverter%2A?displayProperty=nameWithType> für den <xref:System.Xaml.XamlMember> für `BoardSize`aufrufen. Wenn ein gültiger XAML-Schemakontext vorhanden ist, können Sie die Konvertermethoden auch aufrufen, indem Sie eine Instanz von <xref:System.Xaml.Schema.XamlValueConverter%601.ConverterInstance%2A>abrufen.

### <a name="markup-extensions-in-the-xaml-node-stream"></a>Markuperweiterungen im XAML-Knotenstream

Eine Markuperweiterungsverwendung wird im XAML-Knotenstream als Objektknoten innerhalb eines Members gemeldet, wobei das Objekt eine Markuperweiterungsinstanz darstellt. Folglich wird eine Markuperweiterungsverwendung in der Knotenstreamdarstellung genauer dargestellt als eine Typkonverterverwendung, und sie enthält mehr Informationen. <xref:System.Xaml.XamlMember> -Informationen enthalten keine Informationen zur Markuperweiterung, da die Verwendung situationsbedingt ist und sich in jedem möglichen Markupfall ändert. Sie sind ebenso wie Typkonverter für Typen oder Member nicht dediziert oder implizit.

Markuperweiterungen werden in der Knotenstreamdarstellung auch dann als Objektknoten dargestellt, wenn die Markuperweiterungsverwendung im XAML-Textmarkup in Attributform erfolgte, was häufig der Fall ist. Markuperweiterungsverwendungen, bei denen ein explizites Objektelementformular verwendet wurde, werden auf dieselbe Weise behandelt.

Innerhalb eines Objektknotens für die Markuperweiterung sind möglicherweise Member dieser Markuperweiterung vorhanden. Die XAML-Knotenstreamdarstellung behält die Verwendung dieser Markuperweiterung bei, ganz gleich, ob es sich um eine Positionsparameterverwendung oder eine Verwendung mit expliziten benannten Parametern handelt.

Bei einer Positionsparameterverwendung enthält der XAML-Knotenstream eine durch die XAML-Sprache definierte Eigenschaft `_PositionalParameters` , von der die Verwendung aufgezeichnet wird. Diese Eigenschaft ist ein generisches <xref:System.Collections.Generic.List%601> -Element mit <xref:System.Object> -Einschränkung. Die Einschränkung ist ein Objekt und keine Zeichenfolge, da eine Positionsparameterverwendung u. U. geschachtelte Markuperweiterungsverwendungen enthalten könnte. Sie können die Liste durchlaufen und die Indexer für einzelne Listenwerte verwenden, um auf die Positionsparameter der Verwendung zuzugreifen.

Bei einer benannten Parameterverwendung wird jeder benannte Parameter als Memberknoten des Namens im Knotenstream dargestellt. Die Memberwerte sind nicht unbedingt Zeichenfolgen, da eine geschachtelte Markuperweiterungsverwendung vorhanden sein könnte.

Das`ProvideValue` -Element wird noch nicht von der Markuperweiterung aufgerufen. Es wird jedoch aufgerufen, wenn Sie einen XAML-Reader und einen XAML-Writer verbinden, sodass beim Untersuchen im Knotenstream `WriteEndObject` für den Markuperweiterungsknoten aufgerufen wird. Aus diesem Grund muss im Allgemeinen derselbe XAML-Schemakontext verfügbar sein wie für die Bildung des Objektdiagramms auf dem Ladepfad. Andernfalls kann `ProvideValue` in jeder Markuperweiterung Ausnahmen auslösen, da keine erwarteten Dienste verfügbar sind.

<a name="xaml_and_xml_languagedefined_members_in_the_xaml_node_stream"></a>

## <a name="xaml-and-xml-language-defined-members-in-the-xaml-node-stream"></a>Durch XAML- und XML-Sprache definierte Member im XAML-Knotenstream

Bestimmte Member werden aufgrund von Interpretationen und Konventionen eines XAML-Readers in einem XAML-Knotenstream implementiert und nicht durch eine explizite <xref:System.Xaml.XamlMember> -Suche oder -Konstruktion. Häufig sind diese Member XAML-Direktiven. In einigen Fällen wird die Direktive durch das Lesen der XAML im XAML-Knotenstream eingefügt. Anders ausgedrückt: der ursprüngliche Eingabe-XAML-Text hat die Member-Direktive nicht explizit angegeben, aber der XAML-Reader fügt die Direktive ein, um eine strukturelle XAML-Konvention zu erfüllen und Informationen im XAML-knotenstream zu melden, bevor diese Informationen verloren gehen.

In der folgenden Liste sind alle Fälle aufgeführt, in denen ein XAML-Reader voraussichtlich einen XAML-Memberknoten für eine Direktive einfügt, und es wird beschrieben, wie dieser Memberknoten in den .NET Framework-XAML-Dienstimplementierungen identifiziert wird.

- **Initialisierungstext für einen Objektknoten:** Der Name dieses Memberknotens ist `_Initialization`. Er stellt eine XAML-Direktive dar und ist im XAML-Namespace der XAML-Sprache definiert. Eine entsprechende statische Entität kann aus <xref:System.Xaml.XamlLanguage.Initialization%2A>abgerufen werden.

- **Positionsparameter für eine Markuperweiterung:** Der Name dieses Memberknotens ist `_PositionalParameters`, und er ist im XAML-Namespace der XAML-Sprache definiert. Er enthält immer eine generische Liste von Objekten, bei denen es sich um Positionsparameter handelt, die durch Trennung bei dem im Eingabe-XAML angegebenen `,` -Trennzeichen vorab getrennt werden. Eine statische Entität für die Positionsparameterdirektive kann aus <xref:System.Xaml.XamlLanguage.PositionalParameters%2A>abgerufen werden.

- **Unbekannter Inhalt:** Der Name dieses Memberknotens ist `_UnknownContent`. Streng genommen handelt es sich um ein <xref:System.Xaml.XamlDirective>-Element und ist im XAML-Namespace der XAML-Sprache definiert. Diese Direktive wird als Sentinel für Fälle verwendet, in denen ein XAML-Objektelement im Quell-XAML Inhalt aufweist, aber keine Inhaltseigenschaft im aktuell verfügbaren XAML-Schemakontext ermittelt werden kann. Sie können diesen Fall in einem XAML-Knotenstream erkennen, indem Sie ihn auf Member mit dem Namen `_UnknownContent`prüfen. Falls keine andere Aktion in einem Ladepfad-XAML-Knotenstream ausgeführt wird, wird der standardmäßige <xref:System.Xaml.XamlObjectWriter> bei versuchtem `WriteEndObject` ausgelöst, wenn der `_UnknownContent` -Member für ein Objekt gefunden wird. Der standardmäßige <xref:System.Xaml.XamlXmlWriter> wird nicht ausgelöst, und der Member wird als implizit behandelt. Sie können eine statische Entität für `_UnknownContent` von <xref:System.Xaml.XamlLanguage.UnknownContent%2A>abrufen.

- **Sammlungs Eigenschaft einer Auflistung:** Obwohl der unterstützende CLR-Typ einer Auflistungs Klasse, die für XAML verwendet wird, in der Regel über eine dedizierte benannte Eigenschaft verfügt, die die Sammel Elemente enthält, ist diese Eigenschaft einem XAML-Typsystem vor der Unterstützung der Typauflösung nicht bekannt. Stattdessen fügt der XAML-Knotenstream einen `Items` -Platzhalter als Member des XAML-Auflistungstyps ein. In der .NET Framework-XAML-Dienstimplementierung lautet der Name dieser Direktive/dieses Members im Knotenstream `_Items`. Eine Konstante für diese Direktive kann aus <xref:System.Xaml.XamlLanguage.Items%2A>abgerufen werden.

    Beachten Sie, dass ein XAML-knotenstream eine Items-Eigenschaft mit Elementen enthalten kann, die auf der Grundlage der Unterstützungstyp Auflösung und des XAML-Schema Kontexts nicht durchsucht werden können. Ein auf ein Objekt angewendeter

- **In XML definierte Member:** Die in XML definierten Member `xml:base`, `xml:lang` und `xml:space` werden als XAML-Direktiven mit den Namen `base`, `lang`und `space` in den .NET Framework-XAML-Dienstimplementierungen gemeldet. Der Namespace hierfür ist der XML-Namespace `http://www.w3.org/XML/1998/namespace`. Konstanten für jedes dieser Elemente können von <xref:System.Xaml.XamlLanguage>abgerufen werden.

## <a name="node-order"></a>Knotenreihenfolge

In einigen Fällen ändert der <xref:System.Xaml.XamlXmlReader> die Reihenfolge von XAML-Knoten im XAML-Knotenstream gegenüber der Reihenfolge, in der die Knoten bei der Anzeige im Markup oder der Verarbeitung als XML angezeigt werden. Dies geschieht, damit die Knoten so sortiert werden, dass ein <xref:System.Xaml.XamlObjectWriter> den Knotenstream nur vorwärts verarbeiten kann.  In den .NET Framework-XAML-Diensten ordnet der XAML-Reader Knoten neu, anstatt diese Aufgabe dem XAML-Writer zu überlassen. Dies dient zur Leistungsoptimierung für XAML-Objektwriterconsumer des Knotenstreams.

Bestimmte Direktiven sind speziell zum Bereitstellen weiterer Informationen für die Erstellung eines Objekts aus einem Objektelement vorgesehen. Diese Direktiven sind: `Initialization`, `PositionalParameters`, `TypeArguments`, `FactoryMethod`und `Arguments`. Die XAML-Reader der .NET Framework-XAML-Dienste versuchen, diese Direktiven als erste Member im Knotenstream nach dem `StartObject`eines Objekts zu platzieren. Die Gründe dafür werden im nächsten Abschnitt erläutert.

### <a name="xamlobjectwriter-behavior-and-node-order"></a>XamlObjectWriter-Verhalten und Knotenreihenfolge

Das`StartObject` für einen <xref:System.Xaml.XamlObjectWriter> ist nicht notwendigerweise ein Signal für den XAML-Objektwriter, die Objektinstanz sofort zu erstellen. XAML umfasst mehrere Sprachfunktionen, die es ermöglichen, ein Objekt mit zusätzlicher Eingabe zu initialisieren und sich nicht vollständig auf das Aufrufen eines Parameter losen Konstruktors zum Erstellen des anfänglichen Objekts zu verlassen und nur dann Eigenschaften festzulegen. Zu diesen Funktionen zählen: <xref:System.Windows.Markup.XamlDeferLoadAttribute>, Initialisierungstext, [x:TypeArguments](x-typearguments-directive.md), Positionsparameter einer Markuperweiterung, Factorymethoden und zugehörige [x:Arguments](x-arguments-directive.md) -Knoten (XAML 2009). In jedem dieser Fälle wird die tatsächliche Objekterstellung verzögert, und da der Knotenstream neu sortiert wird, kann der XAML-Objektwriter ein Verhalten verwenden, bei dem die Instanz tatsächlich jedes Mal erstellt wird, wenn ein Startmember gefunden wird, bei dem es sich nicht um eine Konstruktionsdirektive für diesen Objekttyp handelt.

### <a name="getobject"></a>GetObject

`GetObject` stellt einen XAML-Knoten dar, in dem ein XAML-Objektwriter den Wert der enthaltenden Eigenschaft des Objekts abrufen soll, anstatt ein neues Objekt zu erstellen. Ein typischer Fall, in dem ein `GetObject` -Knoten in einem XAML-Knotenstream vorkommt, ist ein Auflistungs- oder Wörterbuchobjekt, bei dem die enthaltende Eigenschaft im Objektmodell des Unterstützungstyps bewusst schreibgeschützt ist. In diesem Szenario wird die Auflistung oder das Wörterbuch häufig durch die Initialisierungslogik eines übergeordneten Typs erstellt und initialisiert (normalerweise leer).

## <a name="see-also"></a>Siehe auch

- <xref:System.Xaml.XamlObjectReader>
- [XAML Services](index.md) (XAML-Dienste)
- [XAML-Namespaces](xaml-namespaces-for-net-framework-xaml-services.md)
