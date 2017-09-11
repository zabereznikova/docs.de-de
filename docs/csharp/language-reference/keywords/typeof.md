---
title: typeof (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- typeof
- typeof_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- typeof keyword [C#]
ms.assetid: 0c08d880-515e-46bb-8cd2-48b8dd62c08d
caps.latest.revision: 21
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
ms.openlocfilehash: fdb335e44a5a3634520d3a86495a4508597b4f70
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="typeof-c-reference"></a><span data-ttu-id="e6c2a-102">typeof (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="e6c2a-102">typeof (C# Reference)</span></span>
<span data-ttu-id="e6c2a-103">Wird zum Abrufen des Objekts `System.Type` eines Typs verwendet.</span><span class="sxs-lookup"><span data-stu-id="e6c2a-103">Used to obtain the `System.Type` object for a type.</span></span> <span data-ttu-id="e6c2a-104">Der Ausdruck `typeof` weist folgende Form auf:</span><span class="sxs-lookup"><span data-stu-id="e6c2a-104">A `typeof` expression takes the following form:</span></span>  
  
```  
System.Type type = typeof(int);  
```  
  
## <a name="remarks"></a><span data-ttu-id="e6c2a-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e6c2a-105">Remarks</span></span>  
 <span data-ttu-id="e6c2a-106">Um den Runtime-Typ eines Ausdrucks zu erhalten, können Sie die .NET Framework-Methode <xref:System.Object.GetType%2A> wie in folgendem Beispiel verwenden:</span><span class="sxs-lookup"><span data-stu-id="e6c2a-106">To obtain the run-time type of an expression, you can use the .NET Framework method <xref:System.Object.GetType%2A>, as in the following example:</span></span>  
  
```  
int i = 0;  
System.Type type = i.GetType();  
```  
  
 <span data-ttu-id="e6c2a-107">Der Operator `typeof` kann nicht überladen werden.</span><span class="sxs-lookup"><span data-stu-id="e6c2a-107">The `typeof` operator cannot be overloaded.</span></span>  
  
 <span data-ttu-id="e6c2a-108">Der Operator `typeof` kann auch bei offenen generischen Typen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e6c2a-108">The `typeof` operator can also be used on open generic types.</span></span> <span data-ttu-id="e6c2a-109">Typen mit mehr als einem Parameter müssen die entsprechende Anzahl von Kommas in der Spezifikation haben.</span><span class="sxs-lookup"><span data-stu-id="e6c2a-109">Types with more than one type parameter must have the appropriate number of commas in the specification.</span></span> <span data-ttu-id="e6c2a-110">Das folgende Beispiel zeigt, wie Sie bestimmen, ob der Rückgabetyp einer Methode ein generischer <xref:System.Collections.Generic.IEnumerable%601> ist.</span><span class="sxs-lookup"><span data-stu-id="e6c2a-110">The following example shows how to determine whether the return type of a method is a generic <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="e6c2a-111">Nehmen Sie an, dass die Methode eine Instanz eines MethodInfo-Typs ist:</span><span class="sxs-lookup"><span data-stu-id="e6c2a-111">Assume that method is an instance of a MethodInfo type:</span></span>  
  
```  
string s = method.ReturnType.GetInterface  
    (typeof(System.Collections.Generic.IEnumerable<>).FullName);  
```  
  
## <a name="example"></a><span data-ttu-id="e6c2a-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e6c2a-112">Example</span></span>  
 <span data-ttu-id="e6c2a-113">[!code-cs[csrefKeywordsOperator#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e6c2a-113">[!code-cs[csrefKeywordsOperator#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6c2a-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e6c2a-114">Example</span></span>  
 <span data-ttu-id="e6c2a-115">Dieses Beispiel verwendet die <xref:System.Object.GetType%2A>-Methode um den Typ zu bestimmen, der verwendet wird, um das Ergebnis einer numerischen Berechnung zu speichern.</span><span class="sxs-lookup"><span data-stu-id="e6c2a-115">This sample uses the <xref:System.Object.GetType%2A> method to determine the type that is used to contain the result of a numeric calculation.</span></span> <span data-ttu-id="e6c2a-116">Dies hängt vom Speicherbedarf der resultierenden Zahl ab.</span><span class="sxs-lookup"><span data-stu-id="e6c2a-116">This depends on the storage requirements of the resulting number.</span></span>  
  
 <span data-ttu-id="e6c2a-117">[!code-cs[csrefKeywordsOperator#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="e6c2a-117">[!code-cs[csrefKeywordsOperator#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="e6c2a-118">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="e6c2a-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e6c2a-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6c2a-119">See Also</span></span>  
 <span data-ttu-id="e6c2a-120"><xref:System.Type?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="e6c2a-120"><xref:System.Type?displayProperty=fullName></span></span>   
 <span data-ttu-id="e6c2a-121">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="e6c2a-121">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="e6c2a-122">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e6c2a-122">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="e6c2a-123">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="e6c2a-123">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="e6c2a-124">[is](../../../csharp/language-reference/keywords/is.md) </span><span class="sxs-lookup"><span data-stu-id="e6c2a-124">[is](../../../csharp/language-reference/keywords/is.md) </span></span>  
 [<span data-ttu-id="e6c2a-125">Operatorschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="e6c2a-125">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)

