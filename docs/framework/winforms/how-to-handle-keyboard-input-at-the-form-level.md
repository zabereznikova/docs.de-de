---
title: 'Gewusst wie: Behandeln von Tastatureingaben auf Formularebene'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- keyboard input [Windows Forms], at form level
- Windows Forms, handling keyboard input
- keyboards [Windows Forms], form-level input
ms.assetid: d7f8b390-dc91-42d2-ae0f-2ffa388127ad
ms.openlocfilehash: a75c4f116b32499f9ba33dd863f2a5b6952a3e24
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46000829"
---
# <a name="how-to-handle-keyboard-input-at-the-form-level"></a><span data-ttu-id="87f17-102">Gewusst wie: Behandeln von Tastatureingaben auf Formularebene</span><span class="sxs-lookup"><span data-stu-id="87f17-102">How to: Handle Keyboard Input at the Form Level</span></span>
<span data-ttu-id="87f17-103">Windows Forms bieten die Möglichkeit, Tastatureingaben auf Formularebene zu behandeln, bevor die Eingaben an ein Steuerelement weitergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="87f17-103">Windows Forms provides the ability to handle keyboard messages at the form level, before the messages reach a control.</span></span> <span data-ttu-id="87f17-104">In diesem Thema wird gezeigt, wie Sie diese Aufgabe ausführen.</span><span class="sxs-lookup"><span data-stu-id="87f17-104">This topic shows how to accomplish this task.</span></span>  
  
### <a name="to-handle-a-keyboard-message-at-the-form-level"></a><span data-ttu-id="87f17-105">So behandeln Sie eine Tastatureingabe auf Formularebene</span><span class="sxs-lookup"><span data-stu-id="87f17-105">To handle a keyboard message at the form level</span></span>  
  
-   <span data-ttu-id="87f17-106">Behandeln Sie das Ereignis <xref:System.Windows.Forms.Control.KeyPress> oder <xref:System.Windows.Forms.Control.KeyDown> im Startformular, und legen Sie die <xref:System.Windows.Forms.Form.KeyPreview%2A>-Eigenschaft des Formulars auf `true` fest, damit Tastatureingaben vom Formular empfangen werden, bevor sie an irgendeines der Steuerelemente auf dem Formular weitergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="87f17-106">Handle the <xref:System.Windows.Forms.Control.KeyPress> or <xref:System.Windows.Forms.Control.KeyDown> event of the startup form, and set the <xref:System.Windows.Forms.Form.KeyPreview%2A> property of the form to `true` so that keyboard messages are received by the form before they reach any controls on the form.</span></span> <span data-ttu-id="87f17-107">Im folgenden Codebeispiel wird das <xref:System.Windows.Forms.Control.KeyPress>-Ereignis behandelt, indem alle Zahlentasten erkannt und "1", "4" und "7" verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="87f17-107">The following code example handles the <xref:System.Windows.Forms.Control.KeyPress> event by detecting all of the number keys and consuming '1', '4', and '7'.</span></span>  
  
     [!code-cpp[System.Windows.Forms.KeyboardInputForm#10](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/cpp/form1.cpp#10)]
     [!code-csharp[System.Windows.Forms.KeyboardInputForm#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/CS/form1.cs#10)]
     [!code-vb[System.Windows.Forms.KeyboardInputForm#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/VB/form1.vb#10)]  
  
## <a name="example"></a><span data-ttu-id="87f17-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="87f17-108">Example</span></span>  
 <span data-ttu-id="87f17-109">Das folgende Codebeispiel ist die vollständige Anwendung für das vorstehende Codebeispiel.</span><span class="sxs-lookup"><span data-stu-id="87f17-109">The following code example is the entire application for the above example.</span></span> <span data-ttu-id="87f17-110">Die Anwendung enthält ein <xref:System.Windows.Forms.TextBox> sowie mehrere andere Steuerelemente, die es Ihnen ermöglichen, den Fokus aus dem <xref:System.Windows.Forms.TextBox> zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="87f17-110">The application includes a <xref:System.Windows.Forms.TextBox> along with several other controls that allow you to move focus from the <xref:System.Windows.Forms.TextBox>.</span></span> <span data-ttu-id="87f17-111">Das <xref:System.Windows.Forms.Control.KeyPress>-Ereignis der Haupt-<xref:System.Windows.Forms.Form> verarbeitet "1", "4" und "7", und das <xref:System.Windows.Forms.Control.KeyPress>-Ereignis des <xref:System.Windows.Forms.TextBox> verarbeitet "2", "5" und "8", während die restlichen Tasten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="87f17-111">The <xref:System.Windows.Forms.Control.KeyPress> event of the main <xref:System.Windows.Forms.Form> consumes '1', '4', and '7', and the <xref:System.Windows.Forms.Control.KeyPress> event of the <xref:System.Windows.Forms.TextBox> consumes '2', '5', and '8' while displaying the remaining keys.</span></span> <span data-ttu-id="87f17-112">Vergleichen Sie die Ausgabe von <xref:System.Windows.Forms.MessageBox>, wenn Sie eine Zahlentaste drücken, während das <xref:System.Windows.Forms.TextBox> den Fokus besitzt, mit der Ausgabe von <xref:System.Windows.Forms.MessageBox>, wenn sie eine Zahlentaste drücken, während eines der andere Steuerelemente den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="87f17-112">Compare the <xref:System.Windows.Forms.MessageBox> output when you press a number key while the <xref:System.Windows.Forms.TextBox> has focus with the <xref:System.Windows.Forms.MessageBox> output when you press a number key while focus is on one of the other controls.</span></span>  
  
 [!code-cpp[System.Windows.Forms.KeyBoardInputForm#0](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/cpp/form1.cpp#0)]
 [!code-csharp[System.Windows.Forms.KeyBoardInputForm#0](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.KeyBoardInputForm#0](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="87f17-113">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="87f17-113">Compiling the Code</span></span>  
 <span data-ttu-id="87f17-114">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="87f17-114">This example requires:</span></span>  
  
-   <span data-ttu-id="87f17-115">Verweise auf die Assemblys "System", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="87f17-115">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="87f17-116">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="87f17-116">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="87f17-117">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="87f17-117">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="87f17-118">Siehe auch: [Vorgehensweise Kompilieren und Ausführen eines vollständigen Windows Forms-Codebeispiels mit Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="87f17-118">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87f17-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="87f17-119">See Also</span></span>  
 [<span data-ttu-id="87f17-120">Tastatureingaben in einer Windows Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="87f17-120">Keyboard Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)
