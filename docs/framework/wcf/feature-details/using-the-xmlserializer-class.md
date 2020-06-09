---
title: Verwenden der XmlSerializer-Klasse
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XmlSerializer [WCF], using
ms.assetid: c680602d-39d3-44f1-bf22-8e6654ad5069
ms.openlocfilehash: 2ef2d0eefb571f64040fabd16fd65fdfde7a626d
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600204"
---
# <a name="using-the-xmlserializer-class"></a>Verwenden der XmlSerializer-Klasse

Windows Communication Foundation (WCF) kann zwei verschiedene Serialisierungstechnologien verwenden, um die Daten in der Anwendung in XML umzuwandeln, das zwischen Clients und Diensten übertragen wird, einem Prozess, der als Serialisierung bezeichnet wird.

## <a name="datacontractserializer-as-the-default"></a>DataContractSerializer als Standard

WCF verwendet standardmäßig die- <xref:System.Runtime.Serialization.DataContractSerializer> Klasse, um Datentypen zu serialisieren. Dieses Serialisierungsprogramm unterstützt die folgenden Typen:

- Primitive Typen (z. B. ganze Zahlen, Zeichenfolgen und Bytearrays) sowie einige spezielle Typen wie <xref:System.Xml.XmlElement> und <xref:System.DateTime>, die als Primitive behandelt werden.

- Datenvertragstypen (mit dem <xref:System.Runtime.Serialization.DataContractAttribute>-Attribut markierte Typen).

- Mit dem <xref:System.SerializableAttribute>-Attribut markierte Typen, einschließlich Typen, die die <xref:System.Runtime.Serialization.ISerializable>-Schnittstelle implementieren.

- Typen, die die <xref:System.Xml.Serialization.IXmlSerializable>-Schnittstelle implementieren.

- Viele allgemeine Auflistungstypen, einschließlich vieler generischer Auflistungstypen.

Viele .NET Framework Typen fallen in die beiden letzteren Kategorien und sind daher serialisierbar. Arrays serialisierbarer Typen sind ebenfalls serialisierbar. Eine umfassende Liste finden Sie unter [Angeben von Datenübertragung in Dienstverträgen](specifying-data-transfer-in-service-contracts.md).

Der <xref:System.Runtime.Serialization.DataContractSerializer> , der in Verbindung mit Daten Vertragstypen verwendet wird, ist die empfohlene Methode zum Schreiben neuer WCF-Dienste. Weitere Informationen finden Sie unter [Verwenden von Daten Verträgen](using-data-contracts.md).

## <a name="when-to-use-the-xmlserializer-class"></a>Verwendung der XmlSerializer-Klasse

WCF unterstützt auch die- <xref:System.Xml.Serialization.XmlSerializer> Klasse. Die- <xref:System.Xml.Serialization.XmlSerializer> Klasse ist nicht für WCF eindeutig. Es handelt sich um das gleiche Serialisierungsmodul, das ASP.NET-Webdienste verwenden. Die <xref:System.Xml.Serialization.XmlSerializer>-Klasse unterstützt deutlich weniger Typen als die <xref:System.Runtime.Serialization.DataContractSerializer>-Klasse, ermöglicht jedoch eine größere Kontrolle über das resultierende XML und unterstützt den XSD-Schemastandard (XML Schema definition language) stärker. Sie erfordert außerdem keine deklarativen Attribute für die serialisierbaren Typen. Weitere Informationen finden Sie im Thema zur XML-Serialisierung in der .NET Framework-Dokumentation. Die <xref:System.Xml.Serialization.XmlSerializer>-Klasse unterstützt keine Datenvertragstypen.

Wenn Sie "Svcutil. exe" oder das **Dienstverweis hinzufügen** Feature in Visual Studio verwenden, um Client Code für einen Drittanbieter Dienst zu generieren, oder um auf ein Drittanbieter Schema zuzugreifen, wird automatisch ein geeignetes Serialisierungsprogramm für Sie ausgewählt. Wenn das Schema nicht mit <xref:System.Runtime.Serialization.DataContractSerializer> kompatibel ist, wird <xref:System.Xml.Serialization.XmlSerializer> ausgewählt.

## <a name="manually-switching-to-the-xmlserializer"></a>Manuelles Wechseln zu XmlSerializer

