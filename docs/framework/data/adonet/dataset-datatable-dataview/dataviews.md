---
title: "\"DataViews\""
ms.date: 03/30/2017
ms.assetid: 0fe5dfa2-c1cd-435f-90b6-b4dd2e3ef34b
ms.openlocfilehash: f362e4807bce4fb0e3e8c9ae8cdd6b4704fc28aa
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203812"
---
# <a name="dataviews"></a>"DataViews"
Mit einer <xref:System.Data.DataView> können Sie verschiedene Ansichten der in einer <xref:System.Data.DataTable> gespeicherten Daten erstellen. Diese Funktion wird oft in Datenbindungsanwendungen verwendet. Mithilfe einer **DataView**können Sie die Daten in einer Tabelle mit unterschiedlichen Sortier Reihenfolgen verfügbar machen, und Sie können die Daten nach Zeilen Status oder basierend auf einem Filter Ausdruck filtern.  
  
 Eine **DataView** stellt eine dynamische Ansicht der Daten in der zugrundeliegenden Datentabelle bereit: der Inhalt, die Reihenfolge und die Mitgliedschaft reflektieren Änderungen, sobald sie auftreten. Dieses Verhalten unterscheidet sich von der **Select** -Methode der **Daten**Tabelle, die <xref:System.Data.DataRow> ein Array aus einer Tabelle basierend auf einem bestimmten Filter und/oder einer bestimmten Sortierreihenfolge zurückgibt: dieser Inhalt spiegelt die Änderungen an der zugrunde liegenden Tabelle wider, aber seine Mitgliedschaft und die Reihenfolge bleibt statisch. Die dynamischen Funktionen von **DataView** machen es ideal für Daten Bindungs Anwendungen.  
  
 Eine **DataView** stellt eine dynamische Ansicht eines einzelnen Datensatzes bereit, ähnlich wie eine Daten Bank Sicht, auf die Sie andere Sortier-und Filterkriterien anwenden können. Anders als bei einer Daten Bank Sicht kann eine **DataView** jedoch nicht als Tabelle behandelt werden und kann keine Ansicht von verbundenen Tabellen bereitstellen. Außerdem können Sie keine Spalten ausschließen, die in der Quelltabelle vorhanden sind, und auch keine Spalten (z. B. berechnete Spalten) anhängen, die nicht in der Quelltabelle vorliegen.  
  
 Sie können <xref:System.Data.DataView.DataViewManager%2A> zum Verwalten von Ansichts Einstellungen für alle Tabellen in einem **DataSet**verwenden. Der **DataViewManager** bietet Ihnen eine bequeme Möglichkeit, die Standard Ansichts Einstellungen für jede Tabelle zu verwalten. Wenn Sie ein Steuerelement an mehr als eine Tabelle eines **DataSets**binden, ist die Bindung an einen **DataViewManager** die ideale Wahl.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Erstellen einer DataView](creating-a-dataview.md)  
 Beschreibt das Erstellen einer **DataView** für eine **Daten**Tabelle.  
  
 [Sortieren und Filtern von Daten](sorting-and-filtering-data.md)  
 Beschreibt, wie die Eigenschaften einer **DataView** zum Zurückgeben von Teilmengen von Daten Zeilen, die bestimmte Filterkriterien erfüllen, oder das Zurückgeben von Daten in einer bestimmten Sortierreihenfolge festgelegt werden.  
  
 [DataRows und DataRowViews](datarows-and-datarowviews.md)  
 Beschreibt, wie auf die Daten zugegriffen wird, die von der **DataView**verfügbar gemacht werden.  
  
 [Suchen nach Zeilen](finding-rows.md)  
 Beschreibt, wie Sie eine bestimmte Zeile in einer **DataView**finden.  
  
 [ChildViews und Beziehungen](childviews-and-relations.md)  
 Beschreibt, wie Sichten von Daten aus einer Beziehung zwischen übergeordneten und untergeordneten Elementen mithilfe von **DataView**erstellt werden.  
  
 [Ändern von DataViews](modifying-dataviews.md)  
 Beschreibt, wie die Daten in der zugrunde liegenden Datentabelle über die **DataView**geändert werden, einschließlich der Aktivierung oder Deaktivierung von Updates.  
  
 [Behandeln von DataView-Ereignissen](handling-dataview-events.md)  
 Beschreibt die Verwendung des **ListChanged** -Ereignisses, um eine Benachrichtigung zu erhalten, wenn der Inhalt oder die Reihenfolge einer **DataView** aktualisiert wird.  
  
 [Verwalten von DataViews](managing-dataviews.md)  
 Beschreibt, wie ein **DataViewManager** verwendet wird, um die **DataView** -Einstellungen für jede Tabelle in einem **DataSet**zu verwalten.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [ASP.NET-Webanwendungen](https://docs.microsoft.com/previous-versions/655cec97(v=vs.100))  
 Stellt Übersichten und ausführliche schrittweise Anleitungen zum Erstellen von ASP.NET-Anwendungen, Web Forms und Web Services bereit.  
  
 [Windows-Anwendungen](https://docs.microsoft.com/previous-versions/ms184421(v=vs.100))  
 Stellt ausführliche Informationen zum Arbeiten mit Windows Forms und Konsolenanwendungen bereit.  
  
 [DataSets, DataTables und DataViews](index.md)  
 Beschreibt das **DataSet** -Objekt und wie Sie es zum Verwalten von Anwendungsdaten verwenden können.  
  
 [DataTables](datatables.md)  
 Beschreibt das **datbare** -Objekt und erläutert, wie es zum Verwalten von Anwendungsdaten allein oder als Teil eines **DataSets**verwendet werden kann.  
  
 [ADO.NET](../index.md)  
 Beschreibt die ADO.NET-Architektur und -Komponenten und die Verwendung von ADO.NET zum Zugriff auf vorhandene Datenquellen und zum Verwalten von Anwendungsdaten.  
  
## <a name="see-also"></a>Siehe auch

- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
