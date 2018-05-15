---
title: '&lt;CertificateReference&gt;'
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: e0f9a826a4c8d292346d9efee7970a82b88fb612
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltcertificatereferencegt"></a><span data-ttu-id="a9ad5-102">&lt;CertificateReference&gt;</span><span class="sxs-lookup"><span data-stu-id="a9ad5-102">&lt;certificateReference&gt;</span></span>
<span data-ttu-id="a9ad5-103">Gibt die Einstellungen, die zum finden und überprüfen ein x. 509-Zertifikat in keinem Zertifikatspeicher verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a9ad5-103">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
 <span data-ttu-id="a9ad5-104">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="a9ad5-104">\<system.identityModel.services></span></span>  
<span data-ttu-id="a9ad5-105">\<FederationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="a9ad5-105">\<federationConfiguration></span></span>  
<span data-ttu-id="a9ad5-106">\<ServiceCertificate ></span><span class="sxs-lookup"><span data-stu-id="a9ad5-106">\<serviceCertificate></span></span>  
<span data-ttu-id="a9ad5-107">\<CertificateReference ></span><span class="sxs-lookup"><span data-stu-id="a9ad5-107">\<certificateReference></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9ad5-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="a9ad5-108">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
      <certificateReference   
        storeName="AddressBook||AuthRoot||CertificateAuthority||Disallowed||My||Root||TrustedPeople||TrustedPublisher"  
        storeLocation="CurrentUser||LocalMachine"  
        x509FindType="FindByThumbprint||FindBySubjectName||FindBySubjectDistinguishedName||FindByIssuerName||FindByIssuerDistinguishedName||FindBySerialNumber||FindByTimeValid||FindByTimeNotYetValid||FindByTimeExpired||FindByTemplateName||FindByApplicationPolicy||FindByCertificatePolicy||FindByExtension||FindByKeyUsage||FindBySubjectKeyIdentifier"  
        findValue=xs:String  
        isChainIncluded=xs:Boolean >  
      </certificateReference>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a9ad5-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a9ad5-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a9ad5-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a9ad5-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a9ad5-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="a9ad5-111">Attributes</span></span>  
  
|<span data-ttu-id="a9ad5-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="a9ad5-112">Attribute</span></span>|<span data-ttu-id="a9ad5-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a9ad5-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a9ad5-114">storeName</span><span class="sxs-lookup"><span data-stu-id="a9ad5-114">storeName</span></span>|<span data-ttu-id="a9ad5-115">Der Name des x. 509-Zertifikatspeichers.</span><span class="sxs-lookup"><span data-stu-id="a9ad5-115">The name of the X.509 certificate store.</span></span> <span data-ttu-id="a9ad5-116">Die Standardeinstellung ist "My".</span><span class="sxs-lookup"><span data-stu-id="a9ad5-116">The default is "My".</span></span> <span data-ttu-id="a9ad5-117">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="a9ad5-117">Optional.</span></span>|  
|<span data-ttu-id="a9ad5-118">storeLocation</span><span class="sxs-lookup"><span data-stu-id="a9ad5-118">storeLocation</span></span>|<span data-ttu-id="a9ad5-119">Ein <xref:System.Security.Cryptography.X509Certificates.StoreLocation> Wert, der den Speicherort des x. 509-Zertifikatspeichers angibt.</span><span class="sxs-lookup"><span data-stu-id="a9ad5-119">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="a9ad5-120">Der Standardwert ist "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="a9ad5-120">The default value is "LocalMachine".</span></span> <span data-ttu-id="a9ad5-121">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="a9ad5-121">Optional.</span></span>|  
|<span data-ttu-id="a9ad5-122">x509FindType</span><span class="sxs-lookup"><span data-stu-id="a9ad5-122">x509FindType</span></span>|<span data-ttu-id="a9ad5-123">Ein <xref:System.Security.Cryptography.X509Certificates.X509FindType> Wert, der den Typ der Suche angibt, die ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a9ad5-123">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="a9ad5-124">Der Standardwert ist "FindBySubjectDistinguishedName".</span><span class="sxs-lookup"><span data-stu-id="a9ad5-124">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="a9ad5-125">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="a9ad5-125">Optional.</span></span>|  
|<span data-ttu-id="a9ad5-126">findValue</span><span class="sxs-lookup"><span data-stu-id="a9ad5-126">findValue</span></span>|<span data-ttu-id="a9ad5-127">Der Wert, nach dem im X.509-Zertifikatspeicher gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="a9ad5-127">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="a9ad5-128">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="a9ad5-128">Optional.</span></span>|  
|<span data-ttu-id="a9ad5-129">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="a9ad5-129">isChainIncluded</span></span>|<span data-ttu-id="a9ad5-130">Gibt an, ob die Überprüfung der Zertifikatkette mit ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a9ad5-130">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="a9ad5-131">Der Standardwert ist "true" Überprüfung erfolgt über die Zertifikatkette.</span><span class="sxs-lookup"><span data-stu-id="a9ad5-131">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="a9ad5-132">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="a9ad5-132">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a9ad5-133">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a9ad5-133">Child Elements</span></span>  
 <span data-ttu-id="a9ad5-134">Keiner</span><span class="sxs-lookup"><span data-stu-id="a9ad5-134">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a9ad5-135">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a9ad5-135">Parent Elements</span></span>  
  
|<span data-ttu-id="a9ad5-136">Element</span><span class="sxs-lookup"><span data-stu-id="a9ad5-136">Element</span></span>|<span data-ttu-id="a9ad5-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a9ad5-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a9ad5-138">\<ServiceCertificate ></span><span class="sxs-lookup"><span data-stu-id="a9ad5-138">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|<span data-ttu-id="a9ad5-139">Konfiguriert das Zertifikat, das zum Verschlüsseln und Entschlüsseln von Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a9ad5-139">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9ad5-140">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a9ad5-140">Remarks</span></span>  
 <span data-ttu-id="a9ad5-141">Die `<certificateReference>` -Element gibt die Einstellungen, die zum finden und überprüfen ein x. 509-Zertifikat in keinem Zertifikatspeicher verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a9ad5-141">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="a9ad5-142">Wenn er angegeben wird als untergeordnetes Element von der `<serviceCertficate>` -Element, es gibt die Speicherort und die Überprüfung der Einstellungen des x. 509-Zertifikats, das zum Verschlüsseln und Entschlüsseln von Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a9ad5-142">When it is specified as the child element of the `<serviceCertficate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="a9ad5-143">Die `<certificateReference>` Element dargestellt ist, durch die <xref:System.ServiceModel.Configuration.CertificateReferenceElement> Klasse.</span><span class="sxs-lookup"><span data-stu-id="a9ad5-143">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>
