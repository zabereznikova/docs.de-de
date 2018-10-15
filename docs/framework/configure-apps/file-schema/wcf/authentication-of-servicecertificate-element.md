---
title: '&lt;authentication&gt; des &lt;serviceCertificate&gt;-Elements'
ms.date: 03/30/2017
ms.assetid: 733b67b4-08a1-4d25-9741-10046f9357ef
ms.openlocfilehash: 811d54b49d8cd4fddbf196dbb524c5d303805c4f
ms.sourcegitcommit: d88024e6d6d8b242feae5f4007a709379355aa24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2018
ms.locfileid: "49316453"
---
# <a name="ltauthenticationgt-of-ltservicecertificategt-element"></a><span data-ttu-id="a0ab2-102">&lt;authentication&gt; des &lt;serviceCertificate&gt;-Elements</span><span class="sxs-lookup"><span data-stu-id="a0ab2-102">&lt;authentication&gt; of &lt;serviceCertificate&gt; Element</span></span>
<span data-ttu-id="a0ab2-103">Gibt die vom Clientproxy zum Authentifizieren von Dienstzertifikaten verwendeten Einstellungen an, die mittels SSL/TLS-Verhandlung abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a0ab2-103">Specifies the settings used by the client proxy to authenticate service certificates that are obtained using SSL/TLS negotiation.</span></span>  
  
 <span data-ttu-id="a0ab2-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a0ab2-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a0ab2-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="a0ab2-105">\<behaviors></span></span>  
<span data-ttu-id="a0ab2-106">EndpointBehaviors-Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a0ab2-106">endpointBehaviors section</span></span>  
<span data-ttu-id="a0ab2-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="a0ab2-107">\<behavior></span></span>  
<span data-ttu-id="a0ab2-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="a0ab2-108">\<clientCredentials></span></span>  
<span data-ttu-id="a0ab2-109">\<ServiceCertificate ></span><span class="sxs-lookup"><span data-stu-id="a0ab2-109">\<serviceCertificate></span></span>  
<span data-ttu-id="a0ab2-110">\<Authentifizierung ></span><span class="sxs-lookup"><span data-stu-id="a0ab2-110">\<authentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0ab2-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="a0ab2-111">Syntax</span></span>  
  
```xml  
<authentication customCertificateValidatorType="String" certificateValidationMode="None/PeerTrust/ChainTrust/PeerOrChainTrust/Custom"  
revocationMode="NoCheck/Online/Offline"   
trustedStoreLocation="LocalMachine/CurrentUser" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a0ab2-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a0ab2-112">Attributes and Elements</span></span>  
 <span data-ttu-id="a0ab2-113">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a0ab2-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a0ab2-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="a0ab2-114">Attributes</span></span>  
  
|<span data-ttu-id="a0ab2-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="a0ab2-115">Attribute</span></span>|<span data-ttu-id="a0ab2-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a0ab2-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a0ab2-117">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="a0ab2-117">customCertificateValidatorType</span></span>|<span data-ttu-id="a0ab2-118">Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a0ab2-118">String.</span></span> <span data-ttu-id="a0ab2-119">Ein Typ und eine Assembly, die zum Überprüfen eines benutzerdefinierten Typs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a0ab2-119">A type and assembly used to validate a custom type.</span></span>|  
|<span data-ttu-id="a0ab2-120">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="a0ab2-120">certificateValidationMode</span></span>|<span data-ttu-id="a0ab2-121">Gibt einen der drei für die Überprüfung von Anmeldeinformationen verwendeten Modi an.</span><span class="sxs-lookup"><span data-stu-id="a0ab2-121">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="a0ab2-122">Ist dies auf `Custom` festgelegt, muss außerdem ein customCertificateValidator zur Verfügung gestellt werden.</span><span class="sxs-lookup"><span data-stu-id="a0ab2-122">If set to `Custom`, then a customCertificateValidator must also be supplied.</span></span> <span data-ttu-id="a0ab2-123">Die Standardeinstellung ist `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="a0ab2-123">The default is `ChainTrust`.</span></span>|  
|<span data-ttu-id="a0ab2-124">revocationMode</span><span class="sxs-lookup"><span data-stu-id="a0ab2-124">revocationMode</span></span>|<span data-ttu-id="a0ab2-125">Einer der Modi zum Prüfen auf eine Liste gesperrter Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="a0ab2-125">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="a0ab2-126">Die Standardeinstellung ist `Online`.</span><span class="sxs-lookup"><span data-stu-id="a0ab2-126">The default is `Online`.</span></span>|  
|<span data-ttu-id="a0ab2-127">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="a0ab2-127">trustedStoreLocation</span></span>|<span data-ttu-id="a0ab2-128">Einer der beiden Systemspeicherorte: `LocalMachine` oder `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="a0ab2-128">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="a0ab2-129">Dieser Wert wird verwendet, wenn ein Dienstzertifikat mit dem Client ausgehandelt wird.</span><span class="sxs-lookup"><span data-stu-id="a0ab2-129">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="a0ab2-130">Validierung wird ausgeführt, für die **vertrauenswürdige Personen** am angegebenen Speicherort zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a0ab2-130">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="a0ab2-131">Die Standardeinstellung ist `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="a0ab2-131">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidator-attribute"></a><span data-ttu-id="a0ab2-132">customCertificateValidator-Attribut</span><span class="sxs-lookup"><span data-stu-id="a0ab2-132">customCertificateValidator Attribute</span></span>  
  
