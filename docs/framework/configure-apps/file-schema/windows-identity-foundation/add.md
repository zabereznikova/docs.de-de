---
title: '&lt;add&gt;'
ms.date: 03/30/2017
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 6ee6403fcfe741d3e38bf44eddb1cf52cf856ec8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32757852"
---
# <a name="ltaddgt"></a><span data-ttu-id="e4b5a-102">&lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="e4b5a-102">&lt;add&gt;</span></span>
<span data-ttu-id="e4b5a-103">Fügt den angegebenen Sicherheits-Tokenhandler der Tokenhandler Auflistung hinzu.</span><span class="sxs-lookup"><span data-stu-id="e4b5a-103">Adds the specified security token handler to the token handler collection.</span></span>  
  
 <span data-ttu-id="e4b5a-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="e4b5a-104">\<system.identityModel></span></span>  
<span data-ttu-id="e4b5a-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="e4b5a-105">\<identityConfiguration></span></span>  
<span data-ttu-id="e4b5a-106">\<SecurityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="e4b5a-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="e4b5a-107">\<add></span><span class="sxs-lookup"><span data-stu-id="e4b5a-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4b5a-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="e4b5a-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type=xs:string>  
        <optionalConfigurationElement>  
        </optionalConfigurationElement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e4b5a-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e4b5a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e4b5a-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e4b5a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e4b5a-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="e4b5a-111">Attributes</span></span>  
  
|<span data-ttu-id="e4b5a-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="e4b5a-112">Attribute</span></span>|<span data-ttu-id="e4b5a-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e4b5a-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e4b5a-114">Typ</span><span class="sxs-lookup"><span data-stu-id="e4b5a-114">type</span></span>|<span data-ttu-id="e4b5a-115">Der CLR-Typname der der Tokenhandler hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="e4b5a-115">The CLR type name of the token handler to be added.</span></span> <span data-ttu-id="e4b5a-116">Weitere Informationen zum Angeben der `type` -Attribut angegeben wird, finden Sie unter [benutzerdefinierte Typverweise](http://msdn.microsoft.com/library/7286d2e3-c63d-49fd-abdc-ce2705f22c24).</span><span class="sxs-lookup"><span data-stu-id="e4b5a-116">For more information about how to specify the `type` attribute, see [Custom Type References](http://msdn.microsoft.com/library/7286d2e3-c63d-49fd-abdc-ce2705f22c24).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e4b5a-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e4b5a-117">Child Elements</span></span>  
  
|<span data-ttu-id="e4b5a-118">Element</span><span class="sxs-lookup"><span data-stu-id="e4b5a-118">Element</span></span>|<span data-ttu-id="e4b5a-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e4b5a-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e4b5a-120">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="e4b5a-120">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="e4b5a-121">Ermöglicht die Konfiguration für die <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> -Klasse, die <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> Klasse oder eine abgeleitete Klasse von einer dieser Klassen.</span><span class="sxs-lookup"><span data-stu-id="e4b5a-121">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
|[<span data-ttu-id="e4b5a-122">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="e4b5a-122">\<sessionTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessiontokenrequirement.md)|<span data-ttu-id="e4b5a-123">Ermöglicht die Konfiguration für die <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> abgeleiteten Klassen.</span><span class="sxs-lookup"><span data-stu-id="e4b5a-123">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="e4b5a-124">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="e4b5a-124">\<userNameSecurityTokenHandlerRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/usernamesecuritytokenhandlerrequirement.md)|<span data-ttu-id="e4b5a-125">Ermöglicht die Konfiguration für die <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> abgeleiteten Klassen.</span><span class="sxs-lookup"><span data-stu-id="e4b5a-125">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="e4b5a-126">\<x509SecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="e4b5a-126">\<x509SecurityTokenHandlerRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/x509securitytokenhandlerrequirement.md)|<span data-ttu-id="e4b5a-127">Bietet optionale Konfiguration für die <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> abgeleiteten Klassen.</span><span class="sxs-lookup"><span data-stu-id="e4b5a-127">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e4b5a-128">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e4b5a-128">Parent Elements</span></span>  
  
