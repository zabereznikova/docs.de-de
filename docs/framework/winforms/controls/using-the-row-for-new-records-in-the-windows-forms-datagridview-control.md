---
title: Verwenden der Zeile für neue Datensätze im DataGridView-Steuerelement
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], adding rows for new records
- rows [Windows Forms], new records
- DataGridView control [Windows Forms], data entry
ms.assetid: 6110f1ea-9794-442c-a98a-f104a1feeaf4
ms.openlocfilehash: 2fcd35f8c4d04909cdbc26f6a4293fdd570385b8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728332"
---
# <a name="using-the-row-for-new-records-in-the-windows-forms-datagridview-control"></a>Verwenden der Zeile für neue Datensätze im DataGridView-Steuerelement in Windows Forms
Wenn Sie einen <xref:System.Windows.Forms.DataGridView> zum Bearbeiten von Daten in der Anwendung verwenden, möchten Sie Ihren Benutzern oft die Möglichkeit geben, dem Datenspeicher neue Daten Zeilen hinzuzufügen. Das <xref:System.Windows.Forms.DataGridView>-Steuerelement unterstützt diese Funktion, indem es eine Zeile für neue Datensätze bereitstellt, die immer als letzte Zeile angezeigt wird. Es ist mit einem Sternchen (*)-Symbol in seiner Zeilen Überschrift markiert. In den folgenden Abschnitten werden einige der Punkte erläutert, die Sie beim Programmieren mit der Zeile für neue aktivierte Datensätze berücksichtigen sollten.  
  
## <a name="displaying-the-row-for-new-records"></a>Anzeigen der Zeile für neue Datensätze  
 Verwenden Sie die <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A>-Eigenschaft, um anzugeben, ob die Zeile für neue Datensätze angezeigt wird. Der Standardwert dieser Eigenschaft ist `true`.  
  
 Für den Daten gebundenen Fall wird die Zeile für neue Datensätze angezeigt, wenn die <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A>-Eigenschaft des-Steuer Elements und die <xref:System.ComponentModel.IBindingList.AllowNew%2A?displayProperty=nameWithType>-Eigenschaft der Datenquelle beide `true`sind. Wenn eine der beiden `false` ist, wird die Zeile nicht angezeigt.  
  
## <a name="populating-the-row-for-new-records-with-default-data"></a>Auffüllen der Zeile für neue Datensätze mit Standarddaten  
 Wenn der Benutzer die Zeile für neue Datensätze als aktuelle Zeile auswählt, löst das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded>-Ereignis aus.  
  
 Dieses Ereignis bietet Zugriff auf den neuen <xref:System.Windows.Forms.DataGridViewRow> und ermöglicht es Ihnen, die neue Zeile mit Standarddaten aufzufüllen. Weitere Informationen finden Sie unter Gewusst [wie: Angeben von Standardwerten für neue Zeilen im Windows Forms DataGridView-Steuer](specify-default-values-for-new-rows-in-the-datagrid.md) Element.  
  
## <a name="the-rows-collection"></a>Die Rows-Auflistung  
 Die Zeile für neue Datensätze ist in der <xref:System.Windows.Forms.DataGridView.Rows%2A> Auflistung des <xref:System.Windows.Forms.DataGridView>-Steuer Elements enthalten, verhält sich jedoch in zweierlei Hinsicht anders:  
  
- Die Zeile für neue Datensätze kann nicht Programm gesteuert aus der <xref:System.Windows.Forms.DataGridView.Rows%2A> Sammlung entfernt werden. Eine <xref:System.InvalidOperationException> wird ausgelöst, wenn versucht wird, den Vorgang auszuführen. Außerdem kann der Benutzer die Zeile für neue Datensätze nicht löschen. Die <xref:System.Windows.Forms.DataGridViewRowCollection.Clear%2A?displayProperty=nameWithType>-Methode entfernt diese Zeile nicht aus der <xref:System.Windows.Forms.DataGridView.Rows%2A> Auflistung.  
  
- Nach der Zeile für neue Datensätze kann keine Zeile hinzugefügt werden. Eine <xref:System.InvalidOperationException> wird ausgelöst, wenn versucht wird, diesen Vorgang auszuführen. Folglich ist die Zeile für neue Datensätze immer die letzte Zeile im <xref:System.Windows.Forms.DataGridView>-Steuerelement. Die Methoden auf <xref:System.Windows.Forms.DataGridViewRowCollection>, die Zeilen hinzufügen –<xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopy%2A>und <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopies%2A>– alle Methoden zum Einfügen von anrufen, wenn die Zeile für neue Datensätze vorhanden ist.  
  
