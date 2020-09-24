---
title: <serviceCertificate>
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
ms.openlocfilehash: ce8be6eea5469b099a368a0b62e791faa7e3cbfc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156991"
---
# \<serviceCertificate>

<span data-ttu-id="00ea9-101">Konfiguriert das X. 509-Zertifikat, das zum Verschlüsseln und Entschlüsseln von Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="00ea9-101">Configures the X.509 certificate that is used to encrypt and decrypt tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="00ea9-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="00ea9-102">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="00ea9-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="00ea9-103">Attributes and Elements</span></span>  

 <span data-ttu-id="00ea9-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="00ea9-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="00ea9-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="00ea9-105">Attributes</span></span>  

 <span data-ttu-id="00ea9-106">Keine</span><span class="sxs-lookup"><span data-stu-id="00ea9-106">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="00ea9-107">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="00ea9-107">Child Elements</span></span>  
  
|<span data-ttu-id="00ea9-108">Element</span><span class="sxs-lookup"><span data-stu-id="00ea9-108">Element</span></span>|<span data-ttu-id="00ea9-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00ea9-109">Description</span></span>|  
|-------------|-----------------|  
|[\<certificateReference>](certificatereference.md)|<span data-ttu-id="00ea9-110">Gibt Einstellungen an, die verwendet werden, um ein X. 509-Zertifikat in einem Zertifikat Speicher zu suchen und zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="00ea9-110">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="00ea9-111">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="00ea9-111">Parent Elements</span></span>  
  
|<span data-ttu-id="00ea9-112">Element</span><span class="sxs-lookup"><span data-stu-id="00ea9-112">Element</span></span>|<span data-ttu-id="00ea9-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00ea9-113">Description</span></span>|  
|-------------|-----------------|  
|[\<federationConfiguration>](federationconfiguration.md)|<span data-ttu-id="00ea9-114">Enthält die Einstellungen, mit denen <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (wsfam) und <xref:System.IdentityModel.Services.SessionAuthenticationModule> (Sam) konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="00ea9-114">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="00ea9-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="00ea9-115">Example</span></span>  

 <span data-ttu-id="00ea9-116">Der folgende XML-Code zeigt die Verwendung des- \<serviceCertificate> Elements.</span><span class="sxs-lookup"><span data-stu-id="00ea9-116">The following XML shows the use of the \<serviceCertificate> element.</span></span> <span data-ttu-id="00ea9-117">Der XML-Code stammt aus dem `CustomToken` Beispiel.</span><span class="sxs-lookup"><span data-stu-id="00ea9-117">The XML is taken from the `CustomToken` sample.</span></span>  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
