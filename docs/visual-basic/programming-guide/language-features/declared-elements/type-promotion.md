---
title: Typerweiterung
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- Partial keyword [Visual Basic], unexpected results with type promotion
- scope [Visual Basic], declared elements
- scope [Visual Basic], Visual Basic
- type promotion
- declared elements [Visual Basic], visibility
ms.assetid: 035eeb15-e4c5-4288-ab3c-6bd5d22f7051
ms.openlocfilehash: 6c28ca22e96616ff09e147400bfdb2adb922ff0e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085801"
---
# <a name="type-promotion-visual-basic"></a><span data-ttu-id="e2d35-102">Typerweiterung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e2d35-102">Type Promotion (Visual Basic)</span></span>

<span data-ttu-id="e2d35-103">Wenn Sie ein Programmier Element in einem Modul deklarieren, Visual Basic den Bereich auf den Namespace herauf Stufen, der das Modul enthält.</span><span class="sxs-lookup"><span data-stu-id="e2d35-103">When you declare a programming element in a module, Visual Basic promotes its scope to the namespace containing the module.</span></span> <span data-ttu-id="e2d35-104">Dies wird als *Typerweiterung*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="e2d35-104">This is known as *type promotion*.</span></span>  
  
 <span data-ttu-id="e2d35-105">Das folgende Beispiel zeigt eine Skelett Definition eines Moduls und zwei Member dieses Moduls.</span><span class="sxs-lookup"><span data-stu-id="e2d35-105">The following example shows a skeleton definition of a module and two members of that module.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#1)]  
  
 <span data-ttu-id="e2d35-106">In `projModule` werden Programmier Elemente, die auf Modulebene deklariert werden, zu herauf gestuft `projNamespace` .</span><span class="sxs-lookup"><span data-stu-id="e2d35-106">Within `projModule`, programming elements declared at module level are promoted to `projNamespace`.</span></span> <span data-ttu-id="e2d35-107">Im vorherigen Beispiel `basicEnum` werden und höher gestuft `innerClass` , aber `numberSub` nicht, da Sie nicht auf Modulebene deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="e2d35-107">In the preceding example, `basicEnum` and `innerClass` are promoted, but `numberSub` is not, because it is not declared at module level.</span></span>  
  
## <a name="effect-of-type-promotion"></a><span data-ttu-id="e2d35-108">Auswirkung der Typerweiterung</span><span class="sxs-lookup"><span data-stu-id="e2d35-108">Effect of Type Promotion</span></span>  

 <span data-ttu-id="e2d35-109">Die Auswirkung der Typerweiterung besteht darin, dass eine Qualifizierungs Zeichenfolge nicht den Modulnamen enthalten muss.</span><span class="sxs-lookup"><span data-stu-id="e2d35-109">The effect of type promotion is that a qualification string does not need to include the module name.</span></span> <span data-ttu-id="e2d35-110">Im folgenden Beispiel werden zwei Aufrufe der Prozedur im vorherigen Beispiel durchführt.</span><span class="sxs-lookup"><span data-stu-id="e2d35-110">The following example makes two calls to the procedure in the preceding example.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#2)]  
  
 <span data-ttu-id="e2d35-111">Im vorherigen Beispiel verwendet der erste-Befehl komplette Qualifizierungs Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="e2d35-111">In the preceding example, the first call uses complete qualification strings.</span></span> <span data-ttu-id="e2d35-112">Dies ist jedoch aufgrund der typherauf Stufung nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e2d35-112">However, this is not necessary because of type promotion.</span></span> <span data-ttu-id="e2d35-113">Der zweite-Befehl greift auch auf die Member des Moduls zu, ohne in die Qualifizierungs Zeichenfolgen einzubeziehen `projModule` .</span><span class="sxs-lookup"><span data-stu-id="e2d35-113">The second call also accesses the module's members without including `projModule` in the qualification strings.</span></span>  
  
