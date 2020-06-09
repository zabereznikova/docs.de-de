---
title: XML- und ADO.NET-Typen in Datenverträgen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2ce8461-3c15-4c41-8c81-1cb78f5b59a6
ms.openlocfilehash: 975d4f4f37bbbd895cab4e87686f15017e90f382
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600074"
---
# <a name="xml-and-adonet-types-in-data-contracts"></a>XML- und ADO.NET-Typen in Datenverträgen
Das Daten Vertragsmodell Windows Communication Foundation (WCF) unterstützt bestimmte Typen, die XML direkt darstellen. Wenn diese Typen in XML serialisiert werden, schreibt das Serialisierungsprogramm den XML-Inhalt dieser Typen ohne weitere Verarbeitung. Unterstützte Typen sind <xref:System.Xml.XmlElement>, <xref:System.Xml.XmlNode>-Arrays (jedoch nicht der `XmlNode`-Typ selbst) sowie Typen, die <xref:System.Xml.Serialization.IXmlSerializable> implementieren. Der <xref:System.Data.DataSet>- und <xref:System.Data.DataTable>-Typ sowie typisierte Datasets werden häufig bei der Datenbankprogrammierung verwendet. Diese Typen implementieren die `IXmlSerializable`-Schnittstelle und sind deshalb im Datenvertragsmodell serialisierbar. Einige besondere Überlegungen zu diesen Typen sind am Ende dieses Themas aufgeführt.  
  
## <a name="xml-types"></a>XML-Typen  
  
