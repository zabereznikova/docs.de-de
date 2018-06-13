---
title: Verwenden der Zeile für neue Datensätze im DataGridView-Steuerelement in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], adding rows for new records
- rows [Windows Forms], new records
- DataGridView control [Windows Forms], data entry
ms.assetid: 6110f1ea-9794-442c-a98a-f104a1feeaf4
ms.openlocfilehash: abf62cc9165d74f6bf183e3df30d9a768c0c537f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33540658"
---
# <a name="using-the-row-for-new-records-in-the-windows-forms-datagridview-control"></a>Verwenden der Zeile für neue Datensätze im DataGridView-Steuerelement in Windows Forms
Bei Verwendung einer <xref:System.Windows.Forms.DataGridView> für die Bearbeitung von Daten in der Anwendung wird häufig auf Ihre Benutzer die Möglichkeit zum Hinzufügen von neuer Zeilen mit Daten im Datenspeicher erhalten sollen. Die <xref:System.Windows.Forms.DataGridView> -Steuerelement unterstützt diese Funktionalität durch die Bereitstellung einer Zeile für neue Datensätze, die immer als die letzte Zeile angezeigt wird. Er ist mit einem Sternchen (*) im Zeilenkopf gekennzeichnet. Den folgenden Abschnitten werden einige Dinge, die Sie berücksichtigen sollten, wenn das Programm mit der Zeile für neue Datensätze aktiviert.  
  
## <a name="displaying-the-row-for-new-records"></a>Die Zeile anzeigen für neue Datensätze  
 Verwenden der <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> Eigenschaft, um anzugeben, ob die Zeile für neue Datensätze angezeigt wird. Der Standardwert dieser Eigenschaft ist `true`.  
  
 Für das datengebundene Fall, wird die Zeile für neue Datensätze angezeigt werden Wenn die <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> Eigenschaft des Steuerelements und der <xref:System.ComponentModel.IBindingList.AllowNew%2A?displayProperty=nameWithType> Eigenschaft der Datenquelle sind beide `true`. Wenn entweder `false` und dann die Zeile nicht angezeigt wird.  
  
## <a name="populating-the-row-for-new-records-with-default-data"></a>Die Zeile für neue Datensätze mit Standarddaten aufgefüllt  
 Wenn der Benutzer die Zeile für neue Datensätze als die aktuelle Zeile wählt die <xref:System.Windows.Forms.DataGridView> -Steuerelement löst die <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> Ereignis.  
  
 Dieses Ereignis ermöglicht den Zugriff auf die neue <xref:System.Windows.Forms.DataGridViewRow> und ermöglicht es Ihnen, die neue Zeile mit Standarddaten aufgefüllt. Weitere Informationen finden Sie unter [Vorgehensweise: Angeben von Standardwerten für neue Zeilen im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/specify-default-values-for-new-rows-in-the-datagrid.md)  
  
## <a name="the-rows-collection"></a>Die Auflistung von Zeilen  
 Die Zeile für neue Datensätze ist Bestandteil der <xref:System.Windows.Forms.DataGridView> des Steuerelements <xref:System.Windows.Forms.DataGridView.Rows%2A> Auflistung jedoch verhält sich anders in zweierlei Hinsicht:  
  
-   Die Zeile für neue Datensätze kann nicht entfernt werden, aus der <xref:System.Windows.Forms.DataGridView.Rows%2A> Auflistung programmgesteuert. Ein <xref:System.InvalidOperationException> wird ausgelöst, wenn dies versucht wird. Der Benutzer kann nicht auch die Zeile für neue Datensätze löschen. Die <xref:System.Windows.Forms.DataGridViewRowCollection.Clear%2A?displayProperty=nameWithType> Methode entfernt keine diese Zeile aus der <xref:System.Windows.Forms.DataGridView.Rows%2A> Auflistung.  
  
-   Nach der Zeile für neue Datensätze kann keine Zeile hinzugefügt werden. Ein <xref:System.InvalidOperationException> wird ausgelöst, wenn dies versucht wird. Daher ist die Zeile für neue Datensätze immer die letzte Zeile in der <xref:System.Windows.Forms.DataGridView> Steuerelement. Die Methoden auf <xref:System.Windows.Forms.DataGridViewRowCollection> zum Hinzufügen von Zeilen –<xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopy%2A>, und <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopies%2A>– alle rufen Einfügungsmethoden intern, wenn die Zeile für neue Datensätze vorhanden ist.  
  
