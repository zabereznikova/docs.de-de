---
title: Von Windows Forms unterstützte Datenquellen
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
ms.openlocfilehash: b648d62c9128f0864d60ace1ca56700f594b78c5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59124617"
---
# <a name="data-sources-supported-by-windows-forms"></a>Von Windows Forms unterstützte Datenquellen
In der Vergangenheit wurde die Datenbindung in Anwendungen verwendet, um Daten in Datenbanken nutzen. Mit Windows Forms-Datenbindung, können Sie Daten aus Datenbanken sowie Daten in andere Datenstrukturen, z. B. Arrays und Sammlungen, zugreifen, solange Sie bestimmte Mindestanforderungen erfüllt sind.  
  
## <a name="structures-to-bind-to"></a>Strukturen, um die Bindung an  
 In Windows Forms können Sie an eine Vielzahl von Strukturen binden, von einfachen Objekten (einfache Bindung), komplexe Liste z. B. ADO.NET Datentabellen (komplexe Bindung). Für einfache Bindung unterstützt Windows Forms die Bindung an die öffentlichen Eigenschaften für das einfache Objekt. Windows Forms listenbasierte Bindung in der Regel ist erforderlich, dass das Objekt unterstützt die <xref:System.Collections.IList> Schnittstelle oder die <xref:System.ComponentModel.IListSource> Schnittstelle. Darüber hinaus, wenn Sie über die Bindung sind eine <xref:System.Windows.Forms.BindingSource> -Komponente, die Sie binden können, auf ein Objekt, das unterstützt die <xref:System.Collections.IEnumerable> Schnittstelle. Weitere Informationen zu auf Datenbindung bezogene Schnittstellen, finden Sie unter [im Zusammenhang mit Schnittstellen mit Datenbindung](interfaces-related-to-data-binding.md).  
  
 Die folgende Liste enthält den Strukturen, dass Sie in Windows Forms zu binden können.  
  
 <xref:System.Windows.Forms.BindingSource>  
 Ein <xref:System.Windows.Forms.BindingSource> ist die am häufigsten verwendete Windows Forms-Datenquelle und einen Proxy zwischen einer Datenquelle und Windows Forms-Steuerelemente fungiert. Die allgemeinen <xref:System.Windows.Forms.BindingSource> Verwendungsmuster ist, die Steuerelemente zum Binden der <xref:System.Windows.Forms.BindingSource> und Binden der <xref:System.Windows.Forms.BindingSource> mit der Datenquelle (z. B. eine ADO.NET-Datenquelle oder ein Geschäftsobjekt). Die <xref:System.Windows.Forms.BindingSource> bietet Dienste, die ermöglichen und verbessern die Ebene der bindungsunterstützung Daten. Windows Forms-Liste basiert beispielsweise Steuerelemente wie z. B. die <xref:System.Windows.Forms.DataGridView> und <xref:System.Windows.Forms.ComboBox> unterstützen keine direkte Bindung an <xref:System.Collections.IEnumerable> Datenquellen können Sie jedoch dieses Szenario durch Bindung durch Aktivieren einer <xref:System.Windows.Forms.BindingSource>. In diesem Fall die <xref:System.Windows.Forms.BindingSource> wird die Datenquelle zum Konvertieren einer <xref:System.Collections.IList>.  
  
 Einfache Objekte  
 Windows Forms-Steuerelement für Datenbindungseigenschaften öffentlichen Eigenschaften unterstützt, für die Instanz eines Objekts mit der <xref:System.Windows.Forms.Binding> Typ. Windows Forms unterstützt auch Binden von Steuerelementen Liste basiert, wie eine <xref:System.Windows.Forms.ListControl> an eine Objektinstanz, wenn eine <xref:System.Windows.Forms.BindingSource> verwendet wird.  
  
 Array oder einer Auflistung  
 Um als Datenquelle zu fungieren, muss eine Liste implementieren die <xref:System.Collections.IList> -Schnittstelle, sondern eine Beispiel wäre ein Array, das eine Instanz von der <xref:System.Array> Klasse. Weitere Informationen zu Arrays finden Sie unter [Vorgehensweise: Erstellen Sie ein Array von Objekten (Visual Basic)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/487y7874(v=vs.100)).  
  
 Sie sollten im Allgemeinen verwenden <xref:System.ComponentModel.BindingList%601> beim Erstellen Listen von Objekten für die Datenbindung. <xref:System.ComponentModel.BindingList%601> ist eine generische Version der <xref:System.ComponentModel.IBindingList> Schnittstelle. Die <xref:System.ComponentModel.IBindingList> Schnittstelle erweitert die <xref:System.Collections.IList> -Schnittstelle durch Hinzufügen von Eigenschaften, Methoden und Ereignisse, die für die bidirektionale Datenbindung erforderlich sind.  
  
 <xref:System.Collections.IEnumerable>  
 Windows Forms-Steuerelemente gebunden werden können, mit Datenquellen, die nur unterstützen die <xref:System.Collections.IEnumerable> Schnittstelle, wenn sie über gebunden sind eine <xref:System.Windows.Forms.BindingSource> Komponente.  
  
 [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] Datenobjekte  
 [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] bietet eine Reihe von Datenstrukturen geeignet sind, für die Bindung an. Jede unterscheidet sich in ihrer Komplexität und die Komplexität.  
  
