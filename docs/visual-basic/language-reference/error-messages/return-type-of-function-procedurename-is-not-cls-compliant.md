---
title: Der Rückgabetyp der <procedurename>-Funktion ist nicht CLS-kompatibel.
ms.date: 07/20/2015
f1_keywords:
- bc40027
- vbc40027
helpviewer_keywords:
- BC40027
ms.assetid: 33c088c7-48e7-400c-920e-6d8967e1f3fc
ms.openlocfilehash: 9a877046a1b30e2e3773a41b8b44573e11ff1c96
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159702"
---
# <a name="bc40027-return-type-of-function-procedurename-is-not-cls-compliant"></a><span data-ttu-id="4c4c9-102">BC40027: der Rückgabetyp der Funktion "" \<procedurename> ist nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="4c4c9-102">BC40027: Return type of function '\<procedurename>' is not CLS-compliant</span></span>

<span data-ttu-id="4c4c9-103">Eine `Function` Prozedur ist als gekennzeichnet, `<CLSCompliant(True)>` gibt jedoch einen Typ zurück, der als markiert ist `<CLSCompliant(False)>` , nicht markiert ist oder nicht qualifiziert ist, weil es sich um einen nicht kompatiblen Typ handelt.</span><span class="sxs-lookup"><span data-stu-id="4c4c9-103">A `Function` procedure is marked as `<CLSCompliant(True)>` but returns a type that is marked as `<CLSCompliant(False)>`, is not marked, or does not qualify because it is a noncompliant type.</span></span>

 <span data-ttu-id="4c4c9-104">Damit eine Prozedur mit [Sprachunabhängigkeit und sprachunabhängigen Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS) kompatibel ist, darf sie ausschließlich CLS-kompatible Typen verwenden.</span><span class="sxs-lookup"><span data-stu-id="4c4c9-104">For a procedure to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span> <span data-ttu-id="4c4c9-105">Dies gilt für die Parametertypen, den Rückgabetyp und die Typen all ihrer lokalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="4c4c9-105">This applies to the types of the parameters, the return type, and the types of all its local variables.</span></span>

 <span data-ttu-id="4c4c9-106">Die folgenden Visual Basic-Datentypen sind nicht CLS-kompatibel:</span><span class="sxs-lookup"><span data-stu-id="4c4c9-106">The following Visual Basic data types are not CLS-compliant:</span></span>

- [<span data-ttu-id="4c4c9-107">SByte-Datentyp</span><span class="sxs-lookup"><span data-stu-id="4c4c9-107">SByte Data Type</span></span>](../data-types/sbyte-data-type.md)

- [<span data-ttu-id="4c4c9-108">UInteger-Datentyp</span><span class="sxs-lookup"><span data-stu-id="4c4c9-108">UInteger Data Type</span></span>](../data-types/uinteger-data-type.md)

- [<span data-ttu-id="4c4c9-109">ULong-Datentyp</span><span class="sxs-lookup"><span data-stu-id="4c4c9-109">ULong Data Type</span></span>](../data-types/ulong-data-type.md)

- [<span data-ttu-id="4c4c9-110">UShort-Datentyp</span><span class="sxs-lookup"><span data-stu-id="4c4c9-110">UShort Data Type</span></span>](../data-types/ushort-data-type.md)

 <span data-ttu-id="4c4c9-111">Wenn Sie das <xref:System.CLSCompliantAttribute> auf ein Programmierelement anwenden, legen Sie den `isCompliant` -Parameter des Attributs auf `True` oder `False` fest, um die Kompatibilität bzw. Nichtkompatibilität anzugeben.</span><span class="sxs-lookup"><span data-stu-id="4c4c9-111">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="4c4c9-112">Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.</span><span class="sxs-lookup"><span data-stu-id="4c4c9-112">There is no default for this parameter, and you must supply a value.</span></span>

 <span data-ttu-id="4c4c9-113">Wenn Sie das <xref:System.CLSCompliantAttribute> nicht auf ein Element anwenden, wird dieses als nicht kompatibel betrachtet.</span><span class="sxs-lookup"><span data-stu-id="4c4c9-113">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>

 <span data-ttu-id="4c4c9-114">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="4c4c9-114">By default, this message is a warning.</span></span> <span data-ttu-id="4c4c9-115">Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="4c4c9-115">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="4c4c9-116">**Fehler-ID:** BC40027</span><span class="sxs-lookup"><span data-stu-id="4c4c9-116">**Error ID:** BC40027</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="4c4c9-117">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="4c4c9-117">To correct this error</span></span>

- <span data-ttu-id="4c4c9-118">Wenn die `Function` Prozedur diesen bestimmten Typ zurückgeben muss, entfernen Sie den <xref:System.CLSCompliantAttribute> .</span><span class="sxs-lookup"><span data-stu-id="4c4c9-118">If the `Function` procedure must return this particular type, remove the <xref:System.CLSCompliantAttribute>.</span></span> <span data-ttu-id="4c4c9-119">Die Prozedur kann nicht CLS-kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="4c4c9-119">The procedure cannot be CLS-compliant.</span></span>

- <span data-ttu-id="4c4c9-120">Wenn die `Function` Prozedur CLS-kompatibel sein muss, ändern Sie den Rückgabetyp in den nächstgelegenen CLS-kompatiblen Typ.</span><span class="sxs-lookup"><span data-stu-id="4c4c9-120">If the `Function` procedure must be CLS-compliant, change the return type to the closest CLS-compliant type.</span></span> <span data-ttu-id="4c4c9-121">Anstelle von `UInteger` könnten Sie beispielsweise `Integer` verwenden, wenn Sie den Wertebereich über 2.147.483.647 nicht benötigen.</span><span class="sxs-lookup"><span data-stu-id="4c4c9-121">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="4c4c9-122">Wenn Sie den erweiterten Bereich benötigen, können Sie `UInteger` durch `Long`ersetzen.</span><span class="sxs-lookup"><span data-stu-id="4c4c9-122">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>

- <span data-ttu-id="4c4c9-123">Wenn Sie mit Automation-oder COM-Objekten interagieren, beachten Sie, dass einige Typen unterschiedliche Daten breiten aufweisen als in der .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4c4c9-123">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the .NET Framework.</span></span> <span data-ttu-id="4c4c9-124">Zum Beispiel umfasst `int` in anderen Umgebungen oft 16 Bits.</span><span class="sxs-lookup"><span data-stu-id="4c4c9-124">For example, `int` is often 16 bits in other environments.</span></span> <span data-ttu-id="4c4c9-125">Wenn Sie eine 16-Bit-Ganzzahl an eine solche Komponente zurückgeben, deklarieren Sie Sie als `Short` anstelle von `Integer` in Ihrem verwalteten Visual Basic-Code.</span><span class="sxs-lookup"><span data-stu-id="4c4c9-125">If you are returning a 16-bit integer to such a component, declare it as `Short` instead of `Integer` in your managed Visual Basic code.</span></span>
