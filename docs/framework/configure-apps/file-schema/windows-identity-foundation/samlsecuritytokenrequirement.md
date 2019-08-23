---
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: df259398beb242ea95efb248d6b5140b38ca3c45
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942493"
---
# <a name="samlsecuritytokenrequirement"></a><span data-ttu-id="19872-101">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="19872-101">\<samlSecurityTokenRequirement></span></span>
<span data-ttu-id="19872-102">Stellt die Konfiguration für <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> die-Klasse <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> , die-Klasse oder eine abgeleitete Klasse einer dieser Klassen bereit.</span><span class="sxs-lookup"><span data-stu-id="19872-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span> <span data-ttu-id="19872-103">Wird von der <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> -Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="19872-103">Represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class.</span></span>  
  
 <span data-ttu-id="19872-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="19872-104">\<system.identityModel></span></span>  
<span data-ttu-id="19872-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="19872-105">\<identityConfiguration></span></span>  
<span data-ttu-id="19872-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="19872-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="19872-107">\<add></span><span class="sxs-lookup"><span data-stu-id="19872-107">\<add></span></span>  
<span data-ttu-id="19872-108">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="19872-108">\<samlSecurityTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19872-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="19872-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="19872-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="19872-110">Attributes and Elements</span></span>  
 <span data-ttu-id="19872-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="19872-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="19872-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="19872-112">Attributes</span></span>  
  
|<span data-ttu-id="19872-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="19872-113">Attribute</span></span>|<span data-ttu-id="19872-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="19872-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="19872-115">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="19872-115">mapToWindows</span></span>|<span data-ttu-id="19872-116">Gibt an, ob der Tokenhandler das Validierungs Token einem Windows-Konto zuordnen soll, indem der eingehende UPN-Anspruch verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="19872-116">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="19872-117">Der Standardwert ist "false".</span><span class="sxs-lookup"><span data-stu-id="19872-117">The default is "false".</span></span>|  
|<span data-ttu-id="19872-118">issuerCertificateRevocationMode</span><span class="sxs-lookup"><span data-stu-id="19872-118">issuerCertificateRevocationMode</span></span>|<span data-ttu-id="19872-119">Ein <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> -Wert, der den Sperrmodus angibt, der für das X. 509-Zertifikat verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="19872-119">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="19872-120">Der Standardwert ist "Online".</span><span class="sxs-lookup"><span data-stu-id="19872-120">The default value is "Online".</span></span>|  
|<span data-ttu-id="19872-121">issuerCertificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="19872-121">issuerCertificateValidationMode</span></span>|<span data-ttu-id="19872-122">Ein <xref:System.ServiceModel.Security.X509CertificateValidationMode> -Wert, der den Validierungs Modus angibt, der für das X. 509-Zertifikat verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="19872-122">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="19872-123">Der Standardwert ist "Peer-ChainTrust".</span><span class="sxs-lookup"><span data-stu-id="19872-123">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="19872-124">issuerCertificateTrustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="19872-124">issuerCertificateTrustedStoreLocation</span></span>|<span data-ttu-id="19872-125">Ein <xref:System.Security.Cryptography.X509Certificates.StoreLocation> -Wert, der den X. 509-Zertifikat Speicher angibt.</span><span class="sxs-lookup"><span data-stu-id="19872-125">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="19872-126">Der Standardwert ist "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="19872-126">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="19872-127">issuerCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="19872-127">issuerCertificateValidator</span></span>|<span data-ttu-id="19872-128">Ein benutzerdefinierter Typ, der <xref:System.IdentityModel.Selectors.X509CertificateValidator>von abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="19872-128">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="19872-129">Wenn das `issuerCertificateValidationMode` Attribut "Custom" ist, wird eine Instanz dieses Typs für die Überprüfung des Zertifikat Ausstellers verwendet.</span><span class="sxs-lookup"><span data-stu-id="19872-129">If the `issuerCertificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="19872-130">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="19872-130">Child Elements</span></span>  
  
|<span data-ttu-id="19872-131">Element</span><span class="sxs-lookup"><span data-stu-id="19872-131">Element</span></span>|<span data-ttu-id="19872-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="19872-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="19872-133">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="19872-133">\<nameClaimType></span></span>](nameclaimtype.md)|<span data-ttu-id="19872-134">Legt den Anspruchstyp fest, der <xref:System.Security.Principal.IIdentity.Name%2A> die Eigenschaft angibt.</span><span class="sxs-lookup"><span data-stu-id="19872-134">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span>|  
|[<span data-ttu-id="19872-135">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="19872-135">\<roleClaimType></span></span>](roleclaimtype.md)|<span data-ttu-id="19872-136">Gibt den Anspruchstyp an, der die Rollen Typen Ansprüche in der Auflistung <xref:System.Security.Claims.ClaimsIdentity> von-Objekten definiert <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> , die von der-Methode des tokenhandlers zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="19872-136">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="19872-137">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="19872-137">Parent Elements</span></span>  
  
|<span data-ttu-id="19872-138">Element</span><span class="sxs-lookup"><span data-stu-id="19872-138">Element</span></span>|<span data-ttu-id="19872-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="19872-139">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="19872-140">\<add></span><span class="sxs-lookup"><span data-stu-id="19872-140">\<add></span></span>](add.md)|<span data-ttu-id="19872-141">Fügt der tokenhandlerauflistung den angegebenen Sicherheitstokenhandler hinzu.</span><span class="sxs-lookup"><span data-stu-id="19872-141">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19872-142">Hinweise</span><span class="sxs-lookup"><span data-stu-id="19872-142">Remarks</span></span>  
 <span data-ttu-id="19872-143">Das `<samlSecurityTokenRequirement>` -Element wird durch die <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> -Klasse im Objektmodell dargestellt und zum Konfigurieren der `SamlSecurityTokenRequirement` -Eigenschaft in einem <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> oder einem <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>verwendet.</span><span class="sxs-lookup"><span data-stu-id="19872-143">The `<samlSecurityTokenRequirement>` element is represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class in the object model and is used to configure the `SamlSecurityTokenRequirement` property on a <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> or a <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19872-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="19872-144">Example</span></span>  
  
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
