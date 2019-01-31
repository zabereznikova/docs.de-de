---
title: <tokenReplayDetection>
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: 4deeb1d84f2621adb7ff1b649a505138b6856ec1
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55283074"
---
# <a name="tokenreplaydetection"></a><span data-ttu-id="1fe4e-101">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="1fe4e-101">\<tokenReplayDetection></span></span>
<span data-ttu-id="1fe4e-102">Ermöglicht die Erkennung einer tokenmehrfachverwendung, und gibt an, die Ablaufzeit für Token.</span><span class="sxs-lookup"><span data-stu-id="1fe4e-102">Enables token replay detection and specifies the expiration time for tokens.</span></span>  
  
 <span data-ttu-id="1fe4e-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="1fe4e-103">\<system.identityModel></span></span>  
<span data-ttu-id="1fe4e-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="1fe4e-104">\<identityConfiguration></span></span>  
<span data-ttu-id="1fe4e-105">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="1fe4e-105">\<tokenReplayDetection></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fe4e-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="1fe4e-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a><span data-ttu-id="1fe4e-107">Typ</span><span class="sxs-lookup"><span data-stu-id="1fe4e-107">Type</span></span>  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1fe4e-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1fe4e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1fe4e-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1fe4e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1fe4e-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="1fe4e-110">Attributes</span></span>  
  
|<span data-ttu-id="1fe4e-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="1fe4e-111">Attribute</span></span>|<span data-ttu-id="1fe4e-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1fe4e-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1fe4e-113">enabled</span><span class="sxs-lookup"><span data-stu-id="1fe4e-113">enabled</span></span>|<span data-ttu-id="1fe4e-114">Ein Wert, der angibt, ob die Erkennung einer tokenmehrfachverwendung aktiviert ist. "true", um Token zu aktivieren. replay-Erkennung.</span><span class="sxs-lookup"><span data-stu-id="1fe4e-114">A value that specifies whether token replay detection is enabled; "true" to enable token replay detection.</span></span>|  
|<span data-ttu-id="1fe4e-115">expirationPeriod</span><span class="sxs-lookup"><span data-stu-id="1fe4e-115">expirationPeriod</span></span>|<span data-ttu-id="1fe4e-116">Ein <xref:System.TimeSpan> , der angibt, dass der Höchstmenge des Zeitraums, bevor ein Element als abgelaufen erachtet wird und aus dem Cache entfernt.</span><span class="sxs-lookup"><span data-stu-id="1fe4e-116">A <xref:System.TimeSpan> that specifies the maximum amount of time before an item is considered expired and removed from the cache.</span></span>  <span data-ttu-id="1fe4e-117">Weitere Informationen zur Vorgehensweise beim angeben <xref:System.TimeSpan> Werte finden Sie unter [Timespan-Werten](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="1fe4e-117">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1fe4e-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1fe4e-118">Child Elements</span></span>  
 <span data-ttu-id="1fe4e-119">Keine</span><span class="sxs-lookup"><span data-stu-id="1fe4e-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1fe4e-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1fe4e-120">Parent Elements</span></span>  
  
|<span data-ttu-id="1fe4e-121">Element</span><span class="sxs-lookup"><span data-stu-id="1fe4e-121">Element</span></span>|<span data-ttu-id="1fe4e-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1fe4e-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1fe4e-123">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="1fe4e-123">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="1fe4e-124">Gibt die identitätseinstellungen der Servicelevel.</span><span class="sxs-lookup"><span data-stu-id="1fe4e-124">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="1fe4e-125">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="1fe4e-125">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="1fe4e-126">Stellt die Konfiguration für eine Auflistung der Tokenhandler.</span><span class="sxs-lookup"><span data-stu-id="1fe4e-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1fe4e-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1fe4e-127">Remarks</span></span>  
 <span data-ttu-id="1fe4e-128">Ein `<tokenReplayDetection>` Element kann angegeben werden, auf der Dienstebene unter der `<identityConfiguration>` Element oder die Sicherheitsstufe für die Auflistung von Tokenhandler unter der `<securityTokenHandlerConfiguration>` Element.</span><span class="sxs-lookup"><span data-stu-id="1fe4e-128">A `<tokenReplayDetection>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="1fe4e-129">Einstellungen für eine Auflistung der Tokenhandler überschreiben jene, die für den Dienst angegeben.</span><span class="sxs-lookup"><span data-stu-id="1fe4e-129">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="1fe4e-130">Der Typ der tokenwiedergabecache wird angegeben, durch die [ \<TokenReplayCache >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) Element.</span><span class="sxs-lookup"><span data-stu-id="1fe4e-130">The type of the token replay cache is specified by the [\<tokenReplayCache>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) element.</span></span>
