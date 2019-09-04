---
title: <tokenReplayCache>
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: 9f3a95fd0a39f199eaf13c7509aff22caa0e3b66
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251787"
---
# <a name="tokenreplaycache"></a><span data-ttu-id="093aa-101">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="093aa-101">\<tokenReplayCache></span></span>
<span data-ttu-id="093aa-102">Registriert einen tokenwiedergabe-Cache bei einem Dienst oder einer Sammlung von Sicherheitstokenhandlern.</span><span class="sxs-lookup"><span data-stu-id="093aa-102">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
<span data-ttu-id="093aa-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="093aa-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="093aa-104">&nbsp;&nbsp;[ **\<System. IdentityModel->** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="093aa-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="093aa-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityconfiguration->** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="093aa-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="093aa-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Caches >** ](caches.md)</span><span class="sxs-lookup"><span data-stu-id="093aa-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)</span></span>\
<span data-ttu-id="093aa-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<tokenreplaycache->**</span><span class="sxs-lookup"><span data-stu-id="093aa-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayCache>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="093aa-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="093aa-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="093aa-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="093aa-109">Attributes and Elements</span></span>  
 <span data-ttu-id="093aa-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="093aa-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="093aa-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="093aa-111">Attributes</span></span>  
  
|<span data-ttu-id="093aa-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="093aa-112">Attribute</span></span>|<span data-ttu-id="093aa-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="093aa-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="093aa-114">Typ</span><span class="sxs-lookup"><span data-stu-id="093aa-114">type</span></span>|<span data-ttu-id="093aa-115">Ein Typ, der von der <xref:System.IdentityModel.Tokens.TokenReplayCache> -Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="093aa-115">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="093aa-116">Weitere Informationen zum Angeben eines benutzerdefinierten `type`finden Sie unter [Custom Type References].</span><span class="sxs-lookup"><span data-stu-id="093aa-116">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="093aa-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="093aa-117">Child Elements</span></span>  
 <span data-ttu-id="093aa-118">None</span><span class="sxs-lookup"><span data-stu-id="093aa-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="093aa-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="093aa-119">Parent Elements</span></span>  
  
|<span data-ttu-id="093aa-120">Element</span><span class="sxs-lookup"><span data-stu-id="093aa-120">Element</span></span>|<span data-ttu-id="093aa-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="093aa-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="093aa-122">\<caches></span><span class="sxs-lookup"><span data-stu-id="093aa-122">\<caches></span></span>](caches.md)|<span data-ttu-id="093aa-123">Registriert die von einem Dienst oder einer sicherheitstokenhandlerauflistung verwendeten Caches.</span><span class="sxs-lookup"><span data-stu-id="093aa-123">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="093aa-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="093aa-124">Remarks</span></span>  
 <span data-ttu-id="093aa-125">Der tokenwiedergabe-Cache wird verwendet, um wiedergegebene Token zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="093aa-125">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="093aa-126">Die Erkennung der [ \<tokenwiedergabe wird durch das tokenreplayerkennungs->](tokenreplaydetection.md) -Element aktiviert, das auch die maximale Ablaufzeit für Tokens angibt.</span><span class="sxs-lookup"><span data-stu-id="093aa-126">Token replay detection is enabled by the [\<tokenReplayDetection>](tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="093aa-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="093aa-127">Example</span></span>  
 <span data-ttu-id="093aa-128">Der folgende XML-Code zeigt die Konfiguration eines benutzerdefinierten Caches zum Erkennen von wiedergegebenen Token.</span><span class="sxs-lookup"><span data-stu-id="093aa-128">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="093aa-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="093aa-129">See also</span></span>

- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [<span data-ttu-id="093aa-130">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="093aa-130">\<tokenReplayDetection></span></span>](tokenreplaydetection.md)
