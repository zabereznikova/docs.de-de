---
title: "Code: Starten von Anwendungen und Senden von Tastatureingaben (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- keystrokes, sending
- Shell command example [Visual Basic]
- processes, starting and sending keystrokes
- SendKeys.SendWait examples
ms.assetid: f1303184-fce4-44fb-88b4-aac5f42d5d77
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8bf92a74bc1b60ea3213d80e4df373936c65d89e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-start-an-application-and-send-it-keystrokes-visual-basic"></a><span data-ttu-id="8fe9b-102">Code: Starten von Anwendungen und Senden von Tastatureingaben (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8fe9b-102">How to: Start an Application and Send it Keystrokes (Visual Basic)</span></span>
<span data-ttu-id="8fe9b-103">In diesem Beispiel wird die `Shell`-Funktion verwendet, um die Anwendung „Rechner“ zu starten und anschließend werden zwei Zahlen multipliziert, indem Sie mithilfe der `My.Computer.Keyboard.SendKeys`-Methode Tastatureingaben senden.</span><span class="sxs-lookup"><span data-stu-id="8fe9b-103">This example uses the `Shell` function to start the calculator application and then multiplies two numbers by sending keystrokes using the `My.Computer.Keyboard.SendKeys` method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8fe9b-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8fe9b-104">Example</span></span>  
 [!code-vb[VbVbalrMyComputer#25](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-start-an-application-and-send-it-keystrokes_1.vb)]  
  
## <a name="robust-programming"></a><span data-ttu-id="8fe9b-105">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="8fe9b-105">Robust Programming</span></span>  
 <span data-ttu-id="8fe9b-106">Eine <xref:System.ArgumentException>-Ausnahme wird ausgegeben, wenn eine Anwendung mit dem angeforderten Prozessbezeichner nicht gefunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="8fe9b-106">A <xref:System.ArgumentException> exception is raised if an application with the requested process identifier cannot be found.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="8fe9b-107">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="8fe9b-107">.NET Framework Security</span></span>  
 <span data-ttu-id="8fe9b-108">Ein Aufruf der `Shell`-Funktion erfordert volles Vertrauen (<xref:System.Security.SecurityException>-Klasse).</span><span class="sxs-lookup"><span data-stu-id="8fe9b-108">The call to the `Shell` function requires full trust (<xref:System.Security.SecurityException> class).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fe9b-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8fe9b-109">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A>  
 <xref:Microsoft.VisualBasic.Interaction.Shell%2A>  
 <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>
