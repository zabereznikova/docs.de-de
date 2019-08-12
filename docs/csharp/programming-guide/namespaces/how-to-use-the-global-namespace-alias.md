---
title: 'Vorgehensweise: Verwenden des globalen Namespacealias – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- aliases [C#]
- namespaces [C#], global namespace qualifier
- global namespace [C#]
ms.assetid: 98a1d89b-3c5a-44f7-8400-c4a3c0ec22a9
ms.openlocfilehash: b163981d3cf6d56ab953757931b0b386a47263ff
ms.sourcegitcommit: bbfcc913c275885381820be28f61efcf8e83eecc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2019
ms.locfileid: "68796291"
---
# <a name="how-to-use-the-global-namespace-alias-c-programming-guide"></a><span data-ttu-id="83881-102">Vorgehensweise: Verwenden des globalen Namespacealias (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="83881-102">How to: Use the Global Namespace Alias (C# Programming Guide)</span></span>
<span data-ttu-id="83881-103">Die Möglichkeit, auf einen Member im globalen [Namespace](../../../csharp/language-reference/keywords/namespace.md) zuzugreifen, ist nützlich, wenn der Member möglicherweise von einer anderen Entität mit dem gleichen Namen verdeckt wird.</span><span class="sxs-lookup"><span data-stu-id="83881-103">The ability to access a member in the global [namespace](../../../csharp/language-reference/keywords/namespace.md) is useful when the member might be hidden by another entity of the same name.</span></span>  
  
 <span data-ttu-id="83881-104">Im folgenden Code wird `Console` z.B. zu `TestApp.Console` statt zum `Console`-Typ im <xref:System>-Namespace aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="83881-104">For example, in the following code, `Console` resolves to `TestApp.Console` instead of to the `Console` type in the <xref:System> namespace.</span></span>  
  
 [!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]  
  
 [!code-csharp[csProgGuideNamespaces#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#1)]  
  
 <span data-ttu-id="83881-105">Wenn Sie `System.Console` verwenden, führt dies immer noch zu einem Fehler, da der `System`-Namespace von der `TestApp.System`-Klasse verborgen wird:</span><span class="sxs-lookup"><span data-stu-id="83881-105">Using `System.Console` still results in an error because the `System` namespace is hidden by the class `TestApp.System`:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#2)]  
  
 <span data-ttu-id="83881-106">Diesen Fehler können Sie jedoch umgehen, indem Sie `global::System.Console` folgendermaßen verwenden:</span><span class="sxs-lookup"><span data-stu-id="83881-106">However, you can work around this error by using `global::System.Console`, like this:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#3)]  
  
 <span data-ttu-id="83881-107">Wenn der linke Bezeichner `global` ist, beginnt die Suche nach dem richtigen Bezeichner im globalen Namespace.</span><span class="sxs-lookup"><span data-stu-id="83881-107">When the left identifier is `global`, the search for the right identifier starts at the global namespace.</span></span> <span data-ttu-id="83881-108">Die folgende Deklaration verweist z.B. auf `TestApp` als Member des globalen Spaces.</span><span class="sxs-lookup"><span data-stu-id="83881-108">For example, the following declaration is referencing `TestApp` as a member of the global space.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#4)]  
  
 <span data-ttu-id="83881-109">Es wird natürlich nicht empfohlen, dass Sie Ihren eigenen Namespace mit dem Namen `System` erstellen, und es ist unwahrscheinlich, dass Sie Code finden, in dem dies der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="83881-109">Obviously, creating your own namespaces called `System` is not recommended, and it is unlikely you will encounter any code in which this has happened.</span></span> <span data-ttu-id="83881-110">In größeren Projekte ist es jedoch mehr als möglich, dass Namespaceduplikate auf irgendeine Weise vorkommen.</span><span class="sxs-lookup"><span data-stu-id="83881-110">However, in larger projects, it is a very real possibility that namespace duplication may occur in one form or another.</span></span> <span data-ttu-id="83881-111">In derartigen Situationen ist der globale Namespacequalifizierer die Garantie für Sie, den Stammnamespace angeben zu können.</span><span class="sxs-lookup"><span data-stu-id="83881-111">In these situations, the global namespace qualifier is your guarantee that you can specify the root namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83881-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="83881-112">See also</span></span>

- [<span data-ttu-id="83881-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="83881-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="83881-114">Namespaces</span><span class="sxs-lookup"><span data-stu-id="83881-114">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)
- [<span data-ttu-id="83881-115">:: Operator</span><span class="sxs-lookup"><span data-stu-id="83881-115">:: Operator</span></span>](../../../csharp/language-reference/operators/namespace-alias-qualifier.md)
- [<span data-ttu-id="83881-116">extern</span><span class="sxs-lookup"><span data-stu-id="83881-116">extern</span></span>](../../../csharp/language-reference/keywords/extern.md)
