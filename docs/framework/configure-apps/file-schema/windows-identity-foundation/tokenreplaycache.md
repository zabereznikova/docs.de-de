---
title: '&lt;tokenReplayCache&gt;'
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: d21a819f789b5be4bdf7ebf57b37a072e1d213ff
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2018
ms.locfileid: "47206217"
---
# <a name="lttokenreplaycachegt"></a><span data-ttu-id="f1580-102">&lt;tokenReplayCache&gt;</span><span class="sxs-lookup"><span data-stu-id="f1580-102">&lt;tokenReplayCache&gt;</span></span>
<span data-ttu-id="f1580-103">Registriert einen tokenwiederholungscache mit einem Dienst oder ein Sicherheitstoken-Handlerauflistung an.</span><span class="sxs-lookup"><span data-stu-id="f1580-103">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="f1580-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="f1580-104">\<system.identityModel></span></span>  
<span data-ttu-id="f1580-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="f1580-105">\<identityConfiguration></span></span>  
<span data-ttu-id="f1580-106">\<Speichert ></span><span class="sxs-lookup"><span data-stu-id="f1580-106">\<caches></span></span>  
<span data-ttu-id="f1580-107">\<TokenReplayCache ></span><span class="sxs-lookup"><span data-stu-id="f1580-107">\<tokenReplayCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1580-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="f1580-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
      <tokenReplayCache type=xs:string>  
      </tokenReplayCache>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f1580-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f1580-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f1580-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f1580-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f1580-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="f1580-111">Attributes</span></span>  
  
|<span data-ttu-id="f1580-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="f1580-112">Attribute</span></span>|<span data-ttu-id="f1580-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f1580-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f1580-114">Typ</span><span class="sxs-lookup"><span data-stu-id="f1580-114">type</span></span>|<span data-ttu-id="f1580-115">Ein Typ, der von abgeleitet ist die <xref:System.IdentityModel.Tokens.TokenReplayCache> Klasse.</span><span class="sxs-lookup"><span data-stu-id="f1580-115">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="f1580-116">Weitere Informationen zur Vorgehensweise beim Angeben eines benutzerdefiniertes `type`, finden Sie unter [benutzerdefinierte Typverweise].</span><span class="sxs-lookup"><span data-stu-id="f1580-116">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="f1580-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f1580-117">Child Elements</span></span>  
 <span data-ttu-id="f1580-118">Keiner</span><span class="sxs-lookup"><span data-stu-id="f1580-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f1580-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f1580-119">Parent Elements</span></span>  
  
|<span data-ttu-id="f1580-120">Element</span><span class="sxs-lookup"><span data-stu-id="f1580-120">Element</span></span>|<span data-ttu-id="f1580-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f1580-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f1580-122">\<Speichert ></span><span class="sxs-lookup"><span data-stu-id="f1580-122">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="f1580-123">Registriert die Caches, die von einem Dienst oder ein Sicherheitstoken-Handlerauflistung verwendet.</span><span class="sxs-lookup"><span data-stu-id="f1580-123">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f1580-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f1580-124">Remarks</span></span>  
 <span data-ttu-id="f1580-125">Tokenwiederholungs-Cache wird verwendet, um wiedergegebene Token erkennen.</span><span class="sxs-lookup"><span data-stu-id="f1580-125">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="f1580-126">Erkennung von tokenwiederholungen ist aktiviert, die [ \<TokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) Element, das auch die maximale Ablaufzeit für Token angibt.</span><span class="sxs-lookup"><span data-stu-id="f1580-126">Token replay detection is enabled by the [\<tokenReplayDetection>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1580-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f1580-127">Example</span></span>  
 <span data-ttu-id="f1580-128">Das folgende XML zeigt die Konfiguration eines benutzerdefinierten Cache für wiedergegebene Token erkennen.</span><span class="sxs-lookup"><span data-stu-id="f1580-128">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f1580-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f1580-129">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.TokenReplayCache>  
 [<span data-ttu-id="f1580-130">\<TokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="f1580-130">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)
