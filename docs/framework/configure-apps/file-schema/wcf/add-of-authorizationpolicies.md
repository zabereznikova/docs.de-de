---
title: <add> von <authorizationPolicies>
ms.date: 03/30/2017
ms.assetid: 613a03d8-4384-4556-bce2-8c23286c0bb0
ms.openlocfilehash: e2597bc51e788c919bfe3ce3422ae2911cc6b33b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400698"
---
# <a name="add-of-authorizationpolicies"></a><span data-ttu-id="6debd-102">\<add> von \<authorizationPolicies></span><span class="sxs-lookup"><span data-stu-id="6debd-102">\<add> of \<authorizationPolicies></span></span>
<span data-ttu-id="6debd-103">Gibt eine Autorisierungsrichtlinie für Anspruchstransformation an.</span><span class="sxs-lookup"><span data-stu-id="6debd-103">Specifies an authorization policy for claim transformation.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceAuthorization>**](serviceauthorization-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<authorizationPolicies>**](authorizationpolicies.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="6debd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6debd-104">Syntax</span></span>  
  
```xml  
<authorizationPolicies>
  <add policyType="String" />
</authorizationPolicies>
```  
  
## <a name="type"></a><span data-ttu-id="6debd-105">type</span><span class="sxs-lookup"><span data-stu-id="6debd-105">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6debd-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6debd-106">Attributes and Elements</span></span>  
 <span data-ttu-id="6debd-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6debd-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6debd-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="6debd-108">Attributes</span></span>  
  
|<span data-ttu-id="6debd-109">attribute</span><span class="sxs-lookup"><span data-stu-id="6debd-109">Attribute</span></span>|<span data-ttu-id="6debd-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6debd-110">Description</span></span>|  
|---------------|-----------------|  
|`policyType`|<span data-ttu-id="6debd-111">Ein erforderliches Zeichenfolgenattribut.</span><span class="sxs-lookup"><span data-stu-id="6debd-111">A required String attribute.</span></span><br /><br /> <span data-ttu-id="6debd-112">Das Windows Communication Foundation (WCF)-Zugriffs Steuerungsmodell unterstützt die Bereitstellung einer Gruppe von Autorisierungs Richtlinien als Typen.</span><span class="sxs-lookup"><span data-stu-id="6debd-112">The Windows Communication Foundation (WCF) access control model supports provisioning a set of authorization policies as types.</span></span> <span data-ttu-id="6debd-113">Dieses Attribut gibt eine Autorisierungsrichtlinie an, die die Transformation einer Gruppe von Eingabeansprüchen in eine andere Gruppe von Eingabeansprüchen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="6debd-113">This attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="6debd-114">Die Zugriffssteuerung kann basierend darauf gewährt oder verweigert werden.</span><span class="sxs-lookup"><span data-stu-id="6debd-114">Access control can be granted or denied based on that.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6debd-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6debd-115">Child Elements</span></span>  
 <span data-ttu-id="6debd-116">Keine</span><span class="sxs-lookup"><span data-stu-id="6debd-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6debd-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6debd-117">Parent Elements</span></span>  
  
|<span data-ttu-id="6debd-118">Element</span><span class="sxs-lookup"><span data-stu-id="6debd-118">Element</span></span>|<span data-ttu-id="6debd-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6debd-119">Description</span></span>|  
|-------------|-----------------|  
|[\<authorizationPolicies>](authorizationpolicies.md)|<span data-ttu-id="6debd-120">Gibt eine Auflistung von Autorisierungsrichtlinientypen an.</span><span class="sxs-lookup"><span data-stu-id="6debd-120">Specifies a collection of authorization policy types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6debd-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6debd-121">Remarks</span></span>  
 <span data-ttu-id="6debd-122">Jede Autorisierungsrichtlinie enthält ein einziges erforderliches `policyType`-Attribut, bei dem es sich um eine Zeichenfolge handelt.</span><span class="sxs-lookup"><span data-stu-id="6debd-122">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="6debd-123">Das Attribut gibt eine Autorisierungsrichtlinie an, die die Transformation einer Gruppe von Eingabeansprüchen in eine andere Gruppe von Eingabeansprüchen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="6debd-123">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="6debd-124">Die Zugriffssteuerung kann basierend darauf gewährt oder verweigert werden.</span><span class="sxs-lookup"><span data-stu-id="6debd-124">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="6debd-125">Weitere Informationen zur Funktionsweise von Autorisierungs Richtlinien finden Sie unter <xref:System.IdentityModel.Policy.IAuthorizationPolicy> und [Autorisierungs Richtlinien](../../../wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="6debd-125">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6debd-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6debd-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [<span data-ttu-id="6debd-127">Zugriffsautorisierung für Dienstvorgänge</span><span class="sxs-lookup"><span data-stu-id="6debd-127">Authorizing Access to Service Operations</span></span>](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="6debd-128">Vorgehensweise: Erstellen eines benutzerdefinierten Autorisierungs-Managers für einen Dienst</span><span class="sxs-lookup"><span data-stu-id="6debd-128">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [\<add>](add-of-authorizationpolicies.md)
- [<span data-ttu-id="6debd-129">Autorisierungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="6debd-129">Authorization Policy</span></span>](../../../wcf/samples/authorization-policy.md)
