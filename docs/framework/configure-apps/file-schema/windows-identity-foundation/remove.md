---
title: <remove>
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
ms.openlocfilehash: 7581f581c4b97a07eb4bdeb49eb5ae5ce72c2aa7
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90535715"
---
# \<remove>
<span data-ttu-id="ab6aa-101">Entfernt den angegebenen Sicherheitstokenhandler aus der tokenhandlerauflistung.</span><span class="sxs-lookup"><span data-stu-id="ab6aa-101">Removes the specified security token handler from the token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**  
  
## <a name="syntax"></a><span data-ttu-id="ab6aa-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="ab6aa-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ab6aa-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ab6aa-103">Attributes and Elements</span></span>  
 <span data-ttu-id="ab6aa-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ab6aa-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ab6aa-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="ab6aa-105">Attributes</span></span>  
  
|<span data-ttu-id="ab6aa-106">attribute</span><span class="sxs-lookup"><span data-stu-id="ab6aa-106">Attribute</span></span>|<span data-ttu-id="ab6aa-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ab6aa-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ab6aa-108">type</span><span class="sxs-lookup"><span data-stu-id="ab6aa-108">type</span></span>|<span data-ttu-id="ab6aa-109">Der CLR-Typname des tokenhandlers, der entfernt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ab6aa-109">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="ab6aa-110">Weitere Informationen zum Angeben des- `type` Attributs finden Sie unter [benutzerdefinierte Typverweise](/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span><span class="sxs-lookup"><span data-stu-id="ab6aa-110">For more information about how to specify the `type` attribute, see [Custom Type References](/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span> <span data-ttu-id="ab6aa-111">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ab6aa-111">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ab6aa-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ab6aa-112">Child Elements</span></span>  
 <span data-ttu-id="ab6aa-113">Keine</span><span class="sxs-lookup"><span data-stu-id="ab6aa-113">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ab6aa-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ab6aa-114">Parent Elements</span></span>  
  
|<span data-ttu-id="ab6aa-115">Element</span><span class="sxs-lookup"><span data-stu-id="ab6aa-115">Element</span></span>|<span data-ttu-id="ab6aa-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ab6aa-116">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|<span data-ttu-id="ab6aa-117">Gibt eine Auflistung von Sicherheitstokenhandlern an, die beim Endpunkt registriert sind.</span><span class="sxs-lookup"><span data-stu-id="ab6aa-117">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ab6aa-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ab6aa-118">Example</span></span>  
 <span data-ttu-id="ab6aa-119">Der folgende XML-Code zeigt die Verwendung des `<add>` -Elements und des- `<remove>` Elements, um den standardsitzungstokenhandler durch einen benutzerdefinierten Sitzungs Token-Handler</span><span class="sxs-lookup"><span data-stu-id="ab6aa-119">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="ab6aa-120">Der XML-Code stammt aus dem `ClaimsAwareWebFarm` Beispiel.</span><span class="sxs-lookup"><span data-stu-id="ab6aa-120">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
