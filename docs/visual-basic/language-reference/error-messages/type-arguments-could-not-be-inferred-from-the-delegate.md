---
title: Die Typargumente konnten nicht vom Delegaten abgeleitet werden
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36564
- vbc36564
helpviewer_keywords: BC36564
ms.assetid: 21312807-e1cd-4ac1-ae1c-c28a9c25164d
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 57a3a24af32d9eb85a0f905aa3a73a956723b6d4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="type-arguments-could-not-be-inferred-from-the-delegate"></a><span data-ttu-id="8dd85-102">Die Typargumente konnten nicht vom Delegaten abgeleitet werden</span><span class="sxs-lookup"><span data-stu-id="8dd85-102">Type arguments could not be inferred from the delegate</span></span>
<span data-ttu-id="8dd85-103">Eine Zuweisungsanweisung verwendet `AddressOf` , um die Adresse einer generischen Prozedur zu einem Delegaten zuzuweisen, aber sie stellt keine Typargumente für die generische Prozedur bereit.</span><span class="sxs-lookup"><span data-stu-id="8dd85-103">An assignment statement uses `AddressOf` to assign the address of a generic procedure to a delegate, but it does not supply any type arguments to the generic procedure.</span></span>  
  
 <span data-ttu-id="8dd85-104">Wenn Sie einen generischen Typ aufrufen, geben Sie in der Regel für jeden Typparameter, der durch den generischen Typ definiert wird, ein Typargument an.</span><span class="sxs-lookup"><span data-stu-id="8dd85-104">Normally, when you invoke a generic type, you supply a type argument for each type parameter that the generic type defines.</span></span> <span data-ttu-id="8dd85-105">Wenn Sie keine Typargumente angeben, versucht der Compiler, die an die Typparameter zu übergebenden Typen abzuleiten.</span><span class="sxs-lookup"><span data-stu-id="8dd85-105">If you do not supply any type arguments, the compiler attempts to infer the types to be passed to the type parameters.</span></span> <span data-ttu-id="8dd85-106">Wenn der Kontext nicht genügend Informationen für den Compiler für die Ableitung der Typen bereitstellt, wird ein Fehler generiert.</span><span class="sxs-lookup"><span data-stu-id="8dd85-106">If the context does not provide enough information for the compiler to infer the types, an error is generated.</span></span>  
  
 <span data-ttu-id="8dd85-107">**Fehler-ID:** BC36564</span><span class="sxs-lookup"><span data-stu-id="8dd85-107">**Error ID:** BC36564</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8dd85-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="8dd85-108">To correct this error</span></span>  
  
-   <span data-ttu-id="8dd85-109">Geben Sie im `AddressOf` -Ausdruck die Typargumente für die generische Prozedur an.</span><span class="sxs-lookup"><span data-stu-id="8dd85-109">Specify the type arguments for the generic procedure in the `AddressOf` expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dd85-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8dd85-110">See Also</span></span>  
 [<span data-ttu-id="8dd85-111">Generische Typen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8dd85-111">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="8dd85-112">AddressOf-Operator</span><span class="sxs-lookup"><span data-stu-id="8dd85-112">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [<span data-ttu-id="8dd85-113">Generische Prozeduren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8dd85-113">Generic Procedures in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)  
 [<span data-ttu-id="8dd85-114">Typliste</span><span class="sxs-lookup"><span data-stu-id="8dd85-114">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)  
 [<span data-ttu-id="8dd85-115">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="8dd85-115">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
