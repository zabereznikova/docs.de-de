---
title: Übersicht über das DataGridView-Steuerelement
description: Erfahren Sie, wie Sie das Windows Forms DataGridView-Steuerelement verwenden, um tabellarische Daten aus vielen unterschiedlichen Arten von Datenquellen anzuzeigen und zu bearbeiten.
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
ms.openlocfilehash: 3e68f536853081453f6ba746d342bc016bc8ca17
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174613"
---
# <a name="datagridview-control-overview-windows-forms"></a>Übersicht über das DataGridView-Steuerelement (Windows Forms)
> [!NOTE]
> Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Mit dem- <xref:System.Windows.Forms.DataGridView> Steuerelement können Sie tabellarische Daten aus vielen unterschiedlichen Arten von Datenquellen anzeigen und bearbeiten.  
  
 Das Binden von Daten an das <xref:System.Windows.Forms.DataGridView> Steuerelement ist unkompliziert und intuitiv, und in vielen Fällen ist es genauso einfach wie das Festlegen der- <xref:System.Windows.Forms.DataGridView.DataSource%2A> Eigenschaft. Wenn Sie an eine Datenquelle binden, die mehrere Listen oder Tabellen enthält, legen Sie die- <xref:System.Windows.Forms.DataGridView.DataMember%2A> Eigenschaft auf eine Zeichenfolge fest, die die Liste oder Tabelle angibt, an die die Bindung erfolgen soll.  
  
 Das- <xref:System.Windows.Forms.DataGridView> Steuerelement unterstützt das Standard-Daten Bindungs Modell Windows Forms, sodass es an Instanzen von Klassen gebunden wird, die in der folgenden Liste beschrieben werden:  
  
- Jede Klasse, die die- <xref:System.Collections.IList> Schnittstelle implementiert, einschließlich eindimensionaler Arrays.  
  
- Jede Klasse, die die <xref:System.ComponentModel.IListSource> -Schnittstelle implementiert, <xref:System.Data.DataTable> z <xref:System.Data.DataSet> . b. die Klassen und.  
  
- Jede Klasse, die die- <xref:System.ComponentModel.IBindingList> Schnittstelle implementiert, z. b. die- <xref:System.ComponentModel.BindingList%601> Klasse.  
  
- Jede Klasse, die die- <xref:System.ComponentModel.IBindingListView> Schnittstelle implementiert, z. b. die- <xref:System.Windows.Forms.BindingSource> Klasse.  
  
 Das- <xref:System.Windows.Forms.DataGridView> Steuerelement unterstützt die Datenbindung an die öffentlichen Eigenschaften der Objekte, die von diesen Schnittstellen zurückgegeben werden, oder an die von einer Schnittstelle zurückgegebene Eigenschaften Auflistung <xref:System.ComponentModel.ICustomTypeDescriptor> , sofern Sie für die zurückgegebenen Objekte  
  
 In der Regel Binden Sie eine Bindung an eine <xref:System.Windows.Forms.BindingSource> Komponente und binden die <xref:System.Windows.Forms.BindingSource> Komponente an eine andere Datenquelle oder füllen Sie mit Geschäftsobjekten auf. Die <xref:System.Windows.Forms.BindingSource> Komponente ist die bevorzugte Datenquelle, da Sie an eine Vielzahl von Datenquellen gebunden werden kann und viele Probleme mit der Datenbindung automatisch lösen kann. Weitere Informationen finden Sie unter [BindingSource-Komponente](bindingsource-component.md).  
  
 Das- <xref:System.Windows.Forms.DataGridView> Steuerelement kann auch im *ungebundenen* Modus ohne zugrunde liegenden Datenspeicher verwendet werden. Ein Codebeispiel, das ein ungebundenes Steuerelement verwendet, finden Sie unter Exemplarische Vorgehensweise <xref:System.Windows.Forms.DataGridView> [: Erstellen eines ungebundenen Windows Forms DataGridView-Steuer](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)Elements.  
  
 Das <xref:System.Windows.Forms.DataGridView> Steuerelement ist hochgradig konfigurier Bar und erweiterbar und bietet viele Eigenschaften, Methoden und Ereignisse, um seine Darstellung und das Verhalten anzupassen. Wenn Sie möchten, dass die Windows Forms Anwendung tabellarische Daten anzeigt, sollten Sie das- <xref:System.Windows.Forms.DataGridView> Steuerelement vor anderen verwenden (z <xref:System.Windows.Forms.DataGrid> . b.). Wenn Sie ein kleines Raster mit schreibgeschützten Werten anzeigen oder wenn Sie es einem Benutzer ermöglichen, eine Tabelle mit Millionen von Datensätzen zu bearbeiten, <xref:System.Windows.Forms.DataGridView> bietet Ihnen das-Steuerelement eine leicht programmierbare, Speicher effiziente Lösung.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Zusammenfassung der DataGridView-Steuerelementtechnologie](datagridview-control-technology-summary-windows-forms.md)  
 Fasst <xref:System.Windows.Forms.DataGridView> Steuerelement Konzepte und die Verwendung verwandter Klassen zusammen.  
  
 [Architektur des DataGridView-Steuerelements](datagridview-control-architecture-windows-forms.md)  
 Beschreibt die Architektur des- <xref:System.Windows.Forms.DataGridView> Steuer Elements und erläutert die Typhierarchie und die Vererbungs Struktur.  
  
 [Szenarios für das DataGridView-Steuerelement](datagridview-control-scenarios-windows-forms.md)  
 Beschreibt die gängigsten Szenarien, in denen Steuer <xref:System.Windows.Forms.DataGridView> Elemente verwendet werden.  
  
 [Codeverzeichnis für DataGridView-Steuerelementcode](datagridview-control-code-directory-windows-forms.md)  
 Enthält Links zu Codebeispielen in der Dokumentation für verschiedene <xref:System.Windows.Forms.DataGridView> Aufgaben. Diese Beispiele sind nach Art der Aufgabe kategorisiert.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Spaltentypen im DataGridView-Steuerelement in Windows Forms](column-types-in-the-windows-forms-datagridview-control.md)  
 Erläutert die Spaltentypen im Windows Forms <xref:System.Windows.Forms.DataGridView> Steuerelement, mit denen Informationen angezeigt werden, und ermöglicht Benutzern das ändern oder Hinzufügen von Informationen.  
  
 [Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)  
 Enthält Themen, in denen beschrieben wird, wie das Steuerelement entweder manuell oder mit Daten aus einer externen Datenquelle gefüllt wird.  
  
 [Anpassen des DataGridView-Steuerelements von Windows Forms](customizing-the-windows-forms-datagridview-control.md)  
 Enthält Themen, in denen das benutzerdefinierte Zeichnen von <xref:System.Windows.Forms.DataGridView>-Zellen und Zeilen und das Erstellen von abgeleiteten Zell-, Spalten- und Zeilentypen beschrieben wird.  
  
 [Leistungsoptimierung im DataGridView-Steuerelement in Windows Forms](performance-tuning-in-the-windows-forms-datagridview-control.md)  
 Enthält Themen, in den erläutert wird, wie das Steuerelement effizient eingesetzt wird, um bei der Arbeit mit großen Datenmengen Leistungsprobleme zu vermeiden.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [DataGridView-Steuerelement](datagridview-control-windows-forms.md)
- [Standardfunktionalität des DataGridView-Steuerelements von Windows Forms](default-functionality-in-the-windows-forms-datagridview-control.md)
- [Standardbehandlung von Tastatur und Maus im DataGridView-Steuerelement von Windows Forms](default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)
