---
title: <remove>
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
ms.openlocfilehash: cfdfbb3aabde253ad17b221801b20c1ac9a45c2d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251929"
---
# \<remove>
<span data-ttu-id="0d7f5-101">Entfernt den angegebenen Sicherheitstokenhandler aus der tokenhandlerauflistung.</span><span class="sxs-lookup"><span data-stu-id="0d7f5-101">Removes the specified security token handler from the token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**  
  
## <a name="syntax"></a><span data-ttu-id="0d7f5-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="0d7f5-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <remove type=xs:string >  
      </remove>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0d7f5-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0d7f5-103">Attributes and Elements</span></span>  
 <span data-ttu-id="0d7f5-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0d7f5-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0d7f5-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="0d7f5-105">Attributes</span></span>  
  
|<span data-ttu-id="0d7f5-106">attribute</span><span class="sxs-lookup"><span data-stu-id="0d7f5-106">Attribute</span></span>|<span data-ttu-id="0d7f5-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0d7f5-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0d7f5-108">type</span><span class="sxs-lookup"><span data-stu-id="0d7f5-108">type</span></span>|<span data-ttu-id="0d7f5-109">Der CLR-Typname des tokenhandlers, der entfernt werden soll.</span><span class="sxs-lookup"><span data-stu-id="0d7f5-109">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="0d7f5-110">Weitere Informationen zum Angeben des- `type` Attributs finden Sie unter [benutzerdefinierte Typverweise](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span><span class="sxs-lookup"><span data-stu-id="0d7f5-110">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span> <span data-ttu-id="0d7f5-111">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0d7f5-111">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0d7f5-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0d7f5-112">Child Elements</span></span>  
 <span data-ttu-id="0d7f5-113">Keine</span><span class="sxs-lookup"><span data-stu-id="0d7f5-113">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0d7f5-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0d7f5-114">Parent Elements</span></span>  
  
|<span data-ttu-id="0d7f5-115">Element</span><span class="sxs-lookup"><span data-stu-id="0d7f5-115">Element</span></span>|<span data-ttu-id="0d7f5-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0d7f5-116">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|<span data-ttu-id="0d7f5-117">Gibt eine Auflistung von Sicherheitstokenhandlern an, die beim Endpunkt registriert sind.</span><span class="sxs-lookup"><span data-stu-id="0d7f5-117">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0d7f5-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0d7f5-118">Example</span></span>  
 <span data-ttu-id="0d7f5-119">Der folgende XML-Code zeigt die Verwendung des `<add>` -Elements und des- `<remove>` Elements, um den standardsitzungstokenhandler durch einen benutzerdefinierten Sitzungs Token-Handler</span><span class="sxs-lookup"><span data-stu-id="0d7f5-119">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="0d7f5-120">Der XML-Code stammt aus dem `ClaimsAwareWebFarm` Beispiel.</span><span class="sxs-lookup"><span data-stu-id="0d7f5-120">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
