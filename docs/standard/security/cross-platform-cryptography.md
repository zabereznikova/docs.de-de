---
title: Plattformübergreifende Kryptografie in .net Core und .net 5
description: Erfahren Sie mehr über Kryptografiefunktionen auf von .NET unterstützten Plattformen.
ms.date: 06/19/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- cryptography, cross-platform
- encryption, cross-platform
ms.openlocfilehash: 61fd49e53761deac278b770003eb97241b6c2be9
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87557150"
---
# <a name="cross-platform-cryptography-in-net-core-and-net-5"></a>Plattformübergreifende Kryptografie in .net Core und .net 5

Kryptografische Vorgänge in .net Core und .net 5 werden von Betriebssystem Bibliotheken (OS) durchgeführt. Diese Abhängigkeit hat folgende Vorteile:

* .Net-apps profitieren von der Zuverlässigkeit des Betriebssystems. Die Sicherheit von Kryptografiebibliotheken vor Sicherheitsrisiken zu schützen, ist für Betriebssystemhersteller eine hohe Priorität. Zu diesem Zweck stellen Sie Updates bereit, die Systemadministratoren anwenden sollten.
* .Net-apps haben Zugriff auf FIPS-validierte Algorithmen, wenn die Betriebssystem Bibliotheken FIPS-validiert sind.

Die Abhängigkeit von Betriebssystem Bibliotheken bedeutet auch, dass .NET-Anwendungen nur Kryptografiefunktionen verwenden können, die vom Betriebssystem unterstützt werden. Obwohl alle Plattformen bestimmte Kern Features unterstützen, können einige Funktionen, die .NET unterstützt, auf manchen Plattformen nicht verwendet werden. In diesem Artikel werden die Features beschrieben, die auf den einzelnen Plattformen unterstützt werden.

In diesem Artikel wird davon ausgegangen, dass Sie mit der Kryptografie in .NET vertraut sind. Weitere Informationen finden Sie unter [.net-Kryptografiemodell](cryptography-model.md) und [.net-Kryptografiedienste](cryptographic-services.md).

## <a name="hash-algorithms"></a>Hashalgorithmen

Alle Hash Algorithmen und HMAC-Klassen (Hash-based Message Authentication), einschließlich der- `*Managed` Klassen, werden auf die Betriebssystem Bibliotheken zurück verschoben. Die verschiedenen Betriebssystem Bibliotheken unterscheiden sich in der Leistung, Sie sollten jedoch kompatibel sein.

## <a name="symmetric-encryption"></a>Symmetrische Verschlüsselung

Die zugrunde liegenden Chiffren und Verkettung werden von den Systembibliotheken durchgeführt, und alle werden von allen Plattformen unterstützt.

| Chiffre + Modus | Windows | Linux | macOS |
|---------------|---------|-------|-------|
| AES-CBC       | ✔️     | ✔️    | ✔️   |
| AES-ECB       | ✔️     | ✔️    | ✔️   |
| 3DES-CBC      | ✔️     | ✔️    | ✔️   |
| 3DES-ECB      | ✔️     | ✔️    | ✔️   |
| DES-CBC       | ✔️     | ✔️    | ✔️   |
| DES-ECB       | ✔️     | ✔️    | ✔️   |

## <a name="authenticated-encryption"></a>Authentifizierte Verschlüsselung

Die Unterstützung der authentifizierten Verschlüsselung (AE) wird für AES-CCM und AES-GCM über die <xref:System.Security.Cryptography.AesCcm?displayProperty=fullName> -und-Klassen bereitgestellt <xref:System.Security.Cryptography.AesGcm?displayProperty=fullName> .

Unter Windows und Linux werden die Implementierungen von AES-CCM und AES-GCM von den Betriebssystem Bibliotheken bereitgestellt.

### <a name="aes-ccm-and-aes-gcm-on-macos"></a>AES-CCM und AES-GCM unter macOS

Unter macOS unterstützen die Systembibliotheken AES-CCM oder AES-GCM nicht für Code von Drittanbietern, sodass die <xref:System.Security.Cryptography.AesCcm> -Klasse und die- <xref:System.Security.Cryptography.AesGcm> Klasse OpenSSL zur Unterstützung von verwenden. Benutzer unter macOS müssen eine passende Version von OpenSSL (libcrypto) abrufen, damit diese Typen funktionieren, und Sie müssen sich in einem Pfad befinden, von dem das System standardmäßig eine Bibliothek laden würde. Es wird empfohlen, OpenSSL von einem Paket-Manager wie Homebrew zu installieren.

