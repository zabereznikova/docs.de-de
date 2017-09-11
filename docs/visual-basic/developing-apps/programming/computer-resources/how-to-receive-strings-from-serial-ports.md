---
title: "Gewusst wie: Empfangen von Zeichenfolgen von seriellen Anschlüssen in Visual Basic"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- serial ports, retrieving strings
- strings [Visual Basic], retrieving from serial ports
- My.Resources object
ms.assetid: 8371ce2c-e1c7-476b-a86d-9afc2614b6b7
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 500a6c651f6eb991eb9fefef601d0f593a38352f
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-receive-strings-from-serial-ports-in-visual-basic"></a><span data-ttu-id="c90da-102">Gewusst wie: Empfangen von Zeichenfolgen von seriellen Anschlüssen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c90da-102">How to: Receive Strings From Serial Ports in Visual Basic</span></span>
<span data-ttu-id="c90da-103">Dieses Thema beschreibt, wie `My.Computer.Ports` zum Empfangen von Zeichenfolgen von seriellen Anschlüssen des Computers in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c90da-103">This topic describes how to use `My.Computer.Ports` to receive strings from the computer's serial ports in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
### <a name="to-receive-strings-from-the-serial-port"></a><span data-ttu-id="c90da-104">So werden Zeichenfolgen von seriellen Anschlüssen empfangen</span><span class="sxs-lookup"><span data-stu-id="c90da-104">To receive strings from the serial port</span></span>  
  
