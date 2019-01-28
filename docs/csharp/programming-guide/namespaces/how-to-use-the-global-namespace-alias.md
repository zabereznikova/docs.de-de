---
title: 'Vorgehensweise: Verwenden des globalen Namespacealias – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- aliases [C#]
- namespaces [C#], global namespace qualifier
- global namespace [C#]
ms.assetid: 98a1d89b-3c5a-44f7-8400-c4a3c0ec22a9
ms.openlocfilehash: e01f8d5e8868c11a88d99c42fba06d8fefa5dc92
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491688"
---
# <a name="how-to-use-the-global-namespace-alias-c-programming-guide"></a><span data-ttu-id="0c2ee-102">Vorgehensweise: Verwenden des globalen Namespacealias (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="0c2ee-102">How to: Use the Global Namespace Alias (C# Programming Guide)</span></span>
<span data-ttu-id="0c2ee-103">Die Möglichkeit, auf einen Member im globalen [Namespace](../../../csharp/language-reference/keywords/namespace.md) zuzugreifen, ist nützlich, wenn der Member möglicherweise von einer anderen Entität mit dem gleichen Namen verdeckt wird.</span><span class="sxs-lookup"><span data-stu-id="0c2ee-103">The ability to access a member in the global [namespace](../../../csharp/language-reference/keywords/namespace.md) is useful when the member might be hidden by another entity of the same name.</span></span>  
  
 <span data-ttu-id="0c2ee-104">Im folgenden Code wird `Console` z.B. zu `TestApp.Console` statt zum `Console`-Typ im <xref:System>-Namespace aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="0c2ee-104">For example, in the following code, `Console` resolves to `TestApp.Console` instead of to the `Console` type in the <xref:System> namespace.</span></span>  
  
 [!code-csharp[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-use-the-global-namespace-alias_1.cs)]  
  
 [!code-csharp[csProgGuideNamespaces#1](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_2.cs)]  
  
 <span data-ttu-id="0c2ee-105">Wenn Sie `System.Console` verwenden, führt dies immer noch zu einem Fehler, da der `System`-Namespace von der `TestApp.System`-Klasse verborgen wird:</span><span class="sxs-lookup"><span data-stu-id="0c2ee-105">Using `System.Console` still results in an error because the `System` namespace is hidden by the class `TestApp.System`:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#2](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_3.cs)]  
  
 <span data-ttu-id="0c2ee-106">Diesen Fehler können Sie jedoch umgehen, indem Sie `global::System.Console` folgendermaßen verwenden:</span><span class="sxs-lookup"><span data-stu-id="0c2ee-106">However, you can work around this error by using `global::System.Console`, like this:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#3](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_4.cs)]  
  
 <span data-ttu-id="0c2ee-107">Wenn der linke Bezeichner `global` ist, beginnt die Suche nach dem richtigen Bezeichner im globalen Namespace.</span><span class="sxs-lookup"><span data-stu-id="0c2ee-107">When the left identifier is `global`, the search for the right identifier starts at the global namespace.</span></span> <span data-ttu-id="0c2ee-108">Die folgende Deklaration verweist z.B. auf `TestApp` als Member des globalen Spaces.</span><span class="sxs-lookup"><span data-stu-id="0c2ee-108">For example, the following declaration is referencing `TestApp` as a member of the global space.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#4](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_5.cs)]  
  
 <span data-ttu-id="0c2ee-109">Es wird natürlich nicht empfohlen, dass Sie Ihren eigenen Namespace mit dem Namen `System` erstellen, und es ist unwahrscheinlich, dass Sie Code finden, in dem dies der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="0c2ee-109">Obviously, creating your own namespaces called `System` is not recommended, and it is unlikely you will encounter any code in which this has happened.</span></span> <span data-ttu-id="0c2ee-110">In größeren Projekte ist es jedoch mehr als möglich, dass Namespaceduplikate auf irgendeine Weise vorkommen.</span><span class="sxs-lookup"><span data-stu-id="0c2ee-110">However, in larger projects, it is a very real possibility that namespace duplication may occur in one form or another.</span></span> <span data-ttu-id="0c2ee-111">In derartigen Situationen ist der globale Namespacequalifizierer die Garantie für Sie, den Stammnamespace angeben zu können.</span><span class="sxs-lookup"><span data-stu-id="0c2ee-111">In these situations, the global namespace qualifier is your guarantee that you can specify the root namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c2ee-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0c2ee-112">Example</span></span>  
 <span data-ttu-id="0c2ee-113">In diesem Beispiel wird der `System`-Namespace verwendet, um die `TestClass`-Klasse einzubeziehen, weshalb `global::System.Console` verwendet werden muss, um auf die `System.Console`-Klasse zu verweisen, die vom `System`-Namespace verborgen wird.</span><span class="sxs-lookup"><span data-stu-id="0c2ee-113">In this example, the namespace `System` is used to include the class `TestClass` therefore, `global::System.Console` must be used to reference the `System.Console` class, which is hidden by the `System` namespace.</span></span> <span data-ttu-id="0c2ee-114">Darüber hinaus wird der `colAlias`-Alias verwendet, um auf den `System.Collections`-Namespace zu verweisen. Deshalb wurde die Instanz einer <xref:System.Collections.Hashtable?displayProperty=nameWithType> mit diesem Alias statt mit dem Namespace erstellt.</span><span class="sxs-lookup"><span data-stu-id="0c2ee-114">Also, the alias `colAlias` is used to refer to the namespace `System.Collections`; therefore, the instance of a <xref:System.Collections.Hashtable?displayProperty=nameWithType> was created using this alias instead of the namespace.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#5](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_6.cs)]  
  
<span data-ttu-id="0c2ee-115">**A 1**
**B 2**
**C 3**</span><span class="sxs-lookup"><span data-stu-id="0c2ee-115">**A 1**
**B 2**
**C 3**</span></span>

## <a name="see-also"></a><span data-ttu-id="0c2ee-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0c2ee-116">See also</span></span>

- [<span data-ttu-id="0c2ee-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="0c2ee-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="0c2ee-118">Namespaces</span><span class="sxs-lookup"><span data-stu-id="0c2ee-118">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)
- [<span data-ttu-id="0c2ee-119">. Operator</span><span class="sxs-lookup"><span data-stu-id="0c2ee-119">. Operator</span></span>](../../../csharp/language-reference/operators/member-access-operator.md)
- [<span data-ttu-id="0c2ee-120">:: Operator</span><span class="sxs-lookup"><span data-stu-id="0c2ee-120">:: Operator</span></span>](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)
- [<span data-ttu-id="0c2ee-121">extern</span><span class="sxs-lookup"><span data-stu-id="0c2ee-121">extern</span></span>](../../../csharp/language-reference/keywords/extern.md)
