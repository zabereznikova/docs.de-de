---
title: dataContractSerializer
ms.date: 03/30/2017
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
ms.openlocfilehash: e6524c18780c062c3b5b7dfc2509449cb208e270
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400437"
---
# <a name="datacontractserializer"></a><span data-ttu-id="6d74a-102">dataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="6d74a-102">dataContractSerializer</span></span>
<span data-ttu-id="6d74a-103">Enthält Konfigurationsdaten für den <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="6d74a-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**  
  
## <a name="syntax"></a><span data-ttu-id="6d74a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6d74a-104">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6d74a-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6d74a-105">Attributes and Elements</span></span>  
 <span data-ttu-id="6d74a-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6d74a-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6d74a-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="6d74a-107">Attributes</span></span>  
  
|<span data-ttu-id="6d74a-108">Element</span><span class="sxs-lookup"><span data-stu-id="6d74a-108">Element</span></span>|<span data-ttu-id="6d74a-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6d74a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6d74a-110">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="6d74a-110">ignoreExtensionDataObject</span></span>|<span data-ttu-id="6d74a-111">Ein boolescher Wert ab, der angibt, ob vom Endpunkt bereitgestellte Daten ignoriert werden sollen, wenn dieser serialisiert oder deserialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="6d74a-111">A Boolean value that specifies whether to ignore data supplied by the endpoint, when it is being serialized or deserialized.</span></span>|  
|<span data-ttu-id="6d74a-112">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="6d74a-112">maxItemsInObjectGraph</span></span>|<span data-ttu-id="6d74a-113">Eine ganze Zahl, die die maximale Anzahl der zu serialisierenden oder zu deserialisierenden Elemente angibt.</span><span class="sxs-lookup"><span data-stu-id="6d74a-113">An integer that specifies the maximum number of items to serialize or deserialize.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6d74a-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6d74a-114">Child Elements</span></span>  
 <span data-ttu-id="6d74a-115">Keine</span><span class="sxs-lookup"><span data-stu-id="6d74a-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6d74a-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6d74a-116">Parent Elements</span></span>  
  
|<span data-ttu-id="6d74a-117">Element</span><span class="sxs-lookup"><span data-stu-id="6d74a-117">Element</span></span>|<span data-ttu-id="6d74a-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6d74a-118">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="6d74a-119">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="6d74a-119">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d74a-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6d74a-120">Remarks</span></span>  
 <span data-ttu-id="6d74a-121">Weitere Informationen zu bekannten Typen finden Sie in der <xref:System.Runtime.Serialization.DataContractSerializer>-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="6d74a-121">See the <xref:System.Runtime.Serialization.DataContractSerializer> documentation for more information about known types.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="6d74a-122">Das `<dataContractSerializer>`-Verhaltenselement sollte, wenn vorhanden, in der Konfigurationsdatei immer vor dem `<enableWebScript>`-Verhaltenselement angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="6d74a-122">The `<dataContractSerializer>` behavior element (if present) should always appear before the `<enableWebScript>` behavior element in the configuration file.</span></span> <span data-ttu-id="6d74a-123">Andernfalls ist das resultierende Verhalten nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="6d74a-123">Otherwise, the resulting behavior is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d74a-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6d74a-124">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="6d74a-125">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="6d74a-125">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="6d74a-126">Datenübertragung und Serialisierung</span><span class="sxs-lookup"><span data-stu-id="6d74a-126">Data Transfer and Serialization</span></span>](../../../wcf/feature-details/data-transfer-and-serialization.md)
