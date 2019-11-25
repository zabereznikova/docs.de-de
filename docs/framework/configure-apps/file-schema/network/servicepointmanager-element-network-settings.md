---
title: <servicePointManager>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#servicePointManager
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/servicePointManager
helpviewer_keywords:
- servicePointManager element
- <servicePointManager> element
ms.assetid: 6e5def51-3646-4ef6-a7bd-c69151321bec
ms.openlocfilehash: b7333016fea2d46285d3c98181c0ca4904c376f8
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089130"
---
# <a name="servicepointmanager-element-network-settings"></a><span data-ttu-id="738ea-102">\<ServicePointManager-> Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="738ea-102">\<servicePointManager> Element (Network Settings)</span></span>
<span data-ttu-id="738ea-103">Konfiguriert Verbindungen mit Netzwerkressourcen.</span><span class="sxs-lookup"><span data-stu-id="738ea-103">Configures connections to network resources.</span></span>  

<span data-ttu-id="738ea-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="738ea-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="738ea-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="738ea-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="738ea-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Einstellungen**](settings-element-network-settings.md) ></span><span class="sxs-lookup"><span data-stu-id="738ea-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)</span></span>\
<span data-ttu-id="738ea-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<ServicePointManager >**</span><span class="sxs-lookup"><span data-stu-id="738ea-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<servicePointManager>**</span></span>

## <a name="syntax"></a><span data-ttu-id="738ea-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="738ea-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="738ea-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="738ea-109">Attributes and Elements</span></span>  
 <span data-ttu-id="738ea-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="738ea-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="738ea-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="738ea-111">Attributes</span></span>  
  
|<span data-ttu-id="738ea-112">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="738ea-112">**Attribute**</span></span>|<span data-ttu-id="738ea-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="738ea-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`checkCertificateName`|<span data-ttu-id="738ea-114">Gibt an, ob das System überprüfen soll, ob der Name des Zertifikats mit dem Server Hostnamen übereinstimmt, bevor das Zertifikat verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="738ea-114">Specifies whether the system should verify that the name on the certificate matches the server host name before using the certificate.</span></span> <span data-ttu-id="738ea-115">Der Standardwert ist `true`sein.</span><span class="sxs-lookup"><span data-stu-id="738ea-115">The default value is `true`.</span></span>|  
|`checkCertificateRevocationList`|<span data-ttu-id="738ea-116">Gibt an, ob das System vor der Verwendung des Zertifikats überprüfen soll, ob das Zertifikat widerrufen wurde.</span><span class="sxs-lookup"><span data-stu-id="738ea-116">Specifies whether the system should check whether the certificate has been revoked before using the certificate.</span></span> <span data-ttu-id="738ea-117">Der Standardwert ist `false`sein.</span><span class="sxs-lookup"><span data-stu-id="738ea-117">The default value is `false`.</span></span>|  
|`dnsRefreshTimeout`|<span data-ttu-id="738ea-118">Gibt an, wie lange die Auflösung von Domain Name Service (DNS) in Verbindung mit der Option "DNS Round Robin" in Millisekunden zwischengespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="738ea-118">Specifies how long Domain Name Service (DNS) resolutions are cached in conjunction with the DNS Round Robin option, in milliseconds.</span></span> <span data-ttu-id="738ea-119">Der Standardwert ist 120.000 Millisekunden (zwei Minuten).</span><span class="sxs-lookup"><span data-stu-id="738ea-119">The default value is 120,000 milliseconds (two minutes).</span></span>|  
|`enableDnsRoundRobin`|<span data-ttu-id="738ea-120">Gibt an, ob DNS-Auflösungen von Hostnamen mit mehreren IP-Adressen (Internet Protocol) alle Adressen oder nur den ersten zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="738ea-120">Specifies whether DNS resolutions of host names with multiple Internet Protocol (IP) addresses return all the addresses, or just the first one.</span></span> <span data-ttu-id="738ea-121">Der Standardwert ist `false`sein.</span><span class="sxs-lookup"><span data-stu-id="738ea-121">The default value is `false`.</span></span>|  
|`encryptionPolicy`|<span data-ttu-id="738ea-122">Gibt die Verschlüsselungs Richtlinie an, die auf eine SSL/TLS-Sitzung auf einer <xref:System.Net.ServicePointManager>-Instanz angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="738ea-122">Specifies the encryption policy applied to an SSL/TLS session on a <xref:System.Net.ServicePointManager> instance.</span></span> <span data-ttu-id="738ea-123">Die möglichen Werte entsprechen den Werten für die <xref:System.Net.Security.EncryptionPolicy>-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="738ea-123">The possible values are equivalent to the values for the <xref:System.Net.Security.EncryptionPolicy> enumeration.</span></span> <span data-ttu-id="738ea-124">Die Verwendung von <xref:System.Security.Authentication.CipherAlgorithmType.Null> ist erforderlich, wenn die Verschlüsselungs Richtlinie auf `NoEncryption`festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="738ea-124">The use of <xref:System.Security.Authentication.CipherAlgorithmType.Null> is required when the encryption policy is set to `NoEncryption`.</span></span> <span data-ttu-id="738ea-125">Der Standardwert ist `RequireEncryption`sein.</span><span class="sxs-lookup"><span data-stu-id="738ea-125">The default value is `RequireEncryption`.</span></span>|  
|`expect100Continue`|<span data-ttu-id="738ea-126">Gibt an, ob Post-Methoden erwarten, dass vom Server eine `100-continue`-Antwort empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="738ea-126">Specifies whether POST methods should expect to receive a `100-continue` response from the server.</span></span> <span data-ttu-id="738ea-127">Der Standardwert ist `true`sein.</span><span class="sxs-lookup"><span data-stu-id="738ea-127">The default value is `true`.</span></span>|  
|`useNagleAlgorithm`|<span data-ttu-id="738ea-128">Gibt an, ob vom Dienst Punkt-Manager gesteuerte Verbindungen den Nagle-Algorithmus verwenden.</span><span class="sxs-lookup"><span data-stu-id="738ea-128">Specifies whether connections controlled by the service point manager use the Nagle algorithm.</span></span> <span data-ttu-id="738ea-129">Der Standardwert ist `true`sein.</span><span class="sxs-lookup"><span data-stu-id="738ea-129">The default value is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="738ea-130">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="738ea-130">Child Elements</span></span>  
 <span data-ttu-id="738ea-131">Keine</span><span class="sxs-lookup"><span data-stu-id="738ea-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="738ea-132">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="738ea-132">Parent Elements</span></span>  
  
|<span data-ttu-id="738ea-133">**Element**</span><span class="sxs-lookup"><span data-stu-id="738ea-133">**Element**</span></span>|<span data-ttu-id="738ea-134">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="738ea-134">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="738ea-135">Einstellungen</span><span class="sxs-lookup"><span data-stu-id="738ea-135">Settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="738ea-136">Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="738ea-136">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="738ea-137">Hinweise</span><span class="sxs-lookup"><span data-stu-id="738ea-137">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="738ea-138">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="738ea-138">Configuration Files</span></span>  
 <span data-ttu-id="738ea-139">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="738ea-139">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="738ea-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="738ea-140">See also</span></span>

- <xref:System.Net.ServicePointManager>
- <xref:System.Net.Security.EncryptionPolicy>
- [<span data-ttu-id="738ea-141">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="738ea-141">Network Settings Schema</span></span>](index.md)
