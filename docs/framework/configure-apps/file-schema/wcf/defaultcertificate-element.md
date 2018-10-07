---
title: '&lt;defaultCertificate&gt;-Element'
ms.date: 03/30/2017
ms.assetid: f1ddf364-9a00-45d3-b989-ff381c154ce6
ms.openlocfilehash: 9b99ee36fdb924ea12f3023984a3aa4b590937e8
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2018
ms.locfileid: "48847853"
---
# <a name="ltdefaultcertificategt-element"></a><span data-ttu-id="32203-102">&lt;defaultCertificate&gt;-Element</span><span class="sxs-lookup"><span data-stu-id="32203-102">&lt;defaultCertificate&gt; Element</span></span>
<span data-ttu-id="32203-103">Gibt ein X.509-Zertifikat an, das verwendet wird, wenn ein Dienst oder STS kein Zertifikat über ein Aushandlungsprotokoll bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="32203-103">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>  
  
 <span data-ttu-id="32203-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="32203-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="32203-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="32203-105">\<behaviors></span></span>  
<span data-ttu-id="32203-106">EndpointBehaviors-Abschnitt</span><span class="sxs-lookup"><span data-stu-id="32203-106">endpointBehaviors section</span></span>  
<span data-ttu-id="32203-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="32203-107">\<behavior></span></span>  
<span data-ttu-id="32203-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="32203-108">\<clientCredentials></span></span>  
<span data-ttu-id="32203-109">\<ServiceCertificate ></span><span class="sxs-lookup"><span data-stu-id="32203-109">\<serviceCertificate></span></span>  
<span data-ttu-id="32203-110">\<DefaultCertificate ></span><span class="sxs-lookup"><span data-stu-id="32203-110">\<defaultCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32203-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="32203-111">Syntax</span></span>  
  
