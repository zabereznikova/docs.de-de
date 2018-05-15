---
title: typeof (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- typeof
- typeof_CSharpKeyword
helpviewer_keywords:
- typeof keyword [C#]
ms.assetid: 0c08d880-515e-46bb-8cd2-48b8dd62c08d
ms.openlocfilehash: be79fa4f2cfb1119a50201bf6c18a144726f2f21
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="typeof-c-reference"></a><span data-ttu-id="d219c-102">typeof (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="d219c-102">typeof (C# Reference)</span></span>
<span data-ttu-id="d219c-103">Wird zum Abrufen des Objekts `System.Type` eines Typs verwendet.</span><span class="sxs-lookup"><span data-stu-id="d219c-103">Used to obtain the `System.Type` object for a type.</span></span> <span data-ttu-id="d219c-104">Der Ausdruck `typeof` weist folgende Form auf:</span><span class="sxs-lookup"><span data-stu-id="d219c-104">A `typeof` expression takes the following form:</span></span>  
  
```  
System.Type type = typeof(int);  
```  
  
## <a name="remarks"></a><span data-ttu-id="d219c-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d219c-105">Remarks</span></span>  
 <span data-ttu-id="d219c-106">Um den Runtime-Typ eines Ausdrucks zu erhalten, können Sie die .NET Framework-Methode <xref:System.Object.GetType%2A> wie in folgendem Beispiel verwenden:</span><span class="sxs-lookup"><span data-stu-id="d219c-106">To obtain the run-time type of an expression, you can use the .NET Framework method <xref:System.Object.GetType%2A>, as in the following example:</span></span>  
  
```  
int i = 0;  
System.Type type = i.GetType();  
```  
  
 <span data-ttu-id="d219c-107">Operator `typeof` kann nicht überladen werden.</span><span class="sxs-lookup"><span data-stu-id="d219c-107">The `typeof` operator cannot be overloaded.</span></span>  
  
 <span data-ttu-id="d219c-108">Der Operator `typeof` kann auch bei offenen generischen Typen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d219c-108">The `typeof` operator can also be used on open generic types.</span></span> <span data-ttu-id="d219c-109">Typen mit mehr als einem Parameter müssen die entsprechende Anzahl von Kommas in der Spezifikation haben.</span><span class="sxs-lookup"><span data-stu-id="d219c-109">Types with more than one type parameter must have the appropriate number of commas in the specification.</span></span> <span data-ttu-id="d219c-110">Das folgende Beispiel zeigt, wie Sie bestimmen, ob der Rückgabetyp einer Methode ein generischer <xref:System.Collections.Generic.IEnumerable%601> ist.</span><span class="sxs-lookup"><span data-stu-id="d219c-110">The following example shows how to determine whether the return type of a method is a generic <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="d219c-111">Nehmen Sie an, dass die Methode eine Instanz eines MethodInfo-Typs ist:</span><span class="sxs-lookup"><span data-stu-id="d219c-111">Assume that method is an instance of a MethodInfo type:</span></span>  
  
```  
string s = method.ReturnType.GetInterface  
    (typeof(System.Collections.Generic.IEnumerable<>).FullName);  
```  
  
## <a name="example"></a><span data-ttu-id="d219c-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d219c-112">Example</span></span>  
 [!code-csharp[csrefKeywordsOperator#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="d219c-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d219c-113">Example</span></span>  
 <span data-ttu-id="d219c-114">Dieses Beispiel verwendet die <xref:System.Object.GetType%2A>-Methode um den Typ zu bestimmen, der verwendet wird, um das Ergebnis einer numerischen Berechnung zu speichern.</span><span class="sxs-lookup"><span data-stu-id="d219c-114">This sample uses the <xref:System.Object.GetType%2A> method to determine the type that is used to contain the result of a numeric calculation.</span></span> <span data-ttu-id="d219c-115">Dies hängt vom Speicherbedarf der resultierenden Zahl ab.</span><span class="sxs-lookup"><span data-stu-id="d219c-115">This depends on the storage requirements of the resulting number.</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="d219c-116">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="d219c-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d219c-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d219c-117">See Also</span></span>  
 <xref:System.Type?displayProperty=nameWithType>  
 [<span data-ttu-id="d219c-118">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="d219c-118">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="d219c-119">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="d219c-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="d219c-120">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d219c-120">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="d219c-121">is</span><span class="sxs-lookup"><span data-stu-id="d219c-121">is</span></span>](../../../csharp/language-reference/keywords/is.md)  
 [<span data-ttu-id="d219c-122">Operatorschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d219c-122">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)
