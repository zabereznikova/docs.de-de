---
title: 'Vorgehensweise: Anzeigen der Zeit mithilfe des DateTimePicker-Steuerelements'
description: Erfahren Sie, wie Sie das Windows Forms DateTimePicker-Steuerelement verwenden können, damit Benutzer ein Datum und eine Uhrzeit auswählen und das Datum und die Uhrzeit im angegebenen Format anzeigen können.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time [Windows Forms], displaying in DateTimePicker control
- examples [Windows Forms], DateTimePicker control
- DateTimePicker control [Windows Forms], displaying time
ms.assetid: 0c1c8b40-1b50-4301-a90c-39516775ccb1
ms.openlocfilehash: ab584367a189d05e567bb57d386c6bf629201102
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325581"
---
# <a name="how-to-display-time-with-the-datetimepicker-control"></a>Vorgehensweise: Anzeigen der Zeit mithilfe des DateTimePicker-Steuerelements
Wenn Ihre Anwendung es Benutzern gestatten soll, ein Datum und eine Uhrzeit auszuwählen, und das Datum und die Uhrzeit im angegebenen Format angezeigt werden sollen, verwenden Sie das <xref:System.Windows.Forms.DateTimePicker>-Steuerelement. Das folgende Verfahren zeigt, wie Sie mithilfe des <xref:System.Windows.Forms.DateTimePicker>-Steuerelements die Uhrzeit anzeigen.  
  
### <a name="to-display-the-time-with-the-datetimepicker-control"></a>So zeigen Sie die Uhrzeit mithilfe des DateTimePicker-Steuerelements an  
  
1. Legen Sie die <xref:System.Windows.Forms.DateTimePicker.Format%2A>-Eigenschaft auf <xref:System.Windows.Forms.DateTimePickerFormat.Time> fest.  
  
     [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#2)]  
  
2. Legen Sie die <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A>-Eigenschaft für das <xref:System.Windows.Forms.DateTimePicker> auf `true` fest.  
  
     [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#3)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel veranschaulicht das Erstellen eines <xref:System.Windows.Forms.DateTimePicker>, das es Benutzern ermöglicht, nur eine Uhrzeit auszuwählen.  
  
 [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- Verweise auf die Assemblys "System", "System.Data", "System.Drawing" und "System.Windows.Forms".  
  
## <a name="see-also"></a>Siehe auch

- [DateTimePicker-Steuerelement](datetimepicker-control-windows-forms.md)
