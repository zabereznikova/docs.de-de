---
title: <add> von <authorizationPolicies>
ms.date: 03/30/2017
ms.assetid: 613a03d8-4384-4556-bce2-8c23286c0bb0
ms.openlocfilehash: 532f7f1a74cb3af24d7a1bc26046be901f3cf025
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59205237"
---
# <a name="add-of-authorizationpolicies"></a><span data-ttu-id="d5419-102">\<Hinzufügen > der \<AuthorizationPolicies ></span><span class="sxs-lookup"><span data-stu-id="d5419-102">\<add> of \<authorizationPolicies></span></span>
<span data-ttu-id="d5419-103">Gibt eine Autorisierungsrichtlinie für Anspruchstransformation an.</span><span class="sxs-lookup"><span data-stu-id="d5419-103">Specifies an authorization policy for claim transformation.</span></span>  
  
 <span data-ttu-id="d5419-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d5419-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d5419-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="d5419-105">\<behaviors></span></span>  
<span data-ttu-id="d5419-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="d5419-106">\<behavior></span></span>  
<span data-ttu-id="d5419-107">\<serviceAuthorization></span><span class="sxs-lookup"><span data-stu-id="d5419-107">\<serviceAuthorization></span></span>  
<span data-ttu-id="d5419-108">\<authorizationPolicies></span><span class="sxs-lookup"><span data-stu-id="d5419-108">\<authorizationPolicies></span></span>  
<span data-ttu-id="d5419-109">\<add></span><span class="sxs-lookup"><span data-stu-id="d5419-109">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5419-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="d5419-110">Syntax</span></span>  
  
```xml  
<authorizationPolicies>
  <add policyType="String" />
</authorizationPolicies>
```  
  
## <a name="type"></a><span data-ttu-id="d5419-111">Typ</span><span class="sxs-lookup"><span data-stu-id="d5419-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d5419-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d5419-112">Attributes and Elements</span></span>  
 <span data-ttu-id="d5419-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d5419-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d5419-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="d5419-114">Attributes</span></span>  
  
|<span data-ttu-id="d5419-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="d5419-115">Attribute</span></span>|<span data-ttu-id="d5419-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d5419-116">Description</span></span>|  
|---------------|-----------------|  
|`policyType`|<span data-ttu-id="d5419-117">Ein erforderliches Zeichenfolgenattribut.</span><span class="sxs-lookup"><span data-stu-id="d5419-117">A required String attribute.</span></span><br /><br /> <span data-ttu-id="d5419-118">Das Windows Communication Foundation (WCF)-Zugriffssteuerungsmodell unterstützt die Bereitstellung einer Gruppe von Autorisierungsrichtlinien als Typen.</span><span class="sxs-lookup"><span data-stu-id="d5419-118">The Windows Communication Foundation (WCF) access control model supports provisioning a set of authorization policies as types.</span></span> <span data-ttu-id="d5419-119">Dieses Attribut gibt eine Autorisierungsrichtlinie an, die die Transformation einer Gruppe von Eingabeansprüchen in eine andere Gruppe von Eingabeansprüchen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="d5419-119">This attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="d5419-120">Die Zugriffssteuerung kann basierend darauf gewährt oder verweigert werden.</span><span class="sxs-lookup"><span data-stu-id="d5419-120">Access control can be granted or denied based on that.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d5419-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d5419-121">Child Elements</span></span>  
 <span data-ttu-id="d5419-122">Keine</span><span class="sxs-lookup"><span data-stu-id="d5419-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d5419-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d5419-123">Parent Elements</span></span>  
  
|<span data-ttu-id="d5419-124">Element</span><span class="sxs-lookup"><span data-stu-id="d5419-124">Element</span></span>|<span data-ttu-id="d5419-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d5419-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d5419-126">\<authorizationPolicies></span><span class="sxs-lookup"><span data-stu-id="d5419-126">\<authorizationPolicies></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authorizationpolicies.md)|<span data-ttu-id="d5419-127">Gibt eine Auflistung von Autorisierungsrichtlinientypen an.</span><span class="sxs-lookup"><span data-stu-id="d5419-127">Specifies a collection of authorization policy types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5419-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d5419-128">Remarks</span></span>  
 <span data-ttu-id="d5419-129">Jede Autorisierungsrichtlinie enthält ein einziges erforderliches `policyType`-Attribut, bei dem es sich um eine Zeichenfolge handelt.</span><span class="sxs-lookup"><span data-stu-id="d5419-129">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="d5419-130">Das Attribut gibt eine Autorisierungsrichtlinie an, die die Transformation einer Gruppe von Eingabeansprüchen in eine andere Gruppe von Eingabeansprüchen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="d5419-130">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="d5419-131">Die Zugriffssteuerung kann basierend darauf gewährt oder verweigert werden.</span><span class="sxs-lookup"><span data-stu-id="d5419-131">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="d5419-132">Weitere Informationen zur Funktionsweise einer Autorisierungsrichtlinie finden Sie unter <xref:System.IdentityModel.Policy.IAuthorizationPolicy> und [Autorisierungsrichtlinie](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="d5419-132">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5419-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d5419-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [<span data-ttu-id="d5419-134">Zugriffsautorisierung für Dienstvorgänge</span><span class="sxs-lookup"><span data-stu-id="d5419-134">Authorizing Access to Service Operations</span></span>](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="d5419-135">Vorgehensweise: Erstellen eines benutzerdefinierten Autorisierungs-Managers für einen Dienst</span><span class="sxs-lookup"><span data-stu-id="d5419-135">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="d5419-136">\<add></span><span class="sxs-lookup"><span data-stu-id="d5419-136">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-authorizationpolicies.md)
- [<span data-ttu-id="d5419-137">Autorisierungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="d5419-137">Authorization Policy</span></span>](../../../../../docs/framework/wcf/samples/authorization-policy.md)
