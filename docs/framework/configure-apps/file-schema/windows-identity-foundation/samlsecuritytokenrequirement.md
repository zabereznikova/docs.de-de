---
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: b27f337189a7d0b66ffd38e032b5eb864e5094a1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152631"
---
# <a name="samlsecuritytokenrequirement"></a><span data-ttu-id="cf026-101">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="cf026-101">\<samlSecurityTokenRequirement></span></span>
<span data-ttu-id="cf026-102">Stellt die <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> Konfiguration für <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> die Klasse, die Klasse oder eine abgeleitete Klasse einer dieser Klassen bereit.</span><span class="sxs-lookup"><span data-stu-id="cf026-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span> <span data-ttu-id="cf026-103">Vertreten durch <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> die Klasse.</span><span class="sxs-lookup"><span data-stu-id="cf026-103">Represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class.</span></span>  
  
<span data-ttu-id="cf026-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="cf026-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="cf026-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="cf026-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="cf026-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="cf026-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="cf026-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="cf026-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="cf026-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<hinzufügen>**](add.md)</span><span class="sxs-lookup"><span data-stu-id="cf026-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="cf026-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<samlSecurityTokenRequirement>**</span><span class="sxs-lookup"><span data-stu-id="cf026-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<samlSecurityTokenRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf026-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="cf026-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cf026-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="cf026-111">Attributes and Elements</span></span>  
 <span data-ttu-id="cf026-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cf026-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cf026-113">Attributes</span><span class="sxs-lookup"><span data-stu-id="cf026-113">Attributes</span></span>  
  
|<span data-ttu-id="cf026-114">attribute</span><span class="sxs-lookup"><span data-stu-id="cf026-114">Attribute</span></span>|<span data-ttu-id="cf026-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cf026-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cf026-116">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="cf026-116">mapToWindows</span></span>|<span data-ttu-id="cf026-117">Gibt an, ob der Tokenhandler das Validierungstoken mithilfe des eingehenden UPN-Anspruchs einem Windows-Konto zuordnen soll.</span><span class="sxs-lookup"><span data-stu-id="cf026-117">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="cf026-118">Der Standardwert lautet "false".</span><span class="sxs-lookup"><span data-stu-id="cf026-118">The default is "false".</span></span>|  
|<span data-ttu-id="cf026-119">AusstellerCertificateRevocationMode</span><span class="sxs-lookup"><span data-stu-id="cf026-119">issuerCertificateRevocationMode</span></span>|<span data-ttu-id="cf026-120">Ein <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Wert, der den Sperrmodus angibt, der für das X.509-Zertifikat verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="cf026-120">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="cf026-121">Der Standardwert ist "Online".</span><span class="sxs-lookup"><span data-stu-id="cf026-121">The default value is "Online".</span></span>|  
|<span data-ttu-id="cf026-122">AusstellerCertificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="cf026-122">issuerCertificateValidationMode</span></span>|<span data-ttu-id="cf026-123">Ein <xref:System.ServiceModel.Security.X509CertificateValidationMode> Wert, der den Validierungsmodus angibt, der für das X.509-Zertifikat verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="cf026-123">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="cf026-124">Der Standardwert ist "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="cf026-124">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="cf026-125">AusstellerCertificateTrustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="cf026-125">issuerCertificateTrustedStoreLocation</span></span>|<span data-ttu-id="cf026-126">Ein <xref:System.Security.Cryptography.X509Certificates.StoreLocation> Wert, der den X.509-Zertifikatspeicher angibt.</span><span class="sxs-lookup"><span data-stu-id="cf026-126">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="cf026-127">Der Standardwert ist "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="cf026-127">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="cf026-128">AusstellerCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="cf026-128">issuerCertificateValidator</span></span>|<span data-ttu-id="cf026-129">Ein benutzerdefinierter Typ, <xref:System.IdentityModel.Selectors.X509CertificateValidator>der von ableitet.</span><span class="sxs-lookup"><span data-stu-id="cf026-129">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="cf026-130">Wenn `issuerCertificateValidationMode` das Attribut "Custom" lautet, wird eine Instanz dieses Typs für die Validierung von Ausstellerzertifikaten verwendet.</span><span class="sxs-lookup"><span data-stu-id="cf026-130">If the `issuerCertificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cf026-131">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cf026-131">Child Elements</span></span>  
  
|<span data-ttu-id="cf026-132">Element</span><span class="sxs-lookup"><span data-stu-id="cf026-132">Element</span></span>|<span data-ttu-id="cf026-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cf026-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cf026-134">\<NameClaimType></span><span class="sxs-lookup"><span data-stu-id="cf026-134">\<nameClaimType></span></span>](nameclaimtype.md)|<span data-ttu-id="cf026-135">Legt den Anspruchstyp <xref:System.Security.Principal.IIdentity.Name%2A> fest, der die Eigenschaft angibt.</span><span class="sxs-lookup"><span data-stu-id="cf026-135">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span>|  
|[<span data-ttu-id="cf026-136">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="cf026-136">\<roleClaimType></span></span>](roleclaimtype.md)|<span data-ttu-id="cf026-137">Gibt den Anspruchstyp an, der die Rollentypansprüche in der Auflistung von <xref:System.Security.Claims.ClaimsIdentity> Objekten definiert, die von der <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> Methode des Tokenhandlers zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="cf026-137">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cf026-138">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cf026-138">Parent Elements</span></span>  
  
|<span data-ttu-id="cf026-139">Element</span><span class="sxs-lookup"><span data-stu-id="cf026-139">Element</span></span>|<span data-ttu-id="cf026-140">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cf026-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cf026-141">\<hinzufügen></span><span class="sxs-lookup"><span data-stu-id="cf026-141">\<add></span></span>](add.md)|<span data-ttu-id="cf026-142">Fügt der Tokenhandlerauflistung den angegebenen Sicherheitstokenhandler hinzu.</span><span class="sxs-lookup"><span data-stu-id="cf026-142">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cf026-143">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="cf026-143">Remarks</span></span>  
 <span data-ttu-id="cf026-144">Das `<samlSecurityTokenRequirement>` Element wird <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> durch die Klasse im Objektmodell `SamlSecurityTokenRequirement` dargestellt und <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> zum <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>Konfigurieren der Eigenschaft auf einer oder einer verwendet.</span><span class="sxs-lookup"><span data-stu-id="cf026-144">The `<samlSecurityTokenRequirement>` element is represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class in the object model and is used to configure the `SamlSecurityTokenRequirement` property on a <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> or a <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf026-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cf026-145">Example</span></span>  
  
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