## <a name="visual-customization-of-the-row-for-new-records"></a>Visuelle Anpassung der Zeile für neue Datensätze  
 Wenn die Zeile für neue Datensätze erstellt wird, basiert Sie auf der durch die <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>-Eigenschaft angegebenen Zeile. Alle Zell Stile, die für diese Zeile nicht angegeben sind, werden von anderen Eigenschaften geerbt. Weitere Informationen zur Vererbung von Zellen Formaten finden Sie unter [Zellen Stile im Windows Forms DataGridView-Steuer](cell-styles-in-the-windows-forms-datagridview-control.md)Element.  
  
 Die Anfangswerte, die von Zellen in der Zeile für neue Datensätze angezeigt werden, werden aus der <xref:System.Windows.Forms.DataGridViewCell.DefaultNewRowValue%2A>-Eigenschaft jeder Zelle abgerufen. Bei Zellen vom Typ <xref:System.Windows.Forms.DataGridViewImageCell>gibt diese Eigenschaft ein Platzhalter Bild zurück. Andernfalls gibt diese Eigenschaft `null` zurück. Sie können diese Eigenschaft überschreiben, um einen benutzerdefinierten Wert zurückzugeben. Allerdings können diese anfänglichen Werte durch einen <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> Ereignishandler ersetzt werden, wenn der Fokus in der Zeile für neue Datensätze eintritt.  
  
 Die Standardsymbole für den Header dieser Zeile, die ein Pfeil oder ein Sternchen sind, werden nicht öffentlich verfügbar gemacht. Wenn Sie die Symbole anpassen möchten, müssen Sie eine benutzerdefinierte <xref:System.Windows.Forms.DataGridViewRowHeaderCell> Klasse erstellen.  
  
 In den Standardsymbolen wird die <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>-Eigenschaft des <xref:System.Windows.Forms.DataGridViewCellStyle> verwendet, der von der Zeilen Header Zelle verwendet wird. Die Standardsymbole werden nicht gerendert, wenn nicht genügend Speicherplatz vorhanden ist, um Sie vollständig anzuzeigen.  
  
 Wenn für die Zeilen Header Zelle ein Zeichen folgen Wert festgelegt ist, und wenn nicht genügend Platz für den Text und das Symbol vorhanden ist, wird das Symbol zuerst gelöscht.  
  
## <a name="sorting"></a>Sortierung  
 Im ungebundenen Modus werden neue Datensätze immer am Ende der <xref:System.Windows.Forms.DataGridView> hinzugefügt, auch wenn der Benutzer den Inhalt des <xref:System.Windows.Forms.DataGridView>sortiert hat. Der Benutzer muss die Sortierung erneut anwenden, um die Zeile an die richtige Position zu sortieren. Dieses Verhalten ähnelt dem des <xref:System.Windows.Forms.ListView> Steuer Elements.  
  
 Im Daten gebundenen und virtuellen Modus hängt das Einfügeverhalten, wenn eine Sortierung angewendet wird, von der Implementierung des Datenmodells ab. Für ADO.net wird die Zeile sofort an die richtige Position sortiert.  
  
## <a name="other-notes-on-the-row-for-new-records"></a>Weitere Hinweise in der Zeile für neue Datensätze  
 Die <xref:System.Windows.Forms.DataGridViewRow.Visible%2A>-Eigenschaft dieser Zeile kann nicht auf `false`festgelegt werden. Eine <xref:System.InvalidOperationException> wird ausgelöst, wenn versucht wird, diesen Vorgang auszuführen.  
  
 Die Zeile für neue Datensätze wird immer im nicht ausgewählten Zustand erstellt.  
  
## <a name="virtual-mode"></a>Virtueller Modus  
 Wenn Sie den virtuellen Modus implementieren, müssen Sie nachverfolgen, wann eine Zeile für neue Datensätze im Datenmodell benötigt wird und wann ein Rollback für das Hinzufügen der Zeile ausgeführt werden soll. Die genaue Implementierung dieser Funktionalität hängt von der Implementierung des Datenmodells und seiner Transaktions Semantik ab, z. b. ob der commitbereich auf Zellen-oder Zeilenebene liegt. Weitere Informationen finden Sie [im Windows Forms DataGridView-Steuerelement im virtuellen Modus](virtual-mode-in-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>
- [Dateneingabe im DataGridView-Steuerelement in Windows Forms](data-entry-in-the-windows-forms-datagridview-control.md)
- [Gewusst wie: Angeben von Standardwerten für neue Zeilen im DataGridView-Steuerelement in Windows Forms](specify-default-values-for-new-rows-in-the-datagrid.md)
