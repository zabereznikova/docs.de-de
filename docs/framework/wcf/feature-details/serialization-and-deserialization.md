---
title: Serialisierung und Deserialisierung
description: Erfahren Sie mehr über die WCF-Serialisierungs-Engine, die in beide Richtungen zwischen .NET Framework Objekten und XML übersetzt.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3d71814c-bda7-424b-85b7-15084ff9377a
ms.openlocfilehash: 3927c17a2548a094a63ffd95ff8a3701403de281
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244906"
---
# <a name="serialization-and-deserialization"></a>Serialisierung und Deserialisierung
Windows Communication Foundation (WCF) umfasst ein neues Serialisierungsmodul, das <xref:System.Runtime.Serialization.DataContractSerializer> . Der <xref:System.Runtime.Serialization.DataContractSerializer> übersetzt zwischen .NET Framework-Objekten und XML in beide Richtungen. In diesem Thema wird die Funktionsweise des Serialisierungsprogramms erklärt.  
  
 Beim Serialisieren von .NET Framework Objekten versteht das Serialisierungsprogramm eine Reihe von Programmier Modellen für die Serialisierung, einschließlich des neuen *Daten Vertrags* Modells. Eine vollständige Liste der unterstützten Typen finden Sie unter [Types Supported by the Data Contract Serializer](types-supported-by-the-data-contract-serializer.md). Eine Einführung in Datenverträge finden Sie unter [Using Data Contracts](using-data-contracts.md).  
  
 Beim Deserialisieren von XML verwendet das Serialisierungsprogramm die <xref:System.Xml.XmlReader> -Klasse und die <xref:System.Xml.XmlWriter> -Klasse. Außerdem unterstützt es <xref:System.Xml.XmlDictionaryReader> die <xref:System.Xml.XmlDictionaryWriter> Klassen und, damit es in einigen Fällen optimierte XML-Daten erzeugt, z. b. wenn das binäre WCF-XML-Format verwendet wird.  
  
 WCF enthält auch einen begleitenden Serialisierer, den <xref:System.Runtime.Serialization.NetDataContractSerializer> . Das <xref:System.Runtime.Serialization.NetDataContractSerializer> -Element ähnelt dem <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> -und dem- <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> Serialisierungstyp, da es auch .NET Framework Typnamen als Teil der serialisierten Daten ausgibt. Es wird verwendet, wenn die Endpunkte, die die Serialisierung und die Deserialisierung durchführen, die gleichen Datentypen verwenden. Sowohl <xref:System.Runtime.Serialization.DataContractSerializer> als auch <xref:System.Runtime.Serialization.NetDataContractSerializer> sind von der gemeinsamen Basisklasse <xref:System.Runtime.Serialization.XmlObjectSerializer>abgeleitet.  
  
> [!WARNING]
> Der <xref:System.Runtime.Serialization.DataContractSerializer> serialisiert Zeichenfolgen mit Steuerzeichen mit einem Hexadezimalwert kleiner als 20 als XML-Entitäten. Dies kann zu einem Problem mit einem nicht-WCF-Client führen, wenn solche Daten an einen WCF-Dienst gesendet werden.  
  
## <a name="creating-a-datacontractserializer-instance"></a>Erstellen einer DataContractSerializer-Instanz  
 Das Erstellen einer <xref:System.Runtime.Serialization.DataContractSerializer> -Instanz ist ein wichtiger Schritt. Sie können nach der Erstellung dieser Instanz keine Einstellungen mehr ändern.  
  
