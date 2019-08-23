---
title: <certificateValidation>
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
ms.openlocfilehash: 8185153eb02c5794b0f6ac02a6837806f2073c07
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941922"
---
# <a name="certificatevalidation"></a><span data-ttu-id="b5ed1-101">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="b5ed1-101">\<certificateValidation></span></span>
<span data-ttu-id="b5ed1-102">Steuert die Einstellungen, die von tokenhandlern zum Überprüfen von Zertifikaten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b5ed1-102">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="b5ed1-103">Diese Einstellungen werden überschrieben, wenn ein bestimmter Handler mit einem eigenen Validierungs Steuerelement konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="b5ed1-103">These settings are overridden if a specific handler is configured with its own validator.</span></span>  
  
 <span data-ttu-id="b5ed1-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="b5ed1-104">\<system.identityModel></span></span>  
<span data-ttu-id="b5ed1-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="b5ed1-105">\<identityConfiguration></span></span>  
<span data-ttu-id="b5ed1-106">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="b5ed1-106">\<certificateValidation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5ed1-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="b5ed1-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b5ed1-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b5ed1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b5ed1-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b5ed1-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b5ed1-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="b5ed1-110">Attributes</span></span>  
  
|<span data-ttu-id="b5ed1-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="b5ed1-111">Attribute</span></span>|<span data-ttu-id="b5ed1-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b5ed1-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b5ed1-113">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="b5ed1-113">certificateValidationMode</span></span>|<span data-ttu-id="b5ed1-114">Ein <xref:System.ServiceModel.Security.X509CertificateValidationMode> -Wert, der den Validierungs Modus angibt, der für das X. 509-Zertifikat verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b5ed1-114">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="b5ed1-115">Der Standardwert ist "Peer-ChainTrust".</span><span class="sxs-lookup"><span data-stu-id="b5ed1-115">The default value is "PeerOrChainTrust".</span></span> <span data-ttu-id="b5ed1-116">Wenn Sie ein benutzerdefiniertes Validierungs Steuerelement angeben möchten, legen Sie dieses Attribut auf "Custom" fest, und geben Sie das Validierungs Steuerelement mithilfe [ \<von "certifiinitievalidator" >](certificatevalidator.md)</span><span class="sxs-lookup"><span data-stu-id="b5ed1-116">To specify a custom validator, set this attribute to "Custom" and specify the validator using the [\<certificateValidator>](certificatevalidator.md) element.</span></span> <span data-ttu-id="b5ed1-117">Optional.</span><span class="sxs-lookup"><span data-stu-id="b5ed1-117">Optional.</span></span>|  
|<span data-ttu-id="b5ed1-118">revocationMode</span><span class="sxs-lookup"><span data-stu-id="b5ed1-118">revocationMode</span></span>|<span data-ttu-id="b5ed1-119">Ein <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> -Wert, der den Sperrmodus angibt, der für das X. 509-Zertifikat verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b5ed1-119">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="b5ed1-120">Der Standardwert ist "Online".</span><span class="sxs-lookup"><span data-stu-id="b5ed1-120">The default value is "Online".</span></span> <span data-ttu-id="b5ed1-121">Optional.</span><span class="sxs-lookup"><span data-stu-id="b5ed1-121">Optional.</span></span>|  
|<span data-ttu-id="b5ed1-122">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="b5ed1-122">trustedStoreLocation</span></span>|<span data-ttu-id="b5ed1-123">Ein <xref:System.Security.Cryptography.X509Certificates.StoreLocation> -Wert, der den X. 509-Zertifikat Speicher angibt.</span><span class="sxs-lookup"><span data-stu-id="b5ed1-123">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="b5ed1-124">Der Standardwert ist "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="b5ed1-124">The default value is "LocalMachine".</span></span> <span data-ttu-id="b5ed1-125">Optional.</span><span class="sxs-lookup"><span data-stu-id="b5ed1-125">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b5ed1-126">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b5ed1-126">Child Elements</span></span>  
  
|<span data-ttu-id="b5ed1-127">Element</span><span class="sxs-lookup"><span data-stu-id="b5ed1-127">Element</span></span>|<span data-ttu-id="b5ed1-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b5ed1-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b5ed1-129">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="b5ed1-129">\<certificateValidator></span></span>](certificatevalidator.md)|<span data-ttu-id="b5ed1-130">Gibt einen benutzerdefinierten Typ für die Zertifikats Überprüfung an.</span><span class="sxs-lookup"><span data-stu-id="b5ed1-130">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="b5ed1-131">Dieser Typ wird nur verwendet, wenn `certificateValidationMode` das-Attribut [ \<des certifiinitievalidation->](certificatevalidation.md) -Elements auf "Custom" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="b5ed1-131">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b5ed1-132">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b5ed1-132">Parent Elements</span></span>  
  
|<span data-ttu-id="b5ed1-133">Element</span><span class="sxs-lookup"><span data-stu-id="b5ed1-133">Element</span></span>|<span data-ttu-id="b5ed1-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b5ed1-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b5ed1-135">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="b5ed1-135">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="b5ed1-136">Gibt Identitäts Einstellungen auf Dienst Ebene an.</span><span class="sxs-lookup"><span data-stu-id="b5ed1-136">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="b5ed1-137">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="b5ed1-137">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="b5ed1-138">Stellt die Konfiguration für eine Auflistung von Sicherheitstokenhandlern bereit.</span><span class="sxs-lookup"><span data-stu-id="b5ed1-138">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b5ed1-139">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b5ed1-139">Remarks</span></span>  
 <span data-ttu-id="b5ed1-140">Ein `<certificateValidation>` -Element kann auf der Dienst Ebene unterhalb des `<identityConfiguration>` -Elements oder auf der Auflistungs Ebene des Sicherheitstokenhandlers unter dem `<securityTokenHandlerConfiguration>` -Element angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b5ed1-140">A `<certificateValidation>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="b5ed1-141">Einstellungen für eine tokenhandlerauflistung überschreiben die für den Dienst angegebenen.</span><span class="sxs-lookup"><span data-stu-id="b5ed1-141">Settings on a token handler collection override those specified on the service.</span></span> <span data-ttu-id="b5ed1-142">Einige Tokenhandler ermöglichen es Ihnen, Zertifikat Überprüfungs Einstellungen in der Konfiguration anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b5ed1-142">Some token handlers allow you to specify certificate validation settings in configuration.</span></span> <span data-ttu-id="b5ed1-143">Einstellungen in einzelnen tokenhandlern überschreiben die Angaben auf Dienst Ebene und in der Auflistung der Sicherheitstokenhandler.</span><span class="sxs-lookup"><span data-stu-id="b5ed1-143">Settings on individual token handlers override those specified both at the service level and on the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5ed1-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b5ed1-144">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```
