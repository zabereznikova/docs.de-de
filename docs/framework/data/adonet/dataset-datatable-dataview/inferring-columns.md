---
title: "Herleiten von Spalten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0e022699-c922-454c-93e2-957dd7e7247a
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Herleiten von Spalten
Nachdem von ADO.NET anhand eines XML\-Dokuments ermittelt wurde, welche Elemente als Tabellen für ein <xref:System.Data.DataSet>\-Objekt abgeleitet werden sollen, werden die Spalten für diese Tabellen abgeleitet.  ADO.NET 2.0 enthielt ein neues Modul für Schemaherleitungen, das für jedes **simpleType**\-Element einen Datentyp mit starker Typbindung herleitet.  In vorherigen Versionen war der Datentyp eines hergeleiteten **simpleType**\-Elements immer **xsd:string**.  
  
## Migration und Abwärtskompatibilität  
 Die **ReadXml**\-Methode verwendet ein Argument vom Typ **InferSchema**.  Mit diesem Argument können Sie das mit vorherigen Versionen kompatible Herleitungsverhalten angeben.  Die für die **InferSchema**\-Enumeration verfügbaren Werte werden in der folgenden Tabelle dargestellt.  
  
 <xref:System.Data.XmlReadMode>  
 Stellt Abwärtskompatibilität bereit, indem immer ein einfacher Typ als <xref:System.String> hergeleitet wird.  
  
 <xref:System.Data.XmlReadMode>  
 Leitet einen Datentyp mit strikter Typbindung her.  Löst bei der Verwendung mit einer <xref:System.Data.DataTable> eine Ausnahme aus.  
  
 <xref:System.Data.XmlReadMode>  
 Ignoriert alle Inlineschemata und liest Daten in das vorhandene <xref:System.Data.DataSet>\-Schema ein.  
  
## Attribute  
 Wie unter [Herleiten von Tabellen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-tables.md) definiert, wird ein Element mit Attributen als Tabelle hergeleitet.  Die Attribute dieses Elements werden anschließend als Spalten für die entsprechende Tabelle hergeleitet.  Für die **ColumnMapping**\-Eigenschaft der Spalten wird **MappingType.Attribute** festgelegt, damit die Spaltennamen als Attribute geschrieben werden, falls das Schema wieder in XML zurückgeschrieben wird.  Die Werte der Attribute werden in einer Tabellenzeile gespeichert.  Betrachten Sie beispielsweise den folgenden XML\-Code:  
  
```  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 Durch die Herleitung wird eine Tabelle mit dem Namen **Element1** und den zwei Spalten **attr1** und **attr2** erstellt.  Die **ColumnMapping**\-Eigenschaft der beiden Spalten wird auf **MappingType.Attribute** festgelegt.  
  
 **DataSet:** DocumentElement  
  
 **Tabelle:** Element1  
  
|attr1|attr2|  
|-----------|-----------|  
|value1|value2|  
  
## Elemente ohne Attribute oder untergeordnete Elemente  
 Ein Element ohne untergeordnete Elemente oder Attribute wird als Spalte hergeleitet.  Die **ColumnMapping**\-Eigenschaft der Spalte wird auf **MappingType.Element** festgelegt.  Der Text der untergeordneten Elemente wird in einer Tabellenzeile gespeichert.  Betrachten Sie beispielsweise den folgenden XML\-Code:  
  
```  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 Durch die Herleitung wird eine Tabelle mit dem Namen **Element1** und den zwei Spalten **ChildElement1** und **ChildElement2** erstellt.  Die **ColumnMapping**\-Eigenschaft der beiden Spalten wird auf **MappingType.Element** festgelegt.  
  
 **DataSet:** DocumentElement  
  
 **Tabelle:** Element1  
  
|ChildElement1|ChildElement2|  
|-------------------|-------------------|  
|Text1|Text2|  
  
## Siehe auch  
 [Herleiten der relationalen DataSet\-Struktur aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)   
 [Laden eines DataSet aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)   
 [Laden von DataSet\-Schemainformationen aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)   
 [Verwenden von XML in einem DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)