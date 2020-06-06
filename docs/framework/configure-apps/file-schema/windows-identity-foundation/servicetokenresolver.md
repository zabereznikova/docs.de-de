---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 0983380e553acfe246d6b987784d818b8ae85b17
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152579"
---
# \<serviceTokenResolver>
<span data-ttu-id="c3327-101">Registriert den diensttokenresolver, der von Handlern in der tokenhandlerauflistung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c3327-101">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="c3327-102">Der diensttokenresolver wird verwendet, um das Verschlüsselungs Token für eingehende Token und Nachrichten aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="c3327-102">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTokenResolver>**  
  
## <a name="syntax"></a><span data-ttu-id="c3327-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="c3327-103">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <serviceTokenResolver type=xs:string>  
        </serviceTokenResolver>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c3327-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c3327-104">Attributes and Elements</span></span>  
 <span data-ttu-id="c3327-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c3327-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c3327-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="c3327-106">Attributes</span></span>  
  
|<span data-ttu-id="c3327-107">attribute</span><span class="sxs-lookup"><span data-stu-id="c3327-107">Attribute</span></span>|<span data-ttu-id="c3327-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c3327-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c3327-109">type</span><span class="sxs-lookup"><span data-stu-id="c3327-109">type</span></span>|<span data-ttu-id="c3327-110">Gibt den Typ des diensttokenresolvers an.</span><span class="sxs-lookup"><span data-stu-id="c3327-110">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="c3327-111">Entweder der <xref:System.IdentityModel.Selectors.SecurityTokenResolver> Typ oder ein Typ, der von der-Klasse abgeleitet wird <xref:System.IdentityModel.Selectors.SecurityTokenResolver> .</span><span class="sxs-lookup"><span data-stu-id="c3327-111">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="c3327-112">Weitere Informationen zum Angeben des- `type` Attributs finden Sie unter [Custom Type References].</span><span class="sxs-lookup"><span data-stu-id="c3327-112">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="c3327-113">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c3327-113">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c3327-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c3327-114">Child Elements</span></span>  
 <span data-ttu-id="c3327-115">Keine</span><span class="sxs-lookup"><span data-stu-id="c3327-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c3327-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c3327-116">Parent Elements</span></span>  
  
|<span data-ttu-id="c3327-117">Element</span><span class="sxs-lookup"><span data-stu-id="c3327-117">Element</span></span>|<span data-ttu-id="c3327-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c3327-118">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="c3327-119">Stellt die Konfiguration für eine Auflistung von Sicherheitstokenhandlern bereit.</span><span class="sxs-lookup"><span data-stu-id="c3327-119">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c3327-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c3327-120">Remarks</span></span>  
 <span data-ttu-id="c3327-121">Der diensttokenresolver kann verwendet werden, um das Verschlüsselungs Token für eingehende Token und Nachrichten aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="c3327-121">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="c3327-122">Sie wird verwendet, um den Schlüssel abzurufen, der zum Entschlüsseln eingehender Token verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c3327-122">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="c3327-123">Sie müssen das- `type` Attribut angeben.</span><span class="sxs-lookup"><span data-stu-id="c3327-123">You must specify the `type` attribute.</span></span> <span data-ttu-id="c3327-124">Der angegebene Typ kann entweder <xref:System.IdentityModel.Selectors.SecurityTokenResolver> oder ein benutzerdefinierter Typ sein, der von der-Klasse abgeleitet wird <xref:System.IdentityModel.Selectors.SecurityTokenResolver> .</span><span class="sxs-lookup"><span data-stu-id="c3327-124">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="c3327-125">Mit einigen tokenhandlern können Sie Einstellungen für den diensttokenresolver in der Konfiguration angeben.</span><span class="sxs-lookup"><span data-stu-id="c3327-125">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="c3327-126">Einstellungen in einzelnen tokenhandlern überschreiben die in der Auflistung der Sicherheitstokenhandler angegebenen.</span><span class="sxs-lookup"><span data-stu-id="c3327-126">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c3327-127">Die Angabe des- `<serviceTokenResolver>` Elements als untergeordnetes Element des-Elements wurde als [\<identityConfiguration>](identityconfiguration.md) veraltet markiert, wird jedoch aus Gründen der Abwärtskompatibilität weiterhin unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c3327-127">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="c3327-128">Die Einstellungen für das- `<securityTokenHandlerConfiguration>` Element überschreiben die für das- `<identityConfiguration>` Element.</span><span class="sxs-lookup"><span data-stu-id="c3327-128">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3327-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c3327-129">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
