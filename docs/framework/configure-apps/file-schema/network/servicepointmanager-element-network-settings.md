---
title: '&lt;ServicePointManager&gt; -Element (Netzwerkeinstellungen)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#servicePointManager
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/servicePointManager
helpviewer_keywords:
- servicePointManager element
- <servicePointManager> element
ms.assetid: 6e5def51-3646-4ef6-a7bd-c69151321bec
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 5903174f125938923a63fc031421a8d5a020e56d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32753585"
---
# <a name="ltservicepointmanagergt-element-network-settings"></a><span data-ttu-id="a2673-102">&lt;ServicePointManager&gt; -Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="a2673-102">&lt;servicePointManager&gt; Element (Network Settings)</span></span>
<span data-ttu-id="a2673-103">Konfiguriert die Verbindungen mit Netzwerkressourcen.</span><span class="sxs-lookup"><span data-stu-id="a2673-103">Configures connections to network resources.</span></span>  
  
 <span data-ttu-id="a2673-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a2673-104">\<configuration></span></span>  
<span data-ttu-id="a2673-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="a2673-105">\<system.net></span></span>  
<span data-ttu-id="a2673-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="a2673-106">\<settings></span></span>  
<span data-ttu-id="a2673-107">\<ServicePointManager ></span><span class="sxs-lookup"><span data-stu-id="a2673-107">\<servicePointManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2673-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="a2673-108">Syntax</span></span>  
  
