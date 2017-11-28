---
title: typeof (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- typeof
- typeof_CSharpKeyword
helpviewer_keywords: typeof keyword [C#]
ms.assetid: 0c08d880-515e-46bb-8cd2-48b8dd62c08d
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: be24740ea7f6fbe8780dd9cac58b7dea9aaf6872
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="typeof-c-reference"></a><span data-ttu-id="53b3c-102">typeof (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="53b3c-102">typeof (C# Reference)</span></span>
<span data-ttu-id="53b3c-103">Wird zum Abrufen des Objekts `System.Type` eines Typs verwendet.</span><span class="sxs-lookup"><span data-stu-id="53b3c-103">Used to obtain the `System.Type` object for a type.</span></span> <span data-ttu-id="53b3c-104">Der Ausdruck `typeof` weist folgende Form auf:</span><span class="sxs-lookup"><span data-stu-id="53b3c-104">A `typeof` expression takes the following form:</span></span>  
  
```  
System.Type type = typeof(int);  
```  
  
## <a name="remarks"></a><span data-ttu-id="53b3c-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="53b3c-105">Remarks</span></span>  
 <span data-ttu-id="53b3c-106">Um den Runtime-Typ eines Ausdrucks zu erhalten, können Sie die .NET Framework-Methode <xref:System.Object.GetType%2A> wie in folgendem Beispiel verwenden:</span><span class="sxs-lookup"><span data-stu-id="53b3c-106">To obtain the run-time type of an expression, you can use the .NET Framework method <xref:System.Object.GetType%2A>, as in the following example:</span></span>  
  
```  
int i = 0;  
System.Type type = i.GetType();  
```  
  
 <span data-ttu-id="53b3c-107">Operator `typeof` kann nicht überladen werden.</span><span class="sxs-lookup"><span data-stu-id="53b3c-107">The `typeof` operator cannot be overloaded.</span></span>  
  
 <span data-ttu-id="53b3c-108">Der Operator `typeof` kann auch bei offenen generischen Typen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="53b3c-108">The `typeof` operator can also be used on open generic types.</span></span> <span data-ttu-id="53b3c-109">Typen mit mehr als einem Parameter müssen die entsprechende Anzahl von Kommas in der Spezifikation haben.</span><span class="sxs-lookup"><span data-stu-id="53b3c-109">Types with more than one type parameter must have the appropriate number of commas in the specification.</span></span> <span data-ttu-id="53b3c-110">Das folgende Beispiel zeigt, wie Sie bestimmen, ob der Rückgabetyp einer Methode ein generischer <xref:System.Collections.Generic.IEnumerable%601> ist.</span><span class="sxs-lookup"><span data-stu-id="53b3c-110">The following example shows how to determine whether the return type of a method is a generic <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="53b3c-111">Nehmen Sie an, dass die Methode eine Instanz eines MethodInfo-Typs ist:</span><span class="sxs-lookup"><span data-stu-id="53b3c-111">Assume that method is an instance of a MethodInfo type:</span></span>  
  
```  
string s = method.ReturnType.GetInterface  
    (typeof(System.Collections.Generic.IEnumerable<>).FullName);  
```  
  
## <a name="example"></a><span data-ttu-id="53b3c-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="53b3c-112">Example</span></span>  
 [!code-csharp[csrefKeywordsOperator#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="53b3c-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="53b3c-113">Example</span></span>  
 <span data-ttu-id="53b3c-114">Dieses Beispiel verwendet die <xref:System.Object.GetType%2A>-Methode um den Typ zu bestimmen, der verwendet wird, um das Ergebnis einer numerischen Berechnung zu speichern.</span><span class="sxs-lookup"><span data-stu-id="53b3c-114">This sample uses the <xref:System.Object.GetType%2A> method to determine the type that is used to contain the result of a numeric calculation.</span></span> <span data-ttu-id="53b3c-115">Dies hängt vom Speicherbedarf der resultierenden Zahl ab.</span><span class="sxs-lookup"><span data-stu-id="53b3c-115">This depends on the storage requirements of the resulting number.</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="53b3c-116">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="53b3c-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="53b3c-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="53b3c-117">See Also</span></span>  
 <xref:System.Type?displayProperty=nameWithType>  
 [<span data-ttu-id="53b3c-118">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="53b3c-118">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="53b3c-119">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="53b3c-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="53b3c-120">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="53b3c-120">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="53b3c-121">is</span><span class="sxs-lookup"><span data-stu-id="53b3c-121">is</span></span>](../../../csharp/language-reference/keywords/is.md)  
 [<span data-ttu-id="53b3c-122">Operatorschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="53b3c-122">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)
