---
title: '&lt;add&gt; von &lt;transportConfigurationType&gt;'
ms.date: 03/30/2017
ms.assetid: 03d79db9-571d-4534-acef-d05e5467b257
ms.openlocfilehash: 1079b25ce137dc89fc31f46a11f3720486462021
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149136"
---
# <a name="ltaddgt-of-lttransportconfigurationtypegt"></a><span data-ttu-id="94f45-102">&lt;add&gt; von &lt;transportConfigurationType&gt;</span><span class="sxs-lookup"><span data-stu-id="94f45-102">&lt;add&gt; of &lt;transportConfigurationType&gt;</span></span>
<span data-ttu-id="94f45-103">Dieses Element ist ein Schlüssel-Wert-Paar, das den Typ eines bestimmten Transports identifiziert.</span><span class="sxs-lookup"><span data-stu-id="94f45-103">This element is a key/value pair, which identifies the type of a particular transport.</span></span>  
  
 <span data-ttu-id="94f45-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="94f45-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="94f45-105">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="94f45-105">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="94f45-106">\<TransportConfigurationTypes ></span><span class="sxs-lookup"><span data-stu-id="94f45-106">\<transportConfigurationTypes></span></span>  
<span data-ttu-id="94f45-107">\<add></span><span class="sxs-lookup"><span data-stu-id="94f45-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94f45-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="94f45-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="94f45-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="94f45-109">Attributes and Elements</span></span>  
 <span data-ttu-id="94f45-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="94f45-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="94f45-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="94f45-111">Attributes</span></span>  
  
|<span data-ttu-id="94f45-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="94f45-112">Attribute</span></span>|<span data-ttu-id="94f45-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="94f45-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="94f45-114">Name</span><span class="sxs-lookup"><span data-stu-id="94f45-114">name</span></span>|<span data-ttu-id="94f45-115">Erforderliches Zeichenfolgeattribut.</span><span class="sxs-lookup"><span data-stu-id="94f45-115">Required String attribute.</span></span><br /><br /> <span data-ttu-id="94f45-116">Enthält einen benutzerdefinierten Schlüssel, mit dem der Transporttyp eindeutig identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="94f45-116">Contains a user-defined key that uniquely identifies the transport type.</span></span>|  
|<span data-ttu-id="94f45-117">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="94f45-117">transportConfigurationType</span></span>|<span data-ttu-id="94f45-118">Eine Zeichenfolge, die den Typ enthält, mit dem der Transport implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="94f45-118">A string that contains the type that implements the specific transport.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="94f45-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="94f45-119">Child Elements</span></span>  
 <span data-ttu-id="94f45-120">Keine</span><span class="sxs-lookup"><span data-stu-id="94f45-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="94f45-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="94f45-121">Parent Elements</span></span>  
  
|<span data-ttu-id="94f45-122">Element</span><span class="sxs-lookup"><span data-stu-id="94f45-122">Element</span></span>|<span data-ttu-id="94f45-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="94f45-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="94f45-124">\<TransportConfigurationTypes ></span><span class="sxs-lookup"><span data-stu-id="94f45-124">\<transportConfigurationTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transportconfigurationtypes.md)|<span data-ttu-id="94f45-125">Eine Auflistung von Typen, die den Transport implementieren.</span><span class="sxs-lookup"><span data-stu-id="94f45-125">A collection of types that implement the specific transport.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="94f45-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="94f45-126">Example</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="net.udp"
         transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="see-also"></a><span data-ttu-id="94f45-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94f45-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElement>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 [<span data-ttu-id="94f45-128">Hosting</span><span class="sxs-lookup"><span data-stu-id="94f45-128">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
