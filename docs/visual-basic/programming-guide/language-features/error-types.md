---
title: Fehlertypen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions, types
- errors [Visual Basic], types
- errors [Visual Basic], logic
- errors [Visual Basic], syntax
- logic errors [Visual Basic], Visual Basic
- run-time errors [Visual Basic], types of errors
- syntax errors [Visual Basic], Visual Basic
ms.assetid: 3048aabf-8c97-4e13-9150-853769cb5f6f
ms.openlocfilehash: 07db963ac3cf9d1c0d17c420480189d362cdaf2c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61973172"
---
# <a name="error-types-visual-basic"></a><span data-ttu-id="47bea-102">Fehlertypen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="47bea-102">Error Types (Visual Basic)</span></span>
<span data-ttu-id="47bea-103">In Visual Basic Fehler (so genannte *Ausnahmen*) fallen in drei Kategorien unterteilt: Syntaxfehler, Laufzeitfehler und Logikfehler.</span><span class="sxs-lookup"><span data-stu-id="47bea-103">In Visual Basic, errors (also called *exceptions*) fall into one of three categories: syntax errors, run-time errors, and logic errors.</span></span>  
  
## <a name="syntax-errors"></a><span data-ttu-id="47bea-104">Syntaxfehler</span><span class="sxs-lookup"><span data-stu-id="47bea-104">Syntax Errors</span></span>  
 <span data-ttu-id="47bea-105">*Syntaxfehler* sind diejenigen, die angezeigt werden, während Sie Code schreiben.</span><span class="sxs-lookup"><span data-stu-id="47bea-105">*Syntax errors* are those that appear while you write code.</span></span> <span data-ttu-id="47bea-106">Visual Basic überprüft Ihren Code während der Eingabe in die **Code-Editor** Fenster und warnt Sie, wenn Sie einen Fehler, z. B. Rechtschreibfehler, oder verwenden ein Sprachelement nicht ordnungsgemäß machen.</span><span class="sxs-lookup"><span data-stu-id="47bea-106">Visual Basic checks your code as you type it in the **Code Editor** window and alerts you if you make a mistake, such as misspelling a word or using a language element improperly.</span></span> <span data-ttu-id="47bea-107">Syntaxfehler sind am häufigsten verwendete Typ von Fehlern.</span><span class="sxs-lookup"><span data-stu-id="47bea-107">Syntax errors are the most common type of errors.</span></span> <span data-ttu-id="47bea-108">Sie können sie ganz einfach in beheben die Programmierumgebung, sobald sie auftreten.</span><span class="sxs-lookup"><span data-stu-id="47bea-108">You can fix them easily in the coding environment as soon as they occur.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="47bea-109">Die `Option Explicit` -Anweisung ist eine Methode zur Vermeidung von Syntaxfehlern.</span><span class="sxs-lookup"><span data-stu-id="47bea-109">The `Option Explicit` statement is one means of avoiding syntax errors.</span></span> <span data-ttu-id="47bea-110">Es erzwingt, dass Sie alle Variablen, die in der Anwendung verwendet werden vorab deklarieren.</span><span class="sxs-lookup"><span data-stu-id="47bea-110">It forces you to declare, in advance, all the variables to be used in the application.</span></span> <span data-ttu-id="47bea-111">Daher, wenn diese Variablen im Code verwendet werden, typografische Fehler sofort und können behoben werden.</span><span class="sxs-lookup"><span data-stu-id="47bea-111">Therefore, when those variables are used in the code, any typographic errors are caught immediately and can be fixed.</span></span>  
  
## <a name="run-time-errors"></a><span data-ttu-id="47bea-112">Laufzeitfehler</span><span class="sxs-lookup"><span data-stu-id="47bea-112">Run-Time Errors</span></span>  
 <span data-ttu-id="47bea-113">*Laufzeitfehler* sind diejenigen, die angezeigt werden, nachdem Sie kompilieren und des Codes ausführen.</span><span class="sxs-lookup"><span data-stu-id="47bea-113">*Run-time errors* are those that appear only after you compile and run your code.</span></span> <span data-ttu-id="47bea-114">Diese umfassen Code, der angezeigt werden, korrekt sein, es wurde keine Syntaxfehler vorhanden sind, jedoch, die nicht ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="47bea-114">These involve code that may appear to be correct in that it has no syntax errors, but that will not execute.</span></span> <span data-ttu-id="47bea-115">Beispielsweise können Sie eine einzige Zeile Code zum Öffnen einer Datei ordnungsgemäß schreiben.</span><span class="sxs-lookup"><span data-stu-id="47bea-115">For example, you might correctly write a line of code to open a file.</span></span> <span data-ttu-id="47bea-116">Aber wenn die Datei beschädigt ist, die Anwendung nicht ausführen die `Open` -Funktion, und es nicht mehr ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="47bea-116">But if the file is corrupted, the application cannot carry out the `Open` function, and it stops running.</span></span> <span data-ttu-id="47bea-117">Sie können die meisten Laufzeitfehler beheben, indem Sie den fehlerhaften Code umschreiben und neu kompilieren zu müssen, und erneut durch.</span><span class="sxs-lookup"><span data-stu-id="47bea-117">You can fix most run-time errors by rewriting the faulty code, and then recompiling and rerunning it.</span></span>  
  
## <a name="logic-errors"></a><span data-ttu-id="47bea-118">Logischer Fehler</span><span class="sxs-lookup"><span data-stu-id="47bea-118">Logic Errors</span></span>  
 <span data-ttu-id="47bea-119">*Logikfehler* sind diejenigen, die angezeigt werden, sobald die Anwendung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="47bea-119">*Logic errors* are those that appear once the application is in use.</span></span> <span data-ttu-id="47bea-120">Sie sind die meisten häufig unerwünschten oder unerwartete Ergebnisse als Reaktion auf Benutzeraktionen.</span><span class="sxs-lookup"><span data-stu-id="47bea-120">They are most often unwanted or unexpected results in response to user actions.</span></span> <span data-ttu-id="47bea-121">Z. B. einen falsch Schlüssel oder andere externe beeinflussen möglicherweise dazu führen, dass Ihre Anwendung nicht mehr funktioniert innerhalb der erwarteten Parameter oder vollständig.</span><span class="sxs-lookup"><span data-stu-id="47bea-121">For example, a mistyped key or other outside influence might cause your application to stop working within expected parameters, or altogether.</span></span> <span data-ttu-id="47bea-122">Logische Fehler sind im Allgemeinen am schwersten zu beheben, da es nicht immer klar ist, in dem sie stammen.</span><span class="sxs-lookup"><span data-stu-id="47bea-122">Logic errors are generally the hardest type to fix, since it is not always clear where they originate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47bea-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="47bea-123">See also</span></span>

- [<span data-ttu-id="47bea-124">Try...Catch...Finally-Anweisung</span><span class="sxs-lookup"><span data-stu-id="47bea-124">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="47bea-125">Debugger – Grundlagen</span><span class="sxs-lookup"><span data-stu-id="47bea-125">Debugger Basics</span></span>](/visualstudio/debugger/debugger-basics)
