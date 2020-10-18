---
title: "\"Optional\" erwartet."
ms.date: 07/20/2015
f1_keywords:
- bc30202
- vbc30202
helpviewer_keywords:
- BC30202
ms.assetid: 6f75060c-2db4-4a79-b5d1-5780c09a74cd
ms.openlocfilehash: 9c717cef2052722563e04595ef7a808ea103a75d
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159819"
---
# <a name="bc30202-optional-expected"></a><span data-ttu-id="71080-102">BC30202: "optional" erwartet.</span><span class="sxs-lookup"><span data-stu-id="71080-102">BC30202: 'Optional' expected</span></span>

<span data-ttu-id="71080-103">Auf ein optionales Argument in einer Prozedur Deklaration folgt ein erforderliches Argument.</span><span class="sxs-lookup"><span data-stu-id="71080-103">An optional argument in a procedure declaration is followed by a required argument.</span></span> <span data-ttu-id="71080-104">Jedes Argument, das auf ein optionales Argument folgt, muss ebenfalls optional sein.</span><span class="sxs-lookup"><span data-stu-id="71080-104">Every argument following an optional argument must also be optional.</span></span>

 <span data-ttu-id="71080-105">**Fehler-ID:** BC30202</span><span class="sxs-lookup"><span data-stu-id="71080-105">**Error ID:** BC30202</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="71080-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="71080-106">To correct this error</span></span>

- <span data-ttu-id="71080-107">Wenn das Argument erforderlich ist, verschieben Sie es vor dem ersten optionalen Argument in der Argumentliste.</span><span class="sxs-lookup"><span data-stu-id="71080-107">If the argument is intended to be required, move it to precede the first optional argument in the argument list.</span></span>

- <span data-ttu-id="71080-108">Wenn das Argument optional sein soll, verwenden Sie das- `Optional` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="71080-108">If the argument is intended to be optional, use the `Optional` keyword.</span></span>

## <a name="see-also"></a><span data-ttu-id="71080-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="71080-109">See also</span></span>

- [<span data-ttu-id="71080-110">Optionale Parameter</span><span class="sxs-lookup"><span data-stu-id="71080-110">Optional Parameters</span></span>](../../programming-guide/language-features/procedures/optional-parameters.md)
