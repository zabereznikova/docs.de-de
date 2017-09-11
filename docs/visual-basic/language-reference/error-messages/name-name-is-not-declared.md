---
title: Name &quot;&lt;Namen&gt;&quot; ist nicht deklariert | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30451
- vbc30451
dev_langs:
- VB
helpviewer_keywords:
- BC30451
ms.assetid: 765f099b-e21e-47c6-a906-a065444e56b3
caps.latest.revision: 11
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
ms.openlocfilehash: 1396f24a34a37db064e73d7e259c04050f409ad2
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="name-39ltnamegt39-is-not-declared"></a><span data-ttu-id="7b8fb-102">Name '&lt;Namen&gt;' ist nicht deklariert.</span><span class="sxs-lookup"><span data-stu-id="7b8fb-102">Name &#39;&lt;name&gt;&#39; is not declared</span></span>
<span data-ttu-id="7b8fb-103">Eine Anweisung verweist auf ein Programmierelement, aber der Compiler kann ein Element mit genau diesem Namen nicht finden.</span><span class="sxs-lookup"><span data-stu-id="7b8fb-103">A statement refers to a programming element, but the compiler cannot find an element with that exact name.</span></span>  
  
 <span data-ttu-id="7b8fb-104">**Fehler-ID:** BC30451</span><span class="sxs-lookup"><span data-stu-id="7b8fb-104">**Error ID:** BC30451</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7b8fb-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="7b8fb-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="7b8fb-106">Überprüfen Sie die Schreibweise des Namens in der verweisenden Anweisung.</span><span class="sxs-lookup"><span data-stu-id="7b8fb-106">Check the spelling of the name in the referring statement.</span></span> [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="7b8fb-107">Groß-und Kleinschreibung, wird jedoch eine andere Veränderung der Schreibweise gilt als einen völlig anderen Namen.</span><span class="sxs-lookup"><span data-stu-id="7b8fb-107"> is case-insensitive, but any other variation in the spelling is regarded as a completely different name.</span></span> <span data-ttu-id="7b8fb-108">Beachten Sie, dass der Unterstrich (`_`) Teil des Namens und daher Teil der Schreibweise ist.</span><span class="sxs-lookup"><span data-stu-id="7b8fb-108">Note that the underscore (`_`) is part of the name and therefore part of the spelling.</span></span>  
  
2.  <span data-ttu-id="7b8fb-109">Überprüfen Sie, ob den Memberzugriffsoperator (`.`) zwischen einem Objekt und seine Member.</span><span class="sxs-lookup"><span data-stu-id="7b8fb-109">Check that you have the member access operator (`.`) between an object and its member.</span></span> <span data-ttu-id="7b8fb-110">Angenommen, Sie haben ein <xref:System.Windows.Forms.TextBox>-Steuerelement namens `TextBox1`, für den Zugriff auf die <xref:System.Windows.Forms.TextBoxBase.Text%2A>Eigenschaft Sie geben `TextBox1.Text`.</xref:System.Windows.Forms.TextBoxBase.Text%2A> </xref:System.Windows.Forms.TextBox></span><span class="sxs-lookup"><span data-stu-id="7b8fb-110">For example, if you have a <xref:System.Windows.Forms.TextBox> control named `TextBox1`, to access its <xref:System.Windows.Forms.TextBoxBase.Text%2A> property you should type `TextBox1.Text`.</span></span> <span data-ttu-id="7b8fb-111">Wenn Sie stattdessen `TextBox1Text`eingeben, haben Sie einen anderen Namen erstellt.</span><span class="sxs-lookup"><span data-stu-id="7b8fb-111">If instead you type `TextBox1Text`, you have created a different name.</span></span>  
  
3.  <span data-ttu-id="7b8fb-112">Wenn die Schreibweise richtig ist, und die Syntax von jedem Objekt Memberzugriff richtig ist, stellen Sie sicher, dass das Element deklariert wurde.</span><span class="sxs-lookup"><span data-stu-id="7b8fb-112">If the spelling is correct and the syntax of any object member access is correct, verify that the element has been declared.</span></span> <span data-ttu-id="7b8fb-113">Weitere Informationen finden Sie unter [deklarierten Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/index.md).</span><span class="sxs-lookup"><span data-stu-id="7b8fb-113">For more information, see [Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/index.md).</span></span>  
  
4.  <span data-ttu-id="7b8fb-114">Das Programmierelement deklariert wurde, überprüfen Sie, ob es im Gültigkeitsbereich befindet.</span><span class="sxs-lookup"><span data-stu-id="7b8fb-114">If the programming element has been declared, check that it is in scope.</span></span> <span data-ttu-id="7b8fb-115">Wenn die verweisende Anweisung außerhalb des Bereichs, der das Programmierelement deklariert ist, müssen Sie den Elementnamen qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="7b8fb-115">If the referring statement is outside the region declaring the programming element, you might need to qualify the element name.</span></span> <span data-ttu-id="7b8fb-116">Weitere Informationen finden Sie unter [Gültigkeitsbereich in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span><span class="sxs-lookup"><span data-stu-id="7b8fb-116">For more information, see [Scope in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b8fb-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b8fb-117">See Also</span></span>  
 <span data-ttu-id="7b8fb-118">[Deklarationen und Konstanten: Zusammenfassung](../../../visual-basic/language-reference/keywords/declarations-and-constants-summary.md) </span><span class="sxs-lookup"><span data-stu-id="7b8fb-118">[Declarations and Constants Summary](../../../visual-basic/language-reference/keywords/declarations-and-constants-summary.md) </span></span>  
<span data-ttu-id="7b8fb-119"> [Visual Basic-Benennungskonventionen](../../../visual-basic/programming-guide/program-structure/naming-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="7b8fb-119"> [Visual Basic Naming Conventions](../../../visual-basic/programming-guide/program-structure/naming-conventions.md) </span></span>  
<span data-ttu-id="7b8fb-120"> [Namen deklarierter Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md) </span><span class="sxs-lookup"><span data-stu-id="7b8fb-120"> [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md) </span></span>  
<span data-ttu-id="7b8fb-121"> [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)</span><span class="sxs-lookup"><span data-stu-id="7b8fb-121"> [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)</span></span>
