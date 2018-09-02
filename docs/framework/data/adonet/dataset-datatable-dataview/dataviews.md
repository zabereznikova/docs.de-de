---
title: "\"DataViews\""
ms.date: 03/30/2017
ms.assetid: 0fe5dfa2-c1cd-435f-90b6-b4dd2e3ef34b
ms.openlocfilehash: 75719e91daba189c1d93491a1db26acc80100bea
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43409169"
---
# <a name="dataviews"></a>"DataViews"
Mit einer <xref:System.Data.DataView> können Sie verschiedene Ansichten der in einer <xref:System.Data.DataTable> gespeicherten Daten erstellen. Diese Funktion wird oft in Datenbindungsanwendungen verwendet. Mit einem **DataView**, können Sie die Daten in einer Tabelle mit verschiedenen Sortierreihenfolgen verfügbar machen, und Sie können die Daten nach Zeilenstatus oder basierend auf einem Filterausdruck filtern.  
  
 Ein **DataView** enthält eine dynamische Ansicht von Daten in der zugrunde liegenden **DataTable**: Inhalt, Reihenfolge und Mitgliedschaft spiegeln vorgenommene Änderungen eintreten. Dieses Verhalten unterscheidet sich von der **wählen** -Methode der der **DataTable**, gibt eine <xref:System.Data.DataRow> ein Array aus einer Tabelle basierend auf einer bestimmten Filters und/oder einer Sortierreihenfolge Reihenfolge: Thiscontent enthält Änderungen an der zugrunde liegende Tabelle, jedoch die Mitgliedschaft und Reihenfolge bleiben statisch. Die dynamischen Funktionen von der **DataView** ideal für datenbindungsanwendungen.  
  
 Ein **DataView** bietet Ihnen eine dynamische Ansicht einen Satz von Daten, ähnlich wie eine Ansicht, auf die Sie verschiedene Sortier- und Filterkriterien anwenden können. Im Gegensatz zu einer Datenbankansicht, jedoch eine **DataView** nicht als Tabelle behandelt werden kann und keine Ansicht der verknüpften Tabellen. Außerdem können Sie keine Spalten ausschließen, die in der Quelltabelle vorhanden sind, und auch keine Spalten (z. B. berechnete Spalten) anhängen, die nicht in der Quelltabelle vorliegen.  
  
 Können Sie eine <xref:System.Data.DataView.DataViewManager%2A> zum Verwalten von Einstellungen für alle Tabellen in einem **DataSet**. Die **DataViewManager** bietet eine praktische Möglichkeit zum Verwalten von standardansichtseinstellungen für jede Tabelle. Beim Binden eines Steuerelements auf mehr als eine Tabelle mit einer **DataSet**, binden an eine **DataViewManager** ist die ideale Wahl.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Erstellen einer DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-dataview.md)  
 Beschreibt das Erstellen einer **DataView** für eine **DataTable**.  
  
 [Sortieren und Filtern von Daten](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)  
 Beschreibt, wie zum Festlegen der Eigenschaften von einem **DataView** Zurückgeben von Teilmengen von Datenzeilen bestimmte Filterkriterien erfüllen, oder um Daten in einer bestimmten Sortierreihenfolge zurückzugeben.  
  
 [DataRows und DataRowViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datarows-and-datarowviews.md)  
 Beschreibt, wie Sie Zugriff auf die Daten, die verfügbar gemacht werden, indem die **DataView**.  
  
 [Suchen nach Zeilen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md)  
 Beschreibt, wie Sie eine bestimmte Zeile in einer **DataView**.  
  
 [ChildViews und Beziehungen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/childviews-and-relations.md)  
 Beschreibt das Erstellen von Ansichten von Daten aus einer hierarchischen Beziehung mit einer **DataView**.  
  
 [Ändern von DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/modifying-dataviews.md)  
 Beschreibt, wie Sie zum Ändern der Daten in der zugrunde liegenden **DataTable** über die **DataView**, einschließlich aktivieren oder Deaktivieren von Updates.  
  
 [Behandeln von DataView-Ereignissen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-dataview-events.md)  
 Beschreibt, wie die **ListChanged** Ereignis benachrichtigt bei den Inhalt oder die Reihenfolge der eine **"DataView"** aktualisiert wird.  
  
 [Verwalten von DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/managing-dataviews.md)  
 Beschreibt, wie eine **DataViewManager** zum Verwalten von **DataView** Einstellungen für jede Tabelle in eine **DataSet**.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [ASP.NET-Webanwendungen](https://msdn.microsoft.com/library/a812d7b7-049e-4234-a4c2-6acf690301f6)  
 Stellt Übersichten und ausführliche schrittweise Anleitungen zum Erstellen von ASP.NET-Anwendungen, Web Forms und Web Services bereit.  
  
 [Windows-Anwendungen](https://msdn.microsoft.com/library/a6bb2180-09b1-4738-b9fd-7fb05fc92f23)  
 Stellt ausführliche Informationen zum Arbeiten mit Windows Forms und Konsolenanwendungen bereit.  
  
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 Beschreibt die **DataSet** -Objekt, und wie Sie es zum Verwalten von Anwendungsdaten verwenden können.  
  
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 Beschreibt die **DataTable** -Objekt, und wie Sie es zum Verwalten von Anwendungsdaten allein oder als Teil der verwenden können eine **DataSet**.  
  
 [ADO.NET](../../../../../docs/framework/data/adonet/index.md)  
 Beschreibt die ADO.NET-Architektur und -Komponenten und die Verwendung von ADO.NET zum Zugriff auf vorhandene Datenquellen und zum Verwalten von Anwendungsdaten.  
  
## <a name="see-also"></a>Siehe auch  
 [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
