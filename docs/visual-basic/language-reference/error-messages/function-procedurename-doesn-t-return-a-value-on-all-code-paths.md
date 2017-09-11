---
title: "Funktion &quot;&lt;Prozedurname&gt;&quot; nicht für alle Codepfade einen Wert zurück | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42105
- vbc42105
dev_langs:
- VB
helpviewer_keywords:
- BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
caps.latest.revision: 12
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
ms.openlocfilehash: cec047644bfbf82c5c3c206b23af6b0fc37f834d
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="function-39ltprocedurenamegt39-doesn39t-return-a-value-on-all-code-paths"></a><span data-ttu-id="f4275-102">Funktion "&lt;Prozedurname&gt;' nicht für alle Codepfade einen Wert zurück</span><span class="sxs-lookup"><span data-stu-id="f4275-102">Function &#39;&lt;procedurename&gt;&#39; doesn&#39;t return a value on all code paths</span></span>
<span data-ttu-id="f4275-103">Funktion "\<Prozedurname >' nicht für alle Codepfade einen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="f4275-103">Function '\<procedurename>' doesn't return a value on all code paths.</span></span> <span data-ttu-id="f4275-104">Fehlt eine Return-Anweisung?</span><span class="sxs-lookup"><span data-stu-id="f4275-104">Are you missing a 'Return' statement?</span></span>  
  
 <span data-ttu-id="f4275-105">Ein `Function` Prozedur verfügt über mindestens einen möglichen Codepfad auf, die keinen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="f4275-105">A `Function` procedure has at least one possible path through its code that does not return a value.</span></span>  
  
 <span data-ttu-id="f4275-106">Kann man einen Wert aus einer `Function` Prozedur in einer der folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="f4275-106">You can return a value from a `Function` procedure in any of the following ways:</span></span>  
  
-   <span data-ttu-id="f4275-107">Fügen Sie den Wert in einem [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f4275-107">Include the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
-   <span data-ttu-id="f4275-108">Weisen Sie den Wert der `Function` Prozedur benennen, und führen Sie dann eine `Exit Function` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="f4275-108">Assign the value to the `Function` procedure name and then perform an `Exit Function` statement.</span></span>  
  
-   <span data-ttu-id="f4275-109">Weisen Sie den Wert der `Function` Prozedur benennen, und führen Sie dann die `End Function` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="f4275-109">Assign the value to the `Function` procedure name and then perform the `End Function` statement.</span></span>  
  
 <span data-ttu-id="f4275-110">Wenn die Steuerung an `Exit Function` oder `End Function` und Sie den Namen der Prozedur einen Wert zugewiesen haben, wird die Prozedur gibt den Standardwert des Rückgabedatentyps zurück.</span><span class="sxs-lookup"><span data-stu-id="f4275-110">If control passes to `Exit Function` or `End Function` and you have not assigned any value to the procedure name, the procedure returns the default value of the return data type.</span></span> <span data-ttu-id="f4275-111">Weitere Informationen finden Sie unter "Verhalten" in [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f4275-111">For more information, see "Behavior" in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="f4275-112">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="f4275-112">By default, this message is a warning.</span></span> <span data-ttu-id="f4275-113">Weitere Informationen zu Ausblenden von Warnungen oder Warnungen als Fehler behandeln, finden Sie unter [Konfigurieren von Warnungen in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="f4275-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="f4275-114">**Fehler-ID:** BC42105</span><span class="sxs-lookup"><span data-stu-id="f4275-114">**Error ID:** BC42105</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f4275-115">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="f4275-115">To correct this error</span></span>  
  
-   <span data-ttu-id="f4275-116">Überprüfen Sie die Ablaufsteuerungslogik, und stellen Sie sicher, dass Sie vor jeder Anweisung einen Wert zuweisen, der eine Rückgabe verursacht.</span><span class="sxs-lookup"><span data-stu-id="f4275-116">Check your control flow logic and make sure you assign a value before every statement that causes a return.</span></span>  
  
     <span data-ttu-id="f4275-117">Es ist einfacher sicherstellen, dass bei jeder Beendigung der Prozedur einen Wert zurückgibt, wenn Sie immer verwenden die `Return` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="f4275-117">It is easier to guarantee that every return from the procedure returns a value if you always use the `Return` statement.</span></span> <span data-ttu-id="f4275-118">Wenn Sie die letzte Anweisung vor dazu `End Function` sollte eine `Return` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="f4275-118">If you do this, the last statement before `End Function` should be a `Return` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4275-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f4275-119">See Also</span></span>  
 <span data-ttu-id="f4275-120">[Function-Prozeduren](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="f4275-120">[Function Procedures](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md) </span></span>  
<span data-ttu-id="f4275-121"> [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="f4275-121"> [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md) </span></span>  
<span data-ttu-id="f4275-122"> [Seite „Kompilieren“, Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="f4275-122"> [Compile Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic)</span></span>