|<span data-ttu-id="a0ab2-133">Wert</span><span class="sxs-lookup"><span data-stu-id="a0ab2-133">Value</span></span>|<span data-ttu-id="a0ab2-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a0ab2-134">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a0ab2-135">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a0ab2-135">String</span></span>|<span data-ttu-id="a0ab2-136">Gibt den vollständigen Typnamen und die Assembly sowie weitere Daten zum Suchen des Typs an.</span><span class="sxs-lookup"><span data-stu-id="a0ab2-136">Specifies the type name and assembly and other data used to find the type.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="a0ab2-137">certificateValidationMode-Attribut</span><span class="sxs-lookup"><span data-stu-id="a0ab2-137">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="a0ab2-138">Wert</span><span class="sxs-lookup"><span data-stu-id="a0ab2-138">Value</span></span>|<span data-ttu-id="a0ab2-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a0ab2-139">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a0ab2-140">Enumeration</span><span class="sxs-lookup"><span data-stu-id="a0ab2-140">Enumeration</span></span>|<span data-ttu-id="a0ab2-141">Einer der folgenden Werte: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span><span class="sxs-lookup"><span data-stu-id="a0ab2-141">One of the following values: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span></span><br /><br /> <span data-ttu-id="a0ab2-142">Weitere Informationen finden Sie unter [arbeiten mit Zertifikaten](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="a0ab2-142">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="a0ab2-143">revocationMode-Attribut</span><span class="sxs-lookup"><span data-stu-id="a0ab2-143">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="a0ab2-144">Wert</span><span class="sxs-lookup"><span data-stu-id="a0ab2-144">Value</span></span>|<span data-ttu-id="a0ab2-145">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a0ab2-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a0ab2-146">Enumeration</span><span class="sxs-lookup"><span data-stu-id="a0ab2-146">Enumeration</span></span>|<span data-ttu-id="a0ab2-147">Einer der folgenden Werte: NoCheck, Online, Offline.</span><span class="sxs-lookup"><span data-stu-id="a0ab2-147">One of the following values: NoCheck, Online, Offline.</span></span><br /><br /> <span data-ttu-id="a0ab2-148">Weitere Informationen finden Sie unter [arbeiten mit Zertifikaten](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="a0ab2-148">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="a0ab2-149">trustedStoreLocation-Attribut</span><span class="sxs-lookup"><span data-stu-id="a0ab2-149">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="a0ab2-150">Wert</span><span class="sxs-lookup"><span data-stu-id="a0ab2-150">Value</span></span>|<span data-ttu-id="a0ab2-151">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a0ab2-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a0ab2-152">Enumeration</span><span class="sxs-lookup"><span data-stu-id="a0ab2-152">Enumeration</span></span>|<span data-ttu-id="a0ab2-153">Einer der folgenden Werte: LocalMachine oder CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="a0ab2-153">One of the following values: LocalMachine or CurrentUser.</span></span> <span data-ttu-id="a0ab2-154">Der Standardwert ist CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="a0ab2-154">The default is CurrentUser.</span></span> <span data-ttu-id="a0ab2-155">Wenn die Clientanwendung über ein Systemkonto ausgeführt wird, befindet sich das Zertifikat in der Regel in LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="a0ab2-155">If the client application is running under a system account, then the certificate is typically under LocalMachine.</span></span> <span data-ttu-id="a0ab2-156">Wenn die Clientanwendung über ein Benutzerkonto ausgeführt wird, befindet sich das Zertifikat in der Regel in CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="a0ab2-156">If the client application is running under a user account, then the certificate is typically in CurrentUser.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a0ab2-157">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a0ab2-157">Child Elements</span></span>  
 <span data-ttu-id="a0ab2-158">Keine</span><span class="sxs-lookup"><span data-stu-id="a0ab2-158">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a0ab2-159">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a0ab2-159">Parent Elements</span></span>  
  
|<span data-ttu-id="a0ab2-160">Element</span><span class="sxs-lookup"><span data-stu-id="a0ab2-160">Element</span></span>|<span data-ttu-id="a0ab2-161">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a0ab2-161">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a0ab2-162">\<ServiceCertificate ></span><span class="sxs-lookup"><span data-stu-id="a0ab2-162">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="a0ab2-163">Gibt ein Zertifikat an, das Sie zum Authentifizieren eines Diensts für den Client verwenden können.</span><span class="sxs-lookup"><span data-stu-id="a0ab2-163">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0ab2-164">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a0ab2-164">Remarks</span></span>  
 <span data-ttu-id="a0ab2-165">Mit dem `certificateValidationMode`-Attribut dieses Konfigurationselements wird die Ebene der Vertrauenswürdigkeit angegeben, mit der Zertifikate authentifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="a0ab2-165">The `certificateValidationMode` attribute of this configuration element specifies the level of trust used to authenticate certificates.</span></span> <span data-ttu-id="a0ab2-166">Standardmäßig wird die Ebene `ChainTrust` verwendet, die angibt, dass jedes Zertifikat in einer Zertifizierungshierarchie zu finden sein muss, die in eine vertrauenswürdige Zertifizierungsstelle am Anfang der Kette mündet.</span><span class="sxs-lookup"><span data-stu-id="a0ab2-166">By default, the level is set to `ChainTrust`, which specifies that each certificate must be found in a hierarchy of certificates ending in a trusted certification authority at the top of the chain.</span></span> <span data-ttu-id="a0ab2-167">Dies ist der sicherste Modus.</span><span class="sxs-lookup"><span data-stu-id="a0ab2-167">This is the most secure mode.</span></span> <span data-ttu-id="a0ab2-168">Sie können auch den Wert `PeerOrChainTrust` verwenden, der vorgibt, dass neben den Zertifikaten in einer Vertrauenskette auch selbst ausgestellte Zertifikate (Peervertrauen) akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="a0ab2-168">You can also set the value to `PeerOrChainTrust`, which specifies that self-issued certificates (peer trust) are accepted as well as certificates that are in a trusted chain.</span></span> <span data-ttu-id="a0ab2-169">Sie können diesen Wert beim Entwickeln und Debuggen von Clients und Diensten verwenden, da selbst ausgestellte Zertifikate nicht von einer vertrauenswürdigen Zertifizierungsstelle bezogen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="a0ab2-169">This value is used when developing and debugging clients and services because self-issued certificates need not be purchased from a trusted authority.</span></span> <span data-ttu-id="a0ab2-170">Verwenden Sie beim Bereitstellen eines Clients jedoch den Wert `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="a0ab2-170">When deploying a client, use the `ChainTrust` value instead.</span></span> <span data-ttu-id="a0ab2-171">Sie können den Wert auch auf `Custom` oder `None` festlegen.</span><span class="sxs-lookup"><span data-stu-id="a0ab2-171">You can also set the value to `Custom` or `None`.</span></span> <span data-ttu-id="a0ab2-172">Wenn Sie den `Custom`-Wert verwenden möchten, müssen Sie auch das `customCertificateValidator`-Attribut auf eine Assembly und einen Typ festlegen, die zur Validierung des Zertifikats verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a0ab2-172">To use the `Custom` value, you must also set the `customCertificateValidator` attribute to an assembly and type used to validate the certificate.</span></span> <span data-ttu-id="a0ab2-173">Wenn Sie eine eigene benutzerdefinierte Validierung erstellen möchten, müssen Sie von der abstrakten X509CertificateValidator-Klasse erben.</span><span class="sxs-lookup"><span data-stu-id="a0ab2-173">To create your own custom validator, you must inherit from the abstract X509CertificateValidator class.</span></span> <span data-ttu-id="a0ab2-174">Weitere Informationen finden Sie unter [Vorgehensweise: erstellen ein Diensts, der ein benutzerdefiniertes Zertifikats-Validierungssteuerelement verwendet](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span><span class="sxs-lookup"><span data-stu-id="a0ab2-174">For more information, see [How to: Create a Service that Employs a Custom Certificate Validator](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span></span>  
  
 <span data-ttu-id="a0ab2-175">Das `revocationMode`-Attribut gibt an, wie Zertifikate auf eine Sperre hin überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="a0ab2-175">The `revocationMode` attribute specifies how certificates are checked for revocation.</span></span> <span data-ttu-id="a0ab2-176">Der Standardwert ist `online`, wodurch angegeben wird, dass Zertifikate automatisch auf eine Sperre hin überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="a0ab2-176">The default is `online` which indicates that certificates will be checked automatically for revocation.</span></span> <span data-ttu-id="a0ab2-177">Weitere Informationen finden Sie unter [arbeiten mit Zertifikaten](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="a0ab2-177">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0ab2-178">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a0ab2-178">Example</span></span>  
 <span data-ttu-id="a0ab2-179">In folgendem Beispiel werden zwei Aufgaben ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a0ab2-179">The following example does two tasks.</span></span> <span data-ttu-id="a0ab2-180">Es gibt zunächst ein Dienstzertifikat für den Client zu verwenden, wenn die Kommunikation mit Endpunkten, deren Domänenname `www.contoso.com` über das HTTP-Protokoll.</span><span class="sxs-lookup"><span data-stu-id="a0ab2-180">It first specifies a service certificate for the client to use when communicating with endpoints whose domain name is `www.contoso.com` over the HTTP protocol.</span></span> <span data-ttu-id="a0ab2-181">Danach gibt es den Sperrmodus und den Speicherort für die Authentifizierung an.</span><span class="sxs-lookup"><span data-stu-id="a0ab2-181">Second, it specifies the revocation mode and store location used during authentication.</span></span>  
  
```xml  
<serviceCertificate>  
  <defaultCertificate findValue="www.contoso.com"   
                      storeLocation="LocalMachine"  
                      storeName="TrustedPeople"   
                      x509FindType="FindByIssuerDistinguishedName" />  
  <scopedCertificates>  
     <add targetUri="http://www.contoso.com"   
          findValue="www.contoso.com" storeLocation="LocalMachine"  
                  storeName="Root" x509FindType="FindByIssuerName" />  
  </scopedCertificates>  
  <authentication revocationMode="Online"   
   trustedStoreLocation="LocalMachine" />  
</serviceCertificate>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a0ab2-182">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0ab2-182">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.Authentication%2A>  
 <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>  
 [<span data-ttu-id="a0ab2-183">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="a0ab2-183">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="a0ab2-184">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="a0ab2-184">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="a0ab2-185">Vorgehensweise: Erstellen eines Diensts, der ein benutzerdefiniertes Zertifikatvalidierungssteuerelement verwendet</span><span class="sxs-lookup"><span data-stu-id="a0ab2-185">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 [<span data-ttu-id="a0ab2-186">\<authentication></span><span class="sxs-lookup"><span data-stu-id="a0ab2-186">\<authentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)  
 [<span data-ttu-id="a0ab2-187">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="a0ab2-187">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="a0ab2-188">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="a0ab2-188">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
