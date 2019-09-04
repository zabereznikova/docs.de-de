---
title: <tokenReplayDetection>
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: a4454042e1d97fb3cc2d6f2735104dadda6e7b5a
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251770"
---
# <a name="tokenreplaydetection"></a><span data-ttu-id="ff19f-101">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="ff19f-101">\<tokenReplayDetection></span></span>
<span data-ttu-id="ff19f-102">Aktiviert die Erkennung von tokenwiedergabe und gibt die Ablaufzeit für Token an.</span><span class="sxs-lookup"><span data-stu-id="ff19f-102">Enables token replay detection and specifies the expiration time for tokens.</span></span>  
  
<span data-ttu-id="ff19f-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ff19f-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ff19f-104">&nbsp;&nbsp;[ **\<System. IdentityModel->** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="ff19f-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="ff19f-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityconfiguration->** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="ff19f-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="ff19f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<tokenreplayerkennungs->**</span><span class="sxs-lookup"><span data-stu-id="ff19f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayDetection>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff19f-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="ff19f-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a><span data-ttu-id="ff19f-108">Typ</span><span class="sxs-lookup"><span data-stu-id="ff19f-108">Type</span></span>  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ff19f-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ff19f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ff19f-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ff19f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ff19f-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="ff19f-111">Attributes</span></span>  
  
|<span data-ttu-id="ff19f-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="ff19f-112">Attribute</span></span>|<span data-ttu-id="ff19f-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ff19f-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ff19f-114">aktiviert</span><span class="sxs-lookup"><span data-stu-id="ff19f-114">enabled</span></span>|<span data-ttu-id="ff19f-115">Ein Wert, der angibt, ob die Erkennung der tokenwiedergabe aktiviert ist. "true", um die Erkennung von tokenwiedergabe zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ff19f-115">A value that specifies whether token replay detection is enabled; "true" to enable token replay detection.</span></span>|  
|<span data-ttu-id="ff19f-116">expirationperiod</span><span class="sxs-lookup"><span data-stu-id="ff19f-116">expirationPeriod</span></span>|<span data-ttu-id="ff19f-117">Eine <xref:System.TimeSpan> , die die maximale Zeitspanne angibt, nach der ein Element als abgelaufen betrachtet und aus dem Cache entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="ff19f-117">A <xref:System.TimeSpan> that specifies the maximum amount of time before an item is considered expired and removed from the cache.</span></span>  <span data-ttu-id="ff19f-118">Weitere Informationen zum angeben <xref:System.TimeSpan> von Werten finden Sie unter [TimeSpan Values (TimeSpan-Werte](../windows-workflow-foundation/index.md)).</span><span class="sxs-lookup"><span data-stu-id="ff19f-118">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ff19f-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ff19f-119">Child Elements</span></span>  
 <span data-ttu-id="ff19f-120">None</span><span class="sxs-lookup"><span data-stu-id="ff19f-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ff19f-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ff19f-121">Parent Elements</span></span>  
  
|<span data-ttu-id="ff19f-122">Element</span><span class="sxs-lookup"><span data-stu-id="ff19f-122">Element</span></span>|<span data-ttu-id="ff19f-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ff19f-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ff19f-124">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="ff19f-124">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="ff19f-125">Gibt Identitäts Einstellungen auf Dienst Ebene an.</span><span class="sxs-lookup"><span data-stu-id="ff19f-125">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="ff19f-126">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="ff19f-126">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="ff19f-127">Stellt die Konfiguration für eine Auflistung von Sicherheitstokenhandlern bereit.</span><span class="sxs-lookup"><span data-stu-id="ff19f-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff19f-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ff19f-128">Remarks</span></span>  
 <span data-ttu-id="ff19f-129">Ein `<tokenReplayDetection>` -Element kann auf der Dienst Ebene unterhalb des `<identityConfiguration>` -Elements oder auf der Auflistungs Ebene des Sicherheitstokenhandlers unter dem `<securityTokenHandlerConfiguration>` -Element angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ff19f-129">A `<tokenReplayDetection>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="ff19f-130">Einstellungen für eine tokenhandlerauflistung überschreiben die für den Dienst angegebenen.</span><span class="sxs-lookup"><span data-stu-id="ff19f-130">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="ff19f-131">Der Typ des tokenwiedergabe-Caches wird durch das [ \<tokenreplaycache->](tokenreplaycache.md) Element angegeben.</span><span class="sxs-lookup"><span data-stu-id="ff19f-131">The type of the token replay cache is specified by the [\<tokenReplayCache>](tokenreplaycache.md) element.</span></span>
