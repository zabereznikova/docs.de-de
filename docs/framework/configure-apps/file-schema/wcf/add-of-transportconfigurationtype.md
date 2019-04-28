---
title: <add> von <transportConfigurationType>
ms.date: 03/30/2017
ms.assetid: 03d79db9-571d-4534-acef-d05e5467b257
ms.openlocfilehash: c71a58b13e89bedb5eed24d784c82fb1525f7625
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701436"
---
# <a name="add-of-transportconfigurationtype"></a><span data-ttu-id="034a8-102">\<add> of \<transportConfigurationType></span><span class="sxs-lookup"><span data-stu-id="034a8-102">\<add> of \<transportConfigurationType></span></span>
<span data-ttu-id="034a8-103">Dieses Element ist ein Schlüssel-Wert-Paar, das den Typ eines bestimmten Transports identifiziert.</span><span class="sxs-lookup"><span data-stu-id="034a8-103">This element is a key/value pair, which identifies the type of a particular transport.</span></span>  
  
 <span data-ttu-id="034a8-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="034a8-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="034a8-105">\<ServiceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="034a8-105">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="034a8-106">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="034a8-106">\<transportConfigurationTypes></span></span>  
<span data-ttu-id="034a8-107">\<add></span><span class="sxs-lookup"><span data-stu-id="034a8-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="034a8-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="034a8-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="034a8-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="034a8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="034a8-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="034a8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="034a8-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="034a8-111">Attributes</span></span>  
  
|<span data-ttu-id="034a8-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="034a8-112">Attribute</span></span>|<span data-ttu-id="034a8-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="034a8-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="034a8-114">Name</span><span class="sxs-lookup"><span data-stu-id="034a8-114">name</span></span>|<span data-ttu-id="034a8-115">Erforderliches Zeichenfolgeattribut.</span><span class="sxs-lookup"><span data-stu-id="034a8-115">Required String attribute.</span></span><br /><br /> <span data-ttu-id="034a8-116">Enthält einen benutzerdefinierten Schlüssel, mit dem der Transporttyp eindeutig identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="034a8-116">Contains a user-defined key that uniquely identifies the transport type.</span></span>|  
|<span data-ttu-id="034a8-117">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="034a8-117">transportConfigurationType</span></span>|<span data-ttu-id="034a8-118">Eine Zeichenfolge, die den Typ enthält, mit dem der Transport implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="034a8-118">A string that contains the type that implements the specific transport.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="034a8-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="034a8-119">Child Elements</span></span>  
 <span data-ttu-id="034a8-120">Keiner</span><span class="sxs-lookup"><span data-stu-id="034a8-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="034a8-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="034a8-121">Parent Elements</span></span>  
  
|<span data-ttu-id="034a8-122">Element</span><span class="sxs-lookup"><span data-stu-id="034a8-122">Element</span></span>|<span data-ttu-id="034a8-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="034a8-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="034a8-124">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="034a8-124">\<transportConfigurationTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transportconfigurationtypes.md)|<span data-ttu-id="034a8-125">Eine Auflistung von Typen, die den Transport implementieren.</span><span class="sxs-lookup"><span data-stu-id="034a8-125">A collection of types that implement the specific transport.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="034a8-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="034a8-126">Example</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="net.udp"
         transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="see-also"></a><span data-ttu-id="034a8-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="034a8-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="034a8-128">Hosting</span><span class="sxs-lookup"><span data-stu-id="034a8-128">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
