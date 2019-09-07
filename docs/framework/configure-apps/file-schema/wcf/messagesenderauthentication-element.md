---
title: <messageSenderAuthentication>-Element
ms.date: 03/30/2017
ms.assetid: 8d979dfc-a6f9-42ec-96d5-7fbc13a48118
ms.openlocfilehash: bab0e50d7feba3ea55d505be07cfa41427a5cbbc
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397787"
---
# <a name="messagesenderauthentication-element"></a><span data-ttu-id="39861-102">\<messagesenderauthentication-> Element</span><span class="sxs-lookup"><span data-stu-id="39861-102">\<messageSenderAuthentication> element</span></span>
<span data-ttu-id="39861-103">Gibt die Authentifizierungsoptionen für Peer-to-Peer-Nachrichtenabsender an.</span><span class="sxs-lookup"><span data-stu-id="39861-103">Specifies authentication options for peer-to-peer message senders.</span></span>  
  
 <span data-ttu-id="39861-104">Weitere Informationen zur Peer-zu-Peer-Programmierung finden Sie unter [Peer-to-Peer-Netzwerke](../../../wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="39861-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
<span data-ttu-id="39861-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="39861-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="39861-106">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="39861-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="39861-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="39861-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="39861-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointverhaltens->** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="39861-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="39861-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="39861-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="39861-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Client Anmelde Informationen >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="39861-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="39861-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Peer >** ](peer-of-clientcredentials-element.md)</span><span class="sxs-lookup"><span data-stu-id="39861-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)</span></span>\
<span data-ttu-id="39861-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<messagesenderauthentication->**</span><span class="sxs-lookup"><span data-stu-id="39861-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<messageSenderAuthentication>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39861-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="39861-113">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType= "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="39861-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="39861-114">Attributes and Elements</span></span>  
 <span data-ttu-id="39861-115">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="39861-115">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="39861-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="39861-116">Attributes</span></span>  
  
