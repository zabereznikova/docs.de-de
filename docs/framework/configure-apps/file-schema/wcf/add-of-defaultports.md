---
title: <add> von <defaultPorts>
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: f5de2aa897a3bc37d08932451a2c7b94bc603b9e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400642"
---
# <a name="add-of-defaultports"></a><span data-ttu-id="09d7f-102">\<Fügen Sie > \<von defaultports hinzu ></span><span class="sxs-lookup"><span data-stu-id="09d7f-102">\<add> of \<defaultPorts></span></span>
<span data-ttu-id="09d7f-103">Ein Standardkommunikationsendpunkt, den die Clientanwendung überwacht.</span><span class="sxs-lookup"><span data-stu-id="09d7f-103">A default communications endpoint that the client application listens to.</span></span>  
  
<span data-ttu-id="09d7f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="09d7f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="09d7f-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="09d7f-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="09d7f-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="09d7f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="09d7f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceverhaltens>** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="09d7f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="09d7f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="09d7f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="09d7f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<useRequestHeadersForMetadataAddress >** ](userequestheadersformetadataaddress.md)</span><span class="sxs-lookup"><span data-stu-id="09d7f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<useRequestHeadersForMetadataAddress>**](userequestheadersformetadataaddress.md)</span></span>\
<span data-ttu-id="09d7f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<defaultports >** ](defaultports.md)</span><span class="sxs-lookup"><span data-stu-id="09d7f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultPorts>**](defaultports.md)</span></span>\
<span data-ttu-id="09d7f-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> Hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="09d7f-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09d7f-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="09d7f-112">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add port="Integer"
         scheme="String" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="09d7f-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="09d7f-113">Attributes and Elements</span></span>  
 <span data-ttu-id="09d7f-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="09d7f-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="09d7f-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="09d7f-115">Attributes</span></span>  
  
|<span data-ttu-id="09d7f-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="09d7f-116">Attribute</span></span>|<span data-ttu-id="09d7f-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="09d7f-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="09d7f-118">Port</span><span class="sxs-lookup"><span data-stu-id="09d7f-118">port</span></span>|<span data-ttu-id="09d7f-119">Eine ganze Zahl, die die Nummer des Standardkommunikationsports angibt.</span><span class="sxs-lookup"><span data-stu-id="09d7f-119">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="09d7f-120">scheme</span><span class="sxs-lookup"><span data-stu-id="09d7f-120">scheme</span></span>|<span data-ttu-id="09d7f-121">Eine Zeichenfolge, die die Gruppe von Protokolleinstellungen angibt, die einem Kommunikationsport zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="09d7f-121">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="09d7f-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="09d7f-122">Child Elements</span></span>  
 <span data-ttu-id="09d7f-123">Keine</span><span class="sxs-lookup"><span data-stu-id="09d7f-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="09d7f-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="09d7f-124">Parent Elements</span></span>  
  
|<span data-ttu-id="09d7f-125">Element</span><span class="sxs-lookup"><span data-stu-id="09d7f-125">Element</span></span>|<span data-ttu-id="09d7f-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="09d7f-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="09d7f-127">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="09d7f-127">\<defaultPorts></span></span>](defaultports.md)|<span data-ttu-id="09d7f-128">Eine Auflistung von Standardports mit den Standardkommunikationsendpunkten, die von der Clientanwendung überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="09d7f-128">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="09d7f-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="09d7f-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElement>
