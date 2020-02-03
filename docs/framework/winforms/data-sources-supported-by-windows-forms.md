---
title: Unterstützte Datenquellen
ms.date: 03/30/2017
helpviewer_keywords:
- collections [Windows Forms], binding to
- OLE DB providers [Windows Forms], Windows Forms
- DataTable class [Windows Forms], binding and Windows Forms
- Windows Forms, data binding
- DataView class [Windows Forms], binding and Windows Forms
- DataViewManager class [Windows Forms], binding and Windows Forms
- Windows Forms, source data
- arrays [Windows Forms]
- data sources [Windows Forms]
- data providers [Windows Forms]
- DataSet class [Windows Forms], binding and Windows Forms
- data [Windows Forms], data providers
ms.assetid: 3d2c43f6-462b-4d35-9c86-13e9afe012e1
ms.openlocfilehash: 83ce4bb0d6f0bf81bcad4e38af212dccc3483ca5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742311"
---
# <a name="data-sources-supported-by-windows-forms"></a>Von Windows Forms unterstützte Datenquellen
In der Vergangenheit wurde die Datenbindung innerhalb von Anwendungen verwendet, um die in-Datenbanken gespeicherten Daten zu nutzen. Mit Windows Forms Datenbindung können Sie auf Daten aus Datenbanken sowie auf Daten in anderen Strukturen (z. b. Arrays und Sammlungen) zugreifen, solange bestimmte Mindestanforderungen erfüllt sind.  
  
## <a name="structures-to-bind-to"></a>Strukturen, an die gebunden werden soll  
 In Windows Forms können Sie eine Bindung an eine Vielzahl von Strukturen herstellen, von einfachen Objekten (einfache Bindung) bis hin zu komplexen Listen wie ADO.NET Data Tables (komplexe Bindung). Bei einer einfachen Bindung unterstützt Windows Forms das Binden an die öffentlichen Eigenschaften für das einfache Objekt. Windows Forms Listen basierte Bindung erfordert im Allgemeinen, dass das-Objekt die <xref:System.Collections.IList>-Schnittstelle oder die <xref:System.ComponentModel.IListSource>-Schnittstelle unterstützt. Außerdem können Sie, wenn Sie eine Bindung mit über eine <xref:System.Windows.Forms.BindingSource> Komponente herstellen, eine Bindung an ein Objekt durchlaufen, das die <xref:System.Collections.IEnumerable>-Schnittstelle unterstützt. Weitere Informationen zu Schnittstellen, die mit der Datenbindung verknüpft sind, finden [Sie Unterschnitt stellen für die Datenbindung](interfaces-related-to-data-binding.md).  
  
 In der folgenden Liste werden die Strukturen angezeigt, an die in Windows Forms gebunden werden kann.  
  
 <xref:System.Windows.Forms.BindingSource>  
 Ein <xref:System.Windows.Forms.BindingSource> ist die häufigste Windows Forms Datenquelle und fungiert als Proxy zwischen einer Datenquelle und Windows Forms-Steuerelementen. Das allgemeine <xref:System.Windows.Forms.BindingSource> Verwendungs Muster besteht darin, die Steuerelemente an die <xref:System.Windows.Forms.BindingSource> zu binden und die <xref:System.Windows.Forms.BindingSource> an die Datenquelle zu binden (z. b. eine ADO.net-Datentabelle oder ein Geschäftsobjekt). Der <xref:System.Windows.Forms.BindingSource> bietet Dienste, die die Unterstützung der Datenbindung aktivieren und verbessern. Windows Forms Listen basierten Steuerelementen, z. b. die <xref:System.Windows.Forms.DataGridView> und <xref:System.Windows.Forms.ComboBox>, unterstützen z. b. die Bindung an <xref:System.Collections.IEnumerable> Datenquellen nicht direkt. Sie können dieses Szenario jedoch aktivieren, indem Sie eine <xref:System.Windows.Forms.BindingSource>binden. In diesem Fall konvertiert der <xref:System.Windows.Forms.BindingSource> die Datenquelle in einen <xref:System.Collections.IList>.  
  
 Einfache Objekte  
 Windows Forms unterstützt die Daten Bindungs Steuerelement-Eigenschaften für öffentliche Eigenschaften in der Instanz eines-Objekts unter Verwendung des <xref:System.Windows.Forms.Binding> Typs. Windows Forms unterstützt auch das Binden von Listen basierten Steuerelementen, z. b. eine <xref:System.Windows.Forms.ListControl> an eine Objektinstanz, wenn eine <xref:System.Windows.Forms.BindingSource> verwendet wird.  
  
 Array oder Sammlung  
 Um als Datenquelle zu fungieren, muss eine Liste die <xref:System.Collections.IList>-Schnittstelle implementieren. ein Beispiel wäre ein Array, bei dem es sich um eine Instanz der <xref:System.Array>-Klasse handelt. Weitere Informationen zu Arrays finden Sie unter Vorgehens [Weise: Erstellen eines Arrays von Objekten (Visual Basic)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/487y7874(v=vs.100)).  
  
 Im Allgemeinen sollten Sie <xref:System.ComponentModel.BindingList%601> verwenden, wenn Sie Listen von Objekten für die Datenbindung erstellen. <xref:System.ComponentModel.BindingList%601> ist eine generische Version der <xref:System.ComponentModel.IBindingList>-Schnittstelle. Die <xref:System.ComponentModel.IBindingList> Schnittstelle erweitert die <xref:System.Collections.IList> Schnittstelle durch Hinzufügen von Eigenschaften, Methoden und Ereignissen, die für die bidirektionale Datenbindung erforderlich sind.  
  
 <xref:System.Collections.IEnumerable>  
 Windows Forms Steuerelemente können an Datenquellen gebunden werden, die nur die <xref:System.Collections.IEnumerable> Schnittstelle unterstützen, wenn Sie durch eine <xref:System.Windows.Forms.BindingSource> Komponente gebunden sind.  
  
 ADO.net-Datenobjekte  
 ADO.NET stellt eine Reihe von Datenstrukturen bereit, die für die Bindung an geeignet sind. Jede hängt von ihrer Komplexität und Komplexität ab.  
  
