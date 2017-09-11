---
title: new-Modifizierer (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- new modifier keyword [C#]
ms.assetid: a2e20856-33b9-4620-b535-a60dbce8349b
caps.latest.revision: 28
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f763b9a1d2f146b8ebb475a01bd12f1a4238050a
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="new-modifier-c-reference"></a><span data-ttu-id="cfeea-102">new-Modifizierer (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="cfeea-102">new Modifier (C# Reference)</span></span>
<span data-ttu-id="cfeea-103">Wenn das Schlüsselwort `new` als Deklarationsmodifizierer verwendet wird, blendet es explizit einen von einer Basisklasse geerbten Member aus.</span><span class="sxs-lookup"><span data-stu-id="cfeea-103">When used as a declaration modifier, the `new` keyword explicitly hides a member that is inherited from a base class.</span></span> <span data-ttu-id="cfeea-104">Wenn Sie einen geerbten Member ausblenden, ersetzt die abgeleitete Version des Members die Basisklassenversion.</span><span class="sxs-lookup"><span data-stu-id="cfeea-104">When you hide an inherited member, the derived version of the member replaces the base class version.</span></span> <span data-ttu-id="cfeea-105">Obwohl Sie Member verdecken können, ohne den `new`-Modifizierer zu verwenden, wird eine Compilerwarnung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cfeea-105">Although you can hide members without using the `new` modifier, you get a compiler warning.</span></span> <span data-ttu-id="cfeea-106">Wenn Sie `new` verwenden, um einen Member explizit auszublenden, wird diese Warnung unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="cfeea-106">If you use `new` to explicitly hide a member, it suppresses this warning.</span></span>  
  
 <span data-ttu-id="cfeea-107">Um einen geerbten Member auszublenden, deklarieren Sie ihn mit demselben Membernamen in der abgeleiteten Klasse und ändern ihn mit dem `new`-Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="cfeea-107">To hide an inherited member, declare it in the derived class by using the same member name, and modify it with the `new` keyword.</span></span> <span data-ttu-id="cfeea-108">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="cfeea-108">For example:</span></span>  
  
 <span data-ttu-id="cfeea-109">[!code-cs[csrefKeywordsOperator#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-modifier_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="cfeea-109">[!code-cs[csrefKeywordsOperator#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-modifier_1.cs)]</span></span>  
  
 <span data-ttu-id="cfeea-110">In diesem Beispiel wird `BaseC.Invoke` durch `DerivedC.Invoke` ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="cfeea-110">In this example, `BaseC.Invoke` is hidden by `DerivedC.Invoke`.</span></span> <span data-ttu-id="cfeea-111">Der Vorgang wirkt sich nicht auf das Feld `x` aus, da es nicht mit einem ähnlichen Namen ausgeblendet wird.</span><span class="sxs-lookup"><span data-stu-id="cfeea-111">The field `x` is not affected because it is not hidden by a similar name.</span></span>  
  
 <span data-ttu-id="cfeea-112">Das Ausblenden des Namens durch Vererbung nimmt eine der folgenden Formen an:</span><span class="sxs-lookup"><span data-stu-id="cfeea-112">Name hiding through inheritance takes one of the following forms:</span></span>  
  
-   <span data-ttu-id="cfeea-113">Im Allgemeinen blendet eine Konstante, ein Feld, eine Eigenschaft oder einen Typ, der in einer Klasse oder Struktur eingegeben wird, alle Basisklassenmember aus, die den gleichen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="cfeea-113">Generally, a constant, field, property, or type that is introduced in a class or struct hides all base class members that share its name.</span></span>  <span data-ttu-id="cfeea-114">Es werden bestimmte Fälle unterschieden.</span><span class="sxs-lookup"><span data-stu-id="cfeea-114">There are special cases.</span></span>  <span data-ttu-id="cfeea-115">Wenn Sie beispielsweise ein neues Feld mit dem Namen `N` mit einem nicht aufrufbaren Typ deklarieren, und ein Basistyp deklariert `N` als Methode, blendet das neue Feld die Basisdeklaration nicht in der Aufrufsyntax aus.</span><span class="sxs-lookup"><span data-stu-id="cfeea-115">For example, if you declare a new field with name `N` to have a type that is not invocable, and a base type declares `N` to be a method, the new field does not hide the base declaration in invocation syntax.</span></span>  <span data-ttu-id="cfeea-116">Weitere Informationen finden Sie unter [C#-Sprachspezifikation](http://go.microsoft.com/fwlink/?LinkId=199552) (siehe Abschnitt „Suche nach Membern“ im Abschnitt „Ausdrücke“).</span><span class="sxs-lookup"><span data-stu-id="cfeea-116">See the [C# language specification](http://go.microsoft.com/fwlink/?LinkId=199552) for details (see section "Member Lookup" in section "Expressions").</span></span>  
  
-   <span data-ttu-id="cfeea-117">Durch eine Methode, die in eine Klasse oder Struktur eingeführt ist, werden Eigenschaften, Felder und Typen mit dem gleichen Namen in der Basisklasse ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="cfeea-117">A method introduced in a class or struct hides properties, fields, and types that share that name in the base class.</span></span> <span data-ttu-id="cfeea-118">Alle Basisklassenmethoden mit der gleichen Signatur werden ebenfalls ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="cfeea-118">It also hides all base class methods that have the same signature.</span></span>  
  
-   <span data-ttu-id="cfeea-119">Durch einen Indexer, der in einer Klasse oder Struktur eingeführt ist, werden alle Basisklassenindexer mit der gleichen Signatur ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="cfeea-119">An indexer introduced in a class or struct hides all base class indexers that have the same signature.</span></span>  
  
 <span data-ttu-id="cfeea-120">`new` und [override](../../../csharp/language-reference/keywords/override.md) dürfen nicht gleichzeitig auf denselben Member angewendet werden, da sich die Bedeutungen der beiden Modifizierer gegenseitig ausschließen.</span><span class="sxs-lookup"><span data-stu-id="cfeea-120">It is an error to use both `new` and [override](../../../csharp/language-reference/keywords/override.md) on the same member, because the two modifiers have mutually exclusive meanings.</span></span> <span data-ttu-id="cfeea-121">Mit dem `new`-Modifizierer wird ein neuer Member mit demselben Namen erstellt, und der ursprüngliche Member wird ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="cfeea-121">The `new` modifier creates a new member with the same name and causes the original member to become hidden.</span></span> <span data-ttu-id="cfeea-122">Der `override`-Modifizierer verlängert die Implementierung für einen geerbten Member.</span><span class="sxs-lookup"><span data-stu-id="cfeea-122">The `override` modifier extends the implementation for an inherited member.</span></span>  
  
 <span data-ttu-id="cfeea-123">Wenn der `new`-Modifizierer in einer Deklaration verwendet wird, in der kein geerbter Member ausgeblendet wird, wird eine Warnung generiert.</span><span class="sxs-lookup"><span data-stu-id="cfeea-123">Using the `new` modifier in a declaration that does not hide an inherited member generates a warning.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cfeea-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cfeea-124">Example</span></span>  
 <span data-ttu-id="cfeea-125">In diesem Beispiel wird von einer Basisklasse, `BaseC`, und einer abgeleiteten Klasse, `DerivedC`, der gleiche Feldname `x` verwendet. Auf diese Weise wird der Wert des geerbten Felds ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="cfeea-125">In this example, a base class, `BaseC`, and a derived class, `DerivedC`, use the same field name `x`, which hides the value of the inherited field.</span></span> <span data-ttu-id="cfeea-126">Im Beispiel wird die Verwendung des `new`-Modifizierers veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="cfeea-126">The example demonstrates the use of the `new` modifier.</span></span> <span data-ttu-id="cfeea-127">Außerdem wird gezeigt, wie mit den voll qualifizierten Namen auf die ausgeblendeten Member der Basisklasse zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="cfeea-127">It also demonstrates how to access the hidden members of the base class by using their fully qualified names.</span></span>  
  
 <span data-ttu-id="cfeea-128">[!code-cs[csrefKeywordsOperator#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-modifier_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="cfeea-128">[!code-cs[csrefKeywordsOperator#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-modifier_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="cfeea-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cfeea-129">Example</span></span>  
 <span data-ttu-id="cfeea-130">In diesem Beispiel blendet eine geschachtelte Klasse eine Klasse mit dem gleichen Namen in der Basisklasse aus.</span><span class="sxs-lookup"><span data-stu-id="cfeea-130">In this example, a nested class hides a class that has the same name in the base class.</span></span> <span data-ttu-id="cfeea-131">Das Beispiel veranschaulicht, wie mit dem `new`-Modifizierer die Warnmeldung vermieden wird und wie mit den voll qualifizierten Namen auf die ausgeblendeten Klassenmember zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="cfeea-131">The example demonstrates how to use the `new` modifier to eliminate the warning message and how to access the hidden class members by using their fully qualified names.</span></span>  
  
 <span data-ttu-id="cfeea-132">[!code-cs[csrefKeywordsOperator#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-modifier_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="cfeea-132">[!code-cs[csrefKeywordsOperator#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-modifier_3.cs)]</span></span>  
  
 <span data-ttu-id="cfeea-133">Wenn der `new`-Modifizierer entfernt wird, kann das Programm dennoch kompiliert und ausgeführt werden. Es wird jedoch folgende Warnung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="cfeea-133">If you remove the `new` modifier, the program will still compile and run, but you will get the following warning:</span></span>  
  
```  
The keyword new is required on 'MyDerivedC.x' because it hides inherited member 'MyBaseC.x'.  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="cfeea-134">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="cfeea-134">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cfeea-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cfeea-135">See Also</span></span>  
 <span data-ttu-id="cfeea-136">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="cfeea-136">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="cfeea-137">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="cfeea-137">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="cfeea-138">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="cfeea-138">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="cfeea-139">[Operatorschlüsselwörter](../../../csharp/language-reference/keywords/operator-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="cfeea-139">[Operator Keywords](../../../csharp/language-reference/keywords/operator-keywords.md) </span></span>  
 <span data-ttu-id="cfeea-140">[Modifizierer](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="cfeea-140">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="cfeea-141">[Versionsverwaltung mit den Schlüsselwörtern „override“ und „new“](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="cfeea-141">[Versioning with the Override and New Keywords](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) </span></span>  
 [<span data-ttu-id="cfeea-142">Wann müssen die Schlüsselwörter "override" und "new" verwendet werden?</span><span class="sxs-lookup"><span data-stu-id="cfeea-142">Knowing When to Use Override and New Keywords</span></span>](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md)

