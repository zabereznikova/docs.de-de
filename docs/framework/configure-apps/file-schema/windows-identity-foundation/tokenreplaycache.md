---
title: <tokenReplayCache>
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: 5747a4cfa93118dd41292904b168bbef02fec415
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944079"
---
# <a name="tokenreplaycache"></a><span data-ttu-id="dc4f7-101">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="dc4f7-101">\<tokenReplayCache></span></span>
<span data-ttu-id="dc4f7-102">Registriert einen tokenwiedergabe-Cache bei einem Dienst oder einer Sammlung von Sicherheitstokenhandlern.</span><span class="sxs-lookup"><span data-stu-id="dc4f7-102">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="dc4f7-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="dc4f7-103">\<system.identityModel></span></span>  
<span data-ttu-id="dc4f7-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="dc4f7-104">\<identityConfiguration></span></span>  
<span data-ttu-id="dc4f7-105">\<Caches ></span><span class="sxs-lookup"><span data-stu-id="dc4f7-105">\<caches></span></span>  
<span data-ttu-id="dc4f7-106">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="dc4f7-106">\<tokenReplayCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc4f7-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="dc4f7-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dc4f7-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="dc4f7-108">Attributes and Elements</span></span>  
 <span data-ttu-id="dc4f7-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dc4f7-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dc4f7-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="dc4f7-110">Attributes</span></span>  
  
|<span data-ttu-id="dc4f7-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="dc4f7-111">Attribute</span></span>|<span data-ttu-id="dc4f7-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dc4f7-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dc4f7-113">Typ</span><span class="sxs-lookup"><span data-stu-id="dc4f7-113">type</span></span>|<span data-ttu-id="dc4f7-114">Ein Typ, der von der <xref:System.IdentityModel.Tokens.TokenReplayCache> -Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="dc4f7-114">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="dc4f7-115">Weitere Informationen zum Angeben eines benutzerdefinierten `type`finden Sie unter [Custom Type References].</span><span class="sxs-lookup"><span data-stu-id="dc4f7-115">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="dc4f7-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dc4f7-116">Child Elements</span></span>  
 <span data-ttu-id="dc4f7-117">None</span><span class="sxs-lookup"><span data-stu-id="dc4f7-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dc4f7-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dc4f7-118">Parent Elements</span></span>  
  
|<span data-ttu-id="dc4f7-119">Element</span><span class="sxs-lookup"><span data-stu-id="dc4f7-119">Element</span></span>|<span data-ttu-id="dc4f7-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dc4f7-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dc4f7-121">\<caches></span><span class="sxs-lookup"><span data-stu-id="dc4f7-121">\<caches></span></span>](caches.md)|<span data-ttu-id="dc4f7-122">Registriert die von einem Dienst oder einer sicherheitstokenhandlerauflistung verwendeten Caches.</span><span class="sxs-lookup"><span data-stu-id="dc4f7-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc4f7-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dc4f7-123">Remarks</span></span>  
 <span data-ttu-id="dc4f7-124">Der tokenwiedergabe-Cache wird verwendet, um wiedergegebene Token zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="dc4f7-124">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="dc4f7-125">Die Erkennung der tokenwiedergabe wird durch das [ \<tokenreplayerkennungs->](tokenreplaydetection.md) -Element aktiviert, das auch die maximale Ablaufzeit für Tokens angibt.</span><span class="sxs-lookup"><span data-stu-id="dc4f7-125">Token replay detection is enabled by the [\<tokenReplayDetection>](tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc4f7-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dc4f7-126">Example</span></span>  
 <span data-ttu-id="dc4f7-127">Der folgende XML-Code zeigt die Konfiguration eines benutzerdefinierten Caches zum Erkennen von wiedergegebenen Token.</span><span class="sxs-lookup"><span data-stu-id="dc4f7-127">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="dc4f7-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dc4f7-128">See also</span></span>

- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [<span data-ttu-id="dc4f7-129">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="dc4f7-129">\<tokenReplayDetection></span></span>](tokenreplaydetection.md)
