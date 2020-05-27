---
ms.openlocfilehash: 3c6142fd536bad5676f02570fecd4eb0605db829
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83720972"
---
### <a name="begin-trusted-certificate-syntax-no-longer-supported-for-root-certificates-on-linux"></a><span data-ttu-id="f31e3-101">„BEGIN TRUSTED CERTIFICATE“-Syntax wird nicht mehr für Stammzertifikate unter Linux unterstützt</span><span class="sxs-lookup"><span data-stu-id="f31e3-101">"BEGIN TRUSTED CERTIFICATE" syntax no longer supported for root certificates on Linux</span></span>

<span data-ttu-id="f31e3-102">Stammzertifikate können unter Linux und anderen UNIX-ähnlichen Betriebssystemen (jedoch nicht macOS) in zwei Formen dargestellt werden: als Standard-PEM-Header `BEGIN CERTIFICATE` oder als OpenSSL-spezifischen PEM-Header `BEGIN TRUSTED CERTIFICATE`.</span><span class="sxs-lookup"><span data-stu-id="f31e3-102">Root certificates on Linux and other Unix-like systems (but not macOS) can be presented in two forms: the standard `BEGIN CERTIFICATE` PEM header, and the OpenSSL-specific `BEGIN TRUSTED CERTIFICATE` PEM header.</span></span> <span data-ttu-id="f31e3-103">Die letztere Syntax ermöglicht eine zusätzliche Konfiguration, die Kompatibilitätsprobleme mit der <xref:System.Security.Cryptography.X509Certificates.X509Chain?displayProperty=fullName>-Klasse von .NET Core verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="f31e3-103">The latter syntax allows for additional configuration that has caused compatibility issues with .NET Core's <xref:System.Security.Cryptography.X509Certificates.X509Chain?displayProperty=fullName> class.</span></span> <span data-ttu-id="f31e3-104">`BEGIN TRUSTED CERTIFICATE`-Stammzertifikatinhalte werden ab .NET Core 3.0 nicht mehr von der Ketten-Engine geladen.</span><span class="sxs-lookup"><span data-stu-id="f31e3-104">`BEGIN TRUSTED CERTIFICATE` root certificate contents are no longer loaded by the chain engine starting in .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="f31e3-105">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="f31e3-105">Change description</span></span>

