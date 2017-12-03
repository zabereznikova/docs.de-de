---
title: dataContractSerializer
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a64f5ae4573efbd8c0f7d622e6b94b7786585bb1
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="datacontractserializer"></a><span data-ttu-id="eb3fb-102">dataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="eb3fb-102">dataContractSerializer</span></span>
<span data-ttu-id="eb3fb-103">Enthält Konfigurationsdaten für den <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="eb3fb-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="eb3fb-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="eb3fb-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="eb3fb-105">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="eb3fb-105">\<behaviors></span></span>  
<span data-ttu-id="eb3fb-106">\<EndpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="eb3fb-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="eb3fb-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="eb3fb-107">\<behavior></span></span>  
<span data-ttu-id="eb3fb-108">\<"DataContractSerializer" ></span><span class="sxs-lookup"><span data-stu-id="eb3fb-108">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb3fb-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="eb3fb-109">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"  
      maxItemsInObjectGraph="Integer" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eb3fb-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="eb3fb-110">Attributes and Elements</span></span>  
 <span data-ttu-id="eb3fb-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="eb3fb-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eb3fb-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="eb3fb-112">Attributes</span></span>  
  
|<span data-ttu-id="eb3fb-113">Element</span><span class="sxs-lookup"><span data-stu-id="eb3fb-113">Element</span></span>|<span data-ttu-id="eb3fb-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eb3fb-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="eb3fb-115">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="eb3fb-115">ignoreExtensionDataObject</span></span>|<span data-ttu-id="eb3fb-116">Ein boolescher Wert ab, der angibt, ob vom Endpunkt bereitgestellte Daten ignoriert werden sollen, wenn dieser serialisiert oder deserialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="eb3fb-116">A Boolean value that specifies whether to ignore data supplied by the endpoint, when it is being serialized or deserialized.</span></span>|  
|<span data-ttu-id="eb3fb-117">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="eb3fb-117">maxItemsInObjectGraph</span></span>|<span data-ttu-id="eb3fb-118">Eine ganze Zahl, die die maximale Anzahl der zu serialisierenden oder zu deserialisierenden Elemente angibt.</span><span class="sxs-lookup"><span data-stu-id="eb3fb-118">An integer that specifies the maximum number of items to serialize or deserialize.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eb3fb-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="eb3fb-119">Child Elements</span></span>  
 <span data-ttu-id="eb3fb-120">Keine</span><span class="sxs-lookup"><span data-stu-id="eb3fb-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eb3fb-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="eb3fb-121">Parent Elements</span></span>  
  
|<span data-ttu-id="eb3fb-122">Element</span><span class="sxs-lookup"><span data-stu-id="eb3fb-122">Element</span></span>|<span data-ttu-id="eb3fb-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eb3fb-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eb3fb-124">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="eb3fb-124">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="eb3fb-125">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="eb3fb-125">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eb3fb-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eb3fb-126">Remarks</span></span>  
 <span data-ttu-id="eb3fb-127">Weitere Informationen zu bekannten Typen finden Sie in der <xref:System.Runtime.Serialization.DataContractSerializer>-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="eb3fb-127">See the <xref:System.Runtime.Serialization.DataContractSerializer> documentation for more information about known types.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="eb3fb-128">Das `<dataContractSerializer>`-Verhaltenselement sollte, wenn vorhanden, in der Konfigurationsdatei immer vor dem `<enableWebScript>`-Verhaltenselement angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="eb3fb-128">The `<dataContractSerializer>` behavior element (if present) should always appear before the `<enableWebScript>` behavior element in the configuration file.</span></span> <span data-ttu-id="eb3fb-129">Andernfalls ist das resultierende Verhalten nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="eb3fb-129">Otherwise, the resulting behavior is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb3fb-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eb3fb-130">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>  
 <xref:System.ServiceModel.Configuration.DataContractSerializerElement>  
 [<span data-ttu-id="eb3fb-131">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="eb3fb-131">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="eb3fb-132">Die Datenübertragung und Serialisierung</span><span class="sxs-lookup"><span data-stu-id="eb3fb-132">Data Transfer and Serialization</span></span>](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
