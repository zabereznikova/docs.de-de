---
title: "\"Optional\" erwartet."
ms.date: 07/20/2015
f1_keywords:
- bc30202
- vbc30202
helpviewer_keywords:
- BC30202
ms.assetid: 6f75060c-2db4-4a79-b5d1-5780c09a74cd
ms.openlocfilehash: e212939cf814a9ac632571b2203f2f256dea61ae
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873607"
---
# <a name="optional-expected"></a><span data-ttu-id="70701-102">"Optional" erwartet.</span><span class="sxs-lookup"><span data-stu-id="70701-102">'Optional' expected</span></span>

<span data-ttu-id="70701-103">Auf ein optionales Argument in einer Prozedur Deklaration folgt ein erforderliches Argument.</span><span class="sxs-lookup"><span data-stu-id="70701-103">An optional argument in a procedure declaration is followed by a required argument.</span></span> <span data-ttu-id="70701-104">Jedes Argument, das auf ein optionales Argument folgt, muss ebenfalls optional sein.</span><span class="sxs-lookup"><span data-stu-id="70701-104">Every argument following an optional argument must also be optional.</span></span>  
  
 <span data-ttu-id="70701-105">**Fehler-ID:** BC30202</span><span class="sxs-lookup"><span data-stu-id="70701-105">**Error ID:** BC30202</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="70701-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="70701-106">To correct this error</span></span>  
  
1. <span data-ttu-id="70701-107">Wenn das Argument erforderlich ist, verschieben Sie es vor dem ersten optionalen Argument in der Argumentliste.</span><span class="sxs-lookup"><span data-stu-id="70701-107">If the argument is intended to be required, move it to precede the first optional argument in the argument list.</span></span>  
  
2. <span data-ttu-id="70701-108">Wenn das Argument optional sein soll, verwenden Sie das- `Optional` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="70701-108">If the argument is intended to be optional, use the `Optional` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70701-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="70701-109">See also</span></span>

- [<span data-ttu-id="70701-110">Optionale Parameter</span><span class="sxs-lookup"><span data-stu-id="70701-110">Optional Parameters</span></span>](../../programming-guide/language-features/procedures/optional-parameters.md)
