---
title: Verwenden der Zeile für neue Datensätze im DataGridView-Steuerelement in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], adding rows for new records
- rows [Windows Forms], new records
- DataGridView control [Windows Forms], data entry
ms.assetid: 6110f1ea-9794-442c-a98a-f104a1feeaf4
ms.openlocfilehash: 67c87b28f04b028f329663d6cf8215370a00ef2f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59184820"
---
# <a name="using-the-row-for-new-records-in-the-windows-forms-datagridview-control"></a>Verwenden der Zeile für neue Datensätze im DataGridView-Steuerelement in Windows Forms
Bei Verwendung einer <xref:System.Windows.Forms.DataGridView> für die Bearbeitung von Daten in Ihrer Anwendung häufig möchten geben Sie Ihren Benutzern die Möglichkeit, neue Zeilen mit Daten im Datenspeicher hinzuzufügen. Die <xref:System.Windows.Forms.DataGridView> -Steuerelement unterstützt diese Funktion durch die Bereitstellung einer Zeile für neue Datensätze, die immer als letzte Zeile angezeigt wird. Er ist mit einem Sternchen (*) im Zeilenkopf gekennzeichnet. Den folgenden Abschnitten werden einige der Dinge, die Sie berücksichtigen sollten, wenn das Programm mit der Zeile für neue Datensätze aktiviert.  
  
## <a name="displaying-the-row-for-new-records"></a>Die Zeile anzeigen für neue Datensätze  
 Verwenden der <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> Eigenschaft, um anzugeben, ob die Zeile für neue Datensätze angezeigt wird. Der Standardwert dieser Eigenschaft ist `true`.  
  
 Für das datengebundene Fall, wird die Zeile für neue Datensätze angezeigt werden Wenn die <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> -Eigenschaft des Steuerelements und dem <xref:System.ComponentModel.IBindingList.AllowNew%2A?displayProperty=nameWithType> Eigenschaft der Datenquelle sind beide `true`. Wenn entweder `false` und klicken Sie dann die Zeile nicht angezeigt wird.  
  
## <a name="populating-the-row-for-new-records-with-default-data"></a>Die Zeile für neue Datensätze mit Standarddaten aufgefüllt  
 Wenn der Benutzer die Zeile für neue Datensätze als die aktuelle Zeile und wählt die <xref:System.Windows.Forms.DataGridView> -Steuerelement löst die <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> Ereignis.  
  
 Dieses Ereignis ermöglicht den Zugriff auf die neue <xref:System.Windows.Forms.DataGridViewRow> und ermöglicht es Ihnen, die neue Zeile mit Standarddaten aufgefüllt. Weitere Informationen finden Sie unter [Vorgehensweise: Angeben von Standardwerten für neue Zeilen im DataGridView-Steuerelement in Windows Forms](specify-default-values-for-new-rows-in-the-datagrid.md)  
  
## <a name="the-rows-collection"></a>Die Auflistung von Zeilen  
 Die Zeile für neue Datensätze ist Bestandteil der <xref:System.Windows.Forms.DataGridView> des Steuerelements <xref:System.Windows.Forms.DataGridView.Rows%2A> Auflistung jedoch verhält sich anders in zweierlei Hinsicht:  
  
-   Die Zeile für neue Datensätze kann nicht entfernt werden, aus der <xref:System.Windows.Forms.DataGridView.Rows%2A> Auflistung programmgesteuert. Ein <xref:System.InvalidOperationException> wird ausgelöst, wenn dies versucht wird. Der Benutzer kann nicht auch die Zeile für neue Datensätze gelöscht. Die <xref:System.Windows.Forms.DataGridViewRowCollection.Clear%2A?displayProperty=nameWithType> Methode entfernt sich nicht auf diese Zeile aus der <xref:System.Windows.Forms.DataGridView.Rows%2A> Auflistung.  
  
-   Nach der Zeile für neue Datensätze kann keine Zeile hinzugefügt werden. Ein <xref:System.InvalidOperationException> wird ausgelöst, wenn dies versucht wird. Daher ist die Zeile für neue Datensätze immer die letzte Zeile in der <xref:System.Windows.Forms.DataGridView> Steuerelement. Die Methoden für <xref:System.Windows.Forms.DataGridViewRowCollection> zum Hinzufügen von Zeilen –<xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopy%2A>, und <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopies%2A>– alle rufen Einfügungsmethoden intern, wenn die Zeile für neue Datensätze vorhanden ist.  
  
