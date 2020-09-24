---
title: <sessionTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: 4560c55cee5caf975e83ce9d4dc0b379ab905f8d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156848"
---
# \<sessionTokenRequirement>

<span data-ttu-id="42b7d-101">Stellt die Konfiguration für die- <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> Klasse oder abgeleitete Klassen bereit.</span><span class="sxs-lookup"><span data-stu-id="42b7d-101">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionTokenRequirement>**  
  
## <a name="syntax"></a><span data-ttu-id="42b7d-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="42b7d-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="42b7d-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="42b7d-103">Attributes and Elements</span></span>  

 <span data-ttu-id="42b7d-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="42b7d-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="42b7d-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="42b7d-105">Attributes</span></span>  
  
|<span data-ttu-id="42b7d-106">attribute</span><span class="sxs-lookup"><span data-stu-id="42b7d-106">Attribute</span></span>|<span data-ttu-id="42b7d-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="42b7d-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="42b7d-108">lifetime</span><span class="sxs-lookup"><span data-stu-id="42b7d-108">lifetime</span></span>|<span data-ttu-id="42b7d-109">Gibt die Lebensdauer von Sitzungs Token an.</span><span class="sxs-lookup"><span data-stu-id="42b7d-109">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="42b7d-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="42b7d-110">Child Elements</span></span>  

 <span data-ttu-id="42b7d-111">Keine</span><span class="sxs-lookup"><span data-stu-id="42b7d-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="42b7d-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="42b7d-112">Parent Elements</span></span>  
  
|<span data-ttu-id="42b7d-113">Element</span><span class="sxs-lookup"><span data-stu-id="42b7d-113">Element</span></span>|<span data-ttu-id="42b7d-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="42b7d-114">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add.md)|<span data-ttu-id="42b7d-115">Fügt der tokenhandlerauflistung den angegebenen Sicherheitstokenhandler hinzu.</span><span class="sxs-lookup"><span data-stu-id="42b7d-115">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="42b7d-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="42b7d-116">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
