---
title: <clear> des <claimTypeRequirements>-Elements
ms.date: 03/30/2017
ms.assetid: ef42fde7-f292-4610-9111-9fea382c3b5f
ms.openlocfilehash: aa94a012da11bcec6fb5fe270ad9f3574f88e6d7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172904"
---
# <a name="clear-of-claimtyperequirements-element"></a><span data-ttu-id="44633-102">\<clear> des \<claimTypeRequirements>-Elements</span><span class="sxs-lookup"><span data-stu-id="44633-102">\<clear> of \<claimTypeRequirements> element</span></span>

<span data-ttu-id="44633-103">Gibt an, dass alle Anspruchstypen in den verbundenen Anmeldeinformationen entfernt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="44633-103">Specifies that all the claim types to be removed in the federated credential.</span></span> <span data-ttu-id="44633-104">Dadurch wird sichergestellt, dass die Auflistung beim Starten leer ist.</span><span class="sxs-lookup"><span data-stu-id="44633-104">This ensures that the collection starts empty.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**  
  
## <a name="syntax"></a><span data-ttu-id="44633-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="44633-105">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <clear />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="44633-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="44633-106">Attributes and Elements</span></span>  

 <span data-ttu-id="44633-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="44633-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="44633-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="44633-108">Attributes</span></span>  

 <span data-ttu-id="44633-109">Keine</span><span class="sxs-lookup"><span data-stu-id="44633-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="44633-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="44633-110">Child Elements</span></span>  

 <span data-ttu-id="44633-111">Keine</span><span class="sxs-lookup"><span data-stu-id="44633-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="44633-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="44633-112">Parent Elements</span></span>  
  
|<span data-ttu-id="44633-113">Element</span><span class="sxs-lookup"><span data-stu-id="44633-113">Element</span></span>|<span data-ttu-id="44633-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="44633-114">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-for-message.md)|<span data-ttu-id="44633-115">Gibt eine Auflistung von erforderlichen Anspruchstypen an.</span><span class="sxs-lookup"><span data-stu-id="44633-115">Specifies a collection of required claim types.</span></span> <span data-ttu-id="44633-116">Jedes Element ist vom Typ <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="44633-116">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="44633-117">In einem verbundenen Szenario legen Dienste die Anforderungen für eingehende Anmeldeinformationen fest.</span><span class="sxs-lookup"><span data-stu-id="44633-117">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="44633-118">Zum Beispiel müssen die eingehenden Anmeldeinformationen einen bestimmten Satz an Anspruchstypen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="44633-118">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="44633-119">Jedes Element in dieser Auflistung gibt die Typen der erforderlichen und optionalen Ansprüche an, die in verbundenen Anmeldeinformationen vorhanden sein sollen.</span><span class="sxs-lookup"><span data-stu-id="44633-119">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="44633-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="44633-120">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
