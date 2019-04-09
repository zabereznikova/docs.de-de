---
title: dataContractSerializer
ms.date: 03/30/2017
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
ms.openlocfilehash: 8ba16d9cc30b07d3e6b0924e6013ec01443867d4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59139047"
---
# <a name="datacontractserializer"></a><span data-ttu-id="5cbe1-102">dataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="5cbe1-102">dataContractSerializer</span></span>
<span data-ttu-id="5cbe1-103">Enthält Konfigurationsdaten für den <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="5cbe1-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="5cbe1-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5cbe1-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5cbe1-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="5cbe1-105">\<behaviors></span></span>  
<span data-ttu-id="5cbe1-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="5cbe1-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="5cbe1-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="5cbe1-107">\<behavior></span></span>  
<span data-ttu-id="5cbe1-108">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="5cbe1-108">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cbe1-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="5cbe1-109">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5cbe1-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5cbe1-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5cbe1-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5cbe1-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5cbe1-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="5cbe1-112">Attributes</span></span>  
  
|<span data-ttu-id="5cbe1-113">Element</span><span class="sxs-lookup"><span data-stu-id="5cbe1-113">Element</span></span>|<span data-ttu-id="5cbe1-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5cbe1-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5cbe1-115">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="5cbe1-115">ignoreExtensionDataObject</span></span>|<span data-ttu-id="5cbe1-116">Ein boolescher Wert ab, der angibt, ob vom Endpunkt bereitgestellte Daten ignoriert werden sollen, wenn dieser serialisiert oder deserialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="5cbe1-116">A Boolean value that specifies whether to ignore data supplied by the endpoint, when it is being serialized or deserialized.</span></span>|  
|<span data-ttu-id="5cbe1-117">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="5cbe1-117">maxItemsInObjectGraph</span></span>|<span data-ttu-id="5cbe1-118">Eine ganze Zahl, die die maximale Anzahl der zu serialisierenden oder zu deserialisierenden Elemente angibt.</span><span class="sxs-lookup"><span data-stu-id="5cbe1-118">An integer that specifies the maximum number of items to serialize or deserialize.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5cbe1-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5cbe1-119">Child Elements</span></span>  
 <span data-ttu-id="5cbe1-120">Keine</span><span class="sxs-lookup"><span data-stu-id="5cbe1-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5cbe1-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5cbe1-121">Parent Elements</span></span>  
  
|<span data-ttu-id="5cbe1-122">Element</span><span class="sxs-lookup"><span data-stu-id="5cbe1-122">Element</span></span>|<span data-ttu-id="5cbe1-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5cbe1-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5cbe1-124">\<behavior></span><span class="sxs-lookup"><span data-stu-id="5cbe1-124">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="5cbe1-125">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="5cbe1-125">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5cbe1-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5cbe1-126">Remarks</span></span>  
 <span data-ttu-id="5cbe1-127">Weitere Informationen zu bekannten Typen finden Sie in der <xref:System.Runtime.Serialization.DataContractSerializer>-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="5cbe1-127">See the <xref:System.Runtime.Serialization.DataContractSerializer> documentation for more information about known types.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="5cbe1-128">Das `<dataContractSerializer>`-Verhaltenselement sollte, wenn vorhanden, in der Konfigurationsdatei immer vor dem `<enableWebScript>`-Verhaltenselement angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5cbe1-128">The `<dataContractSerializer>` behavior element (if present) should always appear before the `<enableWebScript>` behavior element in the configuration file.</span></span> <span data-ttu-id="5cbe1-129">Andernfalls ist das resultierende Verhalten nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="5cbe1-129">Otherwise, the resulting behavior is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cbe1-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5cbe1-130">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="5cbe1-131">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="5cbe1-131">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="5cbe1-132">Datenübertragung und Serialisierung</span><span class="sxs-lookup"><span data-stu-id="5cbe1-132">Data Transfer and Serialization</span></span>](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
