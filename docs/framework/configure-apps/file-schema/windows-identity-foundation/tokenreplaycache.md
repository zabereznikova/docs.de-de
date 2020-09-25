---
title: <tokenReplayCache>
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: 5e695bb56b59da40ce9e83f9f4f77d0d22d0b40f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202421"
---
# \<tokenReplayCache>

<span data-ttu-id="8a12f-101">Registriert einen tokenwiedergabe-Cache bei einem Dienst oder einer Sammlung von Sicherheitstokenhandlern.</span><span class="sxs-lookup"><span data-stu-id="8a12f-101">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayCache>**  
  
## <a name="syntax"></a><span data-ttu-id="8a12f-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="8a12f-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8a12f-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8a12f-103">Attributes and Elements</span></span>  

 <span data-ttu-id="8a12f-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8a12f-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8a12f-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="8a12f-105">Attributes</span></span>  
  
|<span data-ttu-id="8a12f-106">attribute</span><span class="sxs-lookup"><span data-stu-id="8a12f-106">Attribute</span></span>|<span data-ttu-id="8a12f-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8a12f-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8a12f-108">type</span><span class="sxs-lookup"><span data-stu-id="8a12f-108">type</span></span>|<span data-ttu-id="8a12f-109">Ein Typ, der von der-Klasse abgeleitet wird <xref:System.IdentityModel.Tokens.TokenReplayCache> .</span><span class="sxs-lookup"><span data-stu-id="8a12f-109">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="8a12f-110">Weitere Informationen zum Angeben eines benutzerdefinierten finden Sie `type` unter [Custom Type References].</span><span class="sxs-lookup"><span data-stu-id="8a12f-110">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="8a12f-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8a12f-111">Child Elements</span></span>  

 <span data-ttu-id="8a12f-112">Keine</span><span class="sxs-lookup"><span data-stu-id="8a12f-112">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8a12f-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8a12f-113">Parent Elements</span></span>  
  
|<span data-ttu-id="8a12f-114">Element</span><span class="sxs-lookup"><span data-stu-id="8a12f-114">Element</span></span>|<span data-ttu-id="8a12f-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8a12f-115">Description</span></span>|  
|-------------|-----------------|  
|[\<caches>](caches.md)|<span data-ttu-id="8a12f-116">Registriert die von einem Dienst oder einer sicherheitstokenhandlerauflistung verwendeten Caches.</span><span class="sxs-lookup"><span data-stu-id="8a12f-116">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a12f-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="8a12f-117">Remarks</span></span>  

 <span data-ttu-id="8a12f-118">Der tokenwiedergabe-Cache wird verwendet, um wiedergegebene Token zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="8a12f-118">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="8a12f-119">Die Erkennung von tokenreplay wird durch das- [\<tokenReplayDetection>](tokenreplaydetection.md) Element aktiviert, das auch die maximale Ablaufzeit für Tokens angibt.</span><span class="sxs-lookup"><span data-stu-id="8a12f-119">Token replay detection is enabled by the [\<tokenReplayDetection>](tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a12f-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8a12f-120">Example</span></span>  

 <span data-ttu-id="8a12f-121">Der folgende XML-Code zeigt die Konfiguration eines benutzerdefinierten Caches zum Erkennen von wiedergegebenen Token.</span><span class="sxs-lookup"><span data-stu-id="8a12f-121">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8a12f-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8a12f-122">See also</span></span>

- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [\<tokenReplayDetection>](tokenreplaydetection.md)
