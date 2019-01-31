---
title: <remove>
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
ms.openlocfilehash: a54957458311e2d5941d1aa1c2486a2f66994d9b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55288131"
---
# <a name="remove"></a><span data-ttu-id="ec4a5-101">\<remove></span><span class="sxs-lookup"><span data-stu-id="ec4a5-101">\<remove></span></span>
<span data-ttu-id="ec4a5-102">Entfernt den angegebene Sicherheitstoken-Handler aus der Auflistung der Tokenhandler.</span><span class="sxs-lookup"><span data-stu-id="ec4a5-102">Removes the specified security token handler from the token handler collection.</span></span>  
  
 <span data-ttu-id="ec4a5-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="ec4a5-103">\<system.identityModel></span></span>  
<span data-ttu-id="ec4a5-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="ec4a5-104">\<identityConfiguration></span></span>  
<span data-ttu-id="ec4a5-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="ec4a5-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="ec4a5-106">\<remove></span><span class="sxs-lookup"><span data-stu-id="ec4a5-106">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec4a5-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="ec4a5-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ec4a5-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ec4a5-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ec4a5-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ec4a5-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ec4a5-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="ec4a5-110">Attributes</span></span>  
  
|<span data-ttu-id="ec4a5-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="ec4a5-111">Attribute</span></span>|<span data-ttu-id="ec4a5-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ec4a5-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ec4a5-113">Typ</span><span class="sxs-lookup"><span data-stu-id="ec4a5-113">type</span></span>|<span data-ttu-id="ec4a5-114">Die CLR-Typnamen, der die token-Handler entfernt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ec4a5-114">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="ec4a5-115">Weitere Informationen zur Vorgehensweise beim Angeben der `type` Attribut, finden Sie unter [benutzerdefinierte Typverweise](https://msdn.microsoft.com/library/7286d2e3-c63d-49fd-abdc-ce2705f22c24).</span><span class="sxs-lookup"><span data-stu-id="ec4a5-115">For more information about how to specify the `type` attribute, see [Custom Type References](https://msdn.microsoft.com/library/7286d2e3-c63d-49fd-abdc-ce2705f22c24).</span></span> <span data-ttu-id="ec4a5-116">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ec4a5-116">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ec4a5-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ec4a5-117">Child Elements</span></span>  
 <span data-ttu-id="ec4a5-118">Keine</span><span class="sxs-lookup"><span data-stu-id="ec4a5-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ec4a5-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ec4a5-119">Parent Elements</span></span>  
  
|<span data-ttu-id="ec4a5-120">Element</span><span class="sxs-lookup"><span data-stu-id="ec4a5-120">Element</span></span>|<span data-ttu-id="ec4a5-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ec4a5-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ec4a5-122">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="ec4a5-122">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="ec4a5-123">Gibt eine Auflistung von sicherheitstokenhandlern, die mit dem Endpunkt registriert sind.</span><span class="sxs-lookup"><span data-stu-id="ec4a5-123">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ec4a5-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ec4a5-124">Example</span></span>  
 <span data-ttu-id="ec4a5-125">Das folgende XML zeigt die Verwendung der `<add>` und `<remove>` Elementen, die dem Sicherheitstoken Standardhandler für Sitzung durch einen benutzerdefinierten sitzungentokenhandlers ersetzen.</span><span class="sxs-lookup"><span data-stu-id="ec4a5-125">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="ec4a5-126">Der XML-Code stammt aus dem `ClaimsAwareWebFarm` Beispiel.</span><span class="sxs-lookup"><span data-stu-id="ec4a5-126">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
