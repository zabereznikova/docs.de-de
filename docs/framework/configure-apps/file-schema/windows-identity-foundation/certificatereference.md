---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: 782ca3344774b8412a18e3cf13bff5f969751ea3
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252145"
---
# <a name="certificatereference"></a><span data-ttu-id="01dd2-101">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="01dd2-101">\<certificateReference></span></span>
<span data-ttu-id="01dd2-102">Gibt Einstellungen an, die verwendet werden, um ein X. 509-Zertifikat in einem Zertifikat Speicher zu suchen und zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="01dd2-102">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
<span data-ttu-id="01dd2-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="01dd2-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="01dd2-104">&nbsp;&nbsp;[ **\<System. IdentityModel. Services->** ](system-identitymodel-services.md)</span><span class="sxs-lookup"><span data-stu-id="01dd2-104">&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)</span></span>\
<span data-ttu-id="01dd2-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<federationconfiguration->** ](federationconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="01dd2-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)</span></span>\
<span data-ttu-id="01dd2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCertificate->** ](servicecertificate.md)</span><span class="sxs-lookup"><span data-stu-id="01dd2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate.md)</span></span>\
<span data-ttu-id="01dd2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<certifiupereferenzierung >**</span><span class="sxs-lookup"><span data-stu-id="01dd2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateReference>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01dd2-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="01dd2-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="01dd2-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="01dd2-109">Attributes and Elements</span></span>  
 <span data-ttu-id="01dd2-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="01dd2-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="01dd2-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="01dd2-111">Attributes</span></span>  
  
|<span data-ttu-id="01dd2-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="01dd2-112">Attribute</span></span>|<span data-ttu-id="01dd2-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="01dd2-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="01dd2-114">storeName</span><span class="sxs-lookup"><span data-stu-id="01dd2-114">storeName</span></span>|<span data-ttu-id="01dd2-115">Der Name des X. 509-Zertifikats Speicher.</span><span class="sxs-lookup"><span data-stu-id="01dd2-115">The name of the X.509 certificate store.</span></span> <span data-ttu-id="01dd2-116">Der Standardwert ist "My".</span><span class="sxs-lookup"><span data-stu-id="01dd2-116">The default is "My".</span></span> <span data-ttu-id="01dd2-117">Optional.</span><span class="sxs-lookup"><span data-stu-id="01dd2-117">Optional.</span></span>|  
|<span data-ttu-id="01dd2-118">storeLocation</span><span class="sxs-lookup"><span data-stu-id="01dd2-118">storeLocation</span></span>|<span data-ttu-id="01dd2-119">Ein <xref:System.Security.Cryptography.X509Certificates.StoreLocation> -Wert, der den Speicherort des X. 509-Zertifikat Speicher angibt.</span><span class="sxs-lookup"><span data-stu-id="01dd2-119">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="01dd2-120">Der Standardwert ist "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="01dd2-120">The default value is "LocalMachine".</span></span> <span data-ttu-id="01dd2-121">Optional.</span><span class="sxs-lookup"><span data-stu-id="01dd2-121">Optional.</span></span>|  
|<span data-ttu-id="01dd2-122">x509FindType</span><span class="sxs-lookup"><span data-stu-id="01dd2-122">x509FindType</span></span>|<span data-ttu-id="01dd2-123">Ein <xref:System.Security.Cryptography.X509Certificates.X509FindType> -Wert, der den Typ der auszuführenden Suche angibt.</span><span class="sxs-lookup"><span data-stu-id="01dd2-123">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="01dd2-124">Der Standardwert ist "findbysubjeterkennbare shedname".</span><span class="sxs-lookup"><span data-stu-id="01dd2-124">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="01dd2-125">Optional.</span><span class="sxs-lookup"><span data-stu-id="01dd2-125">Optional.</span></span>|  
|<span data-ttu-id="01dd2-126">findValue</span><span class="sxs-lookup"><span data-stu-id="01dd2-126">findValue</span></span>|<span data-ttu-id="01dd2-127">Der Wert, nach dem im X.509-Zertifikatspeicher gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="01dd2-127">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="01dd2-128">Optional.</span><span class="sxs-lookup"><span data-stu-id="01dd2-128">Optional.</span></span>|  
|<span data-ttu-id="01dd2-129">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="01dd2-129">isChainIncluded</span></span>|<span data-ttu-id="01dd2-130">Gibt an, ob die Überprüfung mithilfe der Zertifikat Kette durchgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="01dd2-130">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="01dd2-131">Der Standardwert ist "true". die Überprüfung erfolgt mithilfe der Zertifikat Kette.</span><span class="sxs-lookup"><span data-stu-id="01dd2-131">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="01dd2-132">Optional.</span><span class="sxs-lookup"><span data-stu-id="01dd2-132">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="01dd2-133">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="01dd2-133">Child Elements</span></span>  
 <span data-ttu-id="01dd2-134">None</span><span class="sxs-lookup"><span data-stu-id="01dd2-134">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="01dd2-135">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="01dd2-135">Parent Elements</span></span>  
  
|<span data-ttu-id="01dd2-136">Element</span><span class="sxs-lookup"><span data-stu-id="01dd2-136">Element</span></span>|<span data-ttu-id="01dd2-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="01dd2-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="01dd2-138">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="01dd2-138">\<serviceCertificate></span></span>](servicecertificate.md)|<span data-ttu-id="01dd2-139">Konfiguriert das Zertifikat, das zum Verschlüsseln und Entschlüsseln von Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="01dd2-139">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01dd2-140">Hinweise</span><span class="sxs-lookup"><span data-stu-id="01dd2-140">Remarks</span></span>  
 <span data-ttu-id="01dd2-141">Das `<certificateReference>` -Element gibt Einstellungen an, die verwendet werden, um ein X. 509-Zertifikat in einem Zertifikat Speicher zu suchen und zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="01dd2-141">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="01dd2-142">Wenn es als untergeordnetes Element des `<serviceCertificate>` -Elements angegeben ist, gibt es den Speicherort und die Überprüfungs Einstellungen des X. 509-Zertifikats an, das zum Verschlüsseln und Entschlüsseln von Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="01dd2-142">When it is specified as the child element of the `<serviceCertificate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="01dd2-143">Das `<certificateReference>` -Element wird durch die <xref:System.ServiceModel.Configuration.CertificateReferenceElement> -Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="01dd2-143">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>
