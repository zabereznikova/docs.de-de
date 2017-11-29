---
title: Ableiten von Spalten
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0e022699-c922-454c-93e2-957dd7e7247a
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: ba06bce55db53de1da1c07d2a6451d5664fa23bf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="inferring-columns"></a>Ableiten von Spalten
Nachdem von ADO.NET anhand eines XML-Dokuments ermittelt wurde, welche Elemente als Tabellen für ein <xref:System.Data.DataSet>-Objekt abgeleitet werden sollen, werden die Spalten für diese Tabellen abgeleitet. Neu in ADO.NET 2.0 eingeführt, ein neues Schema inferenzmodul, die einen stark typisierten Datentyp für jede leitet **SimpleType** Element. In früheren Versionen der Datentyp eines hergeleiteten **SimpleType** handelte es sich immer **xsd: String**.  
  
## <a name="migration-and-backward-compatibility"></a>Migration und Abwärtskompatibilität  
 Die **ReadXml** -Methode akzeptiert ein Argument des Typs **InferSchema**. Mit diesem Argument können Sie das mit vorherigen Versionen kompatible Herleitungsverhalten angeben. Die verfügbaren Werte für die **InferSchema** Enumeration in der folgenden Tabelle dargestellt sind.  
  
 <xref:System.Data.XmlReadMode.InferSchema>  
 Stellt Abwärtskompatibilität bereit, indem immer ein einfacher Typ als <xref:System.String> hergeleitet wird.  
  
 <xref:System.Data.XmlReadMode.InferTypedSchema>  
 Leitet einen Datentyp mit strikter Typbindung her. Löst bei der Verwendung mit einer <xref:System.Data.DataTable> eine Ausnahme aus.  
  
 <xref:System.Data.XmlReadMode.IgnoreSchema>  
 Ignoriert alle Inlineschemata und liest Daten in das vorhandene <xref:System.Data.DataSet>-Schema ein.  
  
## <a name="attributes"></a>Attribute  
 Gemäß [Herleiten von Tabellen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-tables.md), ein Element mit Attributen als Tabelle hergeleitet. Die Attribute dieses Elements werden anschließend als Spalten für die entsprechende Tabelle hergeleitet. Die **ColumnMapping** Eigenschaft der Spalten wird festgelegt **MappingType.Attribute**, um sicherzustellen, dass die Spaltennamen als Attribute geschrieben werden, wenn das Schema in XML zurückgeschrieben wird. Die Werte der Attribute werden in einer Tabellenzeile gespeichert. Betrachten Sie beispielsweise den folgenden XML-Code:  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 Die Herleitung wird einer Tabelle namens **Element1** mit zwei Spalten **attr1** und **attr2**. Die **ColumnMapping** -Eigenschaft der beiden Spalten wird auf festgelegt **MappingType.Attribute**.  
  
 **DataSet:** DocumentElement  
  
 **Table:** Element1  
  
|attr1|attr2|  
|-----------|-----------|  
|value1|value2|  
  
## <a name="elements-without-attributes-or-child-elements"></a>Elemente ohne Attribute oder untergeordnete Elemente  
 Ein Element ohne untergeordnete Elemente oder Attribute wird als Spalte hergeleitet. Die **ColumnMapping** -Eigenschaft der Spalte wird auf festgelegt **MappingType.Element**. Der Text der untergeordneten Elemente wird in einer Tabellenzeile gespeichert. Betrachten Sie beispielsweise den folgenden XML-Code:  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 Die Herleitung wird einer Tabelle namens **Element1** mit zwei Spalten **ChildElement1** und **ChildElement2**. Die **ColumnMapping** -Eigenschaft der beiden Spalten wird auf festgelegt **MappingType.Element**.  
  
 **DataSet:** DocumentElement  
  
 **Table:** Element1  
  
|ChildElement1|ChildElement2|  
|-------------------|-------------------|  
|Text1|Text2|  
  
## <a name="see-also"></a>Siehe auch  
 [Ableiten von relationalen DataSet-Struktur von XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [Beim Laden eines Datasets aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [Beim Laden von DataSet-Schemainformationen aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [Using XML in a DataSet (Verwenden von XML in einem DataSet)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
