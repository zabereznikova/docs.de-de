---
title: <useRequestHeadersForMetadataAddress>
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: a323e6da0eb173e303d70cc3b7309b898a805573
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172813"
---
# \<useRequestHeadersForMetadataAddress>

<span data-ttu-id="73a43-101">Ermöglicht das Abrufen von Metadatenadressinformationen aus Anforderungsnachrichtenheadern.</span><span class="sxs-lookup"><span data-stu-id="73a43-101">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<useRequestHeadersForMetadataAddress>**  
  
## <a name="syntax"></a><span data-ttu-id="73a43-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="73a43-102">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="73a43-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="73a43-103">Attributes and Elements</span></span>  

 <span data-ttu-id="73a43-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="73a43-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="73a43-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="73a43-105">Attributes</span></span>  

 <span data-ttu-id="73a43-106">Keine</span><span class="sxs-lookup"><span data-stu-id="73a43-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="73a43-107">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="73a43-107">Child Elements</span></span>  
  
|<span data-ttu-id="73a43-108">Element</span><span class="sxs-lookup"><span data-stu-id="73a43-108">Element</span></span>|<span data-ttu-id="73a43-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="73a43-109">Description</span></span>|  
|-------------|-----------------|  
|[\<defaultPorts>](defaultports.md)|<span data-ttu-id="73a43-110">Eine Auflistung von Standardports mit den Standardkommunikationsendpunkten, die von der Clientanwendung überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="73a43-110">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="73a43-111">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="73a43-111">Parent Elements</span></span>  
  
|<span data-ttu-id="73a43-112">Element</span><span class="sxs-lookup"><span data-stu-id="73a43-112">Element</span></span>|<span data-ttu-id="73a43-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="73a43-113">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="73a43-114">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="73a43-114">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="73a43-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="73a43-115">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
