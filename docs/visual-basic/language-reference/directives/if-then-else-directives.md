---
title: '#If...Then...#Else-Anweisungen'
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
ms.openlocfilehash: 7054a6ada4583c5d89e020437eb622a59d3eb17a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410009"
---
# <a name="ifthenelse-directives"></a><span data-ttu-id="74cc3-102">#If...Then...#Else-Anweisung</span><span class="sxs-lookup"><span data-stu-id="74cc3-102">#If...Then...#Else Directives</span></span>

<span data-ttu-id="74cc3-103">Kompiliert bedingt ausgewählte Blöcke Visual Basic Codes.</span><span class="sxs-lookup"><span data-stu-id="74cc3-103">Conditionally compiles selected blocks of Visual Basic code.</span></span>

## <a name="syntax"></a><span data-ttu-id="74cc3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="74cc3-104">Syntax</span></span>

```vb
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

## <a name="parts"></a><span data-ttu-id="74cc3-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="74cc3-105">Parts</span></span>

`expression`  
<span data-ttu-id="74cc3-106">Erforderlich für `#If` -und- `#ElseIf` Anweisungen, optional an anderer Stelle.</span><span class="sxs-lookup"><span data-stu-id="74cc3-106">Required for `#If` and `#ElseIf` statements, optional elsewhere.</span></span> <span data-ttu-id="74cc3-107">Ein beliebiger Ausdruck, der ausschließlich aus einer oder mehreren bedingten Compilerkonstanten, Literalen und Operatoren besteht, die als oder ausgewertet werden `True` `False` .</span><span class="sxs-lookup"><span data-stu-id="74cc3-107">Any expression, consisting exclusively of one or more conditional compiler constants, literals, and operators, that evaluates to `True` or `False`.</span></span>

`statements`  
<span data-ttu-id="74cc3-108">Erforderlich für einen `#If` Anweisungsblock, optional an anderer Stelle.</span><span class="sxs-lookup"><span data-stu-id="74cc3-108">Required for `#If` statement block, optional elsewhere.</span></span> <span data-ttu-id="74cc3-109">Visual Basic Programmzeilen oder Compilerdirektiven, die kompiliert werden, wenn der zugehörige Ausdruck zu ausgewertet wird `True` .</span><span class="sxs-lookup"><span data-stu-id="74cc3-109">Visual Basic program lines or compiler directives that are compiled if the associated expression evaluates to `True`.</span></span>

`#End If`  
<span data-ttu-id="74cc3-110">Beendet den `#If` Anweisungsblock.</span><span class="sxs-lookup"><span data-stu-id="74cc3-110">Terminates the `#If` statement block.</span></span>

## <a name="remarks"></a><span data-ttu-id="74cc3-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="74cc3-111">Remarks</span></span>

<span data-ttu-id="74cc3-112">Auf der-Oberfläche wird das Verhalten der- `#If...Then...#Else` Direktiven genauso wie die- `If...Then...Else` Anweisungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="74cc3-112">On the surface, the behavior of the `#If...Then...#Else` directives appears the same as that of the `If...Then...Else` statements.</span></span> <span data-ttu-id="74cc3-113">Die- `#If...Then...#Else` Direktiven Werten jedoch aus, was vom Compiler kompiliert wird, während die- `If...Then...Else` Anweisungen Bedingungen zur Laufzeit auswerten.</span><span class="sxs-lookup"><span data-stu-id="74cc3-113">However, the `#If...Then...#Else` directives evaluate what is compiled by the compiler, whereas the `If...Then...Else` statements evaluate conditions at run time.</span></span>

