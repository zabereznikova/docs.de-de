---
title: Der Typ des Members "<membername>" ist nicht CLS-kompatibel.
ms.date: 07/20/2015
f1_keywords:
- bc40025
- vbc40025
helpviewer_keywords:
- BC40025
ms.assetid: adbd34bb-43d2-4266-90e7-cd1afaf49b4e
ms.openlocfilehash: 12155062f04b7619cae581540abfc4ce1a8ae34f
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875133"
---
# <a name="type-of-member-membername-is-not-cls-compliant"></a><span data-ttu-id="38c25-102">Der Typ des Members "\<membername>" ist nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="38c25-102">Type of member '\<membername>' is not CLS-compliant</span></span>

<span data-ttu-id="38c25-103">Der für diesen Member angegebene Datentyp ist nicht Teil der [Sprachunabhängigkeit und sprachunabhängigen Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span><span class="sxs-lookup"><span data-stu-id="38c25-103">The data type specified for this member is not part of the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span> <span data-ttu-id="38c25-104">Dies ist kein Fehler in der Komponente, da der .NET Framework und Visual Basic diesen Datentyp unterstützen.</span><span class="sxs-lookup"><span data-stu-id="38c25-104">This is not an error within your component, because the .NET Framework and Visual Basic support this data type.</span></span> <span data-ttu-id="38c25-105">Eine andere Komponente, die in streng CLS-kompatibler Code geschrieben wird, unterstützt diesen Datentyp jedoch möglicherweise nicht.</span><span class="sxs-lookup"><span data-stu-id="38c25-105">However, another component written in strictly CLS-compliant code might not support this data type.</span></span> <span data-ttu-id="38c25-106">Eine solche Komponente ist möglicherweise nicht in der Lage, mit Ihrer Komponente erfolgreich zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="38c25-106">Such a component might not be able to interact successfully with your component.</span></span>  
  
 <span data-ttu-id="38c25-107">Die folgenden Visual Basic-Datentypen sind nicht CLS-kompatibel:</span><span class="sxs-lookup"><span data-stu-id="38c25-107">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
- [<span data-ttu-id="38c25-108">SByte-Datentyp</span><span class="sxs-lookup"><span data-stu-id="38c25-108">SByte Data Type</span></span>](../data-types/sbyte-data-type.md)  
  
- [<span data-ttu-id="38c25-109">UInteger-Datentyp</span><span class="sxs-lookup"><span data-stu-id="38c25-109">UInteger Data Type</span></span>](../data-types/uinteger-data-type.md)  
  
- [<span data-ttu-id="38c25-110">ULong-Datentyp</span><span class="sxs-lookup"><span data-stu-id="38c25-110">ULong Data Type</span></span>](../data-types/ulong-data-type.md)  
  
- [<span data-ttu-id="38c25-111">UShort-Datentyp</span><span class="sxs-lookup"><span data-stu-id="38c25-111">UShort Data Type</span></span>](../data-types/ushort-data-type.md)  
  
 <span data-ttu-id="38c25-112">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="38c25-112">By default, this message is a warning.</span></span> <span data-ttu-id="38c25-113">Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="38c25-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="38c25-114">**Fehler-ID:** BC40025</span><span class="sxs-lookup"><span data-stu-id="38c25-114">**Error ID:** BC40025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="38c25-115">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="38c25-115">To correct this error</span></span>  
  
- <span data-ttu-id="38c25-116">Wenn sich die Komponente nur mit anderen .NET Framework Komponenten oder nicht mit anderen Komponenten verbinden lässt, müssen Sie nichts ändern.</span><span class="sxs-lookup"><span data-stu-id="38c25-116">If your component interfaces only with other .NET Framework components, or does not interface with any other components, you do not need to change anything.</span></span>  
  
- <span data-ttu-id="38c25-117">Wenn Sie mit einer Komponente verbunden sind, die nicht für die .NET Framework geschrieben wurde, können Sie möglicherweise entweder durch Reflektion oder aus der Dokumentation ermitteln, ob dieser Datentyp unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="38c25-117">If you are interfacing with a component not written for the .NET Framework, you might be able to determine, either through reflection or from documentation, whether it supports this data type.</span></span> <span data-ttu-id="38c25-118">Wenn dies der Fall ist, müssen Sie nichts ändern.</span><span class="sxs-lookup"><span data-stu-id="38c25-118">If it does, you do not need to change anything.</span></span>  
  
- <span data-ttu-id="38c25-119">Wenn Sie mit einer Komponente interagieren, die diesen Datentyp nicht unterstützt, müssen Sie Sie durch den nächstgelegenen CLS-kompatiblen Typ ersetzen.</span><span class="sxs-lookup"><span data-stu-id="38c25-119">If you are interfacing with a component that does not support this data type, you must replace it with the closest CLS-compliant type.</span></span> <span data-ttu-id="38c25-120">Anstelle von `UInteger` könnten Sie beispielsweise `Integer` verwenden, wenn Sie den Wertebereich über 2.147.483.647 nicht benötigen.</span><span class="sxs-lookup"><span data-stu-id="38c25-120">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="38c25-121">Wenn Sie den erweiterten Bereich benötigen, können Sie `UInteger` durch `Long`ersetzen.</span><span class="sxs-lookup"><span data-stu-id="38c25-121">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
- <span data-ttu-id="38c25-122">Wenn Sie mit Automation-oder COM-Objekten interagieren, beachten Sie, dass einige Typen unterschiedliche Daten breiten aufweisen als in der .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="38c25-122">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the .NET Framework.</span></span> <span data-ttu-id="38c25-123">Zum Beispiel umfasst `uint` in anderen Umgebungen oft 16 Bits.</span><span class="sxs-lookup"><span data-stu-id="38c25-123">For example, `uint` is often 16 bits in other environments.</span></span> <span data-ttu-id="38c25-124">Wenn Sie ein 16-Bit-Argument an eine solche Komponente übergeben, deklarieren Sie es als `UShort` anstelle von `UInteger` in Ihrem verwalteten Visual Basic-Code.</span><span class="sxs-lookup"><span data-stu-id="38c25-124">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed Visual Basic code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38c25-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="38c25-125">See also</span></span>

- [<span data-ttu-id="38c25-126">Reflexion</span><span class="sxs-lookup"><span data-stu-id="38c25-126">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)