-   <xref:System.Data.DataColumn>. Ein <xref:System.Data.DataColumn> ist der grundlegende Baustein einer <xref:System.Data.DataTable>, eine Anzahl von Spalten eine Tabelle besteht. Jede <xref:System.Data.DataColumn> verfügt über eine <xref:System.Data.DataColumn.DataType%2A> -Eigenschaft, die bestimmt, welche Art von Daten in der Spalte enthalten sind (z. B. die Marke eines Autos in einer Tabelle, die Fahrzeuge beschreibt). Sie können einfache binden ein Steuerelements (z. B. eine <xref:System.Windows.Forms.TextBox> des Steuerelements <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft) auf eine Spalte in einer Datentabelle.  
  
-   <xref:System.Data.DataTable>. Ein <xref:System.Data.DataTable> ist die Darstellung einer Tabelle mit Zeilen und Spalten [!INCLUDE[vstecado](../../../includes/vstecado-md.md)]. Eine Datentabelle enthält zwei Sammlungen: <xref:System.Data.DataColumn>, für die Spalten der Daten in einer Tabelle (die letzten Endes bestimmen, die Arten von Daten, die in dieser Tabelle eingegeben werden können), und <xref:System.Data.DataRow>, die Datenzeilen in einer bestimmten Tabelle darstellt. Sie können komplexe binden ein Steuerelements, die in einer Tabelle enthaltenen Informationen (z. B. die Bindung der <xref:System.Windows.Forms.DataGridView> Steuerelement an eine Datentabelle). Allerdings bei der Bindung an eine <xref:System.Data.DataTable>, Sie sind tatsächlich eine Bindung an die Standardansicht der Tabelle.  
  
-   <xref:System.Data.DataView>. Ein <xref:System.Data.DataView> ist eine angepasste Ansicht einer einzelnen Datentabelle, die gefiltert oder sortiert werden kann. Eine Data source View sind es sich um die Daten "Snapshot", die von komplexen datengebundenen Steuerelementen verwendet. Sie können einfachen oder komplexen-Bindung an die Daten in eine Data source View, jedoch beachten Sie, dass Sie zu einem festen "Bild" der Daten anstelle einer sauberen, Update-Datenquelle binden.  
  
-   <xref:System.Data.DataSet>. Ein <xref:System.Data.DataSet> ist eine Sammlung von Tabellen, Beziehungen und Einschränkungen der Daten in einer Datenbank. Sie können einfache binden oder komplexe Binden an den Daten in einem Dataset, aber beachten Sie, dass Sie auf den Standardwert binden <xref:System.Data.DataViewManager> für die <xref:System.Data.DataSet> (siehe nächsten Aufzählungspunkt).  
  
-   <xref:System.Data.DataViewManager>. Ein <xref:System.Data.DataViewManager> ist eine angepasste Ansicht des gesamten <xref:System.Data.DataSet>, analog zu einem <xref:System.Data.DataView>, aber mit Beziehungen enthalten. Mit einem <xref:System.Data.DataViewManager.DataViewSettings%2A> , Sie können Sammlungssatz standardmäßige Filter- und Sortieroptionen für alle Ansichten, die die <xref:System.Data.DataViewManager> für eine bestimmte Tabelle hat.  
  
## <a name="see-also"></a>Siehe auch

- [Änderungsbenachrichtigung in der Windows Forms-Datenbindung](change-notification-in-windows-forms-data-binding.md)
- [Datenbindung und Windows Forms](data-binding-and-windows-forms.md)
- [Windows Forms-Datenbindung](windows-forms-data-binding.md)
