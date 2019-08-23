---
title: <tokenReplayDetection>
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: 2e2159a73ca79fc362a8138eea95dbd173dafb11
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944298"
---
# <a name="tokenreplaydetection"></a><span data-ttu-id="d16fb-101">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="d16fb-101">\<tokenReplayDetection></span></span>
<span data-ttu-id="d16fb-102">Aktiviert die Erkennung von tokenwiedergabe und gibt die Ablaufzeit für Token an.</span><span class="sxs-lookup"><span data-stu-id="d16fb-102">Enables token replay detection and specifies the expiration time for tokens.</span></span>  
  
 <span data-ttu-id="d16fb-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="d16fb-103">\<system.identityModel></span></span>  
<span data-ttu-id="d16fb-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="d16fb-104">\<identityConfiguration></span></span>  
<span data-ttu-id="d16fb-105">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="d16fb-105">\<tokenReplayDetection></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d16fb-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="d16fb-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a><span data-ttu-id="d16fb-107">Typ</span><span class="sxs-lookup"><span data-stu-id="d16fb-107">Type</span></span>  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d16fb-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d16fb-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d16fb-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d16fb-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d16fb-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="d16fb-110">Attributes</span></span>  
  
|<span data-ttu-id="d16fb-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="d16fb-111">Attribute</span></span>|<span data-ttu-id="d16fb-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d16fb-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d16fb-113">aktiviert</span><span class="sxs-lookup"><span data-stu-id="d16fb-113">enabled</span></span>|<span data-ttu-id="d16fb-114">Ein Wert, der angibt, ob die Erkennung der tokenwiedergabe aktiviert ist. "true", um die Erkennung von tokenwiedergabe zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="d16fb-114">A value that specifies whether token replay detection is enabled; "true" to enable token replay detection.</span></span>|  
|<span data-ttu-id="d16fb-115">expirationperiod</span><span class="sxs-lookup"><span data-stu-id="d16fb-115">expirationPeriod</span></span>|<span data-ttu-id="d16fb-116">Eine <xref:System.TimeSpan> , die die maximale Zeitspanne angibt, nach der ein Element als abgelaufen betrachtet und aus dem Cache entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="d16fb-116">A <xref:System.TimeSpan> that specifies the maximum amount of time before an item is considered expired and removed from the cache.</span></span>  <span data-ttu-id="d16fb-117">Weitere Informationen zum angeben <xref:System.TimeSpan> von Werten finden Sie unter [TimeSpan Values (TimeSpan-Werte](../windows-workflow-foundation/index.md)).</span><span class="sxs-lookup"><span data-stu-id="d16fb-117">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d16fb-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d16fb-118">Child Elements</span></span>  
 <span data-ttu-id="d16fb-119">None</span><span class="sxs-lookup"><span data-stu-id="d16fb-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d16fb-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d16fb-120">Parent Elements</span></span>  
  
|<span data-ttu-id="d16fb-121">Element</span><span class="sxs-lookup"><span data-stu-id="d16fb-121">Element</span></span>|<span data-ttu-id="d16fb-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d16fb-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d16fb-123">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="d16fb-123">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="d16fb-124">Gibt Identitäts Einstellungen auf Dienst Ebene an.</span><span class="sxs-lookup"><span data-stu-id="d16fb-124">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="d16fb-125">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="d16fb-125">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="d16fb-126">Stellt die Konfiguration für eine Auflistung von Sicherheitstokenhandlern bereit.</span><span class="sxs-lookup"><span data-stu-id="d16fb-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d16fb-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d16fb-127">Remarks</span></span>  
 <span data-ttu-id="d16fb-128">Ein `<tokenReplayDetection>` -Element kann auf der Dienst Ebene unterhalb des `<identityConfiguration>` -Elements oder auf der Auflistungs Ebene des Sicherheitstokenhandlers unter dem `<securityTokenHandlerConfiguration>` -Element angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d16fb-128">A `<tokenReplayDetection>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="d16fb-129">Einstellungen für eine tokenhandlerauflistung überschreiben die für den Dienst angegebenen.</span><span class="sxs-lookup"><span data-stu-id="d16fb-129">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="d16fb-130">Der Typ des tokenwiedergabe-Caches wird durch das [ \<tokenreplaycache->](tokenreplaycache.md) Element angegeben.</span><span class="sxs-lookup"><span data-stu-id="d16fb-130">The type of the token replay cache is specified by the [\<tokenReplayCache>](tokenreplaycache.md) element.</span></span>
