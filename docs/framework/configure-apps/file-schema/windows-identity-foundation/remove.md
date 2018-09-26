---
title: '&lt;remove&gt;'
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
ms.openlocfilehash: 410fef1a43f9202d56c4957b1162c53ee056ae3f
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2018
ms.locfileid: "47198721"
---
# <a name="ltremovegt"></a><span data-ttu-id="ca041-102">&lt;remove&gt;</span><span class="sxs-lookup"><span data-stu-id="ca041-102">&lt;remove&gt;</span></span>
<span data-ttu-id="ca041-103">Entfernt den angegebene Sicherheitstoken-Handler aus der Auflistung der Tokenhandler.</span><span class="sxs-lookup"><span data-stu-id="ca041-103">Removes the specified security token handler from the token handler collection.</span></span>  
  
 <span data-ttu-id="ca041-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="ca041-104">\<system.identityModel></span></span>  
<span data-ttu-id="ca041-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="ca041-105">\<identityConfiguration></span></span>  
<span data-ttu-id="ca041-106">\<SecurityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="ca041-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="ca041-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="ca041-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca041-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="ca041-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ca041-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ca041-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ca041-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ca041-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ca041-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="ca041-111">Attributes</span></span>  
  
|<span data-ttu-id="ca041-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="ca041-112">Attribute</span></span>|<span data-ttu-id="ca041-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ca041-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ca041-114">Typ</span><span class="sxs-lookup"><span data-stu-id="ca041-114">type</span></span>|<span data-ttu-id="ca041-115">Die CLR-Typnamen, der die token-Handler entfernt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ca041-115">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="ca041-116">Weitere Informationen zur Vorgehensweise beim Angeben der `type` Attribut, finden Sie unter [benutzerdefinierte Typverweise](https://msdn.microsoft.com/library/7286d2e3-c63d-49fd-abdc-ce2705f22c24).</span><span class="sxs-lookup"><span data-stu-id="ca041-116">For more information about how to specify the `type` attribute, see [Custom Type References](https://msdn.microsoft.com/library/7286d2e3-c63d-49fd-abdc-ce2705f22c24).</span></span> <span data-ttu-id="ca041-117">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ca041-117">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ca041-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ca041-118">Child Elements</span></span>  
 <span data-ttu-id="ca041-119">Keiner</span><span class="sxs-lookup"><span data-stu-id="ca041-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ca041-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ca041-120">Parent Elements</span></span>  
  
|<span data-ttu-id="ca041-121">Element</span><span class="sxs-lookup"><span data-stu-id="ca041-121">Element</span></span>|<span data-ttu-id="ca041-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ca041-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ca041-123">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="ca041-123">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="ca041-124">Gibt eine Auflistung von sicherheitstokenhandlern, die mit dem Endpunkt registriert sind.</span><span class="sxs-lookup"><span data-stu-id="ca041-124">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ca041-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ca041-125">Example</span></span>  
 <span data-ttu-id="ca041-126">Das folgende XML zeigt die Verwendung der `<add>` und `<remove>` Elementen, die dem Sicherheitstoken Standardhandler für Sitzung durch einen benutzerdefinierten sitzungentokenhandlers ersetzen.</span><span class="sxs-lookup"><span data-stu-id="ca041-126">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="ca041-127">Der XML-Code stammt aus dem `ClaimsAwareWebFarm` Beispiel.</span><span class="sxs-lookup"><span data-stu-id="ca041-127">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
