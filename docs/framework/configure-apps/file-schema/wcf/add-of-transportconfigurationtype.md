---
title: <add> von <transportConfigurationType>
ms.date: 03/30/2017
ms.assetid: 03d79db9-571d-4534-acef-d05e5467b257
ms.openlocfilehash: 9bef44ed39ee892080342058206f779b38fb460d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151154"
---
# <a name="add-of-transportconfigurationtype"></a><span data-ttu-id="4fd3c-102">\<add> von \<transportConfigurationType></span><span class="sxs-lookup"><span data-stu-id="4fd3c-102">\<add> of \<transportConfigurationType></span></span>

<span data-ttu-id="4fd3c-103">Dieses Element ist ein Schlüssel-Wert-Paar, das den Typ eines bestimmten Transports identifiziert.</span><span class="sxs-lookup"><span data-stu-id="4fd3c-103">This element is a key/value pair, which identifies the type of a particular transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<transportConfigurationTypes>**](transportconfigurationtypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="4fd3c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4fd3c-104">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4fd3c-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4fd3c-105">Attributes and Elements</span></span>  

 <span data-ttu-id="4fd3c-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4fd3c-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4fd3c-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="4fd3c-107">Attributes</span></span>  
  
|<span data-ttu-id="4fd3c-108">attribute</span><span class="sxs-lookup"><span data-stu-id="4fd3c-108">Attribute</span></span>|<span data-ttu-id="4fd3c-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4fd3c-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4fd3c-110">name</span><span class="sxs-lookup"><span data-stu-id="4fd3c-110">name</span></span>|<span data-ttu-id="4fd3c-111">Erforderliches Zeichenfolgeattribut.</span><span class="sxs-lookup"><span data-stu-id="4fd3c-111">Required String attribute.</span></span><br /><br /> <span data-ttu-id="4fd3c-112">Enthält einen benutzerdefinierten Schlüssel, mit dem der Transporttyp eindeutig identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="4fd3c-112">Contains a user-defined key that uniquely identifies the transport type.</span></span>|  
|<span data-ttu-id="4fd3c-113">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="4fd3c-113">transportConfigurationType</span></span>|<span data-ttu-id="4fd3c-114">Eine Zeichenfolge, die den Typ enthält, mit dem der Transport implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="4fd3c-114">A string that contains the type that implements the specific transport.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4fd3c-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4fd3c-115">Child Elements</span></span>  

 <span data-ttu-id="4fd3c-116">Keine</span><span class="sxs-lookup"><span data-stu-id="4fd3c-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4fd3c-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4fd3c-117">Parent Elements</span></span>  
  
|<span data-ttu-id="4fd3c-118">Element</span><span class="sxs-lookup"><span data-stu-id="4fd3c-118">Element</span></span>|<span data-ttu-id="4fd3c-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4fd3c-119">Description</span></span>|  
|-------------|-----------------|  
|[\<transportConfigurationTypes>](transportconfigurationtypes.md)|<span data-ttu-id="4fd3c-120">Eine Auflistung von Typen, die den Transport implementieren.</span><span class="sxs-lookup"><span data-stu-id="4fd3c-120">A collection of types that implement the specific transport.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4fd3c-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4fd3c-121">Example</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="net.udp"
         transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="see-also"></a><span data-ttu-id="4fd3c-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4fd3c-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="4fd3c-123">Hosting</span><span class="sxs-lookup"><span data-stu-id="4fd3c-123">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
