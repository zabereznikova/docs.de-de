---
title: Der Typ des optionalen Werts für den optionalen <parametername>-Parameter ist nicht CLS-kompatibel.
ms.date: 07/20/2015
f1_keywords:
- BC40042
- vbc40042
helpviewer_keywords:
- BC40042
ms.assetid: 1d6eae29-4ad3-4434-bde4-a53b6051adf5
ms.openlocfilehash: e4fd7f0fd219eba7f20b62e0357d2139a21c0af7
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162686"
---
# <a name="bc40042-type-of-optional-value-for-optional-parameter-parametername-is-not-cls-compliant"></a><span data-ttu-id="8c05f-102">BC40042: der Typ des optionalen Werts für den optionalen Parameter \<parametername> ist nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="8c05f-102">BC40042: Type of optional value for optional parameter \<parametername> is not CLS-compliant</span></span>

<span data-ttu-id="8c05f-103">Eine Prozedur wird durch `<CLSCompliant(True)>` gekennzeichnet, deklariert jedoch einen [optionalen](../modifiers/optional.md) Parameter mit dem Standardwert eines nicht kompatiblen Typs.</span><span class="sxs-lookup"><span data-stu-id="8c05f-103">A procedure is marked as `<CLSCompliant(True)>` but declares an [Optional](../modifiers/optional.md) parameter with default value of a noncompliant type.</span></span>

 <span data-ttu-id="8c05f-104">Damit eine Prozedur mit [Sprachunabhängigkeit und sprachunabhängigen Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS) kompatibel ist, darf sie ausschließlich CLS-kompatible Typen verwenden.</span><span class="sxs-lookup"><span data-stu-id="8c05f-104">For a procedure to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span> <span data-ttu-id="8c05f-105">Dies gilt für die Parametertypen, den Rückgabetyp und die Typen all ihrer lokalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="8c05f-105">This applies to the types of the parameters, the return type, and the types of all its local variables.</span></span> <span data-ttu-id="8c05f-106">Dies gilt auch für die Standardwerte der optionalen Parameter.</span><span class="sxs-lookup"><span data-stu-id="8c05f-106">It also applies to the default values of optional parameters.</span></span>

 <span data-ttu-id="8c05f-107">Die folgenden Visual Basic-Datentypen sind nicht CLS-kompatibel:</span><span class="sxs-lookup"><span data-stu-id="8c05f-107">The following Visual Basic data types are not CLS-compliant:</span></span>

- [<span data-ttu-id="8c05f-108">SByte-Datentyp</span><span class="sxs-lookup"><span data-stu-id="8c05f-108">SByte Data Type</span></span>](../data-types/sbyte-data-type.md)

- [<span data-ttu-id="8c05f-109">UInteger-Datentyp</span><span class="sxs-lookup"><span data-stu-id="8c05f-109">UInteger Data Type</span></span>](../data-types/uinteger-data-type.md)

- [<span data-ttu-id="8c05f-110">ULong-Datentyp</span><span class="sxs-lookup"><span data-stu-id="8c05f-110">ULong Data Type</span></span>](../data-types/ulong-data-type.md)

- [<span data-ttu-id="8c05f-111">UShort-Datentyp</span><span class="sxs-lookup"><span data-stu-id="8c05f-111">UShort Data Type</span></span>](../data-types/ushort-data-type.md)

 <span data-ttu-id="8c05f-112">Wenn Sie das <xref:System.CLSCompliantAttribute> -Attribut auf ein Programmierelement anwenden, legen Sie den `isCompliant` -Parameter des Attributs auf `True` oder `False` fest, um die Kompatibilität bzw. Nichtkompatibilität anzugeben.</span><span class="sxs-lookup"><span data-stu-id="8c05f-112">When you apply the <xref:System.CLSCompliantAttribute> attribute to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="8c05f-113">Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.</span><span class="sxs-lookup"><span data-stu-id="8c05f-113">There is no default for this parameter, and you must supply a value.</span></span>

 <span data-ttu-id="8c05f-114">Wenn Sie <xref:System.CLSCompliantAttribute> nicht auf ein Element anwenden, wird dieses als nicht kompatibel betrachtet.</span><span class="sxs-lookup"><span data-stu-id="8c05f-114">If you do not apply <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>

 <span data-ttu-id="8c05f-115">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="8c05f-115">By default, this message is a warning.</span></span> <span data-ttu-id="8c05f-116">Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="8c05f-116">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="8c05f-117">**Fehler-ID:** BC40042</span><span class="sxs-lookup"><span data-stu-id="8c05f-117">**Error ID:** BC40042</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="8c05f-118">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="8c05f-118">To correct this error</span></span>

- <span data-ttu-id="8c05f-119">Wenn der optionale Parameter einen Standardwert dieses bestimmten Typs aufweisen muss, entfernen Sie <xref:System.CLSCompliantAttribute> .</span><span class="sxs-lookup"><span data-stu-id="8c05f-119">If the optional parameter must have a default value of this particular type, remove <xref:System.CLSCompliantAttribute>.</span></span> <span data-ttu-id="8c05f-120">Die Prozedur kann nicht CLS-kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="8c05f-120">The procedure cannot be CLS-compliant.</span></span>

- <span data-ttu-id="8c05f-121">Wenn die Prozedur CLS-kompatibel sein muss, ändern Sie den Typ des Standardwerts in den ähnlichsten CLS-kompatiblen Typ.</span><span class="sxs-lookup"><span data-stu-id="8c05f-121">If the procedure must be CLS-compliant, change the type of this default value to the closest CLS-compliant type.</span></span> <span data-ttu-id="8c05f-122">Anstelle von `UInteger` könnten Sie beispielsweise `Integer` verwenden, wenn Sie den Wertebereich über 2.147.483.647 nicht benötigen.</span><span class="sxs-lookup"><span data-stu-id="8c05f-122">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="8c05f-123">Wenn Sie den erweiterten Bereich benötigen, können Sie `UInteger` durch `Long`ersetzen.</span><span class="sxs-lookup"><span data-stu-id="8c05f-123">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>

- <span data-ttu-id="8c05f-124">Wenn Sie mit Automation-oder COM-Objekten interagieren, beachten Sie, dass einige Typen unterschiedliche Daten breiten aufweisen als in der .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8c05f-124">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the .NET Framework.</span></span> <span data-ttu-id="8c05f-125">Zum Beispiel umfasst `int` in anderen Umgebungen oft 16 Bits.</span><span class="sxs-lookup"><span data-stu-id="8c05f-125">For example, `int` is often 16 bits in other environments.</span></span> <span data-ttu-id="8c05f-126">Wenn Sie eine 16-Bit-Ganzzahl aus einer solchen Komponente akzeptieren, deklarieren Sie Sie als `Short` anstelle von `Integer` in Ihrem verwalteten Visual Basic-Code.</span><span class="sxs-lookup"><span data-stu-id="8c05f-126">If you are accepting a 16-bit integer from such a component, declare it as `Short` instead of `Integer` in your managed Visual Basic code.</span></span>
