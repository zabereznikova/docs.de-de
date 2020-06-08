---
title: <servicePointManager>-Element (Netzwerkeinstellungen)
description: <servicePointManager>Mit dem Netzwerk Einstellungs Element werden Verbindungen zu den Optionen für Netzwerkressourcen in der .NET Framework konfiguriert.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#servicePointManager
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/servicePointManager
helpviewer_keywords:
- servicePointManager element
- <servicePointManager> element
ms.assetid: 6e5def51-3646-4ef6-a7bd-c69151321bec
ms.openlocfilehash: eb27716ec7c2936f32a7e4d4c983d1e175c4d044
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504523"
---
# <a name="servicepointmanager-element-network-settings"></a><span data-ttu-id="a9863-103">\<servicePointManager>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="a9863-103">\<servicePointManager> Element (Network Settings)</span></span>
<span data-ttu-id="a9863-104">Konfiguriert Verbindungen mit Netzwerkressourcen.</span><span class="sxs-lookup"><span data-stu-id="a9863-104">Configures connections to network resources.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<servicePointManager>**

## <a name="syntax"></a><span data-ttu-id="a9863-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a9863-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a9863-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a9863-106">Attributes and Elements</span></span>  
 <span data-ttu-id="a9863-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a9863-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a9863-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="a9863-108">Attributes</span></span>  
  
|<span data-ttu-id="a9863-109">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="a9863-109">**Attribute**</span></span>|<span data-ttu-id="a9863-110">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a9863-110">**Description**</span></span>|  
|-------------------|---------------------|  
|`checkCertificateName`|<span data-ttu-id="a9863-111">Gibt an, ob das System überprüfen soll, ob der Name des Zertifikats mit dem Server Hostnamen übereinstimmt, bevor das Zertifikat verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a9863-111">Specifies whether the system should verify that the name on the certificate matches the server host name before using the certificate.</span></span> <span data-ttu-id="a9863-112">Der Standardwert lautet `true`.</span><span class="sxs-lookup"><span data-stu-id="a9863-112">The default value is `true`.</span></span>|  
|`checkCertificateRevocationList`|<span data-ttu-id="a9863-113">Gibt an, ob das System vor der Verwendung des Zertifikats überprüfen soll, ob das Zertifikat widerrufen wurde.</span><span class="sxs-lookup"><span data-stu-id="a9863-113">Specifies whether the system should check whether the certificate has been revoked before using the certificate.</span></span> <span data-ttu-id="a9863-114">Der Standardwert lautet `false`.</span><span class="sxs-lookup"><span data-stu-id="a9863-114">The default value is `false`.</span></span>|  
|`dnsRefreshTimeout`|<span data-ttu-id="a9863-115">Gibt an, wie lange die Auflösung von Domain Name Service (DNS) in Verbindung mit der Option "DNS Round Robin" in Millisekunden zwischengespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="a9863-115">Specifies how long Domain Name Service (DNS) resolutions are cached in conjunction with the DNS Round Robin option, in milliseconds.</span></span> <span data-ttu-id="a9863-116">Der Standardwert ist 120.000 Millisekunden (zwei Minuten).</span><span class="sxs-lookup"><span data-stu-id="a9863-116">The default value is 120,000 milliseconds (two minutes).</span></span>|  
|`enableDnsRoundRobin`|<span data-ttu-id="a9863-117">Gibt an, ob DNS-Auflösungen von Hostnamen mit mehreren IP-Adressen (Internet Protocol) alle Adressen oder nur den ersten zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="a9863-117">Specifies whether DNS resolutions of host names with multiple Internet Protocol (IP) addresses return all the addresses, or just the first one.</span></span> <span data-ttu-id="a9863-118">Der Standardwert lautet `false`.</span><span class="sxs-lookup"><span data-stu-id="a9863-118">The default value is `false`.</span></span>|  
|`encryptionPolicy`|<span data-ttu-id="a9863-119">Gibt die Verschlüsselungs Richtlinie an, die auf eine SSL/TLS-Sitzung auf einer-Instanz angewendet wird <xref:System.Net.ServicePointManager> .</span><span class="sxs-lookup"><span data-stu-id="a9863-119">Specifies the encryption policy applied to an SSL/TLS session on a <xref:System.Net.ServicePointManager> instance.</span></span> <span data-ttu-id="a9863-120">Die möglichen Werte entsprechen den Werten für die- <xref:System.Net.Security.EncryptionPolicy> Enumeration.</span><span class="sxs-lookup"><span data-stu-id="a9863-120">The possible values are equivalent to the values for the <xref:System.Net.Security.EncryptionPolicy> enumeration.</span></span> <span data-ttu-id="a9863-121"><xref:System.Security.Authentication.CipherAlgorithmType.Null>Wenn die Verschlüsselungs Richtlinie auf festgelegt ist, ist die Verwendung von erforderlich `NoEncryption` .</span><span class="sxs-lookup"><span data-stu-id="a9863-121">The use of <xref:System.Security.Authentication.CipherAlgorithmType.Null> is required when the encryption policy is set to `NoEncryption`.</span></span> <span data-ttu-id="a9863-122">Der Standardwert lautet `RequireEncryption`.</span><span class="sxs-lookup"><span data-stu-id="a9863-122">The default value is `RequireEncryption`.</span></span>|  
|`expect100Continue`|<span data-ttu-id="a9863-123">Gibt an, ob Post-Methoden erwarten, dass eine `100-continue` Antwort vom Server empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="a9863-123">Specifies whether POST methods should expect to receive a `100-continue` response from the server.</span></span> <span data-ttu-id="a9863-124">Der Standardwert lautet `true`.</span><span class="sxs-lookup"><span data-stu-id="a9863-124">The default value is `true`.</span></span>|  
|`useNagleAlgorithm`|<span data-ttu-id="a9863-125">Gibt an, ob vom Dienst Punkt-Manager gesteuerte Verbindungen den Nagle-Algorithmus verwenden.</span><span class="sxs-lookup"><span data-stu-id="a9863-125">Specifies whether connections controlled by the service point manager use the Nagle algorithm.</span></span> <span data-ttu-id="a9863-126">Der Standardwert lautet `true`.</span><span class="sxs-lookup"><span data-stu-id="a9863-126">The default value is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a9863-127">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a9863-127">Child Elements</span></span>  
 <span data-ttu-id="a9863-128">Keine</span><span class="sxs-lookup"><span data-stu-id="a9863-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a9863-129">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a9863-129">Parent Elements</span></span>  
  
|<span data-ttu-id="a9863-130">**Element**</span><span class="sxs-lookup"><span data-stu-id="a9863-130">**Element**</span></span>|<span data-ttu-id="a9863-131">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a9863-131">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a9863-132">Einstellungen</span><span class="sxs-lookup"><span data-stu-id="a9863-132">Settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="a9863-133">Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="a9863-133">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9863-134">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a9863-134">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="a9863-135">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="a9863-135">Configuration Files</span></span>  
 <span data-ttu-id="a9863-136">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a9863-136">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9863-137">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="a9863-137">See also</span></span>

- <xref:System.Net.ServicePointManager>
- <xref:System.Net.Security.EncryptionPolicy>
- [<span data-ttu-id="a9863-138">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="a9863-138">Network Settings Schema</span></span>](index.md)
