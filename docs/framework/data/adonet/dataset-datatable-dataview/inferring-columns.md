---
title: Ableiten von Spalten
ms.date: 03/30/2017
ms.assetid: 0e022699-c922-454c-93e2-957dd7e7247a
ms.openlocfilehash: 56de4b4d6cf704473ec46957625ad1c376f595c2
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43891352"
---
# <a name="inferring-columns"></a>Ableiten von Spalten
Nachdem von ADO.NET anhand eines XML-Dokuments ermittelt wurde, welche Elemente als Tabellen für ein <xref:System.Data.DataSet>-Objekt abgeleitet werden sollen, werden die Spalten für diese Tabellen abgeleitet. Neu in ADO.NET 2.0 eingeführt, eine neues Schema Rückschluss-Engine, die einen stark typisierten Datentyp für jede herleitet **SimpleType** Element. In früheren Versionen der Datentyp eines hergeleiteten **SimpleType** Element wurde immer **xsd: String**.  
  
## <a name="migration-and-backward-compatibility"></a>Migration und Abwärtskompatibilität  
 Die **ReadXml** Methode akzeptiert ein Argument des Typs **InferSchema**. Mit diesem Argument können Sie das mit vorherigen Versionen kompatible Herleitungsverhalten angeben. Die verfügbaren Werte für die **InferSchema** Enumeration in der folgenden Tabelle dargestellt werden.  
  
 <xref:System.Data.XmlReadMode.InferSchema>  
 Stellt Abwärtskompatibilität bereit, indem immer ein einfacher Typ als <xref:System.String> hergeleitet wird.  
  
 <xref:System.Data.XmlReadMode.InferTypedSchema>  
 Leitet einen Datentyp mit strikter Typbindung her. Löst bei der Verwendung mit einer <xref:System.Data.DataTable> eine Ausnahme aus.  
  
 <xref:System.Data.XmlReadMode.IgnoreSchema>  
 Ignoriert alle Inlineschemata und liest Daten in das vorhandene <xref:System.Data.DataSet>-Schema ein.  
  
## <a name="attributes"></a>Attribute  
 Gemäß [Herleiten von Tabellen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-tables.md), wird ein Element mit Attributen als Tabelle hergeleitet werden. Die Attribute dieses Elements werden anschließend als Spalten für die entsprechende Tabelle hergeleitet. Die **ColumnMapping** -Eigenschaft der Spalten auf festgelegt **MappingType.Attribute**, um sicherzustellen, dass die Spaltennamen werden als Attribute geschrieben werden, wenn das Schema in XML zurückgeschrieben wird. Die Werte der Attribute werden in einer Tabellenzeile gespeichert. Betrachten Sie beispielsweise den folgenden XML-Code:  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 Die Herleitung wird einer Tabelle namens **Element1** mit zwei Spalten, **attr1** und **attr2**. Die **ColumnMapping** -Eigenschaft der beiden Spalten wird festgelegt **MappingType.Attribute**.  
  
 **DataSet:** DocumentElement  
  
 **Tabelle:** Element1  
  
|attr1|attr2|  
|-----------|-----------|  
|value1|value2|  
  
## <a name="elements-without-attributes-or-child-elements"></a>Elemente ohne Attribute oder untergeordnete Elemente  
 Ein Element ohne untergeordnete Elemente oder Attribute wird als Spalte hergeleitet. Die **ColumnMapping** -Eigenschaft der Spalte auf festgelegt **MappingType.Element**. Der Text der untergeordneten Elemente wird in einer Tabellenzeile gespeichert. Betrachten Sie beispielsweise den folgenden XML-Code:  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 Die Herleitung wird einer Tabelle namens **Element1** mit zwei Spalten, **ChildElement1** und **ChildElement2**. Die **ColumnMapping** -Eigenschaft der beiden Spalten wird festgelegt **MappingType.Element**.  
  
 **DataSet:** DocumentElement  
  
 **Tabelle:** Element1  
  
|ChildElement1|ChildElement2|  
|-------------------|-------------------|  
|Text1|Text2|  
  
## <a name="see-also"></a>Siehe auch  
 [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [Laden eines DataSet aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [Laden von DataSet-Schemainformationen aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [Using XML in a DataSet (Verwenden von XML in einem DataSet)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
