---
title: Architektur des DataGridView-Steuerelements (Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], architecture
ms.assetid: 1c6cabf0-02ee-4bbc-9574-b54bb7f5b19e
ms.openlocfilehash: c57f7d22219c0cda91dad174be4e225808a9949d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54494924"
---
# <a name="datagridview-control-architecture-windows-forms"></a>Architektur des DataGridView-Steuerelements (Windows Forms)
Die <xref:System.Windows.Forms.DataGridView> Steuerelement und seinen verwandten Klassen dienen als ein flexibles, erweiterbares System zum Anzeigen und Bearbeiten von Tabellendaten. Diese Klassen sind in enthalten die <xref:System.Windows.Forms?displayProperty=nameWithType> -Namespace, und sie sind alle mit dem Namen mit dem Präfix "DataGridView".  
  
## <a name="architecture-elements"></a>Architekturelemente  
 Die primäre <xref:System.Windows.Forms.DataGridView> Assistentenklassen abgeleitet <xref:System.Windows.Forms.DataGridViewElement>. Das folgende Objektmodell veranschaulicht die <xref:System.Windows.Forms.DataGridViewElement> Vererbungshierarchie.  
  
 ![DataGridViewElement-Objektmodell](../../../../docs/framework/winforms/controls/media/datagridviewelement.gif "DataGridViewElement")  
DataGridViewElement-Objektmodell  
  
 Die <xref:System.Windows.Forms.DataGridViewElement> Klasse stellt einen Verweis auf das übergeordnete Element <xref:System.Windows.Forms.DataGridView> steuern und verfügt über eine <xref:System.Windows.Forms.DataGridViewElement.State%2A> -Eigenschaft, die einen Wert enthält, die eine Kombination von Werten aus darstellt. die <xref:System.Windows.Forms.DataGridViewElementStates> Enumeration.  
  
 Die folgenden Abschnitte beschreiben die <xref:System.Windows.Forms.DataGridView> Assistentenklassen im Detail.  
  
### <a name="datagridviewelementstates"></a>DataGridViewElementStates  
 Die <xref:System.Windows.Forms.DataGridViewElementStates> Enumeration enthält die folgenden Werte:  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.None>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.ReadOnly>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Resizable>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Selected>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Visible>  
  
 Die Werte dieser Enumeration können mit der bitweisen logischen Operatoren kombiniert werden also die <xref:System.Windows.Forms.DataGridViewElement.State%2A> Eigenschaft kann mehreren Zuständen gleichzeitig Ausdrücken. Z. B. eine <xref:System.Windows.Forms.DataGridViewElement> gleichzeitig möglich <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>, <xref:System.Windows.Forms.DataGridViewElementStates.Selected>, und <xref:System.Windows.Forms.DataGridViewElementStates.Visible>.  
  
### <a name="cells-and-bands"></a>Zellen und Bänder  
 Die <xref:System.Windows.Forms.DataGridView> Steuerelement besteht aus zwei grundlegende Arten von Objekten: Zellen und Bänder. Leiten Sie alle Zellen von der <xref:System.Windows.Forms.DataGridViewCell> Basisklasse. Die beiden Arten von Bändern, <xref:System.Windows.Forms.DataGridViewColumn> und <xref:System.Windows.Forms.DataGridViewRow>, beide leiten Sie von der <xref:System.Windows.Forms.DataGridViewBand> Basisklasse.  
  
 Die <xref:System.Windows.Forms.DataGridView> -Steuerelement wirkt mit mehreren Klassen, jedoch die am häufigsten auftretenden <xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewColumn>, und <xref:System.Windows.Forms.DataGridViewRow>.  
  
### <a name="datagridviewcell"></a>DataGridViewCell  
 Die Zelle ist die grundlegende Einheit für die Interaktion der <xref:System.Windows.Forms.DataGridView>. Anzeige beruht auf Zellen, und die Dateneingabe wird häufig Zellen. Sie Zugriff auf Zellen mithilfe der <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> Auflistung von der <xref:System.Windows.Forms.DataGridViewRow> -Klasse, und Sie können die ausgewählten Zellen zugreifen, indem Sie mit der <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> Auflistung von der <xref:System.Windows.Forms.DataGridView> Steuerelement. Das folgende Objektmodell veranschaulicht diese Verwendung sowie die <xref:System.Windows.Forms.DataGridViewCell> Vererbungshierarchie.  
  
 ![DataGridViewCell-Objektmodell](../../../../docs/framework/winforms/controls/media/datagridviewcell.gif "DataGridViewCell")  
