---
ms.openlocfilehash: 3c6142fd536bad5676f02570fecd4eb0605db829
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83720972"
---
### <a name="begin-trusted-certificate-syntax-no-longer-supported-for-root-certificates-on-linux"></a>„BEGIN TRUSTED CERTIFICATE“-Syntax wird nicht mehr für Stammzertifikate unter Linux unterstützt

Stammzertifikate können unter Linux und anderen UNIX-ähnlichen Betriebssystemen (jedoch nicht macOS) in zwei Formen dargestellt werden: als Standard-PEM-Header `BEGIN CERTIFICATE` oder als OpenSSL-spezifischen PEM-Header `BEGIN TRUSTED CERTIFICATE`. Die letztere Syntax ermöglicht eine zusätzliche Konfiguration, die Kompatibilitätsprobleme mit der <xref:System.Security.Cryptography.X509Certificates.X509Chain?displayProperty=fullName>-Klasse von .NET Core verursacht hat. `BEGIN TRUSTED CERTIFICATE`-Stammzertifikatinhalte werden ab .NET Core 3.0 nicht mehr von der Ketten-Engine geladen.

#### <a name="change-description"></a>Änderungsbeschreibung

Zuvor wurden sowohl die `BEGIN CERTIFICATE`- als auch die `BEGIN TRUSTED CERTIFICATE`-Syntax verwendet, um die Vertrauensliste des Stammzertifikats auszufüllen. Wenn die `BEGIN TRUSTED CERTIFICATE`-Syntax verwendet wurde und zusätzliche Optionen in der Datei angegeben wurden, hat <xref:System.Security.Cryptography.X509Certificates.X509Chain> möglicherweise gemeldet, dass die Vertrauenskette explizit nicht zulässig war (<xref:System.Security.Cryptography.X509Certificates.X509ChainStatusFlags.ExplicitDistrust?displayProperty=nameWithType>). Wenn das Zertifikat jedoch auch mit der `BEGIN CERTIFICATE`-Syntax in einer zuvor geladenen Datei angegeben wurde, war die Vertrauenskette zulässig.

Ab .NET Core 3.0 werden `BEGIN TRUSTED CERTIFICATE`-Inhalte nicht mehr gelesen. Wenn das Zertifikat nicht auch über eine Standardsyntax `BEGIN CERTIFICATE` angegeben wird, meldet <xref:System.Security.Cryptography.X509Certificates.X509Chain>, dass der Stamm nicht vertrauenswürdig ist (<xref:System.Security.Cryptography.X509Certificates.X509ChainStatusFlags.UntrustedRoot?displayProperty=nameWithType>).

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="recommended-action"></a>Empfohlene Aktion

Die meisten Anwendungen sind von dieser Änderung nicht betroffen. Bei Anwendungen, denen aufgrund von Berechtigungsproblemen nicht beide Quellen des Stammzertifikats angezeigt werden, treten nach dem Upgrade möglicherweise unerwartete `UntrustedRoot`-Fehler auf.

Viele Linux-Distributionen schreiben Stammzertifikate in zwei Speicherorte: in ein Verzeichnis mit einem einzigen Zertifikat pro Datei und in eine Verkettung mit einer Datei. Bei manchen Distributionen verwendet das Verzeichnis mit einem einzigen Zertifikat pro Datei die `BEGIN TRUSTED CERTIFICATE`-Syntax, während die Dateiverkettung die Standardsyntax `BEGIN CERTIFICATE` verwendet. Stellen Sie sicher, dass alle benutzerdefinierten Stammzertifikate an mindestens einem dieser Speicherorte als `BEGIN CERTIFICATE` hinzugefügt werden und dass beide Speicherorte von Ihrer Anwendung gelesen werden können.

Das übliche Verzeichnis ist */etc/ssl/certs/* , und die übliche verkettete Datei ist */etc/ssl/cert.pem*. Verwenden Sie den Befehl `openssl version -d`, um den plattformspezifischen Stamm zu ermitteln, der sich von */etc/ssl/* unterscheiden kann. Unter Ubuntu 18.04 ist das Verzeichnis beispielsweise */usr/lib/ssl/certs/* und die Datei */usr/lib/ssl/cert.pem*. */usr/lib/ssl/certs/* ist jedoch eine symbolische Verknüpfung mit */etc/ssl/certs/* , und */usr/lib/ssl/cert.pem* ist nicht vorhanden.

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

#### <a name="category"></a>Kategorie

Kryptografie

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Security.Cryptography.X509Certificates.X509Chain?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Security.Cryptography.X509Certificates.X509Chain`

-->
