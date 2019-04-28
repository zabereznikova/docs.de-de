---
title: <remove>
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
ms.openlocfilehash: 17c4d4289cf90b66d52986c054d4807ecff2b3d8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793886"
---
# <a name="remove"></a><span data-ttu-id="2a33d-101">\<remove></span><span class="sxs-lookup"><span data-stu-id="2a33d-101">\<remove></span></span>
<span data-ttu-id="2a33d-102">Entfernt den angegebene Sicherheitstoken-Handler aus der Auflistung der Tokenhandler.</span><span class="sxs-lookup"><span data-stu-id="2a33d-102">Removes the specified security token handler from the token handler collection.</span></span>  
  
 <span data-ttu-id="2a33d-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="2a33d-103">\<system.identityModel></span></span>  
<span data-ttu-id="2a33d-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="2a33d-104">\<identityConfiguration></span></span>  
<span data-ttu-id="2a33d-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="2a33d-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="2a33d-106">\<remove></span><span class="sxs-lookup"><span data-stu-id="2a33d-106">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a33d-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="2a33d-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2a33d-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2a33d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2a33d-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2a33d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2a33d-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="2a33d-110">Attributes</span></span>  
  
|<span data-ttu-id="2a33d-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="2a33d-111">Attribute</span></span>|<span data-ttu-id="2a33d-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2a33d-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2a33d-113">Typ</span><span class="sxs-lookup"><span data-stu-id="2a33d-113">type</span></span>|<span data-ttu-id="2a33d-114">Die CLR-Typnamen, der die token-Handler entfernt werden soll.</span><span class="sxs-lookup"><span data-stu-id="2a33d-114">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="2a33d-115">Weitere Informationen zur Vorgehensweise beim Angeben der `type` Attribut, finden Sie unter [benutzerdefinierte Typverweise](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span><span class="sxs-lookup"><span data-stu-id="2a33d-115">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span> <span data-ttu-id="2a33d-116">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2a33d-116">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2a33d-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2a33d-117">Child Elements</span></span>  
 <span data-ttu-id="2a33d-118">Keiner</span><span class="sxs-lookup"><span data-stu-id="2a33d-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2a33d-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2a33d-119">Parent Elements</span></span>  
  
|<span data-ttu-id="2a33d-120">Element</span><span class="sxs-lookup"><span data-stu-id="2a33d-120">Element</span></span>|<span data-ttu-id="2a33d-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2a33d-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2a33d-122">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="2a33d-122">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="2a33d-123">Gibt eine Auflistung von sicherheitstokenhandlern, die mit dem Endpunkt registriert sind.</span><span class="sxs-lookup"><span data-stu-id="2a33d-123">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2a33d-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2a33d-124">Example</span></span>  
 <span data-ttu-id="2a33d-125">Das folgende XML zeigt die Verwendung der `<add>` und `<remove>` Elementen, die dem Sicherheitstoken Standardhandler für Sitzung durch einen benutzerdefinierten sitzungentokenhandlers ersetzen.</span><span class="sxs-lookup"><span data-stu-id="2a33d-125">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="2a33d-126">Der XML-Code stammt aus dem `ClaimsAwareWebFarm` Beispiel.</span><span class="sxs-lookup"><span data-stu-id="2a33d-126">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