## <a name="visual-customization-of-the-row-for-new-records"></a>Visuelle Anpassung der Zeile für neue Datensätze  
 Wenn die Zeile für neue Datensätze erstellt wird, basiert auf der Zeile angegeben wird, durch die <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> Eigenschaft. Alle Zellenstile, die für diese Zeile nicht angegeben werden, werden von anderen Eigenschaften geerbt. Weitere Informationen zur Vererbung von Zellenstilen finden Sie unter [Zellstile im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  
  
 Die ursprünglichen Werte von Zellen in der Zeile für neue Datensätze aus den einzelnen Zellen abgerufen werden <xref:System.Windows.Forms.DataGridViewCell.DefaultNewRowValue%2A> Eigenschaft. Für die Zellen des Typs <xref:System.Windows.Forms.DataGridViewImageCell>, gibt diese Eigenschaft ein Platzhalterbild zurück. Andernfalls gibt diese Eigenschaft `null` zurück. Überschreiben Sie diese Eigenschaft, um einen benutzerdefinierten Wert zurückgeben. Allerdings können diese ursprünglichen Werte ersetzt werden, durch eine <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> Ereignishandler, wenn der Fokus die Zeile für neue Datensätze eingibt.  
  
 Standardsymbole für diese Zeile mit einer Überschrift, die ein Pfeil oder ein Sternchen sind, sind nicht öffentlich verfügbar gemacht. Wenn Sie die Symbole anpassen möchten, müssen Sie zum Erstellen eines benutzerdefinierten <xref:System.Windows.Forms.DataGridViewRowHeaderCell> Klasse.  
  
 Verwenden Sie die standard-Symbole der <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> Eigenschaft von der <xref:System.Windows.Forms.DataGridViewCellStyle> von die Headerzelle der Zeile verwendet wird. Die standard-Symbole werden nicht gerendert, wenn es nicht genügend Speicherplatz ist für diese vollständig anzuzeigen.  
  
 Wenn die Headerzelle der Zeile hat einen Zeichenfolgenwert festgelegt, und wenn nicht ausreichend Platz für Text und Symbol vorhanden ist, wird das Symbol "zuerst gelöscht.  
  
## <a name="sorting"></a>Sortieren  
 Im ungebundenen Modus werden neue Datensätze immer am Ende hinzugefügt werden die <xref:System.Windows.Forms.DataGridView> , selbst wenn der Benutzer den Inhalt des sortiert wurden die <xref:System.Windows.Forms.DataGridView>. Der Benutzer muss der Sortierung erneut angewendet, um die Zeile an der richtigen Position sortieren; Dieses Verhalten ähnelt dem von der <xref:System.Windows.Forms.ListView> Steuerelement.  
  
 Daten werden abhängig von der Implementierung des Datenmodells gebunden ist, und virtuelle Modi, das Einfügeverhalten, wenn eine Sortierung angewendet wird. Für [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)], die Zeile wird sofort in der richtigen Position sortiert.  
  
## <a name="other-notes-on-the-row-for-new-records"></a>Andere Hinweise auf die Zeile für neue Datensätze  
 Kann nicht festgelegt werden die <xref:System.Windows.Forms.DataGridViewRow.Visible%2A> Eigenschaft dieser Zeile auf `false`. Ein <xref:System.InvalidOperationException> wird ausgelöst, wenn dies versucht wird.  
  
 Die Zeile für neue Datensätze wird immer im Status "deaktiviert" erstellt.  
  
## <a name="virtual-mode"></a>Virtueller Modus  
 Wenn Sie den virtuellen Modus implementieren, müssen Sie verfolgen, wann eine Zeile für neue Datensätze in das Datenmodell und wann Sie das Hinzufügen der Zeile ein Rollback erforderlich ist. Die genaue Implementierung dieser Funktion richtet sich nach der Implementierung des Datenmodells und seiner Transaktionssemantik z. B., ob die Commit-Bereich auf der Ebene Zelle oder Zeile befindet. Weitere Informationen finden Sie unter [Virtueller Modus im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>  
 [Dateneingabe im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)  
 [Gewusst wie: Angeben von Standardwerten für neue Zeilen im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/specify-default-values-for-new-rows-in-the-datagrid.md)
