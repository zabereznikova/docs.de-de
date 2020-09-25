---
title: <callbackTimeouts>
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: 98523489aacebf910bcf5d81c479819183887dff
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198885"
---
# \<callbackTimeouts>

<span data-ttu-id="aa207-101">Gibt den Timeoutwert bei der Weitergabe von Transaktionen vom Server zum Client in einem Duplexrückrufvertragsszenario an.</span><span class="sxs-lookup"><span data-stu-id="aa207-101">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<callbackTimeOuts>**  
  
## <a name="syntax"></a><span data-ttu-id="aa207-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="aa207-102">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="aa207-103">Typ</span><span class="sxs-lookup"><span data-stu-id="aa207-103">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aa207-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="aa207-104">Attributes and Elements</span></span>  

 <span data-ttu-id="aa207-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="aa207-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aa207-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="aa207-106">Attributes</span></span>  
  
|<span data-ttu-id="aa207-107">attribute</span><span class="sxs-lookup"><span data-stu-id="aa207-107">Attribute</span></span>|<span data-ttu-id="aa207-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aa207-108">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="aa207-109">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall angibt, in dem Transaktionen abgeschlossen oder automatisch beendet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="aa207-109">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="aa207-110">Der Standardwert ist "00:00:00".</span><span class="sxs-lookup"><span data-stu-id="aa207-110">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aa207-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="aa207-111">Child Elements</span></span>  

 <span data-ttu-id="aa207-112">Keine</span><span class="sxs-lookup"><span data-stu-id="aa207-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="aa207-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="aa207-113">Parent Elements</span></span>  
  
|<span data-ttu-id="aa207-114">Element</span><span class="sxs-lookup"><span data-stu-id="aa207-114">Element</span></span>|<span data-ttu-id="aa207-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aa207-115">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="aa207-116">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="aa207-116">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aa207-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="aa207-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
