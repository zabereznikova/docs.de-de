---
title: "&#39;DataTable&#39;-Schemadefinition | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: efbcdda4-f5a9-421d-8be2-4c194c74552f
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# &#39;DataTable&#39;-Schemadefinition
Das Schema oder die Struktur einer Tabelle wird durch Spalten und Einschränkungen dargestellt.  Das Schema einer <xref:System.Data.DataTable> wird mit <xref:System.Data.DataColumn>\-Objekten sowie <xref:System.Data.ForeignKeyConstraint>\-Objekten und <xref:System.Data.UniqueConstraint>\-Objekten definiert.  Die Spalten einer Tabelle können Spalten in einer Datenquelle zugeordnet sein, berechnete Werte aus Ausdrücken enthalten, Werte automatisch erhöhen oder primäre Schlüsselwerte enthalten.  
  
 Bei Verweisen auf Namen von Spalten, Beziehungen und Einschränkungen in einer Tabelle muss die Groß\- und Kleinschreibung berücksichtigt werden.  Folglich können zwei oder mehr Spalten, Beziehungen oder Einschränkungen in einer Tabelle vorhanden sein, die den gleichen Namen in unterschiedlicher Schreibweise aufweisen.  Zum Beispiel kann **Col1** und **col1** vorkommen.  In diesem Fall muss die Schreibweise des Verweises auf eine der Spalten genau mit der Schreibweise des Namens der Spalte übereinstimmen. Andernfalls wird eine Ausnahme ausgelöst.  Wenn beispielsweise die Tabelle **myTable** die Spalten **Col1** und **col1** enthält, muss der Verweis auf den Namen **Col1** **myTable.Columns\["Col1"\]** lauten, und der Verweis auf den Namen **col1** muss **myTable.Columns\["col1"\]** lauten.  Es wird eine Ausnahme ausgelöst, wenn versucht wird, auf eine der Spalten durch **myTable.Columns\["COL1"\]** zu verweisen.  
  
 Die Groß\- und Kleinschreibung muss nicht berücksichtigt werden, wenn jeweils nur eine Spalte, Beziehung oder Einschränkung einen bestimmten Namen aufweist.  Das bedeutet, wenn kein anderes Spalten\-, Beziehungs\- oder Einschränkungsobjekt in der Tabelle mit dem Namen dieses bestimmten Spalten\-, Beziehungs\- oder Einschränkungsobjekts übereinstimmt, muss die Groß\- und Kleinschreibung bei dem Verweis auf das Objekt nicht berücksichtigt werden, und es wird keine Ausnahme ausgelöst.  Wenn beispielsweise die Tabelle nur **Col1** aufweist, kann durch **my.Columns\["COL1"\]** darauf verwiesen werden.  
  
> [!NOTE]
>  Die <xref:System.Data.DataTable.CaseSensitive%2A>\-Eigenschaft der **DataTable** hat keine Auswirkungen auf dieses Verhalten.  Die **CaseSensitive**\-Eigenschaft gilt für die Daten in der Tabelle und hat Auswirkungen auf das Sortieren, Suchen, Filtern, Erzwingen von Einschränkungen usw., aber nicht auf Verweise auf Spalten, Beziehungen und Einschränkungen.  
  
## In diesem Abschnitt  
 [Hinzufügen von Spalten zu einer 'DataTable'](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-columns-to-a-datatable.md)  
 Beschreibt, wie die Spalten einer Tabelle mit **DataColumn**\-Objekten definiert werden.  
  
 [Erstellen von Ausdrucksspalten](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-expression-columns.md)  
 Erläutert, wie die **Expression**\-Eigenschaft einer Spalte zum Berechnen von Werten basierend auf den Werten aus anderen Spalten in einer Zeile verwendet werden kann.  
  
 [Erstellen von AutoIncrement\-Spalten](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md)  
 Beschreibt, wie eine Spalte so festgelegt werden kann, dass die numerischen Werte automatisch erhöht werden, um sicherzustellen, dass die Werte in einer Spalte eindeutig sind.  
  
 [Definieren von Primärschlüsseln](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md)  
 Beschreibt, wie der Primärschlüssel einer Tabelle aus ein oder mehreren **DataColumn**\-Objekten angegeben wird.  
  
 ['DataTable'\-Einschränkungen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md)  
 Beschreibt, wie Fremdschlüsseleinschränkungen und eindeutige Einschränkungen für Spalten in einer Tabelle definiert werden.  
  
## Siehe auch  
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)