---
title: Datenvertrags-Schemareferenz
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts [WCF], schema reference
ms.assetid: 9ebb0ebe-8166-4c93-980a-7c8f1f38f7c0
ms.openlocfilehash: af183fa02ea3ec98f316979198624351d9b25f21
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2020
ms.locfileid: "75963372"
---
# <a name="data-contract-schema-reference"></a>Datenvertrags-Schemareferenz

In diesem Thema wird die von <xref:System.Runtime.Serialization.DataContractSerializer> zur Beschreibung der Common Language Runtime (CLR)-Typen für die XML-Serialisierung verwendete Teilmenge des XML-Schemas (XSD) beschrieben.

## <a name="datacontractserializer-mappings"></a>DataContractSerializer-Zuordnungen

Der `DataContractSerializer` ordnet CLR-Typen XSD zu, wenn Metadaten von einem Windows Communication Foundation (WCF)-Dienst mithilfe eines Metadatenendpunkts oder dem [Service Model Metadata Utility-Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)exportiert werden. Weitere Informationen finden Sie unter [Data Contract Serializer](../../../../docs/framework/wcf/feature-details/data-contract-serializer.md).

Der `DataContractSerializer` ordnet XSD auch dann CLR-Typen zu, wenn Svcutil.exe für den Zugriff auf WSDL- (Web Services Description Language) oder XSD-Dokumente und für die Generierung von Vertragsdateien für Dienste oder Clients verwendet wird.

Nur XML-Schemainstanzen, die den in diesem Dokument beschriebenen Anforderungen entsprechen, können mit `DataContractSerializer`CLR-Typen zugeordnet werden.

### <a name="support-levels"></a>Unterstützungsebenen

Der `DataContractSerializer` stellt die folgenden Unterstützungsebenen für eine gegebene XML-Schemafunktion bereit:

- **Unterstützt**. Es gibt eine explizite Zuordnung dieser Funktion zu CLR-Typen oder -Attributen (oder beiden) mit `DataContractSerializer`.

- **Ignoriert**. Die Funktion ist in vom `DataContractSerializer`importierten Schemas zugelassen, hat aber keine Auswirkungen auf die Codegenerierung.

- **Unzulässig**. Der `DataContractSerializer` unterstützt nicht den Import eines Schemas, das diese Funktion verwendet. Svcutil.exe verwendet beispielsweise wieder den <xref:System.Xml.Serialization.XmlSerializer> , wenn auf ein WSDL mit einem Schema zugegriffen wird, das eine solche Funktion verwendet. Dies ist das Standardverhalten.

## <a name="general-information"></a>Allgemeine Informationen

