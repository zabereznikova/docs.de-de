---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: c7dc9cfff15e70eff0086cfd98a19f3360ab8bb0
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423029"
---
# <a name="certificatereference"></a><span data-ttu-id="ea5c3-101">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="ea5c3-101">\<certificateReference></span></span>
<span data-ttu-id="ea5c3-102">Gibt die Einstellungen, die zum Suchen und überprüfen ein x. 509-Zertifikat im Zertifikatspeicher verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ea5c3-102">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
 <span data-ttu-id="ea5c3-103">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="ea5c3-103">\<system.identityModel.services></span></span>  
<span data-ttu-id="ea5c3-104">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="ea5c3-104">\<federationConfiguration></span></span>  
<span data-ttu-id="ea5c3-105">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="ea5c3-105">\<serviceCertificate></span></span>  
<span data-ttu-id="ea5c3-106">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="ea5c3-106">\<certificateReference></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea5c3-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="ea5c3-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ea5c3-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ea5c3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ea5c3-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ea5c3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ea5c3-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="ea5c3-110">Attributes</span></span>  
  
|<span data-ttu-id="ea5c3-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="ea5c3-111">Attribute</span></span>|<span data-ttu-id="ea5c3-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ea5c3-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ea5c3-113">storeName</span><span class="sxs-lookup"><span data-stu-id="ea5c3-113">storeName</span></span>|<span data-ttu-id="ea5c3-114">Der Name des x. 509-Zertifikatspeichers.</span><span class="sxs-lookup"><span data-stu-id="ea5c3-114">The name of the X.509 certificate store.</span></span> <span data-ttu-id="ea5c3-115">Der Standardwert ist "My".</span><span class="sxs-lookup"><span data-stu-id="ea5c3-115">The default is "My".</span></span> <span data-ttu-id="ea5c3-116">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="ea5c3-116">Optional.</span></span>|  
|<span data-ttu-id="ea5c3-117">storeLocation</span><span class="sxs-lookup"><span data-stu-id="ea5c3-117">storeLocation</span></span>|<span data-ttu-id="ea5c3-118">Ein <xref:System.Security.Cryptography.X509Certificates.StoreLocation> -Wert, der den Speicherort des x. 509-Zertifikatspeichers angibt.</span><span class="sxs-lookup"><span data-stu-id="ea5c3-118">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="ea5c3-119">Der Standardwert ist "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="ea5c3-119">The default value is "LocalMachine".</span></span> <span data-ttu-id="ea5c3-120">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="ea5c3-120">Optional.</span></span>|  
|<span data-ttu-id="ea5c3-121">x509FindType</span><span class="sxs-lookup"><span data-stu-id="ea5c3-121">x509FindType</span></span>|<span data-ttu-id="ea5c3-122">Ein <xref:System.Security.Cryptography.X509Certificates.X509FindType> Wert, der den Typ der Suche angibt, die ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ea5c3-122">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="ea5c3-123">Der Standardwert ist "FindBySubjectDistinguishedName".</span><span class="sxs-lookup"><span data-stu-id="ea5c3-123">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="ea5c3-124">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="ea5c3-124">Optional.</span></span>|  
|<span data-ttu-id="ea5c3-125">findValue</span><span class="sxs-lookup"><span data-stu-id="ea5c3-125">findValue</span></span>|<span data-ttu-id="ea5c3-126">Der Wert, nach dem im X.509-Zertifikatspeicher gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="ea5c3-126">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="ea5c3-127">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="ea5c3-127">Optional.</span></span>|  
|<span data-ttu-id="ea5c3-128">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="ea5c3-128">isChainIncluded</span></span>|<span data-ttu-id="ea5c3-129">Gibt an, ob die Validierung mithilfe der Zertifikatskette ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ea5c3-129">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="ea5c3-130">Der Standardwert ist "true"; Mithilfe der Zertifikatskette erfolgt die Validierung.</span><span class="sxs-lookup"><span data-stu-id="ea5c3-130">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="ea5c3-131">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="ea5c3-131">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ea5c3-132">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ea5c3-132">Child Elements</span></span>  
 <span data-ttu-id="ea5c3-133">Keiner</span><span class="sxs-lookup"><span data-stu-id="ea5c3-133">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ea5c3-134">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ea5c3-134">Parent Elements</span></span>  
  
|<span data-ttu-id="ea5c3-135">Element</span><span class="sxs-lookup"><span data-stu-id="ea5c3-135">Element</span></span>|<span data-ttu-id="ea5c3-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ea5c3-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ea5c3-137">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="ea5c3-137">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|<span data-ttu-id="ea5c3-138">Konfiguriert das Zertifikat, das zum Verschlüsseln und Entschlüsseln von Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ea5c3-138">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea5c3-139">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ea5c3-139">Remarks</span></span>  
 <span data-ttu-id="ea5c3-140">Die `<certificateReference>` Element gibt die Einstellungen, die zum Suchen und überprüfen ein x. 509-Zertifikat im Zertifikatspeicher verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ea5c3-140">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="ea5c3-141">Wenn er angegeben wird als untergeordnetes Element von der `<serviceCertificate>` -Element, es gibt die Speicherort und die Überprüfung der Einstellungen des x. 509-Zertifikats, das zum Verschlüsseln und Entschlüsseln von Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ea5c3-141">When it is specified as the child element of the `<serviceCertificate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="ea5c3-142">Die `<certificateReference>` Element wird dargestellt, durch die <xref:System.ServiceModel.Configuration.CertificateReferenceElement> Klasse.</span><span class="sxs-lookup"><span data-stu-id="ea5c3-142">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>
