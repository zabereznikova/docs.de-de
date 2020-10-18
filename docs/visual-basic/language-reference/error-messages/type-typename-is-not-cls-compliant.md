---
title: Typ "<typename>" ist nicht CLS-kompatibel.
ms.date: 07/20/2015
f1_keywords:
- bc40041
- vbc40041
helpviewer_keywords:
- BC40041
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
ms.openlocfilehash: c50e721e9170a402724a11f3aab573c7e8abf4c1
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161165"
---
# <a name="bc40041-type-typename-is-not-cls-compliant"></a><span data-ttu-id="a181d-102">BC40041: der Typ \<typename> ist nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="a181d-102">BC40041: Type \<typename> is not CLS-compliant</span></span>

<span data-ttu-id="a181d-103">Eine Variable, eine Eigenschaft oder eine Funktions Rückgabe wird mit einem Datentyp deklariert, der nicht CLS-kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="a181d-103">A variable, property, or function return is declared with a data type that is not CLS-compliant.</span></span>

 <span data-ttu-id="a181d-104">Damit eine Anwendung mit der [Sprachunabhängigkeit und den Language-Independent Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS) kompatibel ist, darf Sie nur CLS-kompatible Typen verwenden.</span><span class="sxs-lookup"><span data-stu-id="a181d-104">For an application to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span>

 <span data-ttu-id="a181d-105">Die folgenden Visual Basic-Datentypen sind nicht CLS-kompatibel:</span><span class="sxs-lookup"><span data-stu-id="a181d-105">The following Visual Basic data types are not CLS-compliant:</span></span>

- [<span data-ttu-id="a181d-106">SByte-Datentyp</span><span class="sxs-lookup"><span data-stu-id="a181d-106">SByte Data Type</span></span>](../data-types/sbyte-data-type.md)

- [<span data-ttu-id="a181d-107">UInteger-Datentyp</span><span class="sxs-lookup"><span data-stu-id="a181d-107">UInteger Data Type</span></span>](../data-types/uinteger-data-type.md)

- [<span data-ttu-id="a181d-108">ULong-Datentyp</span><span class="sxs-lookup"><span data-stu-id="a181d-108">ULong Data Type</span></span>](../data-types/ulong-data-type.md)

- [<span data-ttu-id="a181d-109">UShort-Datentyp</span><span class="sxs-lookup"><span data-stu-id="a181d-109">UShort Data Type</span></span>](../data-types/ushort-data-type.md)

 <span data-ttu-id="a181d-110">**Fehler-ID:** BC40041</span><span class="sxs-lookup"><span data-stu-id="a181d-110">**Error ID:** BC40041</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="a181d-111">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="a181d-111">To correct this error</span></span>

- <span data-ttu-id="a181d-112">Wenn die Anwendung CLS-kompatibel sein muss, ändern Sie den Datentyp dieses Elements in den nächstgelegenen CLS-kompatiblen Typ.</span><span class="sxs-lookup"><span data-stu-id="a181d-112">If your application needs to be CLS-compliant, change the data type of this element to the closest CLS-compliant type.</span></span> <span data-ttu-id="a181d-113">Anstelle von `UInteger` könnten Sie beispielsweise `Integer` verwenden, wenn Sie den Wertebereich über 2.147.483.647 nicht benötigen.</span><span class="sxs-lookup"><span data-stu-id="a181d-113">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="a181d-114">Wenn Sie den erweiterten Bereich benötigen, können Sie `UInteger` durch `Long`ersetzen.</span><span class="sxs-lookup"><span data-stu-id="a181d-114">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>

- <span data-ttu-id="a181d-115">Wenn Ihre Anwendung nicht CLS-kompatibel sein muss, müssen Sie nichts ändern.</span><span class="sxs-lookup"><span data-stu-id="a181d-115">If your application does not need to be CLS-compliant, you do not need to change anything.</span></span> <span data-ttu-id="a181d-116">Beachten Sie jedoch die Nichtkonformität.</span><span class="sxs-lookup"><span data-stu-id="a181d-116">You should be aware of its noncompliance, however.</span></span>
