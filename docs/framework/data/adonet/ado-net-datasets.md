---
title: DataSets
description: Erfahren Sie mehr über DataSet, eine Speicher residente Datendarstellung, die unabhängig von der Datenquelle in ADO.net ein konsistentes relationales Programmiermodell bereitstellt.
ms.date: 03/30/2017
ms.assetid: 82b641bb-6001-4512-bf1a-2830acdd92ab
ms.openlocfilehash: d78918773c3cc88d8a925788d81cdafdc0a2db27
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153585"
---
# <a name="adonet-datasets"></a>ADO.NET-DataSets

Das- <xref:System.Data.DataSet> Objekt ist für die Unterstützung von getrennten, verteilten Daten Szenarien mit ADO.net von zentraler Bedeutung. Das **DataSet** ist eine Speicher residente Darstellung von Daten, die unabhängig von der Datenquelle ein konsistentes relationales Programmiermodell bereitstellt. Es kann mit mehreren und unterschiedlichen Datenquellen, mit XML-Daten oder zum Verwalten lokaler Anwendungsdaten verwendet werden. Das **DataSet** stellt einen kompletten Satz von Daten dar, einschließlich verknüpfter Tabellen, Einschränkungen und Beziehungen zwischen den Tabellen. Die folgende Abbildung zeigt das **DataSet** -Objektmodell.  
  
 ![ADO.Net](./media/ado-1-bpuedev11.png "ado_1_bpuedev11")  
DataSet-Objektmodell  
  
 Die Methoden und Objekte in einem **DataSet** sind mit denen im relationalen Datenbankmodell konsistent.  
  
 Das **DataSet** kann seine Inhalte auch beibehalten und als XML-Datei und das zugehörige Schema als XSD-Schema (XML Schema Definition Language) erneut laden. Weitere Informationen finden Sie unter [Using XML in a DataSet (Verwenden von XML in einem DataSet)](./dataset-datatable-dataview/using-xml-in-a-dataset.md).  
  
## <a name="the-datatablecollection"></a>Die "DataTableCollection"  

 Ein ADO.net- **DataSet** enthält eine Auflistung von NULL oder mehr Tabellen, die durch-Objekte dargestellt werden <xref:System.Data.DataTable> . Der <xref:System.Data.DataTableCollection> enthält alle **Daten** Tabelle in einem **DataSet**.  
  
 Eine **Daten** Tabelle ist im <xref:System.Data> -Namespace definiert und stellt eine einzelne Tabelle mit Speicher Residenten Daten dar. Sie enthält eine Auflistung mit Spalten, die durch eine <xref:System.Data.DataColumnCollection> dargestellt werden, sowie Einschränkungen, die durch eine <xref:System.Data.ConstraintCollection> dargestellt werden. Gemeinsam definieren sie das Schema der Tabelle. Eine **Daten** Tabelle enthält auch eine Auflistung von Zeilen, die von dargestellt <xref:System.Data.DataRowCollection> werden, die die Daten in der Tabelle enthält. Eine <xref:System.Data.DataRow> behält nicht nur den aktuellen Status, sondern auch die aktuelle und die ursprüngliche Version bei, um Änderungen an den in der Zeile gespeicherten Werten feststellen zu können.  
  
## <a name="the-dataview-class"></a>Die DataView-Klasse  

 Mit einer <xref:System.Data.DataView> können Sie verschiedene Ansichten der in einer <xref:System.Data.DataTable> gespeicherten Daten erstellen. Diese Funktion wird oft in Datenbindungsanwendungen verwendet. Mit einer <xref:System.Data.DataView> können Sie die Daten in einer Tabelle mit verschiedenen Sortierreihenfolgen verfügbar machen und nach Zeilenstatus oder auf der Basis eines Filterausdrucks filtern. Weitere Informationen finden Sie unter ["DataViews"](./dataset-datatable-dataview/dataviews.md).  
  
## <a name="the-datarelationcollection"></a>Die "DataRelationCollection"  

 Ein **DataSet** enthält Beziehungen in seinem- <xref:System.Data.DataRelationCollection> Objekt. Eine Beziehung, die durch das-Objekt dargestellt wird <xref:System.Data.DataRelation> , ordnet Zeilen in einer **Daten** Tabelle Zeilen in einer anderen **Datentabelle**zu. Eine Beziehung entspricht einem Joinpfad, der u. U. zwischen Primärschlüssel- und Fremdschlüsselspalten in einer relationalen Datenbank vorhanden ist. Eine **DataRelations** identifiziert übereinstimmende Spalten in zwei Tabellen eines **DataSets**.  
  
 Beziehungen ermöglichen die Navigation von einer Tabelle zu einer anderen in einem **DataSet**. Die wesentlichen Elemente einer **DataRelations** sind der Name der Beziehung, der Name der verknüpften Tabellen und die zugehörigen Spalten in den einzelnen Tabellen. Beziehungen können mit mehreren Spalten pro Tabelle erstellt werden, indem ein Array mit <xref:System.Data.DataColumn>-Objekten als Schlüsselspalten angegeben wird. Wenn Sie eine Beziehung hinzufügen <xref:System.Data.DataRelationCollection> , können Sie optional eine **uniquekeyeinschränkung** und eine fremd **Schlüssel Einschränkung** hinzufügen, um Integritäts Einschränkungen zu erzwingen, wenn Änderungen an verknüpften Spaltenwerten vorgenommen werden.  
  
 Weitere Informationen finden Sie unter [Hinzufügen von DataRelations](./dataset-datatable-dataview/adding-datarelations.md).  
  
## <a name="xml"></a>XML  

 Sie können ein **DataSet** aus einem XML-Stream oder einem XML-Dokument füllen. Sie können den XML-Stream oder das XML-Dokument verwenden, um Daten, Schema Informationen oder beides für das **DataSet** bereitzustellen. Die aus dem XML-Stream oder dem XML-Dokument bereitgestellten Informationen können mit vorhandenen Daten oder Schema Informationen kombiniert werden, die bereits im **DataSet**vorhanden sind. Weitere Informationen finden Sie unter [Using XML in a DataSet (Verwenden von XML in einem DataSet)](./dataset-datatable-dataview/using-xml-in-a-dataset.md).  
  
## <a name="extendedproperties"></a>ExtendedProperties  

 Das **DataSet**, die **Daten**Tabelle und die **datacolenn** verfügen über eine **ExtendedProperties** -Eigenschaft. **ExtendedProperties** ist eine **PropertyCollection** , in der Sie benutzerdefinierte Informationen platzieren können, wie z. b. die SELECT-Anweisung, die zum Generieren des Resultsets verwendet wurde, oder den Zeitpunkt, zu dem die Daten generiert wurden. Die **ExtendedProperties** -Auflistung wird mit den Schema Informationen für das **DataSet**persistent gespeichert.  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  

 LINQ to DataSet bietet sprach integrierte Abfragefunktionen für in einem DataSet gespeicherte, nicht verbundene Daten. LINQ to DataSet verwendet die LINQ-Standard Syntax und bietet Syntax Überprüfung zur Kompilierzeit, statische Typisierung und IntelliSense-Unterstützung, wenn Sie die Visual Studio-IDE verwenden.  
  
 Weitere Informationen finden Sie unter [LINQ to DataSet](linq-to-dataset.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über ADO.NET](ado-net-overview.md)
- ["DataSets", "DataTables" und "DataViews"](./dataset-datatable-dataview/index.md)
- [Abrufen und Ändern von Daten in ADO.NET](retrieving-and-modifying-data.md)
