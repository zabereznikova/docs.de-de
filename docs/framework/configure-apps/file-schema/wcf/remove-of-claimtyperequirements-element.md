---
title: <remove> des <claimTypeRequirements>-Elements
ms.date: 03/30/2017
ms.assetid: 8ef05bc4-1950-4ee4-95c5-1c6a394eff7e
ms.openlocfilehash: 84f4208d3f4581cf7e8c4455bf3f5d78f7e13b9f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400000"
---
# <a name="remove-of-claimtyperequirements-element"></a><span data-ttu-id="0b666-102">\<remove> des \<claimTypeRequirements>-Elements</span><span class="sxs-lookup"><span data-stu-id="0b666-102">\<remove> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="0b666-103">Gibt die Typen von Ansprüchen an, die in den verbundenen Anmeldeinformationen entfernt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0b666-103">Specifies the types of claims to be removed in the federated credential.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**  
  
## <a name="syntax"></a><span data-ttu-id="0b666-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0b666-104">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <remove claimType="URI" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0b666-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0b666-105">Attributes and Elements</span></span>  
 <span data-ttu-id="0b666-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0b666-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0b666-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="0b666-107">Attributes</span></span>  
  
|<span data-ttu-id="0b666-108">attribute</span><span class="sxs-lookup"><span data-stu-id="0b666-108">Attribute</span></span>|<span data-ttu-id="0b666-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0b666-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0b666-110">claimType</span><span class="sxs-lookup"><span data-stu-id="0b666-110">claimType</span></span>|<span data-ttu-id="0b666-111">Ein URI, der den Typ eines zu entfernenden Anspruchs definiert.</span><span class="sxs-lookup"><span data-stu-id="0b666-111">A URI that defines the type of a claim to be removed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0b666-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0b666-112">Child Elements</span></span>  
 <span data-ttu-id="0b666-113">Keine</span><span class="sxs-lookup"><span data-stu-id="0b666-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0b666-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0b666-114">Parent Elements</span></span>  
  
|<span data-ttu-id="0b666-115">Element</span><span class="sxs-lookup"><span data-stu-id="0b666-115">Element</span></span>|<span data-ttu-id="0b666-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0b666-116">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-for-message.md)|<span data-ttu-id="0b666-117">Gibt eine Auflistung von erforderlichen Anspruchstypen an.</span><span class="sxs-lookup"><span data-stu-id="0b666-117">Specifies a collection of required claim types.</span></span> <span data-ttu-id="0b666-118">Jedes Element ist vom Typ <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="0b666-118">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="0b666-119">In einem verbundenen Szenario legen Dienste die Anforderungen für eingehende Anmeldeinformationen fest.</span><span class="sxs-lookup"><span data-stu-id="0b666-119">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="0b666-120">Zum Beispiel müssen die eingehenden Anmeldeinformationen einen bestimmten Satz an Anspruchstypen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="0b666-120">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="0b666-121">Jedes Element in dieser Auflistung gibt die Typen der erforderlichen und optionalen Ansprüche an, die in verbundenen Anmeldeinformationen vorhanden sein sollen.</span><span class="sxs-lookup"><span data-stu-id="0b666-121">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0b666-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0b666-122">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
