---
title: '&lt;certificateValidation&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 778088f2e0508f5a80c29ae027b2442a80286795
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltcertificatevalidationgt"></a><span data-ttu-id="ac385-102">&lt;certificateValidation&gt;</span><span class="sxs-lookup"><span data-stu-id="ac385-102">&lt;certificateValidation&gt;</span></span>
<span data-ttu-id="ac385-103">Steuert die Einstellungen, die Tokenhandler verwenden, um Zertifikate zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="ac385-103">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="ac385-104">Diese Einstellungen werden überschrieben, wenn ein bestimmten Handler mit der eine eigene Überprüfungsfunktion konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="ac385-104">These settings are overridden if a specific handler is configured with its own validator.</span></span>  
  
 <span data-ttu-id="ac385-105">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="ac385-105">\<system.identityModel></span></span>  
<span data-ttu-id="ac385-106">\<IdentityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="ac385-106">\<identityConfiguration></span></span>  
<span data-ttu-id="ac385-107">\<CertificateValidation ></span><span class="sxs-lookup"><span data-stu-id="ac385-107">\<certificateValidation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac385-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="ac385-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <certificateValidation  
      certificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
      revocationMode="NoCheck||Offline||Online"  
      trustedStoreLocation="CurrentLocation||LocalMachine" >  
    </certificateValidation>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ac385-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ac385-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ac385-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ac385-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ac385-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="ac385-111">Attributes</span></span>  
  
|<span data-ttu-id="ac385-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="ac385-112">Attribute</span></span>|<span data-ttu-id="ac385-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ac385-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ac385-114">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="ac385-114">certificateValidationMode</span></span>|<span data-ttu-id="ac385-115">Ein <xref:System.ServiceModel.Security.X509CertificateValidationMode> Wert, der angibt, den Validierungsmodus für das x. 509-Zertifikat verwenden.</span><span class="sxs-lookup"><span data-stu-id="ac385-115">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="ac385-116">Der Standardwert ist "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="ac385-116">The default value is "PeerOrChainTrust".</span></span> <span data-ttu-id="ac385-117">Um ein benutzerdefiniertes Validierungssteuerelement anzugeben, legen Sie dieses Attribut auf "Benutzerdefiniert", und geben Sie das Validierungssteuerelement mithilfe der [ \<CertificateValidator >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md) Element.</span><span class="sxs-lookup"><span data-stu-id="ac385-117">To specify a custom validator, set this attribute to "Custom" and specify the validator using the [\<certificateValidator>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md) element.</span></span> <span data-ttu-id="ac385-118">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="ac385-118">Optional.</span></span>|  
|<span data-ttu-id="ac385-119">revocationMode</span><span class="sxs-lookup"><span data-stu-id="ac385-119">revocationMode</span></span>|<span data-ttu-id="ac385-120">Ein <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Wert, der angibt, den Sperrmodus, der für das x. 509-Zertifikat verwendet.</span><span class="sxs-lookup"><span data-stu-id="ac385-120">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="ac385-121">Der Standardwert lautet "Online".</span><span class="sxs-lookup"><span data-stu-id="ac385-121">The default value is "Online".</span></span> <span data-ttu-id="ac385-122">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="ac385-122">Optional.</span></span>|  
|<span data-ttu-id="ac385-123">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="ac385-123">trustedStoreLocation</span></span>|<span data-ttu-id="ac385-124">Ein <xref:System.Security.Cryptography.X509Certificates.StoreLocation> Wert, der den x. 509-Zertifikatspeicher angibt.</span><span class="sxs-lookup"><span data-stu-id="ac385-124">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="ac385-125">Der Standardwert ist "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="ac385-125">The default value is "LocalMachine".</span></span> <span data-ttu-id="ac385-126">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="ac385-126">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ac385-127">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ac385-127">Child Elements</span></span>  
  
|<span data-ttu-id="ac385-128">Element</span><span class="sxs-lookup"><span data-stu-id="ac385-128">Element</span></span>|<span data-ttu-id="ac385-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ac385-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ac385-130">\<CertificateValidator ></span><span class="sxs-lookup"><span data-stu-id="ac385-130">\<certificateValidator></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md)|<span data-ttu-id="ac385-131">Gibt einen benutzerdefinierten Typ für die Überprüfung des Zertifikats an.</span><span class="sxs-lookup"><span data-stu-id="ac385-131">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="ac385-132">Dieser Typ wird nur verwendet, wenn die `certificateValidationMode` Attribut von der [ \<CertificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) Element auf "Benutzerdefiniert" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ac385-132">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element is set to "Custom".</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ac385-133">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ac385-133">Parent Elements</span></span>  
  
|<span data-ttu-id="ac385-134">Element</span><span class="sxs-lookup"><span data-stu-id="ac385-134">Element</span></span>|<span data-ttu-id="ac385-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ac385-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ac385-136">\<IdentityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="ac385-136">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="ac385-137">Gibt an, Service Level identitätseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="ac385-137">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="ac385-138">\<SecurityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="ac385-138">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="ac385-139">Ermöglicht die Konfiguration für eine Auflistung der Tokenhandler.</span><span class="sxs-lookup"><span data-stu-id="ac385-139">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac385-140">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ac385-140">Remarks</span></span>  
 <span data-ttu-id="ac385-141">Ein `<certificateValidation>` Element angegeben werden kann, auf Dienstebene unter der `<identityConfiguration>` Element oder auf die Sicherheitsstufe für die Auflistung von Tokenhandler unter der `<securityTokenHandlerConfiguration>` Element.</span><span class="sxs-lookup"><span data-stu-id="ac385-141">A `<certificateValidation>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="ac385-142">Einstellungen für eine Sammlung Tokenhandler außer Kraft für den Dienst angegeben.</span><span class="sxs-lookup"><span data-stu-id="ac385-142">Settings on a token handler collection override those specified on the service.</span></span> <span data-ttu-id="ac385-143">Einige Tokenhandler können Sie in der Konfiguration Clientzertifikats-validierungseinstellungen an.</span><span class="sxs-lookup"><span data-stu-id="ac385-143">Some token handlers allow you to specify certificate validation settings in configuration.</span></span> <span data-ttu-id="ac385-144">Einstellungen für einzelne Tokenhandler überschreiben die angegebenen auf Dienstebene sowohl für die Sicherheit Tokenhandler-Auflistung.</span><span class="sxs-lookup"><span data-stu-id="ac385-144">Settings on individual token handlers override those specified both at the service level and on the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac385-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ac385-145">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```
