---
title: 'Vorgehensweise: Behandeln von Benutzereingabeereignissen in Windows Forms-Steuerelementen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, user input
- user input [Windows Forms], Windows Forms controls
ms.assetid: 3de74dcf-fae3-42d0-92b5-bc04a61a6888
ms.openlocfilehash: cffcdbbaa988033352b08834e52d603fbebfa870
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64591598"
---
# <a name="how-to-handle-user-input-events-in-windows-forms-controls"></a><span data-ttu-id="fd6a9-102">Vorgehensweise: Behandeln von Benutzereingabeereignissen in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="fd6a9-102">How to: Handle User Input Events in Windows Forms Controls</span></span>
<span data-ttu-id="fd6a9-103">In diesem Beispiel wird veranschaulicht, wie die meisten Tastatur-, Maus-, Fokus- und Validierungsereignisse behandelt werden, die in einem Windows Forms-Steuerelement auftreten können.</span><span class="sxs-lookup"><span data-stu-id="fd6a9-103">This example demonstrates how to handle most keyboard, mouse, focus, and validation events that can occur in a Windows Forms control.</span></span> <span data-ttu-id="fd6a9-104">Das Textfeld `TextBoxInput` empfängt die Ereignisse, wenn es den Fokus besitzt; Informationen zu den einzelnen Ereignissen werden in der Reihenfolge, in der die Ereignisse ausgelöst werden, in das Textfeld `TextBoxOutput` geschrieben.</span><span class="sxs-lookup"><span data-stu-id="fd6a9-104">The text box named `TextBoxInput` receives the events when it has focus, and information about each event is written in the text box named `TextBoxOutput` in the order in which the events are raised.</span></span> <span data-ttu-id="fd6a9-105">Die Anwendung verfügt zudem über eine Reihe von Kontrollkästchen, mit denen gefiltert werden kann, welche Ereignisse gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="fd6a9-105">The application also includes a set of check boxes that can be used to filter which events to report.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd6a9-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fd6a9-106">Example</span></span>  
 [!code-cpp[System.Windows.Forms.UserInputWalkthrough#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/cpp/form1.cpp#0)]
 [!code-csharp[System.Windows.Forms.UserInputWalkthrough#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.UserInputWalkthrough#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fd6a9-107">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="fd6a9-107">Compiling the Code</span></span>  
 <span data-ttu-id="fd6a9-108">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="fd6a9-108">This example requires:</span></span>  
  
- <span data-ttu-id="fd6a9-109">Verweise auf die Assemblys "System", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="fd6a9-109">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="fd6a9-110">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="fd6a9-110">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="fd6a9-111">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="fd6a9-111">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd6a9-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd6a9-112">See also</span></span>

- [<span data-ttu-id="fd6a9-113">Benutzereingaben in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fd6a9-113">User Input in Windows Forms</span></span>](user-input-in-windows-forms.md)
