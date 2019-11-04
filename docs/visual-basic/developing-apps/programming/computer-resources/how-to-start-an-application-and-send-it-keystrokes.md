---
title: 'Vorgehensweise: Starten von Anwendungen und Senden von Tastatureingaben – Visual Basic'
ms.date: 10/23/2019
helpviewer_keywords:
- keystrokes, sending
- Shell command example [Visual Basic]
- processes, starting and sending keystrokes
- SendKeys.SendWait examples
ms.assetid: f1303184-fce4-44fb-88b4-aac5f42d5d77
ms.openlocfilehash: 033999c07bb5839a264122b2ca330916bdf844b8
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2019
ms.locfileid: "72919390"
---
# <a name="how-to-start-an-application-and-send-it-keystrokes-visual-basic"></a><span data-ttu-id="6bcea-102">Vorgehensweise: Starten von Anwendungen und Senden von Tastatureingaben (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6bcea-102">How to: start an application and send it keystrokes (Visual Basic)</span></span>

<span data-ttu-id="6bcea-103">In diesem Beispiel wird die <xref:Microsoft.VisualBasic.Interaction.Shell%2A>-Methode verwendet, um die Editor-Anwendung zu starten, und dann wird ein Satz gedruckt, indem mithilfe der [My.Computer.Keyboard.SendKeys](xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A)-Methode Tastatureingaben gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="6bcea-103">This example uses the <xref:Microsoft.VisualBasic.Interaction.Shell%2A> method to start the Notepad application and then prints a sentence by sending keystrokes using the [My.Computer.Keyboard.SendKeys](xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A) method.</span></span>

## <a name="example"></a><span data-ttu-id="6bcea-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6bcea-104">Example</span></span>

[!code-vb[VbVbalrMyComputer#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#25)]

## <a name="robust-programming"></a><span data-ttu-id="6bcea-105">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="6bcea-105">Robust programming</span></span>

<span data-ttu-id="6bcea-106">Eine <xref:System.ArgumentException>-Ausnahme wird ausgegeben, wenn eine Anwendung mit dem angeforderten Prozessbezeichner nicht gefunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="6bcea-106">An <xref:System.ArgumentException> exception is raised if an application with the requested process identifier cannot be found.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="6bcea-107">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="6bcea-107">.NET Framework Security</span></span>

<span data-ttu-id="6bcea-108">Ein Aufruf der `Shell`-Funktion erfordert volles Vertrauen (<xref:System.Security.SecurityException>-Klasse).</span><span class="sxs-lookup"><span data-stu-id="6bcea-108">The call to the `Shell` function requires full trust (<xref:System.Security.SecurityException> class).</span></span>

## <a name="see-also"></a><span data-ttu-id="6bcea-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6bcea-109">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A>
- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>
