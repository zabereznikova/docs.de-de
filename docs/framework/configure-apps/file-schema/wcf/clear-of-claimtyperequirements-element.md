---
title: <clear> des <claimTypeRequirements>-Elements
ms.date: 03/30/2017
ms.assetid: ef42fde7-f292-4610-9111-9fea382c3b5f
ms.openlocfilehash: 01f101f7d0dd5da6a834a4ffb2c7e09df0e23cd8
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400525"
---
# <a name="clear-of-claimtyperequirements-element"></a><span data-ttu-id="d450a-102">\<clear> des \<claimTypeRequirements>-Elements</span><span class="sxs-lookup"><span data-stu-id="d450a-102">\<clear> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="d450a-103">Gibt an, dass alle Anspruchstypen in den verbundenen Anmeldeinformationen entfernt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d450a-103">Specifies that all the claim types to be removed in the federated credential.</span></span> <span data-ttu-id="d450a-104">Dadurch wird sichergestellt, dass die Auflistung beim Starten leer ist.</span><span class="sxs-lookup"><span data-stu-id="d450a-104">This ensures that the collection starts empty.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**  
  
## <a name="syntax"></a><span data-ttu-id="d450a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d450a-105">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <clear />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d450a-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d450a-106">Attributes and Elements</span></span>  
 <span data-ttu-id="d450a-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d450a-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d450a-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="d450a-108">Attributes</span></span>  
 <span data-ttu-id="d450a-109">Keine</span><span class="sxs-lookup"><span data-stu-id="d450a-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d450a-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d450a-110">Child Elements</span></span>  
 <span data-ttu-id="d450a-111">Keine.</span><span class="sxs-lookup"><span data-stu-id="d450a-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d450a-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d450a-112">Parent Elements</span></span>  
  
|<span data-ttu-id="d450a-113">Element</span><span class="sxs-lookup"><span data-stu-id="d450a-113">Element</span></span>|<span data-ttu-id="d450a-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d450a-114">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-for-message.md)|<span data-ttu-id="d450a-115">Gibt eine Auflistung von erforderlichen Anspruchstypen an.</span><span class="sxs-lookup"><span data-stu-id="d450a-115">Specifies a collection of required claim types.</span></span> <span data-ttu-id="d450a-116">Jedes Element ist vom Typ <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="d450a-116">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="d450a-117">In einem verbundenen Szenario legen Dienste die Anforderungen für eingehende Anmeldeinformationen fest.</span><span class="sxs-lookup"><span data-stu-id="d450a-117">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="d450a-118">Zum Beispiel müssen die eingehenden Anmeldeinformationen einen bestimmten Satz an Anspruchstypen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="d450a-118">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="d450a-119">Jedes Element in dieser Auflistung gibt die Typen der erforderlichen und optionalen Ansprüche an, die in verbundenen Anmeldeinformationen vorhanden sein sollen.</span><span class="sxs-lookup"><span data-stu-id="d450a-119">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d450a-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d450a-120">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
