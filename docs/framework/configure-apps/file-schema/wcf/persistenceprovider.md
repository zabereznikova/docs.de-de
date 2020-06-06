---
title: <persistenceProvider>
ms.date: 03/30/2017
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
ms.openlocfilehash: 7c4d9ae29ca1e543217d444e05a661b48e2cbb62
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400076"
---
# \<persistenceProvider>
<span data-ttu-id="b4078-101">Gibt den Typ der zu verwendenden Persistenzanbieterimplementierung sowie das Timeout für Persistenzvorgänge an.</span><span class="sxs-lookup"><span data-stu-id="b4078-101">Specifies the type of the persistence provider implementation to use, as well as the time-out to use for persistence operations.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<persistenceProvider>**  
  
## <a name="syntax"></a><span data-ttu-id="b4078-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4078-102">Syntax</span></span>  
  
```xml  
<persistenceProvider persistenceOperationTimeout="TimeSpan"
                     type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b4078-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b4078-103">Attributes and Elements</span></span>  
 <span data-ttu-id="b4078-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b4078-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b4078-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="b4078-105">Attributes</span></span>  
  
|<span data-ttu-id="b4078-106">attribute</span><span class="sxs-lookup"><span data-stu-id="b4078-106">Attribute</span></span>|<span data-ttu-id="b4078-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b4078-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b4078-108">persistenceOperationTimeout</span><span class="sxs-lookup"><span data-stu-id="b4078-108">persistenceOperationTimeout</span></span>|<span data-ttu-id="b4078-109">Ein <xref:System.TimeSpan>-Wert, der das Timeout angibt, das für Persistenzvorgänge verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b4078-109">A <xref:System.TimeSpan> value that specifies the time-out used for persistence operations.</span></span> <span data-ttu-id="b4078-110">Der Standardwert ist "00:00:30".</span><span class="sxs-lookup"><span data-stu-id="b4078-110">The default is "00:00:30".</span></span>|  
|<span data-ttu-id="b4078-111">type</span><span class="sxs-lookup"><span data-stu-id="b4078-111">type</span></span>|<span data-ttu-id="b4078-112">Eine Zeichenfolge, die den Typ der zu verwendenden Persistenz-Providerfactory angibt.</span><span class="sxs-lookup"><span data-stu-id="b4078-112">A string that specifies the type of the persistence provider factory to use.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b4078-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b4078-113">Child Elements</span></span>  
 <span data-ttu-id="b4078-114">Keine</span><span class="sxs-lookup"><span data-stu-id="b4078-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b4078-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b4078-115">Parent Elements</span></span>  
  
|<span data-ttu-id="b4078-116">Element</span><span class="sxs-lookup"><span data-stu-id="b4078-116">Element</span></span>|<span data-ttu-id="b4078-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4078-117">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="b4078-118">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="b4078-118">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4078-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b4078-119">Remarks</span></span>  
 <span data-ttu-id="b4078-120">Dieses Element gibt den Persistenz-Provider an, der verwendet werden soll, um den Zustand eines WCF-Dienstes zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="b4078-120">This element specifies the persistence provider to be used to serialize the state of a WCF service.</span></span> <span data-ttu-id="b4078-121">Es sollte zusammen mit der `wsHttpContextBinding` verwendet werden, die Zustandsinformationen in HTTP-Headern übergibt.</span><span class="sxs-lookup"><span data-stu-id="b4078-121">It should be used together with the `wsHttpContextBinding` which passes state information in HTTP headers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4078-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b4078-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.PersistenceProviderElement>
- <xref:System.ServiceModel.Persistence.PersistenceProvider>
