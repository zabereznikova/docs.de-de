---
title: Übersicht über das DateTimePicker-Steuerelement (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- DateTimePicker
helpviewer_keywords:
- DateTimePicker control [Windows Forms], about
- date and time picker controls
ms.assetid: 501af106-e9fc-4efc-b9b3-c9d8dcaf8c5c
ms.openlocfilehash: cf44cdff7da06a27921ce5881199a3a88b1096f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="datetimepicker-control-overview-windows-forms"></a>Übersicht über das DateTimePicker-Steuerelement (Windows Forms)
Windows Forms <xref:System.Windows.Forms.DateTimePicker> Control ermöglicht dem Benutzer die Auswahl eines einzelnen Elements aus einer Liste von Datums- oder Zeitangaben. Zur Darstellung eines Datums verwendet, wird in zwei Teilen: einer Dropdownliste mit einem Datum dargestellt in Text- und ein Raster, das angezeigt wird, wenn Sie auf den Dropdownpfeil neben der Liste klicken. Das Raster sieht wie der <xref:System.Windows.Forms.MonthCalendar> Steuerelement, das zur Auswahl mehrerer Datumsangaben verwendet werden kann. Weitere Informationen zu den <xref:System.Windows.Forms.MonthCalendar> steuern, finden Sie unter [Übersicht über das MonthCalendar-Steuerelement](../../../../docs/framework/winforms/controls/monthcalendar-control-overview-windows-forms.md).  
  
## <a name="key-properties"></a>Wichtige Eigenschaften  
 Gegebenenfalls die <xref:System.Windows.Forms.DateTimePicker> als ein Steuerelement zur Auswahl oder Bearbeitung von Uhrzeiten statt Datumsangaben angezeigt werden sollen, legen Sie die <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> Eigenschaft, um `true` und die <xref:System.Windows.Forms.DateTimePicker.Format%2A> Eigenschaft <xref:System.Windows.Forms.DateTimePickerFormat.Time>. Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen der Uhrzeit mit dem DateTimePicker-Steuerelement](../../../../docs/framework/winforms/controls/how-to-display-time-with-the-datetimepicker-control.md).  
  
 Wenn die <xref:System.Windows.Forms.DateTimePicker.ShowCheckBox%2A> -Eigenschaftensatz auf `true`, das Kontrollkästchen neben dem ausgewählten Datum im Steuerelement angezeigt wird. Wenn Sie dieses Kontrollkästchen aktiviert ist, kann der ausgewählte Datum / Uhrzeit-Wert aktualisiert werden. Wenn Sie das Kontrollkästchen leer ist, wird der Wert nicht verfügbar.  
  
 Des Steuerelements <xref:System.Windows.Forms.DateTimePicker.MaxDate%2A> und <xref:System.Windows.Forms.DateTimePicker.MinDate%2A> Eigenschaften bestimmen des Bereichs von Datumsangaben und Uhrzeiten. Die <xref:System.Windows.Forms.DateTimePicker.Value%2A> Eigenschaft enthält, das aktuelle Datum und die Uhrzeit, die auf das Steuerelement festgelegt ist. Weitere Informationen finden Sie unter [Vorgehensweise: festlegen und Zurückgeben von Datumsangaben mit dem DateTimePicker-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md). Die Werte können angezeigt werden, in vier-Formate, die festgelegt werden, indem Sie die <xref:System.Windows.Forms.DateTimePicker.Format%2A> Eigenschaft: <xref:System.Windows.Forms.DateTimePickerFormat.Long>, <xref:System.Windows.Forms.DateTimePickerFormat.Short>, <xref:System.Windows.Forms.DateTimePickerFormat.Time>, oder <xref:System.Windows.Forms.DateTimePickerFormat.Custom>. Wenn Sie ein benutzerdefiniertes Format aktiviert ist, müssen Sie festlegen der <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> Eigenschaft, um eine entsprechende Zeichenfolge ein. Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen eines Datums im benutzerdefinierten Format mit dem DateTimePicker-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Anzeigen eines Datums im benutzerdefinierten Format mit dem DateTimePicker-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md)  
 [Gewusst wie: Festlegen und Zurückgeben von Datumsangaben mit dem DateTimePicker-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
