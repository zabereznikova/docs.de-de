---
title: Details der XML-Serialisierung
description: Durch Serialisierung wird ein Objekt in ein Format konvertiert, das transportiert werden kann. Dieser Artikel bietet eine Übersicht über die XML-Serialisierung und die XmlSerializer-Klasse.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XML serialization, about XML serialization
- ICollection interface, serializing
- XmlSerializer class, serializing
- serialization, about serialization
- DataSet class, serializing
- XML Schema, serializing
ms.assetid: 8c63200d-db63-4a03-a93d-21641623df62
ms.openlocfilehash: 2971f5bbd587dabb62d095da3fef0b428ea9f039
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "93282286"
---
# <a name="xml-serialization"></a>XML-Serialisierung

Unter Serialisierung wird das Konvertieren des Zustands eines Objekts in eine Form verstanden, die sofort transportiert werden kann. Beispielsweise können Sie ein Objekt serialisieren und mittels HTTP über das Internet zwischen einem Client und einem Server transportieren. Bei der Deserialisierung wird das Objekt dagegen aus dem Stream rekonstruiert.

 Die XML-Serialisierung serialisiert nur die öffentlichen Felder und die Eigenschaftenwerte eines Objekts in einen XML-Stream. Bei der XML-Serialisierung werden keine Typinformationen eingeschlossen. Wenn beispielsweise ein **Book** -Objekt gegeben ist, das im **Library** -Namespace existiert, ist nicht garantiert, dass es in ein Objekt des gleichen Typs deserialisiert wird.

