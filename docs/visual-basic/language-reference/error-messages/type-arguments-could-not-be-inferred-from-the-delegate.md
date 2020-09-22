---
title: Die Typargumente konnten nicht vom Delegaten abgeleitet werden
ms.date: 07/20/2015
f1_keywords:
- bc36564
- vbc36564
helpviewer_keywords:
- BC36564
ms.assetid: 21312807-e1cd-4ac1-ae1c-c28a9c25164d
ms.openlocfilehash: 51b0bbf2e346acdd84a1bc2283db4a71adc9f7dc
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870426"
---
# <a name="type-arguments-could-not-be-inferred-from-the-delegate"></a><span data-ttu-id="63f93-102">Die Typargumente konnten nicht vom Delegaten abgeleitet werden</span><span class="sxs-lookup"><span data-stu-id="63f93-102">Type arguments could not be inferred from the delegate</span></span>

<span data-ttu-id="63f93-103">Eine Zuweisungsanweisung verwendet `AddressOf` , um die Adresse einer generischen Prozedur zu einem Delegaten zuzuweisen, aber sie stellt keine Typargumente für die generische Prozedur bereit.</span><span class="sxs-lookup"><span data-stu-id="63f93-103">An assignment statement uses `AddressOf` to assign the address of a generic procedure to a delegate, but it does not supply any type arguments to the generic procedure.</span></span>  
  
 <span data-ttu-id="63f93-104">Wenn Sie einen generischen Typ aufrufen, geben Sie in der Regel für jeden Typparameter, der durch den generischen Typ definiert wird, ein Typargument an.</span><span class="sxs-lookup"><span data-stu-id="63f93-104">Normally, when you invoke a generic type, you supply a type argument for each type parameter that the generic type defines.</span></span> <span data-ttu-id="63f93-105">Wenn Sie keine Typargumente angeben, versucht der Compiler, die an die Typparameter zu übergebenden Typen abzuleiten.</span><span class="sxs-lookup"><span data-stu-id="63f93-105">If you do not supply any type arguments, the compiler attempts to infer the types to be passed to the type parameters.</span></span> <span data-ttu-id="63f93-106">Wenn der Kontext nicht genügend Informationen für den Compiler für die Ableitung der Typen bereitstellt, wird ein Fehler generiert.</span><span class="sxs-lookup"><span data-stu-id="63f93-106">If the context does not provide enough information for the compiler to infer the types, an error is generated.</span></span>  
  
 <span data-ttu-id="63f93-107">**Fehler-ID:** BC36564</span><span class="sxs-lookup"><span data-stu-id="63f93-107">**Error ID:** BC36564</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="63f93-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="63f93-108">To correct this error</span></span>  
  
- <span data-ttu-id="63f93-109">Geben Sie im `AddressOf` -Ausdruck die Typargumente für die generische Prozedur an.</span><span class="sxs-lookup"><span data-stu-id="63f93-109">Specify the type arguments for the generic procedure in the `AddressOf` expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63f93-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="63f93-110">See also</span></span>

- [<span data-ttu-id="63f93-111">Generische Typen in Visual Basic (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63f93-111">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="63f93-112">AddressOf-Operator</span><span class="sxs-lookup"><span data-stu-id="63f93-112">AddressOf Operator</span></span>](../operators/addressof-operator.md)
- [<span data-ttu-id="63f93-113">Generic Procedures in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="63f93-113">Generic Procedures in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-procedures.md)
- [<span data-ttu-id="63f93-114">Type List</span><span class="sxs-lookup"><span data-stu-id="63f93-114">Type List</span></span>](../statements/type-list.md)
- [<span data-ttu-id="63f93-115">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="63f93-115">Extension Methods</span></span>](../../programming-guide/language-features/procedures/extension-methods.md)
