---
title: "Von Windows Forms unterst&#252;tzte Datenquellen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Arrays [Windows Forms]"
  - "Auflistungen [Windows Forms], Binden an"
  - "Daten [Windows Forms], Datenprovider"
  - "Datenanbieter [Windows Forms]"
  - "Datenquellen [Windows Forms]"
  - "DataColumn-Klasse"
  - "DataSet-Klasse, Bindung und Windows Forms"
  - "DataTable-Klasse, Bindung und Windows Forms"
  - "DataView-Klasse, Bindung und Windows Forms"
  - "DataViewManager-Klasse, Bindung und Windows Forms"
  - "OLE DB-Anbieter, Windows Forms"
  - "Windows Forms, Datenbindung"
  - "Windows Forms, Quelldaten"
ms.assetid: 3d2c43f6-462b-4d35-9c86-13e9afe012e1
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Von Windows Forms unterst&#252;tzte Datenquellen
Herkömmlicherweise wurde die Datenbindung in Anwendungen verwendet, um in Datenbanken gespeicherte Daten nutzen zu können.  Mit der Datenbindung von Windows Forms können Sie auf Daten zugreifen, die in Datenbanken sowie in anderen Strukturen, z. B. Arrays oder Auflistungen, enthalten sind \(sofern bestimmte Mindestanforderungen erfüllt sind\).  
  
