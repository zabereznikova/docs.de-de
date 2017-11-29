---
title: Fehlertypen (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- exceptions, types
- errors [Visual Basic], types
- errors [Visual Basic], logic
- errors [Visual Basic], syntax
- logic errors [Visual Basic], Visual Basic
- run-time errors [Visual Basic], types of errors
- syntax errors [Visual Basic], Visual Basic
ms.assetid: 3048aabf-8c97-4e13-9150-853769cb5f6f
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e01ed588d284a475a537a5fcf5ca506d25ca69f1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="error-types-visual-basic"></a><span data-ttu-id="d07cd-102">Fehlertypen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d07cd-102">Error Types (Visual Basic)</span></span>
<span data-ttu-id="d07cd-103">In [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], Fehler (so genannte *Ausnahmen*) fallen in drei Kategorien unterteilt: Syntaxfehler, Laufzeitfehler und logische Fehler.</span><span class="sxs-lookup"><span data-stu-id="d07cd-103">In [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], errors (also called *exceptions*) fall into one of three categories: syntax errors, run-time errors, and logic errors.</span></span>  
  
## <a name="syntax-errors"></a><span data-ttu-id="d07cd-104">Syntaxfehler</span><span class="sxs-lookup"><span data-stu-id="d07cd-104">Syntax Errors</span></span>  
 <span data-ttu-id="d07cd-105">*Syntaxfehler* sind diejenigen, die angezeigt werden, während Sie Code schreiben.</span><span class="sxs-lookup"><span data-stu-id="d07cd-105">*Syntax errors* are those that appear while you write code.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="d07cd-106">überprüft den Code, wie Sie ihn in die **Code-Editor** Fenster und benachrichtigt Sie, falls zu tun, wie z. B. Rechtschreibfehler, oder verwenden ein Sprachelement falsch ist.</span><span class="sxs-lookup"><span data-stu-id="d07cd-106"> checks your code as you type it in the **Code Editor** window and alerts you if you make a mistake, such as misspelling a word or using a language element improperly.</span></span> <span data-ttu-id="d07cd-107">Syntaxfehler sind die am häufigsten verwendete Typ von Fehlern.</span><span class="sxs-lookup"><span data-stu-id="d07cd-107">Syntax errors are the most common type of errors.</span></span> <span data-ttu-id="d07cd-108">Sie können beheben diese einfach in der Codierung Umgebung, sobald sie auftreten.</span><span class="sxs-lookup"><span data-stu-id="d07cd-108">You can fix them easily in the coding environment as soon as they occur.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d07cd-109">Die `Option Explicit` -Anweisung ist eine Methode zur Vermeidung von Syntaxfehlern.</span><span class="sxs-lookup"><span data-stu-id="d07cd-109">The `Option Explicit` statement is one means of avoiding syntax errors.</span></span> <span data-ttu-id="d07cd-110">Er erzwingt, dass Sie im voraus, dass alle Variablen in der Anwendung zu verwendende deklarieren.</span><span class="sxs-lookup"><span data-stu-id="d07cd-110">It forces you to declare, in advance, all the variables to be used in the application.</span></span> <span data-ttu-id="d07cd-111">Daher, wenn diese Variablen im Code verwendet werden, typografische Fehler sofort und behoben werden können.</span><span class="sxs-lookup"><span data-stu-id="d07cd-111">Therefore, when those variables are used in the code, any typographic errors are caught immediately and can be fixed.</span></span>  
  
## <a name="run-time-errors"></a><span data-ttu-id="d07cd-112">Laufzeitfehler</span><span class="sxs-lookup"><span data-stu-id="d07cd-112">Run-Time Errors</span></span>  
 <span data-ttu-id="d07cd-113">*Laufzeitfehler* treten erst nach dem Kompilieren und des Codes ausführen.</span><span class="sxs-lookup"><span data-stu-id="d07cd-113">*Run-time errors* are those that appear only after you compile and run your code.</span></span> <span data-ttu-id="d07cd-114">Diese umfassen Code, der auftreten kann, korrekt sein, es wurde keine Syntaxfehler, jedoch, die nicht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d07cd-114">These involve code that may appear to be correct in that it has no syntax errors, but that will not execute.</span></span> <span data-ttu-id="d07cd-115">Beispielsweise können Sie eine Codezeile zum Öffnen einer Datei ordnungsgemäß schreiben.</span><span class="sxs-lookup"><span data-stu-id="d07cd-115">For example, you might correctly write a line of code to open a file.</span></span> <span data-ttu-id="d07cd-116">Aber wenn die Datei beschädigt ist, die Anwendung nicht ausführen der `Open` -Funktion und die Ausführung beendet.</span><span class="sxs-lookup"><span data-stu-id="d07cd-116">But if the file is corrupted, the application cannot carry out the `Open` function, and it stops running.</span></span> <span data-ttu-id="d07cd-117">Sie können die meisten Laufzeitfehler beheben, indem Sie den fehlerhaften Code umschreiben und neu zu kompilieren und erneut durch.</span><span class="sxs-lookup"><span data-stu-id="d07cd-117">You can fix most run-time errors by rewriting the faulty code, and then recompiling and rerunning it.</span></span>  
  
## <a name="logic-errors"></a><span data-ttu-id="d07cd-118">Logikfehler</span><span class="sxs-lookup"><span data-stu-id="d07cd-118">Logic Errors</span></span>  
 <span data-ttu-id="d07cd-119">*Logikfehler* sind diejenigen, die angezeigt werden, sobald die Anwendung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d07cd-119">*Logic errors* are those that appear once the application is in use.</span></span> <span data-ttu-id="d07cd-120">Sie sind die meisten häufig unerwünschten oder unerwarteten Ergebnissen in Reaktion auf Benutzeraktionen.</span><span class="sxs-lookup"><span data-stu-id="d07cd-120">They are most often unwanted or unexpected results in response to user actions.</span></span> <span data-ttu-id="d07cd-121">Z. B. ein falsch geschriebenes Schlüssel oder anderen externen beeinflussen kann dazu führen, dass Ihre Anwendung zum Programmende innerhalb der erwarteten Parameter oder vollständig.</span><span class="sxs-lookup"><span data-stu-id="d07cd-121">For example, a mistyped key or other outside influence might cause your application to stop working within expected parameters, or altogether.</span></span> <span data-ttu-id="d07cd-122">Logikfehler sind im Allgemeinen der schwersten zu beheben, da es nicht immer klar ist, in dem sie stammen.</span><span class="sxs-lookup"><span data-stu-id="d07cd-122">Logic errors are generally the hardest type to fix, since it is not always clear where they originate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d07cd-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d07cd-123">See Also</span></span>  
 [<span data-ttu-id="d07cd-124">Try...Catch...Finally-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d07cd-124">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="d07cd-125">Debugger – Grundlagen</span><span class="sxs-lookup"><span data-stu-id="d07cd-125">Debugger Basics</span></span>](/visualstudio/debugger/debugger-basics)
