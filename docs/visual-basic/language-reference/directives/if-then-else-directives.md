---
title: '#If... ... #Else-Anweisungen (Visual Basic)'
ms.date: 04/11/2018
f1_keywords:
- vb.#EndIf
- '#End If'
- '#Then'
- '#ElseIf'
- vb.#ElseIf
- vb.#Else
- vb.#If
helpviewer_keywords:
- Visual Basic code, compiling
- '#If directive [Visual Basic]'
- conditional compilation [Visual Basic], directives
- '#End if directive [Visual Basic]'
- selective compiling
- else directive (#else)
- '#Else directive [Visual Basic]'
ms.assetid: 10bba104-e3fd-451b-b672-faa472530502
ms.openlocfilehash: 23e45d00e63c1f50ad2f6d3f08d16adbd13ae2b6
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56968817"
---
# <a name="ifthenelse-directives"></a><span data-ttu-id="5dd70-102">#If...Then...#Else-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5dd70-102">#If...Then...#Else Directives</span></span>
<span data-ttu-id="5dd70-103">Kompiliert bedingt ausgewählte Codeblöcke Visual Basic-Code ein.</span><span class="sxs-lookup"><span data-stu-id="5dd70-103">Conditionally compiles selected blocks of Visual Basic code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5dd70-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5dd70-104">Syntax</span></span>  
  
```  
#If expression Then  
   statements  
[ #ElseIf expression Then  
   [ statements ]  
...  
#ElseIf expression Then  
   [ statements ] ]  
[ #Else  
   [ statements ] ]  
#End If  
```  
  
## <a name="parts"></a><span data-ttu-id="5dd70-105">Teile</span><span class="sxs-lookup"><span data-stu-id="5dd70-105">Parts</span></span>  
 `expression`  
 <span data-ttu-id="5dd70-106">Erforderlich für `#If` und `#ElseIf` Anweisungen, die optional an anderer Stelle.</span><span class="sxs-lookup"><span data-stu-id="5dd70-106">Required for `#If` and `#ElseIf` statements, optional elsewhere.</span></span> <span data-ttu-id="5dd70-107">Ein Ausdruck, bestehend aus ausschließlich eine oder mehrere Konstanten für bedingte Kompilierung, Literale und Operatoren, der ergibt `True` oder `False`.</span><span class="sxs-lookup"><span data-stu-id="5dd70-107">Any expression, consisting exclusively of one or more conditional compiler constants, literals, and operators, that evaluates to `True` or `False`.</span></span>  
  
 `statements`  
 <span data-ttu-id="5dd70-108">Erforderlich für `#If` Anweisung zu blockieren, optionale an anderer Stelle.</span><span class="sxs-lookup"><span data-stu-id="5dd70-108">Required for `#If` statement block, optional elsewhere.</span></span> <span data-ttu-id="5dd70-109">Visual Basic-Programm von Linien oder Compiler-Direktiven, die kompiliert werden, wenn der zugeordnete Ausdruck ergibt `True`.</span><span class="sxs-lookup"><span data-stu-id="5dd70-109">Visual Basic program lines or compiler directives that are compiled if the associated expression evaluates to `True`.</span></span>  
  
 `#End If`  
 <span data-ttu-id="5dd70-110">Beendet die `#If` Anweisungsblock.</span><span class="sxs-lookup"><span data-stu-id="5dd70-110">Terminates the `#If` statement block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5dd70-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5dd70-111">Remarks</span></span>  
 <span data-ttu-id="5dd70-112">Auf der Oberfläche, die das Verhalten der `#If...Then...#Else` Anweisungen identisch angezeigt, wie mit der `If...Then...Else` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="5dd70-112">On the surface, the behavior of the `#If...Then...#Else` directives appears the same as that of the `If...Then...Else` statements.</span></span> <span data-ttu-id="5dd70-113">Allerdings die `#If...Then...#Else` Anweisungen auswerten was vom Compiler kompiliert wird, während die `If...Then...Else` Anweisungen Bedingungen auszuwerten, zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="5dd70-113">However, the `#If...Then...#Else` directives evaluate what is compiled by the compiler, whereas the `If...Then...Else` statements evaluate conditions at run time.</span></span>  
  
 <span data-ttu-id="5dd70-114">Für die bedingte Kompilierung wird normalerweise verwendet, um die gleiche Anwendung für unterschiedliche Plattformen zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="5dd70-114">Conditional compilation is typically used to compile the same program for different platforms.</span></span> <span data-ttu-id="5dd70-115">Es wird außerdem zu verhindern, dass zum Debuggen von Code in eine ausführbare Datei angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="5dd70-115">It is also used to prevent debugging code from appearing in an executable file.</span></span> <span data-ttu-id="5dd70-116">Code während der bedingten Kompilierung ausgeschlossen wird vollständig aus der endgültige ausführbare Datei weggelassen, damit er keine Auswirkungen auf die Größe oder die Leistung hat.</span><span class="sxs-lookup"><span data-stu-id="5dd70-116">Code excluded during conditional compilation is completely omitted from the final executable file, so it has no effect on size or performance.</span></span>  
  
 <span data-ttu-id="5dd70-117">Unabhängig vom Ergebnis der Auswertung, werden alle Ausdrücke ausgewertet, mit `Option Compare Binary`.</span><span class="sxs-lookup"><span data-stu-id="5dd70-117">Regardless of the outcome of any evaluation, all expressions are evaluated using `Option Compare Binary`.</span></span> <span data-ttu-id="5dd70-118">Die `Option Compare` Anweisung wirkt sich nicht auf Ausdrücke in `#If` und `#ElseIf` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="5dd70-118">The `Option Compare` statement does not affect expressions in `#If` and `#ElseIf` statements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5dd70-119">Keine einzeilige Form der `#If`, `#Else`, `#ElseIf`, und `#End If` Direktiven vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="5dd70-119">No single-line form of the `#If`, `#Else`, `#ElseIf`, and `#End If` directives exists.</span></span> <span data-ttu-id="5dd70-120">Kein anderer Code kann auf derselben Zeile wie die Direktiven angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="5dd70-120">No other code can appear on the same line as any of the directives.</span></span> 

<span data-ttu-id="5dd70-121">Die Anweisungen innerhalb eines Blocks für die bedingte Kompilierung müssen vollständigen logischen Anweisungen sein.</span><span class="sxs-lookup"><span data-stu-id="5dd70-121">The statements within a conditional compilation block must be complete logical statements.</span></span> <span data-ttu-id="5dd70-122">Z. B. nicht möglich, nur die Attribute einer Funktion, bedingt zu kompilieren, aber Sie können die Funktion zusammen mit seinen Attributen bedingt deklarieren:</span><span class="sxs-lookup"><span data-stu-id="5dd70-122">For example, you cannot conditionally compile only the attributes of a function, but you can conditionally declare the function along with its attributes:</span></span>

```vb
   #If DEBUG Then
   <WebMethod()>
   Public Function SomeFunction() As String
   #Else
   <WebMethod(CacheDuration:=86400)>
   Public Function SomeFunction() As String
   #End If
```

## <a name="example"></a><span data-ttu-id="5dd70-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5dd70-123">Example</span></span>
 <span data-ttu-id="5dd70-124">Dieses Beispiel verwendet die `#If...Then...#Else` Konstrukt zu bestimmen, ob bestimmte Anweisungen zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="5dd70-124">This example uses the `#If...Then...#Else` construct to determine whether to compile certain statements.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="5dd70-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5dd70-125">See also</span></span>
- [<span data-ttu-id="5dd70-126">#Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5dd70-126">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)
- [<span data-ttu-id="5dd70-127">If...Then...Else-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5dd70-127">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="5dd70-128">Bedingte Kompilierung</span><span class="sxs-lookup"><span data-stu-id="5dd70-128">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- <xref:System.Diagnostics.ConditionalAttribute?displayProperty=nameWithType>


