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
ms.openlocfilehash: 43507ac8e9b5843e8fa9496737a3d77b3a425a7f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963769"
---
# <a name="writeonly-visual-basic"></a><span data-ttu-id="bcaa7-102">WriteOnly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bcaa7-102">WriteOnly (Visual Basic)</span></span>
<span data-ttu-id="bcaa7-103">Gibt an, dass eine Eigenschaft geschrieben, jedoch nicht gelesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="bcaa7-103">Specifies that a property can be written but not read.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bcaa7-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bcaa7-104">Remarks</span></span>  
  
## <a name="rules"></a><span data-ttu-id="bcaa7-105">Regeln</span><span class="sxs-lookup"><span data-stu-id="bcaa7-105">Rules</span></span>  
 <span data-ttu-id="bcaa7-106">**Deklarations Kontext.**</span><span class="sxs-lookup"><span data-stu-id="bcaa7-106">**Declaration Context.**</span></span> <span data-ttu-id="bcaa7-107">Sie können `WriteOnly` nur auf Modulebene verwenden.</span><span class="sxs-lookup"><span data-stu-id="bcaa7-107">You can use `WriteOnly` only at module level.</span></span> <span data-ttu-id="bcaa7-108">Dies bedeutet, dass der Deklarations `WriteOnly` Kontext für eine Eigenschaft eine Klasse, eine Struktur oder ein Modul sein muss und weder eine Quelldatei, ein Namespace noch eine Prozedur sein darf.</span><span class="sxs-lookup"><span data-stu-id="bcaa7-108">This means the declaration context for a `WriteOnly` property must be a class, structure, or module, and cannot be a source file, namespace, or procedure.</span></span>  
  
 <span data-ttu-id="bcaa7-109">Sie können eine Eigenschaft als `WriteOnly`, jedoch nicht als Variable deklarieren.</span><span class="sxs-lookup"><span data-stu-id="bcaa7-109">You can declare a property as `WriteOnly`, but not a variable.</span></span>  
  
## <a name="when-to-use-writeonly"></a><span data-ttu-id="bcaa7-110">Verwendung von "schreibgeschützt"</span><span class="sxs-lookup"><span data-stu-id="bcaa7-110">When to Use WriteOnly</span></span>  
 <span data-ttu-id="bcaa7-111">Manchmal möchten Sie, dass der verarbeitende Code einen Wert festlegen kann, aber nicht ermitteln kann, was er ist.</span><span class="sxs-lookup"><span data-stu-id="bcaa7-111">Sometimes you want the consuming code to be able to set a value but not discover what it is.</span></span> <span data-ttu-id="bcaa7-112">Sensible Daten, z. b. eine Sozialversicherungsnummer oder ein Kennwort, müssen z. b. vor dem Zugriff durch eine beliebige Komponente geschützt werden, die Sie nicht festgelegt hat.</span><span class="sxs-lookup"><span data-stu-id="bcaa7-112">For example, sensitive data, such as a social registration number or a password, needs to be protected from access by any component that did not set it.</span></span> <span data-ttu-id="bcaa7-113">In diesen Fällen können Sie eine `WriteOnly` -Eigenschaft verwenden, um den Wert festzulegen.</span><span class="sxs-lookup"><span data-stu-id="bcaa7-113">In these cases, you can use a `WriteOnly` property to set the value.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="bcaa7-114">Wenn Sie eine `WriteOnly` Eigenschaft definieren und verwenden, sollten Sie die folgenden zusätzlichen Schutzmaßnahmen beachten:</span><span class="sxs-lookup"><span data-stu-id="bcaa7-114">When you define and use a `WriteOnly` property, consider the following additional protective measures:</span></span>  
  
- <span data-ttu-id="bcaa7-115">**Dende.**</span><span class="sxs-lookup"><span data-stu-id="bcaa7-115">**Overriding.**</span></span> <span data-ttu-id="bcaa7-116">Wenn die Eigenschaft ein Member einer Klasse ist, lassen Sie die Standardeinstellung [nodeverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)zu, und deklarieren Sie Sie `Overridable` nicht `MustOverride`oder.</span><span class="sxs-lookup"><span data-stu-id="bcaa7-116">If the property is a member of a class, allow it to default to [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), and do not declare it `Overridable` or `MustOverride`.</span></span> <span data-ttu-id="bcaa7-117">Dadurch wird verhindert, dass eine abgeleitete Klasse den unerwünschten Zugriff über eine außer Kraft Setzung ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="bcaa7-117">This prevents a derived class from making undesired access through an override.</span></span>  
  