> [!NOTE]
> Methoden, Indexer, private Felder und schreibgeschützte Eigenschaften(ausgenommen schreibgeschützte Auflistungen) werden bei der XML-Serialisierung nicht konvertiert. Verwenden Sie <xref:System.Runtime.Serialization.DataContractSerializer> statt der XML-Serialisierung, wenn alle öffentlichen und privaten Felder und Eigenschaften eines Objekts serialisiert werden sollen.

 Bei der XML-Serialisierung ist die <xref:System.Xml.Serialization.XmlSerializer>-Klasse die zentrale Klasse, und die wichtigsten Methoden dieser Klasse sind die **Serialize** -Methode und die **Deserialize** -Methode. <xref:System.Xml.Serialization.XmlSerializer> erstellt C#-Dateien und kompiliert sie in DLL-Dateien, um diese Serialisierung auszuführen. Das [XML Serializer Generator-Tool (Sgen.exe)](xml-serializer-generator-tool-sgen-exe.md) ist dafür konzipiert, diese Serialisierungsassemblys vorab zu erzeugen, die zusammen mit der Anwendung bereitgestellt werden sollen, und die Startleistung zu verbessern. Der von der Klasse **XmlSerializer** generierte XML-Stream entspricht der [Empfehlung für die Sprache der XML-Schemadefinition (XSD) 1.0](https://www.w3.org/TR/xslt) des World Wide Web Consortium (W3C). Zudem entsprechen die generierten Datentypen dem Dokument mit dem Titel „XML-Schema Teil 2: Datentypen“.

 Die Daten des Objekts werden durch Konstrukte der Programmiersprache beschrieben, z.B. Klassen, Felder, Eigenschaften, primitive Typen, Arrays oder auch eingebettetes XML in Form von **XmlElement** - oder **XmlAttribute** -Objekten. Sie können eigene, mit Attributen versehene Klassen erstellen oder Klassen mit dem XML Schema Definition-Tool auf der Grundlage eines vorhandenen XML-Schemas generieren.

 Wenn ein XML-Schema gegeben ist, können Sie das XML Schema Definition-Tool ausführen und so eine Reihe von Klassen erstellen, die für dieses Schema streng typisiert und mit Attributen versehen sind. Wenn eine Instanz einer solchen Klasse serialisiert wird, entspricht der generierte XML-Code dem XML-Schema. Wenn eine solche Klasse gegeben ist, können Sie mit einem einfach bearbeitbaren Objektmodell programmieren und gleichzeitig sicher sein, dass der erzeugte XML-Code dem XML-Schema entspricht. Dies ist eine Alternative dazu, andere Klassen von .NET wie **XmlReader** und **XmlWriter** zum Analysieren und Schreiben von XML-Streams zu verwenden. Weitere Informationen hierzu finden Sie unter [XML Documents and Data (XML-Dokumente und -Daten)](../data/xml/index.md). Diese Klassen ermöglichen es Ihnen, jeden XML-Stream zu analysieren. Verwenden Sie dagegen **XmlSerializer** , wenn der XML-Stream einem bekannten XML-Schema entsprechen soll.

 Attribute steuern den von der **XmlSerializer** -Klasse generierten XML-Stream und ermöglichen es Ihnen, den XML-Namespace, den Elementnamen, den Attributnamen usw. des XML-Streams festzulegen. Weitere Informationen zu diesen Attributen und ihrer Funktion in Bezug auf die XML-Serialisierung finden Sie unter [Controlling XML Serialization Using Attributes (Steuern der XML-Serialisierung mithilfe von Attributen)](controlling-xml-serialization-using-attributes.md). Eine Tabelle der Attribute, die sich auf den generierten XML-Code auswirken, finden Sie unter [Attributes That Control XML Serialization (Attribute zum Steuern der XML-Serialisierung)](attributes-that-control-xml-serialization.md).

 Die **XmlSerializer** -Klasse kann überdies ein Objekt serialisieren und einen codierten SOAP-XML-Stream generieren. Das generierte XML entspricht Abschnitt 5 des World Wide Web Consortium-Dokuments mit dem Titel "Simple Object Access-Protokoll (SOAP) 1.1." Weitere Informationen zu diesem Vorgang finden Sie unter [Vorgehensweise: Serialisieren eines Objekts als einen durch SOAP codierten XML-Stream](how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md). Eine Tabelle der Attribute, die sich auf den generierten XML-Code auswirken, finden Sie unter [Attributes That Control Encoded SOAP Serialization (Attribute zum Steuern der codierten SOAP-Serialisierung)](attributes-that-control-encoded-soap-serialization.md).

 Die **XmlSerializer** -Klasse generiert die SOAP-Nachrichten, die durch XML-Webdienste erstellt und an XML-Webdienste übergeben werden. Zur Steuerung der SOAP-Nachrichten können Sie Attribute auf die Klassen, Rückgabewerte, Parameter und Felder einer Webdienstdatei (ASMX) anwenden. Sie können sowohl die unter "Attribute zur Steuerung der XML-Serialisierung" als auch die unter "Attribute zur Steuerung der Serialisierung von codiertem SOAP" aufgeführten Attribute verwenden, weil XML-Webdienste sowohl das literale als auch das codierte SOAP-Format verarbeiten können. Weitere Informationen dazu, wie sich der von einem XML-Webdienst erzeugte XML-Code mit Attributen steuern lässt, finden Sie unter [XML Serialization with XML Web Services (XML-Serialisierung mit XML-Webdiensten)](xml-serialization-with-xml-web-services.md). Weitere Informationen zum SOAP und zu XML-Webdiensten finden Sie unter [Anpassen der Formatierung von SOAP-Nachrichten](/previous-versions/dotnet/netframework-4.0/dkwy2d72(v=vs.100)).

## <a name="security-considerations-for-xmlserializer-applications"></a>Sicherheitsüberlegungen zu XmlSerializer-Anwendungen

Beim Erstellen einer Anwendung, die die Klasse **XmlSerializer** verwendet, sollten Ihnen die folgenden Elemente und deren Auswirkungen bekannt sein:

