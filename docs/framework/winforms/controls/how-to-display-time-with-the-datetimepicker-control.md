---
title: 'Vorgehensweise: Anzeigen der Zeit mithilfe des DateTimePicker-Steuerelements'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time [Windows Forms], displaying in DateTimePicker control
- examples [Windows Forms], DateTimePicker control
- DateTimePicker control [Windows Forms], displaying time
ms.assetid: 0c1c8b40-1b50-4301-a90c-39516775ccb1
ms.openlocfilehash: f1c1a0abaeddadb44b40d56eb2f8a28e4b58f4f5
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651769"
---
# <a name="how-to-display-time-with-the-datetimepicker-control"></a><span data-ttu-id="2845d-102">Vorgehensweise: Anzeigen der Zeit mithilfe des DateTimePicker-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="2845d-102">How to: Display Time with the DateTimePicker Control</span></span>
<span data-ttu-id="2845d-103">Wenn Ihre Anwendung es Benutzern gestatten soll, ein Datum und eine Uhrzeit auszuwählen, und das Datum und die Uhrzeit im angegebenen Format angezeigt werden sollen, verwenden Sie das <xref:System.Windows.Forms.DateTimePicker>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="2845d-103">If you want your application to enable users to select a date and time, and to display that date and time in the specified format, use the <xref:System.Windows.Forms.DateTimePicker> control.</span></span> <span data-ttu-id="2845d-104">Das folgende Verfahren zeigt, wie Sie mithilfe des <xref:System.Windows.Forms.DateTimePicker>-Steuerelements die Uhrzeit anzeigen.</span><span class="sxs-lookup"><span data-stu-id="2845d-104">The following procedure shows how to use the <xref:System.Windows.Forms.DateTimePicker> control to display the time.</span></span>  
  
### <a name="to-display-the-time-with-the-datetimepicker-control"></a><span data-ttu-id="2845d-105">So zeigen Sie die Uhrzeit mithilfe des DateTimePicker-Steuerelements an</span><span class="sxs-lookup"><span data-stu-id="2845d-105">To display the time with the DateTimePicker control</span></span>  
  
1. <span data-ttu-id="2845d-106">Legen Sie die <xref:System.Windows.Forms.DateTimePicker.Format%2A>-Eigenschaft auf <xref:System.Windows.Forms.DateTimePickerFormat.Time> fest.</span><span class="sxs-lookup"><span data-stu-id="2845d-106">Set the <xref:System.Windows.Forms.DateTimePicker.Format%2A> property to <xref:System.Windows.Forms.DateTimePickerFormat.Time></span></span>  
  
     [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#2)]  
  
2. <span data-ttu-id="2845d-107">Legen Sie die <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A>-Eigenschaft für das <xref:System.Windows.Forms.DateTimePicker> auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="2845d-107">Set the <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> property for the <xref:System.Windows.Forms.DateTimePicker> to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="2845d-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2845d-108">Example</span></span>  
 <span data-ttu-id="2845d-109">Das folgende Codebeispiel veranschaulicht das Erstellen eines <xref:System.Windows.Forms.DateTimePicker>, das es Benutzern ermöglicht, nur eine Uhrzeit auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="2845d-109">The following code sample shows how to create a <xref:System.Windows.Forms.DateTimePicker> that enables users to choose a time only.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2845d-110">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="2845d-110">Compiling the Code</span></span>  
 <span data-ttu-id="2845d-111">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="2845d-111">This example requires:</span></span>  
  
- <span data-ttu-id="2845d-112">Verweise auf die Assemblys "System", "System.Data", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="2845d-112">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="2845d-113">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="2845d-113">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="2845d-114">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="2845d-114">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2845d-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2845d-115">See also</span></span>

- [<span data-ttu-id="2845d-116">DateTimePicker-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="2845d-116">DateTimePicker Control</span></span>](datetimepicker-control-windows-forms.md)
