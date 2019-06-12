---
title: Typ '<typename>' ist nicht CLS-kompatibel.
ms.date: 07/20/2015
f1_keywords:
- bc40041
- vbc40041
helpviewer_keywords:
- BC40041
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
ms.openlocfilehash: 2805cac71cb36d21f5ab21a5875183803d07a4b4
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65642364"
---
# <a name="type-typename-is-not-cls-compliant"></a><span data-ttu-id="7b1ad-102">Typ \<Typname > ist nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="7b1ad-102">Type \<typename> is not CLS-compliant</span></span>
<span data-ttu-id="7b1ad-103">Eine Variable, Eigenschaft oder Funktionsrückgabe wird mit einem Datentyp deklariert, die nicht CLS-kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="7b1ad-103">A variable, property, or function return is declared with a data type that is not CLS-compliant.</span></span>  
  
 <span data-ttu-id="7b1ad-104">Für eine Anwendung einhalten der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS), müssen sie nur CLS-kompatible Typen verwenden.</span><span class="sxs-lookup"><span data-stu-id="7b1ad-104">For an application to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span>  
  
 <span data-ttu-id="7b1ad-105">Die folgenden Visual Basic-Datentypen sind nicht CLS-kompatibel:</span><span class="sxs-lookup"><span data-stu-id="7b1ad-105">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
- [<span data-ttu-id="7b1ad-106">SByte-Datentyp</span><span class="sxs-lookup"><span data-stu-id="7b1ad-106">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
- [<span data-ttu-id="7b1ad-107">UInteger-Datentyp</span><span class="sxs-lookup"><span data-stu-id="7b1ad-107">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
- [<span data-ttu-id="7b1ad-108">ULong-Datentyp</span><span class="sxs-lookup"><span data-stu-id="7b1ad-108">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
- [<span data-ttu-id="7b1ad-109">UShort-Datentyp</span><span class="sxs-lookup"><span data-stu-id="7b1ad-109">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="7b1ad-110">**Fehler-ID:** BC40041</span><span class="sxs-lookup"><span data-stu-id="7b1ad-110">**Error ID:** BC40041</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7b1ad-111">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="7b1ad-111">To correct this error</span></span>  
  
- <span data-ttu-id="7b1ad-112">Wenn Ihre Anwendung CLS-kompatibel sein muss, ändern Sie den Datentyp der dieses Element in den ähnlichsten CLS-kompatiblen Typ.</span><span class="sxs-lookup"><span data-stu-id="7b1ad-112">If your application needs to be CLS-compliant, change the data type of this element to the closest CLS-compliant type.</span></span> <span data-ttu-id="7b1ad-113">Anstelle von `UInteger` könnten Sie beispielsweise `Integer` verwenden, wenn Sie den Wertebereich über 2.147.483.647 nicht benötigen.</span><span class="sxs-lookup"><span data-stu-id="7b1ad-113">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="7b1ad-114">Wenn Sie den erweiterten Bereich benötigen, können Sie `UInteger` durch `Long`ersetzen.</span><span class="sxs-lookup"><span data-stu-id="7b1ad-114">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
- <span data-ttu-id="7b1ad-115">Wenn Ihre Anwendung nicht CLS-kompatibel sein muss, müssen Sie keine Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="7b1ad-115">If your application does not need to be CLS-compliant, you do not need to change anything.</span></span> <span data-ttu-id="7b1ad-116">Sie sollten jedoch beachten die Nichtkompatibilität, sein.</span><span class="sxs-lookup"><span data-stu-id="7b1ad-116">You should be aware of its noncompliance, however.</span></span>
