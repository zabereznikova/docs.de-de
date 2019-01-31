---
title: Die <procedurename>-Funktion gibt nicht für alle Codepfade einen Wert zurück.
ms.date: 07/20/2015
f1_keywords:
- bc42105
- vbc42105
helpviewer_keywords:
- BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
ms.openlocfilehash: 9782bb49a3327c6a8bd9938eca7cb3e899818784
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55281059"
---
# <a name="function-procedurename-doesnt-return-a-value-on-all-code-paths"></a><span data-ttu-id="d9288-102">Funktion "\<Prozedurname >' nicht für alle Codepfade einen Wert zurück</span><span class="sxs-lookup"><span data-stu-id="d9288-102">Function '\<procedurename>' doesn't return a value on all code paths</span></span>
<span data-ttu-id="d9288-103">Funktion "\<Prozedurname >' nicht für alle Codepfade einen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="d9288-103">Function '\<procedurename>' doesn't return a value on all code paths.</span></span> <span data-ttu-id="d9288-104">Fehlt eine Return-Anweisung?</span><span class="sxs-lookup"><span data-stu-id="d9288-104">Are you missing a 'Return' statement?</span></span>  
  
 <span data-ttu-id="d9288-105">Ein `Function` Prozedur verfügt über mindestens einen möglichen Pfad durch den Code, die keinen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="d9288-105">A `Function` procedure has at least one possible path through its code that does not return a value.</span></span>  
  
 <span data-ttu-id="d9288-106">Sie können einen Rückgabewert aus einer `Function` Prozedur in einer der folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="d9288-106">You can return a value from a `Function` procedure in any of the following ways:</span></span>  
  
-   <span data-ttu-id="d9288-107">Fügen Sie den Wert in eine [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d9288-107">Include the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
-   <span data-ttu-id="d9288-108">Weisen Sie den Wert der `Function` Prozedur benennen, und führen Sie dann eine `Exit Function` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="d9288-108">Assign the value to the `Function` procedure name and then perform an `Exit Function` statement.</span></span>  
  
-   <span data-ttu-id="d9288-109">Weisen Sie den Wert der `Function` Prozedur benennen, und führen Sie dann die `End Function` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="d9288-109">Assign the value to the `Function` procedure name and then perform the `End Function` statement.</span></span>  
  
 <span data-ttu-id="d9288-110">Wenn die Steuerung an übergibt `Exit Function` oder `End Function` und Sie für einen beliebigen Wert nicht den Namen der Prozedur zugewiesen haben, gibt die Prozedur den Standardwert des Typs zurückgeben von Daten zurück.</span><span class="sxs-lookup"><span data-stu-id="d9288-110">If control passes to `Exit Function` or `End Function` and you have not assigned any value to the procedure name, the procedure returns the default value of the return data type.</span></span> <span data-ttu-id="d9288-111">Weitere Informationen finden Sie unter "Verhalten" in [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d9288-111">For more information, see "Behavior" in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="d9288-112">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="d9288-112">By default, this message is a warning.</span></span> <span data-ttu-id="d9288-113">Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="d9288-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="d9288-114">**Fehler-ID:** BC42105</span><span class="sxs-lookup"><span data-stu-id="d9288-114">**Error ID:** BC42105</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d9288-115">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="d9288-115">To correct this error</span></span>  
  
-   <span data-ttu-id="d9288-116">Überprüfen Sie Ihre Ablaufsteuerungslogik, und stellen Sie sicher, dass Sie vor jeder Anweisung einen Wert zuweisen, die bewirkt, eine Rückgabe dass.</span><span class="sxs-lookup"><span data-stu-id="d9288-116">Check your control flow logic and make sure you assign a value before every statement that causes a return.</span></span>  
  
     <span data-ttu-id="d9288-117">Es ist einfacher, um sicherzustellen, dass es sich bei jeder Beendigung der Prozedur einen Wert zurückgibt, wenn Sie immer verwenden die `Return` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="d9288-117">It is easier to guarantee that every return from the procedure returns a value if you always use the `Return` statement.</span></span> <span data-ttu-id="d9288-118">Wenn Sie die letzte Anweisung vor so vorgehen `End Function` muss eine `Return` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="d9288-118">If you do this, the last statement before `End Function` should be a `Return` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9288-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9288-119">See also</span></span>
- [<span data-ttu-id="d9288-120">Function-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="d9288-120">Function Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)
- [<span data-ttu-id="d9288-121">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d9288-121">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="d9288-122">Seite „Kompilieren“, Projekt-Designer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9288-122">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