|<span data-ttu-id="39861-117">Attribut</span><span class="sxs-lookup"><span data-stu-id="39861-117">Attribute</span></span>|<span data-ttu-id="39861-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="39861-118">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="39861-119">Ein Typ und eine Assembly, die zum Überprüfen eines benutzerdefinierten Typs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="39861-119">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="39861-120">Das Attribut muss festgelegt werden, wenn für `certificateValidationMode` der Wert `Custom` festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="39861-120">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="39861-121">Gibt einen der drei für die Überprüfung von Anmeldeinformationen verwendeten Modi an.</span><span class="sxs-lookup"><span data-stu-id="39861-121">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="39861-122">Wenn dies auf `Custom` festgelegt wurde, muss auch ein `customCertificateValidator` bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="39861-122">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`revocationMode`|<span data-ttu-id="39861-123">Einer der Modi zum Prüfen auf eine Liste gesperrter Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="39861-123">One of the modes used to check for a revoked certificate lists (CRL).</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="39861-124">Einer der beiden Systemspeicherorte: `LocalMachine` oder `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="39861-124">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="39861-125">Dieser Wert wird verwendet, wenn ein Dienstzertifikat mit dem Client ausgehandelt wird.</span><span class="sxs-lookup"><span data-stu-id="39861-125">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="39861-126">Die Überprüfung wird für den Speicher für **Vertrauenswürdige Personen** am angegebenen Speicherort durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="39861-126">Validation is performed against the **Trusted People** store in the specified store location.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="39861-127">customCertificateValidatorType-Attribut</span><span class="sxs-lookup"><span data-stu-id="39861-127">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="39861-128">Wert</span><span class="sxs-lookup"><span data-stu-id="39861-128">Value</span></span>|<span data-ttu-id="39861-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="39861-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="39861-130">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="39861-130">String</span></span>|<span data-ttu-id="39861-131">Optional.</span><span class="sxs-lookup"><span data-stu-id="39861-131">Optional.</span></span> <span data-ttu-id="39861-132">Gibt den vollständigen Typnamen und die Assembly sowie weitere Daten zum Suchen des Typs an.</span><span class="sxs-lookup"><span data-stu-id="39861-132">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="39861-133">Mindestens ein Namespace und Typname sind erforderlich.</span><span class="sxs-lookup"><span data-stu-id="39861-133">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="39861-134">Zu den optionalen Informationen zählen: Assemblyname, Versionsnummer, Kultur und Token des öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="39861-134">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="39861-135">certificateValidationMode-Attribut</span><span class="sxs-lookup"><span data-stu-id="39861-135">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="39861-136">Wert</span><span class="sxs-lookup"><span data-stu-id="39861-136">Value</span></span>|<span data-ttu-id="39861-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="39861-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="39861-138">Enumeration</span><span class="sxs-lookup"><span data-stu-id="39861-138">Enumeration</span></span>|<span data-ttu-id="39861-139">Optional.</span><span class="sxs-lookup"><span data-stu-id="39861-139">Optional.</span></span> <span data-ttu-id="39861-140">Einer der folgenden Werte: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span><span class="sxs-lookup"><span data-stu-id="39861-140">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="39861-141">Die Standardeinstellung ist `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="39861-141">The default is `ChainTrust`.</span></span> <span data-ttu-id="39861-142">Die Standardeinstellung ist `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="39861-142">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="39861-143">Weitere Informationen finden Sie unter [Arbeiten mit Zertifikaten](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="39861-143">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="39861-144">revocationMode-Attribut</span><span class="sxs-lookup"><span data-stu-id="39861-144">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="39861-145">Wert</span><span class="sxs-lookup"><span data-stu-id="39861-145">Value</span></span>|<span data-ttu-id="39861-146">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="39861-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="39861-147">Enumeration</span><span class="sxs-lookup"><span data-stu-id="39861-147">Enumeration</span></span>|<span data-ttu-id="39861-148">Einer der folgenden Werte: `NoCheck`, `Online`, `Offline`.</span><span class="sxs-lookup"><span data-stu-id="39861-148">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="39861-149">Die Standardeinstellung ist `Online`.</span><span class="sxs-lookup"><span data-stu-id="39861-149">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="39861-150">Weitere Informationen finden Sie unter [Arbeiten mit Zertifikaten](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="39861-150">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="39861-151">trustedStoreLocation-Attribut</span><span class="sxs-lookup"><span data-stu-id="39861-151">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="39861-152">Wert</span><span class="sxs-lookup"><span data-stu-id="39861-152">Value</span></span>|<span data-ttu-id="39861-153">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="39861-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="39861-154">Enumeration</span><span class="sxs-lookup"><span data-stu-id="39861-154">Enumeration</span></span>|<span data-ttu-id="39861-155">Einer der folgenden Werte: `LocalMachine` oder `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="39861-155">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="39861-156">Die Standardeinstellung ist `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="39861-156">The default is `CurrentUser`.</span></span> <span data-ttu-id="39861-157">Wenn die Clientanwendung über ein Systemkonto ausgeführt wird, befindet sich das Zertifikat in der Regel in `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="39861-157">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="39861-158">Wenn die Clientanwendung über ein Benutzerkonto ausgeführt wird, befindet sich das Zertifikat in der Regel in `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="39861-158">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span> <span data-ttu-id="39861-159">Die Standardeinstellung ist `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="39861-159">The default is `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="39861-160">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="39861-160">Child Elements</span></span>  
 <span data-ttu-id="39861-161">Keine</span><span class="sxs-lookup"><span data-stu-id="39861-161">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="39861-162">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="39861-162">Parent Elements</span></span>  
  
|<span data-ttu-id="39861-163">Element</span><span class="sxs-lookup"><span data-stu-id="39861-163">Element</span></span>|<span data-ttu-id="39861-164">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="39861-164">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="39861-165">\<peer></span><span class="sxs-lookup"><span data-stu-id="39861-165">\<peer></span></span>](peer-of-clientcredentials-element.md)|<span data-ttu-id="39861-166">Gibt Anmeldeinformationen an, die zur Authentifizierung des Clients bei einem Peerdienst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="39861-166">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39861-167">Hinweise</span><span class="sxs-lookup"><span data-stu-id="39861-167">Remarks</span></span>  
 <span data-ttu-id="39861-168">Dieses Element muss konfiguriert werden, wenn die Nachrichtenauthentifizierung ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="39861-168">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="39861-169">Für Ausgabekanäle wird jede Nachricht mit dem Zertifikat signiert, das von [ \<Certificate >](certificate-element.md)bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="39861-169">For output channels, each message is signed using the certificate provided by [\<certificate>](certificate-element.md).</span></span> <span data-ttu-id="39861-170">Alle Nachrichten werden vor dem Zustellen zur Anwendung mithilfe des durch das `customCertificateValidatorType`-Attribut dieses Elements angegebenen Validierungssteuerelements mit den Nachrichtenanmeldeinformationen verglichen.</span><span class="sxs-lookup"><span data-stu-id="39861-170">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="39861-171">Das Validierungssteuerelement kann die Anmeldeinformationen akzeptieren oder ablehnen.</span><span class="sxs-lookup"><span data-stu-id="39861-171">The validator can either accept or reject the credential.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39861-172">Beispiel</span><span class="sxs-lookup"><span data-stu-id="39861-172">Example</span></span>  
 <span data-ttu-id="39861-173">Mit dem folgenden Code wird der Validierungsmodus des Nachrichtenabsenders auf `PeerOrChainTrust` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="39861-173">The following code sets the message sender validation mode to `PeerOrChainTrust`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="39861-174">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="39861-174">See also</span></span>

- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="39861-175">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="39861-175">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="39861-176">Peer-to-Peer-Netzwerke</span><span class="sxs-lookup"><span data-stu-id="39861-176">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="39861-177">[Peer Kanalnachrichten-Authentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="39861-177">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="39861-178">[Benutzerdefinierte Peer Kanal Authentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="39861-178">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="39861-179">Sichern von Peerkanalanwendungen</span><span class="sxs-lookup"><span data-stu-id="39861-179">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
