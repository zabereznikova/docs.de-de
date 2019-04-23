---
title: <tokenReplayCache>
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: 1567c669b5e682a7a771d7bedc95a8effa474e36
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59113385"
---
# <a name="tokenreplaycache"></a><span data-ttu-id="74a06-101">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="74a06-101">\<tokenReplayCache></span></span>
<span data-ttu-id="74a06-102">Registriert einen tokenwiederholungscache mit einem Dienst oder ein Sicherheitstoken-Handlerauflistung an.</span><span class="sxs-lookup"><span data-stu-id="74a06-102">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="74a06-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="74a06-103">\<system.identityModel></span></span>  
<span data-ttu-id="74a06-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="74a06-104">\<identityConfiguration></span></span>  
<span data-ttu-id="74a06-105">\<caches></span><span class="sxs-lookup"><span data-stu-id="74a06-105">\<caches></span></span>  
<span data-ttu-id="74a06-106">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="74a06-106">\<tokenReplayCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74a06-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="74a06-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="74a06-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="74a06-108">Attributes and Elements</span></span>  
 <span data-ttu-id="74a06-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="74a06-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="74a06-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="74a06-110">Attributes</span></span>  
  
|<span data-ttu-id="74a06-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="74a06-111">Attribute</span></span>|<span data-ttu-id="74a06-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="74a06-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="74a06-113">Typ</span><span class="sxs-lookup"><span data-stu-id="74a06-113">type</span></span>|<span data-ttu-id="74a06-114">Ein Typ, der von abgeleitet ist die <xref:System.IdentityModel.Tokens.TokenReplayCache> Klasse.</span><span class="sxs-lookup"><span data-stu-id="74a06-114">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="74a06-115">Weitere Informationen zur Vorgehensweise beim Angeben eines benutzerdefiniertes `type`, finden Sie unter [benutzerdefinierte Typverweise].</span><span class="sxs-lookup"><span data-stu-id="74a06-115">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="74a06-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="74a06-116">Child Elements</span></span>  
 <span data-ttu-id="74a06-117">Keiner</span><span class="sxs-lookup"><span data-stu-id="74a06-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="74a06-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="74a06-118">Parent Elements</span></span>  
  
|<span data-ttu-id="74a06-119">Element</span><span class="sxs-lookup"><span data-stu-id="74a06-119">Element</span></span>|<span data-ttu-id="74a06-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="74a06-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="74a06-121">\<caches></span><span class="sxs-lookup"><span data-stu-id="74a06-121">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="74a06-122">Registriert die Caches, die von einem Dienst oder ein Sicherheitstoken-Handlerauflistung verwendet.</span><span class="sxs-lookup"><span data-stu-id="74a06-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74a06-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="74a06-123">Remarks</span></span>  
 <span data-ttu-id="74a06-124">Tokenwiederholungs-Cache wird verwendet, um wiedergegebene Token erkennen.</span><span class="sxs-lookup"><span data-stu-id="74a06-124">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="74a06-125">Erkennung von tokenwiederholungen ist aktiviert, die [ \<TokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) Element, das auch die maximale Ablaufzeit für Token angibt.</span><span class="sxs-lookup"><span data-stu-id="74a06-125">Token replay detection is enabled by the [\<tokenReplayDetection>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74a06-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="74a06-126">Example</span></span>  
 <span data-ttu-id="74a06-127">Das folgende XML zeigt die Konfiguration eines benutzerdefinierten Cache für wiedergegebene Token erkennen.</span><span class="sxs-lookup"><span data-stu-id="74a06-127">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="74a06-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74a06-128">See also</span></span>

- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [<span data-ttu-id="74a06-129">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="74a06-129">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)
