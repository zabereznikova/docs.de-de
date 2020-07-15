---
title: "\"DataSets\", \"DataTables\" und \"DataViews\""
description: Erfahren Sie, wie Sie mit einem ADO.NET-DataSet arbeiten, einer Speicher Residenten Darstellung von Daten, die ein konsistentes relationales Programmiermodell bereitstellt.
ms.date: 03/30/2017
ms.assetid: 6d4c4b69-8919-4224-8a65-6cca1c61b48f
ms.openlocfilehash: 53e12f701b9be1938d62f46bbeb6e63d95c03386
ms.sourcegitcommit: e7748001b1cee80ced691d8a76ca814c0b02dd9b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2020
ms.locfileid: "86374506"
---
# <a name="datasets-datatables-and-dataviews"></a>"DataSets", "DataTables" und "DataViews"

ADO.NET <xref:System.Data.DataSet> ist eine speicherresidente Darstellung von Daten, die – unabhängig von der darin enthaltenen Datenquelle – ein konsistentes relationales Programmiermodell bereitstellt. Ein <xref:System.Data.DataSet> stellt einen kompletten Satz aus Daten dar, einschließlich der Tabellen, die die Daten enthalten, ordnen und einschränken, sowie der Beziehungen zwischen den Tabellen.  
  
Es gibt verschiedene Möglichkeiten, mit einem <xref:System.Data.DataSet> zu arbeiten, die unabhängig voneinander oder kombiniert angewendet werden können. Ihre Möglichkeiten:  
  
- Sie können eine <xref:System.Data.DataTable>, eine <xref:System.Data.DataRelation> und eine <xref:System.Data.Constraint> innerhalb eines <xref:System.Data.DataSet> programmgesteuert erstellen und die Tabellen mit Daten füllen.  
  
- Sie können das <xref:System.Data.DataSet> mithilfe eines `DataAdapter` mit Tabellen von Daten aus einer vorhandenen relationalen Datenquelle füllen.  
  
- Sie können den Inhalt des <xref:System.Data.DataSet> mithilfe von XML laden und beibehalten. Weitere Informationen finden Sie unter [Using XML in a DataSet (Verwenden von XML in einem DataSet)](using-xml-in-a-dataset.md).  
  
Bei einem <xref:System.Data.DataSet> mit strikter Typbindung besteht auch die Möglichkeit, es mit einem XML-Webdienst zu übertragen. Durch seinen Aufbau ist das <xref:System.Data.DataSet> ideal für die Übertragung von Daten mithilfe von XML-Webdiensten geeignet. Eine Übersicht über die XML-Webdienste finden Sie unter [XML Web Services Overview (Übersicht über XML-Webdienste)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w9fdtx28(v=vs.100)). Ein Beispiel für die Nutzung von <xref:System.Data.DataSet> von einem XML-Webdienst aus finden Sie unter [Consuming a DataSet from an XML Web Service (Verwenden eines DataSets von einem XML-Webdienst aus)](consuming-a-dataset-from-an-xml-web-service.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt

 [Sicherheitsleitfaden](security-guidance.md)  
 Bietet Sicherheits Anleitungen für <xref:System.Data.DataSet> und <xref:System.Data.DataTable> .

 [Erstellen eines Datasets](creating-a-dataset.md)  
 Beschreibt die Syntax zum Erstellen einer Instanz eines <xref:System.Data.DataSet>.  
  
 [Hinzufügen einer "DataTable" zu einem "DataSet"](adding-a-datatable-to-a-dataset.md)  
 Beschreibt das Erstellen sowie das Hinzufügen von Tabellen und Spalten zu einem <xref:System.Data.DataSet>.  
  
 [Hinzufügen von "DataRelations"](adding-datarelations.md)  
 Beschreibt das Erstellen von Beziehungen zwischen Tabellen in einem <xref:System.Data.DataSet>.  
  
 [Navigieren in "DataRelations"](navigating-datarelations.md)  
 Beschreibt, wie die Beziehungen zwischen Tabellen in einem <xref:System.Data.DataSet> dazu verwendet werden, untergeordnete oder übergeordnete Zeilen einer Beziehung zwischen über- und untergeordneten Tabellen zurückzugeben.  
  
 [Zusammenführen von DataSet-Inhalten](merging-dataset-contents.md)  
 Beschreibt, wie der Inhalt eines <xref:System.Data.DataSet>-Arrays, <xref:System.Data.DataTable>-Arrays oder <xref:System.Data.DataRow>-Arrays mit einem anderen <xref:System.Data.DataSet> zusammengeführt wird.  
  
 [Kopieren von DataSet-Inhalten](copying-dataset-contents.md)  
 Beschreibt das Erstellen einer Kopie eines <xref:System.Data.DataSet>, die ein Schema sowie angegebene Daten enthalten kann.  
  
 [Behandeln von DataSet-Ereignissen](handling-dataset-events.md)  
 Beschreibt die Ereignisse eines <xref:System.Data.DataSet> und wie diese verwendet werden.  
  
 [Typisierte "DataSets"](typed-datasets.md)  
 Erläutert, was ein typisiertes <xref:System.Data.DataSet> ist, und wie es erstellt und verwendet wird.  
  
 ["DataTables"](datatables.md)  
 Beschreibt das Erstellen einer <xref:System.Data.DataTable>, das Definieren des zugehörigen Schemas und das Bearbeiten von Daten.  
  
 ["DataTableReaders"](datatablereaders.md)  
 Beschreibt das Erstellen und Verwenden eines <xref:System.Data.DataTableReader>.  
  
 ["DataViews"](dataviews.md)  
 Beschreibt das Erstellen von und Arbeiten mit `DataViews` sowie das Arbeiten mit <xref:System.Data.DataView>-Ereignissen.  
  
 [Using XML in a DataSet (Verwenden von XML in einem DataSet)](using-xml-in-a-dataset.md)  
 Beschreibt, wie das <xref:System.Data.DataSet> mit XML als Datenquelle interagiert, einschließlich des Ladens und Beibehaltens des Inhalts eines <xref:System.Data.DataSet> als XML-Daten.  
  
 [Verwenden eines "DataSet" von einem XML-Webdienst aus](consuming-a-dataset-from-an-xml-web-service.md)  
 Beschreibt, wie ein XML-Webdienst erstellt wird, der für die Übertragung von Daten ein <xref:System.Data.DataSet> verwendet.  
  
## <a name="related-sections"></a>Verwandte Abschnitte

 [Neues in ADO.NET](../whats-new.md)  
 Enthält eine Einführung in neue Funktionen von ADO.NET.  
  
 [Übersicht über ADO.NET](../ado-net-overview.md)  
 Bietet eine Einführung in das Design und die Komponenten von ADO.NET.  
  
 [Auffüllen eines "DataSets" durch einen "DataAdapter"](../populating-a-dataset-from-a-dataadapter.md)  
 Beschreibt das Laden eines **DataSets** mit Daten aus einer Datenquelle.  
  
 [Aktualisieren von Datenquellen mit "DataAdapters"](../updating-data-sources-with-dataadapters.md)  
 Beschreibt, wie Änderungen an Daten in einem **DataSet** auch in der Datenquelle vorgenommen werden können.  
  
 [Hinzufügen von vorhandenen Einschränkungen zu einem "DataSet"](../adding-existing-constraints-to-a-dataset.md)  
 Beschreibt das Auffüllen eines **DataSets** mit Primärschlüsselinformationen aus einer Datenquelle.  
  
## <a name="see-also"></a>Weitere Informationen

- [ADO.NET](../index.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
