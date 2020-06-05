---
title: '#Const-Anweisung'
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
ms.openlocfilehash: 91152771a4ef5ec74a7408511ccc2afe28dd442e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415465"
---
# <a name="const-directive"></a><span data-ttu-id="623b9-102">#Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="623b9-102">#Const Directive</span></span>

<span data-ttu-id="623b9-103">Definiert bedingte Compilerkonstanten für Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="623b9-103">Defines conditional compiler constants for Visual Basic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="623b9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="623b9-104">Syntax</span></span>  
  
```vb  
#Const constname = expression  
```  
  
## <a name="parts"></a><span data-ttu-id="623b9-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="623b9-105">Parts</span></span>  

 `constname`  
 <span data-ttu-id="623b9-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="623b9-106">Required.</span></span> <span data-ttu-id="623b9-107">Der Name der Konstanten, die definiert wird.</span><span class="sxs-lookup"><span data-stu-id="623b9-107">Name of the constant being defined.</span></span>  
  
 `expression`  
 <span data-ttu-id="623b9-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="623b9-108">Required.</span></span> <span data-ttu-id="623b9-109">Literale, andere Bedingte Compilerkonstante oder eine beliebige Kombination, die beliebige oder alle arithmetischen oder logischen Operatoren mit Ausnahme von enthält `Is` .</span><span class="sxs-lookup"><span data-stu-id="623b9-109">Literal, other conditional compiler constant, or any combination that includes any or all arithmetic or logical operators except `Is`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="623b9-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="623b9-110">Remarks</span></span>  

 <span data-ttu-id="623b9-111">Bedingte Compilerkonstanten sind immer privat für die Datei, in der Sie angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="623b9-111">Conditional compiler constants are always private to the file in which they appear.</span></span> <span data-ttu-id="623b9-112">Sie können keine öffentlichen Compilerkonstanten mithilfe der- `#Const` Direktive erstellen. Sie können Sie nur in der Benutzeroberfläche oder mit der- `/define` Compileroption erstellen.</span><span class="sxs-lookup"><span data-stu-id="623b9-112">You cannot create public compiler constants using the `#Const` directive; you can create them only in the user interface or with the `/define` compiler option.</span></span>  
  
 <span data-ttu-id="623b9-113">In können nur bedingte Compilerkonstanten und Literale verwendet werden `expression` .</span><span class="sxs-lookup"><span data-stu-id="623b9-113">You can use only conditional compiler constants and literals in `expression`.</span></span> <span data-ttu-id="623b9-114">Die Verwendung einer mit definierten Standard Konstante `Const` verursacht einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="623b9-114">Using a standard constant defined with `Const` causes an error.</span></span> <span data-ttu-id="623b9-115">Umgekehrt können Sie mit dem- `#Const` Schlüsselwort definierte Konstanten nur für die bedingte Kompilierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="623b9-115">Conversely, you can use constants defined with the `#Const` keyword only for conditional compilation.</span></span> <span data-ttu-id="623b9-116">Konstanten können ebenfalls nicht definiert werden. in diesem Fall haben Sie den Wert `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="623b9-116">Constants can also be undefined, in which case they have a value of `Nothing`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="623b9-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="623b9-117">Example</span></span>  

 <span data-ttu-id="623b9-118">Dieses Beispiel verwendet die `#Const`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="623b9-118">This example uses the `#Const` directive.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="623b9-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="623b9-119">See also</span></span>

- [<span data-ttu-id="623b9-120">-define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="623b9-120">-define (Visual Basic)</span></span>](../../reference/command-line-compiler/define.md)
- [<span data-ttu-id="623b9-121">#If...Then...#Else-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="623b9-121">#If...Then...#Else Directives</span></span>](if-then-else-directives.md)
- [<span data-ttu-id="623b9-122">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="623b9-122">Const Statement</span></span>](../statements/const-statement.md)
- [<span data-ttu-id="623b9-123">Bedingte Kompilierung</span><span class="sxs-lookup"><span data-stu-id="623b9-123">Conditional Compilation</span></span>](../../programming-guide/program-structure/conditional-compilation.md)
- [<span data-ttu-id="623b9-124">If...Then...Else-Anweisung</span><span class="sxs-lookup"><span data-stu-id="623b9-124">If...Then...Else Statement</span></span>](../statements/if-then-else-statement.md)
