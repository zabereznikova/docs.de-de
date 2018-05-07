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
ms.openlocfilehash: 4705c8a7153e94fa1cd23cf6c2f622d5cd66ec77
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="data-sources-supported-by-windows-forms"></a>Von Windows Forms unterstützte Datenquellen
Bisher wurde die Datenbindung innerhalb von Anwendungen verwendet, um in Datenbanken gespeicherten Daten nutzen. Mit Windows Forms-Datenbindung, können Sie Daten aus Datenbanken sowie Daten in andere Datenstrukturen, z. B. Arrays und Sammlungen, zugreifen, solange Sie bestimmte Mindestanforderungen erfüllt sind.  
  
## <a name="structures-to-bind-to"></a>Strukturen, zum Binden an  
 In Windows Forms können Sie an eine Vielzahl von Strukturen binden, von einfachen Objekten (einfache Bindung), komplexe Listen z. B. ADO.NET Datentabellen (komplexe Bindung). Für einfache Bindung unterstützt Windows Forms die Bindung an die öffentlichen Eigenschaften für das einfache Objekt. Windows Forms listenbasierte Bindung erfordert im Allgemeinen, dass das Objekt unterstützt die <xref:System.Collections.IList> Schnittstelle oder die <xref:System.ComponentModel.IListSource> Schnittstelle. Darüber hinaus, wenn Sie über die Bindung sind eine <xref:System.Windows.Forms.BindingSource> -Komponente, die Sie binden können, auf ein Objekt, das unterstützt die <xref:System.Collections.IEnumerable> Schnittstelle. Weitere Informationen zu auf Datenbindung bezogene Schnittstellen, finden Sie unter [Schnittstellen im Zusammenhang mit der Datenbindung](../../../docs/framework/winforms/interfaces-related-to-data-binding.md).  
  
 Die folgende Liste enthält den Strukturen, dass Sie an Windows Forms binden können.  
  
 <xref:System.Windows.Forms.BindingSource>  
 Ein <xref:System.Windows.Forms.BindingSource> ist die am häufigsten verwendete Windows Forms-Datenquelle und einen Proxy zwischen einer Datenquelle und Windows Forms-Steuerelemente fungiert. Die allgemeinen <xref:System.Windows.Forms.BindingSource> Binden von Steuerelementen für die Verwendungsmuster ist der <xref:System.Windows.Forms.BindingSource> und Binden der <xref:System.Windows.Forms.BindingSource> mit der Datenquelle (z. B. eine ADO.NET-Datenquelle oder ein Geschäftsobjekt). Die <xref:System.Windows.Forms.BindingSource> stellt Dienste, mit denen und verbessern die Ebene der Unterstützung der Datenbindung. Z. B. Windows Forms-Liste-basierte Steuerelemente wie z. B. die <xref:System.Windows.Forms.DataGridView> und <xref:System.Windows.Forms.ComboBox> unterstützen keine direkte Bindung an <xref:System.Collections.IEnumerable> Datenquellen können Sie jedoch aktivieren dieses Szenario von der Bindung über einen <xref:System.Windows.Forms.BindingSource>. In diesem Fall die <xref:System.Windows.Forms.BindingSource> wandelt die Datenquelle um eine <xref:System.Collections.IList>.  
  
 Einfache Objekte  
 Unterstützt Windows Forms-Steuerelement für Datenbindungseigenschaften öffentlichen Eigenschaften auf der Instanz eines Objekts mit der <xref:System.Windows.Forms.Binding> Typ. Windows Forms unterstützt auch Liste basierend Binden von Steuerelementen, wie z. B. eine <xref:System.Windows.Forms.ListControl> an eine Objektinstanz, wenn eine <xref:System.Windows.Forms.BindingSource> verwendet wird.  
  
 Arrays oder einer Auflistung  
 Zur Verwendung als eine Datenquelle, eine Liste muss Folgendes implementieren die <xref:System.Collections.IList> Schnittstelle; eine Beispiel wäre ein Array, das eine Instanz ist die <xref:System.Array> Klasse. Weitere Informationen zu Arrays finden Sie unter [Vorgehensweise: Erstellen Sie ein Array von Objekten (Visual Basic)](http://msdn.microsoft.com/library/6b64e069-0387-400c-9081-3bdc581020c3).  
  
 Sie sollten im Allgemeinen verwenden <xref:System.ComponentModel.BindingList%601> beim Erstellen von Listen mit Objekten, für die Datenbindung. <xref:System.ComponentModel.BindingList%601> ist eine generische Version der <xref:System.ComponentModel.IBindingList> Schnittstelle. Die <xref:System.ComponentModel.IBindingList> -Schnittstelle erweitert die <xref:System.Collections.IList> -Schnittstelle durch Hinzufügen von Eigenschaften, Methoden und Ereignisse, die für die bidirektionale Datenbindung erforderlich.  
  
 <xref:System.Collections.IEnumerable>  
 Windows Forms-Steuerelemente an Datenquellen, die ausschließlich unterstützen gebunden werden können die <xref:System.Collections.IEnumerable> Schnittstelle, wenn sie über gebunden sind eine <xref:System.Windows.Forms.BindingSource> Komponente.  
  
 [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] Datenobjekte  
 [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] bietet eine Reihe von Datenstrukturen geeignet, für die Bindung an. Jede variiert in ihren Wissensstand und Komplexität.  
  
-   <xref:System.Data.DataColumn> Ein <xref:System.Data.DataColumn> ist der wesentliche Baustein von einem <xref:System.Data.DataTable>, insofern, dass eine Anzahl von Spalten eine Tabelle bilden. Jede <xref:System.Data.DataColumn> verfügt über eine <xref:System.Data.DataColumn.DataType%2A> Eigenschaft, die die Art der Daten in der Spalte enthalten sind (z. B. die Marke der in einer Tabelle zur Beschreibung von Autos) bestimmt. Können Sie einfache-binden ein Steuerelements (z. B. eine <xref:System.Windows.Forms.TextBox> des Steuerelements <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft) auf eine Spalte in einer Datentabelle.  
  
-   <xref:System.Data.DataTable> Ein <xref:System.Data.DataTable> ist die Darstellung einer Tabelle mit Zeilen und Spalten [!INCLUDE[vstecado](../../../includes/vstecado-md.md)]. Eine Datentabelle enthält zwei Auflistungen: <xref:System.Data.DataColumn>, für die Spalten der Daten in einer Tabelle (die bestimmen, letztlich die Arten von Daten, die in dieser Tabelle eingegeben werden können), und <xref:System.Data.DataRow>, die Datenzeilen in einer angegebenen Tabelle darstellt. Sie können komplexe binden ein Steuerelements in einer Tabelle enthaltenen Informationen (z. B. die Bindung der <xref:System.Windows.Forms.DataGridView> Steuerelement an eine Datentabelle). Allerdings beim Binden an eine <xref:System.Data.DataTable>, Sie tatsächlich eine Bindung an die Tabelle standardmäßig angezeigt werden.  
  
-   <xref:System.Data.DataView> Ein <xref:System.Data.DataView> ist eine angepasste Ansicht einer einzelnen Datentabelle, die gefiltert oder sortiert werden kann. Eine Data source View sind, die Daten "Momentaufnahme" von komplexen datengebundenen Steuerelementen verwendet wird. Sie können einfache Bindung oder komplexe Binden der Daten in eine Data source View, jedoch beachten Sie, dass Sie mit einem festen "Bild" Daten statt einer sauberen und Update-Datenquelle binden.  
  
-   <xref:System.Data.DataSet> Ein <xref:System.Data.DataSet> ist eine Auflistung von Tabellen, Beziehungen und Einschränkungen der Daten in einer Datenbank. Sie können einfache Bindung oder komplexe Binden der Daten innerhalb eines Datasets, aber beachten Sie, dass Sie eine an Standardeinstellung Bindung <xref:System.Data.DataViewManager> für die <xref:System.Data.DataSet> (siehe die nächste Aufzählungszeichen zeigen).  
  
-   <xref:System.Data.DataViewManager> Ein <xref:System.Data.DataViewManager> ist eine angepasste Ansicht des gesamten <xref:System.Data.DataSet>, analog zu einem <xref:System.Data.DataView>, jedoch mit Beziehungen enthalten. Mit einem <xref:System.Data.DataViewManager.DataViewSettings%2A> , Sie können Sammlungssatz Standardfilter und Sortierungsoptionen für Sichten, die die <xref:System.Data.DataViewManager> für eine bestimmte Tabelle hat.  
  
## <a name="see-also"></a>Siehe auch  
 [Änderungsbenachrichtigung in der Windows Forms-Datenbindung](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 [Datenbindung und Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 [Windows Forms-Datenbindung](../../../docs/framework/winforms/windows-forms-data-binding.md)