- Der Schemanamespace wird unter [XML-Schema](https://www.w3.org/2001/XMLSchema)beschrieben. In diesem Dokument wird das Präfix "xs" verwendet.

- Alle Attribute mit einem Nicht-Schema-Namespace werden ignoriert.

- Alle Anmerkungen (außer den in diesem Dokument beschriebenen) werden ignoriert.

### <a name="xsschema-attributes"></a>\<xs: Schema >: Attribute

|Attribute|DataContract|
|---------------|------------------|
|`attributeFormDefault`|Ignoriert.|
|`blockDefault`|Ignoriert.|
|`elementFormDefault`|Muss qualifiziert sein. Damit ein Schema vom `DataContractSerializer`unterstützt wird, müssen alle Elemente qualifiziert werden. Dies kann erreicht werden, indem Sie entweder xs:schema/@elementFormDefault auf "qualifiziert" festlegen oder für jede einzelne Element Deklaration xs:element/@form auf "qualifiziert" festlegen.|
|`finalDefault`|Ignoriert.|
|`Id`|Ignoriert.|
|`targetNamespace`|Unterstützt und wird dem Datenvertragsnamespace zugeordnet. Wenn dieses Attribut nicht angegeben ist, wird ein leerer Namespace verwendet. Der reservierte Namespace `http://schemas.microsoft.com/2003/10/Serialization/`kann nicht sein.|
|`version`|Ignoriert.|

### <a name="xsschema-contents"></a>\<xs: Schema >: Inhalt

|Inhalt|Schema|
|--------------|------------|
|`include`|Unterstützt. `DataContractSerializer` unterstützt xs:include und xs:import. Svcutil.exe schränkt jedoch darauf folgende `xs:include/@schemaLocation` - und `xs:import/@location` -Verweise ein, wenn Metadaten aus einer lokalen Datei geladen werden. Die Liste der Schemadateien muss in diesem Fall über einen Out-of-Band-Mechanismus und nicht mittels `include` übergeben werden. Mit `include`angegebene Schemadokumente werden ignoriert.|
|`redefine`|Unzulässig. Die Verwendung von `xs:redefine` durch `DataContractSerializer` ist aus Sicherheitsgründen unzulässig: `x:redefine` erfordert, dass `schemaLocation` befolgt wird. Unter bestimmten Umständen schränkt Svcutil.exe mit DataContract die Verwendung von `schemaLocation`ein.|
|`import`|Unterstützt. `DataContractSerializer` unterstützt `xs:include` und `xs:import`. Svcutil.exe schränkt jedoch darauf folgende `xs:include/@schemaLocation` - und `xs:import/@location` -Verweise ein, wenn Metadaten aus einer lokalen Datei geladen werden. Die Liste der Schemadateien muss in diesem Fall über einen Out-of-Band-Mechanismus und nicht mittels `include` übergeben werden. Mit `include`angegebene Schemadokumente werden ignoriert.|
|`simpleType`|Unterstützt. Siehe den Abschnitt `xs:simpleType` .|
|`complexType`|Unterstützt, wird Datenverträgen zugeordnet. Siehe den Abschnitt `xs:complexType` .|
|`group`|Ignoriert. `DataContractSerializer` bietet keine Unterstützung für `xs:group`, `xs:attributeGroup`und `xs:attribute`. Diese Deklarationen werden als untergeordnete Elemente von `xs:schema`ignoriert; auf sie kann jedoch nicht innerhalb von `complexType` oder anderer unterstützter Konstrukte verwiesen werden.|
|`attributeGroup`|Ignoriert. `DataContractSerializer` bietet keine Unterstützung für `xs:group`, `xs:attributeGroup`und `xs:attribute`. Diese Deklarationen werden als untergeordnete Elemente von `xs:schema`ignoriert; auf sie kann jedoch nicht innerhalb von `complexType` oder anderer unterstützter Konstrukte verwiesen werden.|
|`element`|Unterstützt. Siehe Globale Elementdeklaration (GED).|
|`attribute`|Ignoriert. `DataContractSerializer` bietet keine Unterstützung für `xs:group`, `xs:attributeGroup`und `xs:attribute`. Diese Deklarationen werden als untergeordnete Elemente von `xs:schema`ignoriert; auf sie kann jedoch nicht innerhalb von `complexType` oder anderer unterstützter Konstrukte verwiesen werden.|
|`notation`|Ignoriert.|

## <a name="complex-types--xscomplextype"></a>Komplexe Typen – \<xs: complexType >

### <a name="general-information"></a>Allgemeine Informationen

Jeder komplexe Typ \<xs: complexType > einem Datenvertrag zugeordnet.

### <a name="xscomplextype-attributes"></a>\<xs: complexType >: Attribute

|Attribute|Schema|
|---------------|------------|
|`abstract`|Muss den Wert false aufweisen (Standardwert)|
|`block`|Unzulässig.|
|`final`|Ignoriert.|
|`id`|Ignoriert.|
|`mixed`|Muss den Wert false aufweisen (Standardwert)|
|`name`|Unterstützt. Wird dem Namen des Datenvertrags zugeordnet. Wenn der Name Punkte enthält, wird versucht, den Typ einem inneren Typ zuzuordnen. Beispielsweise wird ein komplexer Typ namens `A.B` einem Datenvertragstyp zugeordnet, der ein innerer Typ mit dem Datenvertragsnamen `A`ist. Dies geschieht jedoch nur dann, wenn ein solcher Datenvertragstyp vorhanden ist. Es ist mehr als eine Verschachtelungsebene möglich: `A.B.C` z.&#160;B. kann ein innerer Typ sein, jedoch nur dann, wenn sowohl `A` als auch `A.B` vorhanden sind.|

### <a name="xscomplextype-contents"></a>\<xs:complexType>: contents

|Inhalt|Schema|
|--------------|------------|
|`simpleContent`|Erweiterungen sind unzulässig.<br /><br /> Einschränkung wird nur von `anySimpleType`zugelassen.|
|`complexContent`|Unterstützt. Siehe "Vererbung".|
|`group`|Unzulässig.|
|`all`|Unzulässig.|
|`choice`|Unzulässig|
|`sequence`|Unterstützt, wird Datenmembern eines Datenvertrags zugeordnet.|
|`attribute`|Unzulässig, auch wenn use="prohibited" (mit einer Ausnahme). Nur optionale Attribute aus dem Standardserialisierungsschema-Namespace werden unterstützt. Sie werden Datenmembern im Datenvertragsprogrammiermodell nicht zugeordnet. Aktuell hat nur ein solches Attribut Bedeutung, es wird im Abschnitt ISerializable erläutert. Alle anderen werden ignoriert.|
|`attributeGroup`|Unzulässig. In der WCF v1-Version ignoriert `DataContractSerializer` das vorhanden sein `attributeGroup` in `xs:complexType`.|
|`anyAttribute`|Unzulässig.|
|(leer)|Wird einem Datenvertrag ohne Datenmember zugeordnet.|

### <a name="xssequence-in-a-complex-type-attributes"></a>\<xs: Sequence > in einem komplexen Typ: Attribute

|Attribute|Schema|
|---------------|------------|
|`id`|Ignoriert.|
|`maxOccurs`|Muss 1 (Standard) sein.|
|`minOccurs`|Muss 1 (Standard) sein.|

### <a name="xssequence-in-a-complex-type-contents"></a>\<xs: Sequence > in einem komplexen Typ: Inhalt

|Inhalt|Schema|
|--------------|------------|
|`element`|Jede Instanz wird einem Datenmember zugeordnet.|
|`group`|Unzulässig.|
|`choice`|Unzulässig.|
|`sequence`|Unzulässig.|
|`any`|Unzulässig.|
|(leer)|Wird einem Datenvertrag ohne Datenmember zugeordnet.|

## <a name="elements--xselement"></a>Elements – \<xs: Element >

### <a name="general-information"></a>Allgemeine Informationen

`<xs:element>` kann in den folgenden Kontexten auftreten:

- Es kann innerhalb eines `<xs:sequence>`-Elements auftreten, das einen Datenmember eines regulären Datenvertrags (keines Auflistungsdatenvertrags) beschreibt. In diesem Fall muss das `maxOccurs` -Attribut 1 sein. (Der Wert 0 ist nicht zulässig.)

- Es kann innerhalb eines `<xs:sequence>`-Elements auftreten, das einen Datenmember eines Auflistungsdatenvertrags beschreibt. In diesem Fall muss der Wert des `maxOccurs` -Attributs größer&#160;1 oder "unbounded" sein.

- Es kann innerhalb eines `<xs:schema>` -Elements als eine globale Elementdeklaration (GED) auftreten.

### <a name="xselement-with-maxoccurs1-within-an-xssequence-data-members"></a>\<xs: Element > mit maxvorkommen = 1 innerhalb eines \<xs: Sequence-> (Datenmember)

|Attribute|Schema|
|---------------|------------|
|`ref`|Unzulässig.|
|`name`|Unterstützt, wird dem Datenmembernamen zugeordnet.|
|`type`|Unterstützt, wird dem Datenmembertyp zugeordnet. Weitere Informationen finden Sie unter Zuordnung von Typen zu primitivem Typen. Wenn nicht angegeben (und wenn das Element keinen anonymen Typ enthält), wird `xs:anyType` angenommen.|
|`block`|Ignoriert.|
|`default`|Unzulässig.|
|`fixed`|Unzulässig.|
|`form`|Muss qualifiziert sein. Dieses Attribut kann über `elementFormDefault` auf `xs:schema`festgelegt werden.|
|`id`|Ignoriert.|
|`maxOccurs`|1|
|`minOccurs`|Wird der <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> -Eigenschaft eines Datenmembers zugeordnet (`IsRequired` hat den Wert true, wenn `minOccurs` &#160;1 ist).|
|`nillable`|Beeinflusst die Typzuordnung. Siehe Zuordnung von Typen zu primitivem Typen.|

### <a name="xselement-with-maxoccurs1-within-an-xssequence-collections"></a>\<xs: Element > mit maxvorkommen > 1 innerhalb einer \<xs: Sequence > (Auflistungen)

- Wird einem <xref:System.Runtime.Serialization.CollectionDataContractAttribute>zugeordnet.

- In Auflistungstypen ist nur ein xs:element innerhalb eines xs:sequence-Elements zugelassen.

 Auflistungen können einen der folgenden Typen aufweisen:

- Reguläre Auflistungen (z. B. Arrays).

- Wörterbuchauflistungen (die einen Wert einem anderen zuordnen, z.&#160;B. eine <xref:System.Collections.Hashtable>).

- Der einzige Unterschied zwischen einem Wörterbuchtyp und einem Array mit Schlüssel-Wert-Paaren liegt im generierten Programmiermodell. Es gibt einen Schemaanmerkungsmechanismus, der verwendet werden kann, um anzugeben, dass ein bestimmter Typ eine Wörterbuchauflistung ist.

Die Regeln für die Attribute `ref`, `block`, `default`, `fixed`, `form`und `id` sind die gleichen wie für diejenigen, die keine Auflistungstypen sind. Die anderen Attribute sind in der folgenden Tabelle aufgeführt:

|Attribute|Schema|
|---------------|------------|
|`name`|Unterstützt, wird der <xref:System.Runtime.Serialization.CollectionDataContractAttribute.ItemName%2A> -Eigenschaft des `CollectionDataContractAttribute` -Attributs zugeordnet.|
|`type`|Unterstützt, wird dem in der Auflistung gespeicherten Typ zugeordnet.|
|`maxOccurs`|Größer&#160;1 oder "unbounded". Das DC-Schema sollte "unbounded" verwenden.|
|`minOccurs`|Ignoriert.|
|`nillable`|Beeinflusst die Typzuordnung. Dieses Attribut wird für Wörterbuchauflistungen ignoriert.|

### <a name="xselement-within-an-xsschema-global-element-declaration"></a>\<xs:-Element innerhalb einer \<xs: Schema > globalen Element Deklaration >

- Eine globale Elementdeklaration (GED), die den gleichen Namen und Namespace wie ein Typ im Schema besitzt, oder die innerhalb ihrer selbst einen anonymen Typ definiert, wird als diesem Typ zugeordnet angesehen.

- Schemaexport: Für alle generierten Typen, sowohl einfache als auch komplexe, werden zugeordnete GEDs generiert.

- Deserialisierung/Serialisierung: Zugeordnete GEDs werden als Stammelemente für den Typ verwendet.

- Schemaimport: Zugeordnete GEDs sind nicht erforderlich und werden ignoriert, wenn sie den folgenden Regeln entsprechen (es sei denn, sie definieren Typen).

|Attribute|Schema|
|---------------|------------|
|`abstract`|Muss für zugeordnete GEDs den Wert false aufweisen.|
|`block`|Unzulässig in zugeordneten GEDs.|
|`default`|Unzulässig in zugeordneten GEDs.|
|`final`|Muss für zugeordnete GEDs den Wert false aufweisen.|
|`fixed`|Unzulässig in zugeordneten GEDs.|
|`id`|Ignoriert.|
|`name`|Unterstützt. Siehe die Definition von zugeordneten GEDs.|
|`nillable`|Muss für zugeordnete GEDs den Wert true aufweisen.|
|`substitutionGroup`|Unzulässig in zugeordneten GEDs.|
|`type`|Unterstützt. Muss dem zugeordneten Typ für zugeordnete GEDs entsprechen (außer wenn das Element einen anonymen Typ enthält).|

### <a name="xselement-contents"></a>\<xs:element>: contents

|Inhalt|Schema|
|--------------|------------|
|`simpleType`|Unterstützt.*|
|`complexType`|Unterstützt.*|
|`unique`|Ignoriert.|
|`key`|Ignoriert.|
|`keyref`|Ignoriert.|
|(leer)|Unterstützt.|

\* bei Verwendung der `simpleType` und `complexType,` Zuordnung für anonyme Typen identisch mit denen für nicht anonyme Typen, mit dem Unterschied, dass es keine anonymen Datenverträge gibt und daher ein benannter Datenvertrag erstellt wird, wobei ein generierter Name aus dem Elementnamen abgeleitet ist. Die folgende Liste enthält die Regeln für anonyme Typen:

- WCF-Implementierungsdetail: Wenn der `xs:element` Name keine Punkte enthält, wird der anonyme Typ einem inneren Typ des äußeren Daten Vertrags Typs zugeordnet. Wenn der Name Punkte enthält, ist der resultierende Datenvertragstyp unabhängig (kein innerer Typ).

- Der generierte Datenvertragsname des inneren Typs setzt sich zusammen aus dem Namen des äußeren Typs, gefolgt von einem Punkt, dem Namen des Elements und der Zeichenfolge "Type".

- Ist ein Datenvertrag mit diesem Namen bereits vorhanden, wird dem Namen&#160;"1", "2", "3" usw. angehängt, um ihn eindeutig zu machen.

## <a name="simple-types---xssimpletype"></a>Einfache Typen-\<xs: simpleType >

### <a name="xssimpletype-attributes"></a>\<xs:simpleType>: attributes

|Attribute|Schema|
|---------------|------------|
|`final`|Ignoriert.|
|`id`|Ignoriert.|
|`name`|Unterstützt, wird dem Namen des Datenvertrags zugeordnet.|

### <a name="xssimpletype-contents"></a>\<xs:simpleType>: contents

|Inhalt|Schema|
|--------------|------------|
|`restriction`|Unterstützt. Wird Enumerationsdatenverträgen zugeordnet. Dieses Attribut wird ignoriert, wenn es nicht zum Enumerationsmuster passt. Siehe den Abschnitt `xs:simpleType` -Einschränkungen.|
|`list`|Unterstützt. Wird Flagenumerationsdatenverträgen zugeordnet. Siehe den Abschnitt `xs:simpleType` -Listen.|
|`union`|Unzulässig.|

### <a name="xsrestriction"></a>\<xs:restriction>

- Einschränkungen komplexer Typen werden nur für base="`xs:anyType`" unterstützt.

- Einfache Typeinschränkungen von `xs:string` , die keine anderen Einschränkungsfacets als `xs:enumeration` haben, werden Enumerationsdatenverträgen zugeordnet.

- Alle anderen einfachen Typeinschränkungen werden den Typen zugeordnet, die sie einschränken. Beispielsweise wird eine Einschränkung von `xs:int` einem Integer zugeordnet, wie es auch bei `xs:int` selbst der Fall ist. Weitere Informationen zur primitiven Typzuordnung finden Sie unter Type/primitive Mapping.

### <a name="xsrestriction-attributes"></a>\<xs: Einschränkungs >: Attribute

|Attribute|Schema|
|---------------|------------|
|`base`|Muss ein unterstützter einfacher Typ oder `xs:anyType`sein.|
|`id`|Ignoriert.|

### <a name="xsrestriction-for-all-other-cases-contents"></a>\<xs: Einschränkungs > für alle anderen Fälle: Inhalt

|Inhalt|Schema|
|--------------|------------|
|`simpleType`|Muss, falls vorhanden, von einem unterstützten primitiven Typ abgeleitet sein.|
|`minExclusive`|Ignoriert.|
|`minInclusive`|Ignoriert.|
|`maxExclusive`|Ignoriert.|
|`maxInclusive`|Ignoriert.|
|`totalDigits`|Ignoriert.|
|`fractionDigits`|Ignoriert.|
|`length`|Ignoriert.|
|`minLength`|Ignoriert.|
|`maxLength`|Ignoriert.|
|`enumeration`|Ignoriert.|
|`whiteSpace`|Ignoriert.|
|`pattern`|Ignoriert.|
|(leer)|Unterstützt.|

## <a name="enumeration"></a>-Enumeration

### <a name="xsrestriction-for-enumerations-attributes"></a>\<xs: Einschränkungs > für Enumerationen: Attribute

|Attribute|Schema|
|---------------|------------|
|`base`|Muss, falls vorhanden, `xs:string`sein.|
|`id`|Ignoriert.|

### <a name="xsrestriction-for-enumerations-contents"></a>\<xs: Einschränkungs > für Enumerationen: Inhalt

|Inhalt|Schema|
|--------------|------------|
|`simpleType`|Muss, falls vorhanden, eine vom Datenvertrag (dieser Abschnitt) unterstützte Enumerationsbeschränkung sein.|
|`minExclusive`|Ignoriert.|
|`minInclusive`|Ignoriert.|
|`maxExclusive`|Ignoriert.|
|`maxInclusive`|Ignoriert.|
|`totalDigits`|Ignoriert.|
|`fractionDigits`|Ignoriert.|
|`length`|Unzulässig.|
|`minLength`|Unzulässig.|
|`maxLength`|Unzulässig.|
|`enumeration`|Unterstützt. Enumerations-"ID" wird ignoriert, und "value" wird dem Wertnamen im Enumerationsdatenvertrag zugeordnet.|
|`whiteSpace`|Unzulässig.|
|`pattern`|Unzulässig.|
|(leer)|Unterstützt, wird leerem Enumerationstyp zugeordnet.|

 Der folgende Code zeigt eine C#-Enumerationsklasse.

```csharp
public enum MyEnum
{
  first = 3,
  second = 4,
  third =5
}
```

Diese Klasse wird vom `DataContractSerializer`dem folgenden Schema zugeordnet. Wenn die Enumerationswerte mit&#160;1 beginnen, werden keine `xs:annotation` -Blöcke generiert.

```xml
<xs:simpleType name="MyEnum">
  <xs:restriction base="xs:string">
    <xs:enumeration value="first">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">
          3
          </EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="second">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">
          4
          </EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
  </xs:restriction>
</xs:simpleType>
```

### <a name="xslist"></a>\<xs:list>

`DataContractSerializer` ordnet mit `System.FlagsAttribute` markierte Enumerationstypen einer von `xs:list` abgeleiteten `xs:string`zu. Andere `xs:list` -Variationen werden nicht unterstützt.

### <a name="xslist-attributes"></a>\<xs: List >: Attribute

|Attribute|Schema|
|---------------|------------|
|`itemType`|Unzulässig.|
|`id`|Ignoriert.|

### <a name="xslist-contents"></a>\<xs:list>: contents

|Inhalt|Schema|
|--------------|------------|
|`simpleType`|Muss eine Einschränkung von `xs:string` mit `xs:enumeration` -Facet sein.|

Sind die Enumerationswerte keine Folge mit Potenzen des Werts&#160;2 (für Flags der Standard), wird der Wert im `xs:annotation/xs:appInfo/ser:EnumerationValue` -Element gespeichert.

Der folgende Code definiert z.&#160;B. einen Enumerationstyp für Flags.

```csharp
[Flags]
public enum AuthFlags
{
  AuthAnonymous = 1,
  AuthBasic = 2,
  AuthNTLM = 4,
  AuthMD5 = 16,
  AuthWindowsLiveID = 64,
}
```

Dieser Typ wird dem folgenden Schema zugeordnet.

```xml
<xs:simpleType name="AuthFlags">
    <xs:list>
      <xs:simpleType>
        <xs:restriction base="xs:string">
          <xs:enumeration value="AuthAnonymous" />
          <xs:enumeration value="AuthBasic" />
          <xs:enumeration value="AuthNTLM" />
          <xs:enumeration value="AuthMD5">
            <xs:annotation>
              <xs:appinfo>
                <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">16</EnumerationValue>
              </xs:appinfo>
            </xs:annotation>
          </xs:enumeration>
          <xs:enumeration value="AuthWindowsLiveID">
            <xs:annotation>
              <xs:appinfo>
                <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">64</EnumerationValue>
              </xs:appinfo>
            </xs:annotation>
          </xs:enumeration>
        </xs:restriction>
      </xs:simpleType>
    </xs:list>
  </xs:simpleType>
```

## <a name="inheritance"></a>Vererbung

### <a name="general-rules"></a>Allgemeine Regeln

Ein Datenvertrag kann von einem anderen Datenvertrag erben. Solche Datenverträge werden einem Basistyp zugeordnet und durch Erweiterungstypen mithilfe des `<xs:extension>` -XML-Schemakonstrukts abgeleitet.

Ein Datenvertrag kann nicht von einem Auflistungsdatenvertrag erben.

Der folgende Code stellt z.&#160;B. einen Datenvertrag dar.

```csharp
[DataContract]
public class Person
{
  [DataMember]
  public string Name;
}
[DataContract]
public class Employee : Person
{
  [DataMember]
  public int ID;
}
```

Dieser Datenvertrag wird der folgenden XML-Schema-Typdeklaration zugeordnet.

```xml
<xs:complexType name="Employee">
 <xs:complexContent mixed="false">
  <xs:extension base="tns:Person">
   <xs:sequence>
    <xs:element minOccurs="0" name="ID" type="xs:int"/>
   </xs:sequence>
  </xs:extension>
 </xs:complexContent>
</xs:complexType>
<xs:complexType name="Person">
 <xs:sequence>
  <xs:element minOccurs="0" name="Name"
    nillable="true" type="xs:string"/>
 </xs:sequence>
</xs:complexType>
```

### <a name="xscomplexcontent-attributes"></a>\<xs:complexContent>: attributes

|Attribute|Schema|
|---------------|------------|
|`id`|Ignoriert.|
|`mixed`|Muss den Wert false aufweisen.|

### <a name="xscomplexcontent-contents"></a>\<xs:complexContent>: contents

|Inhalt|Schema|
|--------------|------------|
|`restriction`|Unzulässig, außer wenn base="`xs:anyType`". Letzteres entspricht der Platzierung des Inhalts von `xs:restriction` direkt unter den Container von `xs:complexContent`.|
|`extension`|Unterstützt. Wird der Datenvertragsvererbung zugeordnet.|

### <a name="xsextension-in-xscomplexcontent-attributes"></a>\<xs: Extension > in \<xs: complexContent >: Attribute

|Attribute|Schema|
|---------------|------------|
|`id`|Ignoriert.|
|`base`|Unterstützt. Wird dem Basisdatenvertragstyp zugeordnet, von dem dieser Typ erbt.|

### <a name="xsextension-in-xscomplexcontent-contents"></a>\<xs: Extension > in \<xs: complexContent >: Content

Die Regeln sind die gleichen wie für den `<xs:complexType>` -Inhalt.

Wird `<xs:sequence>` angegeben, werden dessen Memberelemente den zusätzlichen Datenmembern zugeordnet, die im abgeleiteten Datenvertrag vorhanden sind.

Wenn ein abgeleiteter Typ ein Element mit dem gleichen Namen wie ein Element in einem Basistyp enthält, wird die doppelte Elementdeklaration einem Datenmember zugeordnet, für den ein eindeutiger Name generiert wurde. Dazu werden dem Datenmember so lange positive Ganzzahlen hinzugefügt ("member1", "member2" usw.), bis ein eindeutiger Name gefunden ist. Umgekehrt:

- Wenn ein abgeleiteter Datenvertrag einen Datenmember mit dem gleichen Namen und Typ wie ein Datenmember in einem Basisdatenvertrag enthält, generiert der `DataContractSerializer` dieses entsprechende Element im abgeleiteten Typ.

- Wenn ein abgeleiteter Datenvertrag einen Datenmember mit dem gleichen Namen, jedoch einem anderen Typ als ein Datenmember in einem Basisdatenvertrag enthält, importiert der `DataContractSerializer` ein Schema mit einem Element des Typs `xs:anyType` in die Deklarationen sowohl des Basistyps als auch des abgeleiteten Typs. Der ursprüngliche Typname wird in `xs:annotations/xs:appInfo/ser:ActualType/@Name`beibehalten.

Beide Variationen können zu einem Schema mit einem mehrdeutigen Inhaltsmodell führen, das von der Reihenfolge der jeweiligen Datenmember abhängt.

## <a name="typeprimitive-mapping"></a>Zuordnung von Typen zu primitivem Typen

Der `DataContractSerializer` verwendet die folgende Zuordnung für primitive Typen von XML-Schemas.

|XSD-Datentyp|.NET-Typ|
|--------------|---------------|
|`anyType`|<xref:System.Object>.|
|`anySimpleType`|<xref:System.String>.|
|`duration`|<xref:System.TimeSpan>.|
|`dateTime`|<xref:System.DateTime>.|
|`dateTimeOffset`|<xref:System.DateTime> und <xref:System.TimeSpan> für den Offset. Siehe DateTimeOffset-Serialisierung (unten).|
|`time`|<xref:System.String>.|
|`date`|<xref:System.String>.|
|`gYearMonth`|<xref:System.String>.|
|`gYear`|<xref:System.String>.|
|`gMonthDay`|<xref:System.String>.|
|`gDay`|<xref:System.String>.|
|`gMonth`|<xref:System.String>.|
|`boolean`|<xref:System.Boolean>|
|`base64Binary`|<xref:System.Byte> -Array.|
|`hexBinary`|<xref:System.String>.|
|`float`|<xref:System.Single>.|
|`double`|<xref:System.Double>.|
|`anyURI`|<xref:System.Uri>.|
|`QName`|<xref:System.Xml.XmlQualifiedName>.|
|`string`|<xref:System.String>.|
|`normalizedString`|<xref:System.String>.|
|`token`|<xref:System.String>.|
|`language`|<xref:System.String>.|
|`Name`|<xref:System.String>.|
|`NCName`|<xref:System.String>.|
|`ID`|<xref:System.String>.|
|`IDREF`|<xref:System.String>.|
|`IDREFS`|<xref:System.String>.|
|`ENTITY`|<xref:System.String>.|
|`ENTITIES`|<xref:System.String>.|
|`NMTOKEN`|<xref:System.String>.|
|`NMTOKENS`|<xref:System.String>.|
|`decimal`|<xref:System.Decimal>.|
|`integer`|<xref:System.Int64>.|
|`nonPositiveInteger`|<xref:System.Int64>.|
|`negativeInteger`|<xref:System.Int64>.|
|`long`|<xref:System.Int64>.|
|`int`|<xref:System.Int32>.|
|`short`|<xref:System.Int16>.|
|`Byte`|<xref:System.SByte>.|
|`nonNegativeInteger`|<xref:System.Int64>.|
|`unsignedLong`|<xref:System.UInt64>.|
|`unsignedInt`|<xref:System.UInt32>.|
|`unsignedShort`|<xref:System.UInt16>.|
|`unsignedByte`|<xref:System.Byte>.|
|`positiveInteger`|<xref:System.Int64>.|

## <a name="iserializable-types-mapping"></a>Zuordnung von ISerializable-Typen

In .NET Framework Version 1,0 wurde <xref:System.Runtime.Serialization.ISerializable> als allgemeiner Mechanismus zum Serialisieren von Objekten für Persistenz oder Datenübertragung eingeführt. Es gibt viele .NET Framework Typen, die `ISerializable` implementieren und zwischen Anwendungen übermittelt werden können. <xref:System.Runtime.Serialization.DataContractSerializer> unterstützt von sich aus `ISerializable` -Klassen. Der `DataContractSerializer` ordnet `ISerializable` -Implementierungsschematypen zu, die sich nur durch den qualifizierten Namen (QName) des Typs unterscheiden und tatsächlich Eigenschaftenauflistungen sind. Beispielsweise wird der `DataContractSerializer` <xref:System.Exception> dem folgenden XSD-Typ im `http://schemas.datacontract.org/2004/07/System`-Namespace zugeordnet.

```xml
<xs:complexType name="Exception">
 <xs:sequence>
  <xs:any minOccurs="0" maxOccurs="unbounded"
      namespace="##local" processContents="skip"/>
 </xs:sequence>
 <xs:attribute ref="ser:FactoryType"/>
</xs:complexType>
```

Das optionale, im Serialisierungsschema des Datenvertrags deklarierte Attribut `ser:FactoryType` verweist auf eine Factoryklasse, die den Typ deserialisieren kann. Die Factoryklasse muss Teil der Auflistung bekannter Typen der verwendeten `DataContractSerializer` -Instanz sein. Weitere Informationen zu bekannten Typen finden Sie unter [Data Contract Known Types](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).

## <a name="datacontract-serialization-schema"></a>DataContract-Serialisierungsschema

Eine Anzahl der vom `DataContractSerializer` exportierten Schemas verwendet Typen, Elemente und Attribute eines speziellen Datenvertrags-Serialisierungsnamespace:

`http://schemas.microsoft.com/2003/10/Serialization`

Das Folgende ist eine vollständige Schemadeklaration für die Datenvertragsserialisierung.

```xml
<xs:schema attributeFormDefault="qualified"
   elementFormDefault="qualified"
   targetNamespace =
    "http://schemas.microsoft.com/2003/10/Serialization/"
   xmlns:xs="http://www.w3.org/2001/XMLSchema"
   xmlns:tns="http://schemas.microsoft.com/2003/10/Serialization/">

 <!-- Top-level elements for primitive types. -->
 <xs:element name="anyType" nillable="true" type="xs:anyType"/>
 <xs:element name="anyURI" nillable="true" type="xs:anyURI"/>
 <xs:element name="base64Binary"
       nillable="true" type="xs:base64Binary"/>
 <xs:element name="boolean" nillable="true" type="xs:boolean"/>
 <xs:element name="byte" nillable="true" type="xs:byte"/>
 <xs:element name="dateTime" nillable="true" type="xs:dateTime"/>
 <xs:element name="decimal" nillable="true" type="xs:decimal"/>
 <xs:element name="double" nillable="true" type="xs:double"/>
 <xs:element name="float" nillable="true" type="xs:float"/>
 <xs:element name="int" nillable="true" type="xs:int"/>
 <xs:element name="long" nillable="true" type="xs:long"/>
 <xs:element name="QName" nillable="true" type="xs:QName"/>
 <xs:element name="short" nillable="true" type="xs:short"/>
 <xs:element name="string" nillable="true" type="xs:string"/>
 <xs:element name="unsignedByte"
       nillable="true" type="xs:unsignedByte"/>
 <xs:element name="unsignedInt"
       nillable="true" type="xs:unsignedInt"/>
 <xs:element name="unsignedLong"
       nillable="true" type="xs:unsignedLong"/>
 <xs:element name="unsignedShort"
       nillable="true" type="xs:unsignedShort"/>

 <!-- Primitive types introduced for certain .NET simple types. -->
 <xs:element name="char" nillable="true" type="tns:char"/>
 <xs:simpleType name="char">
  <xs:restriction base="xs:int"/>
 </xs:simpleType>

 <!-- xs:duration is restricted to an ordered value space,
    to map to System.TimeSpan -->
 <xs:element name="duration" nillable="true" type="tns:duration"/>
 <xs:simpleType name="duration">
  <xs:restriction base="xs:duration">
   <xs:pattern
     value="\-?P(\d*D)?(T(\d*H)?(\d*M)?(\d*(\.\d*)?S)?)?"/>
   <xs:minInclusive value="-P10675199DT2H48M5.4775808S"/>
   <xs:maxInclusive value="P10675199DT2H48M5.4775807S"/>
  </xs:restriction>
 </xs:simpleType>

 <xs:element name="guid" nillable="true" type="tns:guid"/>
 <xs:simpleType name="guid">
  <xs:restriction base="xs:string">
   <xs:pattern value="[\da-fA-F]{8}-[\da-fA-F]{4}-[\da-fA-F]{4}-[\da-fA-F]{4}-[\da-fA-F]{12}"/>
  </xs:restriction>
 </xs:simpleType>

 <!-- This is used for schemas exported from ISerializable type. -->
 <xs:attribute name="FactoryType" type="xs:QName"/>
</xs:schema>
```

Auf Folgendes sollte geachtet werden:

- `ser:char` wurde eingeführt, um Unicode-Zeichen des Typs <xref:System.Char>darzustellen.

- Der `valuespace` von `xs:duration` wurde zu einer geordneten Menge reduziert, damit diese einem <xref:System.TimeSpan>zugeordnet werden kann.

- `FactoryType` wird in Schemas verwendet, die von Typen exportiert werden, die von <xref:System.Runtime.Serialization.ISerializable>abgeleitet wurden.

## <a name="importing-non-datacontract-schemas"></a>Importieren von Nicht-DataContract-Schemas

`DataContractSerializer` verfügt über die `ImportXmlTypes` -Option, die den Import von Schemas erlaubt, die dem `DataContractSerializer` -XSD-Profil nicht entsprechen (siehe die <xref:System.Runtime.Serialization.XsdDataContractImporter.Options%2A> -Eigenschaft). Die Festlegung dieser Option auf `true` aktiviert die Akzeptanz nicht-konformer Schematypen und ihre Zuordnung zu der folgenden Implementierung, wobei <xref:System.Xml.Serialization.IXmlSerializable> ein Array von <xref:System.Xml.XmlNode> einschließt (nur der Klassenname unterscheidet sich).

```csharp
[GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]
[System.Xml.Serialization.XmlSchemaProviderAttribute("ExportSchema")]
[System.Xml.Serialization.XmlRootAttribute(IsNullable=false)]
public partial class Person : object, IXmlSerializable
{
  private XmlNode[] nodesField;
  private static XmlQualifiedName typeName =
new XmlQualifiedName("Person","http://Microsoft.ServiceModel.Samples");
  public XmlNode[] Nodes
  {
    get {return this.nodesField;}
    set {this.nodesField = value;}
  }
  public void ReadXml(XmlReader reader)
  {
    this.nodesField = XmlSerializableServices.ReadNodes(reader);
  }
  public void WriteXml(XmlWriter writer)
  {
    XmlSerializableServices.WriteNodes(writer, this.Nodes);
  }
  public System.Xml.Schema.XmlSchema GetSchema()
  {
    return null;
  }
  public static XmlQualifiedName ExportSchema(XmlSchemaSet schemas)
  {
    XmlSerializableServices.AddDefaultSchema(schemas, typeName);
    return typeName;
  }
}
```

## <a name="datetimeoffset-serialization"></a>DateTimeOffset-Serialisierung

<xref:System.DateTimeOffset> wird nicht als primitiver Typ behandelt. Stattdessen wird dieser Typ als komplexes Element mit zwei Teilen serialisiert. Der erste Teil stellt die Datums- und Uhrzeitangabe dar und der zweite Teil den Offset dieser Datums- und Uhrzeitangabe. Ein Beispiel für einen serialisierten DateTimeOffset-Wert wird im folgenden Code gezeigt.

```xml
<OffSet xmlns:a="http://schemas.datacontract.org/2004/07/System">
  <DateTime i:type="b:dateTime" xmlns=""
    xmlns:b="http://www.w3.org/2001/XMLSchema">2008-08-28T08:00:00
  </DateTime>
  <OffsetMinutes i:type="b:short" xmlns=""
   xmlns:b="http://www.w3.org/2001/XMLSchema">-480
   </OffsetMinutes>
</OffSet>
```

Das Schema lautet folgendermaßen:

```xml
<xs:schema targetNamespace="http://schemas.datacontract.org/2004/07/System">
   <xs:complexType name="DateTimeOffset">
      <xs:sequence minOccurs="1" maxOccurs="1">
         <xs:element name="DateTime" type="xs:dateTime"
         minOccurs="1" maxOccurs="1" />
         <xs:element name="OffsetMinutes" type="xs:short"
         minOccurs="1" maxOccurs="1" />
      </xs:sequence>
   </xs:complexType>
</xs:schema>
```

## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- <xref:System.Runtime.Serialization.XsdDataContractImporter>
- [Verwenden von Datenverträgen](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)
