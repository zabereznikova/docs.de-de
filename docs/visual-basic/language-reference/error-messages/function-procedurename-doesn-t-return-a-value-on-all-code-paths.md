---
title: Die <procedurename>-Funktion gibt nicht für alle Codepfade einen Wert zurück.
ms.date: 07/20/2015
f1_keywords:
- bc42105
- vbc42105
helpviewer_keywords:
- BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
ms.openlocfilehash: 5295775b2541219e611e167e304ca8ef99cf6bd8
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874137"
---
# <a name="function-procedurename-doesnt-return-a-value-on-all-code-paths"></a><span data-ttu-id="d4fcc-102">Die \<procedurename>-Funktion gibt nicht für alle Codepfade einen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-102">Function '\<procedurename>' doesn't return a value on all code paths</span></span>

<span data-ttu-id="d4fcc-103">Die Funktion " \<procedurename> " gibt nicht für alle Codepfade einen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-103">Function '\<procedurename>' doesn't return a value on all code paths.</span></span> <span data-ttu-id="d4fcc-104">Fehlt eine Return-Anweisung?</span><span class="sxs-lookup"><span data-stu-id="d4fcc-104">Are you missing a 'Return' statement?</span></span>  
  
 <span data-ttu-id="d4fcc-105">Eine `Function` Prozedur weist mindestens einen möglichen Pfad durch Ihren Code auf, der keinen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-105">A `Function` procedure has at least one possible path through its code that does not return a value.</span></span>  
  
 <span data-ttu-id="d4fcc-106">Sie können einen Wert aus einer `Function` Prozedur mit einer der folgenden Methoden zurückgeben:</span><span class="sxs-lookup"><span data-stu-id="d4fcc-106">You can return a value from a `Function` procedure in any of the following ways:</span></span>  
  
- <span data-ttu-id="d4fcc-107">Fügen Sie den Wert in eine [Return-Anweisung](../statements/return-statement.md)ein.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-107">Include the value in a [Return Statement](../statements/return-statement.md).</span></span>  
  
- <span data-ttu-id="d4fcc-108">Weisen Sie dem Prozedur Namen den Wert zu, `Function` und führen Sie dann eine- `Exit Function` Anweisung aus.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-108">Assign the value to the `Function` procedure name and then perform an `Exit Function` statement.</span></span>  
  
- <span data-ttu-id="d4fcc-109">Weisen Sie dem Prozedur Namen den Wert zu, `Function` und führen Sie dann die `End Function` Anweisung aus.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-109">Assign the value to the `Function` procedure name and then perform the `End Function` statement.</span></span>  
  
 <span data-ttu-id="d4fcc-110">Wenn die Steuerung an `Exit Function` oder weitergeleitet `End Function` wird und Sie dem Prozedur Namen keinen Wert zugewiesen haben, gibt die Prozedur den Standardwert des Rückgabe Datentyps zurück.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-110">If control passes to `Exit Function` or `End Function` and you have not assigned any value to the procedure name, the procedure returns the default value of the return data type.</span></span> <span data-ttu-id="d4fcc-111">Weitere Informationen finden Sie unter "Verhalten" in der [Function-Anweisung](../statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d4fcc-111">For more information, see "Behavior" in [Function Statement](../statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="d4fcc-112">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-112">By default, this message is a warning.</span></span> <span data-ttu-id="d4fcc-113">Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="d4fcc-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="d4fcc-114">**Fehler-ID:** BC42105</span><span class="sxs-lookup"><span data-stu-id="d4fcc-114">**Error ID:** BC42105</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d4fcc-115">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="d4fcc-115">To correct this error</span></span>  
  
- <span data-ttu-id="d4fcc-116">Überprüfen Sie die Ablauf Steuerungslogik, und stellen Sie sicher, dass Sie vor jeder Anweisung, die eine Rückgabe auslöst, einen Wert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-116">Check your control flow logic and make sure you assign a value before every statement that causes a return.</span></span>  
  
     <span data-ttu-id="d4fcc-117">Es ist einfacher sicherzustellen, dass jede Rückgabe von der Prozedur einen Wert zurückgibt, wenn Sie immer die- `Return` Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-117">It is easier to guarantee that every return from the procedure returns a value if you always use the `Return` statement.</span></span> <span data-ttu-id="d4fcc-118">Wenn Sie dies tun, sollte die letzte Anweisung vor `End Function` eine- `Return` Anweisung sein.</span><span class="sxs-lookup"><span data-stu-id="d4fcc-118">If you do this, the last statement before `End Function` should be a `Return` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4fcc-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d4fcc-119">See also</span></span>

- [<span data-ttu-id="d4fcc-120">Function-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="d4fcc-120">Function Procedures</span></span>](../../programming-guide/language-features/procedures/function-procedures.md)
- [<span data-ttu-id="d4fcc-121">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d4fcc-121">Function Statement</span></span>](../statements/function-statement.md)
- [<span data-ttu-id="d4fcc-122">Seite „Kompilieren“, Projekt-Designer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d4fcc-122">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
