---
title: Rückgabetyp der Funktion &#39; &lt;Prozedurname&gt; &#39; ist nicht CLS-kompatibel.
ms.date: 07/20/2015
f1_keywords:
- bc40027
- vbc40027
helpviewer_keywords:
- BC40027
ms.assetid: 33c088c7-48e7-400c-920e-6d8967e1f3fc
ms.openlocfilehash: b7704ee63031c38f708a2243e84b880c25fcf819
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595003"
---
# <a name="return-type-of-function-39ltprocedurenamegt39-is-not-cls-compliant"></a><span data-ttu-id="4e090-102">Rückgabetyp der Funktion &#39; &lt;Prozedurname&gt; &#39; ist nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="4e090-102">Return type of function &#39;&lt;procedurename&gt;&#39; is not CLS-compliant</span></span>
<span data-ttu-id="4e090-103">Ein `Function` Prozedur RuntimeCompatibility als `<CLSCompliant(True)>` gibt jedoch einen Typ mit der Kennzeichnung `<CLSCompliant(False)>`, nicht markiert ist oder nicht geeignet ist, da es sich um einen nicht kompatiblen Typ handelt.</span><span class="sxs-lookup"><span data-stu-id="4e090-103">A `Function` procedure is marked as `<CLSCompliant(True)>` but returns a type that is marked as `<CLSCompliant(False)>`, is not marked, or does not qualify because it is a noncompliant type.</span></span>  
  
 <span data-ttu-id="4e090-104">Damit eine Prozedur mit [Sprachunabhängigkeit und sprachunabhängigen Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS) kompatibel ist, darf sie ausschließlich CLS-kompatible Typen verwenden.</span><span class="sxs-lookup"><span data-stu-id="4e090-104">For a procedure to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span> <span data-ttu-id="4e090-105">Dies gilt für die Parametertypen, den Rückgabetyp und die Typen all ihrer lokalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="4e090-105">This applies to the types of the parameters, the return type, and the types of all its local variables.</span></span>  
  
 <span data-ttu-id="4e090-106">Die folgenden Visual Basic-Datentypen sind nicht CLS-kompatibel:</span><span class="sxs-lookup"><span data-stu-id="4e090-106">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="4e090-107">SByte-Datentyp</span><span class="sxs-lookup"><span data-stu-id="4e090-107">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="4e090-108">UInteger-Datentyp</span><span class="sxs-lookup"><span data-stu-id="4e090-108">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="4e090-109">ULong-Datentyp</span><span class="sxs-lookup"><span data-stu-id="4e090-109">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="4e090-110">UShort-Datentyp</span><span class="sxs-lookup"><span data-stu-id="4e090-110">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="4e090-111">Wenn Sie das <xref:System.CLSCompliantAttribute> auf ein Programmierelement anwenden, legen Sie den `isCompliant` -Parameter des Attributs auf `True` oder `False` fest, um die Kompatibilität bzw. Nichtkompatibilität anzugeben.</span><span class="sxs-lookup"><span data-stu-id="4e090-111">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="4e090-112">Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.</span><span class="sxs-lookup"><span data-stu-id="4e090-112">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="4e090-113">Wenn Sie das <xref:System.CLSCompliantAttribute> nicht auf ein Element anwenden, wird dieses als nicht kompatibel betrachtet.</span><span class="sxs-lookup"><span data-stu-id="4e090-113">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="4e090-114">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="4e090-114">By default, this message is a warning.</span></span> <span data-ttu-id="4e090-115">Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="4e090-115">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="4e090-116">**Fehler-ID:** BC40027</span><span class="sxs-lookup"><span data-stu-id="4e090-116">**Error ID:** BC40027</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4e090-117">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="4e090-117">To correct this error</span></span>  
  
-   <span data-ttu-id="4e090-118">Wenn die `Function` -Prozedur diesen speziellen Typ zurückgeben muss, entfernen Sie die <xref:System.CLSCompliantAttribute>.</span><span class="sxs-lookup"><span data-stu-id="4e090-118">If the `Function` procedure must return this particular type, remove the <xref:System.CLSCompliantAttribute>.</span></span> <span data-ttu-id="4e090-119">Die Prozedur kann nicht CLS-kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="4e090-119">The procedure cannot be CLS-compliant.</span></span>  
  
-   <span data-ttu-id="4e090-120">Wenn die `Function` -Prozedur CLS-kompatibel sein muss, ändern Sie den Rückgabetyp in den ähnlichsten CLS-kompatiblen Typ.</span><span class="sxs-lookup"><span data-stu-id="4e090-120">If the `Function` procedure must be CLS-compliant, change the return type to the closest CLS-compliant type.</span></span> <span data-ttu-id="4e090-121">Anstelle von `UInteger` könnten Sie beispielsweise `Integer` verwenden, wenn Sie den Wertebereich über 2.147.483.647 nicht benötigen.</span><span class="sxs-lookup"><span data-stu-id="4e090-121">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="4e090-122">Wenn Sie den erweiterten Bereich benötigen, können Sie `UInteger` durch `Long`ersetzen.</span><span class="sxs-lookup"><span data-stu-id="4e090-122">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="4e090-123">Beachten Sie beim Verbinden mit Automatisierungs- oder COM-Objekten, dass einige Typen über andere Datenbreiten als im [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] verfügen.</span><span class="sxs-lookup"><span data-stu-id="4e090-123">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="4e090-124">Zum Beispiel umfasst `int` in anderen Umgebungen oft 16 Bits.</span><span class="sxs-lookup"><span data-stu-id="4e090-124">For example, `int` is often 16 bits in other environments.</span></span> <span data-ttu-id="4e090-125">Wenn Sie eine 16-Bit-Ganzzahl an eine solche Komponente zurückgeben, deklarieren Sie es als `Short` anstelle von `Integer` im verwalteten Visual Basic-Code.</span><span class="sxs-lookup"><span data-stu-id="4e090-125">If you are returning a 16-bit integer to such a component, declare it as `Short` instead of `Integer` in your managed Visual Basic code.</span></span>