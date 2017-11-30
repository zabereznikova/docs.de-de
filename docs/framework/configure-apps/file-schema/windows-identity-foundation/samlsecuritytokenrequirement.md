---
title: '&lt;samlSecurityTokenRequirement&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: e0d8d467c2636f5ce95cf5fed189ae00c3ca75fb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltsamlsecuritytokenrequirementgt"></a><span data-ttu-id="c3bfa-102">&lt;samlSecurityTokenRequirement&gt;</span><span class="sxs-lookup"><span data-stu-id="c3bfa-102">&lt;samlSecurityTokenRequirement&gt;</span></span>
<span data-ttu-id="c3bfa-103">Ermöglicht die Konfiguration für die <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> -Klasse, die <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> Klasse oder eine abgeleitete Klasse von einer dieser Klassen.</span><span class="sxs-lookup"><span data-stu-id="c3bfa-103">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span> <span data-ttu-id="c3bfa-104">Dargestellt durch die <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> Klasse.</span><span class="sxs-lookup"><span data-stu-id="c3bfa-104">Represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class.</span></span>  
  
 <span data-ttu-id="c3bfa-105">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="c3bfa-105">\<system.identityModel></span></span>  
<span data-ttu-id="c3bfa-106">\<IdentityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="c3bfa-106">\<identityConfiguration></span></span>  
<span data-ttu-id="c3bfa-107">\<SecurityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="c3bfa-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="c3bfa-108">\<add></span><span class="sxs-lookup"><span data-stu-id="c3bfa-108">\<add></span></span>  
<span data-ttu-id="c3bfa-109">\<SamlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="c3bfa-109">\<samlSecurityTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3bfa-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="c3bfa-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c3bfa-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c3bfa-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c3bfa-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c3bfa-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c3bfa-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="c3bfa-113">Attributes</span></span>  
  
|<span data-ttu-id="c3bfa-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="c3bfa-114">Attribute</span></span>|<span data-ttu-id="c3bfa-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c3bfa-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c3bfa-116">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="c3bfa-116">mapToWindows</span></span>|<span data-ttu-id="c3bfa-117">Gibt an, ob der Tokenhandler das validierende Token eine Windows-Konto zugeordnet werden sollen eingehenden Anspruch der UPN mit.</span><span class="sxs-lookup"><span data-stu-id="c3bfa-117">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="c3bfa-118">Der Standardwert ist "false".</span><span class="sxs-lookup"><span data-stu-id="c3bfa-118">The default is "false".</span></span>|  
|<span data-ttu-id="c3bfa-119">issuerCertificateRevocationMode</span><span class="sxs-lookup"><span data-stu-id="c3bfa-119">issuerCertificateRevocationMode</span></span>|<span data-ttu-id="c3bfa-120">Ein <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Wert, der angibt, den Sperrmodus, der für das x. 509-Zertifikat verwendet.</span><span class="sxs-lookup"><span data-stu-id="c3bfa-120">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="c3bfa-121">Der Standardwert lautet "Online".</span><span class="sxs-lookup"><span data-stu-id="c3bfa-121">The default value is "Online".</span></span>|  
|<span data-ttu-id="c3bfa-122">issuerCertificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="c3bfa-122">issuerCertificateValidationMode</span></span>|<span data-ttu-id="c3bfa-123">Ein <xref:System.ServiceModel.Security.X509CertificateValidationMode> Wert, der angibt, den Validierungsmodus für das x. 509-Zertifikat verwenden.</span><span class="sxs-lookup"><span data-stu-id="c3bfa-123">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="c3bfa-124">Der Standardwert ist "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="c3bfa-124">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="c3bfa-125">issuerCertificateTrustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="c3bfa-125">issuerCertificateTrustedStoreLocation</span></span>|<span data-ttu-id="c3bfa-126">Ein <xref:System.Security.Cryptography.X509Certificates.StoreLocation> Wert, der den x. 509-Zertifikatspeicher angibt.</span><span class="sxs-lookup"><span data-stu-id="c3bfa-126">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="c3bfa-127">Der Standardwert ist "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="c3bfa-127">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="c3bfa-128">issuerCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="c3bfa-128">issuerCertificateValidator</span></span>|<span data-ttu-id="c3bfa-129">Ein benutzerdefinierter Typ, die abgeleitet <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="c3bfa-129">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="c3bfa-130">Wenn die `issuerCertificateValidationMode` Attribut ist "Custom", eine Instanz dieses Typs für die Überprüfung Aussteller des Zertifikats verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="c3bfa-130">If the `issuerCertificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c3bfa-131">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c3bfa-131">Child Elements</span></span>  
  
|<span data-ttu-id="c3bfa-132">Element</span><span class="sxs-lookup"><span data-stu-id="c3bfa-132">Element</span></span>|<span data-ttu-id="c3bfa-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c3bfa-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c3bfa-134">\<NameClaimType ></span><span class="sxs-lookup"><span data-stu-id="c3bfa-134">\<nameClaimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/nameclaimtype.md)|<span data-ttu-id="c3bfa-135">Legt den Typ des Anspruchs, der angibt, die <xref:System.Security.Principal.IIdentity.Name%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="c3bfa-135">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span>|  
|[<span data-ttu-id="c3bfa-136">\<RoleClaimType ></span><span class="sxs-lookup"><span data-stu-id="c3bfa-136">\<roleClaimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/roleclaimtype.md)|<span data-ttu-id="c3bfa-137">Gibt an, der Typ des Anspruchs, der den Typ Rollenansprüche in der Auflistung von definiert <xref:System.Security.Claims.ClaimsIdentity> zurückgegebenen Objekte die <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> Methode von der Tokenhandler.</span><span class="sxs-lookup"><span data-stu-id="c3bfa-137">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c3bfa-138">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c3bfa-138">Parent Elements</span></span>  
  
|<span data-ttu-id="c3bfa-139">Element</span><span class="sxs-lookup"><span data-stu-id="c3bfa-139">Element</span></span>|<span data-ttu-id="c3bfa-140">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c3bfa-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c3bfa-141">\<add></span><span class="sxs-lookup"><span data-stu-id="c3bfa-141">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="c3bfa-142">Fügt den angegebenen Sicherheits-Tokenhandler der Tokenhandler Auflistung hinzu.</span><span class="sxs-lookup"><span data-stu-id="c3bfa-142">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c3bfa-143">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c3bfa-143">Remarks</span></span>  
 <span data-ttu-id="c3bfa-144">Die `<samlSecurityTokenRequirement>` Element dargestellt ist, indem die <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> Klasse im Objektmodell und dient zum Konfigurieren der `SamlSecurityTokenRequirement` Eigenschaft auf eine <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> oder eine <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span><span class="sxs-lookup"><span data-stu-id="c3bfa-144">The `<samlSecurityTokenRequirement>` element is represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class in the object model and is used to configure the `SamlSecurityTokenRequirement` property on a <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> or a <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3bfa-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c3bfa-145">Example</span></span>  
  
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
