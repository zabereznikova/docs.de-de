---
title: <tokenReplayDetection>
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: df512960b522f17dc9247bb5959e246c8c1f15b8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169803"
---
# \<tokenReplayDetection>

<span data-ttu-id="8ffce-101">Aktiviert die Erkennung von tokenwiedergabe und gibt die Ablaufzeit für Token an.</span><span class="sxs-lookup"><span data-stu-id="8ffce-101">Enables token replay detection and specifies the expiration time for tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayDetection>**  
  
## <a name="syntax"></a><span data-ttu-id="8ffce-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="8ffce-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a><span data-ttu-id="8ffce-103">Typ</span><span class="sxs-lookup"><span data-stu-id="8ffce-103">Type</span></span>  

 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8ffce-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8ffce-104">Attributes and Elements</span></span>  

 <span data-ttu-id="8ffce-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8ffce-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8ffce-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="8ffce-106">Attributes</span></span>  
  
|<span data-ttu-id="8ffce-107">attribute</span><span class="sxs-lookup"><span data-stu-id="8ffce-107">Attribute</span></span>|<span data-ttu-id="8ffce-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8ffce-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8ffce-109">enabled</span><span class="sxs-lookup"><span data-stu-id="8ffce-109">enabled</span></span>|<span data-ttu-id="8ffce-110">Ein Wert, der angibt, ob die Erkennung der tokenwiedergabe aktiviert ist. "true", um die Erkennung von tokenwiedergabe zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8ffce-110">A value that specifies whether token replay detection is enabled; "true" to enable token replay detection.</span></span>|  
|<span data-ttu-id="8ffce-111">expirationperiod</span><span class="sxs-lookup"><span data-stu-id="8ffce-111">expirationPeriod</span></span>|<span data-ttu-id="8ffce-112">Eine <xref:System.TimeSpan> , die die maximale Zeitspanne angibt, nach der ein Element als abgelaufen betrachtet und aus dem Cache entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="8ffce-112">A <xref:System.TimeSpan> that specifies the maximum amount of time before an item is considered expired and removed from the cache.</span></span>  <span data-ttu-id="8ffce-113">Weitere Informationen zum Angeben von <xref:System.TimeSpan> Werten finden Sie unter [TimeSpan Values (TimeSpan-Werte](../windows-workflow-foundation/index.md)).</span><span class="sxs-lookup"><span data-stu-id="8ffce-113">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8ffce-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8ffce-114">Child Elements</span></span>  

 <span data-ttu-id="8ffce-115">Keine</span><span class="sxs-lookup"><span data-stu-id="8ffce-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8ffce-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8ffce-116">Parent Elements</span></span>  
  
|<span data-ttu-id="8ffce-117">Element</span><span class="sxs-lookup"><span data-stu-id="8ffce-117">Element</span></span>|<span data-ttu-id="8ffce-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8ffce-118">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="8ffce-119">Gibt Identitäts Einstellungen auf Dienst Ebene an.</span><span class="sxs-lookup"><span data-stu-id="8ffce-119">Specifies service-level identity settings.</span></span>|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="8ffce-120">Stellt die Konfiguration für eine Auflistung von Sicherheitstokenhandlern bereit.</span><span class="sxs-lookup"><span data-stu-id="8ffce-120">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ffce-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="8ffce-121">Remarks</span></span>  

 <span data-ttu-id="8ffce-122">Ein- `<tokenReplayDetection>` Element kann auf der Dienst Ebene unterhalb des- `<identityConfiguration>` Elements oder auf der Auflistungs Ebene des Sicherheitstokenhandlers unter dem-Element angegeben werden `<securityTokenHandlerConfiguration>` .</span><span class="sxs-lookup"><span data-stu-id="8ffce-122">A `<tokenReplayDetection>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="8ffce-123">Einstellungen für eine tokenhandlerauflistung überschreiben die für den Dienst angegebenen.</span><span class="sxs-lookup"><span data-stu-id="8ffce-123">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="8ffce-124">Der Typ des tokenreplay-Caches wird durch das- [\<tokenReplayCache>](tokenreplaycache.md) Element angegeben.</span><span class="sxs-lookup"><span data-stu-id="8ffce-124">The type of the token replay cache is specified by the [\<tokenReplayCache>](tokenreplaycache.md) element.</span></span>
