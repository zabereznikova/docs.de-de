---
title: <x509SecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: 2851820460a34d62175929b48ad57914df557059
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945184"
---
# <a name="x509securitytokenhandlerrequirement"></a><span data-ttu-id="1c0c5-101">\<x509SecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="1c0c5-101">\<x509SecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="1c0c5-102">Stellt eine optionale Konfiguration für <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> die-Klasse oder abgeleitete Klassen bereit.</span><span class="sxs-lookup"><span data-stu-id="1c0c5-102">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="1c0c5-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="1c0c5-103">\<system.identityModel></span></span>  
<span data-ttu-id="1c0c5-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="1c0c5-104">\<identityConfiguration></span></span>  
<span data-ttu-id="1c0c5-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="1c0c5-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="1c0c5-106">\<add></span><span class="sxs-lookup"><span data-stu-id="1c0c5-106">\<add></span></span>  
<span data-ttu-id="1c0c5-107">\<x509SecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="1c0c5-107">\<x509SecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c0c5-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="1c0c5-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1c0c5-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1c0c5-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1c0c5-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1c0c5-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1c0c5-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="1c0c5-111">Attributes</span></span>  
  
|<span data-ttu-id="1c0c5-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="1c0c5-112">Attribute</span></span>|<span data-ttu-id="1c0c5-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1c0c5-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1c0c5-114">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="1c0c5-114">certificateValidationMode</span></span>|<span data-ttu-id="1c0c5-115">Ein <xref:System.ServiceModel.Security.X509CertificateValidationMode> -Wert, der den Validierungs Modus angibt, der für das X. 509-Zertifikat verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="1c0c5-115">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="1c0c5-116">Der Standardwert ist "Peer-ChainTrust".</span><span class="sxs-lookup"><span data-stu-id="1c0c5-116">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="1c0c5-117">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="1c0c5-117">mapToWindows</span></span>|<span data-ttu-id="1c0c5-118">Gibt an, ob der Tokenhandler das Validierungs Token einem Windows-Konto zuordnen soll, indem der eingehende UPN-Anspruch verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1c0c5-118">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="1c0c5-119">Der Standardwert ist "false".</span><span class="sxs-lookup"><span data-stu-id="1c0c5-119">The default is "false".</span></span>|  
|<span data-ttu-id="1c0c5-120">revocationMode</span><span class="sxs-lookup"><span data-stu-id="1c0c5-120">revocationMode</span></span>|<span data-ttu-id="1c0c5-121">Ein <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> -Wert, der den Sperrmodus angibt, der für das X. 509-Zertifikat verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="1c0c5-121">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="1c0c5-122">Der Standardwert ist "Online".</span><span class="sxs-lookup"><span data-stu-id="1c0c5-122">The default value is "Online".</span></span>|  
|<span data-ttu-id="1c0c5-123">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="1c0c5-123">trustedStoreLocation</span></span>|<span data-ttu-id="1c0c5-124">Ein <xref:System.Security.Cryptography.X509Certificates.StoreLocation> -Wert, der den X. 509-Zertifikat Speicher angibt.</span><span class="sxs-lookup"><span data-stu-id="1c0c5-124">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="1c0c5-125">Der Standardwert ist "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="1c0c5-125">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="1c0c5-126">certifikatevalidator</span><span class="sxs-lookup"><span data-stu-id="1c0c5-126">certificateValidator</span></span>|<span data-ttu-id="1c0c5-127">Ein benutzerdefinierter Typ, der <xref:System.IdentityModel.Selectors.X509CertificateValidator>von abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="1c0c5-127">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="1c0c5-128">Wenn das `certificateValidationMode` Attribut "Custom" ist, wird eine Instanz dieses Typs für die Überprüfung des Zertifikat Ausstellers verwendet.</span><span class="sxs-lookup"><span data-stu-id="1c0c5-128">If the `certificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1c0c5-129">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1c0c5-129">Child Elements</span></span>  
 <span data-ttu-id="1c0c5-130">None</span><span class="sxs-lookup"><span data-stu-id="1c0c5-130">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1c0c5-131">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1c0c5-131">Parent Elements</span></span>  
  
|<span data-ttu-id="1c0c5-132">Element</span><span class="sxs-lookup"><span data-stu-id="1c0c5-132">Element</span></span>|<span data-ttu-id="1c0c5-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1c0c5-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1c0c5-134">\<add></span><span class="sxs-lookup"><span data-stu-id="1c0c5-134">\<add></span></span>](add.md)|<span data-ttu-id="1c0c5-135">Fügt der tokenhandlerauflistung den angegebenen Sicherheitstokenhandler hinzu.</span><span class="sxs-lookup"><span data-stu-id="1c0c5-135">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1c0c5-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1c0c5-136">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"   
                                         certificateValidationMode="PeerOrChainTrust"   
                                         revocationMode="Online"   
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```