|<span data-ttu-id="e4b5a-129">Element</span><span class="sxs-lookup"><span data-stu-id="e4b5a-129">Element</span></span>|<span data-ttu-id="e4b5a-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e4b5a-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e4b5a-131">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="e4b5a-131">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="e4b5a-132">Gibt eine Auflistung von sicherheitstokenhandlern, die mit dem Endpunkt registriert sind.</span><span class="sxs-lookup"><span data-stu-id="e4b5a-132">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4b5a-133">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e4b5a-133">Remarks</span></span>  
 <span data-ttu-id="e4b5a-134">Die `<add>` Element kann ein einzelnes untergeordnetes Element, der angibt, die Konfiguration der Tokenhandler in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="e4b5a-134">The `<add>` element can take a single child element that specifies the configuration for the token handler.</span></span> <span data-ttu-id="e4b5a-135">Dies ist abhängig davon, ob die Handlerklasse über verwiesen die `type` Attribut von der `<add>` -Element stellt Unterstützung für diese Funktion.</span><span class="sxs-lookup"><span data-stu-id="e4b5a-135">This is dependent on whether the handler class referenced through the `type` attribute of the `<add>` element provides support for this feature.</span></span> <span data-ttu-id="e4b5a-136">Tokenhandler-Klassen, die diese Funktion bereitstellen, verfügbar machen einen Konstruktor, akzeptiert eine <xref:System.Xml.XmlElement> Objekt.</span><span class="sxs-lookup"><span data-stu-id="e4b5a-136">Token handler classes that provide this feature must expose a constructor that takes an <xref:System.Xml.XmlElement> object.</span></span>  
  
```  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 <span data-ttu-id="e4b5a-137">Einige der integrierten Sicherheit Tokenhandler Klassen stellen diese Funktionalität bereit.</span><span class="sxs-lookup"><span data-stu-id="e4b5a-137">Several of the built-in security token handler classes do provide this functionality.</span></span> <span data-ttu-id="e4b5a-138">Diese Klassen sind <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, und <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.</span><span class="sxs-lookup"><span data-stu-id="e4b5a-138">These classes are <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e4b5a-139">Die Tokenhandler Auflistung darf nur einen einzigen Handler eines angegebenen Typs.</span><span class="sxs-lookup"><span data-stu-id="e4b5a-139">The token handler collection can only contain a single handler of any given type.</span></span> <span data-ttu-id="e4b5a-140">Dies bedeutet, z. B., dass wenn Sie möchten einen Handler hinzuzufügen, die abgeleitet ist die <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> Klasse auf die Auflistung, müssen Sie zuerst Entfernen der <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, die standardmäßig aus der Auflistung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e4b5a-140">This means, for example, that if you want to add a handler that is derived from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class to the collection, you must first remove the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, which is present by default, from the collection.</span></span> <span data-ttu-id="e4b5a-141">Können Sie die [ \<entfernen >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md) Element So entfernen Sie einen einzigen Handler aus der Auflistung oder die Verwendung der [ \<deaktivieren >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md) zu alle Handler aus der Auflistung zu entfernenden Elements.</span><span class="sxs-lookup"><span data-stu-id="e4b5a-141">You can use the [\<remove>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md) element to remove a single handler from the collection or use the [\<clear>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md) element to remove all handlers from the collection.</span></span>  
  
 <span data-ttu-id="e4b5a-142">Für einen Ereignishandler angegebene Einstellungen außer Kraft setzen entsprechende Einstellungen auf der Tokenhandler Sammlung im angegebenen der [ \<SecurityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) Element und den angegebenen auf Dienstebene unter die [ \<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element.</span><span class="sxs-lookup"><span data-stu-id="e4b5a-142">Settings specified on a handler override equivalent settings specified on the token handler collection under the [\<securityTokenHandlerConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) element and those specified at the service-level under the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4b5a-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e4b5a-143">Example</span></span>  
 <span data-ttu-id="e4b5a-144">Das folgende XML zeigt die Verwendung der `<add>` und `<remove>` Elemente der Standardhandler für Sitzung token mit einer benutzerdefinierten-Sitzung Tokenhandler ersetzen.</span><span class="sxs-lookup"><span data-stu-id="e4b5a-144">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="e4b5a-145">Der XML-Code stammt aus dem `ClaimsAwareWebFarm` Beispiel.</span><span class="sxs-lookup"><span data-stu-id="e4b5a-145">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
