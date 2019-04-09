---
title: 'Vorgehensweise: Ändern von Tastatureingaben in ein Standardsteuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyboard input [Windows Forms], modifying
- modifying keyboard input
- Windows Forms, modifying keyboard input
- keyboards [Windows Forms], keyboard input
ms.assetid: 626d3712-d866-4988-bcda-a2d5b36ec0ba
ms.openlocfilehash: 81d33234670fb8ae5445cc86a79f5c3b6a647a03
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225780"
---
# <a name="how-to-modify-keyboard-input-to-a-standard-control"></a><span data-ttu-id="93a61-102">Vorgehensweise: Ändern von Tastatureingaben in ein Standardsteuerelement</span><span class="sxs-lookup"><span data-stu-id="93a61-102">How to: Modify Keyboard Input to a Standard Control</span></span>
<span data-ttu-id="93a61-103">Windows Forms bietet die Möglichkeit, Tastatureingaben zu nutzen und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="93a61-103">Windows Forms provides the ability to consume and modify keyboard input.</span></span> <span data-ttu-id="93a61-104">Nutzen einer Taste bezieht sich auf die Behandlung einer Taste innerhalb einer Methode oder eines Ereignishandlers, sodass andere Methoden und Ereignisse weiter unten in der Meldungswarteschlange den Tastenwert nicht empfangen.</span><span class="sxs-lookup"><span data-stu-id="93a61-104">Consuming a key refers to handling a key within a method or event handler so that other methods and events further down the message queue do not receive the key value.</span></span> <span data-ttu-id="93a61-105">Ändern einer Taste bezieht sich auf ein Ändern des Werts einer Taste, sodass Methoden und Ereignishandler weiter unten in der Meldungswarteschlange einen anderen Tastenwert empfangen.</span><span class="sxs-lookup"><span data-stu-id="93a61-105">Modifying a key refers to modifying the value of a key so that methods and event handlers further down the message queue receive a different key value.</span></span> <span data-ttu-id="93a61-106">In diesem Thema wird gezeigt, wie Sie diese Aufgaben ausführen.</span><span class="sxs-lookup"><span data-stu-id="93a61-106">This topic shows how to accomplish these tasks.</span></span>  
  
### <a name="to-consume-a-key"></a><span data-ttu-id="93a61-107">So nutzen Sie eine Taste</span><span class="sxs-lookup"><span data-stu-id="93a61-107">To consume a key</span></span>  
  
