---
title: 'Vorgehensweise: Vergleichen von Ansprüchen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- claims [WCF], comparing
- claims [WCF]
ms.assetid: 0c4ec84d-53df-408f-8953-9bc437f56c28
ms.openlocfilehash: 29254bd661e72b926b21695ccb646480c53b5475
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70797096"
---
# <a name="how-to-compare-claims"></a><span data-ttu-id="f3f95-102">Vorgehensweise: Vergleichen von Ansprüchen</span><span class="sxs-lookup"><span data-stu-id="f3f95-102">How to: Compare Claims</span></span>

<span data-ttu-id="f3f95-103">Die Identitäts Modell Infrastruktur in Windows Communication Foundation (WCF) wird verwendet, um die Autorisierungs Überprüfung durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="f3f95-103">The Identity Model infrastructure in Windows Communication Foundation (WCF) is used to perform authorization checking.</span></span> <span data-ttu-id="f3f95-104">Eine gängige Aufgabe besteht darin, die Ansprüche im Autorisierungskontext mit den Ansprüchen zu vergleichen, die erforderlich sind, um die angeforderte Aktion auszuführen oder auf die angeforderte Ressource zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="f3f95-104">As such, a common task is to compare claims in the authorization context to the claims required to perform the requested action or access the requested resource.</span></span> <span data-ttu-id="f3f95-105">In diesem Thema wird beschrieben, wie Ansprüche verglichen werden, einschließlich integrierter und benutzerdefinierter Anspruchstypen.</span><span class="sxs-lookup"><span data-stu-id="f3f95-105">This topic describes how to compare claims, including built-in and custom claim types.</span></span> <span data-ttu-id="f3f95-106">Weitere Informationen zur Identitäts Modell Infrastruktur finden Sie unter [Verwalten von Ansprüchen und Autorisierung mit dem Identitäts Modell](../feature-details/managing-claims-and-authorization-with-the-identity-model.md).</span><span class="sxs-lookup"><span data-stu-id="f3f95-106">For more information about the Identity Model infrastructure, see [Managing Claims and Authorization with the Identity Model](../feature-details/managing-claims-and-authorization-with-the-identity-model.md).</span></span>

<span data-ttu-id="f3f95-107">Der Vergleich von Ansprüchen umfasst das Vergleichen der drei Bestandteile des Anspruchs (Typ, Recht und Ressource) mit den entsprechenden Teilen eines anderen Anspruchs, um festzustellen, ob sie identisch sind.</span><span class="sxs-lookup"><span data-stu-id="f3f95-107">Claim comparison involves comparing the three parts of a claim (type, right, and resource) against the same parts in another claim to see if they are equal.</span></span> <span data-ttu-id="f3f95-108">Weitere Informationen finden Sie im folgenden Beispiel.</span><span class="sxs-lookup"><span data-stu-id="f3f95-108">See the following example.</span></span>

