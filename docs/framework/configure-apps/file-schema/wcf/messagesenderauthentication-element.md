---
title: <messageSenderAuthentication>-Element
ms.date: 03/30/2017
ms.assetid: 8d979dfc-a6f9-42ec-96d5-7fbc13a48118
ms.openlocfilehash: bab0e50d7feba3ea55d505be07cfa41427a5cbbc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397787"
---
# <a name="messagesenderauthentication-element"></a><span data-ttu-id="eec7a-102">\<messageSenderAuthentication>-Element</span><span class="sxs-lookup"><span data-stu-id="eec7a-102">\<messageSenderAuthentication> element</span></span>
<span data-ttu-id="eec7a-103">Gibt die Authentifizierungsoptionen für Peer-to-Peer-Nachrichtenabsender an.</span><span class="sxs-lookup"><span data-stu-id="eec7a-103">Specifies authentication options for peer-to-peer message senders.</span></span>  
  
 <span data-ttu-id="eec7a-104">Weitere Informationen zur Peer-zu-Peer-Programmierung finden Sie unter [Peer-to-Peer-Netzwerke](../../../wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="eec7a-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<messageSenderAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="eec7a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="eec7a-105">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType= "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eec7a-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="eec7a-106">Attributes and Elements</span></span>  
 <span data-ttu-id="eec7a-107">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="eec7a-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eec7a-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="eec7a-108">Attributes</span></span>  
  
|<span data-ttu-id="eec7a-109">attribute</span><span class="sxs-lookup"><span data-stu-id="eec7a-109">Attribute</span></span>|<span data-ttu-id="eec7a-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="eec7a-110">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="eec7a-111">Ein Typ und eine Assembly, die zum Überprüfen eines benutzerdefinierten Typs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="eec7a-111">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="eec7a-112">Das Attribut muss festgelegt werden, wenn für `certificateValidationMode` der Wert `Custom` festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="eec7a-112">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="eec7a-113">Gibt einen der drei für die Überprüfung von Anmeldeinformationen verwendeten Modi an.</span><span class="sxs-lookup"><span data-stu-id="eec7a-113">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="eec7a-114">Wenn dies auf `Custom` festgelegt wurde, muss auch ein `customCertificateValidator` bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="eec7a-114">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`revocationMode`|<span data-ttu-id="eec7a-115">Einer der Modi zum Prüfen auf eine Liste gesperrter Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="eec7a-115">One of the modes used to check for a revoked certificate lists (CRL).</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="eec7a-116">Einer der beiden Systemspeicherorte: `LocalMachine` oder `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="eec7a-116">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="eec7a-117">Dieser Wert wird verwendet, wenn ein Dienstzertifikat mit dem Client ausgehandelt wird.</span><span class="sxs-lookup"><span data-stu-id="eec7a-117">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="eec7a-118">Die Überprüfung wird für den Speicher für **Vertrauenswürdige Personen** am angegebenen Speicherort durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="eec7a-118">Validation is performed against the **Trusted People** store in the specified store location.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="eec7a-119">customCertificateValidatorType-Attribut</span><span class="sxs-lookup"><span data-stu-id="eec7a-119">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="eec7a-120">Wert</span><span class="sxs-lookup"><span data-stu-id="eec7a-120">Value</span></span>|<span data-ttu-id="eec7a-121">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="eec7a-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="eec7a-122">String</span><span class="sxs-lookup"><span data-stu-id="eec7a-122">String</span></span>|<span data-ttu-id="eec7a-123">(Optional)</span><span class="sxs-lookup"><span data-stu-id="eec7a-123">Optional.</span></span> <span data-ttu-id="eec7a-124">Gibt den vollständigen Typnamen und die Assembly sowie weitere Daten zum Suchen des Typs an.</span><span class="sxs-lookup"><span data-stu-id="eec7a-124">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="eec7a-125">Mindestens ein Namespace und Typname sind erforderlich.</span><span class="sxs-lookup"><span data-stu-id="eec7a-125">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="eec7a-126">Zu den optionalen Informationen zählen: Assemblyname, Versionsnummer, Kultur und Token des öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="eec7a-126">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="eec7a-127">certificateValidationMode-Attribut</span><span class="sxs-lookup"><span data-stu-id="eec7a-127">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="eec7a-128">Wert</span><span class="sxs-lookup"><span data-stu-id="eec7a-128">Value</span></span>|<span data-ttu-id="eec7a-129">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="eec7a-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="eec7a-130">Enumeration</span><span class="sxs-lookup"><span data-stu-id="eec7a-130">Enumeration</span></span>|<span data-ttu-id="eec7a-131">(Optional)</span><span class="sxs-lookup"><span data-stu-id="eec7a-131">Optional.</span></span> <span data-ttu-id="eec7a-132">Einer der folgenden Werte: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span><span class="sxs-lookup"><span data-stu-id="eec7a-132">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="eec7a-133">Der Standardwert lautet `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="eec7a-133">The default is `ChainTrust`.</span></span> <span data-ttu-id="eec7a-134">Der Standardwert lautet `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="eec7a-134">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="eec7a-135">Weitere Informationen finden Sie unter [Arbeiten mit Zertifikaten](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="eec7a-135">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="eec7a-136">revocationMode-Attribut</span><span class="sxs-lookup"><span data-stu-id="eec7a-136">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="eec7a-137">Wert</span><span class="sxs-lookup"><span data-stu-id="eec7a-137">Value</span></span>|<span data-ttu-id="eec7a-138">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="eec7a-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="eec7a-139">Enumeration</span><span class="sxs-lookup"><span data-stu-id="eec7a-139">Enumeration</span></span>|<span data-ttu-id="eec7a-140">Einer der folgenden Werte: `NoCheck`, `Online`, `Offline`.</span><span class="sxs-lookup"><span data-stu-id="eec7a-140">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="eec7a-141">Der Standardwert lautet `Online`.</span><span class="sxs-lookup"><span data-stu-id="eec7a-141">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="eec7a-142">Weitere Informationen finden Sie unter [Arbeiten mit Zertifikaten](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="eec7a-142">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="eec7a-143">trustedStoreLocation-Attribut</span><span class="sxs-lookup"><span data-stu-id="eec7a-143">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="eec7a-144">Wert</span><span class="sxs-lookup"><span data-stu-id="eec7a-144">Value</span></span>|<span data-ttu-id="eec7a-145">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="eec7a-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="eec7a-146">Enumeration</span><span class="sxs-lookup"><span data-stu-id="eec7a-146">Enumeration</span></span>|<span data-ttu-id="eec7a-147">Einer der folgenden Werte: `LocalMachine` oder `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="eec7a-147">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="eec7a-148">Der Standardwert lautet `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="eec7a-148">The default is `CurrentUser`.</span></span> <span data-ttu-id="eec7a-149">Wenn die Clientanwendung über ein Systemkonto ausgeführt wird, befindet sich das Zertifikat in der Regel in `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="eec7a-149">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="eec7a-150">Wenn die Clientanwendung über ein Benutzerkonto ausgeführt wird, befindet sich das Zertifikat in der Regel in `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="eec7a-150">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span> <span data-ttu-id="eec7a-151">Der Standardwert lautet `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="eec7a-151">The default is `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eec7a-152">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="eec7a-152">Child Elements</span></span>  
 <span data-ttu-id="eec7a-153">Keine</span><span class="sxs-lookup"><span data-stu-id="eec7a-153">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eec7a-154">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="eec7a-154">Parent Elements</span></span>  
  
|<span data-ttu-id="eec7a-155">Element</span><span class="sxs-lookup"><span data-stu-id="eec7a-155">Element</span></span>|<span data-ttu-id="eec7a-156">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eec7a-156">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-clientcredentials-element.md)|<span data-ttu-id="eec7a-157">Gibt Anmeldeinformationen an, die zur Authentifizierung des Clients bei einem Peerdienst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="eec7a-157">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eec7a-158">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="eec7a-158">Remarks</span></span>  
 <span data-ttu-id="eec7a-159">Dieses Element muss konfiguriert werden, wenn die Nachrichtenauthentifizierung ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="eec7a-159">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="eec7a-160">Für Ausgabekanäle wird jede Nachricht mit dem von bereitgestellten Zertifikat signiert [\<certificate>](certificate-element.md) .</span><span class="sxs-lookup"><span data-stu-id="eec7a-160">For output channels, each message is signed using the certificate provided by [\<certificate>](certificate-element.md).</span></span> <span data-ttu-id="eec7a-161">Alle Nachrichten werden vor dem Zustellen zur Anwendung mithilfe des durch das `customCertificateValidatorType`-Attribut dieses Elements angegebenen Validierungssteuerelements mit den Nachrichtenanmeldeinformationen verglichen.</span><span class="sxs-lookup"><span data-stu-id="eec7a-161">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="eec7a-162">Das Validierungssteuerelement kann die Anmeldeinformationen akzeptieren oder ablehnen.</span><span class="sxs-lookup"><span data-stu-id="eec7a-162">The validator can either accept or reject the credential.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eec7a-163">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eec7a-163">Example</span></span>  
 <span data-ttu-id="eec7a-164">Mit dem folgenden Code wird der Validierungsmodus des Nachrichtenabsenders auf `PeerOrChainTrust` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="eec7a-164">The following code sets the message sender validation mode to `PeerOrChainTrust`.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <peer>
          <certificate findValue="www.contoso.com"
                       storeLocation="LocalMachine"
                       x509FindType="FindByIssuerName" />
          <messageSenderAuthentication certificateValidationMode="PeerOrChainTrust" />
          <messageSenderAuthentication certificateValidationMode="None" />
        </peer>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="eec7a-165">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eec7a-165">See also</span></span>

- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="eec7a-166">Verwenden von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="eec7a-166">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="eec7a-167">Peer-to-Peer-Netzwerke</span><span class="sxs-lookup"><span data-stu-id="eec7a-167">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="eec7a-168">[Peerkanal-Nachrichtenauthentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="eec7a-168">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="eec7a-169">[Benutzerdefinierte Peerkanal-Authentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="eec7a-169">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="eec7a-170">Sichern von Peerkanalanwendungen</span><span class="sxs-lookup"><span data-stu-id="eec7a-170">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
