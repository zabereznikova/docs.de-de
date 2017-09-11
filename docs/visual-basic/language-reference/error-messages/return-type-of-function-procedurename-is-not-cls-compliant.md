---
title: "Der Rückgabetyp der Funktion &quot;&lt;Prozedurname&gt;&quot; ist nicht CLS-kompatibel. | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40027
- vbc40027
dev_langs:
- VB
helpviewer_keywords:
- BC40027
ms.assetid: 33c088c7-48e7-400c-920e-6d8967e1f3fc
caps.latest.revision: 13
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
ms.openlocfilehash: 949104d77996cb7678bb9841cd1cd1e9b7f71b56
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="return-type-of-function-39ltprocedurenamegt39-is-not-cls-compliant"></a><span data-ttu-id="763cc-102">Der Rückgabetyp der Funktion "&lt;Prozedurname&gt;' ist nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="763cc-102">Return type of function &#39;&lt;procedurename&gt;&#39; is not CLS-compliant</span></span>
<span data-ttu-id="763cc-103">Ein `Function` Prozedur gekennzeichnet ist, als `<CLSCompliant(True)>` gibt jedoch einen Typ, die als gekennzeichnete `<CLSCompliant(False)>`, nicht markiert ist oder nicht geeignet ist, da es sich um einen nicht kompatiblen Typ handelt.</span><span class="sxs-lookup"><span data-stu-id="763cc-103">A `Function` procedure is marked as `<CLSCompliant(True)>` but returns a type that is marked as `<CLSCompliant(False)>`, is not marked, or does not qualify because it is a noncompliant type.</span></span>  
  
 <span data-ttu-id="763cc-104">Damit eine Prozedur mit [Sprachunabhängigkeit und sprachunabhängigen Komponenten](https://msdn.microsoft.com/library/12a7a7h3) (CLS) kompatibel ist, darf sie ausschließlich CLS-kompatible Typen verwenden.</span><span class="sxs-lookup"><span data-stu-id="763cc-104">For a procedure to be compliant with the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS), it must use only CLS-compliant types.</span></span> <span data-ttu-id="763cc-105">Dies gilt für die Parametertypen, den Rückgabetyp und die Typen all ihrer lokalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="763cc-105">This applies to the types of the parameters, the return type, and the types of all its local variables.</span></span>  
  
 <span data-ttu-id="763cc-106">Die folgenden [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] -Datentypen sind nicht CLS-kompatibel:</span><span class="sxs-lookup"><span data-stu-id="763cc-106">The following [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="763cc-107">SByte-Datentyp</span><span class="sxs-lookup"><span data-stu-id="763cc-107">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="763cc-108">UInteger-Datentyp</span><span class="sxs-lookup"><span data-stu-id="763cc-108">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="763cc-109">ULong-Datentyp</span><span class="sxs-lookup"><span data-stu-id="763cc-109">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="763cc-110">UShort-Datentyp</span><span class="sxs-lookup"><span data-stu-id="763cc-110">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="763cc-111">Beim Anwenden der <xref:System.CLSCompliantAttribute>auf ein Programmierelement, legen Sie des Attributs `isCompliant` Parameter entweder `True` oder `False` an Kompatibilität oder Nichtkompatibilität.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="763cc-111">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="763cc-112">Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.</span><span class="sxs-lookup"><span data-stu-id="763cc-112">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="763cc-113">Wenn Sie nicht anwenden der <xref:System.CLSCompliantAttribute>auf ein Element gilt nicht kompatibel ist.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="763cc-113">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="763cc-114">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="763cc-114">By default, this message is a warning.</span></span> <span data-ttu-id="763cc-115">Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="763cc-115">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="763cc-116">**Fehler-ID:** BC40027</span><span class="sxs-lookup"><span data-stu-id="763cc-116">**Error ID:** BC40027</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="763cc-117">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="763cc-117">To correct this error</span></span>  
  
-   <span data-ttu-id="763cc-118">Wenn die `Function` -Prozedur diesen speziellen Typ zurückgeben muss, entfernen Sie den <xref:System.CLSCompliantAttribute>.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="763cc-118">If the `Function` procedure must return this particular type, remove the <xref:System.CLSCompliantAttribute>.</span></span> <span data-ttu-id="763cc-119">Die Prozedur kann nicht CLS-kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="763cc-119">The procedure cannot be CLS-compliant.</span></span>  
  
-   <span data-ttu-id="763cc-120">Wenn die `Function` -Prozedur CLS-kompatibel sein muss, ändern Sie den Rückgabetyp in den ähnlichsten CLS-kompatiblen Typ.</span><span class="sxs-lookup"><span data-stu-id="763cc-120">If the `Function` procedure must be CLS-compliant, change the return type to the closest CLS-compliant type.</span></span> <span data-ttu-id="763cc-121">Anstelle von `UInteger` könnten Sie beispielsweise `Integer` verwenden, wenn Sie den Wertebereich über 2.147.483.647 nicht benötigen.</span><span class="sxs-lookup"><span data-stu-id="763cc-121">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="763cc-122">Wenn Sie den erweiterten Bereich benötigen, können Sie `UInteger` durch `Long`ersetzen.</span><span class="sxs-lookup"><span data-stu-id="763cc-122">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="763cc-123">Beachten Sie beim Verbinden mit Automatisierungs- oder COM-Objekten, dass einige Typen über andere Datenbreiten als im [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] verfügen.</span><span class="sxs-lookup"><span data-stu-id="763cc-123">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].</span></span> <span data-ttu-id="763cc-124">Zum Beispiel umfasst `int` in anderen Umgebungen oft 16 Bits.</span><span class="sxs-lookup"><span data-stu-id="763cc-124">For example, `int` is often 16 bits in other environments.</span></span> <span data-ttu-id="763cc-125">Wenn Sie an eine solche Komponente eine 16-Bit-Ganzzahl zurückgeben, deklarieren Sie es als `Short` anstelle von `Integer` im verwalteten [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Code.</span><span class="sxs-lookup"><span data-stu-id="763cc-125">If you are returning a 16-bit integer to such a component, declare it as `Short` instead of `Integer` in your managed [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="763cc-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="763cc-126">See Also</span></span>  
 [<span data-ttu-id="763cc-127">\<PAVE über > CLS-kompatiblen Code schreiben</span><span class="sxs-lookup"><span data-stu-id="763cc-127">\<PAVE OVER> Writing CLS-Compliant Code</span></span>](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