[!code-csharp[c_CustomClaimComparison#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#9)]
[!code-vb[c_CustomClaimComparison#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#9)]

<span data-ttu-id="f3f95-109">Beide Ansprüche haben den Anspruchstyp <xref:System.IdentityModel.Claims.ClaimTypes.Name%2A>, das Recht <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> und eine Ressource der Zeichenfolge "someone".</span><span class="sxs-lookup"><span data-stu-id="f3f95-109">Both claims have a claim type of <xref:System.IdentityModel.Claims.ClaimTypes.Name%2A>, a right of <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>, and a resource of the string "someone".</span></span> <span data-ttu-id="f3f95-110">Da alle drei Teile des Anspruchs gleich sind, sind die Ansprüche identisch.</span><span class="sxs-lookup"><span data-stu-id="f3f95-110">As all three parts of the claim are equal, the claims themselves are equal.</span></span>

<span data-ttu-id="f3f95-111">Die integrierten Anspruchstypen werden mit der <xref:System.IdentityModel.Claims.Claim.Equals%2A>-Methode verglichen.</span><span class="sxs-lookup"><span data-stu-id="f3f95-111">The built-in claim types are compared using the <xref:System.IdentityModel.Claims.Claim.Equals%2A> method.</span></span> <span data-ttu-id="f3f95-112">Anspruchsspezifischer Vergleichscode wird verwendet, falls erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f3f95-112">Claim-specific comparison code is used where necessary.</span></span> <span data-ttu-id="f3f95-113">Es liegen z. B. die folgenden zwei Benutzerprinzipalnamen (UPN)-Ansprüche vor:</span><span class="sxs-lookup"><span data-stu-id="f3f95-113">For example, given the following two user principal name (UPN) claims:</span></span>

[!code-csharp[c_CustomClaimComparison#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#4)]
[!code-vb[c_CustomClaimComparison#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#4)]

<span data-ttu-id="f3f95-114">der Vergleichs Code in der <xref:System.IdentityModel.Claims.Claim.Equals%2A> -Methode `true`gibt zurück `example\someone` , wobei angenommen wird, dass dersomeone@example.comgleiche Domänen Benutzer als ' ' bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="f3f95-114">the comparison code in the <xref:System.IdentityModel.Claims.Claim.Equals%2A> method returns `true`, assuming `example\someone` identifies the same domain user as "someone@example.com".</span></span>

<span data-ttu-id="f3f95-115">Benutzerdefinierte Anspruchstypen können auch mit der <xref:System.IdentityModel.Claims.Claim.Equals%2A>-Methode verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="f3f95-115">Custom claim types can also be compared using the <xref:System.IdentityModel.Claims.Claim.Equals%2A> method.</span></span> <span data-ttu-id="f3f95-116">In Fällen, in denen der von der <xref:System.IdentityModel.Claims.Claim.Resource%2A>-Eigenschaft des Anspruchs zurückgegebene Typ kein primitiver Typ ist, gibt <xref:System.IdentityModel.Claims.Claim.Equals%2A> nur `true` zurück, wenn die von den `Resource`-Eigenschaften zurückgegebenen Werte laut der <xref:System.IdentityModel.Claims.Claim.Equals%2A>-Methode identisch sind.</span><span class="sxs-lookup"><span data-stu-id="f3f95-116">However, in cases where the type returned by the <xref:System.IdentityModel.Claims.Claim.Resource%2A> property of the claim is something other than a primitive type, the <xref:System.IdentityModel.Claims.Claim.Equals%2A> returns `true` only if the values returned by the `Resource` properties are equal according to the <xref:System.IdentityModel.Claims.Claim.Equals%2A> method.</span></span> <span data-ttu-id="f3f95-117">In Fällen, in denen dies nicht zutrifft, überschreibt der von der `Resource`-Eigenschaft zurückgegebene benutzerdefinierte Typ die <xref:System.IdentityModel.Claims.Claim.Equals%2A>-Methode und die <xref:System.Object.GetHashCode%2A>-Methode, um die erforderliche benutzerdefinierte Verarbeitung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f3f95-117">In cases where this is not appropriate, the custom type returned by the `Resource` property should override the <xref:System.IdentityModel.Claims.Claim.Equals%2A> and <xref:System.Object.GetHashCode%2A> methods to perform whatever custom processing is necessary.</span></span>

## <a name="comparing-built-in-claims"></a><span data-ttu-id="f3f95-118">Vergleichen von integrierten Ansprüchen</span><span class="sxs-lookup"><span data-stu-id="f3f95-118">Comparing built-in claims</span></span>

1. <span data-ttu-id="f3f95-119">Wenn zwei Instanzen der <xref:System.IdentityModel.Claims.Claim>-Klasse vorliegen, verwenden Sie <xref:System.IdentityModel.Claims.Claim.Equals%2A> für den Vergleich, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f3f95-119">Given two instances of the <xref:System.IdentityModel.Claims.Claim> class, use the <xref:System.IdentityModel.Claims.Claim.Equals%2A> to make the comparison, as shown in the following code.</span></span>

     [!code-csharp[c_CustomClaimComparison#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#5)]
     [!code-vb[c_CustomClaimComparison#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#5)]

### <a name="comparing-custom-claims-with-primitive-resource-types"></a><span data-ttu-id="f3f95-120">Vergleichen von benutzerdefinierten Ansprüchen mit primitiven Ressourcentypen</span><span class="sxs-lookup"><span data-stu-id="f3f95-120">Comparing custom claims with primitive resource types</span></span>

1. <span data-ttu-id="f3f95-121">Für benutzerdefinierte Ansprüche mit primitiven Ressourcentypen kann der Vergleich wie für integrierte Ansprüche erfolgen, wie im folgenden Code veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="f3f95-121">For custom claims with primitive resource types, comparison can be performed as for built-in claims, as shown in the following code.</span></span>

     [!code-csharp[c_CustomClaimComparison#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#6)]
     [!code-vb[c_CustomClaimComparison#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#6)]

2. <span data-ttu-id="f3f95-122">Für benutzerdefinierte Ansprüche mit struktur- oder klassenbasierten Typen überschreibt der Ressourcentyp die <xref:System.IdentityModel.Claims.Claim.Equals%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="f3f95-122">For custom claims with structure or class based resource types, the resource type should override the <xref:System.IdentityModel.Claims.Claim.Equals%2A> method.</span></span>

3. <span data-ttu-id="f3f95-123">Überprüfen Sie zunächst, ob der `obj`-Parameter `null` ist, und wenn ja, geben Sie `false` zurück.</span><span class="sxs-lookup"><span data-stu-id="f3f95-123">First check whether the `obj` parameter is `null`, and if so, return `false`.</span></span>

     [!code-csharp[c_CustomClaimComparison#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#7)]
     [!code-vb[c_CustomClaimComparison#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#7)]

4. <span data-ttu-id="f3f95-124">Rufen Sie als nächstes <xref:System.Object.ReferenceEquals%2A> auf, und übergeben Sie `this` und `obj` als Parameter.</span><span class="sxs-lookup"><span data-stu-id="f3f95-124">Next call <xref:System.Object.ReferenceEquals%2A> and pass `this` and `obj` as parameters.</span></span> <span data-ttu-id="f3f95-125">Wenn `true` zurückgegeben wird, geben Sie `true` zurück.</span><span class="sxs-lookup"><span data-stu-id="f3f95-125">If it returns `true`, then return `true`.</span></span>

     [!code-csharp[c_CustomClaimComparison#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#8)]
     [!code-vb[c_CustomClaimComparison#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#8)]

5. <span data-ttu-id="f3f95-126">Versuchen Sie danach, `obj` einer lokalen Variable des Klassentyps zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="f3f95-126">Next attempt to assign `obj` to a local variable of the class type.</span></span> <span data-ttu-id="f3f95-127">Wenn dieser Versuch fehlschlägt, lautet die Referenz `null`.</span><span class="sxs-lookup"><span data-stu-id="f3f95-127">If this fails, the reference is `null`.</span></span> <span data-ttu-id="f3f95-128">In derartigen Fällen wird `false` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f3f95-128">In such cases, return `false`.</span></span>

6. <span data-ttu-id="f3f95-129">Führen Sie den benutzerdefinierten Vergleich durch, der notwendig ist, um den aktuellen Anspruch ordnungsgemäß mit dem bereitgestellten Anspruch zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="f3f95-129">Perform the custom comparison necessary to correctly compare the current claim to the provided claim.</span></span>

## <a name="example"></a><span data-ttu-id="f3f95-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f3f95-130">Example</span></span>

<span data-ttu-id="f3f95-131">Das folgende Beispiel zeigt einen Vergleich von benutzerdefinierten Ansprüchen, deren Anspruchsressource ein nicht primitiver Typ ist.</span><span class="sxs-lookup"><span data-stu-id="f3f95-131">The following example shows a comparison of custom claims where the claim resource is a non-primitive type.</span></span>

[!code-csharp[c_CustomClaimComparison#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#0)]
[!code-vb[c_CustomClaimComparison#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#0)]

## <a name="see-also"></a><span data-ttu-id="f3f95-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f3f95-132">See also</span></span>

- [<span data-ttu-id="f3f95-133">Verwalten von Ansprüchen und Autorisierung mit dem Identitätsmodell</span><span class="sxs-lookup"><span data-stu-id="f3f95-133">Managing Claims and Authorization with the Identity Model</span></span>](../feature-details/managing-claims-and-authorization-with-the-identity-model.md)
- [<span data-ttu-id="f3f95-134">Vorgehensweise: Erstellen eines benutzerdefinierten Anspruchs</span><span class="sxs-lookup"><span data-stu-id="f3f95-134">How to: Create a Custom Claim</span></span>](how-to-create-a-custom-claim.md)
