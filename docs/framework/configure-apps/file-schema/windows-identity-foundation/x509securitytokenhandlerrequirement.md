---
title: '&lt;x509SecurityTokenHandlerRequirement&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
caps.latest.revision: "3"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 66d4e0d6a121f807f5f372b3f39577b0bb3c4ca6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltx509securitytokenhandlerrequirementgt"></a><span data-ttu-id="acb8a-102">&lt;x509SecurityTokenHandlerRequirement&gt;</span><span class="sxs-lookup"><span data-stu-id="acb8a-102">&lt;x509SecurityTokenHandlerRequirement&gt;</span></span>
<span data-ttu-id="acb8a-103">Bietet optionale Konfiguration für die <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> abgeleiteten Klassen.</span><span class="sxs-lookup"><span data-stu-id="acb8a-103">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="acb8a-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="acb8a-104">\<system.identityModel></span></span>  
<span data-ttu-id="acb8a-105">\<IdentityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="acb8a-105">\<identityConfiguration></span></span>  
<span data-ttu-id="acb8a-106">\<SecurityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="acb8a-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="acb8a-107">\<add></span><span class="sxs-lookup"><span data-stu-id="acb8a-107">\<add></span></span>  
<span data-ttu-id="acb8a-108">\<x509SecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="acb8a-108">\<x509SecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acb8a-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="acb8a-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="acb8a-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="acb8a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="acb8a-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="acb8a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="acb8a-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="acb8a-112">Attributes</span></span>  
  
|<span data-ttu-id="acb8a-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="acb8a-113">Attribute</span></span>|<span data-ttu-id="acb8a-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="acb8a-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="acb8a-115">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="acb8a-115">certificateValidationMode</span></span>|<span data-ttu-id="acb8a-116">Ein <xref:System.ServiceModel.Security.X509CertificateValidationMode> Wert, der angibt, den Validierungsmodus für das x. 509-Zertifikat verwenden.</span><span class="sxs-lookup"><span data-stu-id="acb8a-116">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="acb8a-117">Der Standardwert ist "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="acb8a-117">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="acb8a-118">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="acb8a-118">mapToWindows</span></span>|<span data-ttu-id="acb8a-119">Gibt an, ob der Tokenhandler das validierende Token eine Windows-Konto zugeordnet werden sollen eingehenden Anspruch der UPN mit.</span><span class="sxs-lookup"><span data-stu-id="acb8a-119">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="acb8a-120">Der Standardwert ist "false".</span><span class="sxs-lookup"><span data-stu-id="acb8a-120">The default is "false".</span></span>|  
|<span data-ttu-id="acb8a-121">revocationMode</span><span class="sxs-lookup"><span data-stu-id="acb8a-121">revocationMode</span></span>|<span data-ttu-id="acb8a-122">Ein <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Wert, der angibt, den Sperrmodus, der für das x. 509-Zertifikat verwendet.</span><span class="sxs-lookup"><span data-stu-id="acb8a-122">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="acb8a-123">Der Standardwert lautet "Online".</span><span class="sxs-lookup"><span data-stu-id="acb8a-123">The default value is "Online".</span></span>|  
|<span data-ttu-id="acb8a-124">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="acb8a-124">trustedStoreLocation</span></span>|<span data-ttu-id="acb8a-125">Ein <xref:System.Security.Cryptography.X509Certificates.StoreLocation> Wert, der den x. 509-Zertifikatspeicher angibt.</span><span class="sxs-lookup"><span data-stu-id="acb8a-125">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="acb8a-126">Der Standardwert ist "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="acb8a-126">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="acb8a-127">certificateValidator</span><span class="sxs-lookup"><span data-stu-id="acb8a-127">certificateValidator</span></span>|<span data-ttu-id="acb8a-128">Ein benutzerdefinierter Typ, die abgeleitet <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="acb8a-128">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="acb8a-129">Wenn die `certificateValidationMode` Attribut ist "Custom", eine Instanz dieses Typs für die Überprüfung Aussteller des Zertifikats verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="acb8a-129">If the `certificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="acb8a-130">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="acb8a-130">Child Elements</span></span>  
 <span data-ttu-id="acb8a-131">Keine</span><span class="sxs-lookup"><span data-stu-id="acb8a-131">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="acb8a-132">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="acb8a-132">Parent Elements</span></span>  
  
|<span data-ttu-id="acb8a-133">Element</span><span class="sxs-lookup"><span data-stu-id="acb8a-133">Element</span></span>|<span data-ttu-id="acb8a-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="acb8a-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="acb8a-135">\<add></span><span class="sxs-lookup"><span data-stu-id="acb8a-135">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="acb8a-136">Fügt den angegebenen Sicherheits-Tokenhandler der Tokenhandler Auflistung hinzu.</span><span class="sxs-lookup"><span data-stu-id="acb8a-136">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="acb8a-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="acb8a-137">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"   
                                         certificateValidationMode="PeerOrChainTrust"   
                                         revocationMode="Online"   
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```
