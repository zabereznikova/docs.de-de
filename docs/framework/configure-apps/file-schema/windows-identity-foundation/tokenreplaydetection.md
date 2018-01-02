---
title: '&lt;tokenReplayDetection&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
caps.latest.revision: "6"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 88622d4d30d40702425da8bbdbdaf2c4a6878f47
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="lttokenreplaydetectiongt"></a><span data-ttu-id="5d4cd-102">&lt;tokenReplayDetection&gt;</span><span class="sxs-lookup"><span data-stu-id="5d4cd-102">&lt;tokenReplayDetection&gt;</span></span>
<span data-ttu-id="5d4cd-103">Tokenwiedergabeerkennung aktiviert, und gibt die Ablaufzeit für Token.</span><span class="sxs-lookup"><span data-stu-id="5d4cd-103">Enables token replay detection and specifies the expiration time for tokens.</span></span>  
  
 <span data-ttu-id="5d4cd-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="5d4cd-104">\<system.identityModel></span></span>  
<span data-ttu-id="5d4cd-105">\<IdentityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="5d4cd-105">\<identityConfiguration></span></span>  
<span data-ttu-id="5d4cd-106">\<TokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="5d4cd-106">\<tokenReplayDetection></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d4cd-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="5d4cd-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a><span data-ttu-id="5d4cd-108">Typ</span><span class="sxs-lookup"><span data-stu-id="5d4cd-108">Type</span></span>  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5d4cd-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5d4cd-109">Attributes and Elements</span></span>  
 <span data-ttu-id="5d4cd-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5d4cd-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5d4cd-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="5d4cd-111">Attributes</span></span>  
  
|<span data-ttu-id="5d4cd-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="5d4cd-112">Attribute</span></span>|<span data-ttu-id="5d4cd-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5d4cd-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5d4cd-114">enabled</span><span class="sxs-lookup"><span data-stu-id="5d4cd-114">enabled</span></span>|<span data-ttu-id="5d4cd-115">Ein Wert, der angibt, ob tokenwiederholungen aktiviert ist. "true", um Token zu aktivieren replay-Erkennung.</span><span class="sxs-lookup"><span data-stu-id="5d4cd-115">A value that specifies whether token replay detection is enabled; "true" to enable token replay detection.</span></span>|  
|<span data-ttu-id="5d4cd-116">expirationPeriod</span><span class="sxs-lookup"><span data-stu-id="5d4cd-116">expirationPeriod</span></span>|<span data-ttu-id="5d4cd-117">Ein <xref:System.TimeSpan> , die angibt, dass der maximale Zeitspanne, bevor ein Element betrachtet wird, ist abgelaufen und aus dem Cache entfernt.</span><span class="sxs-lookup"><span data-stu-id="5d4cd-117">A <xref:System.TimeSpan> that specifies the maximum amount of time before an item is considered expired and removed from the cache.</span></span>  <span data-ttu-id="5d4cd-118">Weitere Informationen zum Angeben der <xref:System.TimeSpan> -Werte finden Sie in [Timespan Werte](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="5d4cd-118">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5d4cd-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5d4cd-119">Child Elements</span></span>  
 <span data-ttu-id="5d4cd-120">Keiner</span><span class="sxs-lookup"><span data-stu-id="5d4cd-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5d4cd-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5d4cd-121">Parent Elements</span></span>  
  
|<span data-ttu-id="5d4cd-122">Element</span><span class="sxs-lookup"><span data-stu-id="5d4cd-122">Element</span></span>|<span data-ttu-id="5d4cd-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5d4cd-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d4cd-124">\<IdentityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="5d4cd-124">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="5d4cd-125">Gibt an, Service Level identitätseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="5d4cd-125">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="5d4cd-126">\<SecurityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="5d4cd-126">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="5d4cd-127">Ermöglicht die Konfiguration für eine Auflistung der Tokenhandler.</span><span class="sxs-lookup"><span data-stu-id="5d4cd-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d4cd-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5d4cd-128">Remarks</span></span>  
 <span data-ttu-id="5d4cd-129">Ein `<tokenReplayDetection>` Element angegeben werden kann, auf Dienstebene unter der `<identityConfiguration>` Element oder auf die Sicherheitsstufe für die Auflistung von Tokenhandler unter der `<securityTokenHandlerConfiguration>` Element.</span><span class="sxs-lookup"><span data-stu-id="5d4cd-129">A `<tokenReplayDetection>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="5d4cd-130">Einstellungen für eine Sammlung Tokenhandler außer Kraft für den Dienst angegeben.</span><span class="sxs-lookup"><span data-stu-id="5d4cd-130">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="5d4cd-131">Der Typ des Caches aufbewahrungsdateu wird angegeben, durch die [ \<TokenReplayCache >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) Element.</span><span class="sxs-lookup"><span data-stu-id="5d4cd-131">The type of the token replay cache is specified by the [\<tokenReplayCache>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) element.</span></span>
