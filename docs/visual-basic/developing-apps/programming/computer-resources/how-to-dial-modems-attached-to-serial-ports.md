---
title: 'Vorgehensweise: Wählen mit Modems an seriellen Anschlüssen in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- modems [Visual Basic], dialing
- serial ports [Visual Basic], dialing
- My.Computer.Ports object
ms.assetid: 3834db40-f431-45f1-b671-dc91787164b6
ms.openlocfilehash: db482af7750012d8805d4f834063a2c82224cf67
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59337031"
---
# <a name="how-to-dial-modems-attached-to-serial-ports-in-visual-basic"></a><span data-ttu-id="e81cb-102">Vorgehensweise: Wählen mit Modems an seriellen Anschlüssen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e81cb-102">How to: Dial Modems Attached to Serial Ports in Visual Basic</span></span>
<span data-ttu-id="e81cb-103">In diesem Thema wird beschrieben, wie Sie `My.Computer.Ports` nutzen, um ein Modem in Visual Basic anzuwählen.</span><span class="sxs-lookup"><span data-stu-id="e81cb-103">This topic describes how to use `My.Computer.Ports` to dial a modem in Visual Basic.</span></span>  
  
 <span data-ttu-id="e81cb-104">In der Regel ist das Modem mit einem der seriellen Anschlüsse am Computer verbunden.</span><span class="sxs-lookup"><span data-stu-id="e81cb-104">Typically, the modem is connected to one of the serial ports on the computer.</span></span> <span data-ttu-id="e81cb-105">Damit die Anwendung mit dem Modem kommunizieren kann, muss sie Befehle an den entsprechenden seriellen Anschluss senden.</span><span class="sxs-lookup"><span data-stu-id="e81cb-105">For your application to communicate with the modem, it must send commands to the appropriate serial port.</span></span>  
  
### <a name="to-dial-a-modem"></a><span data-ttu-id="e81cb-106">So wählen Sie ein Modem an</span><span class="sxs-lookup"><span data-stu-id="e81cb-106">To dial a modem</span></span>  
  
1. <span data-ttu-id="e81cb-107">Ermitteln Sie den seriellen Anschluss, mit dem das Modem verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="e81cb-107">Determine which serial port the modem is connected to.</span></span> <span data-ttu-id="e81cb-108">In diesem Beispiel wird davon ausgegangen, dass das Modem mit COM1 verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="e81cb-108">This example assumes the modem is on COM1.</span></span>  
  
2. <span data-ttu-id="e81cb-109">Verwenden Sie die `My.Computer.Ports.OpenSerialPort`-Methode, um einen Verweis auf den Port abzurufen.</span><span class="sxs-lookup"><span data-stu-id="e81cb-109">Use the `My.Computer.Ports.OpenSerialPort` method to obtain a reference to the port.</span></span> <span data-ttu-id="e81cb-110">Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span><span class="sxs-lookup"><span data-stu-id="e81cb-110">For more information, see <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span></span>  
  
     <span data-ttu-id="e81cb-111">Der `Using`-Block ermöglicht es der Anwendung, den seriellen Port auch dann zu schließen, wenn eine Ausnahme generiert wird.</span><span class="sxs-lookup"><span data-stu-id="e81cb-111">The `Using` block allows the application to close the serial port even if it generates an exception.</span></span> <span data-ttu-id="e81cb-112">Sämtlicher Code, der den seriellen Anschluss ändert, sollte in diesem Block oder in einem `Try...Catch...Finally`-Block angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e81cb-112">All code that manipulates the serial port should appear within this block, or within a `Try...Catch...Finally` block.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#28)]  
  
3. <span data-ttu-id="e81cb-113">Legen Sie die `DtrEnable`-Eigenschaft fest, um anzugeben, dass der Computer für eine eingehende Übertragung vom Modem empfangsbereit ist.</span><span class="sxs-lookup"><span data-stu-id="e81cb-113">Set the `DtrEnable` property to indicate that the computer is ready to accept an incoming transmission from the modem.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#29)]  
  
