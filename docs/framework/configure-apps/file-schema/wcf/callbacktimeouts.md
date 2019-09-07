---
title: <callbackTimeouts>
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: e1b40718638ded54e59743730159ea6e65a51a57
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398182"
---
# <a name="callbacktimeouts"></a><span data-ttu-id="bf17b-101">\<callbackTimeouts></span><span class="sxs-lookup"><span data-stu-id="bf17b-101">\<callbackTimeouts></span></span>
<span data-ttu-id="bf17b-102">Gibt den Timeoutwert bei der Weitergabe von Transaktionen vom Server zum Client in einem Duplexrückrufvertragsszenario an.</span><span class="sxs-lookup"><span data-stu-id="bf17b-102">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
<span data-ttu-id="bf17b-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="bf17b-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="bf17b-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="bf17b-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="bf17b-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="bf17b-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="bf17b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointverhaltens->** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="bf17b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="bf17b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="bf17b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="bf17b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<callbacktimeouts >**</span><span class="sxs-lookup"><span data-stu-id="bf17b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<callbackTimeOuts>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf17b-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="bf17b-109">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="bf17b-110">Typ</span><span class="sxs-lookup"><span data-stu-id="bf17b-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bf17b-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="bf17b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="bf17b-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bf17b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bf17b-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="bf17b-113">Attributes</span></span>  
  
|<span data-ttu-id="bf17b-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="bf17b-114">Attribute</span></span>|<span data-ttu-id="bf17b-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bf17b-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="bf17b-116">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall angibt, in dem Transaktionen abgeschlossen oder automatisch beendet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="bf17b-116">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="bf17b-117">Der Standardwert ist "00:00:00".</span><span class="sxs-lookup"><span data-stu-id="bf17b-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bf17b-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bf17b-118">Child Elements</span></span>  
 <span data-ttu-id="bf17b-119">Keine</span><span class="sxs-lookup"><span data-stu-id="bf17b-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bf17b-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bf17b-120">Parent Elements</span></span>  
  
|<span data-ttu-id="bf17b-121">Element</span><span class="sxs-lookup"><span data-stu-id="bf17b-121">Element</span></span>|<span data-ttu-id="bf17b-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bf17b-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bf17b-123">\<behavior></span><span class="sxs-lookup"><span data-stu-id="bf17b-123">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="bf17b-124">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="bf17b-124">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bf17b-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bf17b-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
