---
title: Übersicht über das DataGridView-Steuerelement (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- DataGridView
helpviewer_keywords:
- DataGridView control [Windows Forms], about DataGridView control
- grid controls [Windows Forms]
- tables [Windows Forms], displaying in DataGridView control
- tables [Windows Forms], binding to DataGridView control
- columns [Windows Forms], DataGridView control
- bound controls [Windows Forms], dataGridView control
- datasets [Windows Forms], binding to DataGridView control
- data grids [Windows Forms], about data grids
- data [Windows Forms], resorting
- data [Windows Forms], navigating
- grids [Windows Forms]
- data binding [Windows Forms], DataGridView control
- data sources [Windows Forms], binding to DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 0a45c661-89dc-4390-9cc6-c47eee501488
ms.openlocfilehash: 095c89fd305b1eeb73e2919760abe48e848c6aa0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59112878"
---
# <a name="datagridview-control-overview-windows-forms"></a>Übersicht über das DataGridView-Steuerelement (Windows Forms)
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Mit der <xref:System.Windows.Forms.DataGridView> -Steuerelement, können Sie anzeigen und Bearbeiten von Tabellendaten aus vielen unterschiedlichen Datenquellen.  
  
 Binden von Daten an die <xref:System.Windows.Forms.DataGridView> Steuerelement ist einfach und intuitiv, und in vielen Fällen ist es so einfach wie das Festlegen der <xref:System.Windows.Forms.DataGridView.DataSource%2A> Eigenschaft. Wenn Sie mit einer Datenquelle, die mehrere Listen oder Tabellen enthält binden, legen Sie die <xref:System.Windows.Forms.DataGridView.DataMember%2A> Eigenschaft in eine Zeichenfolge, der angibt, die Liste oder Tabelle zum Binden an.  
  
 Die <xref:System.Windows.Forms.DataGridView> -Steuerelement unterstützt die standardmäßige Windows Forms-Datenbindungsmodell verwendet, damit die Bindung an Instanzen von Klassen, die in der folgenden Liste beschrieben:  
  
-   Jede Klasse, implementiert die <xref:System.Collections.IList> -Schnittstelle, einschließlich eindimensionale Arrays.  
  
-   Jede Klasse, implementiert die <xref:System.ComponentModel.IListSource> Schnittstelle, z. B. die <xref:System.Data.DataTable> und <xref:System.Data.DataSet> Klassen.  
  
-   Jede Klasse, implementiert die <xref:System.ComponentModel.IBindingList> Schnittstelle, z. B. die <xref:System.ComponentModel.BindingList%601> Klasse.  
  
-   Jede Klasse, implementiert die <xref:System.ComponentModel.IBindingListView> Schnittstelle, z. B. die <xref:System.Windows.Forms.BindingSource> Klasse.  
  
 Die <xref:System.Windows.Forms.DataGridView> -Steuerelement unterstützt die Datenbindung an die öffentlichen Eigenschaften der Objekte, die von diesen Schnittstellen zurückgegeben und die Properties-Auflistung, die zurückgegeben werden, indem ein <xref:System.ComponentModel.ICustomTypeDescriptor> Schnittstelle, wenn auf die zurückgegebenen Objekte implementiert.  
  
 In der Regel eine Bindung an eine <xref:System.Windows.Forms.BindingSource> Komponente und die Bindung der <xref:System.Windows.Forms.BindingSource> Komponente in eine andere Datenquelle, oder füllen Sie es mit Geschäftsobjekten. Die <xref:System.Windows.Forms.BindingSource> Komponente ist die bevorzugte Datenquelle aus, da sie eine an eine Vielzahl von Datenquellen Bindung können und kann viele Datenbindung Probleme automatisch beheben. Weitere Informationen finden Sie unter [BindingSource-Komponente](bindingsource-component.md).  
  
 Die <xref:System.Windows.Forms.DataGridView> Steuerelement kann auch verwendet werden, *ungebundenen* -Modus mit keinen zugrunde liegenden Datenspeicher. Ein Codebeispiel, das ein ungebundenes verwendet <xref:System.Windows.Forms.DataGridView> steuern, finden Sie unter [Exemplarische Vorgehensweise: Erstellen eine nicht gebundene Windows Forms-DataGridView-Steuerelement](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md).  
  
 Die <xref:System.Windows.Forms.DataGridView> Steuerelement ist hochgradig konfigurierbar und erweiterbar, und bietet viele Eigenschaften, Methoden und Ereignisse, dessen Darstellung und Verhalten anpassen. Wenn Sie Ihre Windows Forms-Anwendung, die Tabellendaten anzeigen möchten, erwägen Sie die Verwendung der <xref:System.Windows.Forms.DataGridView> Steuerelement vor anderen (z. B. <xref:System.Windows.Forms.DataGrid>). Wenn Sie ein kleines Raster von schreibgeschützten Werten angezeigt werden, oder wenn Sie einen Benutzer zum Bearbeiten einer Tabelle mit Millionen von Datensätzen, aktivieren die <xref:System.Windows.Forms.DataGridView> Steuerelement wird Ihnen eine leicht programmierbar, speichereffizienten Lösung.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Zusammenfassung der DataGridView-Steuerelementtechnologie](datagridview-control-technology-summary-windows-forms.md)  
 Fasst <xref:System.Windows.Forms.DataGridView> Konzepte und die Verwendung von verwandten Klassen zu steuern.  
  
 [Architektur des DataGridView-Steuerelements](datagridview-control-architecture-windows-forms.md)  
 Beschreibt die Architektur von der <xref:System.Windows.Forms.DataGridView> -Steuerelement, erläutert die zugehörige und Vererbung.  
  
 [Szenarios für das DataGridView-Steuerelement](datagridview-control-scenarios-windows-forms.md)  
 Beschreibt die häufigsten Szenarien, in denen <xref:System.Windows.Forms.DataGridView> Steuerelemente verwendet werden.  
  
 [Codeverzeichnis für DataGridView-Steuerelementcode](datagridview-control-code-directory-windows-forms.md)  
 Enthält Links zu Codebeispielen in der Dokumentation für verschiedene <xref:System.Windows.Forms.DataGridView> Aufgaben. Diese Beispiele sind nach Art der Aufgabe kategorisiert.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Spaltentypen im DataGridView-Steuerelement in Windows Forms](column-types-in-the-windows-forms-datagridview-control.md)  
 Beschreibt die Spaltentypen in Windows Forms <xref:System.Windows.Forms.DataGridView> Steuerelement zum Anzeigen von Informationen und ermöglichen Benutzern das Ändern oder Hinzufügen von Informationen verwendet.  
  
 [Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)  
 Enthält Themen, in denen beschrieben wird, wie das Steuerelement entweder manuell oder mit Daten aus einer externen Datenquelle gefüllt wird.  
  
 [Anpassen des DataGridView-Steuerelements von Windows Forms](customizing-the-windows-forms-datagridview-control.md)  
 Enthält Themen, in denen das benutzerdefinierte Zeichnen von <xref:System.Windows.Forms.DataGridView>-Zellen und Zeilen und das Erstellen von abgeleiteten Zell-, Spalten- und Zeilentypen beschrieben wird.  
  
 [Leistungsoptimierung im DataGridView-Steuerelement in Windows Forms](performance-tuning-in-the-windows-forms-datagridview-control.md)  
 Enthält Themen, in den erläutert wird, wie das Steuerelement effizient eingesetzt wird, um bei der Arbeit mit großen Datenmengen Leistungsprobleme zu vermeiden.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [DataGridView-Steuerelement](datagridview-control-windows-forms.md)
- [Standardfunktionalität des DataGridView-Steuerelements von Windows Forms](default-functionality-in-the-windows-forms-datagridview-control.md)
- [Standardbehandlung von Tastatur und Maus im DataGridView-Steuerelement von Windows Forms](default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)
