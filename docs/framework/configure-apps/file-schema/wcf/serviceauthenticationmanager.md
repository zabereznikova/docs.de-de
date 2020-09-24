---
title: <serviceAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: a7c1e06c74bd3ba62d52ef833b8ffb6a8fd594fb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167170"
---
# \<serviceAuthenticationManager>

<span data-ttu-id="f0cda-101">Stellt ein Workflowkonfigurationselement bereit, das die Gültigkeit einer Übertragung, Meldung oder eines Absenders auf Dienstebene festlegt.</span><span class="sxs-lookup"><span data-stu-id="f0cda-101">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceAuthenticationManager>**  
  
## <a name="syntax"></a><span data-ttu-id="f0cda-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0cda-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f0cda-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f0cda-103">Attributes and Elements</span></span>  

 <span data-ttu-id="f0cda-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f0cda-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f0cda-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="f0cda-105">Attributes</span></span>  
  
|<span data-ttu-id="f0cda-106">attribute</span><span class="sxs-lookup"><span data-stu-id="f0cda-106">Attribute</span></span>|<span data-ttu-id="f0cda-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f0cda-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f0cda-108">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="f0cda-108">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="f0cda-109">Eine Zeichenfolge, die den Typ der Authentifizierungsrichtlinie für das aktuelle Verhalten angibt.</span><span class="sxs-lookup"><span data-stu-id="f0cda-109">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f0cda-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f0cda-110">Child Elements</span></span>  

 <span data-ttu-id="f0cda-111">Keine</span><span class="sxs-lookup"><span data-stu-id="f0cda-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f0cda-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f0cda-112">Parent Elements</span></span>  
  
|<span data-ttu-id="f0cda-113">Element</span><span class="sxs-lookup"><span data-stu-id="f0cda-113">Element</span></span>|<span data-ttu-id="f0cda-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f0cda-114">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="f0cda-115">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="f0cda-115">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f0cda-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f0cda-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