1.  <span data-ttu-id="c90da-105">Initialisieren Sie die zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="c90da-105">Initialize the return string.</span></span>  
  
     <span data-ttu-id="c90da-106">[!code-vb[VbVbalrMyComputer#38](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="c90da-106">[!code-vb[VbVbalrMyComputer#38](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_1.vb)]</span></span>  
  
2.  <span data-ttu-id="c90da-107">Bestimmen Sie, welcher serielle Anschluss die Zeichenfolgen bereitstellen soll.</span><span class="sxs-lookup"><span data-stu-id="c90da-107">Determine which serial port should provide the strings.</span></span> <span data-ttu-id="c90da-108">In diesem Beispiel wird vorausgesetzt, dass es `COM1` ist.</span><span class="sxs-lookup"><span data-stu-id="c90da-108">This example assumes it is `COM1`.</span></span>  
  
3.  <span data-ttu-id="c90da-109">Verwenden Sie die `My.Computer.Ports.OpenSerialPort`-Methode, um einen Verweis auf den Port abzurufen.</span><span class="sxs-lookup"><span data-stu-id="c90da-109">Use the `My.Computer.Ports.OpenSerialPort` method to obtain a reference to the port.</span></span> <span data-ttu-id="c90da-110">Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span><span class="sxs-lookup"><span data-stu-id="c90da-110">For more information, see <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span></span>  
  
     <span data-ttu-id="c90da-111">Der `Try...Catch...Finally`-Block ermöglicht es der Anwendung, den seriellen Port auch dann zu schließen, wenn eine Ausnahme generiert wird.</span><span class="sxs-lookup"><span data-stu-id="c90da-111">The `Try...Catch...Finally` block allows the application to close the serial port even if it generates an exception.</span></span> <span data-ttu-id="c90da-112">Sämtlicher Code, der den seriellen Anschluss ändert, sollte in diesem Block angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c90da-112">All code that manipulates the serial port should appear within this block.</span></span>  
  
     <span data-ttu-id="c90da-113">[!code-vb[VbVbalrMyComputer#39](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="c90da-113">[!code-vb[VbVbalrMyComputer#39](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_2.vb)]</span></span>  
  
4.  <span data-ttu-id="c90da-114">Erstellen Sie eine `Do`-Schleife für das Lesen von Textzeilen, bis keine weiteren Zeilen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="c90da-114">Create a `Do` loop for reading lines of text until no more lines are available.</span></span>  
  
     <span data-ttu-id="c90da-115">[!code-vb[VbVbalrMyComputer#40](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="c90da-115">[!code-vb[VbVbalrMyComputer#40](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_3.vb)]</span></span>  
  
5.  <span data-ttu-id="c90da-116">Verwenden Sie die <xref:System.IO.Ports.SerialPort.ReadLine%2A>-Methode, um die nächste verfügbare Textzeile aus dem seriellen Anschluss auszulesen.</span><span class="sxs-lookup"><span data-stu-id="c90da-116">Use the <xref:System.IO.Ports.SerialPort.ReadLine%2A> method to read the next available line of text from the serial port.</span></span>  
  
     <span data-ttu-id="c90da-117">[!code-vb[VbVbalrMyComputer#41](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="c90da-117">[!code-vb[VbVbalrMyComputer#41](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_4.vb)]</span></span>  
  
6.  <span data-ttu-id="c90da-118">Verwenden Sie eine `If`-Anweisung, um zu ermitteln, ob die <xref:System.IO.Ports.SerialPort.ReadLine%2A>-Methode `Nothing` zurückgibt (was bedeutet, dass kein weiterer Text mehr verfügbar ist).</span><span class="sxs-lookup"><span data-stu-id="c90da-118">Use an `If` statement to determine if the <xref:System.IO.Ports.SerialPort.ReadLine%2A> method returns `Nothing` (which means no more text is available).</span></span> <span data-ttu-id="c90da-119">Wenn sie `Nothing` zurückgibt, beenden Sie die `Do`-Schleife.</span><span class="sxs-lookup"><span data-stu-id="c90da-119">If it does return `Nothing`, exit the `Do` loop.</span></span>  
  
     <span data-ttu-id="c90da-120">[!code-vb[VbVbalrMyComputer#42](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="c90da-120">[!code-vb[VbVbalrMyComputer#42](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_5.vb)]</span></span>  
  
7.  <span data-ttu-id="c90da-121">Fügen Sie einen `Else`-Block zur `If`-Anweisung hinzu, um den Fall so zu behandeln, als würde die Zeichenfolge tatsächlich gelesen.</span><span class="sxs-lookup"><span data-stu-id="c90da-121">Add an `Else` block to the `If` statement to handle the case if the string is actually read.</span></span> <span data-ttu-id="c90da-122">Der Block fügt die Zeichenfolge vom seriellen Anschluss an die Rückgabezeichenfolge an.</span><span class="sxs-lookup"><span data-stu-id="c90da-122">The block appends the string from the serial port to the return string.</span></span>  
  
     <span data-ttu-id="c90da-123">[!code-vb[VbVbalrMyComputer#43](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="c90da-123">[!code-vb[VbVbalrMyComputer#43](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_6.vb)]</span></span>  
  
8.  <span data-ttu-id="c90da-124">Gibt die Zeichenfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="c90da-124">Return the string.</span></span>  
  
     <span data-ttu-id="c90da-125">[!code-vb[VbVbalrMyComputer#44](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="c90da-125">[!code-vb[VbVbalrMyComputer#44](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_7.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="c90da-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c90da-126">Example</span></span>  
 <span data-ttu-id="c90da-127">[!code-vb[VbVbalrMyComputer#37](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="c90da-127">[!code-vb[VbVbalrMyComputer#37](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_8.vb)]</span></span>  
  
 <span data-ttu-id="c90da-128">Dieses Codebeispiel ist auch als IntelliSense-Codeausschnitt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c90da-128">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="c90da-129">In der Codeausschnittauswahl ist er unter **Konnektivität und Netzwerk** zu finden.</span><span class="sxs-lookup"><span data-stu-id="c90da-129">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="c90da-130">Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="c90da-130">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c90da-131">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="c90da-131">Compiling the Code</span></span>  
 <span data-ttu-id="c90da-132">In diesem Beispiel wird davon ausgegangen, dass der Computer `COM1` verwendet.</span><span class="sxs-lookup"><span data-stu-id="c90da-132">This example assumes the computer is using `COM1`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="c90da-133">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="c90da-133">Robust Programming</span></span>  
 <span data-ttu-id="c90da-134">In diesem Beispiel wird davon ausgegangen, dass der Computer `COM1` verwendet.</span><span class="sxs-lookup"><span data-stu-id="c90da-134">This example assumes the computer is using `COM1`.</span></span> <span data-ttu-id="c90da-135">Der Code sollte dem Benutzer erlauben, den gewünschten seriellen Anschluss aus einer Liste der verfügbaren Anschlüsse auszuwählen, um mehr Flexibilität zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="c90da-135">For more flexibility, the code should allow the user to select the desired serial port from a list of available ports.</span></span> <span data-ttu-id="c90da-136">Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen von verfügbaren seriellen Anschlüssen](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).</span><span class="sxs-lookup"><span data-stu-id="c90da-136">For more information, see [How to: Show Available Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).</span></span>  
  
 <span data-ttu-id="c90da-137">Dieses Beispiel verwendet einen `Try...Catch...Finally`-Block, um sicherzustellen, dass die Anwendung den Anschluss schließt, und um Zeitüberschreitungen zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="c90da-137">This example uses a `Try...Catch...Finally` block to make sure that the application closes the port and to catch any timeout exceptions.</span></span> <span data-ttu-id="c90da-138">Weitere Informationen finden Sie unter [Try...Catch...Finally-Anweisung](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c90da-138">For more information, see [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c90da-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c90da-139">See Also</span></span>  
 <span data-ttu-id="c90da-140"><xref:Microsoft.VisualBasic.Devices.Ports></span><span class="sxs-lookup"><span data-stu-id="c90da-140"><xref:Microsoft.VisualBasic.Devices.Ports></span></span>   
 <span data-ttu-id="c90da-141"><xref:System.IO.Ports.SerialPort?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c90da-141"><xref:System.IO.Ports.SerialPort?displayProperty=fullName></span></span>   
 <span data-ttu-id="c90da-142">[Vorgehensweise: Wählen mit Modems an seriellen Anschlüssen](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md) </span><span class="sxs-lookup"><span data-stu-id="c90da-142">[How to: Dial Modems Attached to Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md) </span></span>  
 <span data-ttu-id="c90da-143">[Vorgehensweise: Senden von Zeichenfolgen zu seriellen Anschlüssen](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md) </span><span class="sxs-lookup"><span data-stu-id="c90da-143">[How to: Send Strings to Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md) </span></span>  
 [<span data-ttu-id="c90da-144">Gewusst wie: Anzeigen von verfügbaren seriellen Anschlüssen</span><span class="sxs-lookup"><span data-stu-id="c90da-144">How to: Show Available Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)

