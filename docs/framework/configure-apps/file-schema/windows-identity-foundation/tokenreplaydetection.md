---
title: '&lt;tokenReplayDetection&gt;'
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: bd2272cb83dc0183d5008cfa178e11783f51ca2d
ms.sourcegitcommit: 700b9003ea6bdd83a53458bbc436c9b5778344f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2018
ms.locfileid: "48261054"
---
# <a name="lttokenreplaydetectiongt"></a><span data-ttu-id="dcf8e-102">&lt;tokenReplayDetection&gt;</span><span class="sxs-lookup"><span data-stu-id="dcf8e-102">&lt;tokenReplayDetection&gt;</span></span>
<span data-ttu-id="dcf8e-103">Ermöglicht die Erkennung einer tokenmehrfachverwendung, und gibt an, die Ablaufzeit für Token.</span><span class="sxs-lookup"><span data-stu-id="dcf8e-103">Enables token replay detection and specifies the expiration time for tokens.</span></span>  
  
 <span data-ttu-id="dcf8e-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="dcf8e-104">\<system.identityModel></span></span>  
<span data-ttu-id="dcf8e-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="dcf8e-105">\<identityConfiguration></span></span>  
<span data-ttu-id="dcf8e-106">\<TokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="dcf8e-106">\<tokenReplayDetection></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcf8e-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="dcf8e-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a><span data-ttu-id="dcf8e-108">Typ</span><span class="sxs-lookup"><span data-stu-id="dcf8e-108">Type</span></span>  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dcf8e-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="dcf8e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="dcf8e-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dcf8e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dcf8e-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="dcf8e-111">Attributes</span></span>  
  
|<span data-ttu-id="dcf8e-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="dcf8e-112">Attribute</span></span>|<span data-ttu-id="dcf8e-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dcf8e-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dcf8e-114">enabled</span><span class="sxs-lookup"><span data-stu-id="dcf8e-114">enabled</span></span>|<span data-ttu-id="dcf8e-115">Ein Wert, der angibt, ob die Erkennung einer tokenmehrfachverwendung aktiviert ist. "true", um Token zu aktivieren. replay-Erkennung.</span><span class="sxs-lookup"><span data-stu-id="dcf8e-115">A value that specifies whether token replay detection is enabled; "true" to enable token replay detection.</span></span>|  
|<span data-ttu-id="dcf8e-116">expirationPeriod</span><span class="sxs-lookup"><span data-stu-id="dcf8e-116">expirationPeriod</span></span>|<span data-ttu-id="dcf8e-117">Ein <xref:System.TimeSpan> , der angibt, dass der Höchstmenge des Zeitraums, bevor ein Element als abgelaufen erachtet wird und aus dem Cache entfernt.</span><span class="sxs-lookup"><span data-stu-id="dcf8e-117">A <xref:System.TimeSpan> that specifies the maximum amount of time before an item is considered expired and removed from the cache.</span></span>  <span data-ttu-id="dcf8e-118">Weitere Informationen zur Vorgehensweise beim angeben <xref:System.TimeSpan> Werte finden Sie unter [Timespan-Werten](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="dcf8e-118">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dcf8e-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dcf8e-119">Child Elements</span></span>  
 <span data-ttu-id="dcf8e-120">Keiner</span><span class="sxs-lookup"><span data-stu-id="dcf8e-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dcf8e-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dcf8e-121">Parent Elements</span></span>  
  
|<span data-ttu-id="dcf8e-122">Element</span><span class="sxs-lookup"><span data-stu-id="dcf8e-122">Element</span></span>|<span data-ttu-id="dcf8e-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dcf8e-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dcf8e-124">\<IdentityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="dcf8e-124">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="dcf8e-125">Gibt die identitätseinstellungen der Servicelevel.</span><span class="sxs-lookup"><span data-stu-id="dcf8e-125">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="dcf8e-126">\<SecurityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="dcf8e-126">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="dcf8e-127">Stellt die Konfiguration für eine Auflistung der Tokenhandler.</span><span class="sxs-lookup"><span data-stu-id="dcf8e-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dcf8e-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dcf8e-128">Remarks</span></span>  
 <span data-ttu-id="dcf8e-129">Ein `<tokenReplayDetection>` Element kann angegeben werden, auf der Dienstebene unter der `<identityConfiguration>` Element oder die Sicherheitsstufe für die Auflistung von Tokenhandler unter der `<securityTokenHandlerConfiguration>` Element.</span><span class="sxs-lookup"><span data-stu-id="dcf8e-129">A `<tokenReplayDetection>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="dcf8e-130">Einstellungen für eine Auflistung der Tokenhandler überschreiben jene, die für den Dienst angegeben.</span><span class="sxs-lookup"><span data-stu-id="dcf8e-130">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="dcf8e-131">Der Typ der tokenwiedergabecache wird angegeben, durch die [ \<TokenReplayCache >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) Element.</span><span class="sxs-lookup"><span data-stu-id="dcf8e-131">The type of the token replay cache is specified by the [\<tokenReplayCache>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) element.</span></span>
