---
title: <certificateValidation>
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
ms.openlocfilehash: 7b8823d792e3f15846a9483d670994be4b368980
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55273896"
---
# <a name="certificatevalidation"></a><span data-ttu-id="49eb8-101">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="49eb8-101">\<certificateValidation></span></span>
<span data-ttu-id="49eb8-102">Steuert die Einstellungen, die token-Handler zum Überprüfen von Zertifikaten verwenden.</span><span class="sxs-lookup"><span data-stu-id="49eb8-102">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="49eb8-103">Diese Einstellungen werden überschrieben, wenn ein bestimmten Handler mit der eine eigene Überprüfungsfunktion konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="49eb8-103">These settings are overridden if a specific handler is configured with its own validator.</span></span>  
  
 <span data-ttu-id="49eb8-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="49eb8-104">\<system.identityModel></span></span>  
<span data-ttu-id="49eb8-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="49eb8-105">\<identityConfiguration></span></span>  
<span data-ttu-id="49eb8-106">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="49eb8-106">\<certificateValidation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49eb8-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="49eb8-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="49eb8-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="49eb8-108">Attributes and Elements</span></span>  
 <span data-ttu-id="49eb8-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="49eb8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="49eb8-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="49eb8-110">Attributes</span></span>  
  
|<span data-ttu-id="49eb8-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="49eb8-111">Attribute</span></span>|<span data-ttu-id="49eb8-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="49eb8-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="49eb8-113">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="49eb8-113">certificateValidationMode</span></span>|<span data-ttu-id="49eb8-114">Ein <xref:System.ServiceModel.Security.X509CertificateValidationMode> Wert, der angibt, den Validierungsmodus für das x. 509-Zertifikat verwenden.</span><span class="sxs-lookup"><span data-stu-id="49eb8-114">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="49eb8-115">Der Standardwert ist "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="49eb8-115">The default value is "PeerOrChainTrust".</span></span> <span data-ttu-id="49eb8-116">Um ein benutzerdefiniertes Validierungssteuerelement anzugeben, legen Sie dieses Attribut auf "Custom", und geben Sie das Validierungssteuerelement mit der [ \<CertificateValidator >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md) Element.</span><span class="sxs-lookup"><span data-stu-id="49eb8-116">To specify a custom validator, set this attribute to "Custom" and specify the validator using the [\<certificateValidator>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md) element.</span></span> <span data-ttu-id="49eb8-117">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="49eb8-117">Optional.</span></span>|  
|<span data-ttu-id="49eb8-118">revocationMode</span><span class="sxs-lookup"><span data-stu-id="49eb8-118">revocationMode</span></span>|<span data-ttu-id="49eb8-119">Ein <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Wert, der angibt, den Sperrmodus für das x. 509-Zertifikat verwenden.</span><span class="sxs-lookup"><span data-stu-id="49eb8-119">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="49eb8-120">Der Standardwert lautet "Online".</span><span class="sxs-lookup"><span data-stu-id="49eb8-120">The default value is "Online".</span></span> <span data-ttu-id="49eb8-121">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="49eb8-121">Optional.</span></span>|  
|<span data-ttu-id="49eb8-122">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="49eb8-122">trustedStoreLocation</span></span>|<span data-ttu-id="49eb8-123">Ein <xref:System.Security.Cryptography.X509Certificates.StoreLocation> Wert, der den x. 509-Zertifikatspeicher angibt.</span><span class="sxs-lookup"><span data-stu-id="49eb8-123">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="49eb8-124">Der Standardwert ist "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="49eb8-124">The default value is "LocalMachine".</span></span> <span data-ttu-id="49eb8-125">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="49eb8-125">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="49eb8-126">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="49eb8-126">Child Elements</span></span>  
  
|<span data-ttu-id="49eb8-127">Element</span><span class="sxs-lookup"><span data-stu-id="49eb8-127">Element</span></span>|<span data-ttu-id="49eb8-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="49eb8-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="49eb8-129">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="49eb8-129">\<certificateValidator></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md)|<span data-ttu-id="49eb8-130">Gibt einen benutzerdefinierten Typ für die Überprüfung des Zertifikats an.</span><span class="sxs-lookup"><span data-stu-id="49eb8-130">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="49eb8-131">Dieser Typ wird verwendet, nur dann, wenn die `certificateValidationMode` Attribut der [ \<CertificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) Element in "Benutzerdefiniert" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="49eb8-131">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element is set to "Custom".</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="49eb8-132">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="49eb8-132">Parent Elements</span></span>  
  
|<span data-ttu-id="49eb8-133">Element</span><span class="sxs-lookup"><span data-stu-id="49eb8-133">Element</span></span>|<span data-ttu-id="49eb8-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="49eb8-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="49eb8-135">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="49eb8-135">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="49eb8-136">Gibt die identitätseinstellungen der Servicelevel.</span><span class="sxs-lookup"><span data-stu-id="49eb8-136">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="49eb8-137">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="49eb8-137">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="49eb8-138">Stellt die Konfiguration für eine Auflistung der Tokenhandler.</span><span class="sxs-lookup"><span data-stu-id="49eb8-138">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="49eb8-139">Hinweise</span><span class="sxs-lookup"><span data-stu-id="49eb8-139">Remarks</span></span>  
 <span data-ttu-id="49eb8-140">Ein `<certificateValidation>` Element kann angegeben werden, auf der Dienstebene unter der `<identityConfiguration>` Element oder die Sicherheitsstufe für die Auflistung von Tokenhandler unter der `<securityTokenHandlerConfiguration>` Element.</span><span class="sxs-lookup"><span data-stu-id="49eb8-140">A `<certificateValidation>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="49eb8-141">Einstellungen für eine Auflistung der Tokenhandler überschreiben jene, die für den Dienst angegeben.</span><span class="sxs-lookup"><span data-stu-id="49eb8-141">Settings on a token handler collection override those specified on the service.</span></span> <span data-ttu-id="49eb8-142">Einige Tokenhandler können Sie in der Konfiguration Clientzertifikats-validierungseinstellungen an.</span><span class="sxs-lookup"><span data-stu-id="49eb8-142">Some token handlers allow you to specify certificate validation settings in configuration.</span></span> <span data-ttu-id="49eb8-143">Einstellungen für einzelne Tokenhandler überschreiben angegeben, sowohl auf der Dienstebene und auf der Sicherheitstokenhandler-Sammlung.</span><span class="sxs-lookup"><span data-stu-id="49eb8-143">Settings on individual token handlers override those specified both at the service level and on the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49eb8-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="49eb8-144">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```
