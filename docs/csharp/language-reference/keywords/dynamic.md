---
title: dynamic (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- dynamic_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- dynamic [C#]
- dynamic keyword [C#]
ms.assetid: 9e797102-cc83-4964-bf58-afe4f54d16bc
caps.latest.revision: 25
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
ms.openlocfilehash: b68a6ef4dc3dda01638b9bb84db58ba77214f490
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="dynamic-c-reference"></a><span data-ttu-id="772e6-102">dynamic (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="772e6-102">dynamic (C# Reference)</span></span>
<span data-ttu-id="772e6-103">Der `dynamic`-Typ ermöglicht die Vorgänge, in denen er auftritt, um die Typüberprüfung zur Kompilierzeit zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="772e6-103">The `dynamic` type enables the operations in which it occurs to bypass compile-time type checking.</span></span> <span data-ttu-id="772e6-104">Stattdessen werden diese Vorgänge zur Laufzeit aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="772e6-104">Instead, these operations are resolved at run time.</span></span> <span data-ttu-id="772e6-105">Der `dynamic`-Typ vereinfacht den Zugriff auf COM-APIs, z.B. die Office Automation-APIs, und auch auf dynamische APIs, beispielsweise IronPython-Bibliotheken und auf das HTML-Dokumentobjektmodell (Document Object Model, DOM).</span><span class="sxs-lookup"><span data-stu-id="772e6-105">The `dynamic` type simplifies access to COM APIs such as the Office Automation APIs, and also to dynamic APIs such as IronPython libraries, and to the HTML Document Object Model (DOM).</span></span>  
  
 <span data-ttu-id="772e6-106">Der Typ `dynamic` verhält sich in den meisten Fällen wie Typ `object`.</span><span class="sxs-lookup"><span data-stu-id="772e6-106">Type `dynamic` behaves like type `object` in most circumstances.</span></span> <span data-ttu-id="772e6-107">Jedoch werden Vorgänge, die Ausdrücke des Typs `dynamic` enthalten, nicht aufgelöst oder durch den Compiler typgeprüft.</span><span class="sxs-lookup"><span data-stu-id="772e6-107">However, operations that contain expressions of type `dynamic` are not resolved or type checked by the compiler.</span></span> <span data-ttu-id="772e6-108">Der Compiler packt Informationen über den Vorgang. Diese Informationen werden später zur Evaluierung des Vorgangs zur Laufzeit verwendet.</span><span class="sxs-lookup"><span data-stu-id="772e6-108">The compiler packages together information about the operation, and that information is later used to evaluate the operation at run time.</span></span> <span data-ttu-id="772e6-109">Als Teil dieses Prozesses werden Variablen des Typs `dynamic` in Variablen des Typs `object` kompiliert.</span><span class="sxs-lookup"><span data-stu-id="772e6-109">As part of the process, variables of type `dynamic` are compiled into variables of type `object`.</span></span> <span data-ttu-id="772e6-110">Deshalb existiert der Typ `dynamic` nur zur Kompilierzeit und nicht zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="772e6-110">Therefore, type `dynamic` exists only at compile time, not at run time.</span></span>  
  
 <span data-ttu-id="772e6-111">Das folgende Beispiel vergleicht den Unterschied einer Variable des Typs `dynamic` mit einer Variable des Typs `object`.</span><span class="sxs-lookup"><span data-stu-id="772e6-111">The following example contrasts a variable of type `dynamic` to a variable of type `object`.</span></span> <span data-ttu-id="772e6-112">Um den Typ jeder Variable zur Kompilierzeit zu überprüfen, zeigen Sie mit dem Mauszeiger auf `dyn` oder `obj` in den `WriteLine`-Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="772e6-112">To verify the type of each variable at compile time, place the mouse pointer over `dyn` or `obj` in the `WriteLine` statements.</span></span> <span data-ttu-id="772e6-113">IntelliSense zeigt **dynamic** für `dyn` und **object** für `obj`.</span><span class="sxs-lookup"><span data-stu-id="772e6-113">IntelliSense shows **dynamic** for `dyn` and **object** for `obj`.</span></span>  
  
 <span data-ttu-id="772e6-114">[!code-cs[csrefKeywordsTypes#21](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="772e6-114">[!code-cs[csrefKeywordsTypes#21](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_1.cs)]</span></span>  
  
 <span data-ttu-id="772e6-115">Die `WriteLine`-Anweisungen zeigen die Laufzeittypen von `dyn` und `obj`.</span><span class="sxs-lookup"><span data-stu-id="772e6-115">The `WriteLine` statements display the run-time types of `dyn` and `obj`.</span></span> <span data-ttu-id="772e6-116">Zu diesem Zeitpunkt verfügen beide denselben Typ, Integer.</span><span class="sxs-lookup"><span data-stu-id="772e6-116">At that point, both have the same type, integer.</span></span> <span data-ttu-id="772e6-117">Es wird die folgende Ausgabe generiert:</span><span class="sxs-lookup"><span data-stu-id="772e6-117">The following output is produced:</span></span>  
  
 `System.Int32`  
  
 `System.Int32`  
  
 <span data-ttu-id="772e6-118">Um den Unterschied zwischen `dyn` und `obj` zur Kompilierzeit anzuzeigen, fügen Sie die folgenden zwei Zeilen zwischen die Deklarationen und die `WriteLine`-Anweisungen im vorherigen Beispiel ein.</span><span class="sxs-lookup"><span data-stu-id="772e6-118">To see the difference between `dyn` and `obj` at compile time, add the following two lines between the declarations and the `WriteLine` statements in the previous example.</span></span>  
  
```csharp  
dyn = dyn + 3;  
obj = obj + 3;  
```  
  
 <span data-ttu-id="772e6-119">Es wird ein Kompilierfehler für den Versuch, einen Integer und ein Objekt im Ausdruck `obj + 3` einzufügen, ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="772e6-119">A compiler error is reported for the attempted addition of an integer and an object in expression `obj + 3`.</span></span> <span data-ttu-id="772e6-120">Es wird jedoch kein Fehler für `dyn + 3` gemeldet.</span><span class="sxs-lookup"><span data-stu-id="772e6-120">However, no error is reported for `dyn + 3`.</span></span> <span data-ttu-id="772e6-121">Der Ausdruck, der `dyn` enthält, wird nicht zur Kompilierzeit überprüft, da der Typ von `dyn` `dynamic` ist.</span><span class="sxs-lookup"><span data-stu-id="772e6-121">The expression that contains `dyn` is not checked at compile time because the type of `dyn` is `dynamic`.</span></span>  
  
## <a name="context"></a><span data-ttu-id="772e6-122">Kontext</span><span class="sxs-lookup"><span data-stu-id="772e6-122">Context</span></span>  
 <span data-ttu-id="772e6-123">Das Schlüsselwort `dynamic` kann direkt oder als Komponente eines konstruierten Typs in den folgenden Situationen erscheinen:</span><span class="sxs-lookup"><span data-stu-id="772e6-123">The `dynamic` keyword can appear directly or as a component of a constructed type in the following situations:</span></span>  
  
-   <span data-ttu-id="772e6-124">In Deklarationen, als Typ einer Eigenschaft, als Feld, Indexer, Parameter, Rückgabewert, lokale Variable oder Typeinschränkung.</span><span class="sxs-lookup"><span data-stu-id="772e6-124">In declarations, as the type of a property, field, indexer, parameter, return value, local variable, or type constraint.</span></span> <span data-ttu-id="772e6-125">Die folgende Klassendefinition verwendet `dynamic` in einigen unterschiedlichen Deklarationen.</span><span class="sxs-lookup"><span data-stu-id="772e6-125">The following class definition uses `dynamic` in several different declarations.</span></span>  
  
     <span data-ttu-id="772e6-126">[!code-cs[csrefKeywordsTypes#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="772e6-126">[!code-cs[csrefKeywordsTypes#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_2.cs)]</span></span>  
  
-   <span data-ttu-id="772e6-127">In expliziten Typkonvertierungen als Zieltyp einer Konversion.</span><span class="sxs-lookup"><span data-stu-id="772e6-127">In explicit type conversions, as the target type of a conversion.</span></span>  
  
     <span data-ttu-id="772e6-128">[!code-cs[csrefKeywordsTypes#23](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="772e6-128">[!code-cs[csrefKeywordsTypes#23](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_3.cs)]</span></span>  
  
-   <span data-ttu-id="772e6-129">In jedem Kontext, in dem Typen als Werte, z.B. auf der rechten Seite eines `is`-Operators oder eines `as`-Operators oder als Argument für `typeof` als Teil eines konstruierten Typs dienen.</span><span class="sxs-lookup"><span data-stu-id="772e6-129">In any context where types serve as values, such as on the right side of an `is` operator or an `as` operator, or as the argument to `typeof` as part of a constructed type.</span></span> <span data-ttu-id="772e6-130">Zum Beispiel kann `dynamic` in den folgenden Ausdrücken verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="772e6-130">For example, `dynamic` can be used in the following expressions.</span></span>  
  
     <span data-ttu-id="772e6-131">[!code-cs[csrefKeywordsTypes#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="772e6-131">[!code-cs[csrefKeywordsTypes#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_4.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="772e6-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="772e6-132">Example</span></span>  
 <span data-ttu-id="772e6-133">Das folgende Beispiel verwendet `dynamic` in einigen Deklarationen.</span><span class="sxs-lookup"><span data-stu-id="772e6-133">The following example uses `dynamic` in several declarations.</span></span> <span data-ttu-id="772e6-134">Die `Main`-Methode unterscheidet auch die Typüberprüfung zur Kompilierzeit und die Laufzeittypüberprüfung.</span><span class="sxs-lookup"><span data-stu-id="772e6-134">The `Main` method also contrasts compile-time type checking with run-time type checking.</span></span>  
  
 <span data-ttu-id="772e6-135">[!code-cs[csrefKeywordsTypes#25](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="772e6-135">[!code-cs[csrefKeywordsTypes#25](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_5.cs)]</span></span>  
  
 <span data-ttu-id="772e6-136">Weitere Informationen und Beispiele finden Sie unter [Verwenden von dynamischen Typen](../../../csharp/programming-guide/types/using-type-dynamic.md).</span><span class="sxs-lookup"><span data-stu-id="772e6-136">For more information and examples, see [Using Type dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="772e6-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="772e6-137">See Also</span></span>  
 <span data-ttu-id="772e6-138"><xref:System.Dynamic.ExpandoObject?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="772e6-138"><xref:System.Dynamic.ExpandoObject?displayProperty=fullName></span></span>   
 <span data-ttu-id="772e6-139"><xref:System.Dynamic.DynamicObject?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="772e6-139"><xref:System.Dynamic.DynamicObject?displayProperty=fullName></span></span>   
 <span data-ttu-id="772e6-140">[Verwenden von dynamischen Typen](../../../csharp/programming-guide/types/using-type-dynamic.md) </span><span class="sxs-lookup"><span data-stu-id="772e6-140">[Using Type dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md) </span></span>  
 <span data-ttu-id="772e6-141">[Objekt](../../../csharp/language-reference/keywords/object.md) </span><span class="sxs-lookup"><span data-stu-id="772e6-141">[object](../../../csharp/language-reference/keywords/object.md) </span></span>  
 <span data-ttu-id="772e6-142">[is](../../../csharp/language-reference/keywords/is.md) </span><span class="sxs-lookup"><span data-stu-id="772e6-142">[is](../../../csharp/language-reference/keywords/is.md) </span></span>  
 <span data-ttu-id="772e6-143">[as](../../../csharp/language-reference/keywords/as.md) </span><span class="sxs-lookup"><span data-stu-id="772e6-143">[as](../../../csharp/language-reference/keywords/as.md) </span></span>  
 <span data-ttu-id="772e6-144">[typeof](../../../csharp/language-reference/keywords/typeof.md) </span><span class="sxs-lookup"><span data-stu-id="772e6-144">[typeof](../../../csharp/language-reference/keywords/typeof.md) </span></span>  
 <span data-ttu-id="772e6-145">[Vorgehensweise: Sichere Umwandlung mit den Operatoren "as" und "is"](../../../csharp/programming-guide/types/how-to-safely-cast-by-using-as-and-is-operators.md) </span><span class="sxs-lookup"><span data-stu-id="772e6-145">[How to: Safely Cast by Using as and is Operators](../../../csharp/programming-guide/types/how-to-safely-cast-by-using-as-and-is-operators.md) </span></span>  
 [<span data-ttu-id="772e6-146">Exemplarische Vorgehensweise: Erstellen und Verwenden von dynamischen Objekten</span><span class="sxs-lookup"><span data-stu-id="772e6-146">Walkthrough: Creating and Using Dynamic Objects</span></span>](../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)

