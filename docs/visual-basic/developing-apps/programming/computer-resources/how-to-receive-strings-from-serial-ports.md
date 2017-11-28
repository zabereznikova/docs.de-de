---
title: "Gewusst wie: Empfangen von Zeichenfolgen von seriellen Anschlüssen in Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- serial ports, retrieving strings
- strings [Visual Basic], retrieving from serial ports
- My.Resources object
ms.assetid: 8371ce2c-e1c7-476b-a86d-9afc2614b6b7
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6939dee58051e9a97fa704f063f35ff0ac440036
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-receive-strings-from-serial-ports-in-visual-basic"></a><span data-ttu-id="276e8-102">Gewusst wie: Empfangen von Zeichenfolgen von seriellen Anschlüssen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="276e8-102">How to: Receive Strings From Serial Ports in Visual Basic</span></span>
<span data-ttu-id="276e8-103">Dieses Thema beschreibt, wie `My.Computer.Ports` zum Empfangen von Zeichenfolgen von seriellen Anschlüssen des Computers in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="276e8-103">This topic describes how to use `My.Computer.Ports` to receive strings from the computer's serial ports in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
### <a name="to-receive-strings-from-the-serial-port"></a><span data-ttu-id="276e8-104">So werden Zeichenfolgen von seriellen Anschlüssen empfangen</span><span class="sxs-lookup"><span data-stu-id="276e8-104">To receive strings from the serial port</span></span>  
  
1.  <span data-ttu-id="276e8-105">Initialisieren Sie die zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="276e8-105">Initialize the return string.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#38](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_1.vb)]  
  
2.  <span data-ttu-id="276e8-106">Bestimmen Sie, welcher serielle Anschluss die Zeichenfolgen bereitstellen soll.</span><span class="sxs-lookup"><span data-stu-id="276e8-106">Determine which serial port should provide the strings.</span></span> <span data-ttu-id="276e8-107">In diesem Beispiel wird vorausgesetzt, dass es `COM1` ist.</span><span class="sxs-lookup"><span data-stu-id="276e8-107">This example assumes it is `COM1`.</span></span>  
  
3.  <span data-ttu-id="276e8-108">Verwenden Sie die `My.Computer.Ports.OpenSerialPort`-Methode, um einen Verweis auf den Port abzurufen.</span><span class="sxs-lookup"><span data-stu-id="276e8-108">Use the `My.Computer.Ports.OpenSerialPort` method to obtain a reference to the port.</span></span> <span data-ttu-id="276e8-109">Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span><span class="sxs-lookup"><span data-stu-id="276e8-109">For more information, see <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span></span>  
  
     <span data-ttu-id="276e8-110">Der `Try...Catch...Finally`-Block ermöglicht es der Anwendung, den seriellen Port auch dann zu schließen, wenn eine Ausnahme generiert wird.</span><span class="sxs-lookup"><span data-stu-id="276e8-110">The `Try...Catch...Finally` block allows the application to close the serial port even if it generates an exception.</span></span> <span data-ttu-id="276e8-111">Sämtlicher Code, der den seriellen Anschluss ändert, sollte in diesem Block angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="276e8-111">All code that manipulates the serial port should appear within this block.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#39](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_2.vb)]  
  
4.  <span data-ttu-id="276e8-112">Erstellen Sie eine `Do`-Schleife für das Lesen von Textzeilen, bis keine weiteren Zeilen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="276e8-112">Create a `Do` loop for reading lines of text until no more lines are available.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#40](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_3.vb)]  
  
5.  <span data-ttu-id="276e8-113">Verwenden Sie die <xref:System.IO.Ports.SerialPort.ReadLine%2A>-Methode, um die nächste verfügbare Textzeile aus dem seriellen Anschluss auszulesen.</span><span class="sxs-lookup"><span data-stu-id="276e8-113">Use the <xref:System.IO.Ports.SerialPort.ReadLine%2A> method to read the next available line of text from the serial port.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#41](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_4.vb)]  
  
