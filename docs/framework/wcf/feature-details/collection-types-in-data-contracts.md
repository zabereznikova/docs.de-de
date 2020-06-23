---
title: Sammlungstypen in Datenverträgen
description: Erfahren Sie, wie das Daten Vertragsmodell Auflistungen in der .NET Framework behandelt und wie WCF die Datenserialisierung für Sammlungs Typen unterstützt.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- collection types [WCF], data contracts
- data contracts [WCF], collection types
- collection types [WCF]
ms.assetid: 9b45b28e-0a82-4ea3-8c33-ec0094aff9d5
ms.openlocfilehash: 83acf1f74bf3cb117f3f94743eda32d3f2cc4b82
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245179"
---
# <a name="collection-types-in-data-contracts"></a>Sammlungstypen in Datenverträgen

Eine *Sammlung* ist eine Liste von Elementen eines bestimmten Typs. In der .NET Framework können solche Listen mithilfe von Arrays oder einer Vielzahl anderer Typen (generische Liste, generisch <xref:System.ComponentModel.BindingList%601> , <xref:System.Collections.Specialized.StringCollection> oder) dargestellt werden <xref:System.Collections.ArrayList> . Eine Sammlung kann z. B. eine Liste von Adressen für einen bestimmten Kunden enthalten. Solche Sammlungen werden – unabhängig von ihrem tatsächlichen Typ – als *Listensammlungen*bezeichnet.

Es gibt eine spezielle Sammlungsform, die eine Zuordnung zwischen einem Element (dem "Schlüssel") und einem anderen Element (dem "Wert") darstellt. In der .NET Framework werden diese durch Typen wie <xref:System.Collections.Hashtable> und das generische Wörterbuch dargestellt. Eine Zuordnungssammlung kann z. B. eine Stadt ("Schlüssel") der zugehörigen Bevölkerung ("Wert") zuordnen. Solche Sammlungen werden – unabhängig von ihrem tatsächlichen Typ – als *Wörterbuchsammlungen*bezeichnet.

Sammlungen werden im Datenvertragsmodell besonders behandelt.

Typen, die die <xref:System.Collections.IEnumerable> -Schnittstelle einschließlich Arrays und generischen Sammlungen implementieren, werden als Sammlungen erkannt. Davon sind die Typen, die die Schnittstellen für das <xref:System.Collections.IDictionary> oder das generische <xref:System.Collections.Generic.IDictionary%602> implementieren, Wörterbuchsammlungen. Alle anderen sind Listensammlungen.

Weitere Anforderungen an Auflistungs Typen, z. b. die Verwendung einer Methode mit dem Namen `Add` und eines Parameter losen Konstruktors, werden in den folgenden Abschnitten ausführlich erläutert. Dies stellt sicher, dass Sammlungstypen sowohl serialisiert als auch deserialisiert sein können. Dies bedeutet, dass einige Sammlungen nicht direkt unterstützt werden, z. b. die generische <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> (da Sie keinen Parameter losen Konstruktor aufweist). Informationen zum Umgehen dieser Einschränkungen finden Sie im Abschnitt "Verwenden von Sammlungsschnittstellentypen und schreibgeschützten Sammlungen" weiter unten in diesem Thema.

Die in Sammlungen enthaltenen Typen müssen Datenvertragstypen oder anderweitig serialisierbar sein. Weitere Informationen finden Sie [unter vom Datenvertragsserialisierer unterstützte Typen](types-supported-by-the-data-contract-serializer.md).

Weitere Informationen dazu, was und was nicht als gültige Sammlung betrachtet wird, sowie darüber, wie Sammlungen serialisiert werden, finden Sie im Abschnitt Informationen zum Serialisieren von Sammlungen im Abschnitt "Erweiterte Sammlungs Regeln" dieses Themas.

## <a name="interchangeable-collections"></a>Austauschbare Sammlungen

Bei allen Listensammlungen des gleichen Typs wird davon ausgegangen, dass sie den gleichen Datenvertrag haben (es sei denn, sie wurden mit dem <xref:System.Runtime.Serialization.CollectionDataContractAttribute> -Attribut individuell angepasst, wie weiter unten in diesem Thema beschrieben). Daher stimmen beispielsweise die folgenden Datenverträge überein:

