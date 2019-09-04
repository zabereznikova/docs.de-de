---
title: <x509SecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: 76eeea635fd65486a1c16bea15a49018876dae99
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251694"
---
# <a name="x509securitytokenhandlerrequirement"></a><span data-ttu-id="a5844-101">\<x509SecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="a5844-101">\<x509SecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="a5844-102">Stellt eine optionale Konfiguration für <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> die-Klasse oder abgeleitete Klassen bereit.</span><span class="sxs-lookup"><span data-stu-id="a5844-102">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>  
  
<span data-ttu-id="a5844-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a5844-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a5844-104">&nbsp;&nbsp;[ **\<System. IdentityModel->** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="a5844-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="a5844-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityconfiguration->** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="a5844-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="a5844-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securitytokenhandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="a5844-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="a5844-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> Hinzufügen**](add.md)</span><span class="sxs-lookup"><span data-stu-id="a5844-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="a5844-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<x509SecurityTokenHandlerRequirement >**</span><span class="sxs-lookup"><span data-stu-id="a5844-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<x509SecurityTokenHandlerRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5844-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="a5844-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a5844-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a5844-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a5844-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a5844-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a5844-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="a5844-112">Attributes</span></span>  
  
|<span data-ttu-id="a5844-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="a5844-113">Attribute</span></span>|<span data-ttu-id="a5844-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a5844-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a5844-115">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="a5844-115">certificateValidationMode</span></span>|<span data-ttu-id="a5844-116">Ein <xref:System.ServiceModel.Security.X509CertificateValidationMode> -Wert, der den Validierungs Modus angibt, der für das X. 509-Zertifikat verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a5844-116">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="a5844-117">Der Standardwert ist "Peer-ChainTrust".</span><span class="sxs-lookup"><span data-stu-id="a5844-117">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="a5844-118">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="a5844-118">mapToWindows</span></span>|<span data-ttu-id="a5844-119">Gibt an, ob der Tokenhandler das Validierungs Token einem Windows-Konto zuordnen soll, indem der eingehende UPN-Anspruch verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a5844-119">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="a5844-120">Der Standardwert ist "false".</span><span class="sxs-lookup"><span data-stu-id="a5844-120">The default is "false".</span></span>|  
|<span data-ttu-id="a5844-121">revocationMode</span><span class="sxs-lookup"><span data-stu-id="a5844-121">revocationMode</span></span>|<span data-ttu-id="a5844-122">Ein <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> -Wert, der den Sperrmodus angibt, der für das X. 509-Zertifikat verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a5844-122">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="a5844-123">Der Standardwert ist "Online".</span><span class="sxs-lookup"><span data-stu-id="a5844-123">The default value is "Online".</span></span>|  
|<span data-ttu-id="a5844-124">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="a5844-124">trustedStoreLocation</span></span>|<span data-ttu-id="a5844-125">Ein <xref:System.Security.Cryptography.X509Certificates.StoreLocation> -Wert, der den X. 509-Zertifikat Speicher angibt.</span><span class="sxs-lookup"><span data-stu-id="a5844-125">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="a5844-126">Der Standardwert ist "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="a5844-126">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="a5844-127">certifikatevalidator</span><span class="sxs-lookup"><span data-stu-id="a5844-127">certificateValidator</span></span>|<span data-ttu-id="a5844-128">Ein benutzerdefinierter Typ, der <xref:System.IdentityModel.Selectors.X509CertificateValidator>von abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="a5844-128">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="a5844-129">Wenn das `certificateValidationMode` Attribut "Custom" ist, wird eine Instanz dieses Typs für die Überprüfung des Zertifikat Ausstellers verwendet.</span><span class="sxs-lookup"><span data-stu-id="a5844-129">If the `certificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a5844-130">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a5844-130">Child Elements</span></span>  
 <span data-ttu-id="a5844-131">None</span><span class="sxs-lookup"><span data-stu-id="a5844-131">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a5844-132">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a5844-132">Parent Elements</span></span>  
  
|<span data-ttu-id="a5844-133">Element</span><span class="sxs-lookup"><span data-stu-id="a5844-133">Element</span></span>|<span data-ttu-id="a5844-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a5844-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a5844-135">\<add></span><span class="sxs-lookup"><span data-stu-id="a5844-135">\<add></span></span>](add.md)|<span data-ttu-id="a5844-136">Fügt der tokenhandlerauflistung den angegebenen Sicherheitstokenhandler hinzu.</span><span class="sxs-lookup"><span data-stu-id="a5844-136">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a5844-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a5844-137">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"   
                                         certificateValidationMode="PeerOrChainTrust"   
                                         revocationMode="Online"   
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```
