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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "74089130"
---
# <a name="servicepointmanager-element-network-settings"></a><span data-ttu-id="d6884-102">\<servicePointManager>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="d6884-102">\<servicePointManager> Element (Network Settings)</span></span>
<span data-ttu-id="d6884-103">Konfiguriert Verbindungen mit Netzwerkressourcen.</span><span class="sxs-lookup"><span data-stu-id="d6884-103">Configures connections to network resources.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<servicePointManager>**

## <a name="syntax"></a><span data-ttu-id="d6884-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d6884-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d6884-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d6884-105">Attributes and Elements</span></span>  
 <span data-ttu-id="d6884-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d6884-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d6884-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="d6884-107">Attributes</span></span>  
  
|<span data-ttu-id="d6884-108">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="d6884-108">**Attribute**</span></span>|<span data-ttu-id="d6884-109">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="d6884-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`checkCertificateName`|<span data-ttu-id="d6884-110">Gibt an, ob das System überprüfen soll, ob der Name des Zertifikats mit dem Server Hostnamen übereinstimmt, bevor das Zertifikat verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d6884-110">Specifies whether the system should verify that the name on the certificate matches the server host name before using the certificate.</span></span> <span data-ttu-id="d6884-111">Der Standardwert ist `true`.</span><span class="sxs-lookup"><span data-stu-id="d6884-111">The default value is `true`.</span></span>|  
|`checkCertificateRevocationList`|<span data-ttu-id="d6884-112">Gibt an, ob das System vor der Verwendung des Zertifikats überprüfen soll, ob das Zertifikat widerrufen wurde.</span><span class="sxs-lookup"><span data-stu-id="d6884-112">Specifies whether the system should check whether the certificate has been revoked before using the certificate.</span></span> <span data-ttu-id="d6884-113">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="d6884-113">The default value is `false`.</span></span>|  
|`dnsRefreshTimeout`|<span data-ttu-id="d6884-114">Gibt an, wie lange die Auflösung von Domain Name Service (DNS) in Verbindung mit der Option "DNS Round Robin" in Millisekunden zwischengespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="d6884-114">Specifies how long Domain Name Service (DNS) resolutions are cached in conjunction with the DNS Round Robin option, in milliseconds.</span></span> <span data-ttu-id="d6884-115">Der Standardwert ist 120.000 Millisekunden (zwei Minuten).</span><span class="sxs-lookup"><span data-stu-id="d6884-115">The default value is 120,000 milliseconds (two minutes).</span></span>|  
|`enableDnsRoundRobin`|<span data-ttu-id="d6884-116">Gibt an, ob DNS-Auflösungen von Hostnamen mit mehreren IP-Adressen (Internet Protocol) alle Adressen oder nur den ersten zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="d6884-116">Specifies whether DNS resolutions of host names with multiple Internet Protocol (IP) addresses return all the addresses, or just the first one.</span></span> <span data-ttu-id="d6884-117">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="d6884-117">The default value is `false`.</span></span>|  
|`encryptionPolicy`|<span data-ttu-id="d6884-118">Gibt die Verschlüsselungs Richtlinie an, die auf eine SSL/TLS-Sitzung auf einer-Instanz angewendet wird <xref:System.Net.ServicePointManager> .</span><span class="sxs-lookup"><span data-stu-id="d6884-118">Specifies the encryption policy applied to an SSL/TLS session on a <xref:System.Net.ServicePointManager> instance.</span></span> <span data-ttu-id="d6884-119">Die möglichen Werte entsprechen den Werten für die- <xref:System.Net.Security.EncryptionPolicy> Enumeration.</span><span class="sxs-lookup"><span data-stu-id="d6884-119">The possible values are equivalent to the values for the <xref:System.Net.Security.EncryptionPolicy> enumeration.</span></span> <span data-ttu-id="d6884-120"><xref:System.Security.Authentication.CipherAlgorithmType.Null>Wenn die Verschlüsselungs Richtlinie auf festgelegt ist, ist die Verwendung von erforderlich `NoEncryption` .</span><span class="sxs-lookup"><span data-stu-id="d6884-120">The use of <xref:System.Security.Authentication.CipherAlgorithmType.Null> is required when the encryption policy is set to `NoEncryption`.</span></span> <span data-ttu-id="d6884-121">Der Standardwert ist `RequireEncryption`.</span><span class="sxs-lookup"><span data-stu-id="d6884-121">The default value is `RequireEncryption`.</span></span>|  
|`expect100Continue`|<span data-ttu-id="d6884-122">Gibt an, ob Post-Methoden erwarten, dass eine `100-continue` Antwort vom Server empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="d6884-122">Specifies whether POST methods should expect to receive a `100-continue` response from the server.</span></span> <span data-ttu-id="d6884-123">Der Standardwert ist `true`.</span><span class="sxs-lookup"><span data-stu-id="d6884-123">The default value is `true`.</span></span>|  
|`useNagleAlgorithm`|<span data-ttu-id="d6884-124">Gibt an, ob vom Dienst Punkt-Manager gesteuerte Verbindungen den Nagle-Algorithmus verwenden.</span><span class="sxs-lookup"><span data-stu-id="d6884-124">Specifies whether connections controlled by the service point manager use the Nagle algorithm.</span></span> <span data-ttu-id="d6884-125">Der Standardwert ist `true`.</span><span class="sxs-lookup"><span data-stu-id="d6884-125">The default value is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d6884-126">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d6884-126">Child Elements</span></span>  
 <span data-ttu-id="d6884-127">Keine</span><span class="sxs-lookup"><span data-stu-id="d6884-127">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d6884-128">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d6884-128">Parent Elements</span></span>  
  
|<span data-ttu-id="d6884-129">**Element**</span><span class="sxs-lookup"><span data-stu-id="d6884-129">**Element**</span></span>|<span data-ttu-id="d6884-130">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="d6884-130">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d6884-131">Einstellungen</span><span class="sxs-lookup"><span data-stu-id="d6884-131">Settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="d6884-132">Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="d6884-132">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6884-133">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="d6884-133">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="d6884-134">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="d6884-134">Configuration Files</span></span>  
 <span data-ttu-id="d6884-135">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d6884-135">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6884-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d6884-136">See also</span></span>

- <xref:System.Net.ServicePointManager>
- <xref:System.Net.Security.EncryptionPolicy>
- [<span data-ttu-id="d6884-137">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="d6884-137">Network Settings Schema</span></span>](index.md)
