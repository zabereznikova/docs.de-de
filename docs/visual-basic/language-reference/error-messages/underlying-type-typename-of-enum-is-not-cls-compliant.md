---
title: Der zugrunde liegende Typ &lt;Typename&gt; der Enumeration ist nicht CLS-kompatibel. | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40032
- bc40032
dev_langs:
- VB
helpviewer_keywords:
- BC40032
ms.assetid: 32bf1949-fd73-456c-a323-bf1ffe1320ed
caps.latest.revision: 8
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
ms.openlocfilehash: 51628d2232b9e1c89e7fbf931ef0d6602f7cddc9
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="underlying-type-lttypenamegt-of-enum-is-not-cls-compliant"></a><span data-ttu-id="e9c2e-102">Der zugrunde liegende Typ &lt;Typename&gt; der Enumeration ist nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="e9c2e-102">Underlying type &lt;typename&gt; of Enum is not CLS-compliant</span></span>
<span data-ttu-id="e9c2e-103">Der Datentyp angegeben werden, für die diese Enumeration ist nicht Teil der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](https://msdn.microsoft.com/library/12a7a7h3) (CLS).</span><span class="sxs-lookup"><span data-stu-id="e9c2e-103">The data type specified for this enumeration is not part of the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS).</span></span> <span data-ttu-id="e9c2e-104">Dies ist kein Fehler in der Komponente, da die [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] und [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] diesen Datentyp unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e9c2e-104">This is not an error within your component, because the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] and [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] support this data type.</span></span> <span data-ttu-id="e9c2e-105">Allerdings kann eine andere Komponente in streng CLS-kompatiblen Code geschrieben diesen Datentyp nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e9c2e-105">However, another component written in strictly CLS-compliant code might not support this data type.</span></span> <span data-ttu-id="e9c2e-106">Eine solche Komponente kann möglicherweise nicht erfolgreich mit Ihrer Komponente interagieren.</span><span class="sxs-lookup"><span data-stu-id="e9c2e-106">Such a component might not be able to interact successfully with your component.</span></span>  
  
 <span data-ttu-id="e9c2e-107">Die folgenden [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] -Datentypen sind nicht CLS-kompatibel:</span><span class="sxs-lookup"><span data-stu-id="e9c2e-107">The following [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="e9c2e-108">SByte-Datentyp</span><span class="sxs-lookup"><span data-stu-id="e9c2e-108">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="e9c2e-109">UInteger-Datentyp</span><span class="sxs-lookup"><span data-stu-id="e9c2e-109">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="e9c2e-110">ULong-Datentyp</span><span class="sxs-lookup"><span data-stu-id="e9c2e-110">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="e9c2e-111">UShort-Datentyp</span><span class="sxs-lookup"><span data-stu-id="e9c2e-111">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="e9c2e-112">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="e9c2e-112">By default, this message is a warning.</span></span> <span data-ttu-id="e9c2e-113">Weitere Informationen zu Ausblenden von Warnungen oder Warnungen als Fehler behandeln, finden Sie unter [Konfigurieren von Warnungen in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="e9c2e-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="e9c2e-114">**Fehler-ID:** BC40032</span><span class="sxs-lookup"><span data-stu-id="e9c2e-114">**Error ID:** BC40032</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e9c2e-115">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="e9c2e-115">To correct this error</span></span>  
  
-   <span data-ttu-id="e9c2e-116">Wenn die Komponente nur mit anderen Schnittstellen [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] Komponenten oder mit anderen Komponenten verbunden, müssen Sie nichts ändern.</span><span class="sxs-lookup"><span data-stu-id="e9c2e-116">If your component interfaces only with other [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] components, or does not interface with any other components, you do not need to change anything.</span></span>  
  
-   <span data-ttu-id="e9c2e-117">Wenn Sie mit einer Komponente, die nicht für geschriebenen anbinden der [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)], um zu bestimmen, über Reflektion können Sie möglicherweise oder anhand der Dokumentation, ob sie diesen Datentyp unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e9c2e-117">If you are interfacing with a component not written for the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)], you might be able to determine, either through reflection or from documentation, whether it supports this data type.</span></span> <span data-ttu-id="e9c2e-118">Ist dies der Fall ist, brauchen Sie nichts ändern.</span><span class="sxs-lookup"><span data-stu-id="e9c2e-118">If it does, you do not need to change anything.</span></span>  
  
-   <span data-ttu-id="e9c2e-119">Wenn Sie mit einer Komponente verbunden ist, die diesen Datentyp nicht unterstützt, müssen Sie ihn durch den ähnlichsten CLS-kompatiblen Typ ersetzen.</span><span class="sxs-lookup"><span data-stu-id="e9c2e-119">If you are interfacing with a component that does not support this data type, you must replace it with the closest CLS-compliant type.</span></span> <span data-ttu-id="e9c2e-120">Anstelle von `UInteger` könnten Sie beispielsweise `Integer` verwenden, wenn Sie den Wertebereich über 2.147.483.647 nicht benötigen.</span><span class="sxs-lookup"><span data-stu-id="e9c2e-120">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="e9c2e-121">Wenn Sie den erweiterten Bereich benötigen, können Sie `UInteger` durch `Long`ersetzen.</span><span class="sxs-lookup"><span data-stu-id="e9c2e-121">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="e9c2e-122">Beachten Sie beim Verbinden mit Automatisierungs- oder COM-Objekten, dass einige Typen über andere Datenbreiten als im [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] verfügen.</span><span class="sxs-lookup"><span data-stu-id="e9c2e-122">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].</span></span> <span data-ttu-id="e9c2e-123">Zum Beispiel umfasst `uint` in anderen Umgebungen oft 16 Bits.</span><span class="sxs-lookup"><span data-stu-id="e9c2e-123">For example, `uint` is often 16 bits in other environments.</span></span> <span data-ttu-id="e9c2e-124">Wenn Sie ein 16-Bit-Argument an eine solche Komponente übergeben, deklarieren Sie es als `UShort` anstelle von `UInteger` im verwalteten [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Code.</span><span class="sxs-lookup"><span data-stu-id="e9c2e-124">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9c2e-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9c2e-125">See Also</span></span>  
 <span data-ttu-id="e9c2e-126">[Reflektion](http://msdn.microsoft.com/library/5d1d1bcf-08de-4d0b-97a8-912d17c00f26) </span><span class="sxs-lookup"><span data-stu-id="e9c2e-126">[Reflection](http://msdn.microsoft.com/library/5d1d1bcf-08de-4d0b-97a8-912d17c00f26) </span></span>  
<span data-ttu-id="e9c2e-127"> [Reflektion](http://msdn.microsoft.com/library/d1a58e7f-fb39-4d50-bf84-e3b8f9bf9775) </span><span class="sxs-lookup"><span data-stu-id="e9c2e-127"> [Reflection](http://msdn.microsoft.com/library/d1a58e7f-fb39-4d50-bf84-e3b8f9bf9775) </span></span>  
<span data-ttu-id="e9c2e-128"> [\<PAVE über > CLS-kompatiblen Code schreiben](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)</span><span class="sxs-lookup"><span data-stu-id="e9c2e-128"> [\<PAVE OVER> Writing CLS-Compliant Code](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)</span></span>
