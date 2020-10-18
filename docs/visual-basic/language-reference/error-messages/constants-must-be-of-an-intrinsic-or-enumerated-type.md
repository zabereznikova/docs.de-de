---
title: Konstanten müssen einen systeminternen oder enumerierten Typ aufweisen, keinen Klassen-, Struktur-, Typparameter- oder Arraytyp.
ms.date: 07/20/2015
f1_keywords:
- vbc30424
- bc30424
helpviewer_keywords:
- BC30424
ms.assetid: 2d402c2f-27ad-428b-b699-d45cd62f7196
ms.openlocfilehash: e820287f0ddf462b30867d90501f7d730c9c6739
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163154"
---
# <a name="bc30424-constants-must-be-of-an-intrinsic-or-enumerated-type-not-a-class-structure-type-parameter-or-array-type"></a><span data-ttu-id="ad9ba-102">BC30424: Konstanten müssen einen systeminternen oder enumerierten Typ aufweisen, keine Klasse, Struktur, Typparameter oder Arraytyp.</span><span class="sxs-lookup"><span data-stu-id="ad9ba-102">BC30424: Constants must be of an intrinsic or enumerated type, not a class, structure, type parameter, or array type</span></span>

<span data-ttu-id="ad9ba-103">Sie haben versucht, eine Konstante als Klasse, Struktur oder Arraytyp oder als Typparameter zu deklarieren, der durch einen enthaltenden generischen Typ definiert wird.</span><span class="sxs-lookup"><span data-stu-id="ad9ba-103">You have attempted to declare a constant as a class, structure, or array type, or as a type parameter defined by a containing generic type.</span></span>

 <span data-ttu-id="ad9ba-104">Konstanten müssen einen systeminternen Typ aufweisen ( `Boolean` , `Byte` , `Date` , `Decimal` , `Double` , `Integer` , `Long` , `Object` , `SByte` , `Short` , `Single` , `String` , `UInteger` , `ULong` oder `UShort` ), oder ein Typ, der `Enum` auf einem der ganzzahligen Typen basiert.</span><span class="sxs-lookup"><span data-stu-id="ad9ba-104">Constants must be of an intrinsic type (`Boolean`, `Byte`, `Date`, `Decimal`, `Double`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, or `UShort`), or an `Enum` type based on one of the integral types.</span></span>

 <span data-ttu-id="ad9ba-105">**Fehler-ID:** BC30424</span><span class="sxs-lookup"><span data-stu-id="ad9ba-105">**Error ID:** BC30424</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="ad9ba-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="ad9ba-106">To correct this error</span></span>

1. <span data-ttu-id="ad9ba-107">Deklarieren Sie die Konstante als systeminterne oder- `Enum` Typ.</span><span class="sxs-lookup"><span data-stu-id="ad9ba-107">Declare the constant as an intrinsic or `Enum` type.</span></span>

2. <span data-ttu-id="ad9ba-108">Eine Konstante kann auch ein spezieller Wert sein, z `True` `False` . b., oder `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="ad9ba-108">A constant can also be a special value such as `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="ad9ba-109">Der Compiler betrachtet diese vordefinierten Werte als den geeigneten systeminternen Typ.</span><span class="sxs-lookup"><span data-stu-id="ad9ba-109">The compiler considers these predefined values to be of the appropriate intrinsic type.</span></span>

## <a name="see-also"></a><span data-ttu-id="ad9ba-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad9ba-110">See also</span></span>

- [<span data-ttu-id="ad9ba-111">Konstanten und Enumerationen</span><span class="sxs-lookup"><span data-stu-id="ad9ba-111">Constants and Enumerations</span></span>](../constants-and-enumerations.md)
- [<span data-ttu-id="ad9ba-112">Datentypen</span><span class="sxs-lookup"><span data-stu-id="ad9ba-112">Data Types</span></span>](../../programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="ad9ba-113">Datentypen</span><span class="sxs-lookup"><span data-stu-id="ad9ba-113">Data Types</span></span>](../data-types/index.md)