Die `libcrypto.0.9.7.dylib` Bibliotheken und, die `libcrypto.0.9.8.dylib` in macOS enthalten sind, stammen aus früheren Versionen von OpenSSL und werden nicht verwendet. Die `libcrypto.35.dylib` `libcrypto.41.dylib` Bibliotheken, und werden `libcrypto.42.dylib` von libressl verwendet und werden nicht verwendet.

### <a name="aes-ccm-keys-nonces-and-tags"></a>AES-CCM-Schlüssel,-Nonces und-Tags

* Schlüsselgrößen

  AES-CCM funktioniert mit 128-, 192-und 256-Bit-Schlüsseln.

* Nonce-Größen

  Die <xref:System.Security.Cryptography.AesCcm> -Klasse unterstützt die Nonces 56, 64, 72, 80, 88, 96 und 104-Bit (7, 8, 9, 10, 11, 12 und 13 Bytes).

* Taggrößen

  Die- <xref:System.Security.Cryptography.AesCcm> Klasse unterstützt das Erstellen oder Verarbeiten der Tags 32, 48, 64, 80, 96, 112 und 128-Bit (4, 8, 10, 12, 14 und 16 Byte).

### <a name="aes-gcm-keys-nonces-and-tags"></a>AES-GCM-Schlüssel, Nonces und Tags

* Schlüsselgrößen

  AES-GCM funktioniert mit 128-, 192-und 256-Bit-Schlüsseln.

* Nonce-Größen

  Die <xref:System.Security.Cryptography.AesGcm> -Klasse unterstützt nur 96-Bit-Nonces (12 Bytes).

* Taggrößen

  Die- <xref:System.Security.Cryptography.AesGcm> Klasse unterstützt das Erstellen oder Verarbeiten der Tags 96, 104, 112, 120 und 128-Bit (12, 13, 14, 15 und 16 Byte).

## <a name="asymmetric-cryptography"></a>Asymmetrische Kryptografie

Dieser Abschnitt enthält die folgenden Unterabschnitte:

* [RSA](#rsa)
* [ECDsa](#ecdsa)
* [ECDH](#ecdh)
* [DSA](#dsa)

### <a name="rsa"></a>RSA

Die Schlüsselgenerierung von RSA (Rivest – Shamir – Adleman) wird von den Betriebssystem Bibliotheken durchgeführt und unterliegt den Größenbeschränkungen und Leistungsmerkmalen.

RSA-Schlüssel Vorgänge werden von den Betriebssystem Bibliotheken ausgeführt, und die Typen von Schlüsseln, die geladen werden können, unterliegen den Betriebssystemanforderungen.

.Net macht keine "Rohdaten" (nicht aufgefüllte) RSA-Vorgänge verfügbar.

Die Betriebssystem Bibliotheken werden zum Verschlüsseln und Entschlüsseln von Auffüll Zeichen verwendet. Nicht alle Plattformen unterstützen die gleichen Auffüll Optionen:

| Padding-Modus                          | Windows (CNG) | Linux (OpenSSL) | macOS | Windows (CAPI) |
|---------------------------------------|---------------|-----------------|-------|----------------|
| PKCS1-Verschlüsselung                      | ✔️           | ✔️              | ✔️   | ✔️             |
| OAEP-SHA-1                          | ✔️           | ✔️              | ✔️   | ✔️             |
| OAEP-SHA-2 (SHA256, SHA384, SHA512) | ✔️           | ✔️              | ✔️   | ❌             |
| PKCS1 Signature (MD5, SHA-1)          | ✔️           | ✔️              | ✔️   | ✔️             |
| PKCS1-Signatur (SHA-2)               | ✔️           | ✔️              | ✔️   | ⚠️\*           |
| PSS                                   | ✔️           | ✔️              | ✔️   | ❌             |

\*Windows CryptoAPI (CAPI) kann die PKCS1-Signatur mit einem SHA-2-Algorithmus unterstützen. Das einzelne RSA-Objekt kann jedoch in einen Kryptografiedienstanbieter (CSP) geladen werden, der diesen nicht unterstützt.

#### <a name="rsa-on-windows"></a>RSA unter Windows

* Windows CryptoAPI (CAPI) wird immer verwendet, wenn [`new RSACryptoServiceProvider()`](xref:System.Security.Cryptography.RSACryptoServiceProvider) verwendet wird.
* Windows Cryptography API Next Generation (CNG) wird immer verwendet, wenn [`new RSACng()`](xref:System.Security.Cryptography.RSACng) verwendet wird.
* Das von zurückgegebene Objekt <xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType> wird intern von Windows CNG untergebracht. Diese Verwendung von Windows CNG ist ein Implementierungsdetail und unterliegt Änderungen.
* Die- <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey%2A> Erweiterungsmethode für <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> gibt eine- <xref:System.Security.Cryptography.RSACng> Instanz zurück. Diese Verwendung von <xref:System.Security.Cryptography.RSACng> ist ein Implementierungsdetail und unterliegt Änderungen.
* Die- <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey%2A> Erweiterungsmethode für <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> bevorzugt eine- <xref:System.Security.Cryptography.RSACng> Instanz, aber wenn <xref:System.Security.Cryptography.RSACng> der Schlüssel nicht geöffnet werden kann, <xref:System.Security.Cryptography.RSACryptoServiceProvider> wird versucht. Der bevorzugte Anbieter ist ein Implementierungsdetail, der geändert werden kann.

#### <a name="rsa-native-interop"></a>Native RSA-Interop

.Net macht Typen verfügbar, damit Programme mit den vom .net-Kryptografiecode verwendeten Betriebssystem Bibliotheken interagieren können. Die beteiligten Typen übersetzen nicht zwischen Plattformen und sollten nur bei Bedarf direkt verwendet werden.

| type                                                         | Windows | Linux         | macOS         |
|--------------------------------------------------------------|---------|---------------|---------------|
| <xref:System.Security.Cryptography.RSACryptoServiceProvider> | ✔️     | ⚠️<sup>1</sup>| ⚠️<sup>1</sup> |
| <xref:System.Security.Cryptography.RSACng>                   | ✔️     | ❌            | ❌            |
| <xref:System.Security.Cryptography.RSAOpenSsl>               | ❌     | ✔️            | ⚠️<sup>2,2</sup> |

<sup>1</sup> unter macOS und Linux <xref:System.Security.Cryptography.RSACryptoServiceProvider> kann für die Kompatibilität mit vorhandenen Programmen verwendet werden. In diesem Fall löst jede Methode, die Betriebssystem-Interop erfordert, wie z. b. das Öffnen eines benannten Schlüssels, eine aus <xref:System.PlatformNotSupportedException> .

<sup>2</sup> unter macOS <xref:System.Security.Cryptography.RSAOpenSsl> funktioniert, wenn OpenSSL installiert ist und eine geeignete libcrypto-dylib über das Laden dynamischer Bibliotheken gefunden werden kann. Wenn eine entsprechende Bibliothek nicht gefunden werden kann, werden Ausnahmen ausgelöst.

### <a name="ecdsa"></a>ECDsa

ECDSA (Elliptic Curve Digital Signature Algorithmus) die Schlüsselgenerierung erfolgt durch die Betriebssystem Bibliotheken und unterliegt den Größenbeschränkungen und Leistungsmerkmalen.

ECDSA-Schlüssel Kurven werden von den Betriebssystem Bibliotheken definiert und unterliegen ihren Einschränkungen.

| Elliptische-Kurven-                     | Windows 10    | Windows 7-8,1 | Linux         | macOS         |
|------------------------------------|---------------|-----------------|---------------|---------------|
| NIST P-256 (secp256r1)             | ✔️           | ✔️              | ✔️           | ✔️            |
| NIST P-384 (secp384r1)             | ✔️           | ✔️              | ✔️           | ✔️            |
| NIST P-521 (secp521r1)             | ✔️           | ✔️              | ✔️           | ✔️            |
| Brainpool-Kurven (benannte Kurven) | ✔️           | ❌              | ⚠️<sup>1</sup>| ❌           |
| Andere benannte Kurven                 | ⚠️<sup>2,2</sup>| ❌             | ⚠️<sup>1</sup>| ❌           |
| Explizite Kurven                    | ✔️           | ❌              | ✔️           | ❌            |
| Als explizit exportieren oder importieren       | ✔️           | ❌<sup>€</sup>  | ✔️           | ❌<sup>€</sup>|

<sup>1</sup> Linux-Distributionen haben nicht alle Unterstützung für die gleichen benannten Kurven.

<sup>2</sup> die Unterstützung für benannte Kurven wurde Windows CNG in Windows 10 hinzugefügt. Weitere Informationen finden Sie unter [CNG mit dem Namen elliptische Kurven](https://msdn.microsoft.com/library/windows/desktop/mt632245(v=vs.85).aspx). Benannte Kurven sind in früheren Versionen von Windows nicht verfügbar, mit Ausnahme der drei Kurven in Windows 7.

<sup>3</sup> der Export mit expliziten Kurven Parametern erfordert die Unterstützung von Betriebssystem Bibliotheken, die unter macOS oder früheren Versionen von Windows nicht verfügbar ist.

#### <a name="ecdsa-native-interop"></a>Native ECDSA-Interop

.Net macht Typen verfügbar, damit Programme mit den vom .net-Kryptografiecode verwendeten Betriebssystem Bibliotheken interagieren können. Die beteiligten Typen übersetzen nicht zwischen Plattformen und sollten nur bei Bedarf direkt verwendet werden.

| type                                             | Windows | Linux | macOS |
|--------------------------------------------------|---------|-------|-------|
| <xref:System.Security.Cryptography.ECDsaCng>     | ✔️     | ❌    | ❌    |
| <xref:System.Security.Cryptography.ECDsaOpenSsl> | ❌     | ✔️    | ⚠️\*  |

\*Unter macOS <xref:System.Security.Cryptography.ECDsaOpenSsl> funktioniert, wenn OpenSSL im System installiert ist und eine geeignete libcrypto-dylib über das Laden dynamischer Bibliotheken gefunden werden kann. Wenn eine entsprechende Bibliothek nicht gefunden werden kann, werden Ausnahmen ausgelöst.

### <a name="ecdh"></a>ECDH

Die Schlüsselgenerierung von ECDH (Elliptic Curve Diffie-Hellman) erfolgt durch die Betriebssystem Bibliotheken und unterliegt den Größenbeschränkungen und Leistungsmerkmalen.

Die <xref:System.Security.Cryptography.ECDiffieHellman> Klasse gibt den "RAW"-Wert der ECDH-Berechnung nicht zurück. Alle zurückgegebenen Daten sind im Hinblick auf die Funktionen der Schlüssel Ableitung:

* Hash (Z)
* Hash (vorangesteht | | Z | | Anfügen
* HMAC (Key, Z)
* HMAC (Key, voranstellen | | Z | | Anfügen
* HMAC (z, z)
* HMAC (Z, voransetzen | | Z | | Anfügen
* Tls11Prf (Bezeichnung, Seed)

ECDH-Schlüssel Kurven werden von den Betriebssystem Bibliotheken definiert und unterliegen ihren Einschränkungen.

| Elliptische-Kurven-                     | Windows 10    | Windows 7-8,1 | Linux         | macOS         |
|------------------------------------|---------------|-----------------|---------------|---------------|
| NIST P-256 (secp256r1)             | ✔️           | ✔️              | ✔️           | ✔️            |
| NIST P-384 (secp384r1)             | ✔️           | ✔️              | ✔️           | ✔️            |
| NIST P-521 (secp521r1)             | ✔️           | ✔️              | ✔️           | ✔️            |
| Brainpool-Kurven (benannte Kurven) | ✔️           | ❌              | ⚠️<sup>1</sup>| ❌           |
| andere benannte Kurven                 | ⚠️<sup>2,2</sup>| ❌             | ⚠️<sup>1</sup>| ❌           |
| explizite Kurven                    | ✔️           | ❌              | ✔️           | ❌            |
| Als explizit exportieren oder importieren       | ✔️           | ❌<sup>€</sup>  | ✔️           | ❌<sup>€</sup>|

<sup>1</sup> Linux-Distributionen haben nicht alle Unterstützung für die gleichen benannten Kurven.

<sup>2</sup> die Unterstützung für benannte Kurven wurde Windows CNG in Windows 10 hinzugefügt. Weitere Informationen finden Sie unter [CNG mit dem Namen elliptische Kurven](https://msdn.microsoft.com/library/windows/desktop/mt632245(v=vs.85).aspx). Benannte Kurven sind in früheren Versionen von Windows nicht verfügbar, mit Ausnahme der drei Kurven in Windows 7.

<sup>3</sup> der Export mit expliziten Kurven Parametern erfordert die Unterstützung von Betriebssystem Bibliotheken, die unter macOS oder früheren Versionen von Windows nicht verfügbar ist.

#### <a name="ecdh-native-interop"></a>Native ECDH-Interop

.Net macht Typen verfügbar, damit Programme mit den von .NET verwendeten Betriebssystem Bibliotheken interagieren können. Die beteiligten Typen übersetzen nicht zwischen Plattformen und sollten nur bei Bedarf direkt verwendet werden.

| type                                                       | Windows | Linux | macOS |
|------------------------------------------------------------|---------|-------|-------|
| <xref:System.Security.Cryptography.ECDiffieHellmanCng>     | ✔️     | ❌    | ❌   |
| <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl> | ❌     | ✔️    | ⚠️\* |

\*Unter macOS <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl> funktioniert, wenn OpenSSL installiert ist und eine geeignete libcrypto-dylib über das Laden dynamischer Bibliotheken gefunden werden kann. Wenn eine entsprechende Bibliothek nicht gefunden werden kann, werden Ausnahmen ausgelöst.

### <a name="dsa"></a>DSA

Die Schlüsselgenerierung von DSA (Digital Signature Algorithmus) wird von den Systembibliotheken durchgeführt und unterliegt ihren Größenbeschränkungen und Leistungsmerkmalen.

| Funktion                      | Windows CNG | Linux | macOS         | Windows-CAPI |
|-------------------------------|-------------|-------|---------------|--------------|
| Schlüssel Erstellung (<= 1024 Bits)   | ✔️         | ✔️    | ❌            | ✔️           |
| Schlüssel Erstellung (> 1024 Bits)    | ✔️         | ✔️    | ❌            | ❌            |
| Laden von Schlüsseln (<= 1024 Bits)   | ✔️         | ✔️    | ✔️            | ✔️           |
| Laden von Schlüsseln (> 1024 Bits)    | ✔️         | ✔️    | ⚠️\*          | ❌            |
| Fi-186-2                    | ✔️         | ✔️    | ✔️            | ✔️           |
| "Fps 186-3" (SHA-2-Signaturen) | ✔️         | ✔️    | ❌            | ❌            |

\*macOS lädt DSA-Schlüssel, die größer als 1024 Bits sind, aber das Verhalten dieser Schlüssel ist nicht definiert. Sie Verhalten sich nicht gemäß "fps 186-3".

#### <a name="dsa-on-windows"></a>DSA unter Windows

* Windows CryptoAPI (CAPI) wird immer verwendet, wenn [`new DSACryptoServiceProvider()`](xref:System.Security.Cryptography.DSACryptoServiceProvider) verwendet wird.
* Windows Cryptography API Next Generation (CNG) wird immer verwendet, wenn [`new DSACng()`](xref:System.Security.Cryptography.DSACng) verwendet wird.
* Das von zurückgegebene Objekt <xref:System.Security.Cryptography.DSA.Create%2A?displayProperty=nameWithType> wird intern von Windows CNG untergebracht. Diese Verwendung von Windows CNG ist ein Implementierungsdetail und unterliegt Änderungen.
* Die- <xref:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPublicKey%2A> Erweiterungsmethode für <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> gibt eine- <xref:System.Security.Cryptography.DSACng> Instanz zurück. Diese Verwendung von <xref:System.Security.Cryptography.DSACng> ist ein Implementierungsdetail und unterliegt Änderungen.
* Die <xref:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPrivateKey%2A> Erweiterungsmethode für <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> bevorzugt eine- <xref:System.Security.Cryptography.DSACng> Instanz, wenn <xref:System.Security.Cryptography.DSACng> der Schlüssel jedoch nicht geöffnet werden kann, <xref:System.Security.Cryptography.DSACryptoServiceProvider> wird versucht.  Der bevorzugte Anbieter ist ein Implementierungsdetail, der geändert werden kann.

#### <a name="dsa-native-interop"></a>Native DSA-Interop

.Net macht Typen verfügbar, damit Programme mit den vom .net-Kryptografiecode verwendeten Betriebssystem Bibliotheken interagieren können. Die beteiligten Typen übersetzen nicht zwischen Plattformen und sollten nur bei Bedarf direkt verwendet werden.

| type                                                         | Windows | Linux         | macOS         |
|--------------------------------------------------------------|---------|---------------|---------------|
| <xref:System.Security.Cryptography.DSACryptoServiceProvider> | ✔️     | ⚠️<sup>1</sup> | ⚠️<sup>1</sup> |
| <xref:System.Security.Cryptography.DSACng>                   | ✔️     | ❌             | ❌            |
| <xref:System.Security.Cryptography.DSAOpenSsl>               | ❌      | ✔️            | ⚠️<sup>2,2</sup> |

<sup>1</sup> unter macOS und Linux <xref:System.Security.Cryptography.DSACryptoServiceProvider> kann für die Kompatibilität mit vorhandenen Programmen verwendet werden. In diesem Fall löst jede Methode, die System Interop erfordert, wie z. b. das Öffnen eines benannten Schlüssels, eine aus <xref:System.PlatformNotSupportedException> .

<sup>2</sup> unter macOS <xref:System.Security.Cryptography.DSAOpenSsl> funktioniert, wenn OpenSSL installiert ist und eine geeignete libcrypto-dylib über das Laden dynamischer Bibliotheken gefunden werden kann. Wenn eine entsprechende Bibliothek nicht gefunden werden kann, werden Ausnahmen ausgelöst.

## <a name="x509-certificates"></a>X.509-Zertifikate

Der Großteil der Unterstützung für X. 509-Zertifikate in .net stammt aus Betriebssystem Bibliotheken. Zum Laden eines Zertifikats in eine- <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> oder- <xref:System.Security.Cryptography.X509Certificates.X509Certificate> Instanz in .NET muss das Zertifikat von der zugrunde liegenden Betriebssystem Bibliothek geladen werden.

### <a name="read-a-pkcs12pfx"></a>Lesen eines PKCS12/PFX

| Szenario                                     | Windows | Linux | macOS |
|----------------------------------------------|---------|-------|-------|
| Empty                                        | ✔️     | ✔️    | ✔️   |
| Ein Zertifikat, kein privater Schlüssel              | ✔️     | ✔️    | ✔️   |
| Ein Zertifikat mit privatem Schlüssel            | ✔️     | ✔️    | ✔️   |
| Mehrere Zertifikate, keine privaten Schlüssel       | ✔️     | ✔️    | ✔️   |
| Mehrere Zertifikate, ein privater Schlüssel       | ✔️     | ✔️    | ✔️   |
| Mehrere Zertifikate, mehrere private Schlüssel | ✔️     | ⚠️\*  | ✔️   |

\*Verfügbar in .net 5 Preview Releases.

### <a name="write-a-pkcs12pfx"></a>PKCS12/PFX schreiben

| Szenario                                     | Windows | Linux | macOS |
|----------------------------------------------|---------|-------|-------|
| Empty                                        | ✔️     | ✔️    | ⚠️\* |
| Ein Zertifikat, kein privater Schlüssel              | ✔️     | ✔️    | ⚠️\* |
| Ein Zertifikat mit privatem Schlüssel            | ✔️     | ✔️    | ✔️   |
| Mehrere Zertifikate, keine privaten Schlüssel       | ✔️     | ✔️    | ⚠️\* |
| Mehrere Zertifikate, ein privater Schlüssel       | ✔️     | ✔️    | ✔️   |
| Mehrere Zertifikate, mehrere private Schlüssel | ✔️     | ⚠️\*  | ✔️   |
| Kurzlebiges laden                            | ✔️     | ✔️    | ⚠️\* |

\*Verfügbar in .net 5 Preview Releases.

macOS kann keine privaten Zertifikat Schlüssel ohne ein Keychain-Objekt laden, das auf den Datenträger geschrieben werden muss. Keychain werden automatisch für das Laden von PFX erstellt und gelöscht, wenn Sie nicht mehr verwendet werden. Da die <xref:System.Security.Cryptography.X509Certificates.X509KeyStorageFlags.EphemeralKeySet?displayProperty=nameWithType> Option bedeutet, dass der private Schlüssel nicht auf den Datenträger geschrieben werden soll, führt das bestätigen dieses Flags für macOS zu einer <xref:System.PlatformNotSupportedException> .

### <a name="write-a-pkcs7-certificate-collection"></a>Schreiben einer PKCS7-Zertifikat Sammlung

Sowohl Windows als auch Linux geben die-codierten PKCS7-BLOB-BLOB. macOS gibt unverschlüsselte PKCS7-blobdaten mit unbegrenzter Länge aus.

### <a name="x509store"></a>X509Store

Unter Windows ist die- <xref:System.Security.Cryptography.X509Certificates.X509Store> Klasse eine Darstellung der Windows-Zertifikat Speicher-APIs. Diese APIs funktionieren in .net Core und .net 5 genauso wie in .NET Framework.

Unter Linux ist die- <xref:System.Security.Cryptography.X509Certificates.X509Store> Klasse eine Projektion von Entscheidungen über die System Vertrauensstellung (schreibgeschützt), Entscheidungen über Benutzer Vertrauensstellungen (Lese-/Schreibzugriff) und Benutzerschlüssel Speicher (Lese-/Schreibzugriff).

Unter macOS ist die- <xref:System.Security.Cryptography.X509Certificates.X509Store> Klasse eine Projektion von systemvertrauensstellungs-Entscheidungen (schreibgeschützt), Entscheidungen über Benutzer Vertrauensstellungen (schreibgeschützt) und Benutzerschlüssel Speicher (Lese-/Schreibzugriff).

Die folgenden Tabellen zeigen, welche Szenarien auf den einzelnen Plattformen unterstützt werden. Bei nicht unterstützten Szenarien ( ❌ in den Tabellen) wird eine ausgelöst <xref:System.Security.Cryptography.CryptographicException> .

#### <a name="the-my-store"></a>Mein Speicher

| Szenario                                         | Windows | Linux | macOS |
|--------------------------------------------------|---------|-------|-------|
| Currentuser\my öffnen (schreibgeschützt)                   | ✔️     | ✔️    | ✔️   |
| Currentuser\my öffnen (Schreibvorgang)                  | ✔️     | ✔️    | ✔️   |
| Currentuser\my öffnen (existingonly)               | ✔️     | ⚠️    | ✔️   |
| Öffnen Sie LocalMachine\MY.                             | ✔️     | ❌    | ✔️   |

Unter Linux werden Speicher beim ersten Schreibvorgang erstellt, und standardmäßig sind keine Benutzerspeicher vorhanden, sodass das Öffnen `CurrentUser\My` mit `ExistingOnly` möglicherweise fehlschlägt.

Unter macOS ist der `CurrentUser\My` Speicher die standardmäßige Keychain des Benutzers, der `login.keychain` Standardmäßig ist. Der `LocalMachine\My` Speicher ist `System.keychain` .

#### <a name="the-root-store"></a>Der Stamm Speicher

| Szenario                              | Windows | Linux | macOS           |
|---------------------------------------|---------|-------|-----------------|
| Currentuser\root öffnen (schreibgeschützt)      | ✔️     | ✔️    | ✔️             |
| Currentuser\root öffnen (Schreibvorgang)     | ✔️     | ✔️    | ❌              |
| Currentuser\root öffnen (existingonly)  | ✔️     | ⚠️    | ✔️ (wenn schreibgeschützt) |
| Öffnen Sie LocalMachine\ROOT (schreibgeschützt).     | ✔️     | ✔️    | ✔️             |
| Öffnen Sie LocalMachine\ROOT (lesen).    | ✔️     | ❌    | ❌              |
| Öffnen Sie LocalMachine\ROOT (existingonly). | ✔️     | ⚠️    | ✔️ (wenn schreibgeschützt) |

Unter Linux ist der `LocalMachine\Root` Speicher eine Interpretation des Zertifizierungsstellen Pakets im Standardpfad für openssl.

Unter macOS ist der `CurrentUser\Root` Speicher eine Interpretation der `SecTrustSettings` Ergebnisse für die vertrauenswürdige Domäne des Benutzers. Der `LocalMachine\Root` Speicher ist eine Interpretation der `SecTrustSettings` Ergebnisse für die Domänen Admin und System Vertrauensstellung.

#### <a name="the-intermediate-store"></a>Der Zwischenspeicher

| Szenario                                      | Windows | Linux | macOS           |
|-----------------------------------------------|---------|-------|-----------------|
| Currentuser\intermediate öffnen (schreibgeschützt)      | ✔️     | ✔️    | ✔️             |
| Currentuser\intermediate öffnen (Schreibvorgang)     | ✔️     | ✔️    | ❌              |
| Currentuser\intermediate öffnen (existingonly)  | ✔️     | ⚠️    | ✔️ (wenn schreibgeschützt) |
| Öffnen Sie localmachine\intermediate (schreibgeschützt).     | ✔️     | ✔️    | ✔️             |
| Öffnen Sie localmachine\intermediate (Lesevorgang).    | ✔️     | ❌    | ❌              |
| Öffnen Sie localmachine\intermediate (existingonly). | ✔️     | ⚠️    | ✔️ (wenn schreibgeschützt) |

Unter Linux wird der `CurrentUser\Intermediate` Speicher als Cache verwendet, wenn zwischen Zertifizierungsstellen mithilfe ihrer Autorität für die Informations Zugriffsdaten in erfolgreichen X509Chain-Builds heruntergeladen werden. Der `LocalMachine\Intermediate` Speicher ist eine Interpretation des Zertifizierungsstellen Pakets im Standardpfad für openssl.

#### <a name="the-disallowed-store"></a>Der unzulässige Speicher

| Szenario                                    | Windows | Linux | macOS           |
|---------------------------------------------|---------|-------|-----------------|
| Currentuser\unallowed öffnen (schreibgeschützt)      | ✔️     | ⚠️    | ✔️             |
| Currentuser\unallowed öffnen (Lesevorgang)     | ✔️     | ⚠️    | ❌              |
| Currentuser\unallowed öffnen (existingonly)  | ✔️     | ⚠️    | ✔️ (wenn schreibgeschützt) |
| Öffnen Sie localmachine\unallowed (schreibgeschützt).     | ✔️     | ❌    | ✔️             |
| Öffnen Sie localmachine\unallowed (lesen).    | ✔️     | ❌    | ❌              |
| Öffnen Sie localmachine\unallowed (existingonly). | ✔️     | ❌    | ✔️ (wenn schreibgeschützt) |

Unter Linux wird der `Disallowed` Speicher bei der Ketten Bildung nicht verwendet, und der Versuch, diesem Inhalt hinzuzufügen, führt zu einer <xref:System.Security.Cryptography.CryptographicException> . Eine <xref:System.Security.Cryptography.CryptographicException> wird ausgelöst, wenn der Speicher geöffnet wird, `Disallowed` Wenn bereits Inhalte abgerufen wurden.

Unter macOS sind die Speicher "currentuser\unallowed" und "localmachine\unallowed" Interpretationen der entsprechenden sectrustsettings-Ergebnisse für Zertifikate, deren Vertrauenswürdigkeit auf festgelegt ist `Always Deny` .

#### <a name="nonexistent-store"></a>Nicht vorhandener Speicher

| Szenario                                         | Windows | Linux | macOS |
|--------------------------------------------------|---------|-------|-------|
| Nicht vorhandenen Speicher öffnen (existingonly)           | ❌     | ❌     | ❌    |
| Nicht existierenden CurrentUser-Speicher öffnen (Lesevorgang)  | ✔️     | ✔️     | ⚠️   |
| Öffnen Sie den nicht vorhandenen LocalMachine-Speicher (Lesevorgang). | ✔️     | ❌     | ❌    |

Unter macOS wird die Erstellung eines benutzerdefinierten Stores mit der X509Store-API nur für den Standort unterstützt `CurrentUser` . Es wird eine neue Keychain ohne Kennwort im Keychain-Verzeichnis des Benutzers erstellt (*~/Library/keychains*). Um eine Keychain mit einem Kennwort zu erstellen, kann ein P/-Aufruf für `SecKeychainCreate` verwendet werden. Entsprechend `SecKeychainOpen` könnte auch verwendet werden, um Keychain an verschiedenen Orten zu öffnen. Das resultierende `IntPtr` kann an weitergegeben werden, [`new X509Store(IntPtr)`](xref:System.Security.Cryptography.X509Certificates.X509Store.%23ctor(System.IntPtr)) um einen Lese-/Schreib-fähigen Speicher zu erhalten, der den Berechtigungen des aktuellen Benutzers unterliegt.

### <a name="x509chain"></a>X509Chain

macOS unterstützt keine Offline-CRL-Auslastung, daher `X509RevocationMode.Offline` wird als behandelt `X509RevocationMode.Online` .

macOS unterstützt kein vom Benutzer initiiertes Timeout bei der CRL (Zertifikats Sperr Liste)/OCSP (Online Certificate Status-Protokoll)/AIA (Autoritäts Informations Zugriff), das heruntergeladen wird, daher `X509ChainPolicy.UrlRetrievalTimeout` wird ignoriert.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

* [.Net-Kryptografiemodell](cryptography-model.md)
* [.Net-Kryptografiedienste](cryptographic-services.md)
* [Verwenden der Auffüllung für die Zeitsteuerung bei Sicherheitsrisiken mit symmetrischer Entschlüsselung im CBC-Modus](vulnerabilities-cbc-mode.md)
* [ASP.net Core Datenschutz](/aspnet/core/security/data-protection/introduction)