4. <span data-ttu-id="e81cb-114">Senden Sie den Wählbefehl und die Telefonnummer mithilfe der <xref:System.IO.Ports.SerialPort.Write%2A>-Methode über den seriellen Anschluss an das Modem.</span><span class="sxs-lookup"><span data-stu-id="e81cb-114">Send the dial command and the phone number to the modem through the serial port by means of the <xref:System.IO.Ports.SerialPort.Write%2A> method.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#30)]  
  
## <a name="example"></a><span data-ttu-id="e81cb-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e81cb-115">Example</span></span>  
 [!code-vb[VbVbalrMyComputer#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#27)]  
  
 <span data-ttu-id="e81cb-116">Dieses Codebeispiel ist auch als IntelliSense-Codeausschnitt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e81cb-116">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="e81cb-117">In der Codeausschnittauswahl ist er unter **Konnektivität und Netzwerk** zu finden.</span><span class="sxs-lookup"><span data-stu-id="e81cb-117">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="e81cb-118">Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="e81cb-118">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e81cb-119">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="e81cb-119">Compiling the Code</span></span>  
 <span data-ttu-id="e81cb-120">Für das Beispiel wird ein Verweis auf den <xref:System?displayProperty=nameWithType>-Namespace benötigt.</span><span class="sxs-lookup"><span data-stu-id="e81cb-120">This example requires a reference to the <xref:System?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="e81cb-121">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="e81cb-121">Robust Programming</span></span>  
 <span data-ttu-id="e81cb-122">In diesem Beispiel wird davon ausgegangen, dass das Modem mit COM1 verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="e81cb-122">This example assumes the modem is connected to COM1.</span></span> <span data-ttu-id="e81cb-123">Der Code sollte dem Benutzer erlauben, den gewünschten seriellen Anschluss aus einer Liste der verfügbaren Anschlüsse auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="e81cb-123">We recommend that your code allow the user to select the desired serial port from a list of available ports.</span></span> <span data-ttu-id="e81cb-124">Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen von verfügbaren seriellen Anschlüssen](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).</span><span class="sxs-lookup"><span data-stu-id="e81cb-124">For more information, see [How to: Show Available Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).</span></span>  
  
 <span data-ttu-id="e81cb-125">Dieses Beispiel verwendet einen `Using`-Block, um sicherzustellen, dass die Anwendung den Anschluss auch dann schließt, wenn eine Ausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="e81cb-125">This example uses a `Using` block to make sure that the application closes the port even if it throws an exception.</span></span> <span data-ttu-id="e81cb-126">Weitere Informationen finden Sie unter [using-Anweisung](../../../../visual-basic/language-reference/statements/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e81cb-126">For more information, see [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
 <span data-ttu-id="e81cb-127">In diesem Beispiel trennt die Anwendung den seriellen Anschluss, nachdem sie das Modem anwählt.</span><span class="sxs-lookup"><span data-stu-id="e81cb-127">In this example, the application disconnects the serial port after it dials the modem.</span></span> <span data-ttu-id="e81cb-128">In der Praxis ist es erwünscht, dass Daten von und an das Modem übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="e81cb-128">Realistically, you will want to transfer data to and from the modem.</span></span> <span data-ttu-id="e81cb-129">Weitere Informationen finden Sie unter [Vorgehensweise: Empfangen von Zeichenfolgen von seriellen Anschlüssen](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md).</span><span class="sxs-lookup"><span data-stu-id="e81cb-129">For more information, see [How to: Receive Strings From Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e81cb-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e81cb-130">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Ports>
- <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>
- [<span data-ttu-id="e81cb-131">Vorgehensweise: Senden von Zeichenfolgen an serielle Anschlüsse</span><span class="sxs-lookup"><span data-stu-id="e81cb-131">How to: Send Strings to Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md)
- [<span data-ttu-id="e81cb-132">Vorgehensweise: Empfangen von Zeichenfolgen von seriellen Anschlüssen</span><span class="sxs-lookup"><span data-stu-id="e81cb-132">How to: Receive Strings From Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md)
- [<span data-ttu-id="e81cb-133">Vorgehensweise: Anzeigen von verfügbaren seriellen Anschlüssen</span><span class="sxs-lookup"><span data-stu-id="e81cb-133">How to: Show Available Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)
