---
title: Host Steuerelemente in DataGridView-Zellen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], hosting in cells
- DataGridView control [Windows Forms], hosting controls in cells
- cells [Windows Forms], hosting controls
ms.assetid: e79a9d4e-64ec-41f5-93ec-f5492633cbb2
ms.openlocfilehash: a64521a15a272ca8140302f39d15e7f17e0c423b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736543"
---
# <a name="how-to-host-controls-in-windows-forms-datagridview-cells"></a>Gewusst wie: Hosten von Steuerelementen in DataGridView-Zellen in Windows Forms
Das <xref:System.Windows.Forms.DataGridView>Steuerelement bietet mehrere Spaltentypen, die es den Benutzern ermöglichen, Werte auf vielfältige Weise einzugeben und zu bearbeiten. Wenn diese Spaltentypen Ihre Anforderungen an die Dateneingabe nicht erfüllen, können Sie jedoch auch eigene Spaltentypen mit Zellen erstellen, die von Ihnen gewählte Steuerelemente aufnehmen. Zu diesem Zweck müssen Sie Klassen definieren, die von <xref:System.Windows.Forms.DataGridViewColumn> und <xref:System.Windows.Forms.DataGridViewCell> abgeleitet werden. Außerdem müssen Sie eine Klasse definieren, die von <xref:System.Windows.Forms.Control> abgeleitet wird und die <xref:System.Windows.Forms.IDataGridViewEditingControl>-Schnittstelle implementiert.  
  
 Im folgenden Codebeispiel wird das Erstellen einer Kalenderspalte veranschaulicht. Die Zellen dieser Spalte zeigen Daten in einfachen Textfeldzellen an. Wenn der Benutzer jedoch eine Zelle bearbeitet, wird ein <xref:System.Windows.Forms.DateTimePicker>-Steuerelement angezeigt. Um das erneute Implementieren der Funktionen für die Textfeldanzeige zu vermeiden, wird die `CalendarCell`Klasse von der <xref:System.Windows.Forms.DataGridViewTextBoxCell>-Klasse abgeleitet, anstatt die <xref:System.Windows.Forms.DataGridViewCell>-Klasse direkt zu erben.  
  
> [!NOTE]
> Wenn Sie aus <xref:System.Windows.Forms.DataGridViewCell> oder <xref:System.Windows.Forms.DataGridViewColumn> ableiten und der abgeleiteten Klasse neue Eigenschaften hinzufügen, müssen Sie die `Clone`-Methode überschreiben, damit die neuen Eigenschaften bei Klonvorgängen kopiert werden. Außerdem sollten Sie die `Clone`-Methode der Basisklasse aufrufen, damit die Eigenschaften der Basisklasse in die neue Zelle oder Spalte kopiert werden.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Windows.Forms.DataGridViewCalendarColumn#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCalendarColumn/CS/datagridviewcalendarcolumn.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewCalendarColumn#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCalendarColumn/VB/datagridviewcalendarcolumn.vb#000)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Anforderungen für das folgende Beispiel:  
  
- Verweise auf die Assemblys "System" und "System.Windows.Forms".  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- <xref:System.Windows.Forms.DataGridViewCell>
- <xref:System.Windows.Forms.DataGridViewTextBoxCell>
- <xref:System.Windows.Forms.IDataGridViewEditingControl>
- <xref:System.Windows.Forms.DateTimePicker>
- [Anpassen des DataGridView-Steuerelements von Windows Forms](customizing-the-windows-forms-datagridview-control.md)
- [Architektur des DataGridView-Steuerelements](datagridview-control-architecture-windows-forms.md)
- [Spaltentypen im DataGridView-Steuerelement in Windows Forms](column-types-in-the-windows-forms-datagridview-control.md)