[!code-csharp[c_collection_types_in_data_contracts#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_collection_types_in_data_contracts/cs/program.cs#0)]
[!code-vb[c_collection_types_in_data_contracts#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_collection_types_in_data_contracts/vb/program.vb#0)]

Beide Datenverträge führen zu XML-Code, ähnlich dem folgenden Code:

```xml
<PurchaseOrder>
    <customerName>...</customerName>
    <items>
        <Item>...</Item>
        <Item>...</Item>
        <Item>...</Item>
        ...
    </items>
    <comments>
        <string>...</string>
        <string>...</string>
        <string>...</string>
        ...
    </comments>
</PurchaseOrder>
```

Die Austauschbarkeit von Sammlungen ermöglicht Ihnen beispielsweise die Verwendung eines für die Leistung auf dem Server optimierten Sammlungstyps sowie eines Sammlungstyps, der für die Bindung an Benutzerschnittstellenkomponenten auf dem Client entwickelt wurde.

Ähnlich wie bei den Listensammlungen haben alle Wörterbuchsammlungen, die die gleichen Schlüssel- und Werttypen aufweisen, den gleichen Datenvertrag (es sei denn, sie wurden mit dem <xref:System.Runtime.Serialization.CollectionDataContractAttribute> -Attribut individuell angepasst).

Nur der Datenvertragstyp ist, was die Sammlungsäquivalenz betrifft, wichtig, nicht die .NET-Typen, d. h. eine Sammlung vom Typ1 gilt als äquivalent zu einer Sammlung vom Typ2, wenn Typ1 und Typ2 die gleichen Datenverträge aufweisen.

Bei nicht generischen Sammlungen wird davon ausgegangen, dass sie den gleichen Datenvertrag wie generische Sammlungen des Typs `Object`aufweisen. (Beispielsweise sind die Datenverträge für die <xref:System.Collections.ArrayList> und die generische <xref:System.Collections.Generic.List%601> von `Object` gleich.)

## <a name="using-collection-interface-types-and-read-only-collections"></a>Verwenden von Sammlungsschnittstellentypen und schreibgeschützten Sammlungen

Bei Sammlungsschnittstellentypen (<xref:System.Collections.IEnumerable>, <xref:System.Collections.IDictionary>, generische <xref:System.Collections.Generic.IDictionary%602>oder von diesen Schnittstellen abgeleiteten Schnittstellen) wird ebenfalls davon ausgegangen, dass sie die gleichen Sammlungsdatenverträge aufweisen wie die tatsächlichen Sammlungstypen. Daher ist es möglich, den serialisierten Typ als einen Sammlungsschnittstellentyp zu deklarieren. Die Ergebnisse sind die gleichen wie bei der Verwendung eines tatsächlichen Sammlungstyps. So stimmen beispielsweise die folgenden Datenverträge überein:

[!code-csharp[c_collection_types_in_data_contracts#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_collection_types_in_data_contracts/cs/program.cs#1)]
[!code-vb[c_collection_types_in_data_contracts#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_collection_types_in_data_contracts/vb/program.vb#1)]

Wenn der deklarierte Typ eine Schnittstelle ist, kann der derzeit verwendete Instanzentyp während der Serialisierung ein beliebiger Typ sein, der diese Schnittstelle implementiert. Die zuvor beschriebenen Einschränkungen (mit einem Parameter losen Konstruktor und einer- `Add` Methode) gelten nicht. Beispielsweise können Sie Adressen in Customer2 auf eine Instanz einer generischen <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> von "Adress" einstellen, auch wenn es Ihnen nicht möglich ist, einen Datenmember des Typs "Generische <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>" direkt zu deklarieren.

Wenn der deklarierte Typ eine Schnittstelle ist, wählt die Serialisierungs-Engine während der Deserialisierung einen Typ, der die deklarierte Schnittstelle implementiert, und der Typ wird instanziiert. Der Mechanismus der bekannten Typen (beschrieben in " [Data Contract Known Types](data-contract-known-types.md)") hat hier keine Auswirkung. die Auswahl des Typs ist in WCF integriert.

## <a name="customizing-collection-types"></a>Anpassen von Sammlungstypen

Sie können Sammlungstypen anpassen, indem Sie das <xref:System.Runtime.Serialization.CollectionDataContractAttribute> -Attribut verwenden, das auf verschiedene Weise genutzt werden kann.

Beachten Sie, dass das Anpassen von Sammlungstypen die Austauschbarkeit von Sammlungen beeinträchtigt. Daher wird empfohlen, das Anwenden dieses Attributs wenn möglich zu vermeiden. Weitere Informationen zu diesem Problem finden Sie im Abschnitt "Erweiterte Sammlungs Regeln" weiter unten in diesem Thema.

### <a name="collection-data-contract-naming"></a>Benennen von Sammlungsdatenverträgen

Die Regeln für das Benennen von Sammlungstypen ähneln den Regeln für das Benennen von Datenvertragstypen, wie unter [Data Contract Names](data-contract-names.md)beschrieben. Es bestehen jedoch einige wichtige Unterschiede:

- Zum Anpassen des Namens wird das <xref:System.Runtime.Serialization.CollectionDataContractAttribute> -Attribut verwendet und nicht das <xref:System.Runtime.Serialization.DataContractAttribute> -Attribut. Das <xref:System.Runtime.Serialization.CollectionDataContractAttribute> -Attribut weist außerdem `Name` - und `Namespace` -Eigenschaften auf.

- Wenn das <xref:System.Runtime.Serialization.CollectionDataContractAttribute> -Attribut nicht angewendet wird, hängen der Standardname und der Standardnamespace für Sammlungstypen von den Namen und Namespaces der Typen ab, die in der Sammlung enthalten sind. Sie werden nicht vom Namen und dem Namespace des Sammlungstyps selbst beeinflusst. Ein Beispiel finden Sie in den folgenden Typen:

  ```csharp
  public CustomerList1 : Collection<string> {}
  public StringList1 : Collection<string> {}
  ```

Die Datenvertragsnamen beider Typen lauten "ArrayOfstring" (und nicht "CustomerList1" oder "StringList1"), d. h., dass sich durch die Serialisierung eines dieser Typen auf der Stammebene XML-Code ähnlich dem folgenden Code ergibt:

```xml
<ArrayOfstring>
    <string>...</string>
    <string>...</string>
    <string>...</string>
    ...
</ArrayOfstring>
```

Diese Benennungsregel wurde gewählt, um sicherzustellen, dass sämtliche nicht benutzerdefinierten Typen, die eine Liste von Zeichenfolgen darstellen, den gleichen Datenvertrag und die gleiche XML-Darstellung haben. Dies macht Sammlungsaustauschbarkeit möglich. In diesem Beispiel sind "CustomerList1" und "StringList1" vollständig austauschbar.

Wenn jedoch das <xref:System.Runtime.Serialization.CollectionDataContractAttribute> -Attribut angewendet wird, wird die Sammlung zu einem benutzerdefinierten Sammlungsdatenvertrag, auch wenn keine Eigenschaften für das Attribut festgelegt wurden. Der Name und der Namespace des Sammlungsdatenvertrags hängen dann vom Sammlungstyp selbst ab. Ein Beispiel finden Sie im folgenden Typ:

[!code-csharp[c_collection_types_in_data_contracts#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_collection_types_in_data_contracts/cs/program.cs#2)]
[!code-vb[c_collection_types_in_data_contracts#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_collection_types_in_data_contracts/vb/program.vb#2)]

Nach der Serialisierung ähneln die resultierenden XML-Daten Folgendem:

```xml
<CustomerList2>
    <string>...</string>
    <string>...</string>
    <string>...</string>
    ...
</CustomerList2>
```

Beachten Sie, dass dies nicht mehr der XML-Darstellung der nicht benutzerdefinierten Typen entspricht.

- Sie können die `Name` - und die `Namespace` -Eigenschaft verwenden, um die Benennung noch weiter anzupassen. Siehe folgende Klasse.

  [!code-csharp[c_collection_types_in_data_contracts#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_collection_types_in_data_contracts/cs/program.cs#3)]
  [!code-vb[c_collection_types_in_data_contracts#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_collection_types_in_data_contracts/vb/program.vb#3)]

Die resultierenden XML-Daten ähneln Folgendem:

```xml
<cust_list>
    <string>...</string>
    <string>...</string>
    <string>...</string>
    ...
</cust_list>
```

Weitere Informationen finden Sie im Abschnitt "Erweiterte Sammlungs Regeln" weiter unten in diesem Thema.

### <a name="customizing-the-repeating-element-name-in-list-collections"></a>Anpassen des sich wiederholenden Elementnamens in Listensammlungen

Listensammlungen enthalten sich wiederholende Einträge. In der Regel wird jeder sich wiederholende Eintrag als Element dargestellt, das gemäß dem Datenvertragsnamen des in der Sammlung enthaltenen Typs benannt ist.

In den `CustomerList` -Beispielen enthielten die Sammlungen Zeichenfolgen. Der Daten Vertrags Name für den primitiven Typ der Zeichenfolge ist "String", sodass das sich wiederholende Element " \<string> " lautet.

Wenn jedoch die <xref:System.Runtime.Serialization.CollectionDataContractAttribute.ItemName%2A> -Eigenschaft auf dem <xref:System.Runtime.Serialization.CollectionDataContractAttribute> -Attribut verwendet wird, kann dieser sich wiederholende Elementname angepasst werden. Ein Beispiel finden Sie im folgenden Typ:

[!code-csharp[c_collection_types_in_data_contracts#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_collection_types_in_data_contracts/cs/program.cs#4)]
[!code-vb[c_collection_types_in_data_contracts#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_collection_types_in_data_contracts/vb/program.vb#4)]

Die resultierenden XML-Daten ähneln Folgendem:

```xml
<CustomerList4>
    <customer>...</customer>
    <customer>...</customer>
    <customer>...</customer>
    ...
</CustomerList4>
```

Der Namespace des sich wiederholenden Elements entspricht stets dem Namespace des Sammlungsdatenvertrags, der mithilfe der `Namespace` -Eigenschaft angepasst werden kann, wie zuvor beschrieben.

### <a name="customizing-dictionary-collections"></a>Anpassen von Wörterbuchsammlungen

Wörterbuchsammlungen sind im Grunde Listen von Einträgen, bei denen jeder Eintrag über einen Schlüssel gefolgt von einem Wert verfügt. Genau wie bei normalen Listen können Sie den dem sich wiederholenden Element entsprechenden Elementnamen mit der <xref:System.Runtime.Serialization.CollectionDataContractAttribute.ItemName%2A> -Eigenschaft ändern.

Darüber hinaus können Sie die Elementnamen ändern, die für den Schlüssel und den Wert stehen, indem Sie die <xref:System.Runtime.Serialization.CollectionDataContractAttribute.KeyName%2A> - und die <xref:System.Runtime.Serialization.CollectionDataContractAttribute.ValueName%2A> -Eigenschaft verwenden. Die Namespaces für diese Elemente entsprechen dem Namespace des Sammlungsdatenvertrags.

Ein Beispiel finden Sie im folgenden Typ:

[!code-csharp[c_collection_types_in_data_contracts#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_collection_types_in_data_contracts/cs/program.cs#5)]
[!code-vb[c_collection_types_in_data_contracts#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_collection_types_in_data_contracts/vb/program.vb#5)]

Nach der Serialisierung ähneln die resultierenden XML-Daten Folgendem:

```xml
<CountriesOrRegionsWithCapitals>
    <entry>
        <countryorregion>USA</countryorregion>
        <capital>Washington</capital>
    </entry>
    <entry>
        <countryorregion>France</countryorregion>
        <capital>Paris</capital>
    </entry>
    ...
</CountriesOrRegionsWithCapitals>
```

Weitere Informationen zu Wörterbuch Sammlungen finden Sie weiter unten in diesem Thema im Abschnitt "Erweiterte Sammlungs Regeln".

## <a name="collections-and-known-types"></a>Sammlungen und bekannte Typen

Sie müssen Sammlungstypen nicht bekannten Typen hinzufügen, wenn sie polymorph anstelle von anderen Sammlungen oder Sammlungsschnittstellen verwendet werden. Wenn Sie beispielsweise einen Datenmember des Typs <xref:System.Collections.IEnumerable> deklarieren und dazu verwenden, eine Instanz von <xref:System.Collections.ArrayList>zu senden, müssen Sie <xref:System.Collections.ArrayList> nicht bekannten Typen hinzufügen.

Wenn Sie anstelle von Typen polymorphe Sammlungen verwenden, bei denen es sich nicht um Sammlungstypen handelt, müssen sie bekannten Typen hinzugefügt werden. Wenn Sie beispielsweise einen Datenmember des Typs `Object` deklarieren und dazu verwenden, eine Instanz von <xref:System.Collections.ArrayList>zu senden, müssen Sie <xref:System.Collections.ArrayList> bekannten Typen hinzufügen.

Dies ermöglicht es Ihnen nicht, eine äquivalente Sammlung polymorph zu serialisieren. Wenn Sie beispielsweise <xref:System.Collections.ArrayList> der Liste bekannter Typen im vorherigen Beispiel hinzufügen, ist es Ihnen nicht möglich, die `Array of Object` -Klasse zuzuweisen, obwohl sie den gleichen Datenvertrag aufweist. Dieses Verhalten unterscheidet sich nicht vom regulären Verhalten bekannter Typen bei der Serialisierung für Typen, bei denen es sich nicht um Sammlungstypen handelt. Es ist jedoch besonders wichtig, sich im Falle von Sammlungen hierüber im Klaren zu sein, da Sammlungen sehr häufig äquivalent sind.

Während der Serialisierung kann lediglich ein Typ in einem bestimmten Bereich für einen bestimmten Datenvertrag bekannt sein, und äquivalente Sammlungen besitzen alle die gleichen Datenverträge. Das bedeutet, dass Sie im vorherigen Beispiel nicht beide Elemente ( <xref:System.Collections.ArrayList> und `Array of Object` ) bekannten Typen im gleichen Bereich hinzufügen können. Dies entspricht erneut dem Verhalten bekannter Typen für Typen, bei denen es sich nicht um Sammlungstypen handelt. Es ist jedoch besonders wichtig, sich im Falle von Sammlungen hierüber im Klaren zu sein.

Bekannte Typen sind möglicherweise auch für Inhalte von Sammlungen erforderlich. Wenn beispielsweise eine <xref:System.Collections.ArrayList> wirklich Instanzen eines `Type1` und eines `Type2`enthält, sollten beide Typen bekannten Typen hinzugefügt werden.

Im folgenden Beispiel wird ein ordnungsgemäß erstelltes Objektdiagramm mit Sammlungen und bekannten Typen dargestellt. (Das Beispiel ist frei erfunden, da Sie in einer echten Anwendung normalerweise die folgenden Datenmember nicht als `Object`definieren und daher auch keine Probleme mit bekannten Typen/Polymorphie auftreten würden.)

[!code-csharp[c_collection_types_in_data_contracts#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_collection_types_in_data_contracts/cs/program.cs#6)]
[!code-vb[c_collection_types_in_data_contracts#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_collection_types_in_data_contracts/vb/program.vb#6)]

Wenn der deklarierte Typ ein Sammlungstyp ist, wird der deklarierte Typ bei der Deserialisierung instanziiert, unabhängig vom Typ, der tatsächlich gesendet wurde. Wenn der deklarierte Typ eine Sammlungsschnittstelle ist, wählt das Deserialisierungsprogramm einen zu instanziierenden Typ aus, unabhängig von bekannten Typen.

Wenn der deklarierte Typ bei der Deserialisierung kein Sammlungstyp ist, jedoch ein Sammlungstyp gesendet wird, wird ein entsprechender Sammlungstyp aus der Liste der bekannten Typen ausgewählt. Es ist möglich, bei der Deserialisierung der Liste bekannter Typen Sammlungsschnittstellentypen hinzuzufügen. In diesem Fall wählt die Deserialisierungs-Engine erneut einen Typ aus, der instanziiert werden soll.

## <a name="collections-and-the-netdatacontractserializer-class"></a>Sammlungen und die NetDataContractSerializer-Klasse

Wenn die <xref:System.Runtime.Serialization.NetDataContractSerializer> -Klasse verwendet wird, verlieren nicht benutzerdefinierte Sammlungstypen (ohne das <xref:System.Runtime.Serialization.CollectionDataContractAttribute> -Attribut), bei denen es sich nicht um Arrays handelt, ihre spezielle Bedeutung.

Nicht benutzerdefinierte Sammlungstypen, die mit dem <xref:System.SerializableAttribute> -Attribut gekennzeichnet sind, können dennoch von der <xref:System.Runtime.Serialization.NetDataContractSerializer> -Klasse gemäß den Regeln für das <xref:System.SerializableAttribute> -Attribut oder die <xref:System.Runtime.Serialization.ISerializable> -Schnittstelle serialisiert werden.

Benutzerdefinierte Sammlungstypen, Sammlungsschnittstellen und Arrays werden weiterhin als Sammlungen behandelt, selbst wenn die <xref:System.Runtime.Serialization.NetDataContractSerializer> -Klasse verwendet wird.

## <a name="collections-and-schema"></a>Sammlungen und Schema

Alle äquivalenten Sammlungen verfügen über die gleiche Darstellung im XSD-Schema (XML Schema Definition Language). Daher erhalten Sie im generierten Clientcode normalerweise nicht den gleichen Sammlungstyp wie auf dem Server. Beispielsweise kann der Server einen Datenvertrag mit einer generischen <xref:System.Collections.Generic.List%601> für den Datenmember "Integer" verwenden, im generierten Clientcode kann der gleiche Datenmember jedoch ein Array von ganzen Zahlen werden.

Wörterbuch Sammlungen sind mit einer WCF-spezifischen Schema Anmerkung gekennzeichnet, die darauf hinweist, dass es sich um Wörterbücher handelt. Andernfalls können Sie nicht von einfachen Listen unterschieden werden, die Einträge mit einem Schlüssel und einem Wert enthalten. Eine genaue Beschreibung, wie Sammlungen in einem Datenvertragsschema dargestellt werden, finden Sie unter [Data Contract Schema Reference](data-contract-schema-reference.md).

Standardmäßig werden Typen nicht für nicht benutzerdefinierte Sammlungen in importiertem Code generiert. Datenmember von Listensammlungstypen werden als Arrays importiert, und Datenmember von Wörterbuchsammlungstypen werden als generisches Wörterbuch importiert.

Für benutzerdefinierte Sammlungen werden jedoch separate Typen generiert, die mit dem <xref:System.Runtime.Serialization.CollectionDataContractAttribute> -Attribut gekennzeichnet sind. (Ein benutzerdefinierter Sammlungstyp im Schema ist eine, die nicht den Standard Namespace, den Namen, den Namen des wiederholten Elements oder die Schlüssel-Wert-Elementnamen verwendet.) Bei diesen Typen handelt es sich um leere Typen, die von generisch <xref:System.Collections.Generic.List%601> für Listen Typen und generisches Wörterbuch für Wörterbuchtypen abgeleitet

Es können z. B. folgende Typen auf dem Server vorliegen:

[!code-csharp[c_collection_types_in_data_contracts#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_collection_types_in_data_contracts/cs/program.cs#7)]
[!code-vb[c_collection_types_in_data_contracts#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_collection_types_in_data_contracts/vb/program.vb#7)]

Wenn das Schema exportiert und anschließend wieder importiert wird, ähnelt der generierte Clientcode dem folgenden Code (statt Eigenschaften werden zur Erleichterung des Lesens Felder angezeigt).

[!code-csharp[c_collection_types_in_data_contracts#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_collection_types_in_data_contracts/cs/program.cs#8)]
[!code-vb[c_collection_types_in_data_contracts#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_collection_types_in_data_contracts/vb/program.vb#8)]

Möglicherweise möchten Sie andere Typen als die Standardtypen in generiertem Code verwenden. Es könnte z. B. sein, dass Sie die generische <xref:System.ComponentModel.BindingList%601> statt regulärer Arrays für Ihre Datenmember verwenden möchten, um sie leichter an Benutzerschnittstellenkomponenten binden zu können.

Übergeben Sie zum Auswählen der zu generierenden Sammlungstypen eine Liste der Sammlungstypen, die Sie verwenden möchten, in die <xref:System.Runtime.Serialization.ImportOptions.ReferencedCollectionTypes%2A> -Eigenschaft des <xref:System.Runtime.Serialization.ImportOptions> -Objekts, wenn Sie das Schema importieren. Diese Typen werden als *referenzierte Sammlungstypen*bezeichnet.

Wenn auf generische Typen verwiesen wird, müssen sie entweder vollständig offene oder vollständig geschlossene Generics sein.

> [!NOTE]
> Wenn Sie das Tool „Svcutil.exe“ verwenden, kann dieser Verweis über den **/collectionType** -Befehlszeilenschalter (Kurzform: **/ct**) erreicht werden. Denken Sie daran, dass Sie auch die Assembly für die referenzierten Sammlungstypen über den **/reference** -Schalter (Kurzform: **/r**) angeben müssen. Bei generischen Typen folgt auf den Namen des Typs ein Graviszeichen und die Anzahl der generischen Parameter. Das backanführungs \` Zeichen () muss nicht mit dem einfachen Anführungszeichen (') verwechselt werden. Sie können mehrere referenzierte Sammlungstypen angeben, indem Sie den **/collectionType** -Schalter mehrmals verwenden.

Beispielsweise, um zu bewirken, dass alle Listen als generische <xref:System.Collections.Generic.List%601>importiert werden.

```console
svcutil.exe MyService.wsdl MyServiceSchema.xsd /r:C:\full_path_to_system_dll\System.dll /ct:System.Collections.Generic.List`1
```

Beim Importieren einer beliebigen Sammlung wird die Liste der referenzierten Sammlungstypen gescannt, und die am besten passende Sammlung wird verwendet (sofern vorhanden) – entweder als Datenmembertyp (für nicht benutzerdefinierte Sammlungen) oder als Basistyp, von dem abgeleitet wird (für benutzerdefinierte Sammlungen). Wörterbücher werden nur Wörterbüchern gegenübergestellt, während Listen Listen gegenübergestellt werden.

Wenn Sie beispielsweise die generische <xref:System.ComponentModel.BindingList%601> und <xref:System.Collections.Hashtable> der Liste referenzierter Typen hinzufügen, ähnelt der generierte Clientcode für das vorangegangene Beispiel dem folgenden.

[!code-csharp[c_collection_types_in_data_contracts#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_collection_types_in_data_contracts/cs/program.cs#9)]
[!code-vb[c_collection_types_in_data_contracts#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_collection_types_in_data_contracts/vb/program.vb#9)]

Sie können Sammlungsschnittstellentypen als Teil Ihrer referenzierten Sammlungstypen angeben, jedoch können Sie keine ungültigen Sammlungstypen angeben (wie diejenigen ohne `Add` -Methode oder öffentlichen Konstruktor).

Ein geschlossener generischer Typ wird als beste Übereinstimmung betrachtet. (Nicht generische Typen werden als äquivalent zu geschlossenen Generics von `Object`betrachtet). Wenn beispielsweise die Typen "Generische <xref:System.Collections.Generic.List%601> von <xref:System.DateTime>", "Generische <xref:System.ComponentModel.BindingList%601> " (offener generischer Typ) und " <xref:System.Collections.ArrayList> " die referenzierten Sammlungstypen sind, wird Folgendes generiert:

[!code-csharp[c_collection_types_in_data_contracts#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_collection_types_in_data_contracts/cs/program.cs#10)]
[!code-vb[c_collection_types_in_data_contracts#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_collection_types_in_data_contracts/vb/program.vb#10)]

Für Listensammlungen werden nur die Fälle aus der folgenden Tabelle unterstützt:

|Referenzierter Typ|Vom referenzierten Typ implementierte Schnittstelle|Beispiel|Typ behandelt als:|
|---------------------|----------------------------------------------|-------------|----------------------|
|Nicht generisch oder geschlossen generisch (beliebige Anzahl von Parametern)|Nicht generisch|`MyType : IList`<br /><br /> oder<br /><br /> `MyType<T> : IList`<br /><br /> , wobei T= `int`|Geschlossen generisch von `Object` (z. B. `IList<object>`)|
|Nicht generisch oder geschlossen generisch (beliebige Anzahl von Parametern, die nicht notwendigerweise mit dem Sammlungstyp übereinstimmen)|Geschlossen generisch|`MyType : IList<string>`<br /><br /> oder<br /><br /> `MyType<T> : IList<string>` , wobei T=`int`|Geschlossen generisch (z. B. `IList<string>`)|
|Geschlossen generisch mit einer beliebigen Anzahl an Parametern|Offen generisch mit einem beliebigen Parameter des Typs|`MyType<T,U,V> : IList<U>`<br /><br /> , wobei T=`int`, U=`string`, V=`bool`|Geschlossen generisch (z. B. `IList<string>`)|
|Offen generisch mit einem Parameter|Offen generisch mit dem Parameter des Typs|`MyType<T> : IList<T>`, T ist offen|Offen generisch (z. B. `IList<T>`)|

Wenn ein Typ mehr als eine Listensammlungsschnittstelle implementiert, gelten die folgenden Einschränkungen:

- Wenn der Typ das generische <xref:System.Collections.Generic.IEnumerable%601> (oder die davon abgeleiteten Schnittstellen) mehrfach für verschiedene Typen implementiert, gilt der Typ nicht als gültiger referenzierter Sammlungstyp und wird ignoriert. Dies gilt auch, wenn einige Implementierungen ungültig sind oder offene Generics verwenden. Beispielsweise würde ein Typ, der das generische <xref:System.Collections.Generic.IEnumerable%601> von `int` und das generische <xref:System.Collections.Generic.IEnumerable%601> von T implementiert, niemals als referenzierte Sammlung von `int` oder eines anderen Typs verwendet werden, unabhängig davon, ob der Typ eine `Add` -Methode, die `int` akezptiert, oder eine `Add` -Methode, die einen Parameter vom Typ T akzeptiert, oder beides aufweist.

- Wenn der Typ eine generische Sammlungsschnittstelle sowie <xref:System.Collections.IList>implementiert, wird er niemals als referenzierter Sammlungstyp verwendet, es sei denn, die generische Sammlungsschnittstelle ist ein geschlossener generischer Typ vom Typ <xref:System.Object>.

Für Wörterbuchsammlungen werden nur die Fälle aus der folgenden Tabelle unterstützt:

|Referenzierter Typ|Vom referenzierten Typ implementierte Schnittstelle|Beispiel|Typ behandelt als|
|---------------------|----------------------------------------------|-------------|---------------------|
|Nicht generisch oder geschlossen generisch (beliebige Anzahl von Parametern)|<xref:System.Collections.IDictionary>|`MyType : IDictionary`<br /><br /> oder<br /><br /> `MyType<T> : IDictionary` , wobei T=`int`|Geschlossenes generisches `IDictionary<object,object>`|
|Geschlossen generisch (beliebigen Anzahl an Parametern)|<xref:System.Collections.Generic.IDictionary%602>, geschlossen|`MyType<T> : IDictionary<string, bool>` , wobei T=`int`|Geschlossen generisch (z. B. `IDIctionary<string,bool>`)|
|Geschlossen generisch (beliebigen Anzahl an Parametern)|Generisches <xref:System.Collections.Generic.IDictionary%602>, entweder der Schlüssel oder der Wert ist geschlossen, das andere Element ist offen und verwendet einen Parameter des Typs|`MyType<T,U,V> : IDictionary<string,V>` , wobei T=`int`, U=`float`, V=`bool`<br /><br /> oder<br /><br /> `MyType<Z> : IDictionary<Z,bool>` , wobei Z=`string`|Geschlossen generisch (z. B. `IDictionary<string,bool>`)|
|Geschlossen generisch (beliebigen Anzahl an Parametern)|Generisches <xref:System.Collections.Generic.IDictionary%602>, sowohl Schlüssel als auch Wert sind geöffnet und verwenden beide jeweils einen Parameter des Typs|`MyType<T,U,V> : IDictionary<V,U>` , wobei T=`int`, U=`bool`, V=`string`|Geschlossen generisch (z. B. `IDictionary<string,bool>`)|
|Offen generisch (zwei Parameter)|Generisches <xref:System.Collections.Generic.IDictionary%602>, offen, verwendet beide generischen Parametern des Typs in der Reihenfolge, in der sie angezeigt werden.|`MyType<K,V> : IDictionary<K,V>`, K und V beide offen|Offen generisch (z. B. `IDictionary<K,V>`)|

Wenn der Typ sowohl das <xref:System.Collections.IDictionary> als auch das generische <xref:System.Collections.Generic.IDictionary%602>implementiert, wird nur das generische <xref:System.Collections.Generic.IDictionary%602> betrachtet.

Das Verweisen auf teilweise generische Typen wird nicht unterstützt.

Duplikate sind nicht zulässig. Beispielsweise können Sie nicht sowohl die generische <xref:System.Collections.Generic.List%601> von `Integer` als auch die generische Sammlung von `Integer`<xref:System.Runtime.Serialization.ImportOptions.ReferencedCollectionTypes%2A>hinzufügen, da anschließend nicht mehr festgestellt werden kann, was verwendet werden soll, wenn eine Liste mit ganzen Zahlen im Schema auftritt. Duplikate werden nur erkannt, wenn es einen Typ im Schema gibt, der das Duplikatproblem offenlegt. Wenn z. B. das importierte Schema keine Liste mit ganzen Zahlen enthält, kann es sowohl über die generische <xref:System.Collections.Generic.List%601> von `Integer` als auch über die generische Sammlung von `Integer` in den <xref:System.Runtime.Serialization.ImportOptions.ReferencedCollectionTypes%2A>verfügen, doch nichts davon zeigt eine Wirkung.

## <a name="advanced-collection-rules"></a>Erweiterte Sammlungsregeln

### <a name="serializing-collections"></a>Serialisieren von Sammlungen

Im Folgenden finden Sie eine Liste mit Sammlungsregeln für die Serialisierung:

- Das Kombinieren von Sammlungstypen (das Erstellen von Sammlungen von Sammlungen) ist zulässig. Verzweigte Arrays werden als Sammlungen von Sammlungen behandelt. Arrays mit mehreren Dimensionen werden nicht unterstützt.

- Byte- und <xref:System.Xml.XmlNode> -Arrays sind besondere Arraytypen, die als Primitive und nicht als Sammlungen behandelt werden. Die Serialisierung eines Bytearrays führt zu einem einzelnen XML-Element, das statt eines separaten Elements für jedes Byte einen Abschnitt aus Base64-codierten Daten enthält. Weitere Informationen zur Behandlung eines Arrays von finden Sie unter <xref:System.Xml.XmlNode> [XML-und ADO.NET-Typen in Daten Verträgen](xml-and-ado-net-types-in-data-contracts.md). Natürlich können diese besonderen Typen selbst Teil von Sammlungen sein: Ein Bytearray führt zu mehreren XML-Elementen, die jeweils einen Abschnitt aus Base64-codierten Daten enthalten.

- Wenn das <xref:System.Runtime.Serialization.DataContractAttribute> -Attribut auf einen Sammlungstyp angewendet wird, wird der Typ als regulärer Datenvertragstyp und nicht als Sammlung behandelt.

- Wenn ein Sammlungstyp die <xref:System.Xml.Serialization.IXmlSerializable> -Schnittstelle implementiert, dann gelten die folgenden Regeln, wenn ein `myType:IList<string>, IXmlSerializable`-Typ vorliegt:

  - Wird als Typ `IList<string>`deklariert, wird der Typ als Liste serialisiert.

  - Wird als Typ `myType`deklariert, wird der Typ als `IXmlSerializable`serialisiert.

  - Wenn der deklarierte Typ `IXmlSerializable`lautet, wird der Typ nur dann als `IXmlSerializable`serialisiert, wenn Sie `myType` der Liste bekannter Typen hinzufügen.

- Sammlungen werden mit den Methoden aus der folgenden Tabelle serialisiert und deserialisiert:

|Sammlungstyp implementiert|Bei der Serialisierung aufgerufene Methode(n)|Bei der Deserialisierung aufgerufene Methode(n)|
|--------------------------------|-----------------------------------------|-------------------------------------------|
|Generisches <xref:System.Collections.Generic.IDictionary%602>|`get_Keys`, `get_Values`|Generisches Hinzufügen|
|<xref:System.Collections.IDictionary>|`get_Keys`, `get_Values`|`Add`|
|Generisches <xref:System.Collections.Generic.IList%601>|Generischer <xref:System.Collections.Generic.IList%601> -Indexer|Generisches Hinzufügen|
|Generisches <xref:System.Collections.Generic.ICollection%601>|Enumerator|Generisches Hinzufügen|
|<xref:System.Collections.IList>|<xref:System.Collections.IList> -Indexer|`Add`|
|Generisches <xref:System.Collections.Generic.IEnumerable%601>|`GetEnumerator`|Eine nicht statische Methode mit dem Namen `Add` , die einen Parameter des entsprechenden Typs annimmt (den Typ des generischen Parameters oder einen der Basistypen). Eine solche Methode ist erforderlich, damit das Serialisierungsprogramm einen Sammlungstyp sowohl während der Serialisierung als auch während der Deserialisierung als Sammlung behandelt.|
|<xref:System.Collections.IEnumerable> (und daher <xref:System.Collections.ICollection>, die sich daraus ableitet)|`GetEnumerator`|Eine nicht statische Methode namens `Add` , die einen Parameter des Typs `Object`annimmt. Eine solche Methode ist erforderlich, damit das Serialisierungsprogramm einen Sammlungstyp sowohl während der Serialisierung als auch während der Deserialisierung als Sammlung behandelt.|

In der vorangehenden Tabelle werden in absteigender Reihenfolge Sammlungsschnittstellen aufgelistet. Das bedeutet beispielsweise, dass die Sammlung gemäß den <xref:System.Collections.IList> -Regeln serialisiert und deserialisiert wird, wenn ein Typ sowohl die <xref:System.Collections.Generic.IEnumerable%601>als auch das generische <xref:System.Collections.IList> implementiert:

- Bei der Deserialisierung werden alle Sammlungen deserialisiert, indem zuerst eine Instanz des Typs erstellt wird, indem der Parameter lose Konstruktor aufgerufen wird, der vorhanden sein muss, damit das Serialisierungsprogramm einen Sammlungstyp während der Serialisierung und Deserialisierung als Auflistung behandelt.

- Wenn die gleiche generische Sammlungsschnittstelle mehrmals implementiert wird (z. B. wenn ein Typ sowohl die generische <xref:System.Collections.Generic.ICollection%601> von `Integer` als auch die generische <xref:System.Collections.Generic.ICollection%601> von <xref:System.String>implementiert) und keine Schnittstelle mit höherer Rangfolge gefunden wird, wird die Sammlung nicht als gültige Sammlung behandelt.

- Auf Sammlungstypen kann das <xref:System.SerializableAttribute> -Attribut angewendet sein, und sie können die <xref:System.Runtime.Serialization.ISerializable> -Schnittstelle implementieren. Beide werden ignoriert. Wenn jedoch der Typ die Sammlungstypanforderungen nicht vollständig erfüllt (z. B. wenn der Sammlungstyp und die `Add` -Methode fehlen), wird der Typ nicht als Sammlungstyp betrachtet. Daher werden das <xref:System.SerializableAttribute> -Attribut und die <xref:System.Runtime.Serialization.ISerializable> -Schnittstelle verwendet, um die Serialisierbarkeit des Typs zu bestimmen.

- Durch Anwenden des <xref:System.Runtime.Serialization.CollectionDataContractAttribute> -Attributs auf eine Sammlung, um diese anzupassen, wird der oben genannte <xref:System.SerializableAttribute> -Fallback-Mechanismus entfernt. Stattdessen wird eine <xref:System.Runtime.Serialization.InvalidDataContractException> -Ausnahme ausgelöst, wenn eine benutzerdefinierte Sammlung keine Sammlungstypanforderungen erfüllt,. Die Ausnahme Zeichenfolge enthält häufig Informationen, die erläutern, warum ein bestimmter Typ nicht als gültige Auflistung angesehen wird (keine `Add` Methode, kein Parameter loser Konstruktor usw.). Daher ist es häufig hilfreich, das <xref:System.Runtime.Serialization.CollectionDataContractAttribute> Attribut zu Debuggingzwecken anzuwenden.

### <a name="collection-naming"></a>Sammlungsbenennung

Im Folgenden finden Sie eine Liste von Regeln für die Sammlungsbenennung:

- Der Standard Namespace für alle Datenverträge für Wörterbuch Sammlungen sowie für Datenverträge für Listen Sammlungen, die primitive Typen enthalten, ist, `http://schemas.microsoft.com/2003/10/Serialization/Arrays` Wenn nicht mithilfe von Namespace überschrieben. Typen, die integrierten XSD-Typen zugeordnet werden, sowie `char`-, `Timespan`- und `Guid` -Typen, gelten zu diesem Zweck als primitive Typen.

- Der Standardnamespace für Sammlungstypen, die nicht primitive Typen enthalten, ist der gleiche wie der Namespace für die Datenverträge des in der Sammlung enthaltenen Typs, sofern er nicht von "Namespace" überschrieben wurde.

- Der Standardname für Datenverträge für Sammlungstypen ist die Zeichenfolge "ArrayOf" in Kombination mit dem Datenvertragsnamen des in der Sammlung enthaltenen Typs, sofern er nicht von "Name" überschrieben wurde. Der Datenvertragsname einer generischen Liste von ganzen Zahlen lautet z. B. "ArrayOfint". Beachten Sie, dass der Datenvertragsname von `Object` "anyType" lautet, sodass der Datenvertragsname für nicht generische Listen wie <xref:System.Collections.ArrayList> "ArrayOfanyType" lautet.

Der Standardname für Datenverträge für Wörterbuchsammlungen ist die Zeichenfolge "ArrayOfKeyValueOf" in Kombination mit dem Datenvertragsnamen für den Schlüsseltyp, gefolgt vom Datenvertragsnamen des Werttyps, sofern er nicht von `Name`überschrieben wurde. Der Datenvertragsname für ein generisches Wörterbuch für Zeichenfolge und ganze Zahl lautet z. B. "ArrayOfKeyValueOfstringint". Wenn darüber hinaus der Schlüssel- oder der Werttyp kein primitiver Typ ist, wird an den Namen ein Namespacehash der Datenvertragsnamespaces für den Schlüssel- und Werttyp angefügt. Weitere Informationen zu Namespace-Hashes finden Sie unter [Daten Vertrags Namen](data-contract-names.md).

Jeder Wörterbuchsammlungsdatenvertrag weist einen Begleitdatenvertrag auf, der einen Eintrag im Wörterbuch darstellt. Der Name ist der gleiche wie der des Wörterbuchdatenvertrags, bis auf das Präfix "ArrayOf", und der Namespace ist ebenfalls der gleiche wie für den Wörterbuchdatenvertrag. Beispielsweise kann für den "ArrayOfKeyValueOfstringint"-Wörterbuchdatenvertrag der "KeyValueofstringint"-Datenvertrag einen Eintrag im Wörterbuch darstellen. Sie können den Namen dieses Datenvertrags individuell anpassen, indem Sie die `ItemName` -Eigenschaft verwenden, wie im nächsten Abschnitt beschrieben.

Benennungsregeln für generische Typen, wie unter [Data Contract Names](data-contract-names.md)beschrieben, gelten vollständig für Sammlungstypen, d. h. Sie können geschweifte Klammern innerhalb von "Name" verwenden, um generische Parametertypen anzuzeigen. Die Zahlen innerhalb der Klammern verweisen jedoch auf generische Parameter und nicht auf Typen, die in der Sammlung enthalten sind.

## <a name="collection-customization"></a>Sammlungsanpassung

Die folgenden Verwendungen des <xref:System.Runtime.Serialization.CollectionDataContractAttribute> -Attributs sind unzulässig und führen zu einer <xref:System.Runtime.Serialization.InvalidDataContractException> -Ausnahme:

- Das Anwenden des <xref:System.Runtime.Serialization.DataContractAttribute> -Attributs auf einen Typ, auf den das <xref:System.Runtime.Serialization.CollectionDataContractAttribute> -Attribut angewendet wurde, oder auf einen von diesem abgeleiteten Typ.

- Das Anwenden des <xref:System.Runtime.Serialization.CollectionDataContractAttribute> -Attributs auf einen Typ, der die <xref:System.Xml.Serialization.IXmlSerializable> -Schnittstelle implementiert.

- Das Anwenden des <xref:System.Runtime.Serialization.CollectionDataContractAttribute> -Attributs auf einen Typ, bei dem es sich nicht um einen Sammlungstyp handelt.

- Der Versuch, <xref:System.Runtime.Serialization.CollectionDataContractAttribute.KeyName%2A> oder <xref:System.Runtime.Serialization.CollectionDataContractAttribute.ValueName%2A> auf einem <xref:System.Runtime.Serialization.CollectionDataContractAttribute> -Attribut festzulegen, das auf einen Typ angewendet wird, bei dem es sich nicht um einen Wörterbuchtyp handelt.

### <a name="polymorphism-rules"></a>Polymorphieregeln

Wie bereits erwähnt, behindert das Anpassen von Sammlungen mit dem <xref:System.Runtime.Serialization.CollectionDataContractAttribute> -Attribut möglicherweise die Austauschbarkeit der Sammlungen. Zwei benutzerdefinierte Sammlungstypen gelten nur als gleich, wenn ihre Namen, ihr Namespace, ihr Elementname und ihre Schlüssel- und Wertnamen (sofern es sich um Wörterbuchsammlungen handelt) übereinstimmen.

Aufgrund der Anpassungen ist es möglich, einen Sammlungsdatenvertrag, wo noch ein weiterer erwartet wird, versehentlich zu verwenden. Dies sollte vermieden werden. Siehe folgende Typen:

[!code-csharp[c_collection_types_in_data_contracts#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_collection_types_in_data_contracts/cs/program.cs#11)]
[!code-vb[c_collection_types_in_data_contracts#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_collection_types_in_data_contracts/vb/program.vb#11)]

In diesem Fall kann eine Instanz von `Marks1``testMarks`zugewiesen werden. `Marks2` sollte jedoch nicht verwendet werden: Der zugehörige Datenvertrag stimmt nicht mit dem `IList<int>` -Datenvertrag überein. Der Name des Daten Vertrags lautet "Marks2" und nicht "ArrayOfint", und der Name des wiederholten Elements lautet " \<mark> " und nicht " \<int> ".

Die Regeln in der folgenden Tabelle gelten für die polymorphe Zuweisung von Sammlungen:

|Deklarierter Typ|Zuweisen einer nicht benutzerdefinierten Sammlung|Zuweisen einer benutzerdefinierten Sammlung|
|-------------------|--------------------------------------------|---------------------------------------|
|Object|Vertragsname wird serialisiert.|Vertragsname wird serialisiert.<br /><br /> Anpassung wird verwendet.|
|Sammlungsschnittstelle|Vertragsname wird nicht serialisiert.|Vertragsname wird nicht serialisiert.<br /><br /> Anpassung wird nicht verwendet.\*|
|Nicht benutzerdefinierte Sammlung|Vertragsname wird nicht serialisiert.|Vertragsname wird serialisiert.<br /><br /> Anpassung wird verwendet.**|
|Benutzerdefinierte Sammlung|Vertragsname wird serialisiert. Anpassung wird nicht verwendet.\*\*|Vertragsname wird serialisiert.<br /><br /> Die Anpassung des zugewiesenen Typs wird verwendet.\*\*|

\*Mit der- <xref:System.Runtime.Serialization.NetDataContractSerializer> Klasse wird die Anpassung in diesem Fall verwendet. Die <xref:System.Runtime.Serialization.NetDataContractSerializer> -Klasse serialisiert auch den tatsächlichen Typnamen in diesem Fall, sodass die Deserialisierung wie erwartet funktioniert.

\*\*Diese Fälle führen zu Schema ungültigen Instanzen und sollten daher vermieden werden.

In Fällen, in denen der Vertragsname serialisiert wird, sollte die Liste der bekannten Typen den zugewiesenen Sammlungstyp enthalten. Auch der entgegengesetzte Fall trifft zu: In Fällen, in denen der Name nicht serialisiert wird, muss der Typ nicht der Liste der bekannten Typen hinzugefügt werden.

Einem Array eines Basistyps kann ein Array eines abgeleiteten Typs zugewiesen werden. In diesem Fall wird der Vertragsname für den abgeleiteten Typ für jedes sich wiederholende Element serialisiert. Wenn z. B. ein Typ `Book` vom Typ `LibraryItem`abgeleitet wurde, können Sie ein Array von `Book` einem Array von `LibraryItem`hinzufügen. Dies gilt nicht für andere Sammlungstypen. Sie können z. B. eine `Generic List of Book` nicht einem `Generic List of LibraryItem`zuweisen. Sie können aber ein `Generic List of LibraryItem` zuweisen, das `Book` -Instanzen enthält. Sowohl im Fall mit Array als auch im Fall ohne Array sollte `Book` in der Liste der bekannten Typen enthalten sein.

## <a name="collections-and-object-reference-preservation"></a>Sammlungen und Beibehaltung von Objektverweisen

Wenn ein Serialisierungsprogramm in einem Modus ausgeführt wird, in dem es Objektverweise beibehält, gilt die Beibehaltung der Objektverweise auch für Sammlungen. Insbesondere wird Objektidentität sowohl für ganze Sammlungen als auch für einzelne Elemente beibehalten, die in Sammlungen enthalten sind. Für Wörterbücher wird Objektidentität sowohl für Schlüssel- und Wertepaarobjekte als auch für die einzelnen Schlüssel- und Werteobjekte beibehalten.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Runtime.Serialization.CollectionDataContractAttribute>