## <a name="visual-customization-of-the-row-for-new-records"></a>Visuellen Anpassung der Zeile für neue Datensätze  
 Wenn die Zeile für neue Datensätze erstellt wird, müssen sie basiert auf der Zeile, die gemäß der <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> Eigenschaft. Alle Zellstile, die für diese Zeile nicht angegeben werden, werden aus anderen Eigenschaften geerbt. Weitere Informationen zur Vererbung von Zellenstilen finden Sie unter [Zellstile im DataGridView-Steuerelement in Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md).  
  
 Die ursprünglichen Werte von Zellen in der Zeile angezeigt wird, für neue Datensätze aus jeder Zelle abgerufen werden <xref:System.Windows.Forms.DataGridViewCell.DefaultNewRowValue%2A> Eigenschaft. Für die Zellen des Typs <xref:System.Windows.Forms.DataGridViewImageCell>, diese Eigenschaft gibt ein Platzhalterbild zurück. Andernfalls gibt diese Eigenschaft `null` zurück. Sie können diese Eigenschaft, um einen benutzerdefinierten Wert zurückgeben, überschreiben. Allerdings können diese ursprünglichen Werte ersetzt werden, durch eine <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> -Ereignishandler, wenn die Zeile für neue Datensätze von den Fokus hat.  
  
 Standardsymbole für diesen Zeilenheader, die ein Pfeil oder ein Sternchen sind, sind nicht öffentlich verfügbar. Wenn Sie die Symbole anpassen möchten, müssen Sie eine benutzerdefinierte <xref:System.Windows.Forms.DataGridViewRowHeaderCell> Klasse.  
  
 Verwenden Sie die Standardsymbole der <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> Eigenschaft der <xref:System.Windows.Forms.DataGridViewCellStyle> von die Headerzelle der Zeile verwendet wird. Die standard-Symbole werden nicht gerendert, wenn nicht genügend Speicherplatz für die sie vollständig anzuzeigen.  
  
 Wenn die Headerzelle der Zeile einen Zeichenfolgenwert, der festgelegt ist, und nicht genügend Platz für den Text und Symbol vorhanden ist, ist das Symbol nicht angezeigt.  
  
## <a name="sorting"></a>Sortieren  
 In ungebundenen Modus werden neue Datensätze immer am Ende hinzugefügt werden die <xref:System.Windows.Forms.DataGridView> , selbst wenn der Benutzer den Inhalt des sortiert wurden die <xref:System.Windows.Forms.DataGridView>. Der Benutzer muss die Sortierung erneut anzuwenden, um die Zeile an die korrekte Position zu sortieren, Dieses Verhalten ist vergleichbar mit der <xref:System.Windows.Forms.ListView> Steuerelement.  
  
 Daten werden hängt von der Implementierung des Datenmodells gebunden ist, und virtuelle Modi, das Einfügeverhalten, wenn eine Sortierung angewendet wird. Für [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)], die Zeile wird sofort in der richtigen Position sortiert.  
  
## <a name="other-notes-on-the-row-for-new-records"></a>Andere Hinweise auf die Zeile für neue Datensätze  
 Sie können nicht festgelegt werden die <xref:System.Windows.Forms.DataGridViewRow.Visible%2A> Eigenschaft dieser Zeile um `false`. Ein <xref:System.InvalidOperationException> wird ausgelöst, wenn dies versucht wird.  
  
 Die Zeile für neue Datensätze wird immer im Zustand "deaktiviert" erstellt.  
  
## <a name="virtual-mode"></a>Virtueller Modus  
 Wenn Sie virtuellen Modus implementieren, müssen Sie nachverfolgen, wenn eine Zeile für neue Datensätze in das Datenmodell und wann das Hinzufügen der Zeile ein Rollback erforderlich ist. Die genaue Implementierung dieser Funktionalität der Implementierung abhängig von dem Datenmodell und die Transaktionssemantik z. B., ob die Commit-Bereich auf die Zelle oder Zeile ist. Weitere Informationen finden Sie unter [Virtueller Modus im DataGridView-Steuerelement von Windows Forms](virtual-mode-in-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>
- [Dateneingabe im DataGridView-Steuerelement in Windows Forms](data-entry-in-the-windows-forms-datagridview-control.md)
- [Vorgehensweise: Angeben von Standardwerten für neue Zeilen im DataGridView-Steuerelement in Windows Forms](specify-default-values-for-new-rows-in-the-datagrid.md)
