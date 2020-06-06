---
title: <sessionTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: ade55a5b26826633faf2e7ef7598a4071d613bbc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152540"
---
# \<sessionTokenRequirement>
<span data-ttu-id="3735b-101">Stellt die Konfiguration für die- <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> Klasse oder abgeleitete Klassen bereit.</span><span class="sxs-lookup"><span data-stu-id="3735b-101">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionTokenRequirement>**  
  
## <a name="syntax"></a><span data-ttu-id="3735b-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="3735b-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">  
        <sessionTokenRequirement lifetime=TimeSpan >  
        </sessionTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3735b-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3735b-103">Attributes and Elements</span></span>  
 <span data-ttu-id="3735b-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3735b-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3735b-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="3735b-105">Attributes</span></span>  
  
|<span data-ttu-id="3735b-106">attribute</span><span class="sxs-lookup"><span data-stu-id="3735b-106">Attribute</span></span>|<span data-ttu-id="3735b-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3735b-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3735b-108">lifetime</span><span class="sxs-lookup"><span data-stu-id="3735b-108">lifetime</span></span>|<span data-ttu-id="3735b-109">Gibt die Lebensdauer von Sitzungs Token an.</span><span class="sxs-lookup"><span data-stu-id="3735b-109">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3735b-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3735b-110">Child Elements</span></span>  
 <span data-ttu-id="3735b-111">Keine</span><span class="sxs-lookup"><span data-stu-id="3735b-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3735b-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3735b-112">Parent Elements</span></span>  
  
|<span data-ttu-id="3735b-113">Element</span><span class="sxs-lookup"><span data-stu-id="3735b-113">Element</span></span>|<span data-ttu-id="3735b-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3735b-114">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add.md)|<span data-ttu-id="3735b-115">Fügt der tokenhandlerauflistung den angegebenen Sicherheitstokenhandler hinzu.</span><span class="sxs-lookup"><span data-stu-id="3735b-115">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3735b-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3735b-116">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