<span data-ttu-id="74cc3-114">Die bedingte Kompilierung wird normalerweise verwendet, um dasselbe Programm für verschiedene Plattformen zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="74cc3-114">Conditional compilation is typically used to compile the same program for different platforms.</span></span> <span data-ttu-id="74cc3-115">Außerdem wird es verwendet, um zu verhindern, dass Debugcode in einer ausführbaren Datei angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="74cc3-115">It is also used to prevent debugging code from appearing in an executable file.</span></span> <span data-ttu-id="74cc3-116">Code, der während der bedingten Kompilierung ausgeschlossen wird, wird in der endgültigen ausführbaren Datei vollständig ausgelassen und hat daher keine Auswirkung auf die Größe oder Leistung.</span><span class="sxs-lookup"><span data-stu-id="74cc3-116">Code excluded during conditional compilation is completely omitted from the final executable file, so it has no effect on size or performance.</span></span>

<span data-ttu-id="74cc3-117">Unabhängig vom Ergebnis einer Auswertung werden alle Ausdrücke mithilfe von ausgewertet `Option Compare Binary` .</span><span class="sxs-lookup"><span data-stu-id="74cc3-117">Regardless of the outcome of any evaluation, all expressions are evaluated using `Option Compare Binary`.</span></span> <span data-ttu-id="74cc3-118">Die `Option Compare` -Anweisung wirkt sich nicht auf Ausdrücke in `#If` -und- `#ElseIf` Anweisungen aus.</span><span class="sxs-lookup"><span data-stu-id="74cc3-118">The `Option Compare` statement does not affect expressions in `#If` and `#ElseIf` statements.</span></span>

> [!NOTE]
> <span data-ttu-id="74cc3-119">Es sind keine einzeiligen Formen `#If` der `#Else` `#ElseIf` Direktiven,, und `#End If` vorhanden.</span><span class="sxs-lookup"><span data-stu-id="74cc3-119">No single-line form of the `#If`, `#Else`, `#ElseIf`, and `#End If` directives exists.</span></span> <span data-ttu-id="74cc3-120">Es kann kein anderer Code in derselben Zeile wie eine der Direktiven angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="74cc3-120">No other code can appear on the same line as any of the directives.</span></span>

<span data-ttu-id="74cc3-121">Die Anweisungen in einem Block für die bedingte Kompilierung müssen komplette logische Anweisungen sein.</span><span class="sxs-lookup"><span data-stu-id="74cc3-121">The statements within a conditional compilation block must be complete logical statements.</span></span> <span data-ttu-id="74cc3-122">Beispielsweise können Sie die Attribute einer Funktion nicht bedingt kompilieren, Sie können die Funktion aber bedingt zusammen mit ihren Attributen deklarieren:</span><span class="sxs-lookup"><span data-stu-id="74cc3-122">For example, you cannot conditionally compile only the attributes of a function, but you can conditionally declare the function along with its attributes:</span></span>

```vb
#If DEBUG Then
<WebMethod()>
Public Function SomeFunction() As String
#Else
<WebMethod(CacheDuration:=86400)>
Public Function SomeFunction() As String
#End If
```

## <a name="example"></a><span data-ttu-id="74cc3-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="74cc3-123">Example</span></span>

<span data-ttu-id="74cc3-124">In diesem Beispiel wird das- `#If...Then...#Else` Konstrukt verwendet, um zu bestimmen, ob bestimmte Anweisungen kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="74cc3-124">This example uses the `#If...Then...#Else` construct to determine whether to compile certain statements.</span></span>

[!code-vb[VbVbalrConditionalComp#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#1)]

## <a name="see-also"></a><span data-ttu-id="74cc3-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="74cc3-125">See also</span></span>

- [<span data-ttu-id="74cc3-126">#Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="74cc3-126">#Const Directive</span></span>](const-directive.md)
- [<span data-ttu-id="74cc3-127">If...Then...Else-Anweisung</span><span class="sxs-lookup"><span data-stu-id="74cc3-127">If...Then...Else Statement</span></span>](../statements/if-then-else-statement.md)
- [<span data-ttu-id="74cc3-128">Bedingte Kompilierung</span><span class="sxs-lookup"><span data-stu-id="74cc3-128">Conditional Compilation</span></span>](../../programming-guide/program-structure/conditional-compilation.md)
- <xref:System.Diagnostics.ConditionalAttribute?displayProperty=nameWithType>