<span data-ttu-id="f31e3-106">Zuvor wurden sowohl die `BEGIN CERTIFICATE`- als auch die `BEGIN TRUSTED CERTIFICATE`-Syntax verwendet, um die Vertrauensliste des Stammzertifikats auszufüllen.</span><span class="sxs-lookup"><span data-stu-id="f31e3-106">Previously, both the `BEGIN CERTIFICATE` and `BEGIN TRUSTED CERTIFICATE` syntaxes were used to populate the root trust list.</span></span> <span data-ttu-id="f31e3-107">Wenn die `BEGIN TRUSTED CERTIFICATE`-Syntax verwendet wurde und zusätzliche Optionen in der Datei angegeben wurden, hat <xref:System.Security.Cryptography.X509Certificates.X509Chain> möglicherweise gemeldet, dass die Vertrauenskette explizit nicht zulässig war (<xref:System.Security.Cryptography.X509Certificates.X509ChainStatusFlags.ExplicitDistrust?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="f31e3-107">If the `BEGIN TRUSTED CERTIFICATE` syntax was used and additional options were specified in the file, <xref:System.Security.Cryptography.X509Certificates.X509Chain> may have reported that the chain trust was explicitly disallowed (<xref:System.Security.Cryptography.X509Certificates.X509ChainStatusFlags.ExplicitDistrust?displayProperty=nameWithType>).</span></span> <span data-ttu-id="f31e3-108">Wenn das Zertifikat jedoch auch mit der `BEGIN CERTIFICATE`-Syntax in einer zuvor geladenen Datei angegeben wurde, war die Vertrauenskette zulässig.</span><span class="sxs-lookup"><span data-stu-id="f31e3-108">However, if the certificate was also specified with the `BEGIN CERTIFICATE` syntax in a previously loaded file, the chain trust was allowed.</span></span>

<span data-ttu-id="f31e3-109">Ab .NET Core 3.0 werden `BEGIN TRUSTED CERTIFICATE`-Inhalte nicht mehr gelesen.</span><span class="sxs-lookup"><span data-stu-id="f31e3-109">Starting in .NET Core 3.0, `BEGIN TRUSTED CERTIFICATE` contents are no longer read.</span></span> <span data-ttu-id="f31e3-110">Wenn das Zertifikat nicht auch über eine Standardsyntax `BEGIN CERTIFICATE` angegeben wird, meldet <xref:System.Security.Cryptography.X509Certificates.X509Chain>, dass der Stamm nicht vertrauenswürdig ist (<xref:System.Security.Cryptography.X509Certificates.X509ChainStatusFlags.UntrustedRoot?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="f31e3-110">If the certificate is not also specified via a standard `BEGIN CERTIFICATE` syntax, the <xref:System.Security.Cryptography.X509Certificates.X509Chain> reports that the root is not trusted (<xref:System.Security.Cryptography.X509Certificates.X509ChainStatusFlags.UntrustedRoot?displayProperty=nameWithType>).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f31e3-111">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="f31e3-111">Version introduced</span></span>

<span data-ttu-id="f31e3-112">3.0</span><span class="sxs-lookup"><span data-stu-id="f31e3-112">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f31e3-113">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="f31e3-113">Recommended action</span></span>

<span data-ttu-id="f31e3-114">Die meisten Anwendungen sind von dieser Änderung nicht betroffen. Bei Anwendungen, denen aufgrund von Berechtigungsproblemen nicht beide Quellen des Stammzertifikats angezeigt werden, treten nach dem Upgrade möglicherweise unerwartete `UntrustedRoot`-Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="f31e3-114">Most applications are unaffected by this change, but applications that cannot see both root certificate sources because of permissions problems may experience unexpected `UntrustedRoot` errors after upgrading.</span></span>

<span data-ttu-id="f31e3-115">Viele Linux-Distributionen schreiben Stammzertifikate in zwei Speicherorte: in ein Verzeichnis mit einem einzigen Zertifikat pro Datei und in eine Verkettung mit einer Datei.</span><span class="sxs-lookup"><span data-stu-id="f31e3-115">Many Linux distributions (or distros) write root certificates into two locations: a one-certificate-per-file directory, and a one-file concatenation.</span></span> <span data-ttu-id="f31e3-116">Bei manchen Distributionen verwendet das Verzeichnis mit einem einzigen Zertifikat pro Datei die `BEGIN TRUSTED CERTIFICATE`-Syntax, während die Dateiverkettung die Standardsyntax `BEGIN CERTIFICATE` verwendet.</span><span class="sxs-lookup"><span data-stu-id="f31e3-116">On some distros, the one-certificate-per-file directory uses the `BEGIN TRUSTED CERTIFICATE` syntax while the file concatenation uses the standard `BEGIN CERTIFICATE` syntax.</span></span> <span data-ttu-id="f31e3-117">Stellen Sie sicher, dass alle benutzerdefinierten Stammzertifikate an mindestens einem dieser Speicherorte als `BEGIN CERTIFICATE` hinzugefügt werden und dass beide Speicherorte von Ihrer Anwendung gelesen werden können.</span><span class="sxs-lookup"><span data-stu-id="f31e3-117">Ensure that any custom root certificates are added as `BEGIN CERTIFICATE` in at least one of these locations, and that both locations can be read by your application.</span></span>

<span data-ttu-id="f31e3-118">Das übliche Verzeichnis ist */etc/ssl/certs/* , und die übliche verkettete Datei ist */etc/ssl/cert.pem*.</span><span class="sxs-lookup"><span data-stu-id="f31e3-118">The typical directory is */etc/ssl/certs/* and the typical concatenated file is */etc/ssl/cert.pem*.</span></span> <span data-ttu-id="f31e3-119">Verwenden Sie den Befehl `openssl version -d`, um den plattformspezifischen Stamm zu ermitteln, der sich von */etc/ssl/* unterscheiden kann.</span><span class="sxs-lookup"><span data-stu-id="f31e3-119">Use the command `openssl version -d` to determine the platform-specific root, which may differ from */etc/ssl/*.</span></span> <span data-ttu-id="f31e3-120">Unter Ubuntu 18.04 ist das Verzeichnis beispielsweise */usr/lib/ssl/certs/* und die Datei */usr/lib/ssl/cert.pem*.</span><span class="sxs-lookup"><span data-stu-id="f31e3-120">For example, on Ubuntu 18.04, the directory is */usr/lib/ssl/certs/* and the file is */usr/lib/ssl/cert.pem*.</span></span> <span data-ttu-id="f31e3-121">*/usr/lib/ssl/certs/* ist jedoch eine symbolische Verknüpfung mit */etc/ssl/certs/* , und */usr/lib/ssl/cert.pem* ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="f31e3-121">However, */usr/lib/ssl/certs/* is a symlink to */etc/ssl/certs/* and */usr/lib/ssl/cert.pem* does not exist.</span></span>

```bash
$ openssl version -d
OPENSSLDIR: "/usr/lib/ssl"
$ ls -al /usr/lib/ssl
total 12
drwxr-xr-x  3 root root 4096 Dec 12 17:10 .
drwxr-xr-x 73 root root 4096 Feb 20 15:18 ..
lrwxrwxrwx  1 root root   14 Mar 27  2018 certs -> /etc/ssl/certs
drwxr-xr-x  2 root root 4096 Dec 12 17:10 misc
lrwxrwxrwx  1 root root   20 Nov 12 16:58 openssl.cnf -> /etc/ssl/openssl.cnf
lrwxrwxrwx  1 root root   16 Mar 27  2018 private -> /etc/ssl/private
```

#### <a name="category"></a><span data-ttu-id="f31e3-122">Kategorie</span><span class="sxs-lookup"><span data-stu-id="f31e3-122">Category</span></span>

<span data-ttu-id="f31e3-123">Kryptografie</span><span class="sxs-lookup"><span data-stu-id="f31e3-123">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f31e3-124">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="f31e3-124">Affected APIs</span></span>

- <xref:System.Security.Cryptography.X509Certificates.X509Chain?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Security.Cryptography.X509Certificates.X509Chain`

-->
