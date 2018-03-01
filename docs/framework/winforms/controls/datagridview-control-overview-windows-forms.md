---
title: "Übersicht über das DataGridView-Steuerelement (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6d9cc6568813af866acaf20696b870bedc3099be
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="datagridview-control-overview-windows-forms"></a>Übersicht über das DataGridView-Steuerelement (Windows Forms)
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Mit der <xref:System.Windows.Forms.DataGridView> -Steuerelement, können Sie anzeigen und Bearbeiten von Tabellendaten aus vielen unterschiedlichen Datenquellen.  
  
 Binden von Daten an die <xref:System.Windows.Forms.DataGridView> -Steuerelement ist einfach und intuitiv, und in vielen Fällen ist es so einfach wie das Festlegen der <xref:System.Windows.Forms.DataGridView.DataSource%2A> Eigenschaft. Wenn Sie an eine Datenquelle, die mehrere Listen oder Tabellen enthält binden, legen Sie die <xref:System.Windows.Forms.DataGridView.DataMember%2A> -Eigenschaft in eine Zeichenfolge, die angibt, die Liste oder Tabelle zum Binden an.  
  
 Die <xref:System.Windows.Forms.DataGridView> -Steuerelement unterstützt das standardmäßige Windows Forms-Datenbindungsmodell verwendet, damit die Bindung an Instanzen von Klassen, die in der folgenden Liste beschrieben:  
  
-   Jede Klasse, implementiert die <xref:System.Collections.IList> -Schnittstelle, einschließlich eindimensionale Arrays.  
  
-   Jede Klasse, implementiert die <xref:System.ComponentModel.IListSource> Schnittstelle, wie die <xref:System.Data.DataTable> und <xref:System.Data.DataSet> Klassen.  
  
-   Jede Klasse, implementiert die <xref:System.ComponentModel.IBindingList> Schnittstelle, wie die <xref:System.ComponentModel.BindingList%601> Klasse.  
  
-   Jede Klasse, implementiert die <xref:System.ComponentModel.IBindingListView> Schnittstelle, wie die <xref:System.Windows.Forms.BindingSource> Klasse.  
  
 Die <xref:System.Windows.Forms.DataGridView> -Steuerelement unterstützt die Datenbindung an die öffentlichen Eigenschaften der Objekte, die diese Schnittstellen zurückgegebenes oder an die Properties-Auflistung, die zurückgegeben werden, indem ein <xref:System.ComponentModel.ICustomTypeDescriptor> -Schnittstelle ein, wenn auf die zurückgegebenen Objekte implementiert.  
  
 In der Regel eine Bindung an eine <xref:System.Windows.Forms.BindingSource> Komponente und Binden der <xref:System.Windows.Forms.BindingSource> -Komponente an eine andere Datenquelle, oder weisen Sie ihm Geschäftsobjekte. Die <xref:System.Windows.Forms.BindingSource> Komponente ist der bevorzugten Datenquelle aus, weil sie zu einer Vielzahl von Datenquellen binden kann, und kann viele Daten Bindungsprobleme automatisch beheben. Weitere Informationen finden Sie unter [BindingSource-Komponente](../../../../docs/framework/winforms/controls/bindingsource-component.md).  
  
 Die <xref:System.Windows.Forms.DataGridView> Steuerelement kann auch verwendet werden, *ungebundenen* Modus ab, wobei keine zugrunde liegenden Datenspeicher. Ein Codebeispiel, das eine ungebundene verwendet <xref:System.Windows.Forms.DataGridView> steuern, finden Sie unter [Exemplarische Vorgehensweise: Erstellen eines ungebundenen DataGridView-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/walkthrough-creating-an-unbound-windows-forms-datagridview-control.md).  
  
 Die <xref:System.Windows.Forms.DataGridView> -Steuerelement ist hochgradig konfigurierbar und erweiterbar, und bietet viele Eigenschaften, Methoden und Ereignissen, die die Darstellung und Verhalten anpassen. Wenn Sie Ihre Windows Forms-Anwendung Tabellendaten anzeigen möchten, können Sie verwenden die <xref:System.Windows.Forms.DataGridView> Steuerelement vor anderen (z. B. <xref:System.Windows.Forms.DataGrid>). Wenn Sie ein Raster mit kleines schreibgeschützte Werte angezeigt werden, oder wenn Sie einen Benutzer so bearbeiten Sie eine Tabelle mit Millionen von Datensätze, aktivieren die <xref:System.Windows.Forms.DataGridView> -Steuerelement mit einer leicht programmierbare, speichereffizienten Lösung bietet.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Zusammenfassung der DataGridView-Steuerelementtechnologie](../../../../docs/framework/winforms/controls/datagridview-control-technology-summary-windows-forms.md)  
 Fasst <xref:System.Windows.Forms.DataGridView> Konzepte und die Verwendung von verwandten Klassen zu steuern.  
  
 [Architektur des DataGridView-Steuerelements](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)  
 Beschreibt die Architektur von der <xref:System.Windows.Forms.DataGridView> -Steuerelements und erläutert seine Typstruktur Hierarchie und Vererbung.  
  
 [Szenarien für das DataGridView-Steuerelement](../../../../docs/framework/winforms/controls/datagridview-control-scenarios-windows-forms.md)  
 Beschreibt die häufigsten Szenarien, in denen <xref:System.Windows.Forms.DataGridView> Steuerelemente verwendet werden.  
  
 [Codeverzeichnis für DataGridView-Steuerelementcode](../../../../docs/framework/winforms/controls/datagridview-control-code-directory-windows-forms.md)  
 Enthält Links zu Codebeispielen in der Dokumentation für die verschiedenen <xref:System.Windows.Forms.DataGridView> Aufgaben. Diese Beispiele sind nach Art der Aufgabe kategorisiert.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Spaltentypen im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)  
 Beschreibt die Spaltentypen in Windows Forms <xref:System.Windows.Forms.DataGridView> das Benutzersteuerelement zum Anzeigen von Informationen und ermöglichen Benutzern das Ändern oder Hinzufügen von Daten.  
  
 [Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 Enthält Themen, in denen beschrieben wird, wie das Steuerelement entweder manuell oder mit Daten aus einer externen Datenquelle gefüllt wird.  
  
 [Anpassen des DataGridView-Steuerelements von Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 Enthält Themen, in denen das benutzerdefinierte Zeichnen von <xref:System.Windows.Forms.DataGridView>-Zellen und Zeilen und das Erstellen von abgeleiteten Zell-, Spalten- und Zeilentypen beschrieben wird.  
  
 [Leistungsoptimierung im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 Enthält Themen, in den erläutert wird, wie das Steuerelement effizient eingesetzt wird, um bei der Arbeit mit großen Datenmengen Leistungsprobleme zu vermeiden.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [DataGridView-Steuerelement](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [Standardfunktionalität des DataGridView-Steuerelements von Windows Forms](../../../../docs/framework/winforms/controls/default-functionality-in-the-windows-forms-datagridview-control.md)  
 [Standardbehandlung von Tastatur und Maus im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)
