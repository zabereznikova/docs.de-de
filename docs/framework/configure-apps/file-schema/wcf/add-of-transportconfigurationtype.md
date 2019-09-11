---
title: <add> von <transportConfigurationType>
ms.date: 03/30/2017
ms.assetid: 03d79db9-571d-4534-acef-d05e5467b257
ms.openlocfilehash: adf4cd7f02db6535c5950443d09476a9a5ff63fb
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850319"
---
# <a name="add-of-transportconfigurationtype"></a><span data-ttu-id="fd992-102">\<Fügen Sie > \<von transportconfigurationtype hinzu ></span><span class="sxs-lookup"><span data-stu-id="fd992-102">\<add> of \<transportConfigurationType></span></span>
<span data-ttu-id="fd992-103">Dieses Element ist ein Schlüssel-Wert-Paar, das den Typ eines bestimmten Transports identifiziert.</span><span class="sxs-lookup"><span data-stu-id="fd992-103">This element is a key/value pair, which identifies the type of a particular transport.</span></span>  
  
<span data-ttu-id="fd992-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fd992-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fd992-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="fd992-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="fd992-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<servicehoststingenvironment->** ](servicehostingenvironment.md)</span><span class="sxs-lookup"><span data-stu-id="fd992-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)</span></span>\
<span data-ttu-id="fd992-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<transportconfigurationtypes->** ](transportconfigurationtypes.md)</span><span class="sxs-lookup"><span data-stu-id="fd992-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<transportConfigurationTypes>**](transportconfigurationtypes.md)</span></span>\
<span data-ttu-id="fd992-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> Hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="fd992-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd992-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="fd992-109">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fd992-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fd992-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fd992-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fd992-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fd992-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="fd992-112">Attributes</span></span>  
  
|<span data-ttu-id="fd992-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="fd992-113">Attribute</span></span>|<span data-ttu-id="fd992-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fd992-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fd992-115">NAME</span><span class="sxs-lookup"><span data-stu-id="fd992-115">name</span></span>|<span data-ttu-id="fd992-116">Erforderliches Zeichenfolgeattribut.</span><span class="sxs-lookup"><span data-stu-id="fd992-116">Required String attribute.</span></span><br /><br /> <span data-ttu-id="fd992-117">Enthält einen benutzerdefinierten Schlüssel, mit dem der Transporttyp eindeutig identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="fd992-117">Contains a user-defined key that uniquely identifies the transport type.</span></span>|  
|<span data-ttu-id="fd992-118">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="fd992-118">transportConfigurationType</span></span>|<span data-ttu-id="fd992-119">Eine Zeichenfolge, die den Typ enthält, mit dem der Transport implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="fd992-119">A string that contains the type that implements the specific transport.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fd992-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fd992-120">Child Elements</span></span>  
 <span data-ttu-id="fd992-121">None</span><span class="sxs-lookup"><span data-stu-id="fd992-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fd992-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fd992-122">Parent Elements</span></span>  
  
|<span data-ttu-id="fd992-123">Element</span><span class="sxs-lookup"><span data-stu-id="fd992-123">Element</span></span>|<span data-ttu-id="fd992-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fd992-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fd992-125">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="fd992-125">\<transportConfigurationTypes></span></span>](transportconfigurationtypes.md)|<span data-ttu-id="fd992-126">Eine Auflistung von Typen, die den Transport implementieren.</span><span class="sxs-lookup"><span data-stu-id="fd992-126">A collection of types that implement the specific transport.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="fd992-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fd992-127">Example</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="net.udp"
         transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="see-also"></a><span data-ttu-id="fd992-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd992-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="fd992-129">Hosting</span><span class="sxs-lookup"><span data-stu-id="fd992-129">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
