---
title: Ableiten von Spalten
ms.date: 03/30/2017
ms.assetid: 0e022699-c922-454c-93e2-957dd7e7247a
ms.openlocfilehash: 45d27b78b5d83d333c16192e172e7b7e3dd88c10
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164700"
---
# <a name="inferring-columns"></a>Ableiten von Spalten

Nachdem von ADO.NET anhand eines XML-Dokuments ermittelt wurde, welche Elemente als Tabellen für ein <xref:System.Data.DataSet>-Objekt abgeleitet werden sollen, werden die Spalten für diese Tabellen abgeleitet. ADO.NET 2,0 hat eine neue Rückschluss-Engine eingeführt, die einen stark typisierten Datentyp für jedes **simpleType** -Element ableitet. In früheren Versionen war der Datentyp eines abgeleitet **simpleType** -Elements immer " **xsd: String**".  
  
## <a name="migration-and-backward-compatibility"></a>Migration und Abwärtskompatibilität  

 Die "read **XML** "-Methode nimmt ein Argument vom Typ " **InferSchema**" an. Mit diesem Argument können Sie das mit vorherigen Versionen kompatible Herleitungsverhalten angeben. In der folgenden Tabelle sind die verfügbaren Werte für die **InferSchema** -Enumeration aufgeführt.  
  
 <xref:System.Data.XmlReadMode.InferSchema>  
 Stellt Abwärtskompatibilität bereit, indem immer ein einfacher Typ als <xref:System.String> hergeleitet wird.  
  
 <xref:System.Data.XmlReadMode.InferTypedSchema>  
 Leitet einen Datentyp mit strikter Typbindung her. Löst bei der Verwendung mit einer <xref:System.Data.DataTable> eine Ausnahme aus.  
  
 <xref:System.Data.XmlReadMode.IgnoreSchema>  
 Ignoriert alle Inlineschemata und liest Daten in das vorhandene <xref:System.Data.DataSet>-Schema ein.  
  
## <a name="attributes"></a>Attributes  

 Wie in [ableiten von Tabellen](inferring-tables.md)definiert, wird ein Element mit Attributen als Tabelle abgeleitet. Die Attribute dieses Elements werden anschließend als Spalten für die entsprechende Tabelle hergeleitet. Die **ColumnMapping** -Eigenschaft der Spalten wird auf **MappingType. Attribute**festgelegt, um sicherzustellen, dass die Spaltennamen als Attribute geschrieben werden, wenn das Schema in XML zurückgeschrieben wird. Die Werte der Attribute werden in einer Tabellenzeile gespeichert. Betrachten Sie beispielsweise den folgenden XML-Code:  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 Der Rückschluss Prozess erzeugt eine Tabelle mit dem Namen **Element1** mit zwei Spalten: **attr1** und **attr2**. Die **ColumnMapping** -Eigenschaft der beiden Spalten wird auf **MappingType. Attribute**festgelegt.  
  
 **DataSet:** DocumentElement  
  
 **Tabelle:** Element1  
  
|attr1|attr2|  
|-----------|-----------|  
|value1|value2|  
  
## <a name="elements-without-attributes-or-child-elements"></a>Elemente ohne Attribute oder untergeordnete Elemente  

 Ein Element ohne untergeordnete Elemente oder Attribute wird als Spalte hergeleitet. Die **ColumnMapping** -Eigenschaft der Spalte wird auf **MappingType. Element**festgelegt. Der Text der untergeordneten Elemente wird in einer Tabellenzeile gespeichert. Betrachten Sie beispielsweise den folgenden XML-Code:  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 Der Rückschluss Prozess erzeugt eine Tabelle mit dem Namen **Element1** mit zwei Spalten: **ChildElement1** und **ChildElement2**. Die **ColumnMapping** -Eigenschaft der beiden Spalten wird auf **MappingType. Element**festgelegt.  
  
 **DataSet:** DocumentElement  
  
 **Tabelle:** Element1  
  
|ChildElement1|ChildElement2|  
|-------------------|-------------------|  
|Text1|Text2|  
  
## <a name="see-also"></a>Weitere Informationen

- [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema](inferring-dataset-relational-structure-from-xml.md)
- [Laden eines "DataSets" aus XML](loading-a-dataset-from-xml.md)
- [Laden von DataSet-Schemainformationen aus XML](loading-dataset-schema-information-from-xml.md)
- [Using XML in a DataSet (Verwenden von XML in einem DataSet)](using-xml-in-a-dataset.md)
- ["DataSets", "DataTables" und "DataViews"](index.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
