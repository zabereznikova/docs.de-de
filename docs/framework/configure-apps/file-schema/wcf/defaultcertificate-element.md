---
title: <defaultCertificate>-Element
ms.date: 03/30/2017
ms.assetid: f1ddf364-9a00-45d3-b989-ff381c154ce6
ms.openlocfilehash: 93410e815a156f91db1962f05fb1aa6baca7f955
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919252"
---
# <a name="defaultcertificate-element"></a><span data-ttu-id="382b4-102">\<defaultCertificate-> Element</span><span class="sxs-lookup"><span data-stu-id="382b4-102">\<defaultCertificate> Element</span></span>
<span data-ttu-id="382b4-103">Gibt ein X.509-Zertifikat an, das verwendet wird, wenn ein Dienst oder STS kein Zertifikat über ein Aushandlungsprotokoll bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="382b4-103">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>  
  
 <span data-ttu-id="382b4-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="382b4-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="382b4-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="382b4-105">\<behaviors></span></span>  
<span data-ttu-id="382b4-106">endpointverhaltenbereich</span><span class="sxs-lookup"><span data-stu-id="382b4-106">endpointBehaviors section</span></span>  
<span data-ttu-id="382b4-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="382b4-107">\<behavior></span></span>  
<span data-ttu-id="382b4-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="382b4-108">\<clientCredentials></span></span>  
<span data-ttu-id="382b4-109">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="382b4-109">\<serviceCertificate></span></span>  
<span data-ttu-id="382b4-110">\<defaultCertificate></span><span class="sxs-lookup"><span data-stu-id="382b4-110">\<defaultCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="382b4-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="382b4-111">Syntax</span></span>  
  
