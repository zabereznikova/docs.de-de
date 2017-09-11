---
title: Fehlertypen (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- exceptions, types
- errors [Visual Basic], types
- errors [Visual Basic], logic
- errors [Visual Basic], syntax
- logic errors, Visual Basic
- run-time errors, types of errors
- syntax errors, Visual Basic
ms.assetid: 3048aabf-8c97-4e13-9150-853769cb5f6f
caps.latest.revision: 13
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 51cf5820e79ff9467357619d4f5b067bc4168bfb
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="error-types-visual-basic"></a><span data-ttu-id="ac507-102">Fehlertypen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ac507-102">Error Types (Visual Basic)</span></span>
<span data-ttu-id="ac507-103">In [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], Fehler (so genannte *Ausnahmen*) fallen in drei Kategorien unterteilt: Syntaxfehler, Laufzeitfehler und logische Fehler.</span><span class="sxs-lookup"><span data-stu-id="ac507-103">In [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], errors (also called *exceptions*) fall into one of three categories: syntax errors, run-time errors, and logic errors.</span></span>  
  
## <a name="syntax-errors"></a><span data-ttu-id="ac507-104">Syntaxfehler</span><span class="sxs-lookup"><span data-stu-id="ac507-104">Syntax Errors</span></span>  
 <span data-ttu-id="ac507-105">*Syntaxfehler* sind, die beim Schreiben von Code.</span><span class="sxs-lookup"><span data-stu-id="ac507-105">*Syntax errors* are those that appear while you write code.</span></span> [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="ac507-106">überprüft den Code bei der Eingabe in die **Code-Editor** Fenster und warnt Sie, wenn Sie einen Fehler, wie z. B. Rechtschreibfehler oder falsch verwendete machen.</span><span class="sxs-lookup"><span data-stu-id="ac507-106"> checks your code as you type it in the **Code Editor** window and alerts you if you make a mistake, such as misspelling a word or using a language element improperly.</span></span> <span data-ttu-id="ac507-107">Syntaxfehler sind die häufigsten Fehler.</span><span class="sxs-lookup"><span data-stu-id="ac507-107">Syntax errors are the most common type of errors.</span></span> <span data-ttu-id="ac507-108">Sie können diese Probleme beheben problemlos in die Programmierumgebung, sobald sie auftreten.</span><span class="sxs-lookup"><span data-stu-id="ac507-108">You can fix them easily in the coding environment as soon as they occur.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac507-109">Die `Option Explicit` -Anweisung ist ein Mittel zur Vermeidung von Syntaxfehlern.</span><span class="sxs-lookup"><span data-stu-id="ac507-109">The `Option Explicit` statement is one means of avoiding syntax errors.</span></span> <span data-ttu-id="ac507-110">Es erzwingt, dass Sie im voraus, dass das deklarieren alle Variablen in der Anwendung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ac507-110">It forces you to declare, in advance, all the variables to be used in the application.</span></span> <span data-ttu-id="ac507-111">Daher, wenn diese Variablen im Code verwendet werden, Tippfehler sofort und behoben werden können.</span><span class="sxs-lookup"><span data-stu-id="ac507-111">Therefore, when those variables are used in the code, any typographic errors are caught immediately and can be fixed.</span></span>  
  
## <a name="run-time-errors"></a><span data-ttu-id="ac507-112">Laufzeitfehler</span><span class="sxs-lookup"><span data-stu-id="ac507-112">Run-Time Errors</span></span>  
 <span data-ttu-id="ac507-113">*Laufzeitfehler* treten erst nach dem Kompilieren und des Codes ausführen.</span><span class="sxs-lookup"><span data-stu-id="ac507-113">*Run-time errors* are those that appear only after you compile and run your code.</span></span> <span data-ttu-id="ac507-114">Diese umfassen Code, der scheinbar korrekt sein, es wurde keine Syntaxfehler vorhanden sind, wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ac507-114">These involve code that may appear to be correct in that it has no syntax errors, but that will not execute.</span></span> <span data-ttu-id="ac507-115">Beispielsweise können Sie eine Codezeile zum Öffnen einer Datei richtig schreiben.</span><span class="sxs-lookup"><span data-stu-id="ac507-115">For example, you might correctly write a line of code to open a file.</span></span> <span data-ttu-id="ac507-116">Aber wenn die Datei beschädigt ist, die Anwendung nicht ausführen der `Open` -Funktion, und es nicht mehr ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ac507-116">But if the file is corrupted, the application cannot carry out the `Open` function, and it stops running.</span></span> <span data-ttu-id="ac507-117">Die meisten Laufzeitfehler können Sie beheben, indem Sie den fehlerhaften Code umschreiben und neu zu kompilieren und erneut durch.</span><span class="sxs-lookup"><span data-stu-id="ac507-117">You can fix most run-time errors by rewriting the faulty code, and then recompiling and rerunning it.</span></span>  
  
## <a name="logic-errors"></a><span data-ttu-id="ac507-118">Logikfehler</span><span class="sxs-lookup"><span data-stu-id="ac507-118">Logic Errors</span></span>  
 <span data-ttu-id="ac507-119">*Logische Fehler* sind diejenigen, die angezeigt wird, nachdem die Anwendung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ac507-119">*Logic errors* are those that appear once the application is in use.</span></span> <span data-ttu-id="ac507-120">Sie sind die meisten häufig unerwünschte oder unerwartete Ergebnisse in Reaktion auf Benutzeraktionen.</span><span class="sxs-lookup"><span data-stu-id="ac507-120">They are most often unwanted or unexpected results in response to user actions.</span></span> <span data-ttu-id="ac507-121">Z. B. ein falsch geschriebenes Schlüssel oder anderer äußerer Einfluss kann dazu führen, dass Ihre Anwendung innerhalb erwarteter Parameter nicht mehr oder vollständig.</span><span class="sxs-lookup"><span data-stu-id="ac507-121">For example, a mistyped key or other outside influence might cause your application to stop working within expected parameters, or altogether.</span></span> <span data-ttu-id="ac507-122">Logikfehler sind generell am schwersten zu beheben, da nicht immer klar ist, in dem sie stammen.</span><span class="sxs-lookup"><span data-stu-id="ac507-122">Logic errors are generally the hardest type to fix, since it is not always clear where they originate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac507-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac507-123">See Also</span></span>  
 <span data-ttu-id="ac507-124">[Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) </span><span class="sxs-lookup"><span data-stu-id="ac507-124">[Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) </span></span>  
<span data-ttu-id="ac507-125"> [Debugger – Grundlagen](https://docs.microsoft.com/visualstudio/debugger/debugger-basics)</span><span class="sxs-lookup"><span data-stu-id="ac507-125"> [Debugger Basics](https://docs.microsoft.com/visualstudio/debugger/debugger-basics)</span></span>
