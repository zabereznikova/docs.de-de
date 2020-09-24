---
title: <clientVia>
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: 5e62201a38dc4dc251996531a4af5f294dd2395f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151102"
---
# \<clientVia>

<span data-ttu-id="8e52c-101">Gibt den URI an, für den der Transportkanal erstellt werden sollte.</span><span class="sxs-lookup"><span data-stu-id="8e52c-101">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="8e52c-102">Weitere Informationen finden Sie unter <xref:System.ServiceModel.Description.ClientViaBehavior>.</span><span class="sxs-lookup"><span data-stu-id="8e52c-102">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientVia>**  
  
## <a name="syntax"></a><span data-ttu-id="8e52c-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="8e52c-103">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8e52c-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8e52c-104">Attributes and Elements</span></span>  

 <span data-ttu-id="8e52c-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8e52c-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8e52c-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="8e52c-106">Attributes</span></span>  
  
|<span data-ttu-id="8e52c-107">attribute</span><span class="sxs-lookup"><span data-stu-id="8e52c-107">Attribute</span></span>|<span data-ttu-id="8e52c-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8e52c-108">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="8e52c-109">Eine Zeichenfolge, die einen URI angibt, der auf die Route für eine Nachricht verweist.</span><span class="sxs-lookup"><span data-stu-id="8e52c-109">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8e52c-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8e52c-110">Child Elements</span></span>  

 <span data-ttu-id="8e52c-111">Keine</span><span class="sxs-lookup"><span data-stu-id="8e52c-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8e52c-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8e52c-112">Parent Elements</span></span>  
  
|<span data-ttu-id="8e52c-113">Element</span><span class="sxs-lookup"><span data-stu-id="8e52c-113">Element</span></span>|<span data-ttu-id="8e52c-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8e52c-114">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="8e52c-115">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="8e52c-115">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8e52c-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8e52c-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