6.  <span data-ttu-id="276e8-114">Verwenden Sie eine `If`-Anweisung, um zu ermitteln, ob die <xref:System.IO.Ports.SerialPort.ReadLine%2A>-Methode `Nothing` zurückgibt (was bedeutet, dass kein weiterer Text mehr verfügbar ist).</span><span class="sxs-lookup"><span data-stu-id="276e8-114">Use an `If` statement to determine if the <xref:System.IO.Ports.SerialPort.ReadLine%2A> method returns `Nothing` (which means no more text is available).</span></span> <span data-ttu-id="276e8-115">Wenn sie `Nothing` zurückgibt, beenden Sie die `Do`-Schleife.</span><span class="sxs-lookup"><span data-stu-id="276e8-115">If it does return `Nothing`, exit the `Do` loop.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#42](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_5.vb)]  
  
7.  <span data-ttu-id="276e8-116">Fügen Sie einen `Else`-Block zur `If`-Anweisung hinzu, um den Fall so zu behandeln, als würde die Zeichenfolge tatsächlich gelesen.</span><span class="sxs-lookup"><span data-stu-id="276e8-116">Add an `Else` block to the `If` statement to handle the case if the string is actually read.</span></span> <span data-ttu-id="276e8-117">Der Block fügt die Zeichenfolge vom seriellen Anschluss an die Rückgabezeichenfolge an.</span><span class="sxs-lookup"><span data-stu-id="276e8-117">The block appends the string from the serial port to the return string.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#43](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_6.vb)]  
  
8.  <span data-ttu-id="276e8-118">Gibt die Zeichenfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="276e8-118">Return the string.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#44](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_7.vb)]  
  
## <a name="example"></a><span data-ttu-id="276e8-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="276e8-119">Example</span></span>  
 [!code-vb[VbVbalrMyComputer#37](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_8.vb)]  
  
 <span data-ttu-id="276e8-120">Dieses Codebeispiel ist auch als IntelliSense-Codeausschnitt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="276e8-120">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="276e8-121">In der Codeausschnittauswahl ist er unter **Konnektivität und Netzwerk** zu finden.</span><span class="sxs-lookup"><span data-stu-id="276e8-121">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="276e8-122">Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="276e8-122">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="276e8-123">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="276e8-123">Compiling the Code</span></span>  
 <span data-ttu-id="276e8-124">In diesem Beispiel wird davon ausgegangen, dass der Computer `COM1` verwendet.</span><span class="sxs-lookup"><span data-stu-id="276e8-124">This example assumes the computer is using `COM1`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="276e8-125">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="276e8-125">Robust Programming</span></span>  
 <span data-ttu-id="276e8-126">In diesem Beispiel wird davon ausgegangen, dass der Computer `COM1` verwendet.</span><span class="sxs-lookup"><span data-stu-id="276e8-126">This example assumes the computer is using `COM1`.</span></span> <span data-ttu-id="276e8-127">Der Code sollte dem Benutzer erlauben, den gewünschten seriellen Anschluss aus einer Liste der verfügbaren Anschlüsse auszuwählen, um mehr Flexibilität zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="276e8-127">For more flexibility, the code should allow the user to select the desired serial port from a list of available ports.</span></span> <span data-ttu-id="276e8-128">Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen von verfügbaren seriellen Anschlüssen](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).</span><span class="sxs-lookup"><span data-stu-id="276e8-128">For more information, see [How to: Show Available Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).</span></span>  
  
 <span data-ttu-id="276e8-129">Dieses Beispiel verwendet einen `Try...Catch...Finally`-Block, um sicherzustellen, dass die Anwendung den Anschluss schließt, und um Zeitüberschreitungen zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="276e8-129">This example uses a `Try...Catch...Finally` block to make sure that the application closes the port and to catch any timeout exceptions.</span></span> <span data-ttu-id="276e8-130">Weitere Informationen finden Sie unter [Try...Catch...Finally-Anweisung](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="276e8-130">For more information, see [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="276e8-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="276e8-131">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Devices.Ports>  
 <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>  
 [<span data-ttu-id="276e8-132">Gewusst wie: Wählen mit Modems an seriellen Anschlüssen</span><span class="sxs-lookup"><span data-stu-id="276e8-132">How to: Dial Modems Attached to Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md)  
 [<span data-ttu-id="276e8-133">Gewusst wie: Senden von Zeichenfolgen zu seriellen Anschlüssen</span><span class="sxs-lookup"><span data-stu-id="276e8-133">How to: Send Strings to Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md)  
 [<span data-ttu-id="276e8-134">Gewusst wie: Anzeigen von verfügbaren seriellen Anschlüssen</span><span class="sxs-lookup"><span data-stu-id="276e8-134">How to: Show Available Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)