## Strukturen, an die eine Bindung möglich ist  
 In Windows Forms können angefangen von einfachen Objekten \(einfache Bindung\) bis hin zu komplexen Listen wie ADO.NET\-Datentabellen \(komplexe Bindung\) Bindungen an eine Vielzahl von Strukturen vorgenommen werden.  Bei der einfachen Bindung unterstützt Windows Forms das Binden an öffentliche Eigenschaften im einfachen Objekt.  Die listenbasierte Bindung in Windows Forms erfordert im Allgemeinen, dass das Objekt die <xref:System.Collections.IList>\-Schnittstelle oder die <xref:System.ComponentModel.IListSource>\-Schnittstelle unterstützt.  Wenn Sie die Bindung über eine <xref:System.Windows.Forms.BindingSource>\-Komponente ausführen, können Sie zusätzlich eine Bindung an ein Objekt vornehmen, das die <xref:System.Collections.IEnumerable>\-Schnittstelle unterstützt.  Weitere Informationen zu Schnittstellen in Zusammenhang mit der Datenbindung finden Sie unter [Auf Datenbindung bezogene Schnittstellen](../../../docs/framework/winforms/interfaces-related-to-data-binding.md).  
  
 Die folgende Liste enthält die Strukturen, an die Sie in Windows Forms eine Bindung vornehmen können.  
  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.BindingSource> ist die häufigste Windows Forms\-Datenquelle. Sie fungiert als Proxy zwischen einer Datenquelle und Windows Forms\-Steuerelementen.  Das allgemeine Verwendungsmuster von <xref:System.Windows.Forms.BindingSource> sieht vor, Steuerelemente an <xref:System.Windows.Forms.BindingSource> und <xref:System.Windows.Forms.BindingSource> an die Datenquelle \(z. B. eine ADO.NET\-Datenquelle oder ein Geschäftsobjekt\) zu binden.  <xref:System.Windows.Forms.BindingSource> stellt Dienste bereit, die die Unterstützung der Datenbindung ermöglichen und den Grad der Unterstützung verbessern.  Listenbasierte Steuerelemente in Windows Forms, z. B. <xref:System.Windows.Forms.DataGridView> und <xref:System.Windows.Forms.ComboBox>, bieten beispielsweise keine direkte Unterstützung für die Bindung an <xref:System.Collections.IEnumerable>\-Datenquellen. Sie können dieses Szenario jedoch aktivieren, indem Sie die Bindung über <xref:System.Windows.Forms.BindingSource> vornehmen.  In diesem Fall konvertiert <xref:System.Windows.Forms.BindingSource> die Datenquelle in <xref:System.Collections.IList>.  
  
 Einfache Objekte  
 Windows Forms unterstützt in Objektinstanzen mithilfe des <xref:System.Windows.Forms.Binding>\-Typs die Datenbindung von Steuerelementeigenschaften an öffentliche Eigenschaften.  Außerdem unterstützt Windows Forms die Bindung listenbasierter Steuerelemente, z. B. <xref:System.Windows.Forms.ListControl>, an eine Objektinstanz, wenn <xref:System.Windows.Forms.BindingSource> verwendet wird.  
  
 Array oder Auflistung  
 Damit eine Liste als Datenquelle verwendet werden kann, muss sie die <xref:System.Collections.IList>\-Schnittstelle implementieren. Ein Beispiel dafür ist ein Array, das eine Instanz der <xref:System.Array>\-Klasse darstellt.  Weitere Informationen zu Arrays finden Sie unter [How to: Create an Array of Objects \(Visual Basic\)](http://msdn.microsoft.com/de-de/6b64e069-0387-400c-9081-3bdc581020c3).  
  
 Im Allgemeinen sollten Sie <xref:System.ComponentModel.BindingList%601> verwenden, wenn Sie Objektlisten für die Datenbindung erstellen.  <xref:System.ComponentModel.BindingList%601> ist eine generische Version der <xref:System.ComponentModel.IBindingList>\-Schnittstelle.  Die <xref:System.ComponentModel.IBindingList>\-Schnittstelle ist eine Erweiterung der <xref:System.Collections.IList>\-Schnittstelle. Über sie werden Eigenschaften, Methoden und Ereignisse hinzugefügt, die für die bidirektionale Datenbindung erforderlich sind.  
  
 <xref:System.Collections.IEnumerable>  
 Windows Forms\-Steuerelemente können an Datenquellen gebunden werden, die nur die <xref:System.Collections.IEnumerable>\-Schnittstelle unterstützen, wenn sie über eine <xref:System.Windows.Forms.BindingSource>\-Komponente gebunden werden.  
  
 [!INCLUDE[vstecado](../../../includes/vstecado-md.md)]\-Datenobjekte  
 [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] bietet eine Reihe von Datenstrukturen, die für die Bindung geeignet sind.  Diese Strukturen unterscheiden sich hinsichtlich ihres Entwicklungsgrades und ihrer Komplexität.  
  
-   <xref:System.Data.DataColumn>.  Eine <xref:System.Data.DataColumn> bildet den wichtigsten Baustein einer <xref:System.Data.DataTable>, da sich eine Tabelle aus einer Reihe von Spalten zusammensetzt.  Jedes <xref:System.Data.DataColumn>\-Objekt verfügt über eine <xref:System.Data.DataColumn.DataType%2A>\-Eigenschaft, die die Art der Daten bestimmt, die in der Spalte enthalten sind \(in einer Tabelle zur Beschreibung von Autos z. B. die Marke der Autos\).  Ein Steuerelement \(bei einem <xref:System.Windows.Forms.TextBox>\-Steuerelement z. B. die <xref:System.Windows.Forms.Control.Text%2A>\-Eigenschaft\) kann mithilfe der einfachen Bindung an eine Spalte in einer Datentabelle gebunden werden.  
  
-   <xref:System.Data.DataTable>.  Eine <xref:System.Data.DataTable> ist die Darstellung einer Tabelle mit Zeilen und Spalten, wie sie in [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] verwendet wird.  Eine Datentabelle umfasst zwei Auflistungen: <xref:System.Data.DataColumn> für die Datenspalten in einer bestimmten Tabelle \(dadurch wird letztlich bestimmt, welche Arten von Daten in diese Tabelle eingegeben werden können\) sowie <xref:System.Data.DataRow> für die Datenzeilen in einer bestimmten Tabelle.  Ein Steuerelement kann mithilfe der komplexen Bindung an die Daten in einer Datentabelle gebunden werden \(beispielsweise bei Bindung des <xref:System.Windows.Forms.DataGridView>\-Steuerelements an eine Datentabelle\).  Bei der Bindung an <xref:System.Data.DataTable> erstellen Sie tatsächlich eine Bindung an die Standardansicht dieser Tabelle.  
  
-   <xref:System.Data.DataView>.  Eine <xref:System.Data.DataView> ist eine angepasste Ansicht einer einzelnen Datentabelle, die gefiltert oder sortiert werden kann.  Eine Datenansicht ist eine Momentaufnahme der Daten, die von komplex gebundenen Steuerelementen verwendet werden.  Für die Daten in einer Datenansicht können Sie einfache oder komplexe Bindungen vornehmen. Dabei sollten Sie jedoch beachten, dass Sie nicht Bindungen an eine saubere, aktualisierende Datenquelle, sondern an ein festes Abbild der Daten vornehmen.  
  
-   <xref:System.Data.DataSet>.  Ein <xref:System.Data.DataSet> ist eine Auflistung von Tabellen, Beziehungen und Einschränkungen der Daten in einer Datenbank.  Sie können Daten innerhalb eines DataSets mithilfe der einfachen oder komplexen Bindung binden. Stellen Sie jedoch sicher, dass Sie an den standardmäßigen <xref:System.Data.DataViewManager> für <xref:System.Data.DataSet> binden \(siehe dazu den nächsten Gliederungspunkt\).  
  
-   <xref:System.Data.DataViewManager>.  Ein <xref:System.Data.DataViewManager> ist eine angepasste Ansicht des gesamten <xref:System.Data.DataSet>, analog zu einer <xref:System.Data.DataView>, jedoch mit darin enthaltenen Beziehungen.  Mit einer <xref:System.Data.DataViewManager.DataViewSettings%2A>\-Auflistung können Sie standardmäßige Filter\- und Sortieroptionen für beliebige Ansichten festlegen, die <xref:System.Data.DataViewManager> für eine bestimmte Tabelle bereitstellt.  
  
## Siehe auch  
 [Änderungsbenachrichtigung in der Windows Forms\-Datenbindung](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)   
 [Datenbindung und Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)   
 [Datenbindung in Web Forms](../../../docs/framework/winforms/windows-forms-data-binding.md)