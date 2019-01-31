---
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: e1b8acd48ee185b3c6c50f70321bb9ca66e8e02b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55284621"
---
# <a name="samlsecuritytokenrequirement"></a><span data-ttu-id="b1cd1-101">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="b1cd1-101">\<samlSecurityTokenRequirement></span></span>
<span data-ttu-id="b1cd1-102">Ermöglicht die Konfiguration für die <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> -Klasse, die <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> Klasse oder eine abgeleitete Klasse von einer dieser Klassen.</span><span class="sxs-lookup"><span data-stu-id="b1cd1-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span> <span data-ttu-id="b1cd1-103">Dargestellt durch die <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> Klasse.</span><span class="sxs-lookup"><span data-stu-id="b1cd1-103">Represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class.</span></span>  
  
 <span data-ttu-id="b1cd1-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="b1cd1-104">\<system.identityModel></span></span>  
<span data-ttu-id="b1cd1-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="b1cd1-105">\<identityConfiguration></span></span>  
<span data-ttu-id="b1cd1-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="b1cd1-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="b1cd1-107">\<add></span><span class="sxs-lookup"><span data-stu-id="b1cd1-107">\<add></span></span>  
<span data-ttu-id="b1cd1-108">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="b1cd1-108">\<samlSecurityTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1cd1-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="b1cd1-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b1cd1-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b1cd1-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b1cd1-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b1cd1-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b1cd1-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="b1cd1-112">Attributes</span></span>  
  
|<span data-ttu-id="b1cd1-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="b1cd1-113">Attribute</span></span>|<span data-ttu-id="b1cd1-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b1cd1-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b1cd1-115">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="b1cd1-115">mapToWindows</span></span>|<span data-ttu-id="b1cd1-116">Gibt an, ob der Tokenhandler das überprüfende Token zu einem Windows-Konto zuordnen soll, mithilfe des eingehenden UPN-Anspruchs.</span><span class="sxs-lookup"><span data-stu-id="b1cd1-116">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="b1cd1-117">Der Standardwert ist "false".</span><span class="sxs-lookup"><span data-stu-id="b1cd1-117">The default is "false".</span></span>|  
|<span data-ttu-id="b1cd1-118">issuerCertificateRevocationMode</span><span class="sxs-lookup"><span data-stu-id="b1cd1-118">issuerCertificateRevocationMode</span></span>|<span data-ttu-id="b1cd1-119">Ein <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Wert, der angibt, den Sperrmodus für das x. 509-Zertifikat verwenden.</span><span class="sxs-lookup"><span data-stu-id="b1cd1-119">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="b1cd1-120">Der Standardwert lautet "Online".</span><span class="sxs-lookup"><span data-stu-id="b1cd1-120">The default value is "Online".</span></span>|  
|<span data-ttu-id="b1cd1-121">issuerCertificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="b1cd1-121">issuerCertificateValidationMode</span></span>|<span data-ttu-id="b1cd1-122">Ein <xref:System.ServiceModel.Security.X509CertificateValidationMode> Wert, der angibt, den Validierungsmodus für das x. 509-Zertifikat verwenden.</span><span class="sxs-lookup"><span data-stu-id="b1cd1-122">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="b1cd1-123">Der Standardwert ist "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="b1cd1-123">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="b1cd1-124">issuerCertificateTrustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="b1cd1-124">issuerCertificateTrustedStoreLocation</span></span>|<span data-ttu-id="b1cd1-125">Ein <xref:System.Security.Cryptography.X509Certificates.StoreLocation> Wert, der den x. 509-Zertifikatspeicher angibt.</span><span class="sxs-lookup"><span data-stu-id="b1cd1-125">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="b1cd1-126">Der Standardwert ist "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="b1cd1-126">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="b1cd1-127">issuerCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="b1cd1-127">issuerCertificateValidator</span></span>|<span data-ttu-id="b1cd1-128">Ein benutzerdefinierter Typ, die von abgeleitet <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="b1cd1-128">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="b1cd1-129">Wenn die `issuerCertificateValidationMode` -Attribut ist "Custom", wird eine Instanz dieses Typs für die Überprüfung des Ausstellers Zertifikat verwendet.</span><span class="sxs-lookup"><span data-stu-id="b1cd1-129">If the `issuerCertificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b1cd1-130">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b1cd1-130">Child Elements</span></span>  
  
|<span data-ttu-id="b1cd1-131">Element</span><span class="sxs-lookup"><span data-stu-id="b1cd1-131">Element</span></span>|<span data-ttu-id="b1cd1-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b1cd1-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b1cd1-133">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="b1cd1-133">\<nameClaimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/nameclaimtype.md)|<span data-ttu-id="b1cd1-134">Legt den Typ des Anspruchs, der angibt, die <xref:System.Security.Principal.IIdentity.Name%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b1cd1-134">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span>|  
|[<span data-ttu-id="b1cd1-135">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="b1cd1-135">\<roleClaimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/roleclaimtype.md)|<span data-ttu-id="b1cd1-136">Gibt an, den Anspruchstyp, der die Rollenansprüche für den Typ in der Auflistung definiert <xref:System.Security.Claims.ClaimsIdentity> zurückgegebenen Objekte die <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> Methode der Tokenhandler.</span><span class="sxs-lookup"><span data-stu-id="b1cd1-136">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b1cd1-137">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b1cd1-137">Parent Elements</span></span>  
  
|<span data-ttu-id="b1cd1-138">Element</span><span class="sxs-lookup"><span data-stu-id="b1cd1-138">Element</span></span>|<span data-ttu-id="b1cd1-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b1cd1-139">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b1cd1-140">\<add></span><span class="sxs-lookup"><span data-stu-id="b1cd1-140">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="b1cd1-141">Der Tokenhandler-Auflistung hinzugefügt den angegebenen Sicherheitstokenhandler.</span><span class="sxs-lookup"><span data-stu-id="b1cd1-141">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b1cd1-142">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b1cd1-142">Remarks</span></span>  
 <span data-ttu-id="b1cd1-143">Die `<samlSecurityTokenRequirement>` Element dargestellt ist, indem die <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> Klasse im Objektmodell und dient zum Konfigurieren der `SamlSecurityTokenRequirement` Eigenschaft für eine <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> oder ein <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span><span class="sxs-lookup"><span data-stu-id="b1cd1-143">The `<samlSecurityTokenRequirement>` element is represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class in the object model and is used to configure the `SamlSecurityTokenRequirement` property on a <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> or a <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1cd1-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b1cd1-144">Example</span></span>  
  
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
