---
title: Externe Zuordnung
ms.date: 03/30/2017
ms.assetid: 076606b8-d889-4ba0-b5da-ae577b146f23
ms.openlocfilehash: 79427cde0784746480e851cf1be56c8bce854919
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161385"
---
# <a name="external-mapping"></a>Externe Zuordnung

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterstützt *externe Zuordnung*, einen Prozess, mit dem Sie eine separate XML-Datei verwenden, um die Zuordnung zwischen dem Datenmodell der Datenbank und dem Objektmodell anzugeben. Die Verwendung einer externen Zuordnungsdatei bietet u. a. folgende Vorteile:  
  
- Sie können den Zuordnungscode vom Anwendungscode trennen. Hierdurch wird die Übersichtlichkeit des Anwendungscodes verbessert.  
  
- Eine externe Zuordnungsdatei kann in etwa wie eine Konfigurationsdatei behandelt werden. Beispielsweise können Sie das Anwendungsverhalten aktualisieren, nachdem die Binärdateien bereits ausgeliefert wurden, indem Sie einfach die externe Zuordnungsdatei austauschen.  
  
## <a name="requirements"></a>Anforderungen  

 Die Zuordnungsdatei muss eine XML-Datei sein, und die Datei muss anhand einer [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Schema Definitionsdatei (. xsd) überprüft werden.  
  
 Es gelten die folgenden Regeln:  
  
- Die Zuordnungsdatei muss eine XML-Datei sein.  
  
- Die XML-Zuordnungsdatei muss gegenüber der XML-Schemadefinitionsdatei gültig sein. Weitere Informationen finden Sie unter Gewusst wie: Überprüfen von [DBML-und externen Mapping-Dateien](how-to-validate-dbml-and-external-mapping-files.md).  
  
- Externe Zuordnungen überschreiben attributbasierte Zuordnungen. Dies bedeutet, dass alle für Klassen erstellten Zuordnungsattribute von <xref:System.Data.Linq.DataContext> ignoriert werden, wenn Sie <xref:System.Data.Linq.DataContext> unter Verwendung einer externen Zuordnungsquelle erstellen. Dieses Verhalten gilt unabhängig davon, ob die Klasse in der externen Zuordnungsdatei enthalten ist.  
  
- [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] bietet keine Unterstützung für die kombinierte Verwendung beider Zuordnungsarten (attributbasiert und extern).  
  
## <a name="xml-schema-definition-file"></a>XML-Schemadefinitionsdatei  

 Die externe Zuordnung in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] muss gegenüber der folgenden XML-Schemadefinition gültig sein.  
  
 Beachten Sie den Unterschied zwischen dieser Schemadefinitionsdatei und der Schemadefinitionsdatei, die zum Überprüfen einer DBML-Datei verwendet wird. Weitere Informationen finden Sie unter [Code Generierung in LINQ to SQL](code-generation-in-linq-to-sql.md)).  
  
> [!NOTE]
> Visual Studio-Benutzer finden diese XSD-Datei auch im Dialogfeld XML-Schemas als "linqdesqlmapping. xsd". Informationen dazu, wie Sie diese Datei ordnungsgemäß zum Überprüfen einer externen Datei verwenden, finden Sie unter Gewusst wie: Überprüfen von [DBML-und externen Mapping-Dateien](how-to-validate-dbml-and-external-mapping-files.md)  
  