## <a name="defeat-of-type-promotion"></a><span data-ttu-id="e2d35-114">Bekämpfung der herauf Stufung von Typen</span><span class="sxs-lookup"><span data-stu-id="e2d35-114">Defeat of Type Promotion</span></span>  

 <span data-ttu-id="e2d35-115">Wenn der Namespace bereits einen Member mit demselben Namen wie ein Modulmember hat, wird die Typerweiterung für dieses Modulmember unterstrichen.</span><span class="sxs-lookup"><span data-stu-id="e2d35-115">If the namespace already has a member with the same name as a module member, type promotion is defeated for that module member.</span></span> <span data-ttu-id="e2d35-116">Das folgende Beispiel zeigt eine Gerüst Definition einer Enumeration und eines Moduls innerhalb desselben Namespace.</span><span class="sxs-lookup"><span data-stu-id="e2d35-116">The following example shows a skeleton definition of an enumeration and a module within the same namespace.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#3)]  
  
 <span data-ttu-id="e2d35-117">Im vorherigen Beispiel kann Visual Basic die Klasse nicht auf herauf Stufen, `abc` `thisNameSpace` da bereits eine Enumeration mit dem gleichen Namen auf der Namespace Ebene vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e2d35-117">In the preceding example, Visual Basic cannot promote class `abc` to `thisNameSpace` because there is already an enumeration with the same name at namespace level.</span></span> <span data-ttu-id="e2d35-118">Für den Zugriff auf `abcSub` müssen Sie die vollständige Qualifikations Zeichenfolge verwenden `thisNamespace.thisModule.abc.abcSub` .</span><span class="sxs-lookup"><span data-stu-id="e2d35-118">To access `abcSub`, you must use the full qualification string `thisNamespace.thisModule.abc.abcSub`.</span></span> <span data-ttu-id="e2d35-119">`xyz`Die Klasse wird jedoch immer noch herauf gestuft, und Sie können `xyzSub` mit der kürzeren Qualifizierungs Zeichenfolge auf zugreifen `thisNamespace.xyz.xyzSub` .</span><span class="sxs-lookup"><span data-stu-id="e2d35-119">However, class `xyz` is still promoted, and you can access `xyzSub` with the shorter qualification string `thisNamespace.xyz.xyzSub`.</span></span>  
  
### <a name="defeat-of-type-promotion-for-partial-types"></a><span data-ttu-id="e2d35-120">Die unter Stufung der herauf Stufung von Typen für partielle Typen</span><span class="sxs-lookup"><span data-stu-id="e2d35-120">Defeat of Type Promotion for Partial Types</span></span>  

 <span data-ttu-id="e2d35-121">Wenn eine Klasse oder Struktur innerhalb eines Moduls das [partielle](../../../language-reference/modifiers/partial.md) Schlüsselwort verwendet, wird die Typerweiterung für diese Klasse oder Struktur automatisch unterstrichen, unabhängig davon, ob der Namespace über einen Member mit demselben Namen verfügt.</span><span class="sxs-lookup"><span data-stu-id="e2d35-121">If a class or structure inside a module uses the [Partial](../../../language-reference/modifiers/partial.md) keyword, type promotion is automatically defeated for that class or structure, whether or not the namespace has a member with the same name.</span></span> <span data-ttu-id="e2d35-122">Andere Elemente im Modul sind immer noch für die Typerweiterung geeignet.</span><span class="sxs-lookup"><span data-stu-id="e2d35-122">Other elements in the module are still eligible for type promotion.</span></span>  
  
 <span data-ttu-id="e2d35-123">**Konsequenzen.**</span><span class="sxs-lookup"><span data-stu-id="e2d35-123">**Consequences.**</span></span> <span data-ttu-id="e2d35-124">Die unter Folge einer typherauf Stufung einer partiellen Definition kann unerwartete Ergebnisse und sogar Compilerfehler verursachen.</span><span class="sxs-lookup"><span data-stu-id="e2d35-124">Defeat of type promotion of a partial definition can cause unexpected results and even compiler errors.</span></span> <span data-ttu-id="e2d35-125">Im folgenden Beispiel werden Skeleton partielle Definitionen einer-Klasse veranschaulicht, von denen eine innerhalb eines Moduls ist.</span><span class="sxs-lookup"><span data-stu-id="e2d35-125">The following example shows skeleton partial definitions of a class, one of which is inside a module.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#4)]  
  
 <span data-ttu-id="e2d35-126">Im vorherigen Beispiel erwartet der Entwickler möglicherweise, dass der Compiler die beiden partiellen Definitionen von zusammenführen kann `sampleClass` .</span><span class="sxs-lookup"><span data-stu-id="e2d35-126">In the preceding example, the developer might expect the compiler to merge the two partial definitions of `sampleClass`.</span></span> <span data-ttu-id="e2d35-127">Der Compiler kann jedoch die herauf Stufung der partiellen Definition nicht in in Erwägung gezogen `sampleModule` .</span><span class="sxs-lookup"><span data-stu-id="e2d35-127">However, the compiler does not consider promotion for the partial definition inside `sampleModule`.</span></span> <span data-ttu-id="e2d35-128">Daher wird versucht, zwei separate und eindeutige Klassen zu kompilieren, die beide den Namen haben, `sampleClass` jedoch mit unterschiedlichen Qualifizierungs Pfaden.</span><span class="sxs-lookup"><span data-stu-id="e2d35-128">As a result, it attempts to compile two separate and distinct classes, both named `sampleClass` but with different qualification paths.</span></span>  
  
 <span data-ttu-id="e2d35-129">Der Compiler führt partielle Definitionen nur zusammen, wenn ihre voll qualifizierten Pfade identisch sind.</span><span class="sxs-lookup"><span data-stu-id="e2d35-129">The compiler merges partial definitions only when their fully qualified paths are identical.</span></span>  
  
