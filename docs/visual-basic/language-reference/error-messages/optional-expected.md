---
title: "\"Optional\" erwartet."
ms.date: 07/20/2015
f1_keywords:
- bc30202
- vbc30202
helpviewer_keywords:
- BC30202
ms.assetid: 6f75060c-2db4-4a79-b5d1-5780c09a74cd
ms.openlocfilehash: 411e3248409ab0184666f4efefb4ec4becf7cab1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409347"
---
# <a name="optional-expected"></a><span data-ttu-id="be30a-102">"Optional" erwartet.</span><span class="sxs-lookup"><span data-stu-id="be30a-102">'Optional' expected</span></span>
<span data-ttu-id="be30a-103">Auf ein optionales Argument in einer Prozedur Deklaration folgt ein erforderliches Argument.</span><span class="sxs-lookup"><span data-stu-id="be30a-103">An optional argument in a procedure declaration is followed by a required argument.</span></span> <span data-ttu-id="be30a-104">Jedes Argument, das auf ein optionales Argument folgt, muss ebenfalls optional sein.</span><span class="sxs-lookup"><span data-stu-id="be30a-104">Every argument following an optional argument must also be optional.</span></span>  
  
 <span data-ttu-id="be30a-105">**Fehler-ID:** BC30202</span><span class="sxs-lookup"><span data-stu-id="be30a-105">**Error ID:** BC30202</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="be30a-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="be30a-106">To correct this error</span></span>  
  
1. <span data-ttu-id="be30a-107">Wenn das Argument erforderlich ist, verschieben Sie es vor dem ersten optionalen Argument in der Argumentliste.</span><span class="sxs-lookup"><span data-stu-id="be30a-107">If the argument is intended to be required, move it to precede the first optional argument in the argument list.</span></span>  
  
2. <span data-ttu-id="be30a-108">Wenn das Argument optional sein soll, verwenden Sie das- `Optional` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="be30a-108">If the argument is intended to be optional, use the `Optional` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be30a-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="be30a-109">See also</span></span>

- [<span data-ttu-id="be30a-110">Optionale Parameter</span><span class="sxs-lookup"><span data-stu-id="be30a-110">Optional Parameters</span></span>](../../programming-guide/language-features/procedures/optional-parameters.md)
