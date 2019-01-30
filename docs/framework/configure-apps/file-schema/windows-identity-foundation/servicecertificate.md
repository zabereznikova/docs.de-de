---
title: <serviceCertificate>
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
ms.openlocfilehash: 328d074f9edc5ddf871308a7e3d694bf94adea78
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55261601"
---
# <a name="servicecertificate"></a><span data-ttu-id="e635b-101">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="e635b-101">\<serviceCertificate></span></span>
<span data-ttu-id="e635b-102">Konfiguriert das x. 509-Zertifikat, das zum Verschlüsseln und Entschlüsseln von Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e635b-102">Configures the X.509 certificate that is used to encrypt and decrypt tokens.</span></span>  
  
 <span data-ttu-id="e635b-103">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="e635b-103">\<system.identityModel.services></span></span>  
<span data-ttu-id="e635b-104">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="e635b-104">\<federationConfiguration></span></span>  
<span data-ttu-id="e635b-105">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="e635b-105">\<serviceCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e635b-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="e635b-106">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e635b-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e635b-107">Attributes and Elements</span></span>  
 <span data-ttu-id="e635b-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e635b-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e635b-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="e635b-109">Attributes</span></span>  
 <span data-ttu-id="e635b-110">Keine</span><span class="sxs-lookup"><span data-stu-id="e635b-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e635b-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e635b-111">Child Elements</span></span>  
  
|<span data-ttu-id="e635b-112">Element</span><span class="sxs-lookup"><span data-stu-id="e635b-112">Element</span></span>|<span data-ttu-id="e635b-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e635b-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e635b-114">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="e635b-114">\<certificateReference></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatereference.md)|<span data-ttu-id="e635b-115">Gibt die Einstellungen, die zum Suchen und überprüfen ein x. 509-Zertifikat im Zertifikatspeicher verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e635b-115">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e635b-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e635b-116">Parent Elements</span></span>  
  
|<span data-ttu-id="e635b-117">Element</span><span class="sxs-lookup"><span data-stu-id="e635b-117">Element</span></span>|<span data-ttu-id="e635b-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e635b-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e635b-119">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="e635b-119">\<federationConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|<span data-ttu-id="e635b-120">Enthält Einstellungen, konfigurieren die <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) und die <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span><span class="sxs-lookup"><span data-stu-id="e635b-120">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e635b-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e635b-121">Example</span></span>  
 <span data-ttu-id="e635b-122">Das folgende XML zeigt die Verwendung der \<ServiceCertificate >-Element.</span><span class="sxs-lookup"><span data-stu-id="e635b-122">The following XML shows the use of the \<serviceCertificate> element.</span></span> <span data-ttu-id="e635b-123">Der XML-Code stammt aus dem `CustomToken` Beispiel.</span><span class="sxs-lookup"><span data-stu-id="e635b-123">The XML is taken from the `CustomToken` sample.</span></span>  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