- Die **XmlSerializer** -Klasse erstellt C#-Dateien (CS), kompiliert sie zu DLL-Dateien und legt diese in dem Verzeichnis ab, das durch die Umgebungsvariable TEMP angegeben wird. Die Deserialisierung wird in diesen DLL-Dateien ausgeführt.

  > [!NOTE]
  > Diese Serialisierungsassemblys können mit dem Tool SGen.exe im Voraus erzeugt und signiert werden. Dieses Tool kann nicht auf einem Server von Webdiensten ausgeführt werden. Das heißt, es kann nur von Clients und für die manuelle Serialisierung verwendet werden.

  Der Code und die DLL-Dateien sind während ihrer Erstellung und Kompilierung anfällig gegenüber bösartigen Prozessen. Wenn ein Computer mit Microsoft Windows NT 4.0 oder höher eingesetzt wird, können zwei oder mehr Benutzer gemeinsam auf das Verzeichnis TEMP zugreifen. Die gemeinsame Nutzung eines TEMP-Verzeichnisses ist gefährlich, wenn die beiden Konten über unterschiedliche Sicherheitsberechtigungen verfügen und der Benutzer mit den höheren Sicherheitsberechtigungen eine Anwendung ausführt, die **XmlSerializer** verwendet. In diesem Fall kann ein Benutzer die Sicherheit des Computers verletzen, indem er die CS- oder die DLL-Datei, die kompiliert wird, durch eine andere Datei ersetzt. Um diesen Aspekt auszuschließen, stellen Sie immer sicher, dass für jedes Benutzerkonto auf dem Computer ein eigenes Profil vorhanden ist. Standardmäßig zeigt die TEMP-Umgebungsvariable für jedes Konto auf ein anderes Verzeichnis.

- Wenn ein böswilliger Benutzer einen fortlaufenden Stream von XML-Daten an einen Webserver sendet (ein Denial-of-Service-Angriff), dann fährt die **XmlSerializer** -Anwendung solange mit der Verarbeitung von Daten fort, bis die Ressourcen des Computers erschöpft sind.

  Diese Art von Angriff wird unterbunden, wenn ein Computer mit Internet Information Services (IIS) verwendet und die Anwendung in IIS ausgeführt wird. IIS umfasst ein Gate, das keine Streams verarbeitet, die größer als ein definierter Wert (der Standardwert ist 4 KB) sind. Wenn Sie eine Anwendung erstellen, die IIS nicht verwendet und mit **XmlSerializer** deserialisiert, sollten Sie ein ähnliches Gate implementieren, das Denial-of-Service-Angriffe verhindert.

- **XmlSerializer** serialisiert Daten und führt jeden Code mit jedem ihm gegebenen Typ aus.

  Ein bösartiges Objekt kann auf zweierlei Art eine Bedrohung darstellen. Es kann bösartigen Code ausführen, und es kann bösartigen Code in die C#-Datei einfügen, die von **XmlSerializer** erstellt wird. Im ersten Fall, wenn ein bösartiges Objekt eine zerstörerische Prozedur auszuführen versucht, trägt die Codezugriffssicherheit dazu bei, dass kein Schaden angerichtet werden kann. Im zweiten Fall besteht theoretisch die Möglichkeit, dass ein bösartiges Objekt auf irgendeine Weise Code in die von **XmlSerializer** erzeugte C#-Datei einfügen kann. Obwohl dieses Problem gründlich untersucht wurde ein solcher Angriff als unwahrscheinlich gilt, sollten Sie entsprechende Vorsichtsmaßnahmen treffen und nie Daten mit einem unbekannten oder nicht vertrauenswürdigen Typ serialisieren.

- Serialisierte vertrauliche Daten sind unter Umständen verwundbar.

  Nachdem die Daten von der Klasse **XmlSerializer** serialisiert wurden, können sie in einer XML-Datei oder einem anderen Datenspeicher gespeichert werden. Wenn dieser Datenspeicher für andere Prozesse zugänglich oder im Intranet oder dem Internet sichtbar ist, können die Daten gestohlen und missbraucht werden. Wenn Sie beispielsweise eine Anwendung erstellen, die Bestellungen serialisiert, welche Kreditkartennummern enthalten, dann sind diese Daten streng vertraulich. Um Missbrauch oder Diebstahl zu verhindern, sollten Sie den Speicherort der Daten stets schützen und durch geeignete Maßnahmen sicherstellen, dass die Daten vertraulich bleiben.

## <a name="serialization-of-a-simple-class"></a>Serialisierung einer einfachen Klasse

Im folgenden Codebeispiel wird eine grundlegende Klasse mit einem öffentlichen Feld veranschaulicht.

```vb
Public Class OrderForm
    Public OrderDate As DateTime
End Class
```

```csharp
public class OrderForm
{
    public DateTime OrderDate;
}
```

Wenn eine Instanz dieser Klasse serialisiert wird, könnte dies etwa so aussehen.