- <span data-ttu-id="bcaa7-118">**Zugriffsebene.**</span><span class="sxs-lookup"><span data-stu-id="bcaa7-118">**Access Level.**</span></span> <span data-ttu-id="bcaa7-119">Wenn Sie die sensiblen Daten der Eigenschaft in einer oder mehreren Variablen speichern, deklarieren Sie diese als [Privat](../../../visual-basic/language-reference/modifiers/private.md) , sodass kein anderer Code darauf zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="bcaa7-119">If you hold the property's sensitive data in one or more variables, declare them [Private](../../../visual-basic/language-reference/modifiers/private.md) so that no other code can access them.</span></span>  
  
- <span data-ttu-id="bcaa7-120">**Verschlüsselungs.**</span><span class="sxs-lookup"><span data-stu-id="bcaa7-120">**Encryption.**</span></span> <span data-ttu-id="bcaa7-121">Speichern Sie alle sensiblen Daten in verschlüsselter Form und nicht als Klartext.</span><span class="sxs-lookup"><span data-stu-id="bcaa7-121">Store all sensitive data in encrypted form rather than in plain text.</span></span> <span data-ttu-id="bcaa7-122">Wenn bösartiger Code auf diese Weise Zugriff auf diesen Speicherbereich erlangt, ist es schwieriger, die Daten zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="bcaa7-122">If malicious code somehow gains access to that area of memory, it is more difficult to make use of the data.</span></span> <span data-ttu-id="bcaa7-123">Die Verschlüsselung ist auch dann nützlich, wenn es erforderlich ist, die sensiblen Daten zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="bcaa7-123">Encryption is also useful if it is necessary to serialize the sensitive data.</span></span>  
  
- <span data-ttu-id="bcaa7-124">**Zurücksetzen.**</span><span class="sxs-lookup"><span data-stu-id="bcaa7-124">**Resetting.**</span></span> <span data-ttu-id="bcaa7-125">Wenn die Klasse, Struktur oder das Modul, das die Eigenschaft definiert, beendet wird, setzen Sie die sensiblen Daten auf die Standardwerte oder auf andere bedeutungslose Werte zurück.</span><span class="sxs-lookup"><span data-stu-id="bcaa7-125">When the class, structure, or module defining the property is being terminated, reset the sensitive data to default values or to other meaningless values.</span></span> <span data-ttu-id="bcaa7-126">Dies bietet zusätzlichen Schutz, wenn dieser Speicherbereich für den allgemeinen Zugriff freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="bcaa7-126">This gives extra protection when that area of memory is freed for general access.</span></span>  
  
- <span data-ttu-id="bcaa7-127">**Persistenz.**</span><span class="sxs-lookup"><span data-stu-id="bcaa7-127">**Persistence.**</span></span> <span data-ttu-id="bcaa7-128">Bewahren Sie keine sensiblen Daten auf, z. b. auf dem Datenträger, wenn Sie dies vermeiden können.</span><span class="sxs-lookup"><span data-stu-id="bcaa7-128">Do not persist any sensitive data, for example on disk, if you can avoid it.</span></span> <span data-ttu-id="bcaa7-129">Schreiben Sie außerdem keine sensiblen Daten in die Zwischenablage.</span><span class="sxs-lookup"><span data-stu-id="bcaa7-129">Also, do not write any sensitive data to the Clipboard.</span></span>  
  
 <span data-ttu-id="bcaa7-130">Der `WriteOnly` -Modifizierer kann in diesem Kontext verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="bcaa7-130">The `WriteOnly` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="bcaa7-131">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="bcaa7-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="bcaa7-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bcaa7-132">See also</span></span>

- [<span data-ttu-id="bcaa7-133">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="bcaa7-133">ReadOnly</span></span>](../../../visual-basic/language-reference/modifiers/readonly.md)
- [<span data-ttu-id="bcaa7-134">Private</span><span class="sxs-lookup"><span data-stu-id="bcaa7-134">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="bcaa7-135">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="bcaa7-135">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
