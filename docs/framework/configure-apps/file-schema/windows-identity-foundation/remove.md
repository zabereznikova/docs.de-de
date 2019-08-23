---
title: <remove>
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
ms.openlocfilehash: 11aeed0277fc13cbd9a65232311bd575a4a81ff7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942582"
---
# <a name="remove"></a><span data-ttu-id="d1607-101">\<remove></span><span class="sxs-lookup"><span data-stu-id="d1607-101">\<remove></span></span>
<span data-ttu-id="d1607-102">Entfernt den angegebenen Sicherheitstokenhandler aus der tokenhandlerauflistung.</span><span class="sxs-lookup"><span data-stu-id="d1607-102">Removes the specified security token handler from the token handler collection.</span></span>  
  
 <span data-ttu-id="d1607-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="d1607-103">\<system.identityModel></span></span>  
<span data-ttu-id="d1607-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="d1607-104">\<identityConfiguration></span></span>  
<span data-ttu-id="d1607-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="d1607-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="d1607-106">\<remove></span><span class="sxs-lookup"><span data-stu-id="d1607-106">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1607-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="d1607-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d1607-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d1607-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d1607-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d1607-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d1607-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="d1607-110">Attributes</span></span>  
  
|<span data-ttu-id="d1607-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="d1607-111">Attribute</span></span>|<span data-ttu-id="d1607-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d1607-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d1607-113">Typ</span><span class="sxs-lookup"><span data-stu-id="d1607-113">type</span></span>|<span data-ttu-id="d1607-114">Der CLR-Typname des tokenhandlers, der entfernt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d1607-114">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="d1607-115">Weitere Informationen zum Angeben des `type` -Attributs finden Sie unter [benutzerdefinierte Typverweise](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span><span class="sxs-lookup"><span data-stu-id="d1607-115">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span> <span data-ttu-id="d1607-116">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d1607-116">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d1607-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d1607-117">Child Elements</span></span>  
 <span data-ttu-id="d1607-118">None</span><span class="sxs-lookup"><span data-stu-id="d1607-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d1607-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d1607-119">Parent Elements</span></span>  
  
|<span data-ttu-id="d1607-120">Element</span><span class="sxs-lookup"><span data-stu-id="d1607-120">Element</span></span>|<span data-ttu-id="d1607-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d1607-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d1607-122">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="d1607-122">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="d1607-123">Gibt eine Auflistung von Sicherheitstokenhandlern an, die beim Endpunkt registriert sind.</span><span class="sxs-lookup"><span data-stu-id="d1607-123">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d1607-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d1607-124">Example</span></span>  
 <span data-ttu-id="d1607-125">Der folgende XML `<add>` -Code zeigt die Verwendung des `<remove>` -Elements und des-Elements, um den standardsitzungstokenhandler durch einen benutzerdefinierten Sitzungs Token-Handler</span><span class="sxs-lookup"><span data-stu-id="d1607-125">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="d1607-126">Der XML-Code stammt aus `ClaimsAwareWebFarm` dem Beispiel.</span><span class="sxs-lookup"><span data-stu-id="d1607-126">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
