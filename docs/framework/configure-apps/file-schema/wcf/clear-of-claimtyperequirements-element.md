---
title: <clear> des <claimTypeRequirements>-Elements
ms.date: 03/30/2017
ms.assetid: ef42fde7-f292-4610-9111-9fea382c3b5f
ms.openlocfilehash: 01f101f7d0dd5da6a834a4ffb2c7e09df0e23cd8
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400525"
---
# <a name="clear-of-claimtyperequirements-element"></a><span data-ttu-id="31f26-102">\<> von \<claimtyperequiations> Element löschen</span><span class="sxs-lookup"><span data-stu-id="31f26-102">\<clear> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="31f26-103">Gibt an, dass alle Anspruchstypen in den verbundenen Anmeldeinformationen entfernt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="31f26-103">Specifies that all the claim types to be removed in the federated credential.</span></span> <span data-ttu-id="31f26-104">Dadurch wird sichergestellt, dass die Auflistung beim Starten leer ist.</span><span class="sxs-lookup"><span data-stu-id="31f26-104">This ensures that the collection starts empty.</span></span>  
  
<span data-ttu-id="31f26-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="31f26-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="31f26-106">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="31f26-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="31f26-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="31f26-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="31f26-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<WSFederationHttpBinding->** ](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="31f26-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="31f26-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="31f26-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="31f26-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Sicherheits >** ](security-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="31f26-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="31f26-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Message >** ](message-element-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="31f26-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="31f26-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<claimtyperequirequirements->** ](claimtyperequirements-for-message.md)</span><span class="sxs-lookup"><span data-stu-id="31f26-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)</span></span>\
<span data-ttu-id="31f26-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Löschen >**</span><span class="sxs-lookup"><span data-stu-id="31f26-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31f26-114">Syntax</span><span class="sxs-lookup"><span data-stu-id="31f26-114">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <clear />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="31f26-115">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="31f26-115">Attributes and Elements</span></span>  
 <span data-ttu-id="31f26-116">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="31f26-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="31f26-117">Attribute</span><span class="sxs-lookup"><span data-stu-id="31f26-117">Attributes</span></span>  
 <span data-ttu-id="31f26-118">Keine</span><span class="sxs-lookup"><span data-stu-id="31f26-118">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="31f26-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="31f26-119">Child Elements</span></span>  
 <span data-ttu-id="31f26-120">Keine</span><span class="sxs-lookup"><span data-stu-id="31f26-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="31f26-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="31f26-121">Parent Elements</span></span>  
  
|<span data-ttu-id="31f26-122">Element</span><span class="sxs-lookup"><span data-stu-id="31f26-122">Element</span></span>|<span data-ttu-id="31f26-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="31f26-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="31f26-124">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="31f26-124">\<claimTypeRequirements></span></span>](claimtyperequirements-for-message.md)|<span data-ttu-id="31f26-125">Gibt eine Auflistung von erforderlichen Anspruchstypen an.</span><span class="sxs-lookup"><span data-stu-id="31f26-125">Specifies a collection of required claim types.</span></span> <span data-ttu-id="31f26-126">Jedes Element ist vom Typ <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="31f26-126">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="31f26-127">In einem verbundenen Szenario legen Dienste die Anforderungen für eingehende Anmeldeinformationen fest.</span><span class="sxs-lookup"><span data-stu-id="31f26-127">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="31f26-128">Zum Beispiel müssen die eingehenden Anmeldeinformationen einen bestimmten Satz an Anspruchstypen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="31f26-128">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="31f26-129">Jedes Element in dieser Auflistung gibt die Typen der erforderlichen und optionalen Ansprüche an, die in verbundenen Anmeldeinformationen vorhanden sein sollen.</span><span class="sxs-lookup"><span data-stu-id="31f26-129">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="31f26-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="31f26-130">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