```xml  
<?xml version="1.0" encoding="utf-16"?>  
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema" targetNamespace="http://schemas.microsoft.com/linqtosql/mapping/2007" xmlns="http://schemas.microsoft.com/linqtosql/mapping/2007"  
elementFormDefault="qualified" >  
  <xs:element name="Database" type="Database" />  
  <xs:complexType name="Database">  
    <xs:sequence>  
      <xs:element name="Table" type="Table" minOccurs="0" maxOccurs="unbounded" />  
      <xs:element name="Function" type="Function" minOccurs="0" maxOccurs="unbounded" />  
    </xs:sequence>  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Provider" type="xs:string" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Table">  
    <xs:sequence>  
      <xs:element name="Type" type="Type" minOccurs="1" maxOccurs="1" />  
    </xs:sequence>  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Member" type="xs:string" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Type">  
    <xs:sequence>  
      <xs:choice minOccurs="0" maxOccurs="unbounded">  
        <xs:element name="Column" type="Column" minOccurs="0" maxOccurs="unbounded" />  
        <xs:element name="Association" type="Association" minOccurs="0" maxOccurs="unbounded" />  
      </xs:choice>  
      <xs:element name="Type" type="Type" minOccurs="0" maxOccurs="unbounded" />  
    </xs:sequence>  
    <xs:attribute name="Name" type="xs:string" use="required" />  
    <xs:attribute name="InheritanceCode" type="xs:string" use="optional" />  
    <xs:attribute name="IsInheritanceDefault" type="xs:boolean" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Column">  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Member" type="xs:string" use="required" />  
    <xs:attribute name="Storage" type="xs:string" use="optional" />  
    <xs:attribute name="DbType" type="xs:string" use="optional" />  
    <xs:attribute name="IsPrimaryKey" type="xs:boolean" use="optional" />  
    <xs:attribute name="IsDbGenerated" type="xs:boolean" use="optional" />  
    <xs:attribute name="CanBeNull" type="xs:boolean" use="optional" />  
    <xs:attribute name="UpdateCheck" type="UpdateCheck" use="optional" />  
    <xs:attribute name="IsDiscriminator" type="xs:boolean" use="optional" />  
    <xs:attribute name="Expression" type="xs:string" use="optional" />  
    <xs:attribute name="IsVersion" type="xs:boolean" use="optional" />  
    <xs:attribute name="AutoSync" type="AutoSync" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Association">  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Member" type="xs:string" use="required" />  
    <xs:attribute name="Storage" type="xs:string" use="optional" />  
    <xs:attribute name="ThisKey" type="xs:string" use="optional" />  
    <xs:attribute name="OtherKey" type="xs:string" use="optional" />  
    <xs:attribute name="IsForeignKey" type="xs:boolean" use="optional" />  
    <xs:attribute name="IsUnique" type="xs:boolean" use="optional" />  
    <xs:attribute name="DeleteRule" type="xs:string" use="optional" />  
    <xs:attribute name="DeleteOnNull" type="xs:boolean" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Function">  
    <xs:sequence>  
      <xs:element name="Parameter" type="Parameter" minOccurs="0" maxOccurs="unbounded" />  
      <xs:choice>  
        <xs:element name="ElementType" type="Type" minOccurs="0" maxOccurs="unbounded" />  
        <xs:element name="Return" type="Return" minOccurs="0" maxOccurs="1" />  
      </xs:choice>  
    </xs:sequence>  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Method" type="xs:string" use="required" />  
    <xs:attribute name="IsComposable" type="xs:boolean" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Parameter">  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Parameter" type="xs:string" use="required" />  
    <xs:attribute name="DbType" type="xs:string" use="optional" />  
    <xs:attribute name="Direction" type="ParameterDirection" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Return">  
    <xs:attribute name="DbType" type="xs:string" use="optional" />  
  </xs:complexType>  
  <xs:simpleType name="UpdateCheck">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="Always" />  
      <xs:enumeration value="Never" />  
      <xs:enumeration value="WhenChanged" />  
    </xs:restriction>  
  </xs:simpleType>  
  <xs:simpleType name="ParameterDirection">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="In" />  
      <xs:enumeration value="Out" />  
      <xs:enumeration value="InOut" />  
    </xs:restriction>  
  </xs:simpleType>  
  <xs:simpleType name="AutoSync">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="Never" />  
      <xs:enumeration value="OnInsert" />  
      <xs:enumeration value="OnUpdate" />  
      <xs:enumeration value="Always" />  
      <xs:enumeration value="Default" />  
    </xs:restriction>  
  </xs:simpleType>  
</xs:schema>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Codegenerierung in LINQ to SQL](code-generation-in-linq-to-sql.md)
- [Verweis](reference.md)
- [Vorgehensweise: Generieren des Objektmodells als externe Datei](how-to-generate-the-object-model-as-an-external-file.md)
