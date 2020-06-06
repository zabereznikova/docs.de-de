---
title: <tokenReplayCache>
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: 9f3a95fd0a39f199eaf13c7509aff22caa0e3b66
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251787"
---
# \<tokenReplayCache>
<span data-ttu-id="ce9a6-101">Registriert einen tokenwiedergabe-Cache bei einem Dienst oder einer Sammlung von Sicherheitstokenhandlern.</span><span class="sxs-lookup"><span data-stu-id="ce9a6-101">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayCache>**  
  
## <a name="syntax"></a><span data-ttu-id="ce9a6-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="ce9a6-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ce9a6-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ce9a6-103">Attributes and Elements</span></span>  
 <span data-ttu-id="ce9a6-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ce9a6-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ce9a6-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="ce9a6-105">Attributes</span></span>  
  
|<span data-ttu-id="ce9a6-106">attribute</span><span class="sxs-lookup"><span data-stu-id="ce9a6-106">Attribute</span></span>|<span data-ttu-id="ce9a6-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ce9a6-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ce9a6-108">type</span><span class="sxs-lookup"><span data-stu-id="ce9a6-108">type</span></span>|<span data-ttu-id="ce9a6-109">Ein Typ, der von der-Klasse abgeleitet wird <xref:System.IdentityModel.Tokens.TokenReplayCache> .</span><span class="sxs-lookup"><span data-stu-id="ce9a6-109">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="ce9a6-110">Weitere Informationen zum Angeben eines benutzerdefinierten finden Sie `type` unter [Custom Type References].</span><span class="sxs-lookup"><span data-stu-id="ce9a6-110">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="ce9a6-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ce9a6-111">Child Elements</span></span>  
 <span data-ttu-id="ce9a6-112">Keine</span><span class="sxs-lookup"><span data-stu-id="ce9a6-112">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ce9a6-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ce9a6-113">Parent Elements</span></span>  
  
|<span data-ttu-id="ce9a6-114">Element</span><span class="sxs-lookup"><span data-stu-id="ce9a6-114">Element</span></span>|<span data-ttu-id="ce9a6-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ce9a6-115">Description</span></span>|  
|-------------|-----------------|  
|[\<caches>](caches.md)|<span data-ttu-id="ce9a6-116">Registriert die von einem Dienst oder einer sicherheitstokenhandlerauflistung verwendeten Caches.</span><span class="sxs-lookup"><span data-stu-id="ce9a6-116">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce9a6-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ce9a6-117">Remarks</span></span>  
 <span data-ttu-id="ce9a6-118">Der tokenwiedergabe-Cache wird verwendet, um wiedergegebene Token zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="ce9a6-118">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="ce9a6-119">Die Erkennung von tokenreplay wird durch das- [\<tokenReplayDetection>](tokenreplaydetection.md) Element aktiviert, das auch die maximale Ablaufzeit für Tokens angibt.</span><span class="sxs-lookup"><span data-stu-id="ce9a6-119">Token replay detection is enabled by the [\<tokenReplayDetection>](tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce9a6-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ce9a6-120">Example</span></span>  
 <span data-ttu-id="ce9a6-121">Der folgende XML-Code zeigt die Konfiguration eines benutzerdefinierten Caches zum Erkennen von wiedergegebenen Token.</span><span class="sxs-lookup"><span data-stu-id="ce9a6-121">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ce9a6-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ce9a6-122">See also</span></span>

- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [\<tokenReplayDetection>](tokenreplaydetection.md)
