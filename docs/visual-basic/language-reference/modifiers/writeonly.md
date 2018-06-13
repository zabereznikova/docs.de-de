---
title: WriteOnly (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- WriteOnly
- vb.WriteOnly
helpviewer_keywords:
- write-only properties
- WriteOnly keyword [Visual Basic]
- sensitive data, protecting
- properties [Visual Basic], write-only
- sensitive data
ms.assetid: 488d2899-b09f-4cee-92f0-6f9f9fc4f944
ms.openlocfilehash: 4f34f7f4ada3f8d61c9d855eab1b8b073a3d5ed8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33599202"
---
# <a name="writeonly-visual-basic"></a><span data-ttu-id="d9569-102">WriteOnly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9569-102">WriteOnly (Visual Basic)</span></span>
<span data-ttu-id="d9569-103">Gibt an, dass eine Eigenschaft geschrieben, aber nicht gelesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="d9569-103">Specifies that a property can be written but not read.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d9569-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d9569-104">Remarks</span></span>  
  
## <a name="rules"></a><span data-ttu-id="d9569-105">Regeln</span><span class="sxs-lookup"><span data-stu-id="d9569-105">Rules</span></span>  
 <span data-ttu-id="d9569-106">**Deklarationskontext.**</span><span class="sxs-lookup"><span data-stu-id="d9569-106">**Declaration Context.**</span></span> <span data-ttu-id="d9569-107">Sie können `WriteOnly` nur auf Modulebene verwenden.</span><span class="sxs-lookup"><span data-stu-id="d9569-107">You can use `WriteOnly` only at module level.</span></span> <span data-ttu-id="d9569-108">Dies bedeutet, dass der Deklarationskontext für eine `WriteOnly` Eigenschaft muss eine Klasse, Struktur oder Modul, und eine Quelldatei, Namespace oder Prozedur nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="d9569-108">This means the declaration context for a `WriteOnly` property must be a class, structure, or module, and cannot be a source file, namespace, or procedure.</span></span>  
  
 <span data-ttu-id="d9569-109">Sie können deklarieren, dass eine Eigenschaft als `WriteOnly`, aber keine Variable.</span><span class="sxs-lookup"><span data-stu-id="d9569-109">You can declare a property as `WriteOnly`, but not a variable.</span></span>  
  
## <a name="when-to-use-writeonly"></a><span data-ttu-id="d9569-110">WriteOnly verwenden</span><span class="sxs-lookup"><span data-stu-id="d9569-110">When to Use WriteOnly</span></span>  
 <span data-ttu-id="d9569-111">In einigen Fällen möchten Sie in der Lage, einen Wert festlegen, doch nicht zu ermitteln, was ist den verwendeten Code.</span><span class="sxs-lookup"><span data-stu-id="d9569-111">Sometimes you want the consuming code to be able to set a value but not discover what it is.</span></span> <span data-ttu-id="d9569-112">Beispielsweise müssen vertrauliche Daten, z. B. eine Sozialversicherungsnummer oder ein Kennwort aus Access von keiner Komponente geschützt werden, die nicht für die festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d9569-112">For example, sensitive data, such as a social registration number or a password, needs to be protected from access by any component that did not set it.</span></span> <span data-ttu-id="d9569-113">In diesen Fällen können Sie eine `WriteOnly` Eigenschaft zum Festlegen des Werts.</span><span class="sxs-lookup"><span data-stu-id="d9569-113">In these cases, you can use a `WriteOnly` property to set the value.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d9569-114">Wenn Sie definieren und verwenden eine `WriteOnly` -Eigenschaft, sollten Sie die folgenden zusätzlichen Schutzmaßnahmen:</span><span class="sxs-lookup"><span data-stu-id="d9569-114">When you define and use a `WriteOnly` property, consider the following additional protective measures:</span></span>  
  
-   <span data-ttu-id="d9569-115">**Überschreiben.**</span><span class="sxs-lookup"><span data-stu-id="d9569-115">**Overriding.**</span></span> <span data-ttu-id="d9569-116">Wenn die Eigenschaft auf einen Member einer Klasse ist, ermöglichen es standardmäßig [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), und nicht deklarieren `Overridable` oder `MustOverride`.</span><span class="sxs-lookup"><span data-stu-id="d9569-116">If the property is a member of a class, allow it to default to [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), and do not declare it `Overridable` or `MustOverride`.</span></span> <span data-ttu-id="d9569-117">Dadurch wird verhindert, dass eine abgeleitete Klasse unerwünschten Zugriff über eine Außerkraftsetzung.</span><span class="sxs-lookup"><span data-stu-id="d9569-117">This prevents a derived class from making undesired access through an override.</span></span>  
  
-   <span data-ttu-id="d9569-118">**Zugriffsebene.**</span><span class="sxs-lookup"><span data-stu-id="d9569-118">**Access Level.**</span></span> <span data-ttu-id="d9569-119">Wenn Sie die Eigenschaft sensible Daten in eine oder mehrere Variablen enthalten, deklarieren Sie diese [Private](../../../visual-basic/language-reference/modifiers/private.md) , damit kein anderer Code darauf zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="d9569-119">If you hold the property's sensitive data in one or more variables, declare them [Private](../../../visual-basic/language-reference/modifiers/private.md) so that no other code can access them.</span></span>  
  
-   <span data-ttu-id="d9569-120">**Die Verschlüsselung.**</span><span class="sxs-lookup"><span data-stu-id="d9569-120">**Encryption.**</span></span> <span data-ttu-id="d9569-121">Speichern Sie alle gespeicherten vertraulichen Daten in verschlüsselter Form anstatt im nur-Text.</span><span class="sxs-lookup"><span data-stu-id="d9569-121">Store all sensitive data in encrypted form rather than in plain text.</span></span> <span data-ttu-id="d9569-122">Bösartiger Code irgendwie Zugriff auf diesen Bereich des Arbeitsspeichers erlangt, ist es schwieriger zu stellen der Daten verwenden.</span><span class="sxs-lookup"><span data-stu-id="d9569-122">If malicious code somehow gains access to that area of memory, it is more difficult to make use of the data.</span></span> <span data-ttu-id="d9569-123">Verschlüsselung ist auch hilfreich, wenn es erforderlich, um die sensiblen Daten zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="d9569-123">Encryption is also useful if it is necessary to serialize the sensitive data.</span></span>  
  
-   <span data-ttu-id="d9569-124">**Zurücksetzen.**</span><span class="sxs-lookup"><span data-stu-id="d9569-124">**Resetting.**</span></span> <span data-ttu-id="d9569-125">Wenn die Klasse, Struktur oder Modul, definieren die Eigenschaft wird beendet, die sensiblen Daten auf Standardwerte oder andere bedeutungslose Werte zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="d9569-125">When the class, structure, or module defining the property is being terminated, reset the sensitive data to default values or to other meaningless values.</span></span> <span data-ttu-id="d9569-126">Dies bietet zusätzlichen Schutz, wenn Sie diesen Bereich des Arbeitsspeichers für den allgemeinen Zugriff freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d9569-126">This gives extra protection when that area of memory is freed for general access.</span></span>  
  
-   <span data-ttu-id="d9569-127">**Dauerhaftigkeit.**</span><span class="sxs-lookup"><span data-stu-id="d9569-127">**Persistence.**</span></span> <span data-ttu-id="d9569-128">Beibehalten Sie vertraulichen Daten, z. B. auf dem Datenträger nicht, wenn Sie dies vermeiden können.</span><span class="sxs-lookup"><span data-stu-id="d9569-128">Do not persist any sensitive data, for example on disk, if you can avoid it.</span></span> <span data-ttu-id="d9569-129">Schreiben Sie auch nicht vertraulichen Daten in die Zwischenablage.</span><span class="sxs-lookup"><span data-stu-id="d9569-129">Also, do not write any sensitive data to the Clipboard.</span></span>  
  
 <span data-ttu-id="d9569-130">Die `WriteOnly` Modifizierer kann in diesem Kontext verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="d9569-130">The `WriteOnly` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="d9569-131">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d9569-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="d9569-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9569-132">See Also</span></span>  
 [<span data-ttu-id="d9569-133">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="d9569-133">ReadOnly</span></span>](../../../visual-basic/language-reference/modifiers/readonly.md)  
 [<span data-ttu-id="d9569-134">Private</span><span class="sxs-lookup"><span data-stu-id="d9569-134">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
 [<span data-ttu-id="d9569-135">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d9569-135">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
