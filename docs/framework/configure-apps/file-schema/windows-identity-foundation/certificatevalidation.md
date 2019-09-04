---
title: <certificateValidation>
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
ms.openlocfilehash: c2d1a5d36cb5616ef06eedc093dd70a68a164a81
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252134"
---
# <a name="certificatevalidation"></a><span data-ttu-id="58f3f-101">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="58f3f-101">\<certificateValidation></span></span>
<span data-ttu-id="58f3f-102">Steuert die Einstellungen, die von tokenhandlern zum Überprüfen von Zertifikaten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="58f3f-102">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="58f3f-103">Diese Einstellungen werden überschrieben, wenn ein bestimmter Handler mit einem eigenen Validierungs Steuerelement konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="58f3f-103">These settings are overridden if a specific handler is configured with its own validator.</span></span>  
  
<span data-ttu-id="58f3f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="58f3f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="58f3f-105">&nbsp;&nbsp;[ **\<System. IdentityModel->** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="58f3f-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="58f3f-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityconfiguration->** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="58f3f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="58f3f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<certifialievalidation->**</span><span class="sxs-lookup"><span data-stu-id="58f3f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateValidation>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58f3f-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="58f3f-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="58f3f-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="58f3f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="58f3f-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="58f3f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="58f3f-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="58f3f-111">Attributes</span></span>  
  
|<span data-ttu-id="58f3f-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="58f3f-112">Attribute</span></span>|<span data-ttu-id="58f3f-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58f3f-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="58f3f-114">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="58f3f-114">certificateValidationMode</span></span>|<span data-ttu-id="58f3f-115">Ein <xref:System.ServiceModel.Security.X509CertificateValidationMode> -Wert, der den Validierungs Modus angibt, der für das X. 509-Zertifikat verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="58f3f-115">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="58f3f-116">Der Standardwert ist "Peer-ChainTrust".</span><span class="sxs-lookup"><span data-stu-id="58f3f-116">The default value is "PeerOrChainTrust".</span></span> <span data-ttu-id="58f3f-117">Wenn Sie ein benutzerdefiniertes Validierungs Steuerelement angeben möchten, legen Sie dieses Attribut auf "Custom" fest, und geben Sie das Validierungs Steuerelement mithilfe [ \<von "certifiinitievalidator" >](certificatevalidator.md)</span><span class="sxs-lookup"><span data-stu-id="58f3f-117">To specify a custom validator, set this attribute to "Custom" and specify the validator using the [\<certificateValidator>](certificatevalidator.md) element.</span></span> <span data-ttu-id="58f3f-118">Optional.</span><span class="sxs-lookup"><span data-stu-id="58f3f-118">Optional.</span></span>|  
|<span data-ttu-id="58f3f-119">revocationMode</span><span class="sxs-lookup"><span data-stu-id="58f3f-119">revocationMode</span></span>|<span data-ttu-id="58f3f-120">Ein <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> -Wert, der den Sperrmodus angibt, der für das X. 509-Zertifikat verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="58f3f-120">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="58f3f-121">Der Standardwert ist "Online".</span><span class="sxs-lookup"><span data-stu-id="58f3f-121">The default value is "Online".</span></span> <span data-ttu-id="58f3f-122">Optional.</span><span class="sxs-lookup"><span data-stu-id="58f3f-122">Optional.</span></span>|  
|<span data-ttu-id="58f3f-123">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="58f3f-123">trustedStoreLocation</span></span>|<span data-ttu-id="58f3f-124">Ein <xref:System.Security.Cryptography.X509Certificates.StoreLocation> -Wert, der den X. 509-Zertifikat Speicher angibt.</span><span class="sxs-lookup"><span data-stu-id="58f3f-124">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="58f3f-125">Der Standardwert ist "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="58f3f-125">The default value is "LocalMachine".</span></span> <span data-ttu-id="58f3f-126">Optional.</span><span class="sxs-lookup"><span data-stu-id="58f3f-126">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="58f3f-127">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="58f3f-127">Child Elements</span></span>  
  
|<span data-ttu-id="58f3f-128">Element</span><span class="sxs-lookup"><span data-stu-id="58f3f-128">Element</span></span>|<span data-ttu-id="58f3f-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58f3f-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="58f3f-130">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="58f3f-130">\<certificateValidator></span></span>](certificatevalidator.md)|<span data-ttu-id="58f3f-131">Gibt einen benutzerdefinierten Typ für die Zertifikats Überprüfung an.</span><span class="sxs-lookup"><span data-stu-id="58f3f-131">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="58f3f-132">Dieser Typ wird nur verwendet, wenn `certificateValidationMode` das-Attribut [ \<des certifiinitievalidation->](certificatevalidation.md) -Elements auf "Custom" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="58f3f-132">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="58f3f-133">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="58f3f-133">Parent Elements</span></span>  
  
|<span data-ttu-id="58f3f-134">Element</span><span class="sxs-lookup"><span data-stu-id="58f3f-134">Element</span></span>|<span data-ttu-id="58f3f-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58f3f-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="58f3f-136">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="58f3f-136">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="58f3f-137">Gibt Identitäts Einstellungen auf Dienst Ebene an.</span><span class="sxs-lookup"><span data-stu-id="58f3f-137">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="58f3f-138">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="58f3f-138">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="58f3f-139">Stellt die Konfiguration für eine Auflistung von Sicherheitstokenhandlern bereit.</span><span class="sxs-lookup"><span data-stu-id="58f3f-139">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58f3f-140">Hinweise</span><span class="sxs-lookup"><span data-stu-id="58f3f-140">Remarks</span></span>  
 <span data-ttu-id="58f3f-141">Ein `<certificateValidation>` -Element kann auf der Dienst Ebene unterhalb des `<identityConfiguration>` -Elements oder auf der Auflistungs Ebene des Sicherheitstokenhandlers unter dem `<securityTokenHandlerConfiguration>` -Element angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="58f3f-141">A `<certificateValidation>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="58f3f-142">Einstellungen für eine tokenhandlerauflistung überschreiben die für den Dienst angegebenen.</span><span class="sxs-lookup"><span data-stu-id="58f3f-142">Settings on a token handler collection override those specified on the service.</span></span> <span data-ttu-id="58f3f-143">Einige Tokenhandler ermöglichen es Ihnen, Zertifikat Überprüfungs Einstellungen in der Konfiguration anzugeben.</span><span class="sxs-lookup"><span data-stu-id="58f3f-143">Some token handlers allow you to specify certificate validation settings in configuration.</span></span> <span data-ttu-id="58f3f-144">Einstellungen in einzelnen tokenhandlern überschreiben die Angaben auf Dienst Ebene und in der Auflistung der Sicherheitstokenhandler.</span><span class="sxs-lookup"><span data-stu-id="58f3f-144">Settings on individual token handlers override those specified both at the service level and on the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58f3f-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="58f3f-145">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```
