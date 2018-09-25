---
title: '&lt;CertificateReference&gt;'
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: e04dc90134aadfb8af7b0800c7144963d267f513
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47075082"
---
# <a name="ltcertificatereferencegt"></a><span data-ttu-id="fabca-102">&lt;CertificateReference&gt;</span><span class="sxs-lookup"><span data-stu-id="fabca-102">&lt;certificateReference&gt;</span></span>
<span data-ttu-id="fabca-103">Gibt die Einstellungen, die zum Suchen und überprüfen ein x. 509-Zertifikat im Zertifikatspeicher verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fabca-103">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
 <span data-ttu-id="fabca-104">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="fabca-104">\<system.identityModel.services></span></span>  
<span data-ttu-id="fabca-105">\<FederationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="fabca-105">\<federationConfiguration></span></span>  
<span data-ttu-id="fabca-106">\<ServiceCertificate ></span><span class="sxs-lookup"><span data-stu-id="fabca-106">\<serviceCertificate></span></span>  
<span data-ttu-id="fabca-107">\<CertificateReference ></span><span class="sxs-lookup"><span data-stu-id="fabca-107">\<certificateReference></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fabca-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="fabca-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fabca-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fabca-109">Attributes and Elements</span></span>  
 <span data-ttu-id="fabca-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fabca-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fabca-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="fabca-111">Attributes</span></span>  
  
|<span data-ttu-id="fabca-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="fabca-112">Attribute</span></span>|<span data-ttu-id="fabca-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fabca-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fabca-114">storeName</span><span class="sxs-lookup"><span data-stu-id="fabca-114">storeName</span></span>|<span data-ttu-id="fabca-115">Der Name des x. 509-Zertifikatspeichers.</span><span class="sxs-lookup"><span data-stu-id="fabca-115">The name of the X.509 certificate store.</span></span> <span data-ttu-id="fabca-116">Der Standardwert ist "My".</span><span class="sxs-lookup"><span data-stu-id="fabca-116">The default is "My".</span></span> <span data-ttu-id="fabca-117">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="fabca-117">Optional.</span></span>|  
|<span data-ttu-id="fabca-118">storeLocation</span><span class="sxs-lookup"><span data-stu-id="fabca-118">storeLocation</span></span>|<span data-ttu-id="fabca-119">Ein <xref:System.Security.Cryptography.X509Certificates.StoreLocation> -Wert, der den Speicherort des x. 509-Zertifikatspeichers angibt.</span><span class="sxs-lookup"><span data-stu-id="fabca-119">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="fabca-120">Der Standardwert ist "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="fabca-120">The default value is "LocalMachine".</span></span> <span data-ttu-id="fabca-121">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="fabca-121">Optional.</span></span>|  
|<span data-ttu-id="fabca-122">x509FindType</span><span class="sxs-lookup"><span data-stu-id="fabca-122">x509FindType</span></span>|<span data-ttu-id="fabca-123">Ein <xref:System.Security.Cryptography.X509Certificates.X509FindType> Wert, der den Typ der Suche angibt, die ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="fabca-123">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="fabca-124">Der Standardwert ist "FindBySubjectDistinguishedName".</span><span class="sxs-lookup"><span data-stu-id="fabca-124">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="fabca-125">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="fabca-125">Optional.</span></span>|  
|<span data-ttu-id="fabca-126">findValue</span><span class="sxs-lookup"><span data-stu-id="fabca-126">findValue</span></span>|<span data-ttu-id="fabca-127">Der Wert, nach dem im X.509-Zertifikatspeicher gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="fabca-127">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="fabca-128">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="fabca-128">Optional.</span></span>|  
|<span data-ttu-id="fabca-129">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="fabca-129">isChainIncluded</span></span>|<span data-ttu-id="fabca-130">Gibt an, ob die Validierung mithilfe der Zertifikatskette ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="fabca-130">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="fabca-131">Der Standardwert ist "true"; Mithilfe der Zertifikatskette erfolgt die Validierung.</span><span class="sxs-lookup"><span data-stu-id="fabca-131">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="fabca-132">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="fabca-132">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fabca-133">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fabca-133">Child Elements</span></span>  
 <span data-ttu-id="fabca-134">Keiner</span><span class="sxs-lookup"><span data-stu-id="fabca-134">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fabca-135">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fabca-135">Parent Elements</span></span>  
  
|<span data-ttu-id="fabca-136">Element</span><span class="sxs-lookup"><span data-stu-id="fabca-136">Element</span></span>|<span data-ttu-id="fabca-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fabca-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fabca-138">\<ServiceCertificate ></span><span class="sxs-lookup"><span data-stu-id="fabca-138">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|<span data-ttu-id="fabca-139">Konfiguriert das Zertifikat, das zum Verschlüsseln und Entschlüsseln von Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fabca-139">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fabca-140">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fabca-140">Remarks</span></span>  
 <span data-ttu-id="fabca-141">Die `<certificateReference>` Element gibt die Einstellungen, die zum Suchen und überprüfen ein x. 509-Zertifikat im Zertifikatspeicher verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fabca-141">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="fabca-142">Wenn er angegeben wird als untergeordnetes Element von der `<serviceCertficate>` -Element, es gibt die Speicherort und die Überprüfung der Einstellungen des x. 509-Zertifikats, das zum Verschlüsseln und Entschlüsseln von Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fabca-142">When it is specified as the child element of the `<serviceCertficate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="fabca-143">Die `<certificateReference>` Element wird dargestellt, durch die <xref:System.ServiceModel.Configuration.CertificateReferenceElement> Klasse.</span><span class="sxs-lookup"><span data-stu-id="fabca-143">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>
