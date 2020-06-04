---
title: Der Typ des <parametername>-Parameters ist nicht CLS-kompatibel.
ms.date: 07/20/2015
f1_keywords:
- vbc40028
- bc40028
helpviewer_keywords:
- BC40028
ms.assetid: dfa1f6f9-bb88-44ad-b85f-149144363d41
ms.openlocfilehash: edbcadf271c4ccafc11e5b64eb103a0290976179
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413013"
---
# <a name="type-of-parameter-parametername-is-not-cls-compliant"></a><span data-ttu-id="3adef-102">Der Typ des \<parametername>-Parameters ist nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="3adef-102">Type of parameter '\<parametername>' is not CLS-compliant</span></span>
<span data-ttu-id="3adef-103">Eine Prozedur ist als gekennzeichnet, `<CLSCompliant(True)>` deklariert jedoch einen Parameter mit einem Typ, der als markiert ist `<CLSCompliant(False)>` , nicht markiert ist oder nicht qualifiziert ist, weil es sich um einen nicht kompatiblen Typ handelt.</span><span class="sxs-lookup"><span data-stu-id="3adef-103">A procedure is marked as `<CLSCompliant(True)>` but declares a parameter with a type that is marked as `<CLSCompliant(False)>`, is not marked, or does not qualify because it is a noncompliant type.</span></span>  
  
 <span data-ttu-id="3adef-104">Damit eine Prozedur mit [Sprachunabhängigkeit und sprachunabhängigen Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS) kompatibel ist, darf sie ausschließlich CLS-kompatible Typen verwenden.</span><span class="sxs-lookup"><span data-stu-id="3adef-104">For a procedure to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span> <span data-ttu-id="3adef-105">Dies gilt für die Parametertypen, den Rückgabetyp und die Typen all ihrer lokalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="3adef-105">This applies to the types of the parameters, the return type, and the types of all its local variables.</span></span>  
  
 <span data-ttu-id="3adef-106">Die folgenden Visual Basic-Datentypen sind nicht CLS-kompatibel:</span><span class="sxs-lookup"><span data-stu-id="3adef-106">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
- [<span data-ttu-id="3adef-107">SByte-Datentyp</span><span class="sxs-lookup"><span data-stu-id="3adef-107">SByte Data Type</span></span>](../data-types/sbyte-data-type.md)  
  
- [<span data-ttu-id="3adef-108">UInteger-Datentyp</span><span class="sxs-lookup"><span data-stu-id="3adef-108">UInteger Data Type</span></span>](../data-types/uinteger-data-type.md)  
  
- [<span data-ttu-id="3adef-109">ULong-Datentyp</span><span class="sxs-lookup"><span data-stu-id="3adef-109">ULong Data Type</span></span>](../data-types/ulong-data-type.md)  
  
- [<span data-ttu-id="3adef-110">UShort-Datentyp</span><span class="sxs-lookup"><span data-stu-id="3adef-110">UShort Data Type</span></span>](../data-types/ushort-data-type.md)  
  
 <span data-ttu-id="3adef-111">Wenn Sie das <xref:System.CLSCompliantAttribute> auf ein Programmierelement anwenden, legen Sie den `isCompliant` -Parameter des Attributs auf `True` oder `False` fest, um die Kompatibilität bzw. Nichtkompatibilität anzugeben.</span><span class="sxs-lookup"><span data-stu-id="3adef-111">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="3adef-112">Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.</span><span class="sxs-lookup"><span data-stu-id="3adef-112">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="3adef-113">Wenn Sie das <xref:System.CLSCompliantAttribute> nicht auf ein Element anwenden, wird dieses als nicht kompatibel betrachtet.</span><span class="sxs-lookup"><span data-stu-id="3adef-113">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="3adef-114">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="3adef-114">By default, this message is a warning.</span></span> <span data-ttu-id="3adef-115">Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="3adef-115">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="3adef-116">**Fehler-ID:** BC40028</span><span class="sxs-lookup"><span data-stu-id="3adef-116">**Error ID:** BC40028</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3adef-117">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="3adef-117">To correct this error</span></span>  
  
- <span data-ttu-id="3adef-118">Wenn die Prozedur einen Parameter dieses bestimmten Typs annehmen muss, entfernen Sie den <xref:System.CLSCompliantAttribute> .</span><span class="sxs-lookup"><span data-stu-id="3adef-118">If the procedure must take a parameter of this particular type, remove the <xref:System.CLSCompliantAttribute>.</span></span> <span data-ttu-id="3adef-119">Die Prozedur kann nicht CLS-kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="3adef-119">The procedure cannot be CLS-compliant.</span></span>  
  
- <span data-ttu-id="3adef-120">Wenn die Prozedur CLS-kompatibel sein muss, ändern Sie den Typ dieses Parameters in den nächstgelegenen CLS-kompatiblen Typ.</span><span class="sxs-lookup"><span data-stu-id="3adef-120">If the procedure must be CLS-compliant, change the type of this parameter to the closest CLS-compliant type.</span></span> <span data-ttu-id="3adef-121">Anstelle von `UInteger` könnten Sie beispielsweise `Integer` verwenden, wenn Sie den Wertebereich über 2.147.483.647 nicht benötigen.</span><span class="sxs-lookup"><span data-stu-id="3adef-121">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="3adef-122">Wenn Sie den erweiterten Bereich benötigen, können Sie `UInteger` durch `Long`ersetzen.</span><span class="sxs-lookup"><span data-stu-id="3adef-122">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
- <span data-ttu-id="3adef-123">Wenn Sie mit Automation-oder COM-Objekten interagieren, beachten Sie, dass einige Typen unterschiedliche Daten breiten aufweisen als in der .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3adef-123">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the .NET Framework.</span></span> <span data-ttu-id="3adef-124">Zum Beispiel umfasst `int` in anderen Umgebungen oft 16 Bits.</span><span class="sxs-lookup"><span data-stu-id="3adef-124">For example, `int` is often 16 bits in other environments.</span></span> <span data-ttu-id="3adef-125">Wenn Sie eine 16-Bit-Ganzzahl aus einer solchen Komponente akzeptieren, deklarieren Sie Sie als `Short` anstelle von `Integer` in Ihrem verwalteten Visual Basic-Code.</span><span class="sxs-lookup"><span data-stu-id="3adef-125">If you are accepting a 16-bit integer from such a component, declare it as `Short` instead of `Integer` in your managed Visual Basic code.</span></span>
