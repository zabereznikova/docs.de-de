---
title: <x509SecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: 30ce69a35cfdd34e0dfea5c682347eb9187e04ed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152449"
---
# <a name="x509securitytokenhandlerrequirement"></a><span data-ttu-id="9b347-101">\<x509SecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="9b347-101">\<x509SecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="9b347-102">Stellt eine optionale Konfiguration für die <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> Klasse oder abgeleitete Klassen bereit.</span><span class="sxs-lookup"><span data-stu-id="9b347-102">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>  
  
<span data-ttu-id="9b347-103">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9b347-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9b347-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="9b347-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="9b347-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="9b347-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="9b347-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="9b347-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="9b347-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<hinzufügen>**](add.md)</span><span class="sxs-lookup"><span data-stu-id="9b347-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="9b347-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<x509SecurityTokenHandlerRequirement>**</span><span class="sxs-lookup"><span data-stu-id="9b347-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<x509SecurityTokenHandlerRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b347-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b347-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b347-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9b347-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9b347-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9b347-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b347-112">Attributes</span><span class="sxs-lookup"><span data-stu-id="9b347-112">Attributes</span></span>  
  
|<span data-ttu-id="9b347-113">attribute</span><span class="sxs-lookup"><span data-stu-id="9b347-113">Attribute</span></span>|<span data-ttu-id="9b347-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9b347-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9b347-115">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="9b347-115">certificateValidationMode</span></span>|<span data-ttu-id="9b347-116">Ein <xref:System.ServiceModel.Security.X509CertificateValidationMode> Wert, der den Validierungsmodus angibt, der für das X.509-Zertifikat verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9b347-116">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="9b347-117">Der Standardwert ist "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="9b347-117">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="9b347-118">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="9b347-118">mapToWindows</span></span>|<span data-ttu-id="9b347-119">Gibt an, ob der Tokenhandler das Validierungstoken mithilfe des eingehenden UPN-Anspruchs einem Windows-Konto zuordnen soll.</span><span class="sxs-lookup"><span data-stu-id="9b347-119">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="9b347-120">Der Standardwert lautet "false".</span><span class="sxs-lookup"><span data-stu-id="9b347-120">The default is "false".</span></span>|  
|<span data-ttu-id="9b347-121">revocationMode</span><span class="sxs-lookup"><span data-stu-id="9b347-121">revocationMode</span></span>|<span data-ttu-id="9b347-122">Ein <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Wert, der den Sperrmodus angibt, der für das X.509-Zertifikat verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9b347-122">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="9b347-123">Der Standardwert ist "Online".</span><span class="sxs-lookup"><span data-stu-id="9b347-123">The default value is "Online".</span></span>|  
|<span data-ttu-id="9b347-124">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="9b347-124">trustedStoreLocation</span></span>|<span data-ttu-id="9b347-125">Ein <xref:System.Security.Cryptography.X509Certificates.StoreLocation> Wert, der den X.509-Zertifikatspeicher angibt.</span><span class="sxs-lookup"><span data-stu-id="9b347-125">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="9b347-126">Der Standardwert ist "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="9b347-126">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="9b347-127">certificateValidator</span><span class="sxs-lookup"><span data-stu-id="9b347-127">certificateValidator</span></span>|<span data-ttu-id="9b347-128">Ein benutzerdefinierter Typ, <xref:System.IdentityModel.Selectors.X509CertificateValidator>der von ableitet.</span><span class="sxs-lookup"><span data-stu-id="9b347-128">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="9b347-129">Wenn `certificateValidationMode` das Attribut "Custom" lautet, wird eine Instanz dieses Typs für die Validierung von Ausstellerzertifikaten verwendet.</span><span class="sxs-lookup"><span data-stu-id="9b347-129">If the `certificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9b347-130">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9b347-130">Child Elements</span></span>  
 <span data-ttu-id="9b347-131">Keine</span><span class="sxs-lookup"><span data-stu-id="9b347-131">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9b347-132">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9b347-132">Parent Elements</span></span>  
  
|<span data-ttu-id="9b347-133">Element</span><span class="sxs-lookup"><span data-stu-id="9b347-133">Element</span></span>|<span data-ttu-id="9b347-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9b347-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9b347-135">\<hinzufügen></span><span class="sxs-lookup"><span data-stu-id="9b347-135">\<add></span></span>](add.md)|<span data-ttu-id="9b347-136">Fügt der Tokenhandlerauflistung den angegebenen Sicherheitstokenhandler hinzu.</span><span class="sxs-lookup"><span data-stu-id="9b347-136">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9b347-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9b347-137">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"
                                         certificateValidationMode="PeerOrChainTrust"
                                         revocationMode="Online"
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```
