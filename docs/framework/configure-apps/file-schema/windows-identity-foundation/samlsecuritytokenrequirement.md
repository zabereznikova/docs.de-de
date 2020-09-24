---
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: f93ec0007b537e306a570b166eaa4cd2fe7f81e2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157030"
---
# \<samlSecurityTokenRequirement>

<span data-ttu-id="cfe2f-101">Stellt die Konfiguration für die- <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> Klasse, die- <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> Klasse oder eine abgeleitete Klasse einer dieser Klassen bereit.</span><span class="sxs-lookup"><span data-stu-id="cfe2f-101">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span> <span data-ttu-id="cfe2f-102">Wird von der- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="cfe2f-102">Represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<samlSecurityTokenRequirement>**  
  
## <a name="syntax"></a><span data-ttu-id="cfe2f-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="cfe2f-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cfe2f-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="cfe2f-104">Attributes and Elements</span></span>  

 <span data-ttu-id="cfe2f-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cfe2f-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cfe2f-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="cfe2f-106">Attributes</span></span>  
  
|<span data-ttu-id="cfe2f-107">attribute</span><span class="sxs-lookup"><span data-stu-id="cfe2f-107">Attribute</span></span>|<span data-ttu-id="cfe2f-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cfe2f-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cfe2f-109">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="cfe2f-109">mapToWindows</span></span>|<span data-ttu-id="cfe2f-110">Gibt an, ob der Tokenhandler das Validierungs Token einem Windows-Konto zuordnen soll, indem der eingehende UPN-Anspruch verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cfe2f-110">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="cfe2f-111">Der Standardwert lautet "false".</span><span class="sxs-lookup"><span data-stu-id="cfe2f-111">The default is "false".</span></span>|  
|<span data-ttu-id="cfe2f-112">issuercertificaterevocationmode</span><span class="sxs-lookup"><span data-stu-id="cfe2f-112">issuerCertificateRevocationMode</span></span>|<span data-ttu-id="cfe2f-113">Ein- <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Wert, der den Sperrmodus angibt, der für das X. 509-Zertifikat verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="cfe2f-113">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="cfe2f-114">Der Standardwert ist "Online".</span><span class="sxs-lookup"><span data-stu-id="cfe2f-114">The default value is "Online".</span></span>|  
|<span data-ttu-id="cfe2f-115">issuercertifigatevalidationmode</span><span class="sxs-lookup"><span data-stu-id="cfe2f-115">issuerCertificateValidationMode</span></span>|<span data-ttu-id="cfe2f-116">Ein- <xref:System.ServiceModel.Security.X509CertificateValidationMode> Wert, der den Validierungs Modus angibt, der für das X. 509-Zertifikat verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="cfe2f-116">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="cfe2f-117">Der Standardwert ist "Peer-ChainTrust".</span><span class="sxs-lookup"><span data-stu-id="cfe2f-117">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="cfe2f-118">issuercertifieuretrustedstoreloation</span><span class="sxs-lookup"><span data-stu-id="cfe2f-118">issuerCertificateTrustedStoreLocation</span></span>|<span data-ttu-id="cfe2f-119">Ein- <xref:System.Security.Cryptography.X509Certificates.StoreLocation> Wert, der den X. 509-Zertifikat Speicher angibt.</span><span class="sxs-lookup"><span data-stu-id="cfe2f-119">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="cfe2f-120">Der Standardwert ist "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="cfe2f-120">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="cfe2f-121">issuercertifikatevalidator</span><span class="sxs-lookup"><span data-stu-id="cfe2f-121">issuerCertificateValidator</span></span>|<span data-ttu-id="cfe2f-122">Ein benutzerdefinierter Typ, der von abgeleitet wird <xref:System.IdentityModel.Selectors.X509CertificateValidator> .</span><span class="sxs-lookup"><span data-stu-id="cfe2f-122">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="cfe2f-123">Wenn das `issuerCertificateValidationMode` Attribut "Custom" ist, wird eine Instanz dieses Typs für die Überprüfung des Zertifikat Ausstellers verwendet.</span><span class="sxs-lookup"><span data-stu-id="cfe2f-123">If the `issuerCertificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cfe2f-124">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cfe2f-124">Child Elements</span></span>  
  
|<span data-ttu-id="cfe2f-125">Element</span><span class="sxs-lookup"><span data-stu-id="cfe2f-125">Element</span></span>|<span data-ttu-id="cfe2f-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cfe2f-126">Description</span></span>|  
|-------------|-----------------|  
|[\<nameClaimType>](nameclaimtype.md)|<span data-ttu-id="cfe2f-127">Legt den Anspruchstyp fest, der die <xref:System.Security.Principal.IIdentity.Name%2A> Eigenschaft angibt.</span><span class="sxs-lookup"><span data-stu-id="cfe2f-127">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span>|  
|[\<roleClaimType>](roleclaimtype.md)|<span data-ttu-id="cfe2f-128">Gibt den Anspruchstyp an, der die Rollen Typen Ansprüche in der Auflistung von-Objekten definiert, die <xref:System.Security.Claims.ClaimsIdentity> von der- <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> Methode des tokenhandlers zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="cfe2f-128">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cfe2f-129">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cfe2f-129">Parent Elements</span></span>  
  
|<span data-ttu-id="cfe2f-130">Element</span><span class="sxs-lookup"><span data-stu-id="cfe2f-130">Element</span></span>|<span data-ttu-id="cfe2f-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cfe2f-131">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add.md)|<span data-ttu-id="cfe2f-132">Fügt der tokenhandlerauflistung den angegebenen Sicherheitstokenhandler hinzu.</span><span class="sxs-lookup"><span data-stu-id="cfe2f-132">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cfe2f-133">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="cfe2f-133">Remarks</span></span>  

 <span data-ttu-id="cfe2f-134">Das `<samlSecurityTokenRequirement>` -Element wird durch die <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> -Klasse im Objektmodell dargestellt und zum Konfigurieren der- `SamlSecurityTokenRequirement` Eigenschaft in einem <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> oder einem verwendet <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> .</span><span class="sxs-lookup"><span data-stu-id="cfe2f-134">The `<samlSecurityTokenRequirement>` element is represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class in the object model and is used to configure the `SamlSecurityTokenRequirement` property on a <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> or a <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cfe2f-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cfe2f-135">Example</span></span>  
  
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
