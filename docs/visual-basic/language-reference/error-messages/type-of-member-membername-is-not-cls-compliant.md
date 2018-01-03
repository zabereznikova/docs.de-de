---
title: Der Typ des Elements &#39; &lt;Membername&gt;&#39; ist nicht CLS-kompatibel.
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40025
- vbc40025
helpviewer_keywords: BC40025
ms.assetid: adbd34bb-43d2-4266-90e7-cd1afaf49b4e
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bc82714d25efbe9d379fff36f92261cf25a78862
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="type-of-member-39ltmembernamegt39-is-not-cls-compliant"></a><span data-ttu-id="541d1-102">Der Typ des Elements &#39; &lt;Membername&gt;&#39; ist nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="541d1-102">Type of member &#39;&lt;membername&gt;&#39; is not CLS-compliant</span></span>
<span data-ttu-id="541d1-103">Den Datentyp für die angegebene bei diesem Member nicht Teil der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span><span class="sxs-lookup"><span data-stu-id="541d1-103">The data type specified for this member is not part of the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span> <span data-ttu-id="541d1-104">Dies ist kein Fehler innerhalb der Komponente, da die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] und [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Unterstützung für diese Datentypen.</span><span class="sxs-lookup"><span data-stu-id="541d1-104">This is not an error within your component, because the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] and [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] support this data type.</span></span> <span data-ttu-id="541d1-105">Allerdings kann eine andere Komponente in streng CLS-kompatiblem Code geschrieben diesen Datentyp nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="541d1-105">However, another component written in strictly CLS-compliant code might not support this data type.</span></span> <span data-ttu-id="541d1-106">Eine solche Komponente kann möglicherweise nicht erfolgreich mit der Komponente interagieren.</span><span class="sxs-lookup"><span data-stu-id="541d1-106">Such a component might not be able to interact successfully with your component.</span></span>  
  
 <span data-ttu-id="541d1-107">Die folgenden [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] -Datentypen sind nicht CLS-kompatibel:</span><span class="sxs-lookup"><span data-stu-id="541d1-107">The following [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="541d1-108">SByte-Datentyp</span><span class="sxs-lookup"><span data-stu-id="541d1-108">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="541d1-109">UInteger-Datentyp</span><span class="sxs-lookup"><span data-stu-id="541d1-109">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="541d1-110">ULong-Datentyp</span><span class="sxs-lookup"><span data-stu-id="541d1-110">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="541d1-111">UShort-Datentyp</span><span class="sxs-lookup"><span data-stu-id="541d1-111">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="541d1-112">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="541d1-112">By default, this message is a warning.</span></span> <span data-ttu-id="541d1-113">Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="541d1-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="541d1-114">**Fehler-ID:** BC40025</span><span class="sxs-lookup"><span data-stu-id="541d1-114">**Error ID:** BC40025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="541d1-115">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="541d1-115">To correct this error</span></span>  
  
-   <span data-ttu-id="541d1-116">Wenn die Komponente nur mit anderen Schnittstellen [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Komponenten oder nicht mit anderen Komponenten verbunden, müssen Sie nicht nichts ändern.</span><span class="sxs-lookup"><span data-stu-id="541d1-116">If your component interfaces only with other [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] components, or does not interface with any other components, you do not need to change anything.</span></span>  
  
-   <span data-ttu-id="541d1-117">Wenn Sie eine Komponente, die nicht für geschriebenen Datenbreite der [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], um zu bestimmen, entweder über Reflektion können Sie möglicherweise oder aus der Dokumentation gibt an, ob sie diesen Datentyp unterstützt.</span><span class="sxs-lookup"><span data-stu-id="541d1-117">If you are interfacing with a component not written for the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], you might be able to determine, either through reflection or from documentation, whether it supports this data type.</span></span> <span data-ttu-id="541d1-118">Wenn dies der Fall ist, müssen Sie nicht ändert nichts.</span><span class="sxs-lookup"><span data-stu-id="541d1-118">If it does, you do not need to change anything.</span></span>  
  
-   <span data-ttu-id="541d1-119">Wenn Sie mit einer Komponente verbunden sind, die diesen Datentyp nicht unterstützt, müssen Sie ihn durch den ähnlichsten CLS-kompatiblen Typ ersetzen.</span><span class="sxs-lookup"><span data-stu-id="541d1-119">If you are interfacing with a component that does not support this data type, you must replace it with the closest CLS-compliant type.</span></span> <span data-ttu-id="541d1-120">Anstelle von `UInteger` könnten Sie beispielsweise `Integer` verwenden, wenn Sie den Wertebereich über 2.147.483.647 nicht benötigen.</span><span class="sxs-lookup"><span data-stu-id="541d1-120">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="541d1-121">Wenn Sie den erweiterten Bereich benötigen, können Sie `UInteger` durch `Long`ersetzen.</span><span class="sxs-lookup"><span data-stu-id="541d1-121">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="541d1-122">Beachten Sie beim Verbinden mit Automatisierungs- oder COM-Objekten, dass einige Typen über andere Datenbreiten als im [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] verfügen.</span><span class="sxs-lookup"><span data-stu-id="541d1-122">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="541d1-123">Zum Beispiel umfasst `uint` in anderen Umgebungen oft 16 Bits.</span><span class="sxs-lookup"><span data-stu-id="541d1-123">For example, `uint` is often 16 bits in other environments.</span></span> <span data-ttu-id="541d1-124">Wenn Sie ein 16-Bit-Argument an eine solche Komponente übergeben, deklarieren Sie es als `UShort` anstelle von `UInteger` im verwalteten [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Code.</span><span class="sxs-lookup"><span data-stu-id="541d1-124">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="541d1-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="541d1-125">See Also</span></span>  
 [<span data-ttu-id="541d1-126">Reflektion</span><span class="sxs-lookup"><span data-stu-id="541d1-126">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)  
 
