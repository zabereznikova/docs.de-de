---
title: <x509SecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: 6e8267f170dbb26381564be7b66df5f617156885
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790441"
---
# <a name="x509securitytokenhandlerrequirement"></a><span data-ttu-id="61ba7-101">\<x509SecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="61ba7-101">\<x509SecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="61ba7-102">Bietet optionale Konfiguration für die <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> Klasse oder abgeleitete Klassen.</span><span class="sxs-lookup"><span data-stu-id="61ba7-102">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="61ba7-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="61ba7-103">\<system.identityModel></span></span>  
<span data-ttu-id="61ba7-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="61ba7-104">\<identityConfiguration></span></span>  
<span data-ttu-id="61ba7-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="61ba7-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="61ba7-106">\<add></span><span class="sxs-lookup"><span data-stu-id="61ba7-106">\<add></span></span>  
<span data-ttu-id="61ba7-107">\<x509SecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="61ba7-107">\<x509SecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61ba7-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="61ba7-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
        <x509SecurityTokenHandlerRequirement>  
          mapToWindows=xs:boolean  
          certificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
          certificateValidator="Namespace.Class, Assembly"  
          revocationMode="NoCheck||Offline||Online"  
          trustedStoreLocation="CurrentUser||LocalMachine"  
        </x509SecurityTokenHandlerRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="61ba7-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="61ba7-109">Attributes and Elements</span></span>  
 <span data-ttu-id="61ba7-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="61ba7-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="61ba7-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="61ba7-111">Attributes</span></span>  
  
|<span data-ttu-id="61ba7-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="61ba7-112">Attribute</span></span>|<span data-ttu-id="61ba7-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="61ba7-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="61ba7-114">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="61ba7-114">certificateValidationMode</span></span>|<span data-ttu-id="61ba7-115">Ein <xref:System.ServiceModel.Security.X509CertificateValidationMode> Wert, der angibt, den Validierungsmodus für das x. 509-Zertifikat verwenden.</span><span class="sxs-lookup"><span data-stu-id="61ba7-115">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="61ba7-116">Der Standardwert ist "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="61ba7-116">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="61ba7-117">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="61ba7-117">mapToWindows</span></span>|<span data-ttu-id="61ba7-118">Gibt an, ob der Tokenhandler das überprüfende Token zu einem Windows-Konto zuordnen soll, mithilfe des eingehenden UPN-Anspruchs.</span><span class="sxs-lookup"><span data-stu-id="61ba7-118">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="61ba7-119">Der Standardwert ist "false".</span><span class="sxs-lookup"><span data-stu-id="61ba7-119">The default is "false".</span></span>|  
|<span data-ttu-id="61ba7-120">revocationMode</span><span class="sxs-lookup"><span data-stu-id="61ba7-120">revocationMode</span></span>|<span data-ttu-id="61ba7-121">Ein <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Wert, der angibt, den Sperrmodus für das x. 509-Zertifikat verwenden.</span><span class="sxs-lookup"><span data-stu-id="61ba7-121">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="61ba7-122">Der Standardwert lautet "Online".</span><span class="sxs-lookup"><span data-stu-id="61ba7-122">The default value is "Online".</span></span>|  
|<span data-ttu-id="61ba7-123">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="61ba7-123">trustedStoreLocation</span></span>|<span data-ttu-id="61ba7-124">Ein <xref:System.Security.Cryptography.X509Certificates.StoreLocation> Wert, der den x. 509-Zertifikatspeicher angibt.</span><span class="sxs-lookup"><span data-stu-id="61ba7-124">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="61ba7-125">Der Standardwert ist "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="61ba7-125">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="61ba7-126">certificateValidator</span><span class="sxs-lookup"><span data-stu-id="61ba7-126">certificateValidator</span></span>|<span data-ttu-id="61ba7-127">Ein benutzerdefinierter Typ, die von abgeleitet <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="61ba7-127">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="61ba7-128">Wenn die `certificateValidationMode` -Attribut ist "Custom", wird eine Instanz dieses Typs für die Überprüfung des Ausstellers Zertifikat verwendet.</span><span class="sxs-lookup"><span data-stu-id="61ba7-128">If the `certificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="61ba7-129">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="61ba7-129">Child Elements</span></span>  
 <span data-ttu-id="61ba7-130">Keiner</span><span class="sxs-lookup"><span data-stu-id="61ba7-130">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="61ba7-131">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="61ba7-131">Parent Elements</span></span>  
  
|<span data-ttu-id="61ba7-132">Element</span><span class="sxs-lookup"><span data-stu-id="61ba7-132">Element</span></span>|<span data-ttu-id="61ba7-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="61ba7-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="61ba7-134">\<add></span><span class="sxs-lookup"><span data-stu-id="61ba7-134">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="61ba7-135">Der Tokenhandler-Auflistung hinzugefügt den angegebenen Sicherheitstokenhandler.</span><span class="sxs-lookup"><span data-stu-id="61ba7-135">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="61ba7-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="61ba7-136">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"   
                                         certificateValidationMode="PeerOrChainTrust"   
                                         revocationMode="Online"   
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```
