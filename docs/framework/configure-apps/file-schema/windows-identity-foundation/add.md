---
title: <add>
ms.date: 03/30/2017
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
author: BrucePerlerMS
ms.openlocfilehash: 83ba51cbbd5100bf7412f9914a270cac88f7faa1
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73973803"
---
# <a name="add"></a><span data-ttu-id="a42ce-101">\<add></span><span class="sxs-lookup"><span data-stu-id="a42ce-101">\<add></span></span>
<span data-ttu-id="a42ce-102">Fügt der tokenhandlerauflistung den angegebenen Sicherheitstokenhandler hinzu.</span><span class="sxs-lookup"><span data-stu-id="a42ce-102">Adds the specified security token handler to the token handler collection.</span></span>  
  
<span data-ttu-id="a42ce-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a42ce-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a42ce-104">&nbsp;&nbsp;[ **\<System. IdentityModel->** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="a42ce-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="a42ce-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityconfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="a42ce-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="a42ce-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securitytokenhandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="a42ce-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="a42ce-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<hinzufügen >**</span><span class="sxs-lookup"><span data-stu-id="a42ce-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a42ce-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="a42ce-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a42ce-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a42ce-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a42ce-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a42ce-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a42ce-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="a42ce-111">Attributes</span></span>  
  
|<span data-ttu-id="a42ce-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="a42ce-112">Attribute</span></span>|<span data-ttu-id="a42ce-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a42ce-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a42ce-114">Typ</span><span class="sxs-lookup"><span data-stu-id="a42ce-114">type</span></span>|<span data-ttu-id="a42ce-115">Der CLR-Typname des tokenhandlers, der hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a42ce-115">The CLR type name of the token handler to be added.</span></span> <span data-ttu-id="a42ce-116">Weitere Informationen zum Angeben des `type` Attributs finden Sie unter [benutzerdefinierte Typverweise](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span><span class="sxs-lookup"><span data-stu-id="a42ce-116">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a42ce-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a42ce-117">Child Elements</span></span>  
  
|<span data-ttu-id="a42ce-118">Element</span><span class="sxs-lookup"><span data-stu-id="a42ce-118">Element</span></span>|<span data-ttu-id="a42ce-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a42ce-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a42ce-120">\<samlsecuritytokenrequirements ></span><span class="sxs-lookup"><span data-stu-id="a42ce-120">\<samlSecurityTokenRequirement></span></span>](samlsecuritytokenrequirement.md)|<span data-ttu-id="a42ce-121">Stellt die Konfiguration für die <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>-Klasse, die <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>-Klasse oder eine abgeleitete Klasse einer dieser Klassen bereit.</span><span class="sxs-lookup"><span data-stu-id="a42ce-121">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
|[<span data-ttu-id="a42ce-122">\<sessiontokenrequirements ></span><span class="sxs-lookup"><span data-stu-id="a42ce-122">\<sessionTokenRequirement></span></span>](sessiontokenrequirement.md)|<span data-ttu-id="a42ce-123">Stellt die Konfiguration für die <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>-Klasse oder abgeleitete Klassen bereit.</span><span class="sxs-lookup"><span data-stu-id="a42ce-123">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="a42ce-124">\<usernamesecuritytokenhandlerrequirements ></span><span class="sxs-lookup"><span data-stu-id="a42ce-124">\<userNameSecurityTokenHandlerRequirement></span></span>](usernamesecuritytokenhandlerrequirement.md)|<span data-ttu-id="a42ce-125">Stellt die Konfiguration für die <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>-Klasse oder abgeleitete Klassen bereit.</span><span class="sxs-lookup"><span data-stu-id="a42ce-125">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="a42ce-126">\<x509SecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="a42ce-126">\<x509SecurityTokenHandlerRequirement></span></span>](x509securitytokenhandlerrequirement.md)|<span data-ttu-id="a42ce-127">Stellt eine optionale Konfiguration für die <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>-Klasse oder abgeleitete Klassen bereit.</span><span class="sxs-lookup"><span data-stu-id="a42ce-127">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a42ce-128">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a42ce-128">Parent Elements</span></span>  
  