### <a name="xml-element"></a>XML-Element  
 Der `XmlElement`-Typ wird mit seinem XML-Inhalt serialisiert. Verwenden Sie z.&#160;B. den folgenden Typ:  
  
 [!code-csharp[DataContractAttribute#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/datacontractattribute/cs/overview.cs#4)]
 [!code-vb[DataContractAttribute#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/datacontractattribute/vb/overview.vb#4)]  
  
 Die Serialisierung in XML wird wie folgt durchgeführt:  
  
```xml  
<MyDataContract xmlns="http://schemas.contoso.com">  
    <myDataMember>  
        <myElement xmlns="" myAttribute="myValue">  
            myContents  
        </myElement>  
    </myDataMember>  
</MyDataContract>  
```  
  
 Beachten Sie, dass immer noch das Wrapper-Datenmemberelement `<myDataMember>` vorhanden ist. Es gibt keine Möglichkeit, dieses Element im Datenvertragsmodell zu entfernen. Die Serialisierungsprogramme, die dieses Modell verarbeiten (<xref:System.Runtime.Serialization.DataContractSerializer> und <xref:System.Runtime.Serialization.NetDataContractSerializer>), können spezielle Attribute in dieses Wrapperelement einfügen. Diese Attribute enthalten das standardmäßige XML-Schemainstanzattribut "nil" (damit das `XmlElement``null` sein kann) und das Attribut "type" (damit das `XmlElement` polymorph verwendet werden kann). Außerdem sind die folgenden XML-Attribute spezifisch für WCF: "ID", "ref", "Type" und "Assembly". Diese Attribute können ausgegeben werden, um die Verwendung von `XmlElement` bei aktiviertem Objektdiagramm-Beibehaltungsmodus zu unterstützen, oder indem <xref:System.Runtime.Serialization.NetDataContractSerializer> verwendet wird. (Weitere Informationen zum Objekt Diagramm-Beibehaltungs Modus finden Sie unter [Serialisierung und Deserialisierung](serialization-and-deserialization.md).)  
  
 Arrays oder Auflistungen von `XmlElement` sind zulässig und werden wie andere Arrays oder Auflistungen behandelt. Es wird ein Wrapperelement für die gesamte Auflistung und ein separates Wrapperelement (auf ähnliche Weise wie  im vorherigen Beispiel) für jedes  im Array verwendet.  
  
 Bei der Deserialisierung erstellt das Deserialisierungsprogramm aus den eingehenden XML-Daten ein `XmlElement`. Ein gültiges übergeordnetes <xref:System.Xml.XmlDocument> wird vom Deserialisierungsprogramm bereitgestellt.  
  
 Stellen Sie sicher, dass für das XML-Fragment, das in ein `XmlElement` deserialisiert wird, alle verwendeten Präfixe definiert sind, und dass es nicht von den Präfixdefinitionen übergeordneter Elemente abhängig ist. Dies ist nur von Bedeutung, wenn Sie `DataContractSerializer` verwenden, um auf XML von einer anderen Quelle (als `DataContractSerializer`) zuzugreifen.  
  
 Bei der Verwendung mit `DataContractSerializer` kann der `XmlElement` polymorphisch zugewiesen werden, jedoch nur für einen Datenmember vom Typ <xref:System.Object> . Auch wenn es <xref:System.Collections.IEnumerable> implementiert, kann ein `XmlElement` nicht als Auflistungstyp verwendet und keinem <xref:System.Collections.IEnumerable>-Datenmember zugeordnet werden. Wie bei allen polymorphen Zuweisungen gibt den `DataContractSerializer` Daten Vertrags Namen in der resultierenden XML-– in diesem Fall ist es "XmlElement" im http://schemas.datacontract.org/2004/07/System.Xml Namespace "".  
  
 Mit `NetDataContractSerializer` wird jede gültige polymorphe Zuweisung von `XmlElement` (zu `Object` oder `IEnumerable`) unterstützt.  
  
 Versuchen Sie nicht, eines der Serialisierungsprogramme in Verbindung mit Typen zu verwenden, die von `XmlElement` abgeleitet sind, ob polymorph oder auf andere Weise.  
  
### <a name="array-of-xmlnode"></a>XmlNode-Array  
 Das Verwenden von <xref:System.Xml.XmlNode>-Arrays ähnelt stark der Verwendung von `XmlElement`. Wenn Sie `XmlNode`-Arrays verwenden, können Sie flexibler arbeiten, als wenn Sie `XmlElement` verwenden. Sie können innerhalb des Datenmember-Wrapperelements mehrere Elemente schreiben. Neben Elementen können Sie auch andere Inhalte in das Datenmember-Wrapperelement einfügen, zum Beispiel XML-Kommentare. Außerdem können Sie bei Bedarf Attribute in das Datenmember-Wrapperelement einfügen. Sie können diese Schritte ausführen, indem Sie das `XmlNode`-Array mit spezifischen von `XmlNode` abgeleiteten Klassen auffüllen, zum Beispiel mit <xref:System.Xml.XmlAttribute>, `XmlElement` oder <xref:System.Xml.XmlComment>. Verwenden Sie z.&#160;B. den folgenden Typ:  
  
 [!code-csharp[DataContractAttribute#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/datacontractattribute/cs/overview.cs#5)]
 [!code-vb[DataContractAttribute#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/datacontractattribute/vb/overview.vb#5)]  
  
 Nach der Serialisierung sind die sich ergebenden XML-Daten folgendem Code ähnlich:  
  
```xml  
<MyDataContract xmlns="http://schemas.contoso.com">  
  <myDataMember myAttribute="myValue">  
     <!--myComment-->  
     <myElement xmlns="" myAttribute="myValue">  
 myContents  
     </myElement>  
     <myElement xmlns="" myAttribute="myValue">  
       myContents  
     </myElement>  
  </myDataMember>  
</MyDataContract>  
```  
  
 Beachten Sie, dass das Datenmember-Wrapperelement `<myDataMember>` ein Attribut, einen Kommentar und zwei Elemente enthält. Dies sind die vier `XmlNode`-Instanzen, die serialisiert wurden.  
  
 Ein `XmlNode`-Array, das zu ungültigen XML-Daten führen würde, kann nicht serialisiert werden. Ein Array mit zwei `XmlNode`-Instanzen, von der die erste ein `XmlElement` und die zweite ein <xref:System.Xml.XmlAttribute> ist, ist zum Beispiel ungültig, da diese Folge keiner gültigen XML-Instanz entspricht (es gibt keine Möglichkeit, das Attribut anzufügen).  
  
 Bei der Deserialisierung eines `XmlNode`-Arrays werden Knoten erstellt und mit den Informationen aus den eingehenden XML-Daten aufgefüllt. Ein gültiges übergeordnetes <xref:System.Xml.XmlDocument> wird vom Deserialisierungsprogramm bereitgestellt. Alle Knoten werden deserialisiert, einschließlich aller Attribute für das Wrapper-Datenmember-Element, jedoch ohne die Attribute, die von den WCF-Serialisierern eingefügt werden (z. b. die Attribute, die zum Angeben der polymorphen Zuweisung verwendet werden). Die Einschränkung in Bezug auf die Definition aller Namespacepräfixe im XML-Fragment gilt für die Deserialisierung von `XmlNode`-Arrays genauso, wie sie für die Deserialisierung von `XmlElement` gilt.  
  
 Wenn Sie die Serialisierungsprogramme bei aktivierter Objektdiagrammbeibehaltung verwenden, wird die Objektgleichheit nur auf der Ebene der `XmlNode`-Arrays beibehalten, nicht für die einzelnen `XmlNode`-Instanzen.  
  
 Versuchen Sie nicht, ein `XmlNode`-Array zu serialisieren, wenn einer oder mehrere Knoten auf `null` festgelegt sind. Es ist zulässig, dass das gesamte Array `null` ist, nicht jedoch ein einzelner `XmlNode` im Array. Wenn der gesamte Arraymember 0 ist, enthält das Datenmember-Wrapperelement ein spezielles Attribut, das diesen Nullwert angibt. Bei der Deserialisierung wird auch der ganze Arraymember 0.  
  
 Nur normale `XmlNode`-Arrays werden vom Serialisierungsprogramm besonders behandelt. Datenmember, die als andere, `XmlNode` enthaltende Auflistungstypen deklariert sind, oder Datenmember, die als Arrays von Typen deklariert sind, die von `XmlNode` abgeleitet sind, werden nicht besonders behandelt. Aus diesem Grund sind sie normalerweise nicht serialisierbar, es sei denn, sie erfüllen auch eines der Kriterien für die Serialisierbarkeit.  
  
 Arrays oder Auflistungen von Arrays von `XmlNode` sind zulässig. Es wird ein Wrapperelement für die gesamte Auflistung und ein separates Wrapperelement (auf ähnliche Weise wie  im Beispiel oben) für jedes -Array im äußeren Array bzw. in der äußeren Auflistung verwendet.  
  
 Das Auffüllen eines Datenmembers vom Typ <xref:System.Array> von `Object` oder `Array` von `IEnumerable` mit `XmlNode`-Instanzen führt nicht dazu, dass der Datenmember als `Array` mit `XmlNode`-Instanzen behandelt wird. Jeder Arraymember wird getrennt serialisiert.  
  
 Bei der Verwendung mit `DataContractSerializer` können `XmlNode`-Arrays polymorph zugewiesen werden, jedoch nur für einen Datenmember vom Typ `Object`. Auch wenn es `IEnumerable` implementiert, kann ein `XmlNode`-Array nicht als Auflistungstyp verwendet und keinem `IEnumerable`-Datenmember zugeordnet werden. Wie bei allen polymorphen Zuweisungen gibt den `DataContractSerializer` Daten Vertrags Namen in der resultierenden XML-– in diesem Fall "ArrayOfXmlNode" im http://schemas.datacontract.org/2004/07/System.Xml Namespace "" aus. Bei Verwendung mit `NetDataContractSerializer` wird jede gültige Zuweisung eines `XmlNode` Arrays unterstützt.  
  
### <a name="schema-considerations"></a>Schemaüberlegungen  
 Ausführliche Informationen zur Schema Zuordnung von XML-Typen finden Sie unter [Daten Vertrags Schema-Referenz](data-contract-schema-reference.md). Dieser Abschnitt enthält eine Zusammenfassung der wichtigen Punkte.  
  
 Ein Datenmember vom Typ `XmlElement` wird einem Element zugeordnet, das mithilfe des folgenden anonymen Typs definiert wurde.  
  
```xml  
<xsd:complexType>  
   <xsd:sequence>  
      <xsd:any minOccurs="0" processContents="lax" />  
   </xsd:sequence>  
</xsd:complexType>  
```  
  
 Ein Datenmember vom Typ `XmlNode`-Array wird einem Element zugeordnet, das mithilfe des folgenden anonymen Typs definiert wurde.  
  
```xml  
<xsd:complexType mixed="true">  
   <xsd:sequence>  
      <xsd:any minOccurs="0" maxOccurs="unbounded" processContents="lax" />  
   </xsd:sequence>  
   <xsd:anyAttribute/>  
</xsd:complexType>  
```  
  
## <a name="types-implementing-the-ixmlserializable-interface"></a>Typen, die die IXmlSerializable-Schnittstelle implementieren  
 Typen, die die `IXmlSerializable`-Schnittstelle implementieren, werden von `DataContractSerializer` vollständig unterstützt. Sie sollten das <xref:System.Xml.Serialization.XmlSchemaProviderAttribute>-Attribut immer auf diese Typen anwenden, um das dazugehörige Schema zu steuern.  
  
 Es gibt drei Varianten von Typen, die `IXmlSerializable` implementieren: Typen, die beliebigen Inhalt darstellen, Typen, die ein einzelnes Element darstellen, und ältere <xref:System.Data.DataSet>-Typen.  
  
- Inhaltstypen verwenden eine vom `XmlSchemaProviderAttribute`-Attribut angegebene Schemaanbietermethode. Die Methode gibt nicht `null` zurück, und die <xref:System.Xml.Serialization.XmlSchemaProviderAttribute.IsAny%2A>-Eigenschaft des Attributs wird auf ihrem Standardwert `false` belassen. Dies ist die häufigste Verwendung von `IXmlSerializable`-Typen.  
  
- Elementtypen werden verwendet, wenn ein `IXmlSerializable`-Typ seinen eigenen Stammelementnamen kontrollieren muss. Um einen Typ als Elementtyp zu kennzeichnen, legen Sie entweder die <xref:System.Xml.Serialization.XmlSchemaProviderAttribute.IsAny%2A>-Eigenschaft des <xref:System.Xml.Serialization.XmlSchemaProviderAttribute>-Attributs auf `true` fest, oder geben Sie über die Schemaanbietermethode 0 zurück. Die Verwendung einer Schemaanbietermethode ist für Elementtypen optional. Sie können unter `XmlSchemaProviderAttribute` anstatt des Methodennamens auch NULL angeben. Wenn `IsAny` jedoch `true` ist und eine Schemaanbietermethode angegeben ist, muss die Methode NULL zurückgeben.  
  
- Bei älteren <xref:System.Data.DataSet>-Typen handelt es sich um `IXmlSerializable`-Typen, die nicht mit dem `XmlSchemaProviderAttribute`-Attribut gekennzeichnet sind. Stattdessen verwenden sie zur Schemagenerierung die <xref:System.Xml.Serialization.IXmlSerializable.GetSchema%2A>-Methode. Dieses Muster wird für den `DataSet`-Typ und seine von ihm abgeleiteten typisierten Dataset-Klassen in älteren Versionen von .NET Framework verwendet. Es ist jedoch veraltet und wird nur aus Legacygründen noch unterstützt. Verlassen Sie sich nicht auf dieses Muster, und wenden Sie immer das `XmlSchemaProviderAttribute` auf Ihre `IXmlSerializable`-Typen an.  
  
### <a name="ixmlserializable-content-types"></a>IXmlSerializable-Inhaltstypen  
 Wenn Sie einen Datenmember eines Typs serialisieren, der `IXmlSerializable` implementiert und ein wie vorher definierter Inhaltstyp ist, schreibt das Serialisierungsprogramm das Wrapperelement für den Datenmember und übergibt die Steuerung an die <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>-Methode. Die <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>-Implementierung kann beliebige XML-Daten schreiben, auch zum Hinzufügen der Attribute zum Wrapperelement. Nachdem `WriteXml` abgeschlossen ist, schließt das Serialisierungsprogramm das Element.  
  
 Wenn Sie einen Datenmember eines Typs deserialisieren, der `IXmlSerializable` implementiert und ein wie vorher definierter Inhaltstyp ist, ordnet das Deserialisierungsprogramm den XML-Reader im Wrapperelement für den Datenmember an und übergibt die Steuerung an die <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A>-Methode. Die Methode muss das ganze Element lesen, einschließlich des Start- und Endtags. Stellen Sie sicher, dass der `ReadXml`-Code auch den Fall verarbeitet, in dem das Element leer ist. Außerdem sollte sich Ihre `ReadXml`-Implementierung nicht darauf verlassen, dass das Wrapperelement einen bestimmten Namen aufweist. Der Name wird vom Serialisierungsprogramm ausgewählt und kann variieren.  
  
 Es ist zulässig, `IXmlSerializable`-Inhaltstypen polymorph zuzuweisen, zum Beispiel zu Datenmembern vom Typ <xref:System.Object>. Es ist auch zulässig, dass die Typinstanzen NULL sind. Außerdem ist es möglich, `IXmlSerializable`-Typen bei aktivierter Objektdiagrammbeibehaltung und mit <xref:System.Runtime.Serialization.NetDataContractSerializer> zu verwenden. Alle diese Features erfordern, dass das WCF-Serialisierungsprogramm bestimmte Attribute in das Wrapper Element ("Nil" und "Type" im XML-Schema Instanz-Namespace und "ID", "ref", "Type" und "Assembly" in einem WCF-spezifischen Namespace anfügt).  
  
#### <a name="attributes-to-ignore-when-implementing-readxml"></a>Bei der Implementierung von ReadXml zu ignorierende Attribute  
 Bevor die Steuerung an Ihren `ReadXml`-Code übergeben wird, untersucht das Deserialisierungsprogramm das XML-Element, erkennt diese speziellen XML-Attribute und führt die erforderlichen Aktionen aus. Wenn "nil" zum Beispiel `true` ist, wird ein Nullwert deserialisiert, und `ReadXml` wird nicht aufgerufen. Falls Polymorphie erkannt wird, wird der Inhalt des Elements deserialisiert, als ob es sich um einen anderen Typ handeln würde. Die `ReadXml`-Implementierung des polymorph zugewiesenen Typs wird aufgerufen. Eine `ReadXml`-Implementierung sollte diese speziellen Attribute auf jeden Fall ignorieren, da sie vom Deserialisierungsprogramm verarbeitet werden.  
  
### <a name="schema-considerations-for-ixmlserializable-content-types"></a>Schemaüberlegungen für IXmlSerializable-Inhaltstypen  
 Beim Exportieren eines Schemas aus einem `IXmlSerializable`-Inhaltstyp wird die Schemaanbietermethode aufgerufen. Ein <xref:System.Xml.Schema.XmlSchemaSet> wird an die Schemaanbietermethode übergeben. Die Methode kann dem Schemasatz gültige Schemas hinzufügen. Der Schemasatz enthält das Schema, das zum Zeitpunkt des Schemaexports bereits bekannt ist. Wenn die Schemaanbietermethode dem Schemasatz ein Element hinzufügen muss, muss sie ermitteln, ob ein <xref:System.Xml.Schema.XmlSchema> mit dem geeigneten Namespace im Satz bereits vorhanden ist. Falls dies der Fall ist, muss die Schemaanbietermethode das neue Element dem vorhandenen `XmlSchema` hinzufügen. Andernfalls muss sie eine neue `XmlSchema`-Instanz erstellen. Dies ist wichtig, wenn Arrays mit `IXmlSerializable`-Typen verwendet werden. Wenn Sie zum Beispiel über einen `IXmlSerializable`-Typ verfügen, der als Typ "A" in Namespace "B" exportiert wird, ist es möglich, dass der Schemasatz beim Aufrufen der Schemaanbietermethode das Schema "B" bereits enthält, um den Typ "ArrayOfA" aufzunehmen.  
  
 Zusätzlich zum Hinzufügen von Typen zum <xref:System.Xml.Schema.XmlSchemaSet> muss die Schemaanbietermethode für Inhaltstypen einen anderen Wert als NULL zurückgeben. Sie kann ein <xref:System.Xml.XmlQualifiedName>-Element zurückgeben, das den Namen des Schematyps angibt, der für den jeweiligen `IXmlSerializable`-Typ verwendet wird. Dieser qualifizierte Name dient auch als Datenvertragsname und Namespace für den Typ. Es ist zulässig, einen Typ zurückzugeben, der nicht im Schemasatz vorhanden ist, wenn dies direkt nach der Rückgabe der Schemaanbietermethode erfolgt. Es wird jedoch vorausgesetzt, dass der Typ nach dem Export aller verwandten Typen (die <xref:System.Runtime.Serialization.XsdDataContractExporter.Export%2A>-Methode wird für alle relevanten Typen von <xref:System.Runtime.Serialization.XsdDataContractExporter> aufgerufen, und es wird auf die <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas%2A>-Eigenschaft zugegriffen) im Schemasatz vorhanden ist. Das Zugreifen auf die `Schemas`-Eigenschaft, bevor alle relevanten `Export`-Aufrufe durchgeführt wurden, kann zu einer <xref:System.Xml.Schema.XmlSchemaException> führen. Weitere Informationen zum Exportprozess finden Sie unter [Exportieren von Schemas aus Klassen](exporting-schemas-from-classes.md).  
  
 Die Schemaanbietermethode kann auch den zu verwendenden <xref:System.Xml.Schema.XmlSchemaType> zurückgeben. Der Typ kann anonym oder nicht anonym sein. Wenn er anonym ist, wird das Schema für den `IXmlSerializable`-Typ jeweils als anonymer Typ exportiert, wenn der `IXmlSerializable`-Typ als Datenmember verwendet wird. Der `IXmlSerializable`-Typ verfügt trotzdem noch über einen Datenvertragsnamen und einen Namespace. (Dies wird in [Daten Vertrags Namen](data-contract-names.md) beschrieben, mit der Ausnahme, dass das- <xref:System.Runtime.Serialization.DataContractAttribute> Attribut nicht zum Anpassen des Namens verwendet werden kann.) Wenn Sie nicht anonym ist, muss es sich um einen der Typen im Handeln `XmlSchemaSet` . Dies entspricht dem Zurückgeben von `XmlQualifiedName` für den Typ.  
  
 Zusätzlich wird für den Typ eine globale Elementdeklaration exportiert. Wenn auf den Typ nicht das <xref:System.Xml.Serialization.XmlRootAttribute>-Attribut angewendet wurde, weist das Element denselben Namen und Namespace wie der Datenvertrag auf, und seine "nil"-fähige Eigenschaft ist "true". Die einzige Ausnahme ist der Schema Namespace (" http://www.w3.org/2001/XMLSchema ") – Wenn sich der Datenvertrag des Typs in diesem Namespace befindet, befindet sich das entsprechende globale Element im leeren Namespace, da es unzulässig ist, dem Schema Namespace neue Elemente hinzuzufügen. Wenn auf den Typ das `XmlRootAttribute`-Attribut angewendet wurde, wird die globale Elementdeklaration exportiert, indem Folgendes verwendet wird: die Eigenschaften <xref:System.Xml.Serialization.XmlRootAttribute.ElementName%2A>, <xref:System.Xml.Serialization.XmlRootAttribute.Namespace%2A> und <xref:System.Xml.Serialization.XmlRootAttribute.IsNullable%2A>. Die bei angewendetem `XmlRootAttribute` geltenden Standardeinstellungen sind der Datenvertragsname, ein leerer Namespace und der Wert "true" für die Nullfähigkeit ("nillable").  
  
 Die gleichen Regeln für die globale Elementdeklaration gelten für Legacy-Datasettypen. Beachten Sie, dass das `XmlRootAttribute` keine globalen Elementdeklarationen überschreiben kann, die mithilfe von benutzerdefiniertem Code hinzugefügt wurden. Diese können mithilfe der Schemaanbietermethode dem `XmlSchemaSet` oder über `GetSchema` für Legacy-Datasettypen hinzugefügt worden sein.  
  
### <a name="ixmlserializable-element-types"></a>IXmlSerializable-Elementtypen  
 Für `IXmlSerializable`-Elementtypen ist entweder die `IsAny`-Eigenschaft auf `true` festgelegt, oder ihre Schemaanbietermethode gibt `null` zurück.  
  
 Das Serialisieren und Deserialisieren eines Elementtyps ähnelt stark dem Serialisieren und Deserialisieren eines Inhaltstyps. Es gibt jedoch einige wichtige Unterschiede:  
  
- Von der `WriteXml`-Implementierung wird erwartet, dass sie genau ein Element schreibt (das natürlich mehrere untergeordnete Elemente enthalten kann). Sie sollte keine Attribute außerhalb dieses einzelnen Elements, mehrerer gleichgeordneter Elemente oder gemischten Inhalts schreiben. Das Element ist ggf. leer.  
  
- Die `ReadXml`-Implementierung sollte das Wrapperelement nicht lesen. Es wird erwartet, dass sie das einzelne Element liest, das von `WriteXml` erzeugt wird.  
  
- Wenn das Serialisierungsprogramm regelmäßig einen Elementtyp serialisiert (zum Beispiel als Datenmember in einem Datenvertrag), gibt das Serialisierungsprogramm ein Wrapperelement aus, bevor `WriteXml` aufgerufen wird. Dies entspricht der Vorgehensweise bei Inhaltstypen. Bei der Serialisierung eines Elementtyps auf der obersten Ebene gibt das Serialisierungsprogramm normalerweise jedoch kein Wrapperelement für das Element aus, das `WriteXml` schreibt. Dies ist nur der Fall, wenn beim Erstellen des Serialisierungsprogramms in den Konstruktoren `DataContractSerializer` oder `NetDataContractSerializer` explizit ein Stammname und ein Namespace angegeben wurde. Weitere Informationen finden Sie unter [Serialisierung und Deserialisierung](serialization-and-deserialization.md).  
  
- Beim Serialisieren eines Elementtyps auf der obersten Ebene, ohne zur Entwurfszeit den Stammnamen und einen Namespace anzugeben, führen <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteStartObject%2A> und <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteEndObject%2A> im Wesentlichen keine Aktionen aus, und <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteObjectContent%2A> ruft einfach `WriteXml` auf. In diesem Modus kann das Objekt, das serialisiert wird, nicht NULL sein und nicht polymorph zugewiesen werden. Außerdem kann die Objektdiagrammbeibehaltung nicht aktiviert und `NetDataContractSerializer` kann nicht verwendet werden.  
  
- Beim Deserialisieren eines Elementtyps auf der obersten Ebene, ohne zur Entwurfszeit den Stammnamen und den Namespace anzugeben, gibt <xref:System.Runtime.Serialization.XmlObjectSerializer.IsStartObject%2A> den Wert `true` zurück, wenn der Anfang eines beliebigen Elements gefunden werden kann. <xref:System.Runtime.Serialization.XmlObjectSerializer.ReadObject%2A> mit auf `verifyObjectName` festgelegtem `true`-Parameter verhält sich genau so wie `IsStartObject`, bevor das Objekt gelesen wird. `ReadObject` übergibt das Steuerelement dann an die `ReadXml`-Methode.  
  
 Das Schema, das für die Elementtypen exportiert wird, entspricht dem Schema für den `XmlElement`-Typ, wie in einem Abschnitt weiter oben beschrieben. Es gilt jedoch die Ausnahme, dass die Schemaanbietermethode wie bei Inhaltstypen dem <xref:System.Xml.Schema.XmlSchemaSet> zusätzliche Schemas hinzufügen kann. Das Verwenden des `XmlRootAttribute`-Attributs mit Elementtypen ist nicht zulässig, und globale Elementdeklarationen werden für diese Typen nicht ausgegeben.  
  
### <a name="differences-from-the-xmlserializer"></a>Unterschiede zu XmlSerializer  
 Die `IXmlSerializable`-Schnittstelle und das `XmlSchemaProviderAttribute`- und `XmlRootAttribute`-Attribut werden vom <xref:System.Xml.Serialization.XmlSerializer> auch verstanden. Aber es gibt einige Unterschiede dabei, wie diese Elemente im Datenvertragsmodell behandelt werden. Die wichtigsten Unterschiede werden im Folgenden zusammengefasst:  
  
- Die Schemaanbietermethode muss öffentlich sein, um im `XmlSerializer` verwendet werden zu können. Sie muss jedoch nicht öffentlich sein, um im Datenvertragsmodell verwendet werden zu können.  
  
- Die Schemaanbietermethode wird aufgerufen, wenn für `IsAny` im Datenvertragsmodell "true" gilt, jedoch nicht für den `XmlSerializer`.  
  
- Wenn das `XmlRootAttribute`-Attribut für Inhalts- oder Legacy-Datasettypen nicht vorhanden ist, exportiert der `XmlSerializer` eine globale Elementdeklaration in den leeren Namespace. Im Datenvertragsmodell ist der verwendete Namespace normalerweise der Datenvertragsnamespace, wie bereits beschrieben.  
  
 Beachten Sie diese Unterschiede, wenn Sie Typen erstellen, die mit beiden Serialisierungstechnologien verwendet werden.  
  
### <a name="importing-ixmlserializable-schema"></a>Importieren von IXmlSerializable-Schemas  
 Beim Importieren eines Schemas, das aus `IXmlSerializable`-Typen generiert wurde, gibt es verschiedene Möglichkeiten:  
  
- Das generierte Schema kann ein gültiges Daten Vertrags Schema sein, wie unter [Daten Vertrags Schema-Referenz](data-contract-schema-reference.md)beschrieben. In diesem Fall kann das Schema auf die übliche Weise importiert werden, und es werden normale Datenvertragstypen generiert.  
  
- Bei dem generierten Schema kann es sich auch um ein nicht gültiges Datenvertragsschema handeln. Ihre Schemaanbietermethode kann zum Beispiel Schemas mit XML-Attributen generieren, die im Datenvertragsmodell nicht unterstützt werden. In diesem Fall können Sie das Schema als `IXmlSerializable`-Typen importieren. Dieser Import Modus ist standardmäßig nicht aktiviert, kann jedoch problemlos aktiviert werden – z. b. mit dem `/importXmlTypes` Befehls Zeilenschalter zum [Service Model Metadata Utility-Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md). Dies wird im Abschnitt [Importieren von Schemas zum Generieren von Klassen](importing-schema-to-generate-classes.md)ausführlich beschrieben. Beachten Sie, dass Sie für die Typinstanzen direkt mit den XML-Daten arbeiten müssen. Sie können auch erwägen, eine andere Serialisierungstechnologie zu verwenden, die einen größeren Schemabereich unterstützt. Weitere Informationen finden Sie im Thema zur Verwendung von `XmlSerializer`.  
  
- Es ist ratsam, Ihre vorhandenen `IXmlSerializable`-Typen im Proxy wiederzuverwenden, anstatt neue zu generieren. In diesem Fall können Sie die Funktion mit den referenzierten Typen verwenden, die im Thema zum Importieren von Schemas zum Generieren von Typen beschrieben ist, um den wiederzuverwendenden Typ anzugeben. Dies entspricht dem Verwenden des Schalters `/reference` für „svcutil.exe“. Damit wird die Assembly angegeben, die die wiederzuverwendenden Typen enthält.  
  
## <a name="representing-arbitrary-xml-in-data-contracts"></a>Darstellen von beliebigen XML-Daten in Datenverträgen  
 Mithilfe der Typen `XmlElement`, `XmlNode`-Array und `IXmlSerializable` können Sie beliebige XML-Daten in das Datenvertragsmodell einfügen. `DataContractSerializer` und `NetDataContractSerializer` übergeben diesen XML-Inhalt an den verwendeten XML-Writer, ohne dabei den Prozess zu beeinträchtigen. Die XML-Writer können jedoch bestimmte Einschränkungen für die XML-Daten erzwingen, die sie schreiben. Unten sind einige wichtige Beispiele aufgeführt:  
  
- Die XML-Writer erlauben in der Regel keine XML-Dokument Deklaration (z \<?xml version=’1.0’ ?> . b.) in der Mitte des Schreibens eines anderen Dokuments. Sie können kein vollständiges XML-Dokument als `Array`-`XmlNode` für einen Datenmember serialisieren. Dazu müssen Sie entweder die Dokumentdeklaration entfernen oder Ihr eigenes Codierungsschema für die Darstellung verwenden.  
  
- Alle mit WCF bereitgestellten XML-Writer weisen XML-Verarbeitungsanweisungen ( \<? … ?> ) und Dokumenttyp Definitionen ( \<! … > ) auf, da Sie in SOAP-Nachrichten nicht zulässig sind. Auch hier können Sie Ihren eigenen Codierungsmechanismus verwenden, um diese Einschränkung zu umgehen. Wenn Sie dies in die sich ergebenden XML-Daten einfügen müssen, können Sie einen benutzerdefinierten Encoder schreiben, der XML-Writer mit der entsprechenden Unterstützung verwendet.  
  
- Wenn Sie `WriteXml` implementieren, sollten Sie es vermeiden, die <xref:System.Xml.XmlWriter.WriteRaw%2A>-Methode für den XML-Writer aufzurufen. WCF verwendet eine Vielzahl von XML-Codierungen (einschließlich Binärdateien), es ist sehr schwierig oder unmöglich, zu verwenden, `WriteRaw` sodass das Ergebnis in beliebiger Codierung verwendbar ist.  
  
- `WriteXml`Vermeiden Sie beim Implementieren von die Verwendung der <xref:System.Xml.XmlWriter.WriteEntityRef%2A> <xref:System.Xml.XmlWriter.WriteNmToken%2A> Methoden und, die für die mit WCF bereitgestellten XML-Writer nicht unterstützt werden.  
  
## <a name="using-dataset-typed-dataset-and-datatable"></a>Verwenden von DataSet, typisiertem DataSet und DataTable  
 Die Verwendung dieser Typen wird im Datenvertragsmodell vollständig unterstützt. Beachten Sie beim Verwenden dieser Typen die folgenden Punkte:  
  
- Das Schema für diese Typen (vor allem <xref:System.Data.DataSet> und seine typisierten abgeleiteten Klassen) ist möglicherweise nicht mit einigen nicht-WCF-Plattformen interoperabel oder kann bei der Verwendung mit diesen Plattformen zu schlechten Nutzbarkeit führen. Außerdem kann die Verwendung des `DataSet`-Typs zu Leistungseinbußen führen. Zudem kann es das Versehen Ihrer Anwendung mit einer Versionsangabe erschweren. Sie können erwägen, anstelle von `DataSet`-Typen in Ihren Verträgen explizit definierte Datenvertragstypen zu verwenden.  
  
- Beim Importieren von `DataSet`- oder `DataTable`-Schemas ist es wichtig, auf diese Typen zu verweisen. Mit dem Befehlszeilen Tool "Svcutil. exe" kann dies erreicht werden, indem der Assemblyname "System. Data. dll" an den Switch übergeben wird `/reference` . Wenn Sie typisierte Datasetschemas importieren, müssen Sie auf den Typ des typisierten Datasets verweisen. Übergeben Sie mit "Svcutil. exe" den Speicherort der Assembly des typisierten Datasets an den `/reference` Schalter. Weitere Informationen zu Verweis Typen finden Sie unter Importieren von [Schemas zum Generieren von Klassen](importing-schema-to-generate-classes.md).  
  
 Die Unterstützung typisierter DataSets im Datenvertragsmodell ist beschränkt. Typisierte DataSets können serialisiert und deserialisiert werden und können ihr Schema exportieren. Jedoch kann der Datenvertragsschemaimport keine neuen typisierte Dataset-Typen aus dem Schema generieren, sondern nur schon vorhandene wiederverwenden. Sie können mithilfe des `/r`-Schalters von Svcutil.exe auf ein vorhandenes typisiertes DataSet verweisen. Wenn Sie versuchen, Svcutil.exe ohne den `/r`-Schalter für einen Dienst einzusetzen, der ein typisiertes DataSet verwendet, wird automatisch ein alternatives Serialisierungsprogramm (XmlSerializer) ausgewählt. Wenn Sie den DataContractSerializer verwenden und DataSets aus dem Schema generieren müssen, können Sie zu dem folgenden Verfahren greifen: Generieren Sie die typisierten DataSet-Typen (indem Sie das Tool Xsd.exe mit dem Schalter `/d` für den Dienst verwenden), kompilieren Sie die Typen, und verweisen Sie dann mithilfe des `/r`-Schalters von Svcutil.exe auf diese Typen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Xml.Serialization.IXmlSerializable>
- [Verwenden von Datenverträgen](using-data-contracts.md)
- [Vom Datenvertragsserialisierer unterstützte Typen](types-supported-by-the-data-contract-serializer.md)
