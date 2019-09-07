---
title: dataContractSerializer
ms.date: 03/30/2017
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
ms.openlocfilehash: e6524c18780c062c3b5b7dfc2509449cb208e270
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400437"
---
# <a name="datacontractserializer"></a><span data-ttu-id="311ed-102">dataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="311ed-102">dataContractSerializer</span></span>
<span data-ttu-id="311ed-103">Enthält Konfigurationsdaten für den <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="311ed-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
<span data-ttu-id="311ed-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="311ed-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="311ed-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="311ed-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="311ed-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="311ed-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="311ed-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointverhaltens->** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="311ed-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="311ed-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="311ed-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="311ed-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<DataContractSerializer->**</span><span class="sxs-lookup"><span data-stu-id="311ed-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="311ed-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="311ed-110">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="311ed-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="311ed-111">Attributes and Elements</span></span>  
 <span data-ttu-id="311ed-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="311ed-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="311ed-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="311ed-113">Attributes</span></span>  
  
|<span data-ttu-id="311ed-114">Element</span><span class="sxs-lookup"><span data-stu-id="311ed-114">Element</span></span>|<span data-ttu-id="311ed-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="311ed-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="311ed-116">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="311ed-116">ignoreExtensionDataObject</span></span>|<span data-ttu-id="311ed-117">Ein boolescher Wert ab, der angibt, ob vom Endpunkt bereitgestellte Daten ignoriert werden sollen, wenn dieser serialisiert oder deserialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="311ed-117">A Boolean value that specifies whether to ignore data supplied by the endpoint, when it is being serialized or deserialized.</span></span>|  
|<span data-ttu-id="311ed-118">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="311ed-118">maxItemsInObjectGraph</span></span>|<span data-ttu-id="311ed-119">Eine ganze Zahl, die die maximale Anzahl der zu serialisierenden oder zu deserialisierenden Elemente angibt.</span><span class="sxs-lookup"><span data-stu-id="311ed-119">An integer that specifies the maximum number of items to serialize or deserialize.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="311ed-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="311ed-120">Child Elements</span></span>  
 <span data-ttu-id="311ed-121">Keine</span><span class="sxs-lookup"><span data-stu-id="311ed-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="311ed-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="311ed-122">Parent Elements</span></span>  
  
|<span data-ttu-id="311ed-123">Element</span><span class="sxs-lookup"><span data-stu-id="311ed-123">Element</span></span>|<span data-ttu-id="311ed-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="311ed-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="311ed-125">\<behavior></span><span class="sxs-lookup"><span data-stu-id="311ed-125">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="311ed-126">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="311ed-126">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="311ed-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="311ed-127">Remarks</span></span>  
 <span data-ttu-id="311ed-128">Weitere Informationen zu bekannten Typen finden Sie in der <xref:System.Runtime.Serialization.DataContractSerializer>-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="311ed-128">See the <xref:System.Runtime.Serialization.DataContractSerializer> documentation for more information about known types.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="311ed-129">Das `<dataContractSerializer>`-Verhaltenselement sollte, wenn vorhanden, in der Konfigurationsdatei immer vor dem `<enableWebScript>`-Verhaltenselement angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="311ed-129">The `<dataContractSerializer>` behavior element (if present) should always appear before the `<enableWebScript>` behavior element in the configuration file.</span></span> <span data-ttu-id="311ed-130">Andernfalls ist das resultierende Verhalten nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="311ed-130">Otherwise, the resulting behavior is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="311ed-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="311ed-131">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="311ed-132">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="311ed-132">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="311ed-133">Datenübertragung und Serialisierung</span><span class="sxs-lookup"><span data-stu-id="311ed-133">Data Transfer and Serialization</span></span>](../../../wcf/feature-details/data-transfer-and-serialization.md)
