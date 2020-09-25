---
title: <certificateValidation>
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
ms.openlocfilehash: 583fef7eb364c39890b3f9304770b383c1ea6d2a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183506"
---
# \<certificateValidation>

<span data-ttu-id="ab439-101">Steuert die Einstellungen, die von tokenhandlern zum Überprüfen von Zertifikaten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ab439-101">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="ab439-102">Diese Einstellungen werden überschrieben, wenn ein bestimmter Handler mit einem eigenen Validierungs Steuerelement konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="ab439-102">These settings are overridden if a specific handler is configured with its own validator.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateValidation>**  
  
## <a name="syntax"></a><span data-ttu-id="ab439-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="ab439-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ab439-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ab439-104">Attributes and Elements</span></span>  

 <span data-ttu-id="ab439-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ab439-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ab439-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="ab439-106">Attributes</span></span>  
  
|<span data-ttu-id="ab439-107">attribute</span><span class="sxs-lookup"><span data-stu-id="ab439-107">Attribute</span></span>|<span data-ttu-id="ab439-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ab439-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ab439-109">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="ab439-109">certificateValidationMode</span></span>|<span data-ttu-id="ab439-110">Ein- <xref:System.ServiceModel.Security.X509CertificateValidationMode> Wert, der den Validierungs Modus angibt, der für das X. 509-Zertifikat verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ab439-110">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="ab439-111">Der Standardwert ist "Peer-ChainTrust".</span><span class="sxs-lookup"><span data-stu-id="ab439-111">The default value is "PeerOrChainTrust".</span></span> <span data-ttu-id="ab439-112">Um ein benutzerdefiniertes Validierungs Steuerelement anzugeben, legen Sie dieses Attribut auf "Custom" fest, und geben Sie das Validierungs Steuerelement mithilfe des- [\<certificateValidator>](certificatevalidator.md) Elements an</span><span class="sxs-lookup"><span data-stu-id="ab439-112">To specify a custom validator, set this attribute to "Custom" and specify the validator using the [\<certificateValidator>](certificatevalidator.md) element.</span></span> <span data-ttu-id="ab439-113">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="ab439-113">Optional.</span></span>|  
|<span data-ttu-id="ab439-114">revocationMode</span><span class="sxs-lookup"><span data-stu-id="ab439-114">revocationMode</span></span>|<span data-ttu-id="ab439-115">Ein- <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Wert, der den Sperrmodus angibt, der für das X. 509-Zertifikat verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ab439-115">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="ab439-116">Der Standardwert ist "Online".</span><span class="sxs-lookup"><span data-stu-id="ab439-116">The default value is "Online".</span></span> <span data-ttu-id="ab439-117">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="ab439-117">Optional.</span></span>|  
|<span data-ttu-id="ab439-118">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="ab439-118">trustedStoreLocation</span></span>|<span data-ttu-id="ab439-119">Ein- <xref:System.Security.Cryptography.X509Certificates.StoreLocation> Wert, der den X. 509-Zertifikat Speicher angibt.</span><span class="sxs-lookup"><span data-stu-id="ab439-119">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="ab439-120">Der Standardwert ist "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="ab439-120">The default value is "LocalMachine".</span></span> <span data-ttu-id="ab439-121">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="ab439-121">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ab439-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ab439-122">Child Elements</span></span>  
  
|<span data-ttu-id="ab439-123">Element</span><span class="sxs-lookup"><span data-stu-id="ab439-123">Element</span></span>|<span data-ttu-id="ab439-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ab439-124">Description</span></span>|  
|-------------|-----------------|  
|[\<certificateValidator>](certificatevalidator.md)|<span data-ttu-id="ab439-125">Gibt einen benutzerdefinierten Typ für die Zertifikats Überprüfung an.</span><span class="sxs-lookup"><span data-stu-id="ab439-125">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="ab439-126">Dieser Typ wird nur verwendet, wenn das- `certificateValidationMode` Attribut des- [\<certificateValidation>](certificatevalidation.md) Elements auf "Custom" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ab439-126">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ab439-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ab439-127">Parent Elements</span></span>  
  
|<span data-ttu-id="ab439-128">Element</span><span class="sxs-lookup"><span data-stu-id="ab439-128">Element</span></span>|<span data-ttu-id="ab439-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ab439-129">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="ab439-130">Gibt Identitäts Einstellungen auf Dienst Ebene an.</span><span class="sxs-lookup"><span data-stu-id="ab439-130">Specifies service-level identity settings.</span></span>|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="ab439-131">Stellt die Konfiguration für eine Auflistung von Sicherheitstokenhandlern bereit.</span><span class="sxs-lookup"><span data-stu-id="ab439-131">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ab439-132">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ab439-132">Remarks</span></span>  

 <span data-ttu-id="ab439-133">Ein- `<certificateValidation>` Element kann auf der Dienst Ebene unterhalb des- `<identityConfiguration>` Elements oder auf der Auflistungs Ebene des Sicherheitstokenhandlers unter dem-Element angegeben werden `<securityTokenHandlerConfiguration>` .</span><span class="sxs-lookup"><span data-stu-id="ab439-133">A `<certificateValidation>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="ab439-134">Einstellungen für eine tokenhandlerauflistung überschreiben die für den Dienst angegebenen.</span><span class="sxs-lookup"><span data-stu-id="ab439-134">Settings on a token handler collection override those specified on the service.</span></span> <span data-ttu-id="ab439-135">Einige Tokenhandler ermöglichen es Ihnen, Zertifikat Überprüfungs Einstellungen in der Konfiguration anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ab439-135">Some token handlers allow you to specify certificate validation settings in configuration.</span></span> <span data-ttu-id="ab439-136">Einstellungen in einzelnen tokenhandlern überschreiben die Angaben auf Dienst Ebene und in der Auflistung der Sicherheitstokenhandler.</span><span class="sxs-lookup"><span data-stu-id="ab439-136">Settings on individual token handlers override those specified both at the service level and on the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ab439-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ab439-137">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```
