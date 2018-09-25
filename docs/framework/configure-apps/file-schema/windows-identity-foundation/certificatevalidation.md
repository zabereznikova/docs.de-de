---
title: '&lt;certificateValidation&gt;'
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
ms.openlocfilehash: 29881be43f02d275ad135efd97dc8b25a7409beb
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47074787"
---
# <a name="ltcertificatevalidationgt"></a><span data-ttu-id="9718f-102">&lt;certificateValidation&gt;</span><span class="sxs-lookup"><span data-stu-id="9718f-102">&lt;certificateValidation&gt;</span></span>
<span data-ttu-id="9718f-103">Steuert die Einstellungen, die token-Handler zum Überprüfen von Zertifikaten verwenden.</span><span class="sxs-lookup"><span data-stu-id="9718f-103">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="9718f-104">Diese Einstellungen werden überschrieben, wenn ein bestimmten Handler mit der eine eigene Überprüfungsfunktion konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="9718f-104">These settings are overridden if a specific handler is configured with its own validator.</span></span>  
  
 <span data-ttu-id="9718f-105">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="9718f-105">\<system.identityModel></span></span>  
<span data-ttu-id="9718f-106">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="9718f-106">\<identityConfiguration></span></span>  
<span data-ttu-id="9718f-107">\<CertificateValidation ></span><span class="sxs-lookup"><span data-stu-id="9718f-107">\<certificateValidation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9718f-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="9718f-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9718f-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9718f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9718f-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9718f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9718f-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="9718f-111">Attributes</span></span>  
  
|<span data-ttu-id="9718f-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="9718f-112">Attribute</span></span>|<span data-ttu-id="9718f-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9718f-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9718f-114">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="9718f-114">certificateValidationMode</span></span>|<span data-ttu-id="9718f-115">Ein <xref:System.ServiceModel.Security.X509CertificateValidationMode> Wert, der angibt, den Validierungsmodus für das x. 509-Zertifikat verwenden.</span><span class="sxs-lookup"><span data-stu-id="9718f-115">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="9718f-116">Der Standardwert ist "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="9718f-116">The default value is "PeerOrChainTrust".</span></span> <span data-ttu-id="9718f-117">Um ein benutzerdefiniertes Validierungssteuerelement anzugeben, legen Sie dieses Attribut auf "Custom", und geben Sie das Validierungssteuerelement mit der [ \<CertificateValidator >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md) Element.</span><span class="sxs-lookup"><span data-stu-id="9718f-117">To specify a custom validator, set this attribute to "Custom" and specify the validator using the [\<certificateValidator>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md) element.</span></span> <span data-ttu-id="9718f-118">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="9718f-118">Optional.</span></span>|  
|<span data-ttu-id="9718f-119">revocationMode</span><span class="sxs-lookup"><span data-stu-id="9718f-119">revocationMode</span></span>|<span data-ttu-id="9718f-120">Ein <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Wert, der angibt, den Sperrmodus für das x. 509-Zertifikat verwenden.</span><span class="sxs-lookup"><span data-stu-id="9718f-120">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="9718f-121">Der Standardwert lautet "Online".</span><span class="sxs-lookup"><span data-stu-id="9718f-121">The default value is "Online".</span></span> <span data-ttu-id="9718f-122">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="9718f-122">Optional.</span></span>|  
|<span data-ttu-id="9718f-123">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="9718f-123">trustedStoreLocation</span></span>|<span data-ttu-id="9718f-124">Ein <xref:System.Security.Cryptography.X509Certificates.StoreLocation> Wert, der den x. 509-Zertifikatspeicher angibt.</span><span class="sxs-lookup"><span data-stu-id="9718f-124">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="9718f-125">Der Standardwert ist "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="9718f-125">The default value is "LocalMachine".</span></span> <span data-ttu-id="9718f-126">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="9718f-126">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9718f-127">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9718f-127">Child Elements</span></span>  
  
|<span data-ttu-id="9718f-128">Element</span><span class="sxs-lookup"><span data-stu-id="9718f-128">Element</span></span>|<span data-ttu-id="9718f-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9718f-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9718f-130">\<CertificateValidator ></span><span class="sxs-lookup"><span data-stu-id="9718f-130">\<certificateValidator></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md)|<span data-ttu-id="9718f-131">Gibt einen benutzerdefinierten Typ für die Überprüfung des Zertifikats an.</span><span class="sxs-lookup"><span data-stu-id="9718f-131">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="9718f-132">Dieser Typ wird verwendet, nur dann, wenn die `certificateValidationMode` Attribut der [ \<CertificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) Element in "Benutzerdefiniert" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="9718f-132">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element is set to "Custom".</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9718f-133">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9718f-133">Parent Elements</span></span>  
  
|<span data-ttu-id="9718f-134">Element</span><span class="sxs-lookup"><span data-stu-id="9718f-134">Element</span></span>|<span data-ttu-id="9718f-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9718f-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9718f-136">\<IdentityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="9718f-136">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="9718f-137">Gibt die identitätseinstellungen der Servicelevel.</span><span class="sxs-lookup"><span data-stu-id="9718f-137">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="9718f-138">\<SecurityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="9718f-138">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="9718f-139">Stellt die Konfiguration für eine Auflistung der Tokenhandler.</span><span class="sxs-lookup"><span data-stu-id="9718f-139">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9718f-140">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9718f-140">Remarks</span></span>  
 <span data-ttu-id="9718f-141">Ein `<certificateValidation>` Element kann angegeben werden, auf der Dienstebene unter der `<identityConfiguration>` Element oder die Sicherheitsstufe für die Auflistung von Tokenhandler unter der `<securityTokenHandlerConfiguration>` Element.</span><span class="sxs-lookup"><span data-stu-id="9718f-141">A `<certificateValidation>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="9718f-142">Einstellungen für eine Auflistung der Tokenhandler überschreiben jene, die für den Dienst angegeben.</span><span class="sxs-lookup"><span data-stu-id="9718f-142">Settings on a token handler collection override those specified on the service.</span></span> <span data-ttu-id="9718f-143">Einige Tokenhandler können Sie in der Konfiguration Clientzertifikats-validierungseinstellungen an.</span><span class="sxs-lookup"><span data-stu-id="9718f-143">Some token handlers allow you to specify certificate validation settings in configuration.</span></span> <span data-ttu-id="9718f-144">Einstellungen für einzelne Tokenhandler überschreiben angegeben, sowohl auf der Dienstebene und auf der Sicherheitstokenhandler-Sammlung.</span><span class="sxs-lookup"><span data-stu-id="9718f-144">Settings on individual token handlers override those specified both at the service level and on the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9718f-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9718f-145">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```