```xml  
<defaultCertificate findValue="String"   
storeLocation=" CurrentUser/LocalMachine"  
storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"   
x509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialiNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="32203-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="32203-112">Attributes and Elements</span></span>  
 <span data-ttu-id="32203-113">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="32203-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="32203-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="32203-114">Attributes</span></span>  
  
|<span data-ttu-id="32203-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="32203-115">Attribute</span></span>|<span data-ttu-id="32203-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32203-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="32203-117">findValue</span><span class="sxs-lookup"><span data-stu-id="32203-117">findValue</span></span>|<span data-ttu-id="32203-118">Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="32203-118">String.</span></span> <span data-ttu-id="32203-119">Der zu suchende Wert.</span><span class="sxs-lookup"><span data-stu-id="32203-119">The value to search for.</span></span>|  
|<span data-ttu-id="32203-120">x509FindType</span><span class="sxs-lookup"><span data-stu-id="32203-120">x509FindType</span></span>|<span data-ttu-id="32203-121">Enumeration.</span><span class="sxs-lookup"><span data-stu-id="32203-121">Enumeration.</span></span> <span data-ttu-id="32203-122">Eines der zu durchsuchenden Zertifikatfelder.</span><span class="sxs-lookup"><span data-stu-id="32203-122">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="32203-123">storeLocation</span><span class="sxs-lookup"><span data-stu-id="32203-123">storeLocation</span></span>|<span data-ttu-id="32203-124">Enumeration.</span><span class="sxs-lookup"><span data-stu-id="32203-124">Enumeration.</span></span> <span data-ttu-id="32203-125">Einer der zwei zu durchsuchenden Systemspeicherorte.</span><span class="sxs-lookup"><span data-stu-id="32203-125">One of the two system store locations to search.</span></span>|  
|<span data-ttu-id="32203-126">storeName</span><span class="sxs-lookup"><span data-stu-id="32203-126">storeName</span></span>|<span data-ttu-id="32203-127">Enumeration.</span><span class="sxs-lookup"><span data-stu-id="32203-127">Enumeration.</span></span> <span data-ttu-id="32203-128">Einer der zu durchsuchenden Systemspeicher.</span><span class="sxs-lookup"><span data-stu-id="32203-128">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="32203-129">findValue-Attribut</span><span class="sxs-lookup"><span data-stu-id="32203-129">findValue Attribute</span></span>  
  
|<span data-ttu-id="32203-130">Wert</span><span class="sxs-lookup"><span data-stu-id="32203-130">Value</span></span>|<span data-ttu-id="32203-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32203-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="32203-132">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="32203-132">String</span></span>|<span data-ttu-id="32203-133">Der Wert ist vom zu durchsuchenden Feld (das durch das X509FindType-Attribut angegeben wird) abhängig.</span><span class="sxs-lookup"><span data-stu-id="32203-133">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="32203-134">Wenn Sie beispielsweise nach einem Fingerabdruck suchen, muss der Wert eine Zeichenfolge aus hexadezimalen Zahlen sein.</span><span class="sxs-lookup"><span data-stu-id="32203-134">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="32203-135">x509FindType-Attribut</span><span class="sxs-lookup"><span data-stu-id="32203-135">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="32203-136">Wert</span><span class="sxs-lookup"><span data-stu-id="32203-136">Value</span></span>|<span data-ttu-id="32203-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32203-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="32203-138">Enumeration</span><span class="sxs-lookup"><span data-stu-id="32203-138">Enumeration</span></span>|<span data-ttu-id="32203-139">Zu den gültigen Werten gehören: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="32203-139">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="32203-140">storeLocation-Attribut</span><span class="sxs-lookup"><span data-stu-id="32203-140">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="32203-141">Wert</span><span class="sxs-lookup"><span data-stu-id="32203-141">Value</span></span>|<span data-ttu-id="32203-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32203-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="32203-143">Enumeration</span><span class="sxs-lookup"><span data-stu-id="32203-143">Enumeration</span></span>|<span data-ttu-id="32203-144">CurrentUser oder LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="32203-144">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="32203-145">storeName-Attribut</span><span class="sxs-lookup"><span data-stu-id="32203-145">storeName Attribute</span></span>  
  
|<span data-ttu-id="32203-146">Wert</span><span class="sxs-lookup"><span data-stu-id="32203-146">Value</span></span>|<span data-ttu-id="32203-147">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32203-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="32203-148">Enumeration</span><span class="sxs-lookup"><span data-stu-id="32203-148">Enumeration</span></span>|<span data-ttu-id="32203-149">Zu den gültigen Werten gehören: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople und TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="32203-149">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="32203-150">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="32203-150">Child Elements</span></span>  
 <span data-ttu-id="32203-151">Keine</span><span class="sxs-lookup"><span data-stu-id="32203-151">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="32203-152">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="32203-152">Parent Elements</span></span>  
  
|<span data-ttu-id="32203-153">Element</span><span class="sxs-lookup"><span data-stu-id="32203-153">Element</span></span>|<span data-ttu-id="32203-154">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32203-154">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="32203-155">\<ServiceCertificate ></span><span class="sxs-lookup"><span data-stu-id="32203-155">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="32203-156">Gibt ein Zertifikat an, das Sie zum Authentifizieren eines Diensts für den Client verwenden können.</span><span class="sxs-lookup"><span data-stu-id="32203-156">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32203-157">Hinweise</span><span class="sxs-lookup"><span data-stu-id="32203-157">Remarks</span></span>  
 <span data-ttu-id="32203-158">Bei Bindungen mit Zertifikat-basierter Nachrichtensicherheit wird das durch dieses Konfigurationselement angegebene Zertifikat zum Verschlüsseln von Nachrichten für den Dienst sowie für die Signierung von Antworten an den Client verwendet.</span><span class="sxs-lookup"><span data-stu-id="32203-158">For bindings that use certificate-based message security, certificate specified by this configuration element is used to encrypt messages to the service and is expected to be used by the service for signing replies to the client.</span></span> <span data-ttu-id="32203-159">Es speichert ein einzelnes Zertifikat, das verwendent werden soll, wenn kein Zertifikat von einem Dienst angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="32203-159">It stores a single certificate to be used when no certificate is specified by a service.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32203-160">Beispiel</span><span class="sxs-lookup"><span data-stu-id="32203-160">Example</span></span>  
 <span data-ttu-id="32203-161">Im folgenden Beispiel wird ein Zertifikat für Endpunkte verwenden, deren URI beginnt mit `http://www.contoso.com` und ein Zertifikat für alle anderen Endpunkte, die keine zertifikatsaushandlung durchführen.</span><span class="sxs-lookup"><span data-stu-id="32203-161">The following example specifies a certificate to use for endpoints whose URI begins with `http://www.contoso.com` and a certificate to use for all other endpoints that do not perform certificate negotiation.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="32203-162">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="32203-162">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.X509DefaultServiceCertificateElement>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.DefaultCertificate%2A>  
 [<span data-ttu-id="32203-163">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="32203-163">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="32203-164">\<authentication></span><span class="sxs-lookup"><span data-stu-id="32203-164">\<authentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)  
 [<span data-ttu-id="32203-165">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="32203-165">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="32203-166">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="32203-166">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
