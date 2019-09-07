---
title: <serviceAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: cc5ebcf36a10e88d48ed14f1f10dac6396d7b242
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399705"
---
# <a name="serviceauthenticationmanager"></a><span data-ttu-id="0e34b-101">\<serviceAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="0e34b-101">\<serviceAuthenticationManager></span></span>
<span data-ttu-id="0e34b-102">Stellt ein Workflowkonfigurationselement bereit, das die Gültigkeit einer Übertragung, Meldung oder eines Absenders auf Dienstebene festlegt.</span><span class="sxs-lookup"><span data-stu-id="0e34b-102">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator.</span></span>  
  
<span data-ttu-id="0e34b-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0e34b-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0e34b-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="0e34b-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="0e34b-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="0e34b-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="0e34b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceverhaltens>** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="0e34b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="0e34b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="0e34b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="0e34b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<serviceauthenticationmanager->**</span><span class="sxs-lookup"><span data-stu-id="0e34b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceAuthenticationManager>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e34b-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="0e34b-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0e34b-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0e34b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="0e34b-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0e34b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0e34b-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="0e34b-112">Attributes</span></span>  
  
|<span data-ttu-id="0e34b-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="0e34b-113">Attribute</span></span>|<span data-ttu-id="0e34b-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e34b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0e34b-115">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="0e34b-115">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="0e34b-116">Eine Zeichenfolge, die den Typ der Authentifizierungsrichtlinie für das aktuelle Verhalten angibt.</span><span class="sxs-lookup"><span data-stu-id="0e34b-116">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0e34b-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0e34b-117">Child Elements</span></span>  
 <span data-ttu-id="0e34b-118">Keine</span><span class="sxs-lookup"><span data-stu-id="0e34b-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0e34b-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0e34b-119">Parent Elements</span></span>  
  
|<span data-ttu-id="0e34b-120">Element</span><span class="sxs-lookup"><span data-stu-id="0e34b-120">Element</span></span>|<span data-ttu-id="0e34b-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e34b-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0e34b-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="0e34b-122">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="0e34b-123">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="0e34b-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0e34b-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0e34b-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
