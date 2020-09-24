---
title: dataContractSerializer
ms.date: 03/30/2017
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
ms.openlocfilehash: 0e4cbc50c25d4fa1f67f283f2b52d4b174428cd3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153923"
---
# <a name="datacontractserializer"></a><span data-ttu-id="08bfe-102">dataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="08bfe-102">dataContractSerializer</span></span>

<span data-ttu-id="08bfe-103">Enthält Konfigurationsdaten für den <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="08bfe-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**  
  
## <a name="syntax"></a><span data-ttu-id="08bfe-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="08bfe-104">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="08bfe-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="08bfe-105">Attributes and Elements</span></span>  

 <span data-ttu-id="08bfe-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="08bfe-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="08bfe-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="08bfe-107">Attributes</span></span>  
  
|<span data-ttu-id="08bfe-108">Element</span><span class="sxs-lookup"><span data-stu-id="08bfe-108">Element</span></span>|<span data-ttu-id="08bfe-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="08bfe-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="08bfe-110">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="08bfe-110">ignoreExtensionDataObject</span></span>|<span data-ttu-id="08bfe-111">Ein boolescher Wert ab, der angibt, ob vom Endpunkt bereitgestellte Daten ignoriert werden sollen, wenn dieser serialisiert oder deserialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="08bfe-111">A Boolean value that specifies whether to ignore data supplied by the endpoint, when it is being serialized or deserialized.</span></span>|  
|<span data-ttu-id="08bfe-112">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="08bfe-112">maxItemsInObjectGraph</span></span>|<span data-ttu-id="08bfe-113">Eine ganze Zahl, die die maximale Anzahl der zu serialisierenden oder zu deserialisierenden Elemente angibt.</span><span class="sxs-lookup"><span data-stu-id="08bfe-113">An integer that specifies the maximum number of items to serialize or deserialize.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="08bfe-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="08bfe-114">Child Elements</span></span>  

 <span data-ttu-id="08bfe-115">Keine</span><span class="sxs-lookup"><span data-stu-id="08bfe-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="08bfe-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="08bfe-116">Parent Elements</span></span>  
  
|<span data-ttu-id="08bfe-117">Element</span><span class="sxs-lookup"><span data-stu-id="08bfe-117">Element</span></span>|<span data-ttu-id="08bfe-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="08bfe-118">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="08bfe-119">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="08bfe-119">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08bfe-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="08bfe-120">Remarks</span></span>  

 <span data-ttu-id="08bfe-121">Weitere Informationen zu bekannten Typen finden Sie in der <xref:System.Runtime.Serialization.DataContractSerializer>-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="08bfe-121">See the <xref:System.Runtime.Serialization.DataContractSerializer> documentation for more information about known types.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="08bfe-122">Das `<dataContractSerializer>`-Verhaltenselement sollte, wenn vorhanden, in der Konfigurationsdatei immer vor dem `<enableWebScript>`-Verhaltenselement angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="08bfe-122">The `<dataContractSerializer>` behavior element (if present) should always appear before the `<enableWebScript>` behavior element in the configuration file.</span></span> <span data-ttu-id="08bfe-123">Andernfalls ist das resultierende Verhalten nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="08bfe-123">Otherwise, the resulting behavior is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08bfe-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="08bfe-124">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="08bfe-125">Bekannte Typen in Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="08bfe-125">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="08bfe-126">Datenübertragung und Serialisierung</span><span class="sxs-lookup"><span data-stu-id="08bfe-126">Data Transfer and Serialization</span></span>](../../../wcf/feature-details/data-transfer-and-serialization.md)