```xml  
<servicePointManager  
  checkCertificateName="true|false"  
  checkCertificateRevocationList="true|false"  
  encryptionPolicy="AllowNoEncryption|NoEncryption|RequireEncryption"  
  expect100Continue="true|false"  
  useNagleAlgorithm="true|false"  
  enableDnsRoundRobin="true|false"  
  dnsRefreshTimeout="time"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a2673-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a2673-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a2673-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a2673-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a2673-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="a2673-111">Attributes</span></span>  
  
|<span data-ttu-id="a2673-112">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="a2673-112">**Attribute**</span></span>|<span data-ttu-id="a2673-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a2673-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`checkCertificateName`|<span data-ttu-id="a2673-114">Gibt an, ob das System überprüft, ob der Name für das Zertifikat den Hostnamen entspricht, bevor Sie mit dem Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="a2673-114">Specifies whether the system should verify that the name on the certificate matches the server host name before using the certificate.</span></span> <span data-ttu-id="a2673-115">Der Standardwert ist `true`.</span><span class="sxs-lookup"><span data-stu-id="a2673-115">The default value is `true`.</span></span>|  
|`checkCertificateRevocationList`|<span data-ttu-id="a2673-116">Gibt an, ob das System, ob das Zertifikat widerrufen wurde, bevor Sie mithilfe des Zertifikats überprüft werden soll.</span><span class="sxs-lookup"><span data-stu-id="a2673-116">Specifies whether the system should check whether the certificate has been revoked before using the certificate.</span></span> <span data-ttu-id="a2673-117">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="a2673-117">The default value is `false`.</span></span>|  
|`dnsRefreshTimeout`|<span data-ttu-id="a2673-118">Gibt an, wie lange Dienst DNS (Domain Name) Lösungen zwischengespeichert werden in Verbindung mit der DNS-Round-Robin-Option in Millisekunden.</span><span class="sxs-lookup"><span data-stu-id="a2673-118">Specifies how long Domain Name Service (DNS) resolutions are cached in conjunction with the DNS Round Robin option, in milliseconds.</span></span> <span data-ttu-id="a2673-119">Der Standardwert ist 120.000 Millisekunden (zwei Minuten).</span><span class="sxs-lookup"><span data-stu-id="a2673-119">The default value is 120,000 milliseconds (two minutes).</span></span>|  
|`enableDnsRoundRobin`|<span data-ttu-id="a2673-120">Gibt an, ob die DNS-Auflösung des Hosts benennt mit mehreren IP (Internet Protocol)-Adressen zurückgegeben, alle Adressen oder nur die erste Aktivität.</span><span class="sxs-lookup"><span data-stu-id="a2673-120">Specifies whether DNS resolutions of host names with multiple Internet Protocol (IP) addresses return all the addresses, or just the first one.</span></span> <span data-ttu-id="a2673-121">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="a2673-121">The default value is `false`.</span></span>|  
|`encryptionPolicy`|<span data-ttu-id="a2673-122">Gibt an, die Verschlüsselungsrichtlinie für eine SSL/TLS-Sitzung angewendet wird, auf eine <xref:System.Net.ServicePointManager> Instanz.</span><span class="sxs-lookup"><span data-stu-id="a2673-122">Specifies the encryption policy applied to an SSL/TLS session on a <xref:System.Net.ServicePointManager> instance.</span></span> <span data-ttu-id="a2673-123">Die möglichen Werte sind entsprechen den Werten für die <xref:System.Net.Security.EncryptionPolicy> Enumeration.</span><span class="sxs-lookup"><span data-stu-id="a2673-123">The possible values are equivalent to the values for the <xref:System.Net.Security.EncryptionPolicy> enumeration.</span></span> <span data-ttu-id="a2673-124">Die Verwendung von <xref:System.Security.Authentication.CipherAlgorithmType.Null> ist erforderlich, wenn die Verschlüsselungsrichtlinie, um festgelegt ist `NoEncryption`.</span><span class="sxs-lookup"><span data-stu-id="a2673-124">The use of <xref:System.Security.Authentication.CipherAlgorithmType.Null> is required when the encryption policy is set to `NoEncryption`.</span></span> <span data-ttu-id="a2673-125">Der Standardwert ist `RequireEncryption`.</span><span class="sxs-lookup"><span data-stu-id="a2673-125">The default value is `RequireEncryption`.</span></span>|  
|`expect100Continue`|<span data-ttu-id="a2673-126">Gibt an, ob die POST-Methoden erwarten soll eine `100-continue` Antwort vom Server.</span><span class="sxs-lookup"><span data-stu-id="a2673-126">Specifies whether POST methods should expect to receive a `100-continue` response from the server.</span></span> <span data-ttu-id="a2673-127">Der Standardwert ist `true`.</span><span class="sxs-lookup"><span data-stu-id="a2673-127">The default value is `true`.</span></span>|  
|`useNagleAlgorithm`|<span data-ttu-id="a2673-128">Gibt an, ob den Nagle-Algorithmus, Verbindungen, die von der Point-Dienst-Manager gesteuert verwenden.</span><span class="sxs-lookup"><span data-stu-id="a2673-128">Specifies whether connections controlled by the service point manager use the Nagle algorithm.</span></span> <span data-ttu-id="a2673-129">Der Standardwert ist `true`.</span><span class="sxs-lookup"><span data-stu-id="a2673-129">The default value is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a2673-130">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a2673-130">Child Elements</span></span>  
 <span data-ttu-id="a2673-131">Keine</span><span class="sxs-lookup"><span data-stu-id="a2673-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a2673-132">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a2673-132">Parent Elements</span></span>  
  
|<span data-ttu-id="a2673-133">**Element**</span><span class="sxs-lookup"><span data-stu-id="a2673-133">**Element**</span></span>|<span data-ttu-id="a2673-134">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a2673-134">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a2673-135">Einstellungen</span><span class="sxs-lookup"><span data-stu-id="a2673-135">Settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="a2673-136">Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="a2673-136">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2673-137">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a2673-137">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="a2673-138">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="a2673-138">Configuration Files</span></span>  
 <span data-ttu-id="a2673-139">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a2673-139">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2673-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2673-140">See Also</span></span>  
 <xref:System.Net.ServicePointManager>  
 <xref:System.Net.Security.EncryptionPolicy>  
 [<span data-ttu-id="a2673-141">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="a2673-141">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
