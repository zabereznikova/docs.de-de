---
title: <nameClaimType>
ms.date: 03/30/2017
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
author: BrucePerlerMS
ms.openlocfilehash: 4bf8ad2f70499edfc72dd9fcd9a5d8a0aafbbc66
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251940"
---
# \<nameClaimType>
<span data-ttu-id="d7f36-101">Legt den Anspruchstyp fest, der die <xref:System.Security.Principal.IIdentity.Name%2A> Eigenschaft angibt.</span><span class="sxs-lookup"><span data-stu-id="d7f36-101">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="d7f36-102">Der Anspruchstyp wird verwendet, um in der Auflistung von-Objekten zu suchen, die <xref:System.Security.Claims.Claim> <xref:System.Security.Claims.ClaimsIdentity> von der- <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> Methode dieses tokenhandlers zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d7f36-102">The claim type is used to search for a <xref:System.Security.Claims.Claim> in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of this token handler.</span></span> <span data-ttu-id="d7f36-103">Der Wert des übereinstimmenden Anspruchs wird dann als Name der <xref:System.Security.Principal.IIdentity> von diesem Tokenhandler generierten festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d7f36-103">The value of the matching claim is then set as the name of the <xref:System.Security.Principal.IIdentity> generated from this token handler.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<samlSecurityTokenRequirement>**](samlsecuritytokenrequirement.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<nameClaimType>**  
  
## <a name="syntax"></a><span data-ttu-id="d7f36-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d7f36-104">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement>  
          <nameClaimType value=xs:string>  
          </nameClaimType>  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d7f36-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d7f36-105">Attributes and Elements</span></span>  
 <span data-ttu-id="d7f36-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d7f36-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d7f36-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="d7f36-107">Attributes</span></span>  
  
|<span data-ttu-id="d7f36-108">attribute</span><span class="sxs-lookup"><span data-stu-id="d7f36-108">Attribute</span></span>|<span data-ttu-id="d7f36-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d7f36-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d7f36-110">value</span><span class="sxs-lookup"><span data-stu-id="d7f36-110">value</span></span>|<span data-ttu-id="d7f36-111">Eine Zeichenfolge, die den URI angibt, der den Anspruchstyp des Anspruchs darstellt, der für die Eigenschaft verwendet werden soll <xref:System.Security.Principal.IIdentity.Name%2A> .</span><span class="sxs-lookup"><span data-stu-id="d7f36-111">A string that specifies the URI that represents the claim type of the claim to use for the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="d7f36-112">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d7f36-112">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d7f36-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d7f36-113">Child Elements</span></span>  
 <span data-ttu-id="d7f36-114">Keine</span><span class="sxs-lookup"><span data-stu-id="d7f36-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d7f36-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d7f36-115">Parent Elements</span></span>  
  
|<span data-ttu-id="d7f36-116">Element</span><span class="sxs-lookup"><span data-stu-id="d7f36-116">Element</span></span>|<span data-ttu-id="d7f36-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d7f36-117">Description</span></span>|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement>](samlsecuritytokenrequirement.md)|<span data-ttu-id="d7f36-118">Stellt die Konfiguration für die- <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> Klasse, die- <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> Klasse oder eine abgeleitete Klasse einer dieser Klassen bereit.</span><span class="sxs-lookup"><span data-stu-id="d7f36-118">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7f36-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="d7f36-119">Remarks</span></span>  
 <span data-ttu-id="d7f36-120">Das- `<nameClaimType>` Element legt die-Eigenschaft fest, <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> Wenn ein- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> Objekt aus der Konfiguration initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="d7f36-120">The `<nameClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7f36-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d7f36-121">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d7f36-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d7f36-122">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>
