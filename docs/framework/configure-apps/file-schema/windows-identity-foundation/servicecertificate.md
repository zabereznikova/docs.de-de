---
title: <serviceCertificate>
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
ms.openlocfilehash: 653dd9cfadbfd33f5371b77172199b946321bc8c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251859"
---
# \<serviceCertificate>
<span data-ttu-id="893a4-101">Konfiguriert das X. 509-Zertifikat, das zum Verschlüsseln und Entschlüsseln von Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="893a4-101">Configures the X.509 certificate that is used to encrypt and decrypt tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="893a4-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="893a4-102">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="893a4-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="893a4-103">Attributes and Elements</span></span>  
 <span data-ttu-id="893a4-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="893a4-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="893a4-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="893a4-105">Attributes</span></span>  
 <span data-ttu-id="893a4-106">Keine</span><span class="sxs-lookup"><span data-stu-id="893a4-106">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="893a4-107">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="893a4-107">Child Elements</span></span>  
  
|<span data-ttu-id="893a4-108">Element</span><span class="sxs-lookup"><span data-stu-id="893a4-108">Element</span></span>|<span data-ttu-id="893a4-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="893a4-109">Description</span></span>|  
|-------------|-----------------|  
|[\<certificateReference>](certificatereference.md)|<span data-ttu-id="893a4-110">Gibt Einstellungen an, die verwendet werden, um ein X. 509-Zertifikat in einem Zertifikat Speicher zu suchen und zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="893a4-110">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="893a4-111">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="893a4-111">Parent Elements</span></span>  
  
|<span data-ttu-id="893a4-112">Element</span><span class="sxs-lookup"><span data-stu-id="893a4-112">Element</span></span>|<span data-ttu-id="893a4-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="893a4-113">Description</span></span>|  
|-------------|-----------------|  
|[\<federationConfiguration>](federationconfiguration.md)|<span data-ttu-id="893a4-114">Enthält die Einstellungen, mit denen <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (wsfam) und <xref:System.IdentityModel.Services.SessionAuthenticationModule> (Sam) konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="893a4-114">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="893a4-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="893a4-115">Example</span></span>  
 <span data-ttu-id="893a4-116">Der folgende XML-Code zeigt die Verwendung des- \<serviceCertificate> Elements.</span><span class="sxs-lookup"><span data-stu-id="893a4-116">The following XML shows the use of the \<serviceCertificate> element.</span></span> <span data-ttu-id="893a4-117">Der XML-Code stammt aus dem `CustomToken` Beispiel.</span><span class="sxs-lookup"><span data-stu-id="893a4-117">The XML is taken from the `CustomToken` sample.</span></span>  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
