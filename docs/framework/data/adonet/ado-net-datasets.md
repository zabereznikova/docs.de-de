---
title: "ADO.NET-DataSets | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 82b641bb-6001-4512-bf1a-2830acdd92ab
caps.latest.revision: 6
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 6
---
# ADO.NET-DataSets
Die <xref:System.Data.DataSet> Objekt ist für die Unterstützung getrennter, verteilter Datenszenarien mit [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]. Die **DataSet** ist eine speicherresidente Darstellung von Daten, die ein konsistentes relationales Programmiermodell unabhängig von der Datenquelle enthält. Es kann mit mehreren und unterschiedlichen Datenquellen, mit XML-Daten oder zum Verwalten lokaler Anwendungsdaten verwendet werden. Die **DataSet** stellt einen vollständigen Satz von Daten, einschließlich verknüpfter Tabellen, Einschränkungen und Beziehungen zwischen Tabellen dar. Die folgende Abbildung zeigt die **DataSet** -Objektmodell.  
  
 ![ADO.NET-Grafik](../../../../docs/framework/data/adonet/media/ado-1-bpuedev11.png "ado_1_bpuedev11")  
DataSet-Objektmodell  
  
 Die Methoden und Objekte in einer **DataSet** sind mit denen des relationalen Datenbankmodells konsistent.  
  
 Die **DataSet** auch beibehalten werden kann, und Laden Sie den Inhalt als XML und sein Schema als Schema für XML Schema Definition Language (XSD). Weitere Informationen finden Sie unter [mithilfe von XML in einem DataSet](../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).  
  
## <a name="the-datatablecollection"></a>Die "DataTableCollection"  
 Ein [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] **DataSet** enthält eine Auflistung von NULL oder mehr Tabellen dargestellte <xref:System.Data.DataTable> Objekte. Die <xref:System.Data.DataTableCollection> enthält alle der **DataTable** Objekte in einem **DataSet**.  
  
 Ein **DataTable** wird definiert, der <xref:System.Data> Namespace und stellt eine einzelne Tabelle mit speicherresistenten Daten dar. Sie enthält eine Auflistung von Spalten, deren ein <xref:System.Data.DataColumnCollection>, und Einschränkungen dargestellt durch eine <xref:System.Data.ConstraintCollection>, die zusammen das Schema der Tabelle definiert. Ein **DataTable** enthält außerdem eine Auflistung von Zeilen dargestellt durch die <xref:System.Data.DataRowCollection>, die die Daten in der Tabelle enthält. Zusammen mit den aktuellen Status eine <xref:System.Data.DataRow> behält seine aktuellen und ursprünglichen Versionen zum Identifizieren von Änderungen an den Werten in der Zeile gespeichert.  
  
## <a name="the-dataview-class"></a>Die DataView-Klasse  
 Ein <xref:System.Data.DataView> können Sie unterschiedliche Ansichten von Daten in einem <xref:System.Data.DataTable>, eine Funktion, die häufig in datenbindungsanwendungen verwendet wird. Mithilfe einer <xref:System.Data.DataView>Sie die Daten in einer Tabelle mit verschiedenen Sortierreihenfolgen verfügbar machen und Sie können die Daten nach Zeilenstatus oder basierend auf einem Filterausdruck filtern. Weitere Informationen finden Sie unter [DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).  
  
## <a name="the-datarelationcollection"></a>Die "DataRelationCollection"  
 Ein **DataSet** enthält Beziehungen in der <xref:System.Data.DataRelationCollection> Objekt. Eine Beziehung, dargestellt durch die <xref:System.Data.DataRelation> Objekt ordnet Zeilen in einer **DataTable** Zeilen in einer anderen **DataTable**. Eine Beziehung entspricht einem Joinpfad, der u. U. zwischen Primärschlüssel- und Fremdschlüsselspalten in einer relationalen Datenbank vorhanden ist. Ein **DataRelation** kennzeichnet übereinstimmende Spalten in zwei Tabellen mit einem **DataSet**.  
  
 Beziehungen ermöglichen das Navigieren von einer Tabelle in eine andere in einer **DataSet**. Die wichtigsten Elemente einer **DataRelation** sind der Name der Beziehung, die Namen der Tabellen erstellt wird und die verknüpften Spalten in jeder Tabelle. Beziehungen können mit mehr als eine Spalte pro Tabelle erstellt werden, durch Angeben eines Arrays von <xref:System.Data.DataColumn> Objekte als Schlüsselspalten. Beim Hinzufügen einer Beziehung zu den <xref:System.Data.DataRelationCollection>, optional können Sie Hinzufügen einer **UniqueKeyConstraint** und **ForeignKeyConstraint** auf bei an verknüpften Spaltenwerten Änderungen integritätseinschränkungen zu erzwingen.  
  
 Weitere Informationen finden Sie unter [DataRelations hinzufügen](../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md).  
  
## <a name="xml"></a>XML  
 Kann ein **DataSet** aus einem XML-Stream oder das Dokument. Können Sie die XML-Stream oder das Dokument zum Angeben der **DataSet** Daten oder Schemainformationen oder beides. Die Informationen aus der XML-Stream oder das Dokument kann kombiniert werden, mit vorhandenen Daten oder Schemainformationen, die bereits im der **DataSet**. Weitere Informationen finden Sie unter [mithilfe von XML in einem DataSet](../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).  
  
## <a name="extendedproperties"></a>ExtendedProperties  
 Die **DataSet**, **DataTable**, und **DataColumn** verfügen alle über ein **ExtendedProperties** Eigenschaft. **ExtendedProperties** ist ein **PropertyCollection** platzieren können Sie benutzerdefinierte Informationen, z. B. die SELECT-Anweisung, die zum Erstellen des Resultsets verwendet wurde oder die Uhrzeit, die Daten generiert wurde. Die **ExtendedProperties** Sammlung wird gespeichert, die Schemainformationen für die **DataSet**.  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] bietet LINQ-Funktionen für in einem Dataset gespeicherte nicht verbundene Daten. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]verwendet standardmäßige [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] Syntax und Kompilierzeit-Syntax zu überprüfen, statische Typisierung und IntelliSense-Unterstützung bietet, bei der Verwendung der [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] IDE.  
  
 Weitere Informationen finden Sie unter [LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über ADO.NET](../../../../docs/framework/data/adonet/ado-net-overview.md)   
 [DataSets, "DataTables" und "DataViews"](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Abrufen und Ändern von Daten in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [ADO.NET verwaltete Anbieter und DataSet-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)