---
title: <remove>
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
ms.openlocfilehash: c4ba7b6f2a9b9092c5f24d424c6de2b0f510ac88
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164999"
---
# \<remove>

<span data-ttu-id="a1549-101">Entfernt den angegebenen Sicherheitstokenhandler aus der tokenhandlerauflistung.</span><span class="sxs-lookup"><span data-stu-id="a1549-101">Removes the specified security token handler from the token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**  
  
## <a name="syntax"></a><span data-ttu-id="a1549-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="a1549-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a1549-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a1549-103">Attributes and Elements</span></span>  

 <span data-ttu-id="a1549-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a1549-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a1549-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="a1549-105">Attributes</span></span>  
  
|<span data-ttu-id="a1549-106">attribute</span><span class="sxs-lookup"><span data-stu-id="a1549-106">Attribute</span></span>|<span data-ttu-id="a1549-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a1549-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a1549-108">type</span><span class="sxs-lookup"><span data-stu-id="a1549-108">type</span></span>|<span data-ttu-id="a1549-109">Der CLR-Typname des tokenhandlers, der entfernt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a1549-109">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="a1549-110">Weitere Informationen zum Angeben des- `type` Attributs finden Sie unter [benutzerdefinierte Typverweise](/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span><span class="sxs-lookup"><span data-stu-id="a1549-110">For more information about how to specify the `type` attribute, see [Custom Type References](/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span> <span data-ttu-id="a1549-111">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a1549-111">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a1549-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a1549-112">Child Elements</span></span>  

 <span data-ttu-id="a1549-113">Keine</span><span class="sxs-lookup"><span data-stu-id="a1549-113">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a1549-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a1549-114">Parent Elements</span></span>  
  
|<span data-ttu-id="a1549-115">Element</span><span class="sxs-lookup"><span data-stu-id="a1549-115">Element</span></span>|<span data-ttu-id="a1549-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a1549-116">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|<span data-ttu-id="a1549-117">Gibt eine Auflistung von Sicherheitstokenhandlern an, die beim Endpunkt registriert sind.</span><span class="sxs-lookup"><span data-stu-id="a1549-117">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a1549-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a1549-118">Example</span></span>  

 <span data-ttu-id="a1549-119">Der folgende XML-Code zeigt die Verwendung des `<add>` -Elements und des- `<remove>` Elements, um den standardsitzungstokenhandler durch einen benutzerdefinierten Sitzungs Token-Handler</span><span class="sxs-lookup"><span data-stu-id="a1549-119">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="a1549-120">Der XML-Code stammt aus dem `ClaimsAwareWebFarm` Beispiel.</span><span class="sxs-lookup"><span data-stu-id="a1549-120">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
