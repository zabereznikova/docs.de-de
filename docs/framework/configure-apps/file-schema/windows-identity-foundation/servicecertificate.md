---
title: '&lt;ServiceCertificate&gt;'
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
ms.openlocfilehash: 008d2269a72759117658e27ec130cc8cf62cfdfa
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47084305"
---
# <a name="ltservicecertificategt"></a><span data-ttu-id="f51f3-102">&lt;ServiceCertificate&gt;</span><span class="sxs-lookup"><span data-stu-id="f51f3-102">&lt;serviceCertificate&gt;</span></span>
<span data-ttu-id="f51f3-103">Konfiguriert das x. 509-Zertifikat, das zum Verschlüsseln und Entschlüsseln von Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f51f3-103">Configures the X.509 certificate that is used to encrypt and decrypt tokens.</span></span>  
  
 <span data-ttu-id="f51f3-104">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="f51f3-104">\<system.identityModel.services></span></span>  
<span data-ttu-id="f51f3-105">\<FederationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="f51f3-105">\<federationConfiguration></span></span>  
<span data-ttu-id="f51f3-106">\<ServiceCertificate ></span><span class="sxs-lookup"><span data-stu-id="f51f3-106">\<serviceCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f51f3-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="f51f3-107">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f51f3-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f51f3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f51f3-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f51f3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f51f3-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="f51f3-110">Attributes</span></span>  
 <span data-ttu-id="f51f3-111">Keiner</span><span class="sxs-lookup"><span data-stu-id="f51f3-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f51f3-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f51f3-112">Child Elements</span></span>  
  
|<span data-ttu-id="f51f3-113">Element</span><span class="sxs-lookup"><span data-stu-id="f51f3-113">Element</span></span>|<span data-ttu-id="f51f3-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f51f3-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f51f3-115">\<CertificateReference ></span><span class="sxs-lookup"><span data-stu-id="f51f3-115">\<certificateReference></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatereference.md)|<span data-ttu-id="f51f3-116">Gibt die Einstellungen, die zum Suchen und überprüfen ein x. 509-Zertifikat im Zertifikatspeicher verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f51f3-116">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f51f3-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f51f3-117">Parent Elements</span></span>  
  
|<span data-ttu-id="f51f3-118">Element</span><span class="sxs-lookup"><span data-stu-id="f51f3-118">Element</span></span>|<span data-ttu-id="f51f3-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f51f3-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f51f3-120">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="f51f3-120">\<federationConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|<span data-ttu-id="f51f3-121">Enthält Einstellungen, konfigurieren die <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) und die <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span><span class="sxs-lookup"><span data-stu-id="f51f3-121">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f51f3-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f51f3-122">Example</span></span>  
 <span data-ttu-id="f51f3-123">Das folgende XML zeigt die Verwendung der \<ServiceCertificate >-Element.</span><span class="sxs-lookup"><span data-stu-id="f51f3-123">The following XML shows the use of the \<serviceCertificate> element.</span></span> <span data-ttu-id="f51f3-124">Der XML-Code stammt aus dem `CustomToken` Beispiel.</span><span class="sxs-lookup"><span data-stu-id="f51f3-124">The XML is taken from the `CustomToken` sample.</span></span>  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
