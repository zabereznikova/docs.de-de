---
title: <callbackTimeouts>
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: e1b40718638ded54e59743730159ea6e65a51a57
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398182"
---
# \<callbackTimeouts>
<span data-ttu-id="777bc-101">Gibt den Timeoutwert bei der Weitergabe von Transaktionen vom Server zum Client in einem Duplexrückrufvertragsszenario an.</span><span class="sxs-lookup"><span data-stu-id="777bc-101">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<callbackTimeOuts>**  
  
## <a name="syntax"></a><span data-ttu-id="777bc-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="777bc-102">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="777bc-103">type</span><span class="sxs-lookup"><span data-stu-id="777bc-103">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="777bc-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="777bc-104">Attributes and Elements</span></span>  
 <span data-ttu-id="777bc-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="777bc-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="777bc-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="777bc-106">Attributes</span></span>  
  
|<span data-ttu-id="777bc-107">attribute</span><span class="sxs-lookup"><span data-stu-id="777bc-107">Attribute</span></span>|<span data-ttu-id="777bc-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="777bc-108">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="777bc-109">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall angibt, in dem Transaktionen abgeschlossen oder automatisch beendet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="777bc-109">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="777bc-110">Der Standardwert ist "00:00:00".</span><span class="sxs-lookup"><span data-stu-id="777bc-110">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="777bc-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="777bc-111">Child Elements</span></span>  
 <span data-ttu-id="777bc-112">Keine</span><span class="sxs-lookup"><span data-stu-id="777bc-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="777bc-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="777bc-113">Parent Elements</span></span>  
  
|<span data-ttu-id="777bc-114">Element</span><span class="sxs-lookup"><span data-stu-id="777bc-114">Element</span></span>|<span data-ttu-id="777bc-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="777bc-115">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="777bc-116">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="777bc-116">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="777bc-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="777bc-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
