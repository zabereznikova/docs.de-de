---
title: 'Gewusst wie: Senden von Zeichenfolgen zu seriellen Anschlüssen in Visual Basic'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- ports, sending strings to
- strings [Visual Basic], sending to serial ports
- My.Computer.Ports object
- serial ports, sending strings to
ms.assetid: 6ebf46cd-b2d0-4b2c-9a1f-be177b22ad52
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d796f2d581188fd3753bf3d18b04b2fbeb901945
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-send-strings-to-serial-ports-in-visual-basic"></a><span data-ttu-id="0d7ed-102">Gewusst wie: Senden von Zeichenfolgen zu seriellen Anschlüssen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0d7ed-102">How to: Send Strings to Serial Ports in Visual Basic</span></span>
<span data-ttu-id="0d7ed-103">Dieses Thema beschreibt, wie `My.Computer.Ports` zum Senden von Zeichenfolgen an serielle Ports des Computers in Visual Basic verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0d7ed-103">This topic describes how to use `My.Computer.Ports` to send strings to the computer's serial ports in Visual Basic.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d7ed-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0d7ed-104">Example</span></span>  
 <span data-ttu-id="0d7ed-105">Dieses Beispiel sendet eine Zeichenfolge an den seriellen COM1-Anschluss.</span><span class="sxs-lookup"><span data-stu-id="0d7ed-105">This example sends a string to the COM1 serial port.</span></span> <span data-ttu-id="0d7ed-106">Möglicherweise müssen Sie auf Ihrem Computer einen anderen seriellen Anschluss verwenden.</span><span class="sxs-lookup"><span data-stu-id="0d7ed-106">You may need to use a different serial port on your computer.</span></span>  
  
 <span data-ttu-id="0d7ed-107">Verwenden Sie die `My.Computer.Ports.OpenSerialPort`-Methode, um einen Verweis auf den Port abzurufen.</span><span class="sxs-lookup"><span data-stu-id="0d7ed-107">Use the `My.Computer.Ports.OpenSerialPort` method to obtain a reference to the port.</span></span> <span data-ttu-id="0d7ed-108">Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span><span class="sxs-lookup"><span data-stu-id="0d7ed-108">For more information, see <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span></span>  
  
 <span data-ttu-id="0d7ed-109">Der `Using`-Block ermöglicht es der Anwendung, den seriellen Port auch dann zu schließen, wenn eine Ausnahme generiert wird.</span><span class="sxs-lookup"><span data-stu-id="0d7ed-109">The `Using` block allows the application to close the serial port even if it generates an exception.</span></span> <span data-ttu-id="0d7ed-110">Sämtlicher Code, der den seriellen Anschluss ändert, sollte in diesem Block oder in einem `Try...Catch...Finally`-Block angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="0d7ed-110">All code that manipulates the serial port should appear within this block or within a `Try...Catch...Finally` block.</span></span>  
  
 <span data-ttu-id="0d7ed-111">Die <xref:System.IO.Ports.SerialPort.WriteLine%2A>-Methode sendet die Daten an den seriellen Anschluss.</span><span class="sxs-lookup"><span data-stu-id="0d7ed-111">The <xref:System.IO.Ports.SerialPort.WriteLine%2A> method sends the data to the serial port.</span></span>  
  
 [!code-vb[VbVbalrMyComputer#33](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-send-strings-to-serial-ports_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0d7ed-112">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="0d7ed-112">Compiling the Code</span></span>  
  
-   <span data-ttu-id="0d7ed-113">In diesem Beispiel wird davon ausgegangen, dass der Computer `COM1` verwendet.</span><span class="sxs-lookup"><span data-stu-id="0d7ed-113">This example assumes the computer is using `COM1`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="0d7ed-114">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="0d7ed-114">Robust Programming</span></span>  
 <span data-ttu-id="0d7ed-115">In diesem Beispiel wird davon ausgegangen, dass der Computer `COM1` verwendet; für eine erhöhte Flexibilität sollte der Code es dem Benutzer ermöglichen, den gewünschten seriellen Anschluss aus einer Liste von seriellen Anschlüssen auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="0d7ed-115">This example assumes the computer is using `COM1`; for more flexibility, the code should allow the user to select the desired serial port from a list of available ports.</span></span> <span data-ttu-id="0d7ed-116">Weitere Informationen finden Sie unter [Gewusst wie: Anzeigen von verfügbaren seriellen Anschlüssen](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).</span><span class="sxs-lookup"><span data-stu-id="0d7ed-116">For more information, see [How to: Show Available Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).</span></span>  
  
 <span data-ttu-id="0d7ed-117">Dieses Beispiel verwendet einen `Using`-Block, um sicherzustellen, dass die Anwendung den Anschluss auch dann schließt, wenn eine Ausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="0d7ed-117">This example uses a `Using` block to make sure that the application closes the port even if it throws an exception.</span></span> <span data-ttu-id="0d7ed-118">Weitere Informationen finden Sie unter [using-Anweisung](../../../../visual-basic/language-reference/statements/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0d7ed-118">For more information, see [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d7ed-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0d7ed-119">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Devices.Ports>  
 <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>  
 [<span data-ttu-id="0d7ed-120">Gewusst wie: Wählen mit Modems an seriellen Anschlüssen</span><span class="sxs-lookup"><span data-stu-id="0d7ed-120">How to: Dial Modems Attached to Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md)  
 [<span data-ttu-id="0d7ed-121">Gewusst wie: Anzeigen von verfügbaren seriellen Anschlüssen</span><span class="sxs-lookup"><span data-stu-id="0d7ed-121">How to: Show Available Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)
