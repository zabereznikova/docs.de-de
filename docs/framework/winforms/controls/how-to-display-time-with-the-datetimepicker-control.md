---
title: 'Gewusst wie: Anzeigen der Zeit mithilfe des DateTimePicker-Steuerelements'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time [Windows Forms], displaying in DateTimePicker control
- examples [Windows Forms], DateTimePicker control
- DateTimePicker control [Windows Forms], displaying time
ms.assetid: 0c1c8b40-1b50-4301-a90c-39516775ccb1
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 987ad88b6bab74a8ccc25db6f3c124161306e9dc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-time-with-the-datetimepicker-control"></a><span data-ttu-id="d52bf-102">Gewusst wie: Anzeigen der Zeit mithilfe des DateTimePicker-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="d52bf-102">How to: Display Time with the DateTimePicker Control</span></span>
<span data-ttu-id="d52bf-103">Wenn Ihre Anwendung es Benutzern gestatten soll, ein Datum und eine Uhrzeit auszuwählen, und das Datum und die Uhrzeit im angegebenen Format angezeigt werden sollen, verwenden Sie das <xref:System.Windows.Forms.DateTimePicker>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="d52bf-103">If you want your application to enable users to select a date and time, and to display that date and time in the specified format, use the <xref:System.Windows.Forms.DateTimePicker> control.</span></span> <span data-ttu-id="d52bf-104">Das folgende Verfahren zeigt, wie Sie mithilfe des <xref:System.Windows.Forms.DateTimePicker>-Steuerelements die Uhrzeit anzeigen.</span><span class="sxs-lookup"><span data-stu-id="d52bf-104">The following procedure shows how to use the <xref:System.Windows.Forms.DateTimePicker> control to display the time.</span></span>  
  
### <a name="to-display-the-time-with-the-datetimepicker-control"></a><span data-ttu-id="d52bf-105">So zeigen Sie die Uhrzeit mithilfe des DateTimePicker-Steuerelements an</span><span class="sxs-lookup"><span data-stu-id="d52bf-105">To display the time with the DateTimePicker control</span></span>  
  
1.  <span data-ttu-id="d52bf-106">Legen Sie die <xref:System.Windows.Forms.DateTimePicker.Format%2A>-Eigenschaft auf <xref:System.Windows.Forms.DateTimePickerFormat.Time> fest.</span><span class="sxs-lookup"><span data-stu-id="d52bf-106">Set the <xref:System.Windows.Forms.DateTimePicker.Format%2A> property to <xref:System.Windows.Forms.DateTimePickerFormat.Time></span></span>  
  
     [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#2)]  
  
2.  <span data-ttu-id="d52bf-107">Legen Sie die <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A>-Eigenschaft für das <xref:System.Windows.Forms.DateTimePicker> auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="d52bf-107">Set the <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> property for the <xref:System.Windows.Forms.DateTimePicker> to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="d52bf-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d52bf-108">Example</span></span>  
 <span data-ttu-id="d52bf-109">Das folgende Codebeispiel veranschaulicht das Erstellen eines <xref:System.Windows.Forms.DateTimePicker>, das es Benutzern ermöglicht, nur eine Uhrzeit auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="d52bf-109">The following code sample shows how to create a <xref:System.Windows.Forms.DateTimePicker> that enables users to choose a time only.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d52bf-110">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="d52bf-110">Compiling the Code</span></span>  
 <span data-ttu-id="d52bf-111">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="d52bf-111">This example requires:</span></span>  
  
-   <span data-ttu-id="d52bf-112">Verweise auf die Assemblys "System", "System.Data", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="d52bf-112">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="d52bf-113">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] oder [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] finden Sie unter [Erstellen von der Befehlszeile aus](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Erstellen über die Befehlszeile mit „csc.exe“](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="d52bf-113">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="d52bf-114">Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="d52bf-114">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="d52bf-115">Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="d52bf-115">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d52bf-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d52bf-116">See Also</span></span>  
 [<span data-ttu-id="d52bf-117">DateTimePicker-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="d52bf-117">DateTimePicker Control</span></span>](../../../../docs/framework/winforms/controls/datetimepicker-control-windows-forms.md)
