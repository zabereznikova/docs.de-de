---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: 47d432a84d070476ddffd9b98a4ba46d8163bdc3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152813"
---
# \<certificateReference>
<span data-ttu-id="ebd96-101">Gibt Einstellungen an, die verwendet werden, um ein X. 509-Zertifikat in einem Zertifikat Speicher zu suchen und zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="ebd96-101">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateReference>**  
  
## <a name="syntax"></a><span data-ttu-id="ebd96-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="ebd96-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ebd96-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ebd96-103">Attributes and Elements</span></span>  
 <span data-ttu-id="ebd96-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ebd96-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ebd96-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="ebd96-105">Attributes</span></span>  
  
|<span data-ttu-id="ebd96-106">attribute</span><span class="sxs-lookup"><span data-stu-id="ebd96-106">Attribute</span></span>|<span data-ttu-id="ebd96-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ebd96-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ebd96-108">storeName</span><span class="sxs-lookup"><span data-stu-id="ebd96-108">storeName</span></span>|<span data-ttu-id="ebd96-109">Der Namen des X.509-Zertifikatsspeichers.</span><span class="sxs-lookup"><span data-stu-id="ebd96-109">The name of the X.509 certificate store.</span></span> <span data-ttu-id="ebd96-110">Der Standardwert ist "My".</span><span class="sxs-lookup"><span data-stu-id="ebd96-110">The default is "My".</span></span> <span data-ttu-id="ebd96-111">(Optional)</span><span class="sxs-lookup"><span data-stu-id="ebd96-111">Optional.</span></span>|  
|<span data-ttu-id="ebd96-112">storeLocation</span><span class="sxs-lookup"><span data-stu-id="ebd96-112">storeLocation</span></span>|<span data-ttu-id="ebd96-113">Ein- <xref:System.Security.Cryptography.X509Certificates.StoreLocation> Wert, der den Speicherort des X. 509-Zertifikat Speicher angibt.</span><span class="sxs-lookup"><span data-stu-id="ebd96-113">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="ebd96-114">Der Standardwert ist "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="ebd96-114">The default value is "LocalMachine".</span></span> <span data-ttu-id="ebd96-115">(Optional)</span><span class="sxs-lookup"><span data-stu-id="ebd96-115">Optional.</span></span>|  
|<span data-ttu-id="ebd96-116">x509FindType</span><span class="sxs-lookup"><span data-stu-id="ebd96-116">x509FindType</span></span>|<span data-ttu-id="ebd96-117">Ein- <xref:System.Security.Cryptography.X509Certificates.X509FindType> Wert, der den Typ der auszuführenden Suche angibt.</span><span class="sxs-lookup"><span data-stu-id="ebd96-117">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="ebd96-118">Der Standardwert ist "findbysubjeterkennbare shedname".</span><span class="sxs-lookup"><span data-stu-id="ebd96-118">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="ebd96-119">(Optional)</span><span class="sxs-lookup"><span data-stu-id="ebd96-119">Optional.</span></span>|  
|<span data-ttu-id="ebd96-120">findValue</span><span class="sxs-lookup"><span data-stu-id="ebd96-120">findValue</span></span>|<span data-ttu-id="ebd96-121">Der Wert, nach dem im X.509-Zertifikatspeicher gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="ebd96-121">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="ebd96-122">(Optional)</span><span class="sxs-lookup"><span data-stu-id="ebd96-122">Optional.</span></span>|  
|<span data-ttu-id="ebd96-123">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="ebd96-123">isChainIncluded</span></span>|<span data-ttu-id="ebd96-124">Gibt an, ob die Überprüfung mithilfe der Zertifikat Kette durchgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ebd96-124">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="ebd96-125">Der Standardwert ist "true". die Überprüfung erfolgt mithilfe der Zertifikat Kette.</span><span class="sxs-lookup"><span data-stu-id="ebd96-125">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="ebd96-126">(Optional)</span><span class="sxs-lookup"><span data-stu-id="ebd96-126">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ebd96-127">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ebd96-127">Child Elements</span></span>  
 <span data-ttu-id="ebd96-128">Keine</span><span class="sxs-lookup"><span data-stu-id="ebd96-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ebd96-129">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ebd96-129">Parent Elements</span></span>  
  
|<span data-ttu-id="ebd96-130">Element</span><span class="sxs-lookup"><span data-stu-id="ebd96-130">Element</span></span>|<span data-ttu-id="ebd96-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ebd96-131">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate.md)|<span data-ttu-id="ebd96-132">Konfiguriert das Zertifikat, das zum Verschlüsseln und Entschlüsseln von Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ebd96-132">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ebd96-133">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ebd96-133">Remarks</span></span>  
 <span data-ttu-id="ebd96-134">Das- `<certificateReference>` Element gibt Einstellungen an, die verwendet werden, um ein X. 509-Zertifikat in einem Zertifikat Speicher zu suchen und zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="ebd96-134">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="ebd96-135">Wenn es als untergeordnetes Element des-Elements angegeben ist `<serviceCertificate>` , gibt es den Speicherort und die Überprüfungs Einstellungen des X. 509-Zertifikats an, das zum Verschlüsseln und Entschlüsseln von Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ebd96-135">When it is specified as the child element of the `<serviceCertificate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="ebd96-136">Das- `<certificateReference>` Element wird durch die- <xref:System.ServiceModel.Configuration.CertificateReferenceElement> Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ebd96-136">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>
