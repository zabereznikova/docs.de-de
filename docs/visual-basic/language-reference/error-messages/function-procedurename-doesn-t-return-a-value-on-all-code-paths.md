---
title: "Function &#39; &lt;Prozedurname&gt;&#39; ist nicht &#39; t für alle Codepfade einen Wert zurück"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42105
- vbc42105
helpviewer_keywords: BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5244d97a79f2450f44fe05f63510369914375912
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="function-39ltprocedurenamegt39-doesn39t-return-a-value-on-all-code-paths"></a><span data-ttu-id="73433-102">Function &#39; &lt;Prozedurname&gt;&#39; ist nicht &#39; t für alle Codepfade einen Wert zurück</span><span class="sxs-lookup"><span data-stu-id="73433-102">Function &#39;&lt;procedurename&gt;&#39; doesn&#39;t return a value on all code paths</span></span>
<span data-ttu-id="73433-103">Funktion "\<Prozedurname >' ist nicht für alle Codepfade einen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="73433-103">Function '\<procedurename>' doesn't return a value on all code paths.</span></span> <span data-ttu-id="73433-104">Fehlt eine "Return"-Anweisung?</span><span class="sxs-lookup"><span data-stu-id="73433-104">Are you missing a 'Return' statement?</span></span>  
  
 <span data-ttu-id="73433-105">Ein `Function` Prozedur hat mindestens einen möglichen Pfad durch ihren Code, die keinen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="73433-105">A `Function` procedure has at least one possible path through its code that does not return a value.</span></span>  
  
 <span data-ttu-id="73433-106">Sie können einen Rückgabewert aus einer `Function` Prozedur in einem der folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="73433-106">You can return a value from a `Function` procedure in any of the following ways:</span></span>  
  
-   <span data-ttu-id="73433-107">Schließen Sie den Wert in einer [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="73433-107">Include the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
-   <span data-ttu-id="73433-108">Weisen Sie den Wert der `Function` Prozedur benennen, und führen Sie dann eine `Exit Function` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="73433-108">Assign the value to the `Function` procedure name and then perform an `Exit Function` statement.</span></span>  
  
-   <span data-ttu-id="73433-109">Weisen Sie den Wert der `Function` Prozedur benennen, und führen Sie dann die `End Function` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="73433-109">Assign the value to the `Function` procedure name and then perform the `End Function` statement.</span></span>  
  
 <span data-ttu-id="73433-110">Wenn die Steuerung an übergibt `Exit Function` oder `End Function` und Sie den Namen der Prozedur ausnahmslos zugewiesen haben, die Prozedur den Standardwert der Rückgabedatentyp zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="73433-110">If control passes to `Exit Function` or `End Function` and you have not assigned any value to the procedure name, the procedure returns the default value of the return data type.</span></span> <span data-ttu-id="73433-111">Weitere Informationen finden Sie unter "Verhalten" in [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="73433-111">For more information, see "Behavior" in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="73433-112">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="73433-112">By default, this message is a warning.</span></span> <span data-ttu-id="73433-113">Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="73433-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="73433-114">**Fehler-ID:** BC42105</span><span class="sxs-lookup"><span data-stu-id="73433-114">**Error ID:** BC42105</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="73433-115">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="73433-115">To correct this error</span></span>  
  
-   <span data-ttu-id="73433-116">Überprüfen Sie Ihre Ablaufsteuerungslogik, und stellen Sie sicher, dass Sie vor jeder Anweisung einen Wert zuweisen, die bewirkt, eine Rückgabe dass.</span><span class="sxs-lookup"><span data-stu-id="73433-116">Check your control flow logic and make sure you assign a value before every statement that causes a return.</span></span>  
  
     <span data-ttu-id="73433-117">Es ist einfacher, um sicherzustellen, dass jede Rückgabe aus der Prozedur einen Wert zurückgibt, wenn Sie immer verwenden die `Return` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="73433-117">It is easier to guarantee that every return from the procedure returns a value if you always use the `Return` statement.</span></span> <span data-ttu-id="73433-118">Wenn Sie die letzte Anweisung vor dazu `End Function` sollte eine `Return` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="73433-118">If you do this, the last statement before `End Function` should be a `Return` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73433-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="73433-119">See Also</span></span>  
 [<span data-ttu-id="73433-120">Function-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="73433-120">Function Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)  
 [<span data-ttu-id="73433-121">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="73433-121">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="73433-122">Seite „Kompilieren“, Projekt-Designer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="73433-122">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