## <a name="recommendations"></a><span data-ttu-id="e2d35-130">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="e2d35-130">Recommendations</span></span>  

 <span data-ttu-id="e2d35-131">Die folgenden Empfehlungen stellen eine gute Programmierpraxis dar.</span><span class="sxs-lookup"><span data-stu-id="e2d35-131">The following recommendations represent good programming practice.</span></span>  
  
- <span data-ttu-id="e2d35-132">**Eindeutige Namen.**</span><span class="sxs-lookup"><span data-stu-id="e2d35-132">**Unique Names.**</span></span> <span data-ttu-id="e2d35-133">Wenn Sie die vollständige Kontrolle über die Benennung von Programmier Elementen haben, empfiehlt es sich immer, eindeutige Namen überall zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e2d35-133">When you have full control over the naming of programming elements, it is always a good idea to use unique names everywhere.</span></span> <span data-ttu-id="e2d35-134">Identische Namen erfordern eine zusätzliche Qualifizierung und können dazu führen, dass Ihr Code schwieriger zu lesen ist.</span><span class="sxs-lookup"><span data-stu-id="e2d35-134">Identical names require extra qualification and can make your code harder to read.</span></span> <span data-ttu-id="e2d35-135">Sie können auch zu geringfügigen Fehlern und unerwarteten Ergebnissen führen.</span><span class="sxs-lookup"><span data-stu-id="e2d35-135">They can also lead to subtle errors and unexpected results.</span></span>  
  
- <span data-ttu-id="e2d35-136">**Vollständige Qualifizierung.**</span><span class="sxs-lookup"><span data-stu-id="e2d35-136">**Full Qualification.**</span></span> <span data-ttu-id="e2d35-137">Wenn Sie mit Modulen und anderen Elementen im gleichen Namespace arbeiten, besteht der sicherste Ansatz darin, stets die vollständige Qualifikation für alle Programmier Elemente zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e2d35-137">When you are working with modules and other elements in the same namespace, the safest approach is to always use full qualification for all programming elements.</span></span> <span data-ttu-id="e2d35-138">Wenn die Typerweiterung für ein Modulmember besiegt wird und Sie diesen Member nicht vollständig qualifizieren, können Sie versehentlich auf ein anderes Programmier Element zugreifen.</span><span class="sxs-lookup"><span data-stu-id="e2d35-138">If type promotion is defeated for a module member and you do not fully qualify that member, you could inadvertently access a different programming element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2d35-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2d35-139">See also</span></span>

- [<span data-ttu-id="e2d35-140">Module-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e2d35-140">Module Statement</span></span>](../../../language-reference/statements/module-statement.md)
- [<span data-ttu-id="e2d35-141">Namespace-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e2d35-141">Namespace Statement</span></span>](../../../language-reference/statements/namespace-statement.md)
- [<span data-ttu-id="e2d35-142">Partial</span><span class="sxs-lookup"><span data-stu-id="e2d35-142">Partial</span></span>](../../../language-reference/modifiers/partial.md)
- [<span data-ttu-id="e2d35-143">Gültigkeitsbereich in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e2d35-143">Scope in Visual Basic</span></span>](scope.md)
- [<span data-ttu-id="e2d35-144">Vorgehensweise: Steuern des Gültigkeitsbereichs einer Variablen</span><span class="sxs-lookup"><span data-stu-id="e2d35-144">How to: Control the Scope of a Variable</span></span>](how-to-control-the-scope-of-a-variable.md)
- [<span data-ttu-id="e2d35-145">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="e2d35-145">References to Declared Elements</span></span>](references-to-declared-elements.md)
