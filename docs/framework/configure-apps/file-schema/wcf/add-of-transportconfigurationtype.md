---
title: '&lt;add&gt; von &lt;transportConfigurationType&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03d79db9-571d-4534-acef-d05e5467b257
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2b52345ae30ab56a6f34d2aa46f9836d67555b15
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-lttransportconfigurationtypegt"></a><span data-ttu-id="caaf8-102">&lt;add&gt; von &lt;transportConfigurationType&gt;</span><span class="sxs-lookup"><span data-stu-id="caaf8-102">&lt;add&gt; of &lt;transportConfigurationType&gt;</span></span>
<span data-ttu-id="caaf8-103">Dieses Element ist ein Schlüssel-Wert-Paar, das den Typ eines bestimmten Transports identifiziert.</span><span class="sxs-lookup"><span data-stu-id="caaf8-103">This element is a key/value pair, which identifies the type of a particular transport.</span></span>  
  
 <span data-ttu-id="caaf8-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="caaf8-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="caaf8-105">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="caaf8-105">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="caaf8-106">\<TransportConfigurationTypes ></span><span class="sxs-lookup"><span data-stu-id="caaf8-106">\<transportConfigurationTypes></span></span>  
<span data-ttu-id="caaf8-107">\<add></span><span class="sxs-lookup"><span data-stu-id="caaf8-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="caaf8-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="caaf8-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>   
   <transportConfigurationTypes>  
      <add name="String"  
               transportConfigurationType="String"/>   
   </transportConfigurationTypes>  
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="caaf8-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="caaf8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="caaf8-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="caaf8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="caaf8-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="caaf8-111">Attributes</span></span>  
  
|<span data-ttu-id="caaf8-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="caaf8-112">Attribute</span></span>|<span data-ttu-id="caaf8-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="caaf8-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="caaf8-114">Name</span><span class="sxs-lookup"><span data-stu-id="caaf8-114">name</span></span>|<span data-ttu-id="caaf8-115">Erforderliches Zeichenfolgeattribut.</span><span class="sxs-lookup"><span data-stu-id="caaf8-115">Required String attribute.</span></span><br /><br /> <span data-ttu-id="caaf8-116">Enthält einen benutzerdefinierten Schlüssel, mit dem der Transporttyp eindeutig identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="caaf8-116">Contains a user-defined key that uniquely identifies the transport type.</span></span>|  
|<span data-ttu-id="caaf8-117">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="caaf8-117">transportConfigurationType</span></span>|<span data-ttu-id="caaf8-118">Eine Zeichenfolge, die den Typ enthält, mit dem der Transport implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="caaf8-118">A string that contains the type that implements the specific transport.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="caaf8-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="caaf8-119">Child Elements</span></span>  
 <span data-ttu-id="caaf8-120">Keiner</span><span class="sxs-lookup"><span data-stu-id="caaf8-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="caaf8-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="caaf8-121">Parent Elements</span></span>  
  
|<span data-ttu-id="caaf8-122">Element</span><span class="sxs-lookup"><span data-stu-id="caaf8-122">Element</span></span>|<span data-ttu-id="caaf8-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="caaf8-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="caaf8-124">\<TransportConfigurationTypes ></span><span class="sxs-lookup"><span data-stu-id="caaf8-124">\<transportConfigurationTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transportconfigurationtypes.md)|<span data-ttu-id="caaf8-125">Eine Auflistung von Typen, die den Transport implementieren.</span><span class="sxs-lookup"><span data-stu-id="caaf8-125">A collection of types that implement the specific transport.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="caaf8-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="caaf8-126">Example</span></span>  
  
```xml  
<serviceHostingEnvironment>   
   <transportConfigurationTypes>  
      <add name="net.udp"  
      transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />   
   </transportConfigurationTypes>  
</serviceHostingEnvironment>  
```  
  
## <a name="see-also"></a><span data-ttu-id="caaf8-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="caaf8-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElement>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 [<span data-ttu-id="caaf8-128">Hosting</span><span class="sxs-lookup"><span data-stu-id="caaf8-128">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
