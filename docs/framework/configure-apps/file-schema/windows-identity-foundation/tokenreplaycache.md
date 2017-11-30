---
title: '&lt;tokenReplayCache&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: e43e79416ddb8862cbc6e52d9d449a02b123af83
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="lttokenreplaycachegt"></a><span data-ttu-id="f4877-102">&lt;tokenReplayCache&gt;</span><span class="sxs-lookup"><span data-stu-id="f4877-102">&lt;tokenReplayCache&gt;</span></span>
<span data-ttu-id="f4877-103">Registriert einen token-Replay-Cache mit einem Dienst oder einer Sicherheit Tokenhandler-Auflistung.</span><span class="sxs-lookup"><span data-stu-id="f4877-103">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="f4877-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="f4877-104">\<system.identityModel></span></span>  
<span data-ttu-id="f4877-105">\<IdentityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="f4877-105">\<identityConfiguration></span></span>  
<span data-ttu-id="f4877-106">\<Speichert ></span><span class="sxs-lookup"><span data-stu-id="f4877-106">\<caches></span></span>  
<span data-ttu-id="f4877-107">\<TokenReplayCache ></span><span class="sxs-lookup"><span data-stu-id="f4877-107">\<tokenReplayCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4877-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="f4877-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f4877-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f4877-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f4877-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f4877-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f4877-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="f4877-111">Attributes</span></span>  
  
|<span data-ttu-id="f4877-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="f4877-112">Attribute</span></span>|<span data-ttu-id="f4877-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f4877-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f4877-114">Typ</span><span class="sxs-lookup"><span data-stu-id="f4877-114">type</span></span>|<span data-ttu-id="f4877-115">Ein Typ, der von abgeleitet ist die <xref:System.IdentityModel.Tokens.TokenReplayCache> Klasse.</span><span class="sxs-lookup"><span data-stu-id="f4877-115">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="f4877-116">Weitere Informationen über das Angeben eines benutzerdefiniertes `type`, finden Sie unter [benutzerdefinierte Typverweise].</span><span class="sxs-lookup"><span data-stu-id="f4877-116">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="f4877-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f4877-117">Child Elements</span></span>  
 <span data-ttu-id="f4877-118">Keine</span><span class="sxs-lookup"><span data-stu-id="f4877-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f4877-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f4877-119">Parent Elements</span></span>  
  
|<span data-ttu-id="f4877-120">Element</span><span class="sxs-lookup"><span data-stu-id="f4877-120">Element</span></span>|<span data-ttu-id="f4877-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f4877-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f4877-122">\<Speichert ></span><span class="sxs-lookup"><span data-stu-id="f4877-122">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="f4877-123">Registriert die Caches, die von einem Dienst oder eine Auflistung der Security-Tokenhandler verwendet.</span><span class="sxs-lookup"><span data-stu-id="f4877-123">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f4877-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f4877-124">Remarks</span></span>  
 <span data-ttu-id="f4877-125">Die token-Replay-Cache wird verwendet, wiedergegebene Token erkannt.</span><span class="sxs-lookup"><span data-stu-id="f4877-125">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="f4877-126">Tokenwiedergabeerkennung wird aktiviert, indem die [ \<TokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) Element, das auch die maximale Ablaufzeit für Token angibt.</span><span class="sxs-lookup"><span data-stu-id="f4877-126">Token replay detection is enabled by the [\<tokenReplayDetection>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4877-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f4877-127">Example</span></span>  
 <span data-ttu-id="f4877-128">Das folgende XML zeigt die Konfiguration eines benutzerdefinierten Caches zum Erkennen von wiedergegebenen Token.</span><span class="sxs-lookup"><span data-stu-id="f4877-128">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f4877-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f4877-129">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.TokenReplayCache>  
 [<span data-ttu-id="f4877-130">\<TokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="f4877-130">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)
