---
title: <messageSenderAuthentication>
ms.date: 03/30/2017
ms.assetid: ea62fc06-55fb-42e0-aa2b-8867bdf4b415
ms.openlocfilehash: c6183a8d27d56c7199b815ccb31b06f983a51b33
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398389"
---
# \<messageSenderAuthentication>
<span data-ttu-id="1e058-101">Gibt Authentifizierungseinstellungen für ein Peerzertifikat an, das von einem Nachrichtenabsender verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1e058-101">Specifies authentication settings for peer certificate used by a message sender.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<messageSenderAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="1e058-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="1e058-102">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1e058-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1e058-103">Attributes and Elements</span></span>  
 <span data-ttu-id="1e058-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1e058-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1e058-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="1e058-105">Attributes</span></span>  
  
|<span data-ttu-id="1e058-106">attribute</span><span class="sxs-lookup"><span data-stu-id="1e058-106">Attribute</span></span>|<span data-ttu-id="1e058-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1e058-107">Description</span></span>|  
|---------------|-----------------|  
|`certificateValidationMode`|<span data-ttu-id="1e058-108">Optionale Enumeration.</span><span class="sxs-lookup"><span data-stu-id="1e058-108">Optional enumeration.</span></span> <span data-ttu-id="1e058-109">Gibt einen von fünf die Überprüfung von Anmeldeinformationen verwendeten Modi an.</span><span class="sxs-lookup"><span data-stu-id="1e058-109">Specifies one of five modes used to validate credentials.</span></span> <span data-ttu-id="1e058-110">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="1e058-110">This attribute is of type <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="1e058-111">Wenn dies auf `Custom` festgelegt wurde, muss auch ein `customCertificateValidator` bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="1e058-111">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="1e058-112">Optionale Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="1e058-112">Optional string.</span></span> <span data-ttu-id="1e058-113">Bestimmt einen Typ und eine Assembly, die zum Prüfen eines benutzerdefinierten Typs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1e058-113">Specifies a type and assembly used to validate a custom type.</span></span> <span data-ttu-id="1e058-114">Das Attribut muss festgelegt werden, wenn für `certificateValidationMode` der Wert `Custom` festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="1e058-114">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span> <span data-ttu-id="1e058-115">Dieses Attribut ist vom Typ <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="1e058-115">This attribute is of type <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="1e058-116">Windows Communication Foundation (WCF) stellt ein Standardmäßiges Peer Zertifikat-Validierungs Steuerelement bereit, das das Peer Zertifikat anhand des Speicher vertrauenswürdiger Personen überprüft.</span><span class="sxs-lookup"><span data-stu-id="1e058-116">Windows Communication Foundation (WCF) provides a default peer certificate validator that verifies the peer certificate against the trusted people store.</span></span> <span data-ttu-id="1e058-117">Außerdem wird überprüft, ob sich das Zertifikat zu einem gültigen Stamm verkettet.</span><span class="sxs-lookup"><span data-stu-id="1e058-117">It also verifies that the certificate chains up to a valid root.</span></span> <span data-ttu-id="1e058-118">Sie können ein benutzerdefiniertes Validierungssteuerelement implementieren, um ein anderes Verhalten anzugeben und dieses Attribut zum Verweisen auf das benutzerdefinierte Validierungssteuerelement verwenden.</span><span class="sxs-lookup"><span data-stu-id="1e058-118">You can implement a custom validator to specify a different behavior and use this attribute to point to the custom validator.</span></span>|  
|`revocationMode`|<span data-ttu-id="1e058-119">Optionale Enumeration.</span><span class="sxs-lookup"><span data-stu-id="1e058-119">Optional enumeration.</span></span> <span data-ttu-id="1e058-120">Legt den Zertifikatssperrmodus fest.</span><span class="sxs-lookup"><span data-stu-id="1e058-120">Specifies the certificate revocation mode.</span></span> <span data-ttu-id="1e058-121">Dieses Attribut ist vom Typ <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span><span class="sxs-lookup"><span data-stu-id="1e058-121">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span> <span data-ttu-id="1e058-122">Das System stellt anhand der Liste mit den gesperrten Zertifikaten sicher, dass das Clientzertifikat nicht gesperrt wurde.</span><span class="sxs-lookup"><span data-stu-id="1e058-122">The system verifies that the peer certificate has not been revoked by looking it up in the revoked certificate list.</span></span> <span data-ttu-id="1e058-123">Diese Überprüfung kann entweder online oder offline mit einer zwischengespeicherten Liste gesperrter Zertifikate erfolgen.</span><span class="sxs-lookup"><span data-stu-id="1e058-123">This check can be performed either by checking online or against a cached revocation list.</span></span> <span data-ttu-id="1e058-124">Die Sperrüberprüfung kann deaktiviert werden, indem für dieses Attribut der Wert NoCheck festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="1e058-124">Revocation checking can be turned off by setting this attribute to NoCheck.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="1e058-125">Optionale Enumeration.</span><span class="sxs-lookup"><span data-stu-id="1e058-125">Optional enumeration.</span></span> <span data-ttu-id="1e058-126">Gibt den vertrauenswürdigen Speicherort an, an dem das Peer Zertifikat vom WCF-Sicherheitssystem überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="1e058-126">Specifies the trusted store location where the peer certificate is validated by the WCF security system.</span></span> <span data-ttu-id="1e058-127">Dieses Attribut ist vom Typ <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span><span class="sxs-lookup"><span data-stu-id="1e058-127">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1e058-128">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1e058-128">Child Elements</span></span>  
 <span data-ttu-id="1e058-129">Keine</span><span class="sxs-lookup"><span data-stu-id="1e058-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1e058-130">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1e058-130">Parent Elements</span></span>  
  
