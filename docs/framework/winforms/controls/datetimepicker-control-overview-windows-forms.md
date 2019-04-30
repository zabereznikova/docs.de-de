---
title: Übersicht über das DateTimePicker-Steuerelement (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- DateTimePicker
helpviewer_keywords:
- DateTimePicker control [Windows Forms], about
- date and time picker controls
ms.assetid: 501af106-e9fc-4efc-b9b3-c9d8dcaf8c5c
ms.openlocfilehash: 451172b51427e4932470c53737c7bc276920271c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61909167"
---
# <a name="datetimepicker-control-overview-windows-forms"></a>Übersicht über das DateTimePicker-Steuerelement (Windows Forms)
Die Windows-Formulare <xref:System.Windows.Forms.DateTimePicker> Steuerelement ermöglicht dem Benutzer, wählen Sie ein einzelnes Element aus einer Liste von Datumsangaben oder Uhrzeiten. Wenn zur Darstellung eines Datums verwendet, er wird in zwei Teilen: einer Dropdownliste ein Datum dargestellt in Text- und ein Raster, das angezeigt wird, wenn Sie auf den Dropdownpfeil neben der Liste klicken. Das Raster sieht wie der <xref:System.Windows.Forms.MonthCalendar> -Steuerelement, das für die Auswahl mehrerer Datumsangaben verwendet werden kann. Weitere Informationen zu den <xref:System.Windows.Forms.MonthCalendar> steuern, finden Sie unter [Übersicht über das MonthCalendar-Steuerelement](monthcalendar-control-overview-windows-forms.md).  
  
## <a name="key-properties"></a>Schlüsseleigenschaften  
 Wenn Sie möchten die <xref:System.Windows.Forms.DateTimePicker> um als ein Steuerelement zur Auswahl oder Bearbeitung von Uhrzeiten anstelle von Daten angezeigt werden, legen Sie die <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> Eigenschaft, um `true` und die <xref:System.Windows.Forms.DateTimePicker.Format%2A> Eigenschaft, um <xref:System.Windows.Forms.DateTimePickerFormat.Time>. Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen der Zeit mithilfe des DateTimePicker-Steuerelements](how-to-display-time-with-the-datetimepicker-control.md).  
  
 Wenn die <xref:System.Windows.Forms.DateTimePicker.ShowCheckBox%2A> -Eigenschaftensatz auf `true`, das Kontrollkästchen neben dem ausgewählten Datum im Steuerelement angezeigt wird. Wenn Sie dieses Kontrollkästchen aktiviert ist, kann der ausgewählte Datum / Uhrzeit-Wert aktualisiert werden. Wenn Sie dieses Kontrollkästchen leer ist, wird der Wert nicht verfügbar angezeigt.  
  
 Des Steuerelements <xref:System.Windows.Forms.DateTimePicker.MaxDate%2A> und <xref:System.Windows.Forms.DateTimePicker.MinDate%2A> Eigenschaften bestimmen den Bereich für Datums- und Uhrzeitangaben. Die <xref:System.Windows.Forms.DateTimePicker.Value%2A> Eigenschaft enthält das aktuelle Datum und die Uhrzeit, die auf das Steuerelement festgelegt ist. Weitere Informationen finden Sie unter [Vorgehensweise: Festlegen und Zurückgeben von Datumsangaben mit dem Windows Forms DateTimePicker-Steuerelement](how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md). Die Werte angezeigt werden können, in vier Formaten, die festgelegt werden, indem die <xref:System.Windows.Forms.DateTimePicker.Format%2A> Eigenschaft: <xref:System.Windows.Forms.DateTimePickerFormat.Long>, <xref:System.Windows.Forms.DateTimePickerFormat.Short>, <xref:System.Windows.Forms.DateTimePickerFormat.Time>, oder <xref:System.Windows.Forms.DateTimePickerFormat.Custom>. Wenn Sie ein benutzerdefiniertes Format ausgewählt ist, müssen Sie festlegen der <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> Eigenschaft, um eine entsprechende Zeichenfolge ein. Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen eines Datums im benutzerdefinierten Format mit dem DateTimePicker-Steuerelement in Windows Forms](display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md).  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Anzeigen eines Datums im benutzerdefinierten Format mit dem DateTimePicker-Steuerelement in Windows Forms](display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md)
- [Vorgehensweise: Festlegen und Zurückgeben von Datumsangaben mit dem DateTimePicker-Steuerelement in Windows Forms](how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
