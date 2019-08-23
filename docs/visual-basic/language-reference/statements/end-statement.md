---
title: End-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.End
- End
helpviewer_keywords:
- execution [Visual Basic], ending
- files [Visual Basic], closing
- End keyword [Visual Basic], End statements
- programs [Visual Basic], quitting
- code, exiting
- program termination
- End statement [Visual Basic]
- execution [Visual Basic], stopping
ms.assetid: 0e64467c-0f34-4aab-9ddd-43f8b9d55d90
ms.openlocfilehash: 9307cf10e6125441bd49baa0e663a5a13f234005
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944469"
---
# <a name="end-statement"></a><span data-ttu-id="1a459-102">End Statement</span><span class="sxs-lookup"><span data-stu-id="1a459-102">End Statement</span></span>
<span data-ttu-id="1a459-103">Beendet die Ausführung sofort.</span><span class="sxs-lookup"><span data-stu-id="1a459-103">Terminates execution immediately.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a459-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1a459-104">Syntax</span></span>  
  
```  
End  
```  
  
## <a name="remarks"></a><span data-ttu-id="1a459-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1a459-105">Remarks</span></span>  
 <span data-ttu-id="1a459-106">Sie können die `End` -Anweisung an einer beliebigen Stelle in einer Prozedur platzieren, um die Ausführung der gesamten Anwendung zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="1a459-106">You can place the `End` statement anywhere in a procedure to force the entire application to stop running.</span></span> <span data-ttu-id="1a459-107">`End`schließt alle Dateien, die mit `Open` einer-Anweisung geöffnet wurden, und löscht alle Variablen der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="1a459-107">`End` closes any files opened with an `Open` statement and clears all the application's variables.</span></span> <span data-ttu-id="1a459-108">Die Anwendung wird geschlossen, sobald keine anderen Programme Verweise auf Ihre Objekte enthalten und der zugehörige Code nicht mehr ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1a459-108">The application closes as soon as there are no other programs holding references to its objects and none of its code is running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1a459-109">Die `End` -Anweisung beendet die Codeausführung abrupt und ruft weder die `Dispose` - `Finalize` Methode noch die-Methode oder andere Visual Basic Code auf.</span><span class="sxs-lookup"><span data-stu-id="1a459-109">The `End` statement stops code execution abruptly, and does not invoke the `Dispose` or `Finalize` method, or any other Visual Basic code.</span></span> <span data-ttu-id="1a459-110">Objekt Verweise, die von anderen Programmen gehalten werden, werden für ungültig erklärt.</span><span class="sxs-lookup"><span data-stu-id="1a459-110">Object references held by other programs are invalidated.</span></span> <span data-ttu-id="1a459-111">Wenn eine `End` -Anweisung in einem `Try` -oder `Catch` -Block gefunden wird, wird das-Steuer `Finally` Element nicht an den entsprechenden-Block übergeben.</span><span class="sxs-lookup"><span data-stu-id="1a459-111">If an `End` statement is encountered within a `Try` or `Catch` block, control does not pass to the corresponding `Finally` block.</span></span>  
  
 <span data-ttu-id="1a459-112">Die `Stop` -Anweisung hält die Ausführung an, `End`aber im Gegensatz dazu schließt Sie keine Dateien oder löscht Variablen, es sei denn, Sie findet in einer kompilierten ausführbaren Datei (. exe).</span><span class="sxs-lookup"><span data-stu-id="1a459-112">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
 <span data-ttu-id="1a459-113">Da `End` Ihre Anwendung beendet, ohne dass Sie an Ressourcen teilnimmt, die möglicherweise geöffnet sind, sollten Sie versuchen, die Anwendung ordnungsgemäß zu schließen, bevor Sie Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="1a459-113">Because `End` terminates your application without attending to any resources that might be open, you should try to close down cleanly before using it.</span></span> <span data-ttu-id="1a459-114">Wenn für Ihre Anwendung z. b. Formulare geöffnet sind, sollten Sie diese schließen, bevor die `End` Steuerung die-Anweisung erreicht.</span><span class="sxs-lookup"><span data-stu-id="1a459-114">For example, if your application has any forms open, you should close them before control reaches the `End` statement.</span></span>  
  
 <span data-ttu-id="1a459-115">Sie sollten nur `End` sparsam und nur dann verwenden, wenn Sie sofort beenden müssen.</span><span class="sxs-lookup"><span data-stu-id="1a459-115">You should use `End` sparingly, and only when you need to stop immediately.</span></span> <span data-ttu-id="1a459-116">Die normalen Methoden zum Beenden einer Prozedur ([Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md) und [Exit-Anweisung](../../../visual-basic/language-reference/statements/exit-statement.md)) schließen die Prozedur nicht nur ordnungsgemäß, sondern geben dem aufrufenden Code auch die Möglichkeit, sauber zu schließen.</span><span class="sxs-lookup"><span data-stu-id="1a459-116">The normal ways to terminate a procedure ([Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) and [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md)) not only close down the procedure cleanly but also give the calling code the opportunity to close down cleanly.</span></span> <span data-ttu-id="1a459-117">Eine Konsolenanwendung kann z. b. einfach `Return` aus der `Main` Prozedur entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="1a459-117">A console application, for example, can simply `Return` from the `Main` procedure.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="1a459-118">Die `End` -Anweisung ruft <xref:System.Environment.Exit%2A> die-Methode <xref:System.Environment> <xref:System> der-Klasse im-Namespace auf.</span><span class="sxs-lookup"><span data-stu-id="1a459-118">The `End` statement calls the <xref:System.Environment.Exit%2A> method of the <xref:System.Environment> class in the <xref:System> namespace.</span></span> <span data-ttu-id="1a459-119"><xref:System.Environment.Exit%2A>erfordert, dass Sie `UnmanagedCode` über die-Berechtigung verfügen.</span><span class="sxs-lookup"><span data-stu-id="1a459-119"><xref:System.Environment.Exit%2A> requires that you have `UnmanagedCode` permission.</span></span> <span data-ttu-id="1a459-120">Andernfalls tritt ein <xref:System.Security.SecurityException> Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="1a459-120">If you do not, a <xref:System.Security.SecurityException> error occurs.</span></span>  
  
 <span data-ttu-id="1a459-121">Wenn ein zusätzliches Schlüsselwort folgt, [wird \<das End-Schlüsselwort > Anweisung](../../../visual-basic/language-reference/statements/end-keyword-statement.md) das Ende der Definition der entsprechenden Prozedur bzw. des entsprechenden Blocks verstreicht.</span><span class="sxs-lookup"><span data-stu-id="1a459-121">When followed by an additional keyword, [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) delineates the end of the definition of the appropriate procedure or block.</span></span> <span data-ttu-id="1a459-122">`End Function` Beendet beispielsweise die Definition einer `Function` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="1a459-122">For example, `End Function` terminates the definition of a `Function` procedure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a459-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1a459-123">Example</span></span>  
 <span data-ttu-id="1a459-124">Im folgenden Beispiel wird die `End` -Anweisung verwendet, um die Codeausführung zu beenden, wenn der Benutzer sie anfordert.</span><span class="sxs-lookup"><span data-stu-id="1a459-124">The following example uses the `End` statement to terminate code execution if the user requests it.</span></span>  
  
 [!code-vb[VbVersHelp60Controls#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVersHelp60Controls/VB/Form1.vb#64)]  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="1a459-125">Entwickler Hinweise zu intelligenten Geräten</span><span class="sxs-lookup"><span data-stu-id="1a459-125">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="1a459-126">Diese Anweisung wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1a459-126">This statement is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a459-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1a459-127">See also</span></span>

- <xref:System.Security.Permissions.SecurityPermissionFlag>
- [<span data-ttu-id="1a459-128">Stop-Anweisung</span><span class="sxs-lookup"><span data-stu-id="1a459-128">Stop Statement</span></span>](../../../visual-basic/language-reference/statements/stop-statement.md)
- [<span data-ttu-id="1a459-129">End \<-Schlüsselwort > Anweisung</span><span class="sxs-lookup"><span data-stu-id="1a459-129">End \<keyword> Statement</span></span>](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
