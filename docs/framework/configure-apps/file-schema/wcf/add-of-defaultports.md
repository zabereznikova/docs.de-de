---
title: <add> von <defaultPorts>
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: f5de2aa897a3bc37d08932451a2c7b94bc603b9e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400642"
---
# <a name="add-of-defaultports"></a><span data-ttu-id="85f90-102">\<add> von \<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="85f90-102">\<add> of \<defaultPorts></span></span>
<span data-ttu-id="85f90-103">Ein Standardkommunikationsendpunkt, den die Clientanwendung überwacht.</span><span class="sxs-lookup"><span data-stu-id="85f90-103">A default communications endpoint that the client application listens to.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<useRequestHeadersForMetadataAddress>**](userequestheadersformetadataaddress.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultPorts>**](defaultports.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="85f90-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="85f90-104">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add port="Integer"
         scheme="String" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="85f90-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="85f90-105">Attributes and Elements</span></span>  
 <span data-ttu-id="85f90-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="85f90-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="85f90-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="85f90-107">Attributes</span></span>  
  
|<span data-ttu-id="85f90-108">attribute</span><span class="sxs-lookup"><span data-stu-id="85f90-108">Attribute</span></span>|<span data-ttu-id="85f90-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="85f90-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="85f90-110">port</span><span class="sxs-lookup"><span data-stu-id="85f90-110">port</span></span>|<span data-ttu-id="85f90-111">Eine ganze Zahl, die die Nummer des Standardkommunikationsports angibt.</span><span class="sxs-lookup"><span data-stu-id="85f90-111">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="85f90-112">scheme</span><span class="sxs-lookup"><span data-stu-id="85f90-112">scheme</span></span>|<span data-ttu-id="85f90-113">Eine Zeichenfolge, die die Gruppe von Protokolleinstellungen angibt, die einem Kommunikationsport zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="85f90-113">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="85f90-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="85f90-114">Child Elements</span></span>  
 <span data-ttu-id="85f90-115">Keine</span><span class="sxs-lookup"><span data-stu-id="85f90-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="85f90-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="85f90-116">Parent Elements</span></span>  
  
|<span data-ttu-id="85f90-117">Element</span><span class="sxs-lookup"><span data-stu-id="85f90-117">Element</span></span>|<span data-ttu-id="85f90-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="85f90-118">Description</span></span>|  
|-------------|-----------------|  
|[\<defaultPorts>](defaultports.md)|<span data-ttu-id="85f90-119">Eine Auflistung von Standardports mit den Standardkommunikationsendpunkten, die von der Clientanwendung überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="85f90-119">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="85f90-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="85f90-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElement>
