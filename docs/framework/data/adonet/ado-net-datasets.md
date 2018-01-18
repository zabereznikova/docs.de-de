---
title: ADO.NET-DataSets
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 82b641bb-6001-4512-bf1a-2830acdd92ab
caps.latest.revision: "6"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: b9d566f99802ea80ae73132579bb3068b1ff3b28
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="adonet-datasets"></a>ADO.NET-DataSets
Das <xref:System.Data.DataSet>-Objekt spielt für die Unterstützung getrennter, verteilter Datenszenarien mit [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] eine zentrale Rolle. Die **DataSet** ist eine speicherresidente Darstellung von Daten, auf denen ein konsistentes relationales Programmiermodell unabhängig von der Datenquelle. Es kann mit mehreren und unterschiedlichen Datenquellen, mit XML-Daten oder zum Verwalten lokaler Anwendungsdaten verwendet werden. Die **DataSet** stellt einen vollständigen Satz von Daten, einschließlich verknüpfter Tabellen, Einschränkungen und Beziehungen zwischen Tabellen dar. Die folgende Abbildung zeigt die **DataSet** -Objektmodell.  
  
 ![ADO.Net graphic](../../../../docs/framework/data/adonet/media/ado-1-bpuedev11.png "ado_1_bpuedev11")  
DataSet-Objektmodell  
  
 Die Methoden und Objekte in einem **DataSet** sind mit denen des relationalen Datenbankmodells konsistent.  
  
 Die **DataSet** können auch beibehalten und aktualisiert seinen Inhalt als XML und sein Schema als Schema für XML Schema Definition Language (XSD). Weitere Informationen finden Sie unter [Using XML in a DataSet (Verwenden von XML in einem DataSet)](../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).  
  
## <a name="the-datatablecollection"></a>Die "DataTableCollection"  
 Ein [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] **DataSet** enthält eine Auflistung von NULL oder mehr Tabellen dargestellte <xref:System.Data.DataTable> Objekte. Die <xref:System.Data.DataTableCollection> enthält alle der **DataTable** Objekte in einem **DataSet**.  
  
 Ein **DataTable** wird definiert, der <xref:System.Data> Namespace und stellt eine einzelne Tabelle mit speicherresistenten Daten dar. Sie enthält eine Auflistung mit Spalten, die durch eine <xref:System.Data.DataColumnCollection> dargestellt werden, sowie Einschränkungen, die durch eine <xref:System.Data.ConstraintCollection> dargestellt werden. Gemeinsam definieren sie das Schema der Tabelle. Ein **DataTable** enthält auch eine Auflistung von Zeilen dargestellt durch die <xref:System.Data.DataRowCollection>, die die Daten in der Tabelle enthält. Eine <xref:System.Data.DataRow> behält nicht nur den aktuellen Status, sondern auch die aktuelle und die ursprüngliche Version bei, um Änderungen an den in der Zeile gespeicherten Werten feststellen zu können.  
  
## <a name="the-dataview-class"></a>Die DataView-Klasse  
 Mit einer <xref:System.Data.DataView> können Sie verschiedene Ansichten der in einer <xref:System.Data.DataTable> gespeicherten Daten erstellen. Diese Funktion wird oft in Datenbindungsanwendungen verwendet. Mit einer <xref:System.Data.DataView> können Sie die Daten in einer Tabelle mit verschiedenen Sortierreihenfolgen verfügbar machen und nach Zeilenstatus oder auf der Basis eines Filterausdrucks filtern. Weitere Informationen finden Sie unter ["DataViews"](../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).  
  
## <a name="the-datarelationcollection"></a>Die "DataRelationCollection"  
 Ein **DataSet** enthält Beziehungen in seiner <xref:System.Data.DataRelationCollection> Objekt. Eine Beziehung, dargestellt durch die <xref:System.Data.DataRelation> Objekt ordnet Zeilen in einer **DataTable** Zeilen in einer anderen **DataTable**. Eine Beziehung entspricht einem Joinpfad, der u. U. zwischen Primärschlüssel- und Fremdschlüsselspalten in einer relationalen Datenbank vorhanden ist. Ein **DataRelation** kennzeichnet übereinstimmende Spalten in zwei Tabellen mit einem **DataSet**.  
  
 Beziehungen ermöglichen das Navigieren von einer Tabelle in eine andere in einer **DataSet**. Die wichtigsten Elemente der eine **DataRelation** sind der Name der Beziehung, die den Namen der Tabellen wird und die verknüpften Spalten in jeder Tabelle. Beziehungen können mit mehreren Spalten pro Tabelle erstellt werden, indem ein Array mit <xref:System.Data.DataColumn>-Objekten als Schlüsselspalten angegeben wird. Beim Hinzufügen einer Beziehung zu den <xref:System.Data.DataRelationCollection>, optional können Sie Hinzufügen einer **UniqueKeyConstraint** und ein **ForeignKeyConstraint** integritätseinschränkungen zu erzwingen, wenn Änderungen an verknüpften Spalte vorgenommen werden Werte.  
  
 Weitere Informationen finden Sie unter [Hinzufügen von "DataRelations"](../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md).  
  
## <a name="xml"></a>XML  
 Sie können ggf. eine **DataSet** aus einer XML-Stream oder das Dokument. Können Sie die XML-Stream oder das Dokument zum Angeben der **DataSet** Daten, Schemainformationen oder beides. Die bereitgestellten aus des XML-Streams oder-Dokuments können kombiniert werden mit vorhandenen Daten oder Schemainformationen, die bereits im die **DataSet**. Weitere Informationen finden Sie unter [Using XML in a DataSet (Verwenden von XML in einem DataSet)](../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).  
  
## <a name="extendedproperties"></a>ExtendedProperties  
 Die **DataSet**, **DataTable**, und **DataColumn** alle verfügen über eine **"ExtendedProperties"** Eigenschaft. **Die "ExtendedProperties"** ist ein **PropertyCollection** platzieren können Sie benutzerdefinierte Informationen, z. B. die SELECT-Anweisung, die zum Erstellen des Resultsets verwendet wurde, oder die Uhrzeit, die Daten generiert wurde. Die **"ExtendedProperties"** Auflistung wird beibehalten, mit den Schemainformationen für die **DataSet**.  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] bietet LINQ-Funktionen für in einem Dataset gespeicherte nicht verbundene Daten. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]verwendet Standard [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] Syntax und bietet syntaxüberprüfung der Zeitpunkt der Kompilierung, statische Typisierung und IntelliSense-Unterstützung, wenn Sie die [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] IDE.  
  
 Weitere Informationen finden Sie unter [LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über ADO.NET](../../../../docs/framework/data/adonet/ado-net-overview.md)  
 [DataSets, DataTables und DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Abrufen und Ändern von Daten in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
