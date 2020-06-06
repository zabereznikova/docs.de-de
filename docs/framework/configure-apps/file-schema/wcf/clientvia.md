---
title: <clientVia>
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: a1c2ee68fb039e24e1462148cb52daf1bb57f8ed
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398110"
---
# \<clientVia>
<span data-ttu-id="0e1f0-101">Gibt den URI an, für den der Transportkanal erstellt werden sollte.</span><span class="sxs-lookup"><span data-stu-id="0e1f0-101">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="0e1f0-102">Weitere Informationen finden Sie unter <xref:System.ServiceModel.Description.ClientViaBehavior>.</span><span class="sxs-lookup"><span data-stu-id="0e1f0-102">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientVia>**  
  
## <a name="syntax"></a><span data-ttu-id="0e1f0-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="0e1f0-103">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0e1f0-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0e1f0-104">Attributes and Elements</span></span>  
 <span data-ttu-id="0e1f0-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0e1f0-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0e1f0-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="0e1f0-106">Attributes</span></span>  
  
|<span data-ttu-id="0e1f0-107">attribute</span><span class="sxs-lookup"><span data-stu-id="0e1f0-107">Attribute</span></span>|<span data-ttu-id="0e1f0-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0e1f0-108">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="0e1f0-109">Eine Zeichenfolge, die einen URI angibt, der auf die Route für eine Nachricht verweist.</span><span class="sxs-lookup"><span data-stu-id="0e1f0-109">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0e1f0-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0e1f0-110">Child Elements</span></span>  
 <span data-ttu-id="0e1f0-111">Keine</span><span class="sxs-lookup"><span data-stu-id="0e1f0-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0e1f0-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0e1f0-112">Parent Elements</span></span>  
  
|<span data-ttu-id="0e1f0-113">Element</span><span class="sxs-lookup"><span data-stu-id="0e1f0-113">Element</span></span>|<span data-ttu-id="0e1f0-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e1f0-114">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="0e1f0-115">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="0e1f0-115">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0e1f0-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0e1f0-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