|<span data-ttu-id="a42ce-129">Element</span><span class="sxs-lookup"><span data-stu-id="a42ce-129">Element</span></span>|<span data-ttu-id="a42ce-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a42ce-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a42ce-131">\<securitytokenhandlers ></span><span class="sxs-lookup"><span data-stu-id="a42ce-131">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="a42ce-132">Gibt eine Auflistung von Sicherheitstokenhandlern an, die beim Endpunkt registriert sind.</span><span class="sxs-lookup"><span data-stu-id="a42ce-132">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a42ce-133">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a42ce-133">Remarks</span></span>  
 <span data-ttu-id="a42ce-134">Das `<add>`-Element kann ein einzelnes untergeordnetes Element annehmen, das die Konfiguration für den Tokenhandler angibt.</span><span class="sxs-lookup"><span data-stu-id="a42ce-134">The `<add>` element can take a single child element that specifies the configuration for the token handler.</span></span> <span data-ttu-id="a42ce-135">Dies hängt davon ab, ob die Handlerklasse, auf die über das `type`-Attribut des `<add>`-Elements verwiesen wird, Unterstützung für diese Funktion bietet.</span><span class="sxs-lookup"><span data-stu-id="a42ce-135">This is dependent on whether the handler class referenced through the `type` attribute of the `<add>` element provides support for this feature.</span></span> <span data-ttu-id="a42ce-136">Tokenhandlerklassen, die diese Funktion bereitstellen, müssen einen Konstruktor verfügbar machen, der ein <xref:System.Xml.XmlElement> Objekt annimmt.</span><span class="sxs-lookup"><span data-stu-id="a42ce-136">Token handler classes that provide this feature must expose a constructor that takes an <xref:System.Xml.XmlElement> object.</span></span>  

```csharp  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 <span data-ttu-id="a42ce-137">Einige der integrierten sicherheitstokenhandlerklassen stellen diese Funktionalität bereit.</span><span class="sxs-lookup"><span data-stu-id="a42ce-137">Several of the built-in security token handler classes do provide this functionality.</span></span> <span data-ttu-id="a42ce-138">Diese Klassen sind <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>und <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.</span><span class="sxs-lookup"><span data-stu-id="a42ce-138">These classes are <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a42ce-139">Die tokenhandlerauflistung kann nur einen einzelnen Handler eines beliebigen Typs enthalten.</span><span class="sxs-lookup"><span data-stu-id="a42ce-139">The token handler collection can only contain a single handler of any given type.</span></span> <span data-ttu-id="a42ce-140">Wenn Sie z. b. einen Handler hinzufügen möchten, der von der <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>-Klasse zur-Auflistung abgeleitet ist, müssen Sie zuerst das <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, das standardmäßig vorhanden ist, aus der-Auflistung entfernen.</span><span class="sxs-lookup"><span data-stu-id="a42ce-140">This means, for example, that if you want to add a handler that is derived from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class to the collection, you must first remove the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, which is present by default, from the collection.</span></span> <span data-ttu-id="a42ce-141">Sie können das [\<remove >](remove.md) -Element verwenden, um einen einzelnen Handler aus der Auflistung zu entfernen, oder das [\<Clear >](clear.md) -Element verwenden, um alle Handler aus der Auflistung zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="a42ce-141">You can use the [\<remove>](remove.md) element to remove a single handler from the collection or use the [\<clear>](clear.md) element to remove all handlers from the collection.</span></span>  
  
 <span data-ttu-id="a42ce-142">Die Einstellungen, die für einen Handler angegeben werden, überschreiben die entsprechenden Einstellungen, die für die [tokenhandlerauflistung unter dem\<securitytokenhandlerconfiguration->](securitytokenhandlerconfiguration.md) Element angegeben wurden, und die auf Dienst Ebene unter dem [\<identityconfiguration->](identityconfiguration.md) Element angegebenen</span><span class="sxs-lookup"><span data-stu-id="a42ce-142">Settings specified on a handler override equivalent settings specified on the token handler collection under the [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) element and those specified at the service-level under the [\<identityConfiguration>](identityconfiguration.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a42ce-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a42ce-143">Example</span></span>  
 <span data-ttu-id="a42ce-144">Der folgende XML-Code zeigt die Verwendung der `<add>`-und `<remove>`-Elemente, um den standardsitzungstokenhandler durch einen benutzerdefinierten Sitzungs Token-Handler zu ersetzen</span><span class="sxs-lookup"><span data-stu-id="a42ce-144">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="a42ce-145">Der XML-Code stammt aus dem `ClaimsAwareWebFarm`-Beispiel.</span><span class="sxs-lookup"><span data-stu-id="a42ce-145">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
