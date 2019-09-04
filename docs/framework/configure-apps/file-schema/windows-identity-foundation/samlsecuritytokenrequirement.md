---
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: cab7572518a7a6dc26f8bbcf67cd424fa1c01085
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251903"
---
# <a name="samlsecuritytokenrequirement"></a><span data-ttu-id="cd834-101">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="cd834-101">\<samlSecurityTokenRequirement></span></span>
<span data-ttu-id="cd834-102">Stellt die Konfiguration für <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> die-Klasse <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> , die-Klasse oder eine abgeleitete Klasse einer dieser Klassen bereit.</span><span class="sxs-lookup"><span data-stu-id="cd834-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span> <span data-ttu-id="cd834-103">Wird von der <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> -Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="cd834-103">Represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class.</span></span>  
  
<span data-ttu-id="cd834-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="cd834-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="cd834-105">&nbsp;&nbsp;[ **\<System. IdentityModel->** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="cd834-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="cd834-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityconfiguration->** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="cd834-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="cd834-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securitytokenhandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="cd834-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="cd834-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> Hinzufügen**](add.md)</span><span class="sxs-lookup"><span data-stu-id="cd834-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="cd834-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<samlsecuritytokenrequirements->**</span><span class="sxs-lookup"><span data-stu-id="cd834-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<samlSecurityTokenRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd834-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="cd834-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement   
            issuerCertificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
            issuerCertificateRevocationMode="NoCheck||Offline||Online"  
            issuerCertificateTrustedStoreLocation="CurrentLocation||LocalMachine"  
            issuerCertificateValidator="Namespace.Class Assembly"  
            mapToWindows=xs:boolean  
          <nameClaimType value=xs:string />  
          <roleClaimType value=xs:string />  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cd834-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="cd834-111">Attributes and Elements</span></span>  
 <span data-ttu-id="cd834-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cd834-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cd834-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="cd834-113">Attributes</span></span>  
  
|<span data-ttu-id="cd834-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="cd834-114">Attribute</span></span>|<span data-ttu-id="cd834-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd834-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cd834-116">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="cd834-116">mapToWindows</span></span>|<span data-ttu-id="cd834-117">Gibt an, ob der Tokenhandler das Validierungs Token einem Windows-Konto zuordnen soll, indem der eingehende UPN-Anspruch verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cd834-117">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="cd834-118">Der Standardwert ist "false".</span><span class="sxs-lookup"><span data-stu-id="cd834-118">The default is "false".</span></span>|  
|<span data-ttu-id="cd834-119">issuerCertificateRevocationMode</span><span class="sxs-lookup"><span data-stu-id="cd834-119">issuerCertificateRevocationMode</span></span>|<span data-ttu-id="cd834-120">Ein <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> -Wert, der den Sperrmodus angibt, der für das X. 509-Zertifikat verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="cd834-120">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="cd834-121">Der Standardwert ist "Online".</span><span class="sxs-lookup"><span data-stu-id="cd834-121">The default value is "Online".</span></span>|  
|<span data-ttu-id="cd834-122">issuerCertificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="cd834-122">issuerCertificateValidationMode</span></span>|<span data-ttu-id="cd834-123">Ein <xref:System.ServiceModel.Security.X509CertificateValidationMode> -Wert, der den Validierungs Modus angibt, der für das X. 509-Zertifikat verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="cd834-123">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="cd834-124">Der Standardwert ist "Peer-ChainTrust".</span><span class="sxs-lookup"><span data-stu-id="cd834-124">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="cd834-125">issuerCertificateTrustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="cd834-125">issuerCertificateTrustedStoreLocation</span></span>|<span data-ttu-id="cd834-126">Ein <xref:System.Security.Cryptography.X509Certificates.StoreLocation> -Wert, der den X. 509-Zertifikat Speicher angibt.</span><span class="sxs-lookup"><span data-stu-id="cd834-126">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="cd834-127">Der Standardwert ist "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="cd834-127">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="cd834-128">issuerCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="cd834-128">issuerCertificateValidator</span></span>|<span data-ttu-id="cd834-129">Ein benutzerdefinierter Typ, der <xref:System.IdentityModel.Selectors.X509CertificateValidator>von abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="cd834-129">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="cd834-130">Wenn das `issuerCertificateValidationMode` Attribut "Custom" ist, wird eine Instanz dieses Typs für die Überprüfung des Zertifikat Ausstellers verwendet.</span><span class="sxs-lookup"><span data-stu-id="cd834-130">If the `issuerCertificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cd834-131">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cd834-131">Child Elements</span></span>  
  
|<span data-ttu-id="cd834-132">Element</span><span class="sxs-lookup"><span data-stu-id="cd834-132">Element</span></span>|<span data-ttu-id="cd834-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd834-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cd834-134">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="cd834-134">\<nameClaimType></span></span>](nameclaimtype.md)|<span data-ttu-id="cd834-135">Legt den Anspruchstyp fest, der <xref:System.Security.Principal.IIdentity.Name%2A> die Eigenschaft angibt.</span><span class="sxs-lookup"><span data-stu-id="cd834-135">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span>|  
|[<span data-ttu-id="cd834-136">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="cd834-136">\<roleClaimType></span></span>](roleclaimtype.md)|<span data-ttu-id="cd834-137">Gibt den Anspruchstyp an, der die Rollen Typen Ansprüche in der Auflistung <xref:System.Security.Claims.ClaimsIdentity> von-Objekten definiert <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> , die von der-Methode des tokenhandlers zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="cd834-137">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cd834-138">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cd834-138">Parent Elements</span></span>  
  
|<span data-ttu-id="cd834-139">Element</span><span class="sxs-lookup"><span data-stu-id="cd834-139">Element</span></span>|<span data-ttu-id="cd834-140">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd834-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cd834-141">\<add></span><span class="sxs-lookup"><span data-stu-id="cd834-141">\<add></span></span>](add.md)|<span data-ttu-id="cd834-142">Fügt der tokenhandlerauflistung den angegebenen Sicherheitstokenhandler hinzu.</span><span class="sxs-lookup"><span data-stu-id="cd834-142">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd834-143">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cd834-143">Remarks</span></span>  
 <span data-ttu-id="cd834-144">Das `<samlSecurityTokenRequirement>` -Element wird durch die <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> -Klasse im Objektmodell dargestellt und zum Konfigurieren der `SamlSecurityTokenRequirement` -Eigenschaft in einem <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> oder einem <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>verwendet.</span><span class="sxs-lookup"><span data-stu-id="cd834-144">The `<samlSecurityTokenRequirement>` element is represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class in the object model and is used to configure the `SamlSecurityTokenRequirement` property on a <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> or a <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd834-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cd834-145">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement issuerCertificateValidationMode="PeerOrChainTrust"  
                                  issuerCertificateRevocationMode="Online"  
                                  issuerCertificateTrustedStoreLocation="LocalMachine"  
                                  mapToWindows="false">  
  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```