-   <span data-ttu-id="93a61-108">Legen Sie in einem <xref:System.Windows.Forms.Control.KeyPress>-Ereignishandler die <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A>-Eigenschaft der <xref:System.Windows.Forms.KeyPressEventArgs>-Klasse auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="93a61-108">In a <xref:System.Windows.Forms.Control.KeyPress> event handler, set the <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> property of the <xref:System.Windows.Forms.KeyPressEventArgs> class to `true`.</span></span>  
  
     <span data-ttu-id="93a61-109">- oder - </span><span class="sxs-lookup"><span data-stu-id="93a61-109">-or-</span></span>  
  
     <span data-ttu-id="93a61-110">Legen Sie in einem <xref:System.Windows.Forms.Control.KeyDown>-Ereignishandler die <xref:System.Windows.Forms.KeyEventArgs.Handled%2A>-Eigenschaft der <xref:System.Windows.Forms.KeyEventArgs>-Klasse auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="93a61-110">In a <xref:System.Windows.Forms.Control.KeyDown> event handler, set the <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> property of the <xref:System.Windows.Forms.KeyEventArgs> class to `true`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="93a61-111">Ein Festlegen der <xref:System.Windows.Forms.KeyEventArgs.Handled%2A>-Eigenschaft im <xref:System.Windows.Forms.Control.KeyDown>-Ereignishandler verhindert nicht, dass das <xref:System.Windows.Forms.Control.KeyPress>- und das <xref:System.Windows.Forms.Control.KeyUp>-Ereignis für die aktuelle Tastatureingabe ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="93a61-111">Setting the <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> property in the <xref:System.Windows.Forms.Control.KeyDown> event handler does not prevent the <xref:System.Windows.Forms.Control.KeyPress> and <xref:System.Windows.Forms.Control.KeyUp> events from being raised for the current keystroke.</span></span> <span data-ttu-id="93a61-112">Verwenden Sie die <xref:System.Windows.Forms.KeyEventArgs.SuppressKeyPress%2A>-Eigenschaft für diesen Zweck.</span><span class="sxs-lookup"><span data-stu-id="93a61-112">Use the <xref:System.Windows.Forms.KeyEventArgs.SuppressKeyPress%2A> property for this purpose.</span></span>  
  
     <span data-ttu-id="93a61-113">Das folgende Beispiel ist ein Auszug aus einer `switch`-Anweisung, von der die <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A>-Eigenschaft der <xref:System.Windows.Forms.KeyPressEventArgs>-Klasse ausgewertet wird, die von einem <xref:System.Windows.Forms.Control.KeyPress>-Ereignishandler empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="93a61-113">The following example is an excerpt from a `switch` statement that examines the <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> property of the <xref:System.Windows.Forms.KeyPressEventArgs> received by a <xref:System.Windows.Forms.Control.KeyPress> event handler.</span></span> <span data-ttu-id="93a61-114">In diesem Code werden die Zeichentasten 'A' und 'a' genutzt.</span><span class="sxs-lookup"><span data-stu-id="93a61-114">This code consumes the 'A' and 'a' character keys.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyBoardInput#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#6)]
     [!code-vb[System.Windows.Forms.KeyBoardInput#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#6)]  
  
### <a name="to-modify-a-standard-character-key"></a><span data-ttu-id="93a61-115">So ändern Sie eine Standardzeichentaste</span><span class="sxs-lookup"><span data-stu-id="93a61-115">To modify a standard character key</span></span>  
  
-   <span data-ttu-id="93a61-116">Legen Sie in einem <xref:System.Windows.Forms.Control.KeyPress>-Ereignishandler die <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A>-Eigenschaft der <xref:System.Windows.Forms.KeyPressEventArgs>-Klasse auf den Wert der neuen Zeichentaste fest.</span><span class="sxs-lookup"><span data-stu-id="93a61-116">In a <xref:System.Windows.Forms.Control.KeyPress> event handler, set the <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> property of the <xref:System.Windows.Forms.KeyPressEventArgs> class to the value of the new character key.</span></span>  
  
     <span data-ttu-id="93a61-117">Das folgende Beispiel ist ein Auszug aus einer `switch`-Anweisung, in der 'B' in 'A' und 'b' in 'a' geändert wird.</span><span class="sxs-lookup"><span data-stu-id="93a61-117">The following example is an excerpt from a `switch` statement that modifies 'B' to 'A' and 'b' to 'a'.</span></span> <span data-ttu-id="93a61-118">Beachten Sie, dass die <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A>-Eigenschaft des <xref:System.Windows.Forms.KeyPressEventArgs>-Parameters auf `false` festgelegt wird, sodass der neue Tastenwert an andere Methoden und Ereignisse in der Meldungswarteschlange weitergegeben wird.</span><span class="sxs-lookup"><span data-stu-id="93a61-118">Note that the <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> property of the <xref:System.Windows.Forms.KeyPressEventArgs> parameter is set to `false`, so that the new key value is propagated to other methods and events in the message queue.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyBoardInput#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#7)]
     [!code-vb[System.Windows.Forms.KeyBoardInput#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#7)]  
  
### <a name="to-modify-a-noncharacter-key"></a><span data-ttu-id="93a61-119">So ändern Sie eine Nicht-Zeichentaste</span><span class="sxs-lookup"><span data-stu-id="93a61-119">To modify a noncharacter key</span></span>  
  
-   <span data-ttu-id="93a61-120">Überschreiben Sie eine <xref:System.Windows.Forms.Control>-Methode, von der Windows-Meldungen verarbeitet werden, suchen Sie die Meldung WM_KEYDOWN oder WM_SYSKEYDOWN, und legen Sie die <xref:System.Windows.Forms.Message.WParam%2A>-Eigenschaft des <xref:System.Windows.Forms.Message>-Parameters auf den <xref:System.Windows.Forms.Keys>-Wert fest, der den neuen Wert der Nicht-Zeichentaste darstellt.</span><span class="sxs-lookup"><span data-stu-id="93a61-120">Override a <xref:System.Windows.Forms.Control> method that processes Windows messages, detect the WM_KEYDOWN or WM_SYSKEYDOWN message, and set the <xref:System.Windows.Forms.Message.WParam%2A> property of the <xref:System.Windows.Forms.Message> parameter to the <xref:System.Windows.Forms.Keys> value that represents the new noncharacter key.</span></span>  
  
     <span data-ttu-id="93a61-121">Im folgenden Codebeispiel wird veranschaulicht, wie Sie die <xref:System.Windows.Forms.Control.PreProcessMessage%2A>-Methode eines Steuerelements überschreiben, um die Tasten F1 bis F9 zu erkennen und jede Betätigung der Taste F3 in F1 zu ändern.</span><span class="sxs-lookup"><span data-stu-id="93a61-121">The following code example demonstrates how to override the <xref:System.Windows.Forms.Control.PreProcessMessage%2A> method of a control to detect keys F1 through F9 and modify any F3 key press to F1.</span></span> <span data-ttu-id="93a61-122">Weitere Informationen zu <xref:System.Windows.Forms.Control> Methoden, die Sie zum Abfangen von tastaturmeldungen überschreiben können, finden Sie unter [Benutzereingaben in Windows Forms-Anwendungen](user-input-in-a-windows-forms-application.md) und [Funktionsweise von Tastatureingaben](how-keyboard-input-works.md).</span><span class="sxs-lookup"><span data-stu-id="93a61-122">For more information on <xref:System.Windows.Forms.Control> methods that you can override to intercept keyboard messages, see [User Input in a Windows Forms Application](user-input-in-a-windows-forms-application.md) and [How Keyboard Input Works](how-keyboard-input-works.md).</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyBoardInput#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#12)]
     [!code-vb[System.Windows.Forms.KeyBoardInput#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="93a61-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="93a61-123">Example</span></span>  
 <span data-ttu-id="93a61-124">Im folgenden Codebeispiel wird die vollständige Anwendung für die Codebeispiele aus den vorherigen Abschnitten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="93a61-124">The following code example is the complete application for the code examples in the previous sections.</span></span> <span data-ttu-id="93a61-125">In der Anwendung wird ein benutzerdefiniertes Steuerelement, das aus der <xref:System.Windows.Forms.TextBox>-Klasse abgeleitet wurde, dazu verwendet, Tastatureingaben zu nutzen und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="93a61-125">The application uses a custom control derived from the <xref:System.Windows.Forms.TextBox> class to consume and modify keyboard input.</span></span>  
  
 [!code-csharp[System.Windows.Forms.KeyBoardInput#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.KeyBoardInput#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="93a61-126">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="93a61-126">Compiling the Code</span></span>  
 <span data-ttu-id="93a61-127">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="93a61-127">This example requires:</span></span>  
  
-   <span data-ttu-id="93a61-128">Verweise auf die Assemblys "System", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="93a61-128">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="93a61-129">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="93a61-129">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="93a61-130">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="93a61-130">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93a61-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="93a61-131">See also</span></span>

- [<span data-ttu-id="93a61-132">Tastatureingaben in einer Windows Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="93a61-132">Keyboard Input in a Windows Forms Application</span></span>](keyboard-input-in-a-windows-forms-application.md)
- [<span data-ttu-id="93a61-133">Benutzereingabe in einer Windows Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="93a61-133">User Input in a Windows Forms Application</span></span>](user-input-in-a-windows-forms-application.md)
- [<span data-ttu-id="93a61-134">Funktionsweise von Tastatureingaben</span><span class="sxs-lookup"><span data-stu-id="93a61-134">How Keyboard Input Works</span></span>](how-keyboard-input-works.md)
