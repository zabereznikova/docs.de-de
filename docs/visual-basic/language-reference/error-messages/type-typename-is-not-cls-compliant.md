---
title: Typ &lt;Typename&gt; ist nicht CLS-kompatibel. | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40041
- vbc40041
dev_langs:
- VB
helpviewer_keywords:
- BC40041
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: a8d65568e862c941d5b927582833dff803219bf9
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="type-lttypenamegt-is-not-cls-compliant"></a><span data-ttu-id="9f0dc-102">Typ &lt;Typename&gt; ist nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="9f0dc-102">Type &lt;typename&gt; is not CLS-compliant</span></span>
<span data-ttu-id="9f0dc-103">Eine Variable, eine Eigenschaft oder eine Funktionsrückgabe ist mit einem Datentyp deklariert, die nicht CLS-kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="9f0dc-103">A variable, property, or function return is declared with a data type that is not CLS-compliant.</span></span>  
  
 <span data-ttu-id="9f0dc-104">Für eine Anwendung kompatibel mit der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](https://msdn.microsoft.com/library/12a7a7h3) (CLS), müssen sie nur CLS-kompatible Typen verwenden.</span><span class="sxs-lookup"><span data-stu-id="9f0dc-104">For an application to be compliant with the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS), it must use only CLS-compliant types.</span></span>  
  
 <span data-ttu-id="9f0dc-105">Die folgenden [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] -Datentypen sind nicht CLS-kompatibel:</span><span class="sxs-lookup"><span data-stu-id="9f0dc-105">The following [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="9f0dc-106">SByte-Datentyp</span><span class="sxs-lookup"><span data-stu-id="9f0dc-106">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="9f0dc-107">UInteger-Datentyp</span><span class="sxs-lookup"><span data-stu-id="9f0dc-107">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="9f0dc-108">ULong-Datentyp</span><span class="sxs-lookup"><span data-stu-id="9f0dc-108">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="9f0dc-109">UShort-Datentyp</span><span class="sxs-lookup"><span data-stu-id="9f0dc-109">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="9f0dc-110">**Fehler-ID:** BC40041</span><span class="sxs-lookup"><span data-stu-id="9f0dc-110">**Error ID:** BC40041</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9f0dc-111">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="9f0dc-111">To correct this error</span></span>  
  
-   <span data-ttu-id="9f0dc-112">Wenn die Anwendung CLS-kompatibel sein muss, ändern Sie den Datentyp dieses Elements in den ähnlichsten CLS-kompatiblen Typ.</span><span class="sxs-lookup"><span data-stu-id="9f0dc-112">If your application needs to be CLS-compliant, change the data type of this element to the closest CLS-compliant type.</span></span> <span data-ttu-id="9f0dc-113">Anstelle von `UInteger` könnten Sie beispielsweise `Integer` verwenden, wenn Sie den Wertebereich über 2.147.483.647 nicht benötigen.</span><span class="sxs-lookup"><span data-stu-id="9f0dc-113">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="9f0dc-114">Wenn Sie den erweiterten Bereich benötigen, können Sie `UInteger` durch `Long`ersetzen.</span><span class="sxs-lookup"><span data-stu-id="9f0dc-114">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="9f0dc-115">Wenn die Anwendung nicht CLS-kompatibel sein muss, brauchen Sie nichts ändern.</span><span class="sxs-lookup"><span data-stu-id="9f0dc-115">If your application does not need to be CLS-compliant, you do not need to change anything.</span></span> <span data-ttu-id="9f0dc-116">Sie sollten jedoch beachten Sie die Nichtkonformität sein.</span><span class="sxs-lookup"><span data-stu-id="9f0dc-116">You should be aware of its noncompliance, however.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f0dc-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f0dc-117">See Also</span></span>  
 [<span data-ttu-id="9f0dc-118">\<PAVE über > CLS-kompatiblen Code schreiben</span><span class="sxs-lookup"><span data-stu-id="9f0dc-118">\<PAVE OVER> Writing CLS-Compliant Code</span></span>](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
