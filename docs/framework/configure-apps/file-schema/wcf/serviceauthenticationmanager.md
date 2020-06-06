---
title: <serviceAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: cc5ebcf36a10e88d48ed14f1f10dac6396d7b242
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399705"
---
# \<serviceAuthenticationManager>
<span data-ttu-id="85fff-101">Stellt ein Workflowkonfigurationselement bereit, das die Gültigkeit einer Übertragung, Meldung oder eines Absenders auf Dienstebene festlegt.</span><span class="sxs-lookup"><span data-stu-id="85fff-101">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceAuthenticationManager>**  
  
## <a name="syntax"></a><span data-ttu-id="85fff-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="85fff-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="85fff-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="85fff-103">Attributes and Elements</span></span>  
 <span data-ttu-id="85fff-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="85fff-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="85fff-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="85fff-105">Attributes</span></span>  
  
|<span data-ttu-id="85fff-106">attribute</span><span class="sxs-lookup"><span data-stu-id="85fff-106">Attribute</span></span>|<span data-ttu-id="85fff-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="85fff-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="85fff-108">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="85fff-108">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="85fff-109">Eine Zeichenfolge, die den Typ der Authentifizierungsrichtlinie für das aktuelle Verhalten angibt.</span><span class="sxs-lookup"><span data-stu-id="85fff-109">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="85fff-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="85fff-110">Child Elements</span></span>  
 <span data-ttu-id="85fff-111">Keine</span><span class="sxs-lookup"><span data-stu-id="85fff-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="85fff-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="85fff-112">Parent Elements</span></span>  
  
|<span data-ttu-id="85fff-113">Element</span><span class="sxs-lookup"><span data-stu-id="85fff-113">Element</span></span>|<span data-ttu-id="85fff-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="85fff-114">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="85fff-115">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="85fff-115">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="85fff-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="85fff-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