DataGridViewCell-Objektmodell  
  
 Die <xref:System.Windows.Forms.DataGridViewCell> Typ ist eine abstrakte Basisklasse, von der alle Arten der Zelle abgeleitet werden. <xref:System.Windows.Forms.DataGridViewCell> und seinen abgeleiteten Typen sind nicht an Windows Forms-Steuerelemente, aber einige Windows Forms-Hoststeuerelemente. Weiteren Bearbeitungsfunktionen unterstützt, die eine Zelle wird in der Regel von eines gehosteten Steuerelements behandelt.  
  
 <xref:System.Windows.Forms.DataGridViewCell> Objekte können nicht ihre eigenen Darstellung und das Zeichnen-Funktionen auf dieselbe Weise steuern wie Windows Forms-Steuerelemente. Stattdessen die <xref:System.Windows.Forms.DataGridView> ist verantwortlich für die Darstellung der <xref:System.Windows.Forms.DataGridViewCell> Objekte. Sie können das Aussehen und Verhalten von Zellen erheblich beeinflussen, indem die Interaktion mit der <xref:System.Windows.Forms.DataGridView> Eigenschaften und Ereignisse des Steuerelements. Wenn Sie über besondere Anforderungen für Anpassungen, die über die Funktionen der verfügen die <xref:System.Windows.Forms.DataGridView> -Steuerelement, können Sie eigene abgeleitete Klasse implementieren <xref:System.Windows.Forms.DataGridViewCell> oder eine ihrer untergeordneten Klassen.  
  
 Die folgende Liste enthält die von abgeleiteten Klassen <xref:System.Windows.Forms.DataGridViewCell>:  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxCell>  
  
-   <xref:System.Windows.Forms.DataGridViewButtonCell>  
  
-   <xref:System.Windows.Forms.DataGridViewLinkCell>  
  
-   <xref:System.Windows.Forms.DataGridViewCheckBoxCell>  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxCell>  
  
-   <xref:System.Windows.Forms.DataGridViewImageCell>  
  
-   <xref:System.Windows.Forms.DataGridViewHeaderCell>  
  
-   <xref:System.Windows.Forms.DataGridViewRowHeaderCell>  
  
-   <xref:System.Windows.Forms.DataGridViewColumnHeaderCell>  
  
-   <xref:System.Windows.Forms.DataGridViewTopLeftHeaderCell>  
  
-   Die benutzerdefinierte Zellentypen  
  
### <a name="datagridviewcolumn"></a>DataGridViewColumn  
 Das Schema der <xref:System.Windows.Forms.DataGridView> angefügten Datenspeicher des Steuerelements, ausgedrückt in der <xref:System.Windows.Forms.DataGridView> des Steuerelements Spalten. Sie erreichen die <xref:System.Windows.Forms.DataGridView> des Steuerelements Spalten mithilfe der <xref:System.Windows.Forms.DataGridView.Columns%2A> Auflistung. Sie können die ausgewählten Spalten zugreifen, indem Sie mit der <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> Auflistung. Das folgende Objektmodell veranschaulicht diese Verwendung sowie die <xref:System.Windows.Forms.DataGridViewColumn> Vererbungshierarchie.  
  
 ![DataGridViewColumn-Objektmodell](../../../../docs/framework/winforms/controls/media/datagridviewcolumn.gif "DataGridViewColumn")  
DataGridViewColumn-Objektmodell  
  
 Einige der wichtigsten Zellentypen verfügen über entsprechende Spaltentypen. Diese stammen von der <xref:System.Windows.Forms.DataGridViewColumn> Basisklasse.  
  
 Die folgende Liste enthält die von abgeleiteten Klassen <xref:System.Windows.Forms.DataGridViewColumn>:  
  
-   <xref:System.Windows.Forms.DataGridViewButtonColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewImageColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewLinkColumn>  
  