```xml
<OrderForm>
    <OrderDate>12/12/01</OrderDate>
</OrderForm>
```

Weitere Beispiele zur Serialisierung finden Sie unter [Examples of XML Serialization (Beispiele für die XML-Serialisierung)](examples-of-xml-serialization.md).

## <a name="items-that-can-be-serialized"></a>Elemente, die serialisiert werden können

Die folgenden Elemente können mit der **XmlSerializer** -Klasse serialisiert werden:

- Öffentliche Eigenschaften mit Lese-/Schreibzugriff und Felder von öffentlichen Klassen

- Klassen, die **ICollection** oder **IEnumerable** implementieren.

  > [!NOTE]
  > Nur Auflistungen werden serialisiert, öffentliche Eigenschaften nicht

- **XmlElement** -Objekte.

- **XmlNode** -Objekte.

- **DataSet** -Objekte.

 Weitere Informationen zum Serialisieren oder Deserialisieren von Objekten finden Sie unter [Vorgehensweise: Serialisieren eines Objekts](how-to-serialize-an-object.md) und [ Deserialisieren eines Objekts mithilfe von XmlSerializer](how-to-deserialize-an-object.md).

## <a name="advantages-of-using-xml-serialization"></a>Vorteile der XML-Serialisierung

Die Klasse **XmlSerializer** gibt Ihnen uneingeschränkte und flexible Kontrolle bei der Serialisierung eines Objekts als XML. Wenn Sie einen XML-Webdienst erstellen, können Sie Attribute, die die Serialisierung steuern, auf Klassen und Member anwenden, um sicherzustellen, dass die XML-Ausgabe dem gegebenen Schema entspricht.

**XmlSerializer** ermöglicht beispielsweise Folgendes:

- Angeben, ob ein Feld oder eine Eigenschaft als Attribut oder ein Element codiert werden soll.

- Angeben des zu verwendenden XML-Namespace.

- Angeben des Namens eines Elements oder Attributs, wenn ein Feld- oder Eigenschaftenname unpassend ist.

Ein weiterer Vorteil der XM-Serialisierung besteht darin, dass für die von Ihnen entwickelten Anwendungen keine Einschränkungen gelten, solange der erzeugte XML-Stream dem gegebenen Schema entspricht. Stellen Sie sich ein Schema vor, das das zum Beschreiben von Büchern dient. Es stellt als Elemente den Titel, Autor, Verleger und die ISBN-Nummer zur Verfügung. Sie können eine Anwendung entwickeln, die die XML-Daten auf die gewünschte Weise verarbeitet, z. B. als Buchbestellung oder Bücherbestand. In beiden Fällen besteht die einzige Anforderung darin, dass der XML-Stream dem angegebenen XSD-Schema (XML Schema Definition Language) entspricht.

## <a name="xml-serialization-considerations"></a>Überlegungen zur XML-Serialisierung

Folgende Punkte sollten bei der Verwendung der **XmlSerializer** -Klasse berücksichtigt werden:

- Das Tool Sgen.exe wurde speziell entworfen, um Serialisierungsassemblys mit optimaler Leistung zu generieren.

- Die serialisierten Daten enthalten nur die Daten selbst und die Struktur der Klassen. Typidentität und Assemblyinformationen sind nicht darin enthalten.

- Es können nur öffentliche Eigenschaften und Felder serialisiert werden. Eigenschaften müssen über öffentliche Accessoren (get- und set-Methoden) verfügen. Wenn nicht öffentliche Daten serialisiert werden müssen, verwenden Sie die <xref:System.Runtime.Serialization.DataContractSerializer>-Klasse statt der XML-Serialisierung.

- Eine Klasse muss über einen parameterlosen Konstruktor verfügen, damit sie von der Klasse **XmlSerializer** serialisiert wird.

- Methoden können nicht serialisiert werden.

