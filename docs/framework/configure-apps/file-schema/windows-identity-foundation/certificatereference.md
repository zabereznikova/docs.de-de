---
title: '&lt;CertificateReference&gt;'
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: e04dc90134aadfb8af7b0800c7144963d267f513
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2018
ms.locfileid: "47206890"
---
# <a name="ltcertificatereferencegt"></a><span data-ttu-id="2301d-102">&lt;CertificateReference&gt;</span><span class="sxs-lookup"><span data-stu-id="2301d-102">&lt;certificateReference&gt;</span></span>
<span data-ttu-id="2301d-103">Gibt die Einstellungen, die zum Suchen und überprüfen ein x. 509-Zertifikat im Zertifikatspeicher verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2301d-103">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
 <span data-ttu-id="2301d-104">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="2301d-104">\<system.identityModel.services></span></span>  
<span data-ttu-id="2301d-105">\<FederationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="2301d-105">\<federationConfiguration></span></span>  
<span data-ttu-id="2301d-106">\<ServiceCertificate ></span><span class="sxs-lookup"><span data-stu-id="2301d-106">\<serviceCertificate></span></span>  
<span data-ttu-id="2301d-107">\<CertificateReference ></span><span class="sxs-lookup"><span data-stu-id="2301d-107">\<certificateReference></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2301d-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="2301d-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2301d-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2301d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2301d-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2301d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2301d-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="2301d-111">Attributes</span></span>  
  
|<span data-ttu-id="2301d-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="2301d-112">Attribute</span></span>|<span data-ttu-id="2301d-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2301d-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2301d-114">storeName</span><span class="sxs-lookup"><span data-stu-id="2301d-114">storeName</span></span>|<span data-ttu-id="2301d-115">Der Name des x. 509-Zertifikatspeichers.</span><span class="sxs-lookup"><span data-stu-id="2301d-115">The name of the X.509 certificate store.</span></span> <span data-ttu-id="2301d-116">Der Standardwert ist "My".</span><span class="sxs-lookup"><span data-stu-id="2301d-116">The default is "My".</span></span> <span data-ttu-id="2301d-117">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="2301d-117">Optional.</span></span>|  
|<span data-ttu-id="2301d-118">storeLocation</span><span class="sxs-lookup"><span data-stu-id="2301d-118">storeLocation</span></span>|<span data-ttu-id="2301d-119">Ein <xref:System.Security.Cryptography.X509Certificates.StoreLocation> -Wert, der den Speicherort des x. 509-Zertifikatspeichers angibt.</span><span class="sxs-lookup"><span data-stu-id="2301d-119">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="2301d-120">Der Standardwert ist "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="2301d-120">The default value is "LocalMachine".</span></span> <span data-ttu-id="2301d-121">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="2301d-121">Optional.</span></span>|  
|<span data-ttu-id="2301d-122">x509FindType</span><span class="sxs-lookup"><span data-stu-id="2301d-122">x509FindType</span></span>|<span data-ttu-id="2301d-123">Ein <xref:System.Security.Cryptography.X509Certificates.X509FindType> Wert, der den Typ der Suche angibt, die ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="2301d-123">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="2301d-124">Der Standardwert ist "FindBySubjectDistinguishedName".</span><span class="sxs-lookup"><span data-stu-id="2301d-124">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="2301d-125">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="2301d-125">Optional.</span></span>|  
|<span data-ttu-id="2301d-126">findValue</span><span class="sxs-lookup"><span data-stu-id="2301d-126">findValue</span></span>|<span data-ttu-id="2301d-127">Der Wert, nach dem im X.509-Zertifikatspeicher gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="2301d-127">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="2301d-128">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="2301d-128">Optional.</span></span>|  
|<span data-ttu-id="2301d-129">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="2301d-129">isChainIncluded</span></span>|<span data-ttu-id="2301d-130">Gibt an, ob die Validierung mithilfe der Zertifikatskette ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="2301d-130">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="2301d-131">Der Standardwert ist "true"; Mithilfe der Zertifikatskette erfolgt die Validierung.</span><span class="sxs-lookup"><span data-stu-id="2301d-131">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="2301d-132">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="2301d-132">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2301d-133">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2301d-133">Child Elements</span></span>  
 <span data-ttu-id="2301d-134">Keiner</span><span class="sxs-lookup"><span data-stu-id="2301d-134">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2301d-135">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2301d-135">Parent Elements</span></span>  
  
|<span data-ttu-id="2301d-136">Element</span><span class="sxs-lookup"><span data-stu-id="2301d-136">Element</span></span>|<span data-ttu-id="2301d-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2301d-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2301d-138">\<ServiceCertificate ></span><span class="sxs-lookup"><span data-stu-id="2301d-138">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|<span data-ttu-id="2301d-139">Konfiguriert das Zertifikat, das zum Verschlüsseln und Entschlüsseln von Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2301d-139">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2301d-140">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2301d-140">Remarks</span></span>  
 <span data-ttu-id="2301d-141">Die `<certificateReference>` Element gibt die Einstellungen, die zum Suchen und überprüfen ein x. 509-Zertifikat im Zertifikatspeicher verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2301d-141">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="2301d-142">Wenn er angegeben wird als untergeordnetes Element von der `<serviceCertficate>` -Element, es gibt die Speicherort und die Überprüfung der Einstellungen des x. 509-Zertifikats, das zum Verschlüsseln und Entschlüsseln von Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2301d-142">When it is specified as the child element of the `<serviceCertficate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="2301d-143">Die `<certificateReference>` Element wird dargestellt, durch die <xref:System.ServiceModel.Configuration.CertificateReferenceElement> Klasse.</span><span class="sxs-lookup"><span data-stu-id="2301d-143">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>
