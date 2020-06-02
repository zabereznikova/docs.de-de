---
title: Serialisierung (C#)
ms.date: 01/02/2020
ms.openlocfilehash: b2532ccf281fdfaa951d56675066f1e239f9f480
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241980"
---
# <a name="serialization-c"></a>Serialisierung (C#)

Serialisierung ist der Prozess der Konvertierung eines Objekts in einen Bytestream, um das Objekt zu speichern oder in den Arbeitsspeicher, eine Datenbank oder eine Datei zu übertragen. Hauptzweck ist es, den Zustand eines Objekts zu speichern, um es bei Bedarf neu erstellen zu können. Der umgekehrte Vorgang wird als Deserialisierung bezeichnet.

## <a name="how-serialization-works"></a>Funktionsweise der Serialisierung

Diese Abbildung zeigt den gesamten Ablauf der Serialisierung:

![Grafik zur Serialisierung](./media/index/serialization-process.gif)

Das Objekt wird in einem Stream serialisiert, der die Daten enthält. Der Stream kann auch Informationen zum Objekttyp enthalten, z. B. zur Version, Kultur und zum Assemblynamen. Aus diesem Stream kann das Objekt in einer Datenbank, einer Datei oder einem Arbeitsspeicher gespeichert werden.

### <a name="uses-for-serialization"></a>Verwendungszwecke der Serialisierung

Mit der Serialisierung kann der Entwickler den Zustand eines Objekts speichern und das Objekt bei Bedarf neu erstellen. Die Serialisierung stellt sowohl Objektspeicher als auch Datenaustausch bereit. Mithilfe der Serialisierung kann ein Entwickler die folgenden Aktionen ausführen:

* Senden des Objekts an eine Remoteanwendung mithilfe eines Webdiensts
* Übergeben eines Objekts von einer Domäne zu einer anderen
* Übergeben eines Objekts über eine Firewall als JSON- oder XML-Zeichenfolge
* Verwalten von Sicherheits- und benutzerspezifischen Informationen über Anwendungen

## <a name="json-serialization"></a>JSON-Serialisierung

Der <xref:System.Text.Json>-Namespace enthält Klassen für die JSON-Serialisierung und -Deserialisierung (JavaScript Object Notation). JSON ist ein offener Standard, der häufig zum Freigeben von Daten über das Internet verwendet wird.

Bei der JSON-Serialisierung werden die öffentlichen Eigenschaften eines Objekts in eine Zeichenfolge, ein Bytearray oder Stream serialisiert, die der [RFC 8259 JSON-Spezifikation](https://tools.ietf.org/html/rfc8259) entsprechen. Zur Steuerung der Art und Weise, wie <xref:System.Text.Json.JsonSerializer> eine Instanz der Klasse serialisiert oder deserialisiert:

* Verwenden Sie ein <xref:System.Text.Json.JsonSerializerOptions>-Objekt.
* Wenden Sie die Attribute des <xref:System.Text.Json.Serialization>-Namespaces auf Klassen oder Eigenschaften an.
* [Implementieren Sie benutzerdefinierte Konverter](../../../../standard/serialization/system-text-json-converters-how-to.md).

## <a name="binary-and-xml-serialization"></a>Binär- und XML-Serialisierung

Der <xref:System.Runtime.Serialization>-Namespace enthält Klassen für die binäre Serialisierung und Deserialisierung sowie die XML-Serialisierung und -Deserialisierung.

Die binäre Serialisierung verwendet zum Generieren einer kompakten Serialisierung die binäre Codierung für den Speicher oder für socketbasierte Netzwerkstreams. Bei der binären Serialisierung werden alle Member einschließlich der schreibgeschützten Member serialisiert, und die Leistung wird verbessert.

Bei der XML-Serialisierung werden die öffentlichen Felder und Eigenschaften eines Objekts bzw. die Parameter und Rückgabewerte von Methoden in einen XML-Stream serialisiert, der einem bestimmtem XSD-Dokument (XML Schema Definition) entspricht. Die XML-Serialisierung führt zu stark typisierten Klassen mit öffentlichen Eigenschaften und Feldern, die in XML konvertiert werden. <xref:System.Xml.Serialization> enthält Klassen zum Serialisieren und Deserialisieren in XML. Sie wenden Attribute auf Klassen und Klassenmember an, um die Art der Serialisierung oder Deserialisierung einer Instanz der Klasse durch <xref:System.Xml.Serialization.XmlSerializer> zu steuern.

### <a name="making-an-object-serializable"></a>Aktivieren der Serialisierbarkeit eines Objekts

Für die Binär- oder XML-Serialisierung benötigen Sie:

* das zu serialisierende Objekt
* einen Stream mit dem serialisierten Objekt
* eine <xref:System.Runtime.Serialization.Formatter?displayProperty=fullName>-Instanz

Wenden Sie das Attribut <xref:System.SerializableAttribute> auf einen Typ an, um anzugeben, dass Instanzen des Typs serialisiert werden können. Eine Ausnahme wird ausgelöst, wenn Sie versuchen zu serialisieren, aber der Typ nicht über das Attribut <xref:System.SerializableAttribute> verfügt.

Wenden Sie das <xref:System.NonSerializedAttribute>-Attribut an, um zu verhindern, dass ein Feld serialisiert wird. Wenn ein Feld eines serialisierbaren Typs einen Zeiger, ein Handle oder eine andere Datenstruktur enthält, der/die für eine bestimmte Umgebung spezifisch ist, und das Feld in keiner anderen Umgebung sinnvoll wiederhergestellt werden kann, sollten Sie den Typ als nicht serialisierbar markieren.

Wenn eine serialisierte Klasse Verweise auf Objekte anderer Klassen enthält, die mit <xref:System.SerializableAttribute> markiert sind, werden diese Objekte ebenfalls serialisiert.

### <a name="basic-and-custom-serialization"></a>Einfache und benutzerdefinierte Serialisierung

Die Binär- und XML-Serialisierung kann auf zwei Arten ausgeführt werden: einfach und benutzerdefiniert.

Die einfache Serialisierung verwendet .NET, um ein Objekt automatisch zu serialisieren. Die einzige Voraussetzung ist, dass die Klasse über das <xref:System.SerializableAttribute>-Attribut verfügt. Das Attribut <xref:System.NonSerializedAttribute> kann verwendet werden, um die Serialisierung bestimmter Felder zu verhindern.

Wenn Sie einfache Serialisierung verwenden, kann die Versionsverwaltung von Objekten Probleme bereiten. Sie sollten benutzerdefinierte Serialisierung verwenden, wenn die Versionsverwaltung wichtig ist. Die einfache Serialisierung ist die einfachste Möglichkeit zur Serialisierung, bietet allerdings nicht viel Steuerungsmöglichkeiten für den Prozess.

Bei der benutzerdefinierten Serialisierung können Sie genau angeben, welche Objekte serialisiert werden und wie die Serialisierung erfolgt. Die Klasse muss als <xref:System.SerializableAttribute> markiert und in die <xref:System.Runtime.Serialization.ISerializable>-Schnittstelle implementiert sein. Wenn das Objekt auch benutzerdefiniert deserialisiert werden soll, verwenden Sie einen benutzerdefinierten Konstruktor.

## <a name="designer-serialization"></a>Designerserialisierung

Die Designerserialisierung ist eine besondere Form der Serialisierung, die auch die Art der Objektpersistenz einbezieht, die mit Entwicklungstools verknüpft ist. Bei der Designerserialisierung handelt es sich um den Prozess der Konvertierung eines Objektdiagramms in eine Quelldatei, die später zum Wiederherstellen des Objektdiagramms verwendet werden kann. Eine Quelldatei kann Code-, Markup- oder sogar SQL-Tabelleninformationen enthalten.

## <a name="related-topics-and-examples"></a><a name="BKMK_RelatedTopics"></a> Verwandte Themen und Beispiele  

Die [System.Text.Json-Übersicht](../../../../standard/serialization/system-text-json-overview.md) verdeutlicht, wie Sie die `System.Text.Json`-Bibliothek erhalten.

[Serialisieren und Deserialisieren von JSON-Daten in .NET](../../../../standard/serialization/system-text-json-how-to.md):
Veranschaulicht, wie Objektdaten in und aus JSON mithilfe der <xref:System.Text.Json.JsonSerializer>-Klasse gelesen und geschrieben werden.

[Exemplarische Vorgehensweise: Beibehalten eines Objekts in Visual Studio](walkthrough-persisting-an-object-in-visual-studio.md)  
Veranschaulicht, wie die Serialisierung verwendet werden kann, um die Daten eines Objekts zwischen Instanzen beizubehalten. Dadurch können Sie Werte speichern und abrufen, wenn das Objekt das nächste Mal instanziiert wird.

[Lesen von Objektdaten aus einer XML-Datei (C#)](how-to-read-object-data-from-an-xml-file.md)  
Zeigt, wie Objektdaten gelesen werden, die zuvor mithilfe der <xref:System.Xml.Serialization.XmlSerializer>-Klasse in eine XML-Datei geschrieben wurden.

[Schreiben von Objektdaten in eine XML-Datei (C#)](how-to-write-object-data-to-an-xml-file.md)  
Zeigt, wie ein Objekt aus einer Klasse mithilfe der <xref:System.Xml.Serialization.XmlSerializer>-Klasse in eine XML-Datei geschrieben wird.