- [https://login.microsoftonline.com/consumers/](<xref:System.Data.DataColumn>). Ein <xref:System.Data.DataColumn> ist der wesentliche Baustein eines <xref:System.Data.DataTable>, da eine Reihe von Spalten eine Tabelle bilden. Jede <xref:System.Data.DataColumn> verfügt über eine <xref:System.Data.DataColumn.DataType%2A>-Eigenschaft, die die Art der Daten bestimmt, die die Spalte enthält (z. b. das Erstellen eines Auto Fahrzeugs in einer Tabelle, die Autos beschreibt). Sie können ein Steuerelement (z. b. die <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft eines <xref:System.Windows.Forms.TextBox> Steuer Elements) einfach an eine Spalte in einer Datentabelle binden.  
  
- [https://login.microsoftonline.com/consumers/](<xref:System.Data.DataTable>). Ein <xref:System.Data.DataTable> ist die Darstellung einer Tabelle mit Zeilen und Spalten in ADO.net. Eine Datentabelle enthält zwei Auflistungen: <xref:System.Data.DataColumn>, die die Spalten von Daten in einer bestimmten Tabelle darstellen (die letztendlich die Arten von Daten bestimmen, die in diese Tabelle eingegeben werden können), und <xref:System.Data.DataRow>, die die Daten Zeilen in einer bestimmten Tabelle darstellen. Sie können ein-Steuerelement Komplex an die in einer Datentabelle enthaltenen Informationen binden (z. b. das <xref:System.Windows.Forms.DataGridView>-Steuerelement an eine Datentabelle binden). Wenn Sie jedoch eine Bindung an eine <xref:System.Data.DataTable>, sind Sie eine wirkliche Bindung an die Standardansicht der Tabelle.  
  
- [https://login.microsoftonline.com/consumers/](<xref:System.Data.DataView>). Eine <xref:System.Data.DataView> ist eine angepasste Ansicht einer einzelnen Datentabelle, die gefiltert oder sortiert werden kann. Eine Datenansicht ist die Daten "Snapshot", die von komplexen gebundenen Steuerelementen verwendet werden. Sie können eine einfache Bindung oder eine komplexe Bindung an die Daten innerhalb einer Datenansicht vornehmen, aber beachten Sie, dass Sie an ein festes "Bild" der Daten anstatt an eine saubere, aktualisierbare Datenquelle binden.  
  
- [https://login.microsoftonline.com/consumers/](<xref:System.Data.DataSet>). Eine <xref:System.Data.DataSet> ist eine Auflistung von Tabellen, Beziehungen und Einschränkungen der Daten in einer Datenbank. Sie können eine einfache Bindung oder eine komplexe Bindung an die Daten innerhalb eines Datasets herstellen, aber beachten Sie, dass Sie an den Standard <xref:System.Data.DataViewManager> für die <xref:System.Data.DataSet> binden (siehe nächster Aufzählungs Punkt).  
  
- [https://login.microsoftonline.com/consumers/](<xref:System.Data.DataViewManager>). Eine <xref:System.Data.DataViewManager> ist eine angepasste Ansicht der gesamten <xref:System.Data.DataSet>, analog zu einer <xref:System.Data.DataView>, jedoch mit enthaltenen Beziehungen. Mit einer <xref:System.Data.DataViewManager.DataViewSettings%2A> Sammlung können Sie Standardfilter und Sortieroptionen für alle Sichten festlegen, die der <xref:System.Data.DataViewManager> für eine bestimmte Tabelle hat.  
  
## <a name="see-also"></a>Weitere Informationen

- [Änderungsbenachrichtigung in der Windows Forms-Datenbindung](change-notification-in-windows-forms-data-binding.md)
- [Datenbindung und Windows Forms](data-binding-and-windows-forms.md)
- [Windows Forms-Datenbindung](windows-forms-data-binding.md)