-   Benutzerdefinierte Spaltentypen  
  
### <a name="datagridview-editing-controls"></a>Bearbeiten von DataGridView-Steuerelement  
 Zellen, die erweiterte Bearbeitungsfunktionen, in der Regel unterstützen, verwenden Sie ein gehostetes Steuerelement, das von einer Windows Forms-Steuerelement abgeleitet wird. Diese Steuerelemente implementieren, auch die <xref:System.Windows.Forms.IDataGridViewEditingControl> Schnittstelle. Das folgende Objektmodell veranschaulicht die Verwendung dieser Steuerelemente.  
  
 ![Bearbeiten von Objektmodell des DataGridView](../../../../docs/framework/winforms/controls/media/datagridviewediting.gif "DataGridViewEditing")  
Bearbeitung im DataGridView-Steuerelement-Objektmodell  
  
 Die folgenden Bearbeitungssteuerelemente sind im Lieferumfang der <xref:System.Windows.Forms.DataGridView> Steuerelement:  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>  
  
 Weitere Informationen zum Erstellen eigener Bearbeitungssteuerelemente, finden Sie unter [Vorgehensweise: Hosten von Steuerelementen in Windows Forms DataGridView-Zellen](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md).  
  
 Die folgende Tabelle zeigt die Beziehung zwischen Zellentypen, Spaltentypen und Bearbeitung von Steuerelementen.  
  
|Zellentyp|Gehostete Steuerelement|Spaltentyp|  
|---------------|--------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewButtonCell>|n/v|<xref:System.Windows.Forms.DataGridViewButtonColumn>|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxCell>|nicht verfügbar|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewComboBoxCell>|<xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewImageCell>|nicht verfügbar|<xref:System.Windows.Forms.DataGridViewImageColumn>|  
|<xref:System.Windows.Forms.DataGridViewLinkCell>|n/v|<xref:System.Windows.Forms.DataGridViewLinkColumn>|  
|<xref:System.Windows.Forms.DataGridViewTextBoxCell>|<xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|  
  
### <a name="datagridviewrow"></a>DataGridViewRow  
 Die <xref:System.Windows.Forms.DataGridViewRow> Klasse angezeigt, die Daten des Datensatzes aus den Daten Felder zu speichern, zu dem die <xref:System.Windows.Forms.DataGridView> Steuerelement angefügt ist. Sie können den Zugriff auf die <xref:System.Windows.Forms.DataGridView> des Steuerelements Zeilen mithilfe der <xref:System.Windows.Forms.DataGridView.Rows%2A> Auflistung. Sie können die ausgewählten Zeilen zugreifen, indem Sie mit der <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> Auflistung. Das folgende Objektmodell veranschaulicht diese Verwendung sowie die <xref:System.Windows.Forms.DataGridViewRow> Vererbungshierarchie.  
  
 ![DataGridViewRow-Objektmodell](../../../../docs/framework/winforms/controls/media/datagridviewrow.gif "DataGridViewRow")  
DataGridViewRow-Objektmodell  
  
 Sie können Ihre eigenen Typen von Ableiten der <xref:System.Windows.Forms.DataGridViewRow> Klasse, obwohl dies in der Regel nicht notwendig ist. Die <xref:System.Windows.Forms.DataGridView> Steuerelement verfügt über mehrere zeilenbezogenen Ereignisse und Eigenschaften zum Anpassen des Verhaltens des seine <xref:System.Windows.Forms.DataGridViewRow> Objekte.  
  
 Wenn Sie aktivieren die <xref:System.Windows.Forms.DataGridView> des Steuerelements <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> -Eigenschaft, eine spezielle Zeile für neue Zeilen hinzugefügt, die als letzte Zeile angezeigt wird. Diese Zeile ist Teil der <xref:System.Windows.Forms.DataGridView.Rows%2A> -Auflistung, aber es verfügt über spezielle Funktionen, die möglicherweise Ihre Aufmerksamkeit erfordern. Weitere Informationen finden Sie unter [verwenden die Zeile für neue Datensätze im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Siehe auch
- [Übersicht über das DataGridView-Steuerelement](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)
- [Anpassen des DataGridView-Steuerelements von Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)
- [Verwenden der Zeile für neue Datensätze im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
