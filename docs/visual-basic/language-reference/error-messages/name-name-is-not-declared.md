---
title: Namen &#39; &lt;Namen&gt; &#39; ist nicht deklariert
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30451
- vbc30451
helpviewer_keywords:
- BC30451
ms.assetid: 765f099b-e21e-47c6-a906-a065444e56b3
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 26245952a2dc5341dedba6c497c47773b882b49b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="name-39ltnamegt39-is-not-declared"></a><span data-ttu-id="1b3af-102">Namen &#39; &lt;Namen&gt; &#39; ist nicht deklariert</span><span class="sxs-lookup"><span data-stu-id="1b3af-102">Name &#39;&lt;name&gt;&#39; is not declared</span></span>
<span data-ttu-id="1b3af-103">Eine Anweisung verweist auf ein Programmierelement, aber der Compiler ein Element mit genau diesem Namen kann nicht gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="1b3af-103">A statement refers to a programming element, but the compiler cannot find an element with that exact name.</span></span>  
  
 <span data-ttu-id="1b3af-104">**Fehler-ID:** BC30451</span><span class="sxs-lookup"><span data-stu-id="1b3af-104">**Error ID:** BC30451</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1b3af-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="1b3af-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="1b3af-106">Überprüfen Sie die Schreibweise des Namens in der verweisenden Anweisung.</span><span class="sxs-lookup"><span data-stu-id="1b3af-106">Check the spelling of the name in the referring statement.</span></span> <span data-ttu-id="1b3af-107">Visual Basic unterscheidet Groß-/Kleinschreibung, aber eine andere Variante der Schreibweise als dem völlig anderen Namen betrachtet wird.</span><span class="sxs-lookup"><span data-stu-id="1b3af-107">Visual Basic is case-insensitive, but any other variation in the spelling is regarded as a completely different name.</span></span> <span data-ttu-id="1b3af-108">Beachten Sie, dass der Unterstrich (`_`) Teil des Namens und daher Teil der Schreibweise ist.</span><span class="sxs-lookup"><span data-stu-id="1b3af-108">Note that the underscore (`_`) is part of the name and therefore part of the spelling.</span></span>  
  
2.  <span data-ttu-id="1b3af-109">Überprüfen Sie, ob Sie den Memberzugriffsoperator (`.`) zwischen einem Objekt und seinem Member.</span><span class="sxs-lookup"><span data-stu-id="1b3af-109">Check that you have the member access operator (`.`) between an object and its member.</span></span> <span data-ttu-id="1b3af-110">Wenn Sie z. B. ein <xref:System.Windows.Forms.TextBox> -Steuerelement namens `TextBox1`besitzen, müssen Sie für den Zugriff auf dessen <xref:System.Windows.Forms.TextBoxBase.Text%2A> -Eigenschaft `TextBox1.Text`eingeben.</span><span class="sxs-lookup"><span data-stu-id="1b3af-110">For example, if you have a <xref:System.Windows.Forms.TextBox> control named `TextBox1`, to access its <xref:System.Windows.Forms.TextBoxBase.Text%2A> property you should type `TextBox1.Text`.</span></span> <span data-ttu-id="1b3af-111">Wenn Sie stattdessen `TextBox1Text`eingeben, haben Sie einen anderen Namen erstellt.</span><span class="sxs-lookup"><span data-stu-id="1b3af-111">If instead you type `TextBox1Text`, you have created a different name.</span></span>  
  
3.  <span data-ttu-id="1b3af-112">Wenn die Schreibweise korrekt ist und die Syntax für alle Member Objektzugriff richtig ist, stellen Sie sicher, dass das Element deklariert wurde.</span><span class="sxs-lookup"><span data-stu-id="1b3af-112">If the spelling is correct and the syntax of any object member access is correct, verify that the element has been declared.</span></span> <span data-ttu-id="1b3af-113">Weitere Informationen finden Sie unter [deklarierten Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/index.md).</span><span class="sxs-lookup"><span data-stu-id="1b3af-113">For more information, see [Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/index.md).</span></span>  
  
4.  <span data-ttu-id="1b3af-114">Wenn das Programmierelement deklariert wurde, überprüfen Sie, dass es sich im Gültigkeitsbereich befindet.</span><span class="sxs-lookup"><span data-stu-id="1b3af-114">If the programming element has been declared, check that it is in scope.</span></span> <span data-ttu-id="1b3af-115">Wenn die verweisende Anweisung außerhalb des Bereichs, der das Programmierelement deklariert ist, müssen Sie möglicherweise den Namen zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="1b3af-115">If the referring statement is outside the region declaring the programming element, you might need to qualify the element name.</span></span> <span data-ttu-id="1b3af-116">Weitere Informationen finden Sie unter [Gültigkeitsbereich in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span><span class="sxs-lookup"><span data-stu-id="1b3af-116">For more information, see [Scope in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b3af-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b3af-117">See Also</span></span>  
 [<span data-ttu-id="1b3af-118">Deklarationen und Konstanten: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="1b3af-118">Declarations and Constants Summary</span></span>](../../../visual-basic/language-reference/keywords/declarations-and-constants-summary.md)  
 [<span data-ttu-id="1b3af-119">Visual Basic-Benennungskonventionen</span><span class="sxs-lookup"><span data-stu-id="1b3af-119">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [<span data-ttu-id="1b3af-120">Namen deklarierter Elemente</span><span class="sxs-lookup"><span data-stu-id="1b3af-120">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [<span data-ttu-id="1b3af-121">Verweise auf deklarierte Elemente</span><span class="sxs-lookup"><span data-stu-id="1b3af-121">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
