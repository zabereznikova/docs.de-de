---
title: '&lt;samlSecurityTokenRequirement&gt;'
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: c9856dae971691baf9dabe845bdecae90cbc8aa5
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2018
ms.locfileid: "48031889"
---
# <a name="ltsamlsecuritytokenrequirementgt"></a><span data-ttu-id="b22a0-102">&lt;samlSecurityTokenRequirement&gt;</span><span class="sxs-lookup"><span data-stu-id="b22a0-102">&lt;samlSecurityTokenRequirement&gt;</span></span>
<span data-ttu-id="b22a0-103">Ermöglicht die Konfiguration für die <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> -Klasse, die <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> Klasse oder eine abgeleitete Klasse von einer dieser Klassen.</span><span class="sxs-lookup"><span data-stu-id="b22a0-103">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span> <span data-ttu-id="b22a0-104">Dargestellt durch die <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> Klasse.</span><span class="sxs-lookup"><span data-stu-id="b22a0-104">Represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class.</span></span>  
  
 <span data-ttu-id="b22a0-105">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="b22a0-105">\<system.identityModel></span></span>  
<span data-ttu-id="b22a0-106">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="b22a0-106">\<identityConfiguration></span></span>  
<span data-ttu-id="b22a0-107">\<SecurityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="b22a0-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="b22a0-108">\<add></span><span class="sxs-lookup"><span data-stu-id="b22a0-108">\<add></span></span>  
<span data-ttu-id="b22a0-109">\<SamlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="b22a0-109">\<samlSecurityTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b22a0-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="b22a0-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b22a0-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b22a0-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b22a0-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b22a0-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b22a0-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="b22a0-113">Attributes</span></span>  
  
|<span data-ttu-id="b22a0-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="b22a0-114">Attribute</span></span>|<span data-ttu-id="b22a0-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b22a0-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b22a0-116">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="b22a0-116">mapToWindows</span></span>|<span data-ttu-id="b22a0-117">Gibt an, ob der Tokenhandler das überprüfende Token zu einem Windows-Konto zuordnen soll, mithilfe des eingehenden UPN-Anspruchs.</span><span class="sxs-lookup"><span data-stu-id="b22a0-117">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="b22a0-118">Der Standardwert ist "false".</span><span class="sxs-lookup"><span data-stu-id="b22a0-118">The default is "false".</span></span>|  
|<span data-ttu-id="b22a0-119">issuerCertificateRevocationMode</span><span class="sxs-lookup"><span data-stu-id="b22a0-119">issuerCertificateRevocationMode</span></span>|<span data-ttu-id="b22a0-120">Ein <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Wert, der angibt, den Sperrmodus für das x. 509-Zertifikat verwenden.</span><span class="sxs-lookup"><span data-stu-id="b22a0-120">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="b22a0-121">Der Standardwert lautet "Online".</span><span class="sxs-lookup"><span data-stu-id="b22a0-121">The default value is "Online".</span></span>|  
|<span data-ttu-id="b22a0-122">issuerCertificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="b22a0-122">issuerCertificateValidationMode</span></span>|<span data-ttu-id="b22a0-123">Ein <xref:System.ServiceModel.Security.X509CertificateValidationMode> Wert, der angibt, den Validierungsmodus für das x. 509-Zertifikat verwenden.</span><span class="sxs-lookup"><span data-stu-id="b22a0-123">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="b22a0-124">Der Standardwert ist "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="b22a0-124">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="b22a0-125">issuerCertificateTrustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="b22a0-125">issuerCertificateTrustedStoreLocation</span></span>|<span data-ttu-id="b22a0-126">Ein <xref:System.Security.Cryptography.X509Certificates.StoreLocation> Wert, der den x. 509-Zertifikatspeicher angibt.</span><span class="sxs-lookup"><span data-stu-id="b22a0-126">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="b22a0-127">Der Standardwert ist "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="b22a0-127">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="b22a0-128">issuerCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="b22a0-128">issuerCertificateValidator</span></span>|<span data-ttu-id="b22a0-129">Ein benutzerdefinierter Typ, die von abgeleitet <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="b22a0-129">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="b22a0-130">Wenn die `issuerCertificateValidationMode` -Attribut ist "Custom", wird eine Instanz dieses Typs für die Überprüfung des Ausstellers Zertifikat verwendet.</span><span class="sxs-lookup"><span data-stu-id="b22a0-130">If the `issuerCertificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b22a0-131">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b22a0-131">Child Elements</span></span>  
  
|<span data-ttu-id="b22a0-132">Element</span><span class="sxs-lookup"><span data-stu-id="b22a0-132">Element</span></span>|<span data-ttu-id="b22a0-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b22a0-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b22a0-134">\<NameClaimType ></span><span class="sxs-lookup"><span data-stu-id="b22a0-134">\<nameClaimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/nameclaimtype.md)|<span data-ttu-id="b22a0-135">Legt den Typ des Anspruchs, der angibt, die <xref:System.Security.Principal.IIdentity.Name%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b22a0-135">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span>|  
|[<span data-ttu-id="b22a0-136">\<RoleClaimType ></span><span class="sxs-lookup"><span data-stu-id="b22a0-136">\<roleClaimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/roleclaimtype.md)|<span data-ttu-id="b22a0-137">Gibt an, den Anspruchstyp, der die Rollenansprüche für den Typ in der Auflistung definiert <xref:System.Security.Claims.ClaimsIdentity> zurückgegebenen Objekte die <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> Methode der Tokenhandler.</span><span class="sxs-lookup"><span data-stu-id="b22a0-137">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b22a0-138">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b22a0-138">Parent Elements</span></span>  
  
|<span data-ttu-id="b22a0-139">Element</span><span class="sxs-lookup"><span data-stu-id="b22a0-139">Element</span></span>|<span data-ttu-id="b22a0-140">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b22a0-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b22a0-141">\<add></span><span class="sxs-lookup"><span data-stu-id="b22a0-141">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="b22a0-142">Der Tokenhandler-Auflistung hinzugefügt den angegebenen Sicherheitstokenhandler.</span><span class="sxs-lookup"><span data-stu-id="b22a0-142">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b22a0-143">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b22a0-143">Remarks</span></span>  
 <span data-ttu-id="b22a0-144">Die `<samlSecurityTokenRequirement>` Element dargestellt ist, indem die <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> Klasse im Objektmodell und dient zum Konfigurieren der `SamlSecurityTokenRequirement` Eigenschaft für eine <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> oder ein <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span><span class="sxs-lookup"><span data-stu-id="b22a0-144">The `<samlSecurityTokenRequirement>` element is represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class in the object model and is used to configure the `SamlSecurityTokenRequirement` property on a <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> or a <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b22a0-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b22a0-145">Example</span></span>  
  
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
