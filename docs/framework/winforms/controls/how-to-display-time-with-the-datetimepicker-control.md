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
# <a name="how-to-display-time-with-the-datetimepicker-control"></a><span data-ttu-id="0bee3-103">Vorgehensweise: Anzeigen der Zeit mithilfe des DateTimePicker-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="0bee3-103">How to: Display Time with the DateTimePicker Control</span></span>
<span data-ttu-id="0bee3-104">Wenn Ihre Anwendung es Benutzern gestatten soll, ein Datum und eine Uhrzeit auszuwählen, und das Datum und die Uhrzeit im angegebenen Format angezeigt werden sollen, verwenden Sie das <xref:System.Windows.Forms.DateTimePicker>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0bee3-104">If you want your application to enable users to select a date and time, and to display that date and time in the specified format, use the <xref:System.Windows.Forms.DateTimePicker> control.</span></span> <span data-ttu-id="0bee3-105">Das folgende Verfahren zeigt, wie Sie mithilfe des <xref:System.Windows.Forms.DateTimePicker>-Steuerelements die Uhrzeit anzeigen.</span><span class="sxs-lookup"><span data-stu-id="0bee3-105">The following procedure shows how to use the <xref:System.Windows.Forms.DateTimePicker> control to display the time.</span></span>  
  
### <a name="to-display-the-time-with-the-datetimepicker-control"></a><span data-ttu-id="0bee3-106">So zeigen Sie die Uhrzeit mithilfe des DateTimePicker-Steuerelements an</span><span class="sxs-lookup"><span data-stu-id="0bee3-106">To display the time with the DateTimePicker control</span></span>  
  
1. <span data-ttu-id="0bee3-107">Legen Sie die <xref:System.Windows.Forms.DateTimePicker.Format%2A>-Eigenschaft auf <xref:System.Windows.Forms.DateTimePickerFormat.Time> fest.</span><span class="sxs-lookup"><span data-stu-id="0bee3-107">Set the <xref:System.Windows.Forms.DateTimePicker.Format%2A> property to <xref:System.Windows.Forms.DateTimePickerFormat.Time></span></span>  
  
     [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#2)]  
  
2. <span data-ttu-id="0bee3-108">Legen Sie die <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A>-Eigenschaft für das <xref:System.Windows.Forms.DateTimePicker> auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="0bee3-108">Set the <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> property for the <xref:System.Windows.Forms.DateTimePicker> to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="0bee3-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0bee3-109">Example</span></span>  
 <span data-ttu-id="0bee3-110">Das folgende Codebeispiel veranschaulicht das Erstellen eines <xref:System.Windows.Forms.DateTimePicker>, das es Benutzern ermöglicht, nur eine Uhrzeit auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="0bee3-110">The following code sample shows how to create a <xref:System.Windows.Forms.DateTimePicker> that enables users to choose a time only.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0bee3-111">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="0bee3-111">Compiling the Code</span></span>  
 <span data-ttu-id="0bee3-112">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="0bee3-112">This example requires:</span></span>  
  
- <span data-ttu-id="0bee3-113">Verweise auf die Assemblys "System", "System.Data", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="0bee3-113">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bee3-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0bee3-114">See also</span></span>

- [<span data-ttu-id="0bee3-115">DateTimePicker-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="0bee3-115">DateTimePicker Control</span></span>](datetimepicker-control-windows-forms.md)
