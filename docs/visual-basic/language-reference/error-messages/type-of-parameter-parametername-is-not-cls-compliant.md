---
title: Typ des Parameters &quot;&lt;Parametername&gt;&quot; ist nicht CLS-kompatibel. | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40028
- bc40028
dev_langs:
- VB
helpviewer_keywords:
- BC40028
ms.assetid: dfa1f6f9-bb88-44ad-b85f-149144363d41
caps.latest.revision: 11
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
ms.openlocfilehash: 25392d9855b44d9f82157601648384955951475e
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="type-of-parameter-39ltparameternamegt39-is-not-cls-compliant"></a><span data-ttu-id="8287f-102">Typ des Parameters '&lt;Parametername&gt;' ist nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="8287f-102">Type of parameter &#39;&lt;parametername&gt;&#39; is not CLS-compliant</span></span>
<span data-ttu-id="8287f-103">Eine Prozedur ist als markiert `<CLSCompliant(True)>` deklariert jedoch einen Parameter mit einem Typ, die als gekennzeichnete `<CLSCompliant(False)>`, nicht markiert ist oder nicht geeignet ist, da es sich um einen nicht kompatiblen Typ handelt.</span><span class="sxs-lookup"><span data-stu-id="8287f-103">A procedure is marked as `<CLSCompliant(True)>` but declares a parameter with a type that is marked as `<CLSCompliant(False)>`, is not marked, or does not qualify because it is a noncompliant type.</span></span>  
  
 <span data-ttu-id="8287f-104">Damit eine Prozedur mit [Sprachunabhängigkeit und sprachunabhängigen Komponenten](https://msdn.microsoft.com/library/12a7a7h3) (CLS) kompatibel ist, darf sie ausschließlich CLS-kompatible Typen verwenden.</span><span class="sxs-lookup"><span data-stu-id="8287f-104">For a procedure to be compliant with the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS), it must use only CLS-compliant types.</span></span> <span data-ttu-id="8287f-105">Dies gilt für die Parametertypen, den Rückgabetyp und die Typen all ihrer lokalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="8287f-105">This applies to the types of the parameters, the return type, and the types of all its local variables.</span></span>  
  
 <span data-ttu-id="8287f-106">Die folgenden [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] -Datentypen sind nicht CLS-kompatibel:</span><span class="sxs-lookup"><span data-stu-id="8287f-106">The following [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="8287f-107">SByte-Datentyp</span><span class="sxs-lookup"><span data-stu-id="8287f-107">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="8287f-108">UInteger-Datentyp</span><span class="sxs-lookup"><span data-stu-id="8287f-108">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="8287f-109">ULong-Datentyp</span><span class="sxs-lookup"><span data-stu-id="8287f-109">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="8287f-110">UShort-Datentyp</span><span class="sxs-lookup"><span data-stu-id="8287f-110">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="8287f-111">Beim Anwenden der <xref:System.CLSCompliantAttribute>auf ein Programmierelement, legen Sie des Attributs `isCompliant` Parameter entweder `True` oder `False` an Kompatibilität oder Nichtkompatibilität.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="8287f-111">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="8287f-112">Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.</span><span class="sxs-lookup"><span data-stu-id="8287f-112">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="8287f-113">Wenn Sie nicht anwenden der <xref:System.CLSCompliantAttribute>auf ein Element gilt nicht kompatibel ist.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="8287f-113">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="8287f-114">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="8287f-114">By default, this message is a warning.</span></span> <span data-ttu-id="8287f-115">Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="8287f-115">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="8287f-116">**Fehler-ID:** BC40028</span><span class="sxs-lookup"><span data-stu-id="8287f-116">**Error ID:** BC40028</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8287f-117">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="8287f-117">To correct this error</span></span>  
  
-   <span data-ttu-id="8287f-118">Wenn die Prozedur einen Parameter dieses speziellen Typs akzeptieren muss, entfernen Sie den <xref:System.CLSCompliantAttribute>.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="8287f-118">If the procedure must take a parameter of this particular type, remove the <xref:System.CLSCompliantAttribute>.</span></span> <span data-ttu-id="8287f-119">Die Prozedur kann nicht CLS-kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="8287f-119">The procedure cannot be CLS-compliant.</span></span>  
  
-   <span data-ttu-id="8287f-120">Wenn die Prozedur CLS-kompatibel sein muss, ändern Sie den Typ dieses Parameters in den ähnlichsten CLS-kompatiblen Typ.</span><span class="sxs-lookup"><span data-stu-id="8287f-120">If the procedure must be CLS-compliant, change the type of this parameter to the closest CLS-compliant type.</span></span> <span data-ttu-id="8287f-121">Anstelle von `UInteger` könnten Sie beispielsweise `Integer` verwenden, wenn Sie den Wertebereich über 2.147.483.647 nicht benötigen.</span><span class="sxs-lookup"><span data-stu-id="8287f-121">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="8287f-122">Wenn Sie den erweiterten Bereich benötigen, können Sie `UInteger` durch `Long`ersetzen.</span><span class="sxs-lookup"><span data-stu-id="8287f-122">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="8287f-123">Beachten Sie beim Verbinden mit Automatisierungs- oder COM-Objekten, dass einige Typen über andere Datenbreiten als im [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] verfügen.</span><span class="sxs-lookup"><span data-stu-id="8287f-123">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].</span></span> <span data-ttu-id="8287f-124">Zum Beispiel umfasst `int` in anderen Umgebungen oft 16 Bits.</span><span class="sxs-lookup"><span data-stu-id="8287f-124">For example, `int` is often 16 bits in other environments.</span></span> <span data-ttu-id="8287f-125">Wenn Sie von einer solchen Komponente eine 16-Bit-Ganzzahl akzeptieren, deklarieren Sie sie im verwalteten [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]-Code als `Short` anstatt als `Integer`.</span><span class="sxs-lookup"><span data-stu-id="8287f-125">If you are accepting a 16-bit integer from such a component, declare it as `Short` instead of `Integer` in your managed [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8287f-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8287f-126">See Also</span></span>  
 [<span data-ttu-id="8287f-127">\<PAVE über > CLS-kompatiblen Code schreiben</span><span class="sxs-lookup"><span data-stu-id="8287f-127">\<PAVE OVER> Writing CLS-Compliant Code</span></span>](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
