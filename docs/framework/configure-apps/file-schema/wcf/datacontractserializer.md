---
title: dataContractSerializer
ms.date: 03/30/2017
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
ms.openlocfilehash: a024ca89bd766681f25b992f1d2c66a92e3b31b7
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150200"
---
# <a name="datacontractserializer"></a><span data-ttu-id="f8059-102">dataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="f8059-102">dataContractSerializer</span></span>
<span data-ttu-id="f8059-103">Enthält Konfigurationsdaten für den <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="f8059-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="f8059-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f8059-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f8059-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="f8059-105">\<behaviors></span></span>  
<span data-ttu-id="f8059-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="f8059-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="f8059-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="f8059-107">\<behavior></span></span>  
<span data-ttu-id="f8059-108">\<DataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="f8059-108">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8059-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="f8059-109">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f8059-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f8059-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f8059-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f8059-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f8059-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="f8059-112">Attributes</span></span>  
  
|<span data-ttu-id="f8059-113">Element</span><span class="sxs-lookup"><span data-stu-id="f8059-113">Element</span></span>|<span data-ttu-id="f8059-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f8059-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f8059-115">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="f8059-115">ignoreExtensionDataObject</span></span>|<span data-ttu-id="f8059-116">Ein boolescher Wert ab, der angibt, ob vom Endpunkt bereitgestellte Daten ignoriert werden sollen, wenn dieser serialisiert oder deserialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="f8059-116">A Boolean value that specifies whether to ignore data supplied by the endpoint, when it is being serialized or deserialized.</span></span>|  
|<span data-ttu-id="f8059-117">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="f8059-117">maxItemsInObjectGraph</span></span>|<span data-ttu-id="f8059-118">Eine ganze Zahl, die die maximale Anzahl der zu serialisierenden oder zu deserialisierenden Elemente angibt.</span><span class="sxs-lookup"><span data-stu-id="f8059-118">An integer that specifies the maximum number of items to serialize or deserialize.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f8059-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f8059-119">Child Elements</span></span>  
 <span data-ttu-id="f8059-120">Keine</span><span class="sxs-lookup"><span data-stu-id="f8059-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f8059-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f8059-121">Parent Elements</span></span>  
  
|<span data-ttu-id="f8059-122">Element</span><span class="sxs-lookup"><span data-stu-id="f8059-122">Element</span></span>|<span data-ttu-id="f8059-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f8059-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f8059-124">\<behavior></span><span class="sxs-lookup"><span data-stu-id="f8059-124">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="f8059-125">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="f8059-125">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f8059-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f8059-126">Remarks</span></span>  
 <span data-ttu-id="f8059-127">Weitere Informationen zu bekannten Typen finden Sie in der <xref:System.Runtime.Serialization.DataContractSerializer>-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="f8059-127">See the <xref:System.Runtime.Serialization.DataContractSerializer> documentation for more information about known types.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="f8059-128">Das `<dataContractSerializer>`-Verhaltenselement sollte, wenn vorhanden, in der Konfigurationsdatei immer vor dem `<enableWebScript>`-Verhaltenselement angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f8059-128">The `<dataContractSerializer>` behavior element (if present) should always appear before the `<enableWebScript>` behavior element in the configuration file.</span></span> <span data-ttu-id="f8059-129">Andernfalls ist das resultierende Verhalten nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="f8059-129">Otherwise, the resulting behavior is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8059-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8059-130">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>  
 <xref:System.ServiceModel.Configuration.DataContractSerializerElement>  
 [<span data-ttu-id="f8059-131">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="f8059-131">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="f8059-132">Datenübertragung und Serialisierung</span><span class="sxs-lookup"><span data-stu-id="f8059-132">Data Transfer and Serialization</span></span>](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