```xml  
<defaultCertificate findValue="String"
                    storeLocation=" CurrentUser/LocalMachine"
                    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                    x509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialiNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="382b4-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="382b4-112">Attributes and Elements</span></span>  
 <span data-ttu-id="382b4-113">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="382b4-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="382b4-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="382b4-114">Attributes</span></span>  
  
|<span data-ttu-id="382b4-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="382b4-115">Attribute</span></span>|<span data-ttu-id="382b4-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="382b4-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="382b4-117">findValue</span><span class="sxs-lookup"><span data-stu-id="382b4-117">findValue</span></span>|<span data-ttu-id="382b4-118">Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="382b4-118">String.</span></span> <span data-ttu-id="382b4-119">Der zu suchende Wert.</span><span class="sxs-lookup"><span data-stu-id="382b4-119">The value to search for.</span></span>|  
|<span data-ttu-id="382b4-120">x509FindType</span><span class="sxs-lookup"><span data-stu-id="382b4-120">x509FindType</span></span>|<span data-ttu-id="382b4-121">Enumeration.</span><span class="sxs-lookup"><span data-stu-id="382b4-121">Enumeration.</span></span> <span data-ttu-id="382b4-122">Eines der zu durchsuchenden Zertifikatfelder.</span><span class="sxs-lookup"><span data-stu-id="382b4-122">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="382b4-123">storeLocation</span><span class="sxs-lookup"><span data-stu-id="382b4-123">storeLocation</span></span>|<span data-ttu-id="382b4-124">Enumeration.</span><span class="sxs-lookup"><span data-stu-id="382b4-124">Enumeration.</span></span> <span data-ttu-id="382b4-125">Einer der zwei zu durchsuchenden Systemspeicherorte.</span><span class="sxs-lookup"><span data-stu-id="382b4-125">One of the two system store locations to search.</span></span>|  
|<span data-ttu-id="382b4-126">storeName</span><span class="sxs-lookup"><span data-stu-id="382b4-126">storeName</span></span>|<span data-ttu-id="382b4-127">Enumeration.</span><span class="sxs-lookup"><span data-stu-id="382b4-127">Enumeration.</span></span> <span data-ttu-id="382b4-128">Einer der zu durchsuchenden Systemspeicher.</span><span class="sxs-lookup"><span data-stu-id="382b4-128">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="382b4-129">findValue-Attribut</span><span class="sxs-lookup"><span data-stu-id="382b4-129">findValue Attribute</span></span>  
  
|<span data-ttu-id="382b4-130">Wert</span><span class="sxs-lookup"><span data-stu-id="382b4-130">Value</span></span>|<span data-ttu-id="382b4-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="382b4-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="382b4-132">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="382b4-132">String</span></span>|<span data-ttu-id="382b4-133">Der Wert ist vom zu durchsuchenden Feld (das durch das X509FindType-Attribut angegeben wird) abhängig.</span><span class="sxs-lookup"><span data-stu-id="382b4-133">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="382b4-134">Wenn Sie beispielsweise nach einem Fingerabdruck suchen, muss der Wert eine Zeichenfolge aus hexadezimalen Zahlen sein.</span><span class="sxs-lookup"><span data-stu-id="382b4-134">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="382b4-135">x509FindType-Attribut</span><span class="sxs-lookup"><span data-stu-id="382b4-135">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="382b4-136">Wert</span><span class="sxs-lookup"><span data-stu-id="382b4-136">Value</span></span>|<span data-ttu-id="382b4-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="382b4-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="382b4-138">Enumeration</span><span class="sxs-lookup"><span data-stu-id="382b4-138">Enumeration</span></span>|<span data-ttu-id="382b4-139">Mögliche Werte: FindByThumbprint, findbysubjetname, findbysubjetissushedname, FindByIssuerName, findbyissuererkennbar shedname, findbyserialnumber, FindByTimeValid, FindByTimeNotYetValid, findbyserialnumber, findbytimeabgelauf, findbytemplatename , Findbyapplicationpolicy, findbycertificatepolicy, findbyextension, findbykeyusage, findbysubjetkeyidentifier.</span><span class="sxs-lookup"><span data-stu-id="382b4-139">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="382b4-140">storeLocation-Attribut</span><span class="sxs-lookup"><span data-stu-id="382b4-140">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="382b4-141">Wert</span><span class="sxs-lookup"><span data-stu-id="382b4-141">Value</span></span>|<span data-ttu-id="382b4-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="382b4-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="382b4-143">Enumeration</span><span class="sxs-lookup"><span data-stu-id="382b4-143">Enumeration</span></span>|<span data-ttu-id="382b4-144">CurrentUser oder LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="382b4-144">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="382b4-145">storeName-Attribut</span><span class="sxs-lookup"><span data-stu-id="382b4-145">storeName Attribute</span></span>  
  
|<span data-ttu-id="382b4-146">Wert</span><span class="sxs-lookup"><span data-stu-id="382b4-146">Value</span></span>|<span data-ttu-id="382b4-147">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="382b4-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="382b4-148">Enumeration</span><span class="sxs-lookup"><span data-stu-id="382b4-148">Enumeration</span></span>|<span data-ttu-id="382b4-149">Mögliche Werte: Addressbook, AuthRoot, CertificateAuthority, unallowed, my, root, treuhändpeople und Treuhänder Publisher.</span><span class="sxs-lookup"><span data-stu-id="382b4-149">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="382b4-150">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="382b4-150">Child Elements</span></span>  
 <span data-ttu-id="382b4-151">Keine</span><span class="sxs-lookup"><span data-stu-id="382b4-151">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="382b4-152">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="382b4-152">Parent Elements</span></span>  
  
|<span data-ttu-id="382b4-153">Element</span><span class="sxs-lookup"><span data-stu-id="382b4-153">Element</span></span>|<span data-ttu-id="382b4-154">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="382b4-154">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="382b4-155">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="382b4-155">\<serviceCertificate></span></span>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="382b4-156">Gibt ein Zertifikat an, das Sie zum Authentifizieren eines Diensts für den Client verwenden können.</span><span class="sxs-lookup"><span data-stu-id="382b4-156">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="382b4-157">Hinweise</span><span class="sxs-lookup"><span data-stu-id="382b4-157">Remarks</span></span>  
 <span data-ttu-id="382b4-158">Bei Bindungen mit Zertifikat-basierter Nachrichtensicherheit wird das durch dieses Konfigurationselement angegebene Zertifikat zum Verschlüsseln von Nachrichten für den Dienst sowie für die Signierung von Antworten an den Client verwendet.</span><span class="sxs-lookup"><span data-stu-id="382b4-158">For bindings that use certificate-based message security, certificate specified by this configuration element is used to encrypt messages to the service and is expected to be used by the service for signing replies to the client.</span></span> <span data-ttu-id="382b4-159">Es speichert ein einzelnes Zertifikat, das verwendent werden soll, wenn kein Zertifikat von einem Dienst angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="382b4-159">It stores a single certificate to be used when no certificate is specified by a service.</span></span>  
  
## <a name="example"></a><span data-ttu-id="382b4-160">Beispiel</span><span class="sxs-lookup"><span data-stu-id="382b4-160">Example</span></span>  
 <span data-ttu-id="382b4-161">Das folgende Beispiel gibt ein Zertifikat an, das für Endpunkte verwendet wird, `http://www.contoso.com` deren URI mit beginnt, und ein Zertifikat, das für alle anderen Endpunkte verwendet werden soll, die keine Zertifikats Aushandlung ausführen.</span><span class="sxs-lookup"><span data-stu-id="382b4-161">The following example specifies a certificate to use for endpoints whose URI begins with `http://www.contoso.com` and a certificate to use for all other endpoints that do not perform certificate negotiation.</span></span>  
  
```xml  
<serviceCertificate>
  <defaultCertificate findValue="www.contoso.com"
                      storeLocation="LocalMachine"
                      storeName="TrustedPeople"
                      x509FindType="FindByIssuerDistinguishedName" />
  <scopedCertificates>
    <add targetUri="http://www.contoso.com"
         findValue="www.contoso.com"
         storeLocation="LocalMachine"
         storeName="Root"
         x509FindType="FindByIssuerName" />
  </scopedCertificates>
  <authentication revocationMode="Online"
                  trustedStoreLocation="LocalMachine" />
</serviceCertificate>
```  
  
## <a name="see-also"></a><span data-ttu-id="382b4-162">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="382b4-162">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509DefaultServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.DefaultCertificate%2A>
- [<span data-ttu-id="382b4-163">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="382b4-163">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="382b4-164">\<authentication></span><span class="sxs-lookup"><span data-stu-id="382b4-164">\<authentication></span></span>](authentication-of-clientcertificate-element.md)
- [<span data-ttu-id="382b4-165">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="382b4-165">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="382b4-166">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="382b4-166">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
