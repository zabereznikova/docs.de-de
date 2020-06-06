---
title: <x509SecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: 30ce69a35cfdd34e0dfea5c682347eb9187e04ed
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152449"
---
# \<x509SecurityTokenHandlerRequirement>
<span data-ttu-id="50d0b-101">Stellt eine optionale Konfiguration für die- <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> Klasse oder abgeleitete Klassen bereit.</span><span class="sxs-lookup"><span data-stu-id="50d0b-101">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<x509SecurityTokenHandlerRequirement>**  
  
## <a name="syntax"></a><span data-ttu-id="50d0b-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="50d0b-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="50d0b-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="50d0b-103">Attributes and Elements</span></span>  
 <span data-ttu-id="50d0b-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="50d0b-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="50d0b-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="50d0b-105">Attributes</span></span>  
  
|<span data-ttu-id="50d0b-106">attribute</span><span class="sxs-lookup"><span data-stu-id="50d0b-106">Attribute</span></span>|<span data-ttu-id="50d0b-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="50d0b-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="50d0b-108">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="50d0b-108">certificateValidationMode</span></span>|<span data-ttu-id="50d0b-109">Ein- <xref:System.ServiceModel.Security.X509CertificateValidationMode> Wert, der den Validierungs Modus angibt, der für das X. 509-Zertifikat verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="50d0b-109">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="50d0b-110">Der Standardwert ist "Peer-ChainTrust".</span><span class="sxs-lookup"><span data-stu-id="50d0b-110">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="50d0b-111">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="50d0b-111">mapToWindows</span></span>|<span data-ttu-id="50d0b-112">Gibt an, ob der Tokenhandler das Validierungs Token einem Windows-Konto zuordnen soll, indem der eingehende UPN-Anspruch verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="50d0b-112">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="50d0b-113">Der Standardwert lautet "false".</span><span class="sxs-lookup"><span data-stu-id="50d0b-113">The default is "false".</span></span>|  
|<span data-ttu-id="50d0b-114">revocationMode</span><span class="sxs-lookup"><span data-stu-id="50d0b-114">revocationMode</span></span>|<span data-ttu-id="50d0b-115">Ein- <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Wert, der den Sperrmodus angibt, der für das X. 509-Zertifikat verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="50d0b-115">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="50d0b-116">Der Standardwert ist "Online".</span><span class="sxs-lookup"><span data-stu-id="50d0b-116">The default value is "Online".</span></span>|  
|<span data-ttu-id="50d0b-117">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="50d0b-117">trustedStoreLocation</span></span>|<span data-ttu-id="50d0b-118">Ein- <xref:System.Security.Cryptography.X509Certificates.StoreLocation> Wert, der den X. 509-Zertifikat Speicher angibt.</span><span class="sxs-lookup"><span data-stu-id="50d0b-118">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="50d0b-119">Der Standardwert ist "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="50d0b-119">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="50d0b-120">certifikatevalidator</span><span class="sxs-lookup"><span data-stu-id="50d0b-120">certificateValidator</span></span>|<span data-ttu-id="50d0b-121">Ein benutzerdefinierter Typ, der von abgeleitet wird <xref:System.IdentityModel.Selectors.X509CertificateValidator> .</span><span class="sxs-lookup"><span data-stu-id="50d0b-121">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="50d0b-122">Wenn das `certificateValidationMode` Attribut "Custom" ist, wird eine Instanz dieses Typs für die Überprüfung des Zertifikat Ausstellers verwendet.</span><span class="sxs-lookup"><span data-stu-id="50d0b-122">If the `certificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="50d0b-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="50d0b-123">Child Elements</span></span>  
 <span data-ttu-id="50d0b-124">Keine</span><span class="sxs-lookup"><span data-stu-id="50d0b-124">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="50d0b-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="50d0b-125">Parent Elements</span></span>  
  
|<span data-ttu-id="50d0b-126">Element</span><span class="sxs-lookup"><span data-stu-id="50d0b-126">Element</span></span>|<span data-ttu-id="50d0b-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="50d0b-127">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add.md)|<span data-ttu-id="50d0b-128">Fügt der tokenhandlerauflistung den angegebenen Sicherheitstokenhandler hinzu.</span><span class="sxs-lookup"><span data-stu-id="50d0b-128">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="50d0b-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="50d0b-129">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"
                                         certificateValidationMode="PeerOrChainTrust"
                                         revocationMode="Online"
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```
