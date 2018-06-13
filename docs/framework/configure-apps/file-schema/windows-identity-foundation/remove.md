---
title: '&lt;remove&gt;'
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: dfea0b0eb4b133308f10b523a659cc00f87252b8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755072"
---
# <a name="ltremovegt"></a><span data-ttu-id="6b30c-102">&lt;remove&gt;</span><span class="sxs-lookup"><span data-stu-id="6b30c-102">&lt;remove&gt;</span></span>
<span data-ttu-id="6b30c-103">Entfernt die angegebene Sicherheitsschlüssel-Tokenhandler aus der Auflistung Tokenhandler an.</span><span class="sxs-lookup"><span data-stu-id="6b30c-103">Removes the specified security token handler from the token handler collection.</span></span>  
  
 <span data-ttu-id="6b30c-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="6b30c-104">\<system.identityModel></span></span>  
<span data-ttu-id="6b30c-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="6b30c-105">\<identityConfiguration></span></span>  
<span data-ttu-id="6b30c-106">\<SecurityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="6b30c-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="6b30c-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="6b30c-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b30c-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="6b30c-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6b30c-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6b30c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="6b30c-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6b30c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6b30c-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="6b30c-111">Attributes</span></span>  
  
|<span data-ttu-id="6b30c-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="6b30c-112">Attribute</span></span>|<span data-ttu-id="6b30c-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6b30c-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6b30c-114">Typ</span><span class="sxs-lookup"><span data-stu-id="6b30c-114">type</span></span>|<span data-ttu-id="6b30c-115">Der CLR-Typname der der Tokenhandler entfernt werden soll.</span><span class="sxs-lookup"><span data-stu-id="6b30c-115">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="6b30c-116">Weitere Informationen zum Angeben der `type` -Attribut angegeben wird, finden Sie unter [benutzerdefinierte Typverweise](http://msdn.microsoft.com/library/7286d2e3-c63d-49fd-abdc-ce2705f22c24).</span><span class="sxs-lookup"><span data-stu-id="6b30c-116">For more information about how to specify the `type` attribute, see [Custom Type References](http://msdn.microsoft.com/library/7286d2e3-c63d-49fd-abdc-ce2705f22c24).</span></span> <span data-ttu-id="6b30c-117">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6b30c-117">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6b30c-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6b30c-118">Child Elements</span></span>  
 <span data-ttu-id="6b30c-119">Keiner</span><span class="sxs-lookup"><span data-stu-id="6b30c-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6b30c-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6b30c-120">Parent Elements</span></span>  
  
|<span data-ttu-id="6b30c-121">Element</span><span class="sxs-lookup"><span data-stu-id="6b30c-121">Element</span></span>|<span data-ttu-id="6b30c-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6b30c-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6b30c-123">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="6b30c-123">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="6b30c-124">Gibt eine Auflistung von sicherheitstokenhandlern, die mit dem Endpunkt registriert sind.</span><span class="sxs-lookup"><span data-stu-id="6b30c-124">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6b30c-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6b30c-125">Example</span></span>  
 <span data-ttu-id="6b30c-126">Das folgende XML zeigt die Verwendung der `<add>` und `<remove>` Elemente der Standardhandler für Sitzung token mit einer benutzerdefinierten-Sitzung Tokenhandler ersetzen.</span><span class="sxs-lookup"><span data-stu-id="6b30c-126">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="6b30c-127">Der XML-Code stammt aus dem `ClaimsAwareWebFarm` Beispiel.</span><span class="sxs-lookup"><span data-stu-id="6b30c-127">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
