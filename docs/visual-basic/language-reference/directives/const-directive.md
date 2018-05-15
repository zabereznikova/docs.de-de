---
title: '##Const-Direktive'
ms.date: 07/20/2015
f1_keywords:
- vb.#Const
- '#vb.Const'
- '#Const'
helpviewer_keywords:
- '#Const directive'
- conditional compilation [Visual Basic], directives
- Const directive (#Const)
- Visual Basic compiler, compiler directives
- constants [Visual Basic], Const directive
- constants [Visual Basic], declaring
- Const statement [Visual Basic], directive (#Const)
- 'declaring constants [Visual Basic], #const directive'
ms.assetid: 707669e5-23f9-4f17-8622-a0d534429386
ms.openlocfilehash: a3b3318f6b44f7d1798e08195be5aeb920b61c0c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="const-directive"></a><span data-ttu-id="7e0a3-102">#Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="7e0a3-102">#Const Directive</span></span>
<span data-ttu-id="7e0a3-103">Definiert Konstanten für die bedingte Kompilierung für Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-103">Defines conditional compiler constants for Visual Basic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e0a3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7e0a3-104">Syntax</span></span>  
  
```  
#Const constname = expression  
```  
  
## <a name="parts"></a><span data-ttu-id="7e0a3-105">Teile</span><span class="sxs-lookup"><span data-stu-id="7e0a3-105">Parts</span></span>  
 `constname`  
 <span data-ttu-id="7e0a3-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-106">Required.</span></span> <span data-ttu-id="7e0a3-107">Die Namen der Konstanten definiert wird.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-107">Name of the constant being defined.</span></span>  
  
 `expression`  
 <span data-ttu-id="7e0a3-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-108">Required.</span></span> <span data-ttu-id="7e0a3-109">Literalzeichen, andere Konstanten für die bedingte Kompilierung oder eine beliebige Kombination, die alle arithmetische oder logische Operatoren außer enthält `Is`.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-109">Literal, other conditional compiler constant, or any combination that includes any or all arithmetic or logical operators except `Is`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e0a3-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7e0a3-110">Remarks</span></span>  
 <span data-ttu-id="7e0a3-111">Konstanten für die bedingte Kompilierung sind immer privat für die Datei, in der sie angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-111">Conditional compiler constants are always private to the file in which they appear.</span></span> <span data-ttu-id="7e0a3-112">Mithilfe von öffentlichen Compilerkonstanten kann nicht erstellt werden die `#Const` Richtlinie; Sie können diese erstellen, nur in der Benutzeroberfläche oder mit der `/define` -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-112">You cannot create public compiler constants using the `#Const` directive; you can create them only in the user interface or with the `/define` compiler option.</span></span>  
  
 <span data-ttu-id="7e0a3-113">Können Sie nur Konditionelle Compilerkonstanten und Literale in `expression`.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-113">You can use only conditional compiler constants and literals in `expression`.</span></span> <span data-ttu-id="7e0a3-114">Mithilfe einer standard-konstantes definiert mit `Const` verursacht einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-114">Using a standard constant defined with `Const` causes an error.</span></span> <span data-ttu-id="7e0a3-115">Umgekehrt können Sie mit definierte Konstanten verwenden die `#Const` Schlüsselwort nur für die bedingte Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-115">Conversely, you can use constants defined with the `#Const` keyword only for conditional compilation.</span></span> <span data-ttu-id="7e0a3-116">Konstanten können auch nicht definiert sein, in diesem Fall haben einen Wert von `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-116">Constants can also be undefined, in which case they have a value of `Nothing`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e0a3-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7e0a3-117">Example</span></span>  
 <span data-ttu-id="7e0a3-118">Dieses Beispiel verwendet die `#Const`-Direktive.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-118">This example uses the `#Const` directive.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#3](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/const-directive_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="7e0a3-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7e0a3-119">See Also</span></span>  
 [<span data-ttu-id="7e0a3-120">/ define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7e0a3-120">/define (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/define.md)  
 [<span data-ttu-id="7e0a3-121">#If...Then...#Else-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="7e0a3-121">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [<span data-ttu-id="7e0a3-122">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="7e0a3-122">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
 [<span data-ttu-id="7e0a3-123">Bedingte Kompilierung</span><span class="sxs-lookup"><span data-stu-id="7e0a3-123">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 [<span data-ttu-id="7e0a3-124">If...Then...Else-Anweisung</span><span class="sxs-lookup"><span data-stu-id="7e0a3-124">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