- **XmlSerializer** kann Klassen verarbeiten, die **IEnumerable** oder **ICollection** anders implementieren, wenn sie die folgenden Anforderungen erfüllen.

  Eine Klasse, die **IEnumerable** implementiert, muss eine öffentliche **Add** -Methode mit einem einzigen Parameter implementieren. Der Parameter der **Add** -Methode muss von dem Typ (polymorph) sein, den die **IEnumerator.Current** -Eigenschaft zurückgibt, die von der **GetEnumerator** -Methode zurückgegeben wird.

  Eine Klasse, die **ICollection** zusätzlich zu **IEnumerable** implementiert (z.B. **CollectionBase** ) muss eine öffentliche und mit **Item** indizierte Eigenschaft (Indexer in C#), die einen Integer-Wert annimmt, sowie eine öffentliche **Count** -Eigenschaft vom Typ **Integer** aufweisen. Der Parameter, der der **Add** -Methode übergeben wird, muss vom gleichen Typ sein wie der Wert, den die **Item** -Eigenschaft zurückgibt, oder muss ein Basistyp dieses Typs sein.

  Bei Klassen, die **ICollection** implementieren, werden die zu serialisierenden Werte nicht durch einen Aufruf von **Item** , sondern über die indizierte **GetEnumerator** -Eigenschaft abgerufen. Öffentliche Felder und Eigenschaften werden nicht serialisiert, mit Ausnahme von öffentlichen Feldern, die eine andere Auflistungsklasse zurückgeben (eine Klasse, die **ICollection** implementiert). Ein Beispiel finden Sie in [Examples of XML Serialization (Beispiele für die XML-Serialisierung)](examples-of-xml-serialization.md).

## <a name="xsd-data-type-mapping"></a>XSD-Datentypzuordnung

Das W3C-Dokument mit dem Titel [XML-Schema Teil 2: Datentypen](https://www.w3.org/TR/xmlschema-2/) gibt die einfachen Datentypen an, die in einem Schema für die Sprache der XML-Schemadefinition (XSD) zulässig sind. Für viele dieser Datentypen (beispielsweise **int** und **decimal** ) ist ein entsprechender Datentyp in .NET vorhanden. Für einige XML-Datentypen sind jedoch keine entsprechenden .NET-Datentypen verfügbar (beispielsweise für den Datentyp **NMTOKEN** ). In diesen Fällen erzeugen Sie mit dem XML Schema Definition-Tool ( [XML Schema Definition Tool (Xsd.exe)](xml-schema-definition-tool-xsd-exe.md)) Klassen anhand eines Schemas. Ein entsprechendes Attribut wird auf ein Member vom Typ „Zeichenfolge“ angewendet, und die **DataType** -Eigenschaft wird auf den Namen des XML-Datentyps festgelegt. Wenn ein Schema beispielsweise ein Element namens „MyToken“ mit dem XML-Datentyp **NMTOKEN** aufweist, enthält die erzeugte Klasse unter Umständen einen Member, der wie im folgenden Beispiel aussieht.

```vb
<XmlElement(DataType:="NMTOKEN")> _
Public MyToken As String
```

```csharp
[XmlElement(DataType = "NMTOKEN")]
public string MyToken;
```

Ebenso gilt: Wenn Sie eine Klasse erstellen, die einem bestimmten XML-Schema (XSD) entsprechen soll, müssen Sie das entsprechende Attribut anwenden und deren **DataType** -Eigenschaft auf den Namen des gewünschten XML-Datentyps festlegen.

Eine umfassende Liste mit Typzuordnungen finden Sie in der **DataType** -Eigenschaft der folgenden Attributklassen:

- <xref:System.Xml.Serialization.SoapAttributeAttribute>

- <xref:System.Xml.Serialization.SoapElementAttribute>

- <xref:System.Xml.Serialization.XmlArrayItemAttribute>

- <xref:System.Xml.Serialization.XmlAttributeAttribute>

- <xref:System.Xml.Serialization.XmlElementAttribute>

- <xref:System.Xml.Serialization.XmlRootAttribute>

## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.Serialization.XmlSerializer>
- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.IO.FileStream>
- [XML- und SOAP-Serialisierung](xml-and-soap-serialization.md)
- [Binäre Serialisierung](binary-serialization.md)
- [Serialisierung](index.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [Beispiele für die XML-Serialisierung](examples-of-xml-serialization.md)
- [How to: Serialisieren eines Objekts](how-to-serialize-an-object.md).
- [How to: Deserialisieren eines Objekts](how-to-deserialize-an-object.md).