|<span data-ttu-id="1e058-131">Element</span><span class="sxs-lookup"><span data-stu-id="1e058-131">Element</span></span>|<span data-ttu-id="1e058-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1e058-132">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-servicecredentials.md)|<span data-ttu-id="1e058-133">Gibt die aktuellen Anmeldeinformationen für einen Peerknoten an.</span><span class="sxs-lookup"><span data-stu-id="1e058-133">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e058-134">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="1e058-134">Remarks</span></span>  
 <span data-ttu-id="1e058-135">Dieses Element muss konfiguriert werden, wenn die Nachrichtenauthentifizierung ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="1e058-135">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="1e058-136">Für Ausgabekanäle wird jede Nachricht mit dem von bereitgestellten Zertifikat signiert [\<certificate>](certificate-element.md) .</span><span class="sxs-lookup"><span data-stu-id="1e058-136">For output channels, each message is signed using the certificate provided by [\<certificate>](certificate-element.md).</span></span> <span data-ttu-id="1e058-137">Alle Nachrichten werden vor dem Zustellen zur Anwendung mithilfe des durch das `customCertificateValidatorType`-Attribut dieses Elements angegebenen Validierungssteuerelements mit den Nachrichtenanmeldeinformationen verglichen.</span><span class="sxs-lookup"><span data-stu-id="1e058-137">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="1e058-138">Das Validierungssteuerelement kann die Anmeldeinformationen akzeptieren oder ablehnen.</span><span class="sxs-lookup"><span data-stu-id="1e058-138">The validator can either accept or reject the credential.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e058-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1e058-139">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- [<span data-ttu-id="1e058-140">Verwenden von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="1e058-140">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="1e058-141">Peer-to-Peer-Netzwerke</span><span class="sxs-lookup"><span data-stu-id="1e058-141">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="1e058-142">[Peerkanal-Nachrichtenauthentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="1e058-142">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="1e058-143">[Benutzerdefinierte Peerkanal-Authentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="1e058-143">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="1e058-144">Sichern von Peerkanalanwendungen</span><span class="sxs-lookup"><span data-stu-id="1e058-144">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
