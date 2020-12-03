---
title: 'Breaking Change: TLS-Standardverschlüsselungssuites für .NET unter Linux'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, durch den .NET unter Linux jetzt bei der Verwendung von TLS/SSL die OpenSSL-Konfiguration für Standard-Cipher-Suites berücksichtigt.
ms.date: 10/16/2020
ms.openlocfilehash: f1c23517161ac213a9cd7cf6e7da8eebeb91583b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759188"
---
# <a name="default-tls-cipher-suites-for-net-on-linux"></a><span data-ttu-id="1a268-103">TLS-Standardverschlüsselungssuites für .NET unter Linux</span><span class="sxs-lookup"><span data-stu-id="1a268-103">Default TLS cipher suites for .NET on Linux</span></span>

<span data-ttu-id="1a268-104">.NET unter Linux akzeptiert jetzt die OpenSSL-Konfiguration für Standardverschlüsselungssuites bei der Verwendung von TLS/SSL über die Klasse <xref:System.Net.Security.SslStream> oder Vorgänge auf höherer Ebene, z. B. HTTP über die Klasse <xref:System.Net.Http.HttpClient>.</span><span class="sxs-lookup"><span data-stu-id="1a268-104">.NET, on Linux, now respects the OpenSSL configuration for default cipher suites when doing TLS/SSL via the <xref:System.Net.Security.SslStream> class or higher-level operations, such as HTTPS via the <xref:System.Net.Http.HttpClient> class.</span></span> <span data-ttu-id="1a268-105">Wenn keine Standardverschlüsselungssuites explizit konfiguriert werden, verwendet .NET unter Linux eine stark eingeschränkte Liste mit zulässigen Verschlüsselungssuites.</span><span class="sxs-lookup"><span data-stu-id="1a268-105">When default cipher suites aren't explicitly configured, .NET on Linux uses a tightly restricted list of permitted cipher suites.</span></span>

## <a name="change-description"></a><span data-ttu-id="1a268-106">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="1a268-106">Change description</span></span>

<span data-ttu-id="1a268-107">In früheren .NET-Versionen akzeptiert .NET die Systemkonfiguration für Standardverschlüsselungssuites nicht.</span><span class="sxs-lookup"><span data-stu-id="1a268-107">In previous .NET versions, .NET does not respect system configuration for default cipher suites.</span></span> <span data-ttu-id="1a268-108">Die Liste der Standardverschlüsselungssuites für .NET unter Linux umfasst wenige Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="1a268-108">The default cipher suite list for .NET on Linux is very permissive.</span></span>

<span data-ttu-id="1a268-109">Ab .NET 5.0 akzeptiert .NET unter Linux die OpenSSL-Konfiguration für Standardverschlüsselungssuites, wenn diese in *openssl.cnf* angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="1a268-109">Starting in .NET 5.0, .NET on Linux respects the OpenSSL configuration for default cipher suites when it's specified in *openssl.cnf*.</span></span> <span data-ttu-id="1a268-110">Wenn keine Verschlüsselungssuites explizit konfiguriert sind, lauten die einzigen zulässigen Verschlüsselungssuites wie folgt:</span><span class="sxs-lookup"><span data-stu-id="1a268-110">When cipher suites aren't explicitly configured, the only permitted cipher suites are as follows:</span></span>

- <span data-ttu-id="1a268-111">TLS 1.3-Verschlüsselungssuites</span><span class="sxs-lookup"><span data-stu-id="1a268-111">TLS 1.3 cipher suites</span></span>
- <span data-ttu-id="1a268-112">TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384</span><span class="sxs-lookup"><span data-stu-id="1a268-112">TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384</span></span>
- <span data-ttu-id="1a268-113">TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256</span><span class="sxs-lookup"><span data-stu-id="1a268-113">TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256</span></span>
- <span data-ttu-id="1a268-114">TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384</span><span class="sxs-lookup"><span data-stu-id="1a268-114">TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384</span></span>
- <span data-ttu-id="1a268-115">TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256</span><span class="sxs-lookup"><span data-stu-id="1a268-115">TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256</span></span>
- <span data-ttu-id="1a268-116">TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA384</span><span class="sxs-lookup"><span data-stu-id="1a268-116">TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA384</span></span>
- <span data-ttu-id="1a268-117">TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256</span><span class="sxs-lookup"><span data-stu-id="1a268-117">TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256</span></span>
- <span data-ttu-id="1a268-118">TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384</span><span class="sxs-lookup"><span data-stu-id="1a268-118">TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384</span></span>
- <span data-ttu-id="1a268-119">TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256</span><span class="sxs-lookup"><span data-stu-id="1a268-119">TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256</span></span>

<span data-ttu-id="1a268-120">Da dieser Fallbackstandard keine Verschlüsselungssuites enthält, die mit TLS 1.0 oder TLS 1.1 kompatibel sind, werden diese älteren Protokollversionen standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="1a268-120">Since this fallback default doesn't include any cipher suites that are compatible with TLS 1.0 or TLS 1.1, these older protocol versions are effectively disabled by default.</span></span>

