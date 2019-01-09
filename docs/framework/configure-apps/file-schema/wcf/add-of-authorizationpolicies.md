---
title: '&lt;add&gt; von &lt;authorizationPolicies&gt;'
ms.date: 03/30/2017
ms.assetid: 613a03d8-4384-4556-bce2-8c23286c0bb0
ms.openlocfilehash: 5f4afe0a0a72d7f45dd0ed38cbcc7a0d89d17d44
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54148460"
---
# <a name="ltaddgt-of-ltauthorizationpoliciesgt"></a><span data-ttu-id="16282-102">&lt;add&gt; von &lt;authorizationPolicies&gt;</span><span class="sxs-lookup"><span data-stu-id="16282-102">&lt;add&gt; of &lt;authorizationPolicies&gt;</span></span>
<span data-ttu-id="16282-103">Gibt eine Autorisierungsrichtlinie für Anspruchstransformation an.</span><span class="sxs-lookup"><span data-stu-id="16282-103">Specifies an authorization policy for claim transformation.</span></span>  
  
 <span data-ttu-id="16282-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="16282-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="16282-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="16282-105">\<behaviors></span></span>  
<span data-ttu-id="16282-106">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="16282-106">\<behavior></span></span>  
<span data-ttu-id="16282-107">\<ServiceAuthorization ></span><span class="sxs-lookup"><span data-stu-id="16282-107">\<serviceAuthorization></span></span>  
<span data-ttu-id="16282-108">\<AuthorizationPolicies ></span><span class="sxs-lookup"><span data-stu-id="16282-108">\<authorizationPolicies></span></span>  
<span data-ttu-id="16282-109">\<add></span><span class="sxs-lookup"><span data-stu-id="16282-109">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16282-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="16282-110">Syntax</span></span>  
  
```xml  
<authorizationPolicies>
  <add policyType="String" />
</authorizationPolicies>
```  
  
## <a name="type"></a><span data-ttu-id="16282-111">Typ</span><span class="sxs-lookup"><span data-stu-id="16282-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="16282-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="16282-112">Attributes and Elements</span></span>  
 <span data-ttu-id="16282-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="16282-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="16282-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="16282-114">Attributes</span></span>  
  
|<span data-ttu-id="16282-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="16282-115">Attribute</span></span>|<span data-ttu-id="16282-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="16282-116">Description</span></span>|  
|---------------|-----------------|  
|`policyType`|<span data-ttu-id="16282-117">Ein erforderliches Zeichenfolgenattribut.</span><span class="sxs-lookup"><span data-stu-id="16282-117">A required String attribute.</span></span><br /><br /> <span data-ttu-id="16282-118">Das Windows Communication Foundation (WCF)-Zugriffssteuerungsmodell unterstützt die Bereitstellung einer Gruppe von Autorisierungsrichtlinien als Typen.</span><span class="sxs-lookup"><span data-stu-id="16282-118">The Windows Communication Foundation (WCF) access control model supports provisioning a set of authorization policies as types.</span></span> <span data-ttu-id="16282-119">Dieses Attribut gibt eine Autorisierungsrichtlinie an, die die Transformation einer Gruppe von Eingabeansprüchen in eine andere Gruppe von Eingabeansprüchen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="16282-119">This attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="16282-120">Die Zugriffssteuerung kann basierend darauf gewährt oder verweigert werden.</span><span class="sxs-lookup"><span data-stu-id="16282-120">Access control can be granted or denied based on that.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="16282-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="16282-121">Child Elements</span></span>  
 <span data-ttu-id="16282-122">Keine</span><span class="sxs-lookup"><span data-stu-id="16282-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="16282-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="16282-123">Parent Elements</span></span>  
  
|<span data-ttu-id="16282-124">Element</span><span class="sxs-lookup"><span data-stu-id="16282-124">Element</span></span>|<span data-ttu-id="16282-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="16282-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="16282-126">\<AuthorizationPolicies ></span><span class="sxs-lookup"><span data-stu-id="16282-126">\<authorizationPolicies></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authorizationpolicies.md)|<span data-ttu-id="16282-127">Gibt eine Auflistung von Autorisierungsrichtlinientypen an.</span><span class="sxs-lookup"><span data-stu-id="16282-127">Specifies a collection of authorization policy types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16282-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="16282-128">Remarks</span></span>  
 <span data-ttu-id="16282-129">Jede Autorisierungsrichtlinie enthält ein einziges erforderliches `policyType`-Attribut, bei dem es sich um eine Zeichenfolge handelt.</span><span class="sxs-lookup"><span data-stu-id="16282-129">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="16282-130">Das Attribut gibt eine Autorisierungsrichtlinie an, die die Transformation einer Gruppe von Eingabeansprüchen in eine andere Gruppe von Eingabeansprüchen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="16282-130">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="16282-131">Die Zugriffssteuerung kann basierend darauf gewährt oder verweigert werden.</span><span class="sxs-lookup"><span data-stu-id="16282-131">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="16282-132">Weitere Informationen zur Funktionsweise einer Autorisierungsrichtlinie finden Sie unter <xref:System.IdentityModel.Policy.IAuthorizationPolicy> und [Autorisierungsrichtlinie](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="16282-132">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16282-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="16282-133">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
 <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>  
 <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>  
 <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>  
 <xref:System.IdentityModel.Policy.IAuthorizationPolicy>  
 [<span data-ttu-id="16282-134">Zugriffsautorisierung für Dienstvorgänge</span><span class="sxs-lookup"><span data-stu-id="16282-134">Authorizing Access to Service Operations</span></span>](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)  
 [<span data-ttu-id="16282-135">Vorgehensweise: Erstellen eines benutzerdefinierten Autorisierungs-Managers für einen Dienst</span><span class="sxs-lookup"><span data-stu-id="16282-135">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)  
 [<span data-ttu-id="16282-136">\<add></span><span class="sxs-lookup"><span data-stu-id="16282-136">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-authorizationpolicies.md)  
 [<span data-ttu-id="16282-137">Autorisierungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="16282-137">Authorization Policy</span></span>](../../../../../docs/framework/wcf/samples/authorization-policy.md)