Es kann vorkommen, dass Sie manuell zu <xref:System.Xml.Serialization.XmlSerializer> wechseln müssen. Dies ist beispielsweise in den folgenden Situationen der Fall:

- Beim Migrieren einer Anwendung von ASP.NET-Webdiensten zu WCF empfiehlt es sich, vorhandene, <xref:System.Xml.Serialization.XmlSerializer> -kompatible Typen wiederzuverwenden, anstatt neue Daten Vertragstypen zu erstellen.

- Wenn die präzise Steuerung von in Nachrichten enthaltenen XML-Daten wichtig ist, jedoch kein WSDL (Web Services Description Language)-Dokument zur Verfügung steht, z.&#160;B. beim Erstellen eines Diensts mit Typen, die einem bestimmten standardisierten, veröffentlichten Schema entsprechen müssen, das nicht mit dem DataContractSerializer kompatibel ist.

- Beim Erstellen von Diensten, die dem älteren SOAP-Codierungsstandard folgen.

In diesen und anderen Fällen können Sie manuell zur <xref:System.Xml.Serialization.XmlSerializer>-Klasse wechseln, indem Sie das `XmlSerializerFormatAttribute`-Attribut auf den Dienst anwenden, wie im folgenden Code dargestellt.

[!code-csharp[c_XmlSerializer#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_xmlserializer/cs/source.cs#1)]
[!code-vb[c_XmlSerializer#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_xmlserializer/vb/source.vb#1)]

## <a name="security-considerations"></a>Überlegungen zur Sicherheit

> [!NOTE]
> Beim Wechseln von Serialisierungs-Engines ist große Sorgfalt geboten. Derselbe Typ kann je nach verwendetem Serialisierungsprogramm mehrere Serialisierungskonzepte umfassen. Wenn Sie versehentlich das falsche Serialisierungsprogramm verwenden, legen Sie möglicherweise Informationen aus dem Typ offen, deren Offenlegung Sie nicht beabsichtigt haben.

Beispielsweise serialisiert die <xref:System.Runtime.Serialization.DataContractSerializer>-Klasse beim Serialisieren von Datenvertragstypen nur mit dem <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribut markierte Member. Die <xref:System.Xml.Serialization.XmlSerializer>-Klasse serialisiert jeden öffentlichen Member. Beachten Sie den Typ im folgenden Code:

[!code-csharp[c_XmlSerializer#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_xmlserializer/cs/source.cs#2)]
[!code-vb[c_XmlSerializer#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_xmlserializer/vb/source.vb#2)]

Wenn der Typ versehentlich in einem Dienstvertrag verwendet wird, in dem die <xref:System.Xml.Serialization.XmlSerializer>-Klasse ausgewählt ist, wird der `creditCardNumber`-Member serialisiert, was wahrscheinlich nicht beabsichtigt ist.

Auch wenn die <xref:System.Runtime.Serialization.DataContractSerializer>-Klasse der Standard ist, können Sie sie explizit für Ihren Dienst auswählen (obwohl dies nie erforderlich sein sollte), indem Sie das <xref:System.ServiceModel.DataContractFormatAttribute>-Attribut auf den Dienstvertragstyp anwenden.

Das für den Dienst verwendete Serialisierungsprogramm ist ein wesentlicher Bestandteil des Vertrags und kann durch Auswahl einer anderen Bindung oder durch Ändern anderer Konfigurationseinstellungen nicht geändert werden.

Andere wichtige Sicherheitsüberlegungen gelten für die <xref:System.Xml.Serialization.XmlSerializer>-Klasse. Zuerst wird dringend empfohlen, dass jede WCF-Anwendung, die die-Klasse verwendet, <xref:System.Xml.Serialization.XmlSerializer> mit einem Schlüssel signiert wird, der von der-Offenlegung geschützt wird. Diese Empfehlung gilt sowohl für das manuelle Wechseln zu <xref:System.Xml.Serialization.XmlSerializer> als auch ein automatisches Wechseln (mit Svcutil.exe, "Dienstverweis hinzufügen" oder ein ähnliches Tool). Dies liegt daran, dass das <xref:System.Xml.Serialization.XmlSerializer> Serialisierungsmodul das Laden von *vorgenerierten Serialisierungsassemblys* unterstützt, sofern diese mit demselben Schlüssel wie die Anwendung signiert sind. Eine nicht signierte Anwendung ist vollständig ungeschützt gegen die Möglichkeit, dass eine bösartige Assembly, die mit dem erwarteten Namen der vorgenerierten Serialisierungsassembly übereinstimmt, im Anwendungsordner oder im globalen Assemblycache platziert wird. Natürlich muss ein Angreifer zuerst Schreibzugriff auf einen der beiden Speicherorte erhalten, um diese Aktion auszuführen.

Eine weitere Bedrohung, die beim Verwenden von <xref:System.Xml.Serialization.XmlSerializer> vorhanden ist, hängt mit dem Schreibzugriff auf den temporären Ordners des Systems zusammen. Die <xref:System.Xml.Serialization.XmlSerializer> Serialisierungs-Engine erstellt und verwendet temporäre *Serialisierungsassemblys* in diesem Ordner. Sie sollten sich der Tatsache bewusst sein, dass jeder Vorgang mit Schreibzugriff auf den temporären Ordner diese Serialisierungsassemblys mit bösartigem Code überschreiben kann.

## <a name="rules-for-xmlserializer-support"></a>Regeln für XmlSerializer-Unterstützung

Sie können mit <xref:System.Xml.Serialization.XmlSerializer> kompatible Attribute nicht direkt auf Vertragsvorgangsparameter oder Rückgabewerte anwenden. Sie können jedoch auf typisierte Nachrichten (Nachrichtenvertragstextteile) angewendet werden, wie der folgende Code zeigt:

[!code-csharp[c_XmlSerializer#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_xmlserializer/cs/source.cs#3)]
[!code-vb[c_XmlSerializer#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_xmlserializer/vb/source.vb#3)]

Beim Anwenden auf typisierte Nachrichtenmember überschreiben diese Attribute Eigenschaften, die mit den typisierten Nachrichtenattributen in Konflikt stehen. Beispielsweise wird im folgenden Code `ElementName` durch `Name` überschrieben.

[!code-csharp[c_XmlSerializer#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_xmlserializer/cs/source.cs#4)]
[!code-vb[c_XmlSerializer#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_xmlserializer/vb/source.vb#4)]

Das <xref:System.ServiceModel.MessageHeaderArrayAttribute>-Attribut wird nicht unterstützt, wenn <xref:System.Xml.Serialization.XmlSerializer> verwendet wird.

> [!NOTE]
> In diesem Fall löst die <xref:System.Xml.Serialization.XmlSerializer> folgende Ausnahme aus, die vor WCF freigegeben wird: "ein Element, das auf der obersten Schema Ebene deklariert wurde, kann nicht über `maxOccurs` > 1 verfügen. Geben Sie ein Wrapperelement für "more" an, indem Sie `XmlArray` oder `XmlArrayItem` anstelle von `XmlElementAttribute` verwenden oder indem Sie den Wrapped-Parameterstil verwenden.
>
> Wenn Sie eine solche Ausnahme empfangen, prüfen Sie, ob diese Situation zutrifft.

WCF unterstützt das <xref:System.Xml.Serialization.SoapIncludeAttribute> -Attribut und das- <xref:System.Xml.Serialization.XmlIncludeAttribute> Attribut in Nachrichten Verträgen und Vorgangs Verträgen nicht. verwenden Sie stattdessen das- <xref:System.Runtime.Serialization.KnownTypeAttribute> Attribut.

## <a name="types-that-implement-the-ixmlserializable-interface"></a>Typen, die die IXmlSerializable-Schnittstelle implementieren

Typen, die die `IXmlSerializable`-Schnittstelle implementieren, werden von `DataContractSerializer` vollständig unterstützt. Sie sollten das <xref:System.Xml.Serialization.XmlSchemaProviderAttribute>-Attribut immer auf diese Typen anwenden, um das dazugehörige Schema zu steuern.

> [!WARNING]
> Wenn Sie polymorphe Typen verwenden, müssen Sie <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> auf den Typ anwenden, um sicherzustellen, dass der richtige Typ serialisiert wird.

Es gibt drei Varianten von Typen, die `IXmlSerializable` implementieren: Typen, die beliebigen Inhalt darstellen, Typen, die ein einzelnes Element darstellen, und ältere <xref:System.Data.DataSet>-Typen.

- Inhaltstypen verwenden eine vom `XmlSchemaProviderAttribute`-Attribut angegebene Schemaanbietermethode. Die Methode gibt nicht `null` zurück, und die <xref:System.Xml.Serialization.XmlSchemaProviderAttribute.IsAny%2A>-Eigenschaft des Attributs wird auf ihrem Standardwert `false` belassen. Dies ist die häufigste Verwendung von `IXmlSerializable`-Typen.

- Elementtypen werden verwendet, wenn ein `IXmlSerializable`-Typ seinen eigenen Stammelementnamen kontrollieren muss. Um einen Typ als Elementtyp zu kennzeichnen, legen Sie entweder die <xref:System.Xml.Serialization.XmlSchemaProviderAttribute.IsAny%2A>-Eigenschaft des <xref:System.Xml.Serialization.XmlSchemaProviderAttribute>-Attributs auf `true` fest, oder geben Sie über die Schemaanbietermethode `null` zurück. Die Verwendung einer Schemaanbietermethode ist für Elementtypen optional. Sie können unter `null` anstatt des Methodennamens auch `XmlSchemaProviderAttribute` angeben. Wenn `IsAny` jedoch `true` ist und eine Schemaanbietermethode angegeben ist, muss die Methode `null` zurückgeben.

- Bei älteren <xref:System.Data.DataSet>-Typen handelt es sich um `IXmlSerializable`-Typen, die nicht mit dem `XmlSchemaProviderAttribute`-Attribut gekennzeichnet sind. Stattdessen verwenden sie zur Schemagenerierung die <xref:System.Xml.Serialization.IXmlSerializable.GetSchema%2A>-Methode. Dieses Muster wird für den `DataSet`-Typ und seine von ihm abgeleiteten typisierten Dataset-Klassen in älteren Versionen von .NET Framework verwendet. Es ist jedoch veraltet und wird nur aus Legacygründen noch unterstützt. Verlassen Sie sich nicht auf dieses Muster, und wenden Sie immer das `XmlSchemaProviderAttribute` auf Ihre `IXmlSerializable`-Typen an.

### <a name="ixmlserializable-content-types"></a>IXmlSerializable-Inhaltstypen

Wenn Sie einen Datenmember eines Typs serialisieren, der `IXmlSerializable` implementiert und ein wie zuvor definierter Inhaltstyp ist, schreibt das Serialisierungsprogramm das Wrapperelement für den Datenmember und übergibt die Steuerung an die <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>-Methode. Die <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>-Implementierung kann beliebige XML-Daten schreiben, auch zum Hinzufügen der Attribute zum Wrapperelement. Nachdem `WriteXml` abgeschlossen ist, schließt das Serialisierungsprogramm das Element.

Wenn Sie einen Datenmember eines Typs deserialisieren, der `IXmlSerializable` implementiert und ein wie zuvor definierter Inhaltstyp ist, ordnet das Deserialisierungsprogramm den XML-Reader im Wrapperelement für den Datenmember an und übergibt die Steuerung an die <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A>-Methode. Die Methode muss das ganze Element lesen, einschließlich des Start- und Endtags. Stellen Sie sicher, dass der `ReadXml`-Code auch den Fall verarbeitet, in dem das Element leer ist. Außerdem sollte sich Ihre `ReadXml`-Implementierung nicht darauf verlassen, dass das Wrapperelement einen bestimmten Namen aufweist. Der Name wird vom Serialisierungsprogramm ausgewählt und kann variieren.

Es ist zulässig, `IXmlSerializable`-Inhaltstypen polymorph zuzuweisen, zum Beispiel zu Datenmembern vom Typ <xref:System.Object>. Es ist auch zulässig, dass die Typinstanzen NULL sind. Außerdem ist es möglich, `IXmlSerializable`-Typen bei aktivierter Objektdiagrammbeibehaltung und mit <xref:System.Runtime.Serialization.NetDataContractSerializer> zu verwenden. Alle diese Features erfordern, dass das WCF-Serialisierungsprogramm bestimmte Attribute in das Wrapper Element ("Nil" und "Type" im XML-Schema Instanz-Namespace und "ID", "ref", "Type" und "Assembly" in einem WCF-spezifischen Namespace anfügt).

#### <a name="attributes-to-ignore-when-implementing-readxml"></a>Bei der Implementierung von ReadXml zu ignorierende Attribute

Bevor die Steuerung an Ihren `ReadXml`-Code übergeben wird, untersucht das Deserialisierungsprogramm das XML-Element, erkennt diese speziellen XML-Attribute und führt die erforderlichen Aktionen aus. Wenn "nil" zum Beispiel `true` ist, wird ein Nullwert deserialisiert, und `ReadXml` wird nicht aufgerufen. Falls Polymorphie erkannt wird, wird der Inhalt des Elements deserialisiert, als ob es sich um einen anderen Typ handeln würde. Die `ReadXml`-Implementierung des polymorph zugewiesenen Typs wird aufgerufen. Eine `ReadXml`-Implementierung sollte diese speziellen Attribute auf jeden Fall ignorieren, da sie vom Deserialisierungsprogramm verarbeitet werden.

### <a name="schema-considerations-for-ixmlserializable-content-types"></a>Schemaüberlegungen für IXmlSerializable-Inhaltstypen

Beim Exportieren eines Schemas und eines `IXmlSerializable`-Inhaltstyp wird die Schemaanbietermethode aufgerufen. Ein <xref:System.Xml.Schema.XmlSchemaSet> wird an die Schemaanbietermethode übergeben. Die Methode kann dem Schemasatz gültige Schemas hinzufügen. Der Schemasatz enthält das Schema, das zum Zeitpunkt des Schemaexports bereits bekannt ist. Wenn die Schemaanbietermethode dem Schemasatz ein Element hinzufügen muss, muss sie ermitteln, ob ein <xref:System.Xml.Schema.XmlSchema> mit dem geeigneten Namespace im Satz bereits vorhanden ist. Falls dies der Fall ist, muss die Schemaanbietermethode das neue Element dem vorhandenen `XmlSchema` hinzufügen. Andernfalls muss sie eine neue `XmlSchema`-Instanz erstellen. Dies ist wichtig, wenn Arrays mit `IXmlSerializable`-Typen verwendet werden. Wenn Sie zum Beispiel über einen `IXmlSerializable`-Typ verfügen, der als Typ "A" in Namespace "B" exportiert wird, ist es möglich, dass der Schemasatz beim Aufrufen der Schemaanbietermethode das Schema "B" bereits enthält, um den Typ "ArrayOfA" aufzunehmen.

Zusätzlich zum Hinzufügen von Typen zum <xref:System.Xml.Schema.XmlSchemaSet> muss die Schemaanbietermethode für Inhaltstypen einen anderen Wert als NULL zurückgeben. Sie kann ein <xref:System.Xml.XmlQualifiedName>-Element zurückgeben, das den Namen des Schematyps angibt, der für den jeweiligen `IXmlSerializable`-Typ verwendet wird. Dieser qualifizierte Name dient auch als Datenvertragsname und Namespace für den Typ. Es ist zulässig, einen Typ zurückzugeben, der nicht im Schemasatz vorhanden ist, wenn dies direkt nach der Rückgabe der Schemaanbietermethode erfolgt. Es wird jedoch vorausgesetzt, dass der Typ nach dem Export aller verwandten Typen (die <xref:System.Runtime.Serialization.XsdDataContractExporter.Export%2A>-Methode wird für alle relevanten Typen von <xref:System.Runtime.Serialization.XsdDataContractExporter> aufgerufen, und es wird auf die <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas%2A>-Eigenschaft zugegriffen) im Schemasatz vorhanden ist. Das Zugreifen auf die `Schemas`-Eigenschaft, bevor alle relevanten `Export`-Aufrufe durchgeführt wurden, kann zu einer <xref:System.Xml.Schema.XmlSchemaException> führen. Weitere Informationen zum Exportprozess finden Sie unter [Exportieren von Schemas aus Klassen](exporting-schemas-from-classes.md).

Die Schemaanbietermethode kann auch den zu verwendenden <xref:System.Xml.Schema.XmlSchemaType> zurückgeben. Der Typ kann anonym oder nicht anonym sein. Wenn er anonym ist, wird das Schema für den `IXmlSerializable`-Typ jeweils als anonymer Typ exportiert, wenn der `IXmlSerializable`-Typ als Datenmember verwendet wird. Der `IXmlSerializable`-Typ verfügt trotzdem noch über einen Datenvertragsnamen und einen Namespace. (Dies wird in [Daten Vertrags Namen](data-contract-names.md) beschrieben, mit der Ausnahme, dass das- <xref:System.Runtime.Serialization.DataContractAttribute> Attribut nicht zum Anpassen des Namens verwendet werden kann.) Wenn Sie nicht anonym ist, muss es sich um einen der Typen im Handeln `XmlSchemaSet` . Dies entspricht dem Zurückgeben von `XmlQualifiedName` für den Typ.

Zusätzlich wird für den Typ eine globale Elementdeklaration exportiert. Wenn auf den Typ nicht das <xref:System.Xml.Serialization.XmlRootAttribute>-Attribut angewendet wurde, weist das Element denselben Namen und Namespace wie der Datenvertrag auf, und seine nillable-Eigenschaft ist `true`. Die einzige Ausnahme ist der Schema Namespace ( `http://www.w3.org/2001/XMLSchema` ) – Wenn sich der Datenvertrag des Typs in diesem Namespace befindet, befindet sich das entsprechende globale Element im leeren Namespace, da es unzulässig ist, dem Schema Namespace neue Elemente hinzuzufügen. Wenn auf den Typ das `XmlRootAttribute`-Attribut angewendet wurde, wird die globale Elementdeklaration exportiert, indem Folgendes verwendet wird: die Eigenschaften <xref:System.Xml.Serialization.XmlRootAttribute.ElementName%2A>, <xref:System.Xml.Serialization.XmlRootAttribute.Namespace%2A> und <xref:System.Xml.Serialization.XmlRootAttribute.IsNullable%2A>. Die bei angewendetem `XmlRootAttribute` geltenden Standardeinstellungen sind der Datenvertragsname, ein leerer Namespace und der Wert `true` für "nillable".

Die gleichen Regeln für die globale Elementdeklaration gelten für Legacy-Datasettypen. Beachten Sie, dass das `XmlRootAttribute` keine globalen Elementdeklarationen überschreiben kann, die mithilfe von benutzerdefiniertem Code hinzugefügt wurden. Diese können mithilfe der Schemaanbietermethode dem `XmlSchemaSet` oder über `GetSchema` für Legacy-Datasettypen hinzugefügt worden sein.

### <a name="ixmlserializable-element-types"></a>IXmlSerializable-Elementtypen

Für `IXmlSerializable`-Elementtypen ist entweder die `IsAny`-Eigenschaft auf `true` festgelegt, oder ihre Schemaanbietermethode gibt `null` zurück.

Das Serialisieren und Deserialisieren eines Elementtyps ähnelt stark dem Serialisieren und Deserialisieren eines Inhaltstyps. Es gibt jedoch einige wichtige Unterschiede:

- Von der `WriteXml`-Implementierung wird erwartet, dass sie genau ein Element schreibt (das natürlich mehrere untergeordnete Elemente enthalten kann). Sie sollte keine Attribute außerhalb dieses einzelnen Elements, mehrerer gleichgeordneter Elemente oder gemischten Inhalts schreiben. Das Element ist ggf. leer.

- Die `ReadXml`-Implementierung sollte das Wrapperelement nicht lesen. Es wird erwartet, dass sie das einzelne Element liest, das von `WriteXml` erzeugt wird.

- Wenn das Serialisierungsprogramm regelmäßig einen Elementtyp serialisiert (zum Beispiel als Datenmember in einem Datenvertrag), gibt das Serialisierungsprogramm ein Wrapperelement aus, bevor `WriteXml` aufgerufen wird. Dies entspricht der Vorgehensweise bei Inhaltstypen. Bei der Serialisierung eines Elementtyps auf der obersten Ebene gibt das Serialisierungsprogramm normalerweise jedoch kein Wrapperelement für das Element aus, das `WriteXml` schreibt. Dies ist nur der Fall, wenn beim Erstellen des Serialisierungsprogramms in den Konstruktoren `DataContractSerializer` oder `NetDataContractSerializer` explizit ein Stammname und ein Namespace angegeben werden. Weitere Informationen finden Sie unter [Serialisierung und Deserialisierung](serialization-and-deserialization.md).

- Beim Serialisieren eines Elementtyps auf der obersten Ebene, ohne zur Entwurfszeit den Stammnamen und einen Namespace anzugeben, führen <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteStartObject%2A> und <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteEndObject%2A> im Wesentlichen keine Aktionen aus, und <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteObjectContent%2A> ruft einfach `WriteXml` auf. In diesem Modus kann das Objekt, das serialisiert wird, nicht `null` sein und nicht polymorph zugewiesen werden. Außerdem kann die Objektdiagrammbeibehaltung nicht aktiviert und `NetDataContractSerializer` kann nicht verwendet werden.

- Beim Deserialisieren eines Elementtyps auf der obersten Ebene, ohne zur Entwurfszeit den Stammnamen und den Namespace anzugeben, gibt <xref:System.Runtime.Serialization.XmlObjectSerializer.IsStartObject%2A> den Wert `true` zurück, wenn der Anfang eines beliebigen Elements gefunden werden kann. <xref:System.Runtime.Serialization.XmlObjectSerializer.ReadObject%2A> mit auf `verifyObjectName` festgelegtem `true`-Parameter verhält sich genau so wie `IsStartObject`, bevor das Objekt gelesen wird. `ReadObject` übergibt das Steuerelement dann an die `ReadXml`-Methode.

Das Schema, das für die Elementtypen exportiert wird, entspricht dem Schema für den `XmlElement`-Typ, wie in einem Abschnitt weiter oben beschrieben. Es gilt jedoch die Ausnahme, dass die Schemaanbietermethode wie bei Inhaltstypen dem <xref:System.Xml.Schema.XmlSchemaSet> zusätzliche Schemas hinzufügen kann. Das Verwenden des `XmlRootAttribute`-Attributs mit Elementtypen ist nicht zulässig, und globale Elementdeklarationen werden für diese Typen nicht ausgegeben.

### <a name="differences-from-the-xmlserializer"></a>Unterschiede zu XmlSerializer

Die `IXmlSerializable`-Schnittstelle und das `XmlSchemaProviderAttribute`- und `XmlRootAttribute`-Attribut werden vom <xref:System.Xml.Serialization.XmlSerializer> auch verstanden. Aber es gibt einige Unterschiede dabei, wie diese Elemente im Datenvertragsmodell behandelt werden. Die wichtigsten Unterschiede werden im Folgenden zusammengefasst:

- Die Schemaanbietermethode muss öffentlich sein, um im `XmlSerializer` verwendet werden zu können. Sie muss jedoch nicht öffentlich sein, um im Datenvertragsmodell verwendet werden zu können.

- Die Schemaanbietermethode wird aufgerufen, wenn für `IsAny` im Datenvertragsmodell `true` gilt, jedoch nicht für den `XmlSerializer`.

- Wenn das `XmlRootAttribute`-Attribut für Inhalts- oder Legacy-Datasettypen nicht vorhanden ist, exportiert der `XmlSerializer` eine globale Elementdeklaration in den leeren Namespace. Im Datenvertragsmodell ist der verwendete Namespace normalerweise der Datenvertragsnamespace, wie bereits beschrieben.

Beachten Sie diese Unterschiede, wenn Sie Typen erstellen, die mit beiden Serialisierungstechnologien verwendet werden.

### <a name="importing-ixmlserializable-schema"></a>Importieren von IXmlSerializable-Schemas

Beim Importieren eines Schemas, das aus `IXmlSerializable`-Typen generiert wurde, gibt es verschiedene Möglichkeiten:

- Das generierte Schema kann ein gültiges Daten Vertrags Schema sein, wie unter [Daten Vertrags Schema-Referenz](data-contract-schema-reference.md)beschrieben. In diesem Fall kann das Schema auf die übliche Weise importiert werden, und es werden normale Datenvertragstypen generiert.

- Bei dem generierten Schema kann es sich auch um ein nicht gültiges Datenvertragsschema handeln. Ihre Schemaanbietermethode kann zum Beispiel Schemas mit XML-Attributen generieren, die im Datenvertragsmodell nicht unterstützt werden. In diesem Fall können Sie das Schema als `IXmlSerializable`-Typen importieren. Dieser Import Modus ist standardmäßig nicht aktiviert, kann jedoch problemlos aktiviert werden – z. b. mit dem `/importXmlTypes` Befehls Zeilenschalter zum [Service Model Metadata Utility-Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md). Dies wird im Abschnitt [Importieren von Schemas zum Generieren von Klassen](importing-schema-to-generate-classes.md)ausführlich beschrieben. Beachten Sie, dass Sie für die Typinstanzen direkt mit den XML-Daten arbeiten müssen. Sie können auch erwägen, eine andere Serialisierungstechnologie zu verwenden, die einen größeren Schemabereich unterstützt. Weitere Informationen finden Sie im Thema zur Verwendung von `XmlSerializer`.

- Es ist ratsam, Ihre vorhandenen `IXmlSerializable`-Typen im Proxy wiederzuverwenden, anstatt neue zu generieren. In diesem Fall können Sie die Funktion mit den referenzierten Typen verwenden, die im Thema zum Importieren von Schemas zum Generieren von Typen beschrieben ist, um den wiederzuverwendenden Typ anzugeben. Dies entspricht dem Verwenden des Schalters `/reference` für „svcutil.exe“. Damit wird die Assembly angegeben, die die wiederzuverwendenden Typen enthält.

### <a name="xmlserializer-legacy-behavior"></a>XmlSerializer-Legacyverhalten

In .NET Framework 4.0 und früher wurden von XmlSerializer temporäre Serialisierungsassemblys generiert, indem C#-Code in eine Datei geschrieben wurde. Die Datei wurde anschließend in eine Assembly kompiliert.  Dieses Verhalten hatte einige unerwünschte Folgen, z. B. das Verzögern der Startzeit für die Serialisierung. In .NET Framework 4.5 wurde das Verhalten geändert, um die Assemblys zu generieren, ohne den Compiler verwenden zu müssen. Einige Entwickler möchten den generierten C#-Code jedoch anzeigen. Sie können mit der folgenden Konfiguration festlegen, dass dieses Legacyverhalten verwendet wird:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.xml.serialization>
    <xmlSerializer tempFilesLocation='e:\temp\XmlSerializerBug' useLegacySerializerGeneration="true" />
  </system.xml.serialization>
  <system.diagnostics>
    <switches>
      <add name="XmlSerialization.Compilation" value="1" />
    </switches>
  </system.diagnostics>
</configuration>
```

Wenn Kompatibilitätsprobleme auftreten, z. b. Wenn `XmlSerializer` eine abgeleitete Klasse nicht mit einer nicht öffentlichen neuen außer Kraft Setzung serialisiert werden kann, können Sie auf das Legacy Verhalten zurück wechseln, `XMLSerializer` indem Sie die folgende Konfiguration verwenden:

```xml
<configuration>
  <appSettings>
    <add key="System:Xml:Serialization:UseLegacySerializerGeneration" value="true" />
  </appSettings>
</configuration>
```

Als Alternative zu der oben beschriebenen Konfiguration können Sie die folgende Konfiguration auf einem Computer verwenden, auf dem .NET Framework 4,5 oder eine neuere Version ausgeführt wird:

```xml
<configuration>
  <system.xml.serialization>
    <xmlSerializer useLegacySerializerGeneration="true"/>
  </system.xml.serialization>
</configuration>
```

> [!NOTE]
> Der `<xmlSerializer useLegacySerializerGeneration="true"/>` Switch funktioniert nur auf einem Computer, auf dem .NET Framework 4,5 oder eine neuere Version ausgeführt wird. Der obige `appSettings` Ansatz funktioniert für alle .NET Framework Versionen.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.DataContractFormatAttribute>
- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Xml.Serialization.XmlSerializer>
- <xref:System.ServiceModel.MessageHeaderArrayAttribute>
- [Angeben von Datenübertragung in Dienstverträgen](specifying-data-transfer-in-service-contracts.md)
- [Verwenden von Datenverträgen](using-data-contracts.md)
- [Vorgehensweise: Verbessern der Startzeit von WCF-Clientanwendungen mit dem XmlSerializer](startup-time-of-wcf-client-applications-using-the-xmlserializer.md)
