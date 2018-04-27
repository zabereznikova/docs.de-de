---
title: Typ &lt;Typename&gt; ist nicht CLS-kompatibel.
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40041
- vbc40041
helpviewer_keywords:
- BC40041
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 73abc8b055e7eb9d1a4f6917d816cab5b4509f86
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="type-lttypenamegt-is-not-cls-compliant"></a><span data-ttu-id="1dc0a-102">Typ &lt;Typename&gt; ist nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="1dc0a-102">Type &lt;typename&gt; is not CLS-compliant</span></span>
<span data-ttu-id="1dc0a-103">Eine Variable, Eigenschaft oder Funktionsrückgabe ist mit einem Datentyp deklariert, der nicht CLS-kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="1dc0a-103">A variable, property, or function return is declared with a data type that is not CLS-compliant.</span></span>  
  
 <span data-ttu-id="1dc0a-104">Für eine Anwendung einhalten der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS), müssen sie nur CLS-kompatible Typen verwenden.</span><span class="sxs-lookup"><span data-stu-id="1dc0a-104">For an application to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span>  
  
 <span data-ttu-id="1dc0a-105">Die folgenden Visual Basic-Datentypen sind nicht CLS-kompatibel:</span><span class="sxs-lookup"><span data-stu-id="1dc0a-105">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="1dc0a-106">SByte-Datentyp</span><span class="sxs-lookup"><span data-stu-id="1dc0a-106">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="1dc0a-107">UInteger-Datentyp</span><span class="sxs-lookup"><span data-stu-id="1dc0a-107">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="1dc0a-108">ULong-Datentyp</span><span class="sxs-lookup"><span data-stu-id="1dc0a-108">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="1dc0a-109">UShort-Datentyp</span><span class="sxs-lookup"><span data-stu-id="1dc0a-109">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="1dc0a-110">**Fehler-ID:** BC40041</span><span class="sxs-lookup"><span data-stu-id="1dc0a-110">**Error ID:** BC40041</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1dc0a-111">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="1dc0a-111">To correct this error</span></span>  
  
-   <span data-ttu-id="1dc0a-112">Wenn Ihre Anwendung CLS-kompatibel sein muss, ändern Sie den Datentyp dieses Elements in den ähnlichsten CLS-kompatiblen Typ.</span><span class="sxs-lookup"><span data-stu-id="1dc0a-112">If your application needs to be CLS-compliant, change the data type of this element to the closest CLS-compliant type.</span></span> <span data-ttu-id="1dc0a-113">Anstelle von `UInteger` könnten Sie beispielsweise `Integer` verwenden, wenn Sie den Wertebereich über 2.147.483.647 nicht benötigen.</span><span class="sxs-lookup"><span data-stu-id="1dc0a-113">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="1dc0a-114">Wenn Sie den erweiterten Bereich benötigen, können Sie `UInteger` durch `Long`ersetzen.</span><span class="sxs-lookup"><span data-stu-id="1dc0a-114">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="1dc0a-115">Wenn Ihre Anwendung nicht CLS-kompatibel sein muss, müssen Sie nicht ändert nichts.</span><span class="sxs-lookup"><span data-stu-id="1dc0a-115">If your application does not need to be CLS-compliant, you do not need to change anything.</span></span> <span data-ttu-id="1dc0a-116">Sie sollten jedoch seine Nichtkompatibilität bewusst sein.</span><span class="sxs-lookup"><span data-stu-id="1dc0a-116">You should be aware of its noncompliance, however.</span></span>