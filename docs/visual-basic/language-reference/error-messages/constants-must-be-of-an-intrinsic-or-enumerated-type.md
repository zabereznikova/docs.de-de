---
title: Konstanten müssen einen systeminternen oder enumerierten Typ aufweisen, keinen Klassen-, Struktur-, Typparameter- oder Arraytyp.
ms.date: 07/20/2015
f1_keywords:
- vbc30424
- bc30424
helpviewer_keywords:
- BC30424
ms.assetid: 2d402c2f-27ad-428b-b699-d45cd62f7196
ms.openlocfilehash: 88bbab2005b464ee97d647f2b4b9be6ff81e2d82
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61649841"
---
# <a name="constants-must-be-of-an-intrinsic-or-enumerated-type-not-a-class-structure-type-parameter-or-array-type"></a><span data-ttu-id="b7799-102">Konstanten müssen einen systeminternen oder enumerierten Typ aufweisen, keinen Klassen-, Struktur-, Typparameter- oder Arraytyp.</span><span class="sxs-lookup"><span data-stu-id="b7799-102">Constants must be of an intrinsic or enumerated type, not a class, structure, type parameter, or array type</span></span>
<span data-ttu-id="b7799-103">Sie haben versucht, eine Konstante als eine Klasse, Struktur oder Arraytyp oder als eine von einem enthaltenden generischen Typ definierten Typparameter deklarieren.</span><span class="sxs-lookup"><span data-stu-id="b7799-103">You have attempted to declare a constant as a class, structure, or array type, or as a type parameter defined by a containing generic type.</span></span>  
  
 <span data-ttu-id="b7799-104">Konstanten müssen einen systeminternen Typ sein (`Boolean`, `Byte`, `Date`, `Decimal`, `Double`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, oder `UShort`), oder ein `Enum` Typ basierend auf einer ganzzahligen Typen.</span><span class="sxs-lookup"><span data-stu-id="b7799-104">Constants must be of an intrinsic type (`Boolean`, `Byte`, `Date`, `Decimal`, `Double`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, or `UShort`), or an `Enum` type based on one of the integral types.</span></span>  
  
 <span data-ttu-id="b7799-105">**Fehler-ID:** BC30424</span><span class="sxs-lookup"><span data-stu-id="b7799-105">**Error ID:** BC30424</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b7799-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="b7799-106">To correct this error</span></span>  
  
1. <span data-ttu-id="b7799-107">Deklarieren Sie die Konstante als systeminterne Funktion oder `Enum` Typ.</span><span class="sxs-lookup"><span data-stu-id="b7799-107">Declare the constant as an intrinsic or `Enum` type.</span></span>  
  
2. <span data-ttu-id="b7799-108">Eine Konstante kann auch sein ein spezieller Wert wie z. B. `True`, `False`, oder `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="b7799-108">A constant can also be a special value such as `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="b7799-109">Der Compiler betrachtet diese vordefinierten Werte von den entsprechenden systeminternen Typ sein.</span><span class="sxs-lookup"><span data-stu-id="b7799-109">The compiler considers these predefined values to be of the appropriate intrinsic type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7799-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b7799-110">See also</span></span>

- [<span data-ttu-id="b7799-111">Konstanten und Enumerationen</span><span class="sxs-lookup"><span data-stu-id="b7799-111">Constants and Enumerations</span></span>](../../../visual-basic/language-reference/constants-and-enumerations.md)
- [<span data-ttu-id="b7799-112">Datentypen</span><span class="sxs-lookup"><span data-stu-id="b7799-112">Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="b7799-113">Datentypen</span><span class="sxs-lookup"><span data-stu-id="b7799-113">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
