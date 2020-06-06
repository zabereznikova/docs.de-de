---
title: <tokenReplayDetection>
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: a4454042e1d97fb3cc2d6f2735104dadda6e7b5a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251770"
---
# \<tokenReplayDetection>
<span data-ttu-id="05f42-101">Aktiviert die Erkennung von tokenwiedergabe und gibt die Ablaufzeit für Token an.</span><span class="sxs-lookup"><span data-stu-id="05f42-101">Enables token replay detection and specifies the expiration time for tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayDetection>**  
  
## <a name="syntax"></a><span data-ttu-id="05f42-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="05f42-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a><span data-ttu-id="05f42-103">type</span><span class="sxs-lookup"><span data-stu-id="05f42-103">Type</span></span>  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="05f42-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="05f42-104">Attributes and Elements</span></span>  
 <span data-ttu-id="05f42-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="05f42-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="05f42-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="05f42-106">Attributes</span></span>  
  
|<span data-ttu-id="05f42-107">attribute</span><span class="sxs-lookup"><span data-stu-id="05f42-107">Attribute</span></span>|<span data-ttu-id="05f42-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="05f42-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="05f42-109">enabled</span><span class="sxs-lookup"><span data-stu-id="05f42-109">enabled</span></span>|<span data-ttu-id="05f42-110">Ein Wert, der angibt, ob die Erkennung der tokenwiedergabe aktiviert ist. "true", um die Erkennung von tokenwiedergabe zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="05f42-110">A value that specifies whether token replay detection is enabled; "true" to enable token replay detection.</span></span>|  
|<span data-ttu-id="05f42-111">expirationperiod</span><span class="sxs-lookup"><span data-stu-id="05f42-111">expirationPeriod</span></span>|<span data-ttu-id="05f42-112">Eine <xref:System.TimeSpan> , die die maximale Zeitspanne angibt, nach der ein Element als abgelaufen betrachtet und aus dem Cache entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="05f42-112">A <xref:System.TimeSpan> that specifies the maximum amount of time before an item is considered expired and removed from the cache.</span></span>  <span data-ttu-id="05f42-113">Weitere Informationen zum Angeben von <xref:System.TimeSpan> Werten finden Sie unter [TimeSpan Values (TimeSpan-Werte](../windows-workflow-foundation/index.md)).</span><span class="sxs-lookup"><span data-stu-id="05f42-113">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="05f42-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="05f42-114">Child Elements</span></span>  
 <span data-ttu-id="05f42-115">Keine</span><span class="sxs-lookup"><span data-stu-id="05f42-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="05f42-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="05f42-116">Parent Elements</span></span>  
  
|<span data-ttu-id="05f42-117">Element</span><span class="sxs-lookup"><span data-stu-id="05f42-117">Element</span></span>|<span data-ttu-id="05f42-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="05f42-118">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="05f42-119">Gibt Identitäts Einstellungen auf Dienst Ebene an.</span><span class="sxs-lookup"><span data-stu-id="05f42-119">Specifies service-level identity settings.</span></span>|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="05f42-120">Stellt die Konfiguration für eine Auflistung von Sicherheitstokenhandlern bereit.</span><span class="sxs-lookup"><span data-stu-id="05f42-120">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05f42-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="05f42-121">Remarks</span></span>  
 <span data-ttu-id="05f42-122">Ein- `<tokenReplayDetection>` Element kann auf der Dienst Ebene unterhalb des- `<identityConfiguration>` Elements oder auf der Auflistungs Ebene des Sicherheitstokenhandlers unter dem-Element angegeben werden `<securityTokenHandlerConfiguration>` .</span><span class="sxs-lookup"><span data-stu-id="05f42-122">A `<tokenReplayDetection>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="05f42-123">Einstellungen für eine tokenhandlerauflistung überschreiben die für den Dienst angegebenen.</span><span class="sxs-lookup"><span data-stu-id="05f42-123">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="05f42-124">Der Typ des tokenreplay-Caches wird durch das- [\<tokenReplayCache>](tokenreplaycache.md) Element angegeben.</span><span class="sxs-lookup"><span data-stu-id="05f42-124">The type of the token replay cache is specified by the [\<tokenReplayCache>](tokenreplaycache.md) element.</span></span>