<span data-ttu-id="1a268-121">Das Bereitstellen eines CipherSuitePolicy-Werts für SslStream für eine bestimmte Sitzung ersetzt weiterhin den Inhalt der Konfigurationsdatei und/oder den .NET-Fallbackstandard.</span><span class="sxs-lookup"><span data-stu-id="1a268-121">Supplying a CipherSuitePolicy value to SslStream for a specific session will still replace the configuration file content and/or .NET fallback default.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="1a268-122">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="1a268-122">Reason for change</span></span>

<span data-ttu-id="1a268-123">Benutzer, die .NET unter Linux ausführen, haben darum gebeten, dass die Standardkonfiguration für <xref:System.Net.Security.SslStream> so geändert werden muss, dass sie eine zuverlässige Bewertung der Sicherheit von Bewertungstools von Drittanbietern bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="1a268-123">Users running .NET on Linux requested that the default configuration for <xref:System.Net.Security.SslStream> be changed to one that provided a high security rating from third-party assessment tools.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="1a268-124">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="1a268-124">Version introduced</span></span>

<span data-ttu-id="1a268-125">5.0</span><span class="sxs-lookup"><span data-stu-id="1a268-125">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="1a268-126">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="1a268-126">Recommended action</span></span>

<span data-ttu-id="1a268-127">Die neuen Standardeinstellungen funktionieren sehr wahrscheinlich bei der Kommunikation mit modernen Clients oder Servern.</span><span class="sxs-lookup"><span data-stu-id="1a268-127">The new defaults are likely to work when communicating with modern clients or servers.</span></span> <span data-ttu-id="1a268-128">Wenn Sie die Liste der Standardverschlüsselungssuites erweitern müssen, damit Legacyclients akzeptiert (oder Legacyserver kontaktiert) werden, geben Sie entweder einen `CipherSuitePolicy`-Wert an, oder ändern Sie die OpenSSL-Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="1a268-128">If you need to expand the default cipher suite list to accept legacy clients (or to contact legacy servers), either specify a `CipherSuitePolicy` value or change the OpenSSL configuration file.</span></span> <span data-ttu-id="1a268-129">Bei vielen Linux-Distributionen befindet sich die OpenSSL-Konfigurationsdatei unter */etc/ssl/openssl.cnf*.</span><span class="sxs-lookup"><span data-stu-id="1a268-129">On many Linux distributions, the OpenSSL configuration file is at */etc/ssl/openssl.cnf*.</span></span>

<span data-ttu-id="1a268-130">Diese *openssl.cnf*-Beispieldatei stellt eine Basisdatei dar, die der Richtlinie für Standardverschlüsselungssuites für .NET 5.0 und höher unter Linux entspricht.</span><span class="sxs-lookup"><span data-stu-id="1a268-130">This sample *openssl.cnf* file is a minimal file that's equivalent to the default cipher suites policy for .NET 5.0 and later on Linux.</span></span> <span data-ttu-id="1a268-131">Anstatt die Systemdatei zu ersetzen, sollten Sie diese Konzepte mit der Datei zusammenführen, die auf Ihrem System vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="1a268-131">Instead of replacing the system file, merge these concepts with the file that's present on your system.</span></span>

```ini
openssl_conf = default_conf

[default_conf]
ssl_conf = ssl_sect

[ssl_sect]
system_default = system_default_sect

[system_default_sect]
CipherString = ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-RSA-AES256-GCM-SHA384:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-SHA384:ECDHE-ECDSA-AES128-SHA256:ECDHE-RSA-AES256-SHA384:ECDHE-RSA-AES128-SHA256
```

<span data-ttu-id="1a268-132">In den Red Hat Enterprise Linux-, CentOS- und Fedora-Distributionen werden .NET-Anwendungen standardmäßig auf die Verschlüsselungssuites beschränkt, die von den systemweiten Kryptografierichtlinien zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="1a268-132">On the Red Hat Enterprise Linux, CentOS, and Fedora distributions, .NET applications default to the cipher suites permitted by the system-wide cryptographic policies.</span></span> <span data-ttu-id="1a268-133">Verwenden Sie für diese Distributionen die Kryptografierichtlinienkonfiguration anstelle von *openssl.cnf*.</span><span class="sxs-lookup"><span data-stu-id="1a268-133">On these distributions, use the crypto-policies configuration instead of *openssl.cnf*.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="1a268-134">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="1a268-134">Affected APIs</span></span>

<span data-ttu-id="1a268-135">Nicht über eine API-Analyse erkennbar</span><span class="sxs-lookup"><span data-stu-id="1a268-135">Not detectible via API analysis.</span></span>

<!--

### Affected APIs

- Not detectible via API analysis.

### Category

- Cryptography
- Security

-->