### <a name="specifying-the-root-type"></a>Angeben des Stammtyps  
 Der *Stammtyp* ist der Typ, von dem Instanzen serialisiert oder deserialisiert werden. Für <xref:System.Runtime.Serialization.DataContractSerializer> sind viele überladene Konstruktoren verfügbar; aber mindestens ein Stammtyp muss mit dem Parameter `type` angegeben werden.  
  
 Ein für einen bestimmten Stammtyp erstelltes Serialisierungsprogramm kann nur dann zum Serialisieren (oder Deserialisieren) eines anderen Typs verwendet werden, wenn dieser Typ vom Stammtyp abgeleitet ist. Das folgende Beispiel zeigt zwei Klassen.  
  
 [!code-csharp[c_StandaloneDataContractSerializer#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#1)]
 [!code-vb[c_StandaloneDataContractSerializer#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#1)]  
  
 In diesem Code wird eine Instanz der `DataContractSerializer` -Klasse erstellt, die lediglich zum Serialisieren und Deserialisieren der `Person` -Klasse verwendet werden kann.  
  
 [!code-csharp[c_StandaloneDataContractSerializer#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#2)]
 [!code-vb[c_StandaloneDataContractSerializer#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#2)]  
  
### <a name="specifying-known-types"></a>Angeben von bekannten Typen  
 Wenn die serialisierten Typen polymorph sind und die Polymorphie nicht bereits mithilfe des <xref:System.Runtime.Serialization.KnownTypeAttribute> -Attributs oder eines anderen Mechanismus gehandhabt wird, dann muss dem Konstruktor der Serializer-Instanz im `knownTypes` -Parameter eine Liste der möglichen bekannten Typen übergeben werden. Weitere Informationen zu bekannten Typen finden Sie unter [Data Contract Known Types](data-contract-known-types.md).  
  
 Im folgenden Codebeispiel wird die Klasse namens `LibraryPatron`veranschaulicht, die eine Auflistung des Typs `LibraryItem`enthält. Die zweite Klasse definiert den `LibraryItem` -Typ. Die dritte Klasse und die vierte Klasse (`Book` und `Newspaper`) sind von der `LibraryItem` -Klasse abgeleitet.  
  
 [!code-csharp[c_StandaloneDataContractSerializer#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#3)]  
 [!code-vb[c_StandaloneDataContractSerializer#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#3)]  
  
 Im folgenden Code wird unter Angabe des `knownTypes` -Parameters eine Serializer-Instanz erstellt.  
  
 [!code-csharp[c_StandaloneDataContractSerializer#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#4)]
 [!code-vb[c_StandaloneDataContractSerializer#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#4)]  
  
### <a name="specifying-the-default-root-name-and-namespace"></a>Angeben von Standardstammnamen und -namespace  
 Wenn ein Objekt serialisiert wird, werden der Standardname und der Namespace des äußersten XML-Elements in der Regel anhand des Namens und Namespace des Datenvertrags bestimmt. Die Namen aller inneren Elemente werden aus den Datenmembernamen ermittelt, und als Namespace wird ihnen der Namespace des Datenvertrags zugeordnet. Im folgenden Beispiel werden die Werte für `Name` und `Namespace` in den Konstruktoren für die <xref:System.Runtime.Serialization.DataContractAttribute> -Klasse und die <xref:System.Runtime.Serialization.DataMemberAttribute> -Klasse festgelegt.  
  
 [!code-csharp[c_StandaloneDataContractSerializer#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#5)]
 [!code-vb[c_StandaloneDataContractSerializer#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#5)]  
  
 Durch die Serialisierung einer Instanz der `Person` -Klasse wird eine XML-Ausgabe erzeugt, die folgendem XML-Code ähnelt.  
  
```xml  
<PersonContract xmlns="http://schemas.contoso.com">  
  <AddressMember>  
    <StreetMember>123 Main Street</StreetMember>  
   </AddressMember>  
</PersonContract>  
```  
  
 Sie können den Standardnamen und den Namespace des Stammelements anpassen, indem Sie Werte für den `rootName` -Parameter und den `rootNamespace` -Parameter dem <xref:System.Runtime.Serialization.DataContractSerializer> -Konstruktor übergeben. Beachten Sie, dass sich der `rootNamespace` -Parameter nicht auf den Namespace der darin enthaltenen Elemente auswirkt, die Datenmembern entsprechen. Die Parameterangabe betrifft nur den Namespace des äußersten Elements.  
  
 Diese Werte können als Zeichenfolgen oder als Instanzen der <xref:System.Xml.XmlDictionaryString> -Klasse übergeben werden, damit sie unter Verwendung des binären XML-Formats optimiert werden können.  
  
### <a name="setting-the-maximum-objects-quota"></a>Festlegen des maximalen Objektkontingents  
 Einige `DataContractSerializer` -Konstruktorüberladungen verfügen über den `maxItemsInObjectGraph` -Parameter. Dieser Parameter legt die maximale Anzahl von Objekten fest, die das Serialisierungsprogramm in einem <xref:System.Runtime.Serialization.XmlObjectSerializer.ReadObject%2A> -Methodenaufruf serialisieren oder deserialisieren kann. (Die Methode liest immer ein Stammobjekt, aber dieses Objekt kann in seinen Datenmembern andere Objekte enthalten. Diese Objekte verfügen möglicherweise über andere Objekte usw.) Der Standardwert ist 65536. Beachten Sie, dass beim Serialisieren und Deserialisieren von Arrays jeder Arrayeintrag als separates Objekt betrachtet wird. Beachten Sie zudem, dass einige Objekte über eine große Speicherdarstellung verfügen und dass dieses Kontingent allein daher möglicherweise nicht ausreicht, um einen Denial-of-Service-Angriff zu verhindern. Weitere Informationen finden Sie unter [Sicherheitsüberlegungen für Daten](security-considerations-for-data.md). Wenn Sie das Kontingent über die Standardeinstellung hinaus erhöhen müssen, müssen Sie dies unbedingt sowohl auf der sendenden (serialisierenden) als auch der empfangenden (deserialisierenden) Seite tun, da das Kontingent sowohl für das Lesen als auch das Schreiben von Daten gilt.  
  
### <a name="round-trips"></a>Roundtrips  
 Ein *Roundtrip* tritt auf, wenn ein Objekt in einem Vorgang deserialisiert und erneut serialisiert wird. Das heißt, Daten werden aus XML in eine Objektinstanz und wieder zurück in einen XML-Stream umgewandelt.  
  
 Einige `DataContractSerializer` -Konstruktorüberladungen verfügen über den `ignoreExtensionDataObject` -Parameter, der standardmäßig auf `false` festgelegt ist. In diesem Standardmodus können Daten von einer neueren Version des Datenvertrags zu einer älteren Datenvertragsversion und wieder zurück zur neueren Version geschickt werden, ohne dass Datenverluste auftreten, sofern der Datenvertrag die <xref:System.Runtime.Serialization.IExtensibleDataObject> -Schnittstelle implementiert. Nehmen wir beispielsweise an, Version 1 des `Person` -Datenvertrags enthält die Datenmember `Name` und `PhoneNumber` , und in Version 2 wurde der Member `Nickname` hinzugefügt. Wenn `IExtensibleDataObject` implementiert wurde, dann werden beim Senden der Daten von Version 2 an Version 1 die `Nickname` -Daten gespeichert und beim erneuten Serialisieren der Daten wieder ausgegeben. Daher gehen in Roundtrips keine Daten verloren. Weitere Informationen finden Sie unter [Forward-kompatible Datenverträge](forward-compatible-data-contracts.md) und [Versions](data-contract-versioning.md)Verwaltung von Daten Verträgen.  
  
#### <a name="security-and-schema-validity-concerns-with-round-trips"></a>Bedenken hinsichtlich der Sicherheit und Schemavalidierung bei Roundtrips  
 Roundtrips beeinträchtigen möglicherweise die Sicherheit. Beispielsweise kann das Deserialisieren und Speichern von großen Mengen externer Daten ein Sicherheitsrisiko darstellen. Es kann Sicherheitsbedenken in Bezug auf die erneute Ausgabe dieser Daten geben, weil sich diese nicht verifizieren lassen, insbesondere wenn sie digital signiert sind. Beispielsweise könnte im obigen Szenario der Endpunkt mit Version&#160;1 einen `Nickname` -Wert signieren, der bösartige Daten enthält. Schließlich kann es Bedenken hinsichtlich der Schemavalidierung geben: Es kann wünschenswert sein, dass ein Endpunkt nur Daten, die genau dem angegebenen Datenvertrag entsprechen, und keine zusätzlichen Werte ausgibt. Im vorigen Beispiel besagt der Datenvertrag des Endpunkts mit Version&#160;1, dass dieser nur `Name` und `PhoneNumber`ausgibt, und bei Verwendung einer Schemavalidierung verursacht die Ausgabe des zusätzlichen `Nickname` -Werts einen Fehler.  
  
#### <a name="enabling-and-disabling-round-trips"></a>Aktivieren und Deaktivieren von Roundtrips  
 Wenn Sie Roundtrips deaktivieren möchten, implementieren Sie die <xref:System.Runtime.Serialization.IExtensibleDataObject> -Schnittstelle nicht. Falls Sie keine Kontrolle über die Typen haben, legen Sie den `ignoreExtensionDataObject` -Parameter auf `true` fest, um Roundtrips zu unterbinden.  
  
### <a name="object-graph-preservation"></a>Objektdiagrammbeibehaltung  
 Normalerweise befasst sich das Serialisierungsprogramm nicht mit der Objektidentität, wie im folgenden Code gezeigt.  
  
 [!code-csharp[c_StandaloneDataContractSerializer#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#6)]
 [!code-vb[c_StandaloneDataContractSerializer#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#6)]  
  
 Im folgenden Code wird ein PurchaseOrder-Objekt erstellt.  
  
 [!code-csharp[c_StandaloneDataContractSerializer#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#7)]
 [!code-vb[c_StandaloneDataContractSerializer#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#7)]  
  
 Beachten Sie, dass das `billTo` -Feld und `shipTo` -Feld auf die gleiche Objektinstanz festgelegt werden. Das generierte XML dupliziert allerdings die doppelt vorhandenen Informationen und ähnelt dem folgenden XML.  
  
```xml  
<PurchaseOrder>  
  <billTo><street>123 Main St.</street></billTo>  
  <shipTo><street>123 Main St.</street></shipTo>  
</PurchaseOrder>  
```  
  
 Dieser Ansatz verfügt über die folgenden Eigenschaften, die möglicherweise unerwünscht sind:  
  
- Leistung. Die Datenreplizierung ist ineffizient.  
  
- Zirkuläre Verweise. Wenn Objekte auf sich selbst verweisen, resultiert die Serialisierung durch Replizierung auch dann in einer Endlosschleife, wenn die Verweise über andere Objekte führen. (Das Serialisierungsprogramm löst in diesem Fall eine <xref:System.Runtime.Serialization.SerializationException> aus.)  
  
- Semantik. Gelegentlich ist es wichtig, die Tatsache zu vermerken, dass zwei Verweise auf das gleiche Objekt und nicht auf zwei identische Objekte zeigen.  
  
 Aus diesem Grund verfügen einige `DataContractSerializer` -Konstruktorüberladungen über den `preserveObjectReferences` -Parameter (dessen Standardwert lautet `false`). Wenn dieser Parameter auf festgelegt ist `true` , wird eine spezielle Methode zur Codierung von Objekt verweisen verwendet, die nur WCF versteht. Wenn der Parameter auf `true`festgelegt wird, sieht das XML-Codebeispiel etwa wie folgt aus.  
  
```xml  
<PurchaseOrder ser:id="1">  
  <billTo ser:id="2"><street ser:id="3">123 Main St.</street></billTo>  
  <shipTo ser:ref="2"/>  
</PurchaseOrder>  
```  
  
 Der "ser"-Namespace verweist auf den Standardserialisierungsnamespace `http://schemas.microsoft.com/2003/10/Serialization/` . Jedes Datenelement wird nur einmal serialisiert und erhält eine ID-Nummer. Bei nachfolgender Verwendung wird ein Verweis auf die bereits serialisierten Daten erzeugt.  
  
> [!IMPORTANT]
> Ist sowohl das Attribut "id" als auch das Attribut "ref" im `XMLElement`des Datenvertrags vorhanden, wird das Attribut "ref" berücksichtigt, und das Attribut "id" wird ignoriert.  
  
 Es ist wichtig, die Einschränkungen dieses Modus zu kennen:  
  
- Das XML, das der `DataContractSerializer` erzeugt, wenn der `preserveObjectReferences` -Parameter auf `true` festgelegt ist, kann von keiner anderen Technologie verarbeitet werden. Nur eine andere `DataContractSerializer` -Instanz, bei der der `preserveObjectReferences` -Parameter auch auf `true`festgelegt ist, kann darauf zugreifen.  
  
- Es ist keine Metadaten- (Schema)-Unterstützung für diese Funktion verfügbar. Das Schema, das erzeugt wird, ist nur in dem Fall gültig, in dem `preserveObjectReferences` auf `false`festgelegt ist.  
  
- Diese Funktion bewirkt möglicherweise, dass Serialisierung und Deserialisierung langsamer ausgeführt werden. Obwohl die Daten nicht repliziert werden müssen, müssen in diesem Modus zusätzliche Objektvergleiche angestellt werden.  
  
> [!CAUTION]
> Wenn der `preserveObjectReferences` -Modus aktiviert ist, muss der `maxItemsInObjectGraph` -Wert unbedingt auf das richtige Kontingent festgelegt werden. Aufgrund der Art und Weise, wie Arrays in diesem Modus behandelt werden, ist es für Angreifer einfach, eine kleine bösartige Nachricht zu erstellen, die in zu einem hohen Speicherverbrauch führt, der nur durch das `maxItemsInObjectGraph` -Kontingent begrenzt wird.  
  
### <a name="specifying-a-data-contract-surrogate"></a>Angeben eines Datenvertrag-Ersatzzeichens  
 Einige `DataContractSerializer` -Konstruktorüberladungen verfügen über den `dataContractSurrogate` -Parameter, der möglicherweise auf `null`festgelegt ist. Andernfalls können Sie mit diesem Parameter ein *Datenvertrag-Ersatzzeichen*festlegen, d.&#160;h. einen Typ, der die <xref:System.Runtime.Serialization.IDataContractSurrogate> -Schnittstelle implementiert. Sie können dann mithilfe dieser Schnittstelle die Serialisierung und Deserialisierung anpassen. Weitere Informationen finden Sie unter [Data Contract Surrogates](../extending/data-contract-surrogates.md).  
  
## <a name="serialization"></a>Serialisierung  
 Die folgenden Ausführungen gelten für alle von <xref:System.Runtime.Serialization.XmlObjectSerializer>abgeleiteten Klassen, einschließlich der <xref:System.Runtime.Serialization.DataContractSerializer> -Klasse und der <xref:System.Runtime.Serialization.NetDataContractSerializer> -Klasse.  
  
### <a name="simple-serialization"></a>Einfache Serialisierung  
 Die grundlegendste Möglichkeit, ein Objekt zu serialisieren, besteht darin, es der <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteObject%2A> -Methode zu übergeben. Es gibt drei Überladungen, jeweils eine zum Schreiben in ein <xref:System.IO.Stream>-Objekt, ein <xref:System.Xml.XmlWriter>-Objekt oder ein <xref:System.Xml.XmlDictionaryWriter>-Objekt. Bei Verwendung der <xref:System.IO.Stream> -Überladung enthält die Ausgabe XML in UTF-8-Codierung. Bei Verwendung der <xref:System.Xml.XmlDictionaryWriter> -Überladung optimiert das Serialisierungsprogramm seine Ausgabe für binäres XML.  
  
 Bei Verwendung der- <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteObject%2A> Methode verwendet das Serialisierungsprogramm den Standardnamen und-Namespace für das Wrapper Element und schreibt es zusammen mit dem Inhalt (Weitere Informationen finden Sie im vorherigen Abschnitt "angeben des Standard Stamms und Namespace").  
  
 Im folgenden Codebeispiel wird der Schreibvorgang mit <xref:System.Xml.XmlDictionaryWriter>veranschaulicht.  
  
 [!code-csharp[c_StandaloneDataContractSerializer#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#8)]
 [!code-vb[c_StandaloneDataContractSerializer#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#8)]  
  
 Damit wird XML generiert, das etwa wie folgt aussieht.  
  
```xml  
<Person>  
  <Name>Jay Hamlin</Name>  
  <Address>123 Main St.</Address>  
</Person>  
```  
  
### <a name="step-by-step-serialization"></a>Schrittweise Serialisierung  
 Verwenden Sie die Methoden <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteStartObject%2A>, <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteObjectContent%2A>und <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteEndObject%2A> , um das Endelement und den Inhalt des Objekts zu schreiben bzw. das Wrapperelement zu schließen.  
  
> [!NOTE]
> Es sind keine <xref:System.IO.Stream> -Überladungen für diese Methoden verfügbar.  
  
 Diese schrittweise Serialisierung wird üblicherweise in zwei Fällen eingesetzt. Erstens wird sie verwendet, um Inhalte wie Attribute oder Kommentare zwischen `WriteStartObject` und `WriteObjectContent`einzufügen. Dies wird im folgenden Beispiel veranschaulicht.  
  
 [!code-csharp[c_StandaloneDataContractSerializer#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#9)]
 [!code-vb[c_StandaloneDataContractSerializer#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#9)]  
  
 Damit wird XML generiert, das etwa wie folgt aussieht.  
  
```xml  
<Person serializedBy="myCode">  
  <Name>Jay Hamlin</Name>  
  <Address>123 Main St.</Address>  
</Person>  
```  
  
 Sie wird auch häufig verwendet, um die Verwendung von <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteStartObject%2A> und <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteEndObject%2A> zu vermeiden und ein eigenes, benutzerdefiniertes Wrapperelement zu schreiben (oder die Erstellung eines Wrapperelements ganz zu umgehen), wie im folgenden Code gezeigt.  
  
 [!code-csharp[c_StandaloneDataContractSerializer#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#10)]
 [!code-vb[c_StandaloneDataContractSerializer#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#10)]  
  
 Damit wird XML generiert, das etwa wie folgt aussieht.  
  
```xml  
<MyCustomWrapper>  
  <Name>Jay Hamlin</Name>  
  <Address>123 Main St.</Address>  
</MyCustomWrapper>  
```  
  
> [!NOTE]
> Die Verwendung der schrittweisen Serialisierung kann in XML resultieren, das keinem gültigen Schema entspricht.  
  
## <a name="deserialization"></a>Deserialisierung  
 Die folgenden Ausführungen gelten für alle von <xref:System.Runtime.Serialization.XmlObjectSerializer>abgeleiteten Klassen, einschließlich der <xref:System.Runtime.Serialization.DataContractSerializer> -Klasse und der <xref:System.Runtime.Serialization.NetDataContractSerializer> -Klasse.  
  
 Die grundlegendste Möglichkeit, ein Objekt zu deserialisieren, besteht im Aufruf einer der Überladungen der <xref:System.Runtime.Serialization.XmlObjectSerializer.ReadObject%2A> -Methode. Es sind drei Überladungen verfügbar, jeweils eine zum Lesen mit einem <xref:System.Xml.XmlDictionaryReader>-Objekt, einem `XmlReader`-Objekt oder einem `Stream`-Objekt. Beachten Sie, dass die `Stream` -Überladung einen textbasierten <xref:System.Xml.XmlDictionaryReader> erstellt, der nicht durch Kontingente geschützt wird und nur zum Lesen vertrauenswürdiger Daten verwendet werden sollte.  
  
 Beachten Sie außerdem, dass das von der `ReadObject` -Methode zurückgegebene Objekt in den entsprechenden Typ umgewandelt werden muss.  
  
 Im folgenden Code wird eine Instanz der <xref:System.Runtime.Serialization.DataContractSerializer> -Klasse und ein <xref:System.Xml.XmlDictionaryReader>erzeugt, und dann eine `Person` -Instanz deserialisiert.  
  
 [!code-csharp[c_StandaloneDataContractSerializer#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#11)]
 [!code-vb[c_StandaloneDataContractSerializer#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#11)]  
  
 Positionieren Sie den XML-Reader vor dem Aufruf der <xref:System.Runtime.Serialization.XmlObjectSerializer.ReadObject%2A> -Methode auf dem Wrapperelement oder einem Knoten, der keinen Inhalt enthält und sich vor dem Wrapperelement befindet. Sie können zu diesem Zweck die <xref:System.Xml.XmlReader.Read%2A> -Methode der <xref:System.Xml.XmlReader> -Klasse oder der davon abgeleiteten Klasse aufrufen und den <xref:System.Xml.XmlReader.NodeType%2A>testen, wie im folgenden Code gezeigt.  
  
 [!code-csharp[c_StandaloneDataContractSerializer#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#12)]
 [!code-vb[c_StandaloneDataContractSerializer#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#12)]  
  
 Beachten Sie, dass Sie Attribute dieses Wrapperelements lesen können, bevor der Reader an `ReadObject`übergeben wird.  
  
 Wenn Sie eine der einfachen `ReadObject` über Ladungen verwenden, sucht das Deserialisierungsprogramm im Wrapper Element nach dem Standardnamen und-Namespace (siehe den vorherigen Abschnitt "angeben des standardmäßigen Stamm namens und Namespace") und löst eine Ausnahme aus, wenn ein unbekanntes Element gefunden wird. Im vorstehenden Beispiel wird das Wrapperelement `<Person>` erwartet. Die <xref:System.Runtime.Serialization.XmlObjectSerializer.IsStartObject%2A> -Methode wird aufgerufen, um zu überprüfen, ob der Reader auf einem Element mit dem erwarteten Namen positioniert wurde.  
  
 Es gibt eine Möglichkeit, diese Namensüberprüfung des Wrapperelements zu deaktivieren. Einige Überladungen der `ReadObject` -Methode akzeptieren den Booleschen Parameter `verifyObjectName`, der standardmäßig auf `true` festgelegt ist. Wenn der Parameter auf `false`festgelegt wird, werden Name und Namespace des Wrapperelements ignoriert. Dies ist beim Lesen von XML hilfreich, das mit dem oben beschriebenen schrittweisen Serialisierungsmechanismus geschrieben wurde.  
  
## <a name="using-the-netdatacontractserializer"></a>Verwenden von NetDataContractSerializer  
 Der Hauptunterschied zwischen `DataContractSerializer` und <xref:System.Runtime.Serialization.NetDataContractSerializer> besteht darin, dass der `DataContractSerializer` Daten Vertrags Namen verwendet, während der `NetDataContractSerializer` vollständige .NET Framework Assembly und Typnamen in der serialisierten XML ausgibt. Dies bedeutet, dass die Endpunkte für Serialisierung und Deserialisierung genau die gleichen Datentypen verwenden müssen. Folglich muss der Mechanismus der bekannten Typen nicht in Verbindung mit `NetDataContractSerializer` verwendet werden, weil stets bekannt ist, welche Typen im Einzelnen deserialisiert werden müssen.  
  
 Es können jedoch verschiedene Probleme auftreten:  
  
- Sicherheit. Jeder Typ, der in dem zu deserialisierenden XML gefunden wird, wird geladen. Dies kann ausgenutzt werden, um das Laden bösartiger Typen zu erzwingen. `NetDataContractSerializer` sollte nur dann für nicht vertrauenswürdige Daten eingesetzt werden, wenn ein *Serialisierungsbinder* verwendet wird (über die <xref:System.Runtime.Serialization.NetDataContractSerializer.Binder%2A> -Eigenschaft oder einen Konstruktorparameter). Die Binder lässt nur das Laden sicherer Typen zu. Der Bindermechanismus ist mit dem Mechanismus identisch, den die im <xref:System.Runtime.Serialization> -Namespace definierten Typen verwenden.  
  
- Versionskontrolle. Die Angabe vollständiger Typ- und Assemblynamen im XML schränkt die Verfahren zur Versionskontrolle der Typen schwerwiegend ein. Folgendes kann nicht geändert werden: Typnamen, Namespaces, Assemblynamen und Assemblyversionen. Wenn die <xref:System.Runtime.Serialization.NetDataContractSerializer.AssemblyFormat%2A> -Eigenschaft oder der Konstruktorparameter auf <xref:System.Runtime.Serialization.Formatters.FormatterAssemblyStyle.Simple> statt den Standardwert <xref:System.Runtime.Serialization.Formatters.FormatterAssemblyStyle.Full> festgelegt wird, sind Änderungen der Assemblyversion, jedoch keine generischen Parametertypen zulässig.  
  
- Interoperabilität. Da .NET Framework Typ-und Assemblynamen in der XML-Datei enthalten sind, können andere Plattformen als die .NET Framework nicht auf die resultierenden Daten zugreifen.  
  
- Leistung. Die Ausgabe von Typ- und Assemblynamen vergrößert den Umfang des resultierenden XML bedeutend.  
  
 Dieser Mechanismus ähnelt der binären Serialisierung oder der SOAP-Serialisierung, die von .NET Framework Remoting verwendet wird (insbesondere von <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> und <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> ).  
  
 Die Verwendung von `NetDataContractSerializer` unterscheidet sich von der Verwendung von `DataContractSerializer`lediglich in folgender Hinsicht:  
  
- Die Konstruktoren erfordern keine Angabe des Stammtyps. Sie können jeden Typ mit der gleichen Instanz von `NetDataContractSerializer`serialisieren.  
  
- Die Konstruktoren akzeptieren keine Liste bekannter Typen an. Der Mechanismus der bekannten Typen ist unnötig, wenn die Typnamen in XML serialisiert werden.  
  
- Die Konstruktoren akzeptieren kein Datenvertrag-Ersatzzeichen. Stattdessen akzeptieren sie einen <xref:System.Runtime.Serialization.ISurrogateSelector> -Parameter namens `surrogateSelector` (welcher der <xref:System.Runtime.Serialization.NetDataContractSerializer.SurrogateSelector%2A> -Eigenschaft zugeordnet wird). Dies ist ein älterer Ersatzzeichenmechanismus.  
  
- Die Konstruktoren akzeptieren einen Parameter namens `assemblyFormat` vom <xref:System.Runtime.Serialization.Formatters.FormatterAssemblyStyle> , welcher der <xref:System.Runtime.Serialization.NetDataContractSerializer.AssemblyFormat%2A> -Eigenschaft zugeordnet wird. Wie oben erläutert, lassen sich damit die Versionskontrollfähigkeiten des Serialisierungsprogramms verbessern. Dies entspricht dem <xref:System.Runtime.Serialization.Formatters.FormatterAssemblyStyle> -Mechanismus in der binären Serialisierung oder der SOAP-Serialisierung.  
  
- Die Konstruktoren akzeptieren einen <xref:System.Runtime.Serialization.StreamingContext> -Parameter namens `context` , welcher der <xref:System.Runtime.Serialization.NetDataContractSerializer.Context%2A> -Eigenschaft zugeordnet wird. Sie können diesen zur Übergabe von Informationen an Typen nutzen, die serialisiert werden. Diese Art der Verwendung entspricht dem <xref:System.Runtime.Serialization.StreamingContext> -Mechanismus, der in anderen <xref:System.Runtime.Serialization> -Klassen verwendet wird.  
  
- Die <xref:System.Runtime.Serialization.NetDataContractSerializer.Serialize%2A> -Methode und die <xref:System.Runtime.Serialization.NetDataContractSerializer.Deserialize%2A> -Methode sind Aliase für die <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteObject%2A> -Methode bzw. die <xref:System.Runtime.Serialization.XmlObjectSerializer.ReadObject%2A> -Methode. Sie sollen ein konsistenteres Programmiermodell für die binäre Serialisierung oder SOAP-Serialisierung bereitstellen.  
  
 Weitere Informationen zu diesen Funktionen finden Sie unter [binäre Serialisierung](../../../standard/serialization/binary-serialization.md).  
  
 Die von der `NetDataContractSerializer` -Klasse und der `DataContractSerializer` -Klasse verwendeten XML-Formate sind normalerweise nicht kompatibel. Das heißt, es ist nicht möglich, Daten mit einem dieser Serialisierungsprogramme zu serialisieren und sie mit dem anderen Serialisierungsprogramm zu deserialisieren.  
  
 Beachten Sie außerdem, dass `NetDataContractSerializer` nicht den vollständigen .NET Framework-und Assemblynamen für jeden Knoten im Objekt Diagramm ausgibt. Diese Informationen werden nur im Fall möglicher Mehrdeutigkeiten ausgegeben. Das heißt, sie werden auf der Stammobjektebene und für polymorphe Fälle ausgegeben.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Runtime.Serialization.NetDataContractSerializer>
- <xref:System.Runtime.Serialization.XmlObjectSerializer>
- [Binäre Serialisierung](../../../standard/serialization/binary-serialization.md)
- [Vom Datenvertragsserialisierer unterstützte Typen](types-supported-by-the-data-contract-serializer.md)
