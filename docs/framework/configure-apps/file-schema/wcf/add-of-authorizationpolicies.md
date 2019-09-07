---
title: <add> von <authorizationPolicies>
ms.date: 03/30/2017
ms.assetid: 613a03d8-4384-4556-bce2-8c23286c0bb0
ms.openlocfilehash: e2597bc51e788c919bfe3ce3422ae2911cc6b33b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400698"
---
# <a name="add-of-authorizationpolicies"></a><span data-ttu-id="6f346-102">\<Hinzufügen von \<> von AuthorizationPolicies ></span><span class="sxs-lookup"><span data-stu-id="6f346-102">\<add> of \<authorizationPolicies></span></span>
<span data-ttu-id="6f346-103">Gibt eine Autorisierungsrichtlinie für Anspruchstransformation an.</span><span class="sxs-lookup"><span data-stu-id="6f346-103">Specifies an authorization policy for claim transformation.</span></span>  
  
<span data-ttu-id="6f346-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6f346-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6f346-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="6f346-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="6f346-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="6f346-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="6f346-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceverhaltens>** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="6f346-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="6f346-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="6f346-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="6f346-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ServiceAuthorization->** ](serviceauthorization-element.md)</span><span class="sxs-lookup"><span data-stu-id="6f346-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceAuthorization>**](serviceauthorization-element.md)</span></span>\
<span data-ttu-id="6f346-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<AuthorizationPolicies->** ](authorizationpolicies.md)</span><span class="sxs-lookup"><span data-stu-id="6f346-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<authorizationPolicies>**](authorizationpolicies.md)</span></span>\
<span data-ttu-id="6f346-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> Hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="6f346-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f346-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="6f346-112">Syntax</span></span>  
  
```xml  
<authorizationPolicies>
  <add policyType="String" />
</authorizationPolicies>
```  
  
## <a name="type"></a><span data-ttu-id="6f346-113">Typ</span><span class="sxs-lookup"><span data-stu-id="6f346-113">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6f346-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6f346-114">Attributes and Elements</span></span>  
 <span data-ttu-id="6f346-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6f346-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6f346-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="6f346-116">Attributes</span></span>  
  
|<span data-ttu-id="6f346-117">Attribut</span><span class="sxs-lookup"><span data-stu-id="6f346-117">Attribute</span></span>|<span data-ttu-id="6f346-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6f346-118">Description</span></span>|  
|---------------|-----------------|  
|`policyType`|<span data-ttu-id="6f346-119">Ein erforderliches Zeichenfolgenattribut.</span><span class="sxs-lookup"><span data-stu-id="6f346-119">A required String attribute.</span></span><br /><br /> <span data-ttu-id="6f346-120">Das Windows Communication Foundation (WCF)-Zugriffs Steuerungsmodell unterstützt die Bereitstellung einer Gruppe von Autorisierungs Richtlinien als Typen.</span><span class="sxs-lookup"><span data-stu-id="6f346-120">The Windows Communication Foundation (WCF) access control model supports provisioning a set of authorization policies as types.</span></span> <span data-ttu-id="6f346-121">Dieses Attribut gibt eine Autorisierungsrichtlinie an, die die Transformation einer Gruppe von Eingabeansprüchen in eine andere Gruppe von Eingabeansprüchen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="6f346-121">This attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="6f346-122">Die Zugriffssteuerung kann basierend darauf gewährt oder verweigert werden.</span><span class="sxs-lookup"><span data-stu-id="6f346-122">Access control can be granted or denied based on that.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6f346-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6f346-123">Child Elements</span></span>  
 <span data-ttu-id="6f346-124">Keine</span><span class="sxs-lookup"><span data-stu-id="6f346-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6f346-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6f346-125">Parent Elements</span></span>  
  
|<span data-ttu-id="6f346-126">Element</span><span class="sxs-lookup"><span data-stu-id="6f346-126">Element</span></span>|<span data-ttu-id="6f346-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6f346-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6f346-128">\<authorizationPolicies></span><span class="sxs-lookup"><span data-stu-id="6f346-128">\<authorizationPolicies></span></span>](authorizationpolicies.md)|<span data-ttu-id="6f346-129">Gibt eine Auflistung von Autorisierungsrichtlinientypen an.</span><span class="sxs-lookup"><span data-stu-id="6f346-129">Specifies a collection of authorization policy types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f346-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6f346-130">Remarks</span></span>  
 <span data-ttu-id="6f346-131">Jede Autorisierungsrichtlinie enthält ein einziges erforderliches `policyType`-Attribut, bei dem es sich um eine Zeichenfolge handelt.</span><span class="sxs-lookup"><span data-stu-id="6f346-131">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="6f346-132">Das Attribut gibt eine Autorisierungsrichtlinie an, die die Transformation einer Gruppe von Eingabeansprüchen in eine andere Gruppe von Eingabeansprüchen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="6f346-132">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="6f346-133">Die Zugriffssteuerung kann basierend darauf gewährt oder verweigert werden.</span><span class="sxs-lookup"><span data-stu-id="6f346-133">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="6f346-134">Weitere Informationen zur Funktionsweise von Autorisierungs Richtlinien finden <xref:System.IdentityModel.Policy.IAuthorizationPolicy> Sie unter und [Autorisierungs Richtlinien](../../../wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="6f346-134">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f346-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6f346-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [<span data-ttu-id="6f346-136">Zugriffsautorisierung für Dienstvorgänge</span><span class="sxs-lookup"><span data-stu-id="6f346-136">Authorizing Access to Service Operations</span></span>](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="6f346-137">Vorgehensweise: Erstellen eines benutzerdefinierten Autorisierungs-Managers für einen Dienst</span><span class="sxs-lookup"><span data-stu-id="6f346-137">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="6f346-138">\<add></span><span class="sxs-lookup"><span data-stu-id="6f346-138">\<add></span></span>](add-of-authorizationpolicies.md)
- [<span data-ttu-id="6f346-139">Autorisierungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="6f346-139">Authorization Policy</span></span>](../../../wcf/samples/authorization-policy.md)
