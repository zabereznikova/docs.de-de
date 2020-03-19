---
title: CBC-Entschlüsselungsschwachen
description: Erfahren Sie, wie Sie timing-Schwachstellen mit der symmetrischen Entschlüsselung im Cipher-Block-Chaining (CBC-Modus) mithilfe von Padding erkennen und verringern.
ms.date: 06/12/2018
author: blowdart
ms.openlocfilehash: 47520ea4c9c7d0ef4d79378c93c6ce1f2ba7dd6d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186097"
---
# <a name="timing-vulnerabilities-with-cbc-mode-symmetric-decryption-using-padding"></a>Verwenden der Auffüllung für die Zeitsteuerung bei Sicherheitsrisiken mit symmetrischer Entschlüsselung im CBC-Modus

Microsoft ist der Ansicht, dass es nicht mehr sicher ist, Daten zu entschlüsseln, die mit dem CBC-Modus (Cipher-Block-Chaining) verschlüsselt sind, wenn überprüfbare Auffüllungen angewendet wurden, ohne zuvor die Integrität des Verschlüsselungstextes zu gewährleisten, mit Ausnahme von sehr spezifischen Umständen. Dieses Urteil basiert auf derzeit bekannten kryptografischen Forschungen.

## <a name="introduction"></a>Einführung

Ein Auffüllungs-Orakelangriff ist eine Art von Angriff auf verschlüsselte Daten, die es dem Angreifer ermöglicht, den Inhalt der Daten zu entschlüsseln, ohne den Schlüssel zu kennen.

Ein Orakel bezieht sich auf ein "Tell", das einem Angreifer Informationen darüber gibt, ob die ausgeführte Aktion richtig ist oder nicht. Stellen Sie sich vor, Sie spielen ein Brett- oder Kartenspiel mit einem Kind. Wenn ihr Gesicht mit einem großen Lächeln aufleuchtet, weil sie denken, dass sie im Begriff sind, einen guten Zug zu machen, ist das ein Orakel. Sie als Gegner können dieses Orakel verwenden, um Ihren nächsten Zug entsprechend zu planen.

Padding ist ein spezifischer kryptografischer Begriff. Einige Chiffren, d. h. die Algorithmen, die zum Verschlüsseln Ihrer Daten verwendet werden, arbeiten an Datenblöcken, bei denen jeder Block eine feste Größe hat. Wenn die Zuschlüsseln der Daten nicht die richtige Größe zum Ausfüllen der Blöcke haben, werden die Daten aufgefüllt, bis dies der Grund ist. Viele Formen der Polsterung erfordern, dass Die polsterung immer vorhanden ist, auch wenn die ursprüngliche Eingabe die richtige Größe hatte. Dies ermöglicht es, die Polsterung immer sicher bei der Entschlüsselung entfernt werden.

Zusammengenommen zeigt eine Softwareimplementierung mit einem Auffüllungsorakel, ob entschlüsselte Daten über eine gültige Auffüllung verfügen. Das Orakel könnte etwas so Einfaches sein, wie die Rückgabe eines Werts, der "Ungültige Auffüllung" sagt, oder etwas Komplizierteres, wie eine messbar andere Zeit zu nehmen, um einen gültigen Block zu verarbeiten, im Gegensatz zu einem ungültigen Block.

Blockbasierte Verschlüsselungen haben eine andere Eigenschaft, den so genannten Modus, der die Beziehung der Daten im ersten Block zu den Daten im zweiten Block bestimmt usw. Einer der am häufigsten verwendeten Modi ist CBC. CBC führt einen anfänglichen zuzufälligen Block ein, der als Initialisierungsvektor (IV) bekannt ist, und kombiniert den vorherigen Block mit dem Ergebnis statischer Verschlüsselung, um ihn so zu machen, dass die Verschlüsselung derselben Nachricht mit demselben Schlüssel nicht immer die gleiche verschlüsselte Ausgabe erzeugt.

Ein Angreifer kann ein Auffüllungsorakel in Kombination mit der Struktur von CBC-Daten verwenden, um leicht geänderte Nachrichten an den Code zu senden, der das Orakel verfügbar macht, und weiterhin Daten senden, bis das Orakel ihnen mitteilt, dass die Daten korrekt sind. Aus dieser Antwort kann der Angreifer das Nachrichtenbyte byte entschlüsseln.

Moderne Computernetzwerke sind von so hoher Qualität, dass ein Angreifer sehr kleine (weniger als 0,1 ms) Unterschiede in der Ausführungszeit auf Remote-Systemen erkennen kann.Anwendungen, die davon ausgehen, dass eine erfolgreiche Entschlüsselung nur erfolgen kann, wenn die Daten nicht manipuliert wurden, können anfällig für Angriffe von Tools sein, die entworfen wurden, um Unterschiede bei der erfolgreichen und erfolglosen Entschlüsselung zu beobachten. Obwohl dieser zeitliche Unterschied in einigen Sprachen oder Bibliotheken erheblicher sein kann als in anderen, wird nun angenommen, dass dies eine praktische Bedrohung für alle Sprachen und Bibliotheken ist, wenn die Reaktion der Anwendung auf Fehler berücksichtigt wird.

Dieser Angriff basiert auf der Fähigkeit, die verschlüsselten Daten zu ändern und das Ergebnis mit dem Orakel zu testen. Die einzige Möglichkeit, den Angriff vollständig zu mildern, besteht darin, Änderungen an den verschlüsselten Daten zu erkennen und keine Aktionen darauf auszuführen. Die Standardmethode hierzu besteht darin, eine Signatur für die Daten zu erstellen und diese Signatur zu überprüfen, bevor Vorgänge ausgeführt werden. Die Signatur muss überprüfbar sein, sie kann nicht vom Angreifer erstellt werden, da sie andernfalls die verschlüsselten Daten ändern und dann eine neue Signatur basierend auf den geänderten Daten berechnen würde. Ein häufiger Typ geeigneter Signatur wird als Keyed-Hash-Nachrichtenauthentifizierungscode (Keyed-Hash Message Authentication Code, HMAC) bezeichnet. Ein HMAC unterscheidet sich von einer Prüfsumme dadurch, dass er einen geheimen Schlüssel benötigt, der nur der Person bekannt ist, die den HMAC herstellt, und der Person, die ihn validiert. Ohne den Besitz des Schlüssels können Sie keinen korrekten HMAC produzieren. Wenn Sie Ihre Daten erhalten, nehmen Sie die verschlüsselten Daten, berechnen sie unabhängig voneinander den HMAC mit dem geheimen Schlüssel, den Sie und den Absender gemeinsam verwenden, und vergleichen dann den hMAC, den sie gesendet haben, mit dem von Ihnen berechneten. Dieser Vergleich muss konstante Zeit sein, da Sie sonst ein anderes nachweisbares Orakel hinzugefügt haben, das eine andere Art von Angriff ermöglicht.

Zusammenfassend müssen Sie diese mit einem HMAC (oder einer anderen Datenintegritätsprüfung) kombinieren, den Sie mit einem konstanten Zeitvergleich überprüfen, bevor Sie versuchen, die Daten zu entschlüsseln, um gepolsterte CBC-Blockchiffren sicher zu verwenden. Da alle geänderten Nachrichten die gleiche Zeit in Anspruch nehmen, um eine Antwort zu erzeugen, wird der Angriff verhindert.

## <a name="who-is-vulnerable"></a>Wer ist verwundbar?

Diese Sicherheitsanfälligkeit gilt sowohl für verwaltete als auch für systemeigene Anwendungen, die ihre eigene Verschlüsselung und Entschlüsselung durchführen. Dazu gehören z. B.:

- Eine Anwendung, die ein Cookie für die spätere Entschlüsselung auf dem Server verschlüsselt.
- Eine Datenbankanwendung, die Benutzern die Möglichkeit bietet, Daten in eine Tabelle einzufügen, deren Spalten später entschlüsselt werden.
- Eine Datenübertragungsanwendung, die auf Verschlüsselung mit einem freigegebenen Schlüssel basiert, um die Daten während der Übertragung zu schützen.
- Eine Anwendung, die Nachrichten "innerhalb" des TLS-Tunnels verschlüsselt und entschlüsselt.

Beachten Sie, dass die Verwendung von TLS allein Sie in diesen Szenarien möglicherweise nicht schützt.

Eine anfällige Anwendung:

- Entschlüsselt Daten im CBC-Verschlüsselungsmodus mit einem überprüfbaren Auffüllungsmodus, z. B. PKCS-7 oder ANSI X.923.
- Führt die Entschlüsselung durch, ohne eine Datenintegritätsprüfung durchgeführt zu haben (über einen MAC oder eine asymmetrische digitale Signatur).

Dies gilt auch für Anwendungen, die auf Abstraktionen über diesen Primitiven basieren, z. B. die EnvelopedData-Struktur für Kryptografische Nachrichtensyntax (PKCS-7/CMS).

## <a name="related-areas-of-concern"></a>Verwandte Bereiche, die Anlass zur Sorge geben

Untersuchungen haben Microsoft dazu veranlasst, sich weiter sorgen über CBC-Nachrichten zu sein, die mit ISO 10126-äquivalenter Auffüllung gepolstert sind, wenn die Nachricht eine bekannte oder vorhersehbare Fußzeilenstruktur aufweist. Beispielsweise Inhalte, die gemäß den Regeln der W3C XML Encryption Syntax and Processing Recommendation (xmlenc, EncryptedXml) erstellt wurden. Während die W3C-Anleitung zum Signieren der Nachricht dann als angemessen angesehen wurde, empfiehlt Microsoft nun, immer verschlüsselungs-dann-signieren zu tun.

Anwendungsentwickler sollten immer darauf achten, die Anwendbarkeit eines asymmetrischen Signaturschlüssels zu überprüfen, da keine inhärente Vertrauensstellung zwischen einem asymmetrischen Schlüssel und einer beliebigen Nachricht besteht.

## <a name="details"></a>Details

In der Vergangenheit gab es Konsens, dass es wichtig ist, wichtige Daten zu verschlüsseln und zu authentifizieren, indem Mittel wie HMAC- oder RSA-Signaturen verwendet werden. Es gab jedoch weniger klare Anleitungen, wie die Verschlüsselungs- und Authentifizierungsvorgänge sequenziert werden. Aufgrund der in diesem Artikel beschriebenen Sicherheitsanfälligkeit ist microsoftes Anleitung nun immer das Paradigma "verschlüsseln-dann-zeichen" zu verwenden. Das heißt, zuerst Daten mit einem symmetrischen Schlüssel verschlüsseln, dann einen MAC oder eine asymmetrische Signatur über den Chiffretext (verschlüsselte Daten) berechnen. Führen Sie beim Entschlüsseln von Daten das Gegenteil aus. Bestätigen Sie zunächst den MAC oder die Signatur des Chiffretexts, und entschlüsseln Sie ihn dann.

Eine Klasse von Schwachstellen, die als "Padding-Orakel-Angriffe" bekannt sind, gibt es seit über 10 Jahren. Diese Sicherheitsanfälligkeiten ermöglichen es einem Angreifer, Daten zu entschlüsseln, die durch symmetrische Blockalgorithmen wie AES und 3DES verschlüsselt wurden, und verwenden nicht mehr als 4096 Versuche pro Datenblock. Diese Sicherheitsanfälligkeiten nutzen die Tatsache, dass Blockchiffren am häufigsten mit überprüfbaren Auffüllungsdaten am Ende verwendet werden. Es wurde festgestellt, dass ein Angreifer die Daten entschlüsseln kann, wenn ein Angreifer mit Demischertext manipuliert und herausfinden kann, ob die Manipulation einen Fehler im Format des Auffüllens verursacht hat.

Anfänglich basierten praktische Angriffe auf Diensten, die unterschiedliche Fehlercodes zurückgeben würden, je nach, ob die Auffüllung gültig war, wie z. B. die ASP.NET Sicherheitsanfälligkeit [MS10-070](/security-updates/SecurityBulletins/2010/ms10-070). Microsoft ist jedoch nun der Ansicht, dass es praktisch ist, ähnliche Angriffe durchzuführen, indem nur die zeitlichen Unterschiede zwischen gültiger und ungültiger Auffüllung verwendet werden.

Sofern das Verschlüsselungsschema eine Signatur verwendet und die Signaturüberprüfung mit einer festen Laufzeit für eine bestimmte Datenlänge (unabhängig vom Inhalt) durchgeführt wird, kann die Datenintegrität überprüft werden, ohne dass informationen über einen [Seitenkanal](https://en.wikipedia.org/wiki/Side-channel_attack)an einen Angreifer abgegeben werden. Da die Integritätsprüfung alle manipulierten Nachrichten ablehnt, wird die Bedrohung durch das Auffüllen von Orakelen verringert.

## <a name="guidance"></a>Anleitungen

Zuallererst empfiehlt Microsoft, dass alle Daten, die vertraulich sind, über Transport Layer Security (TLS), den Nachfolger von Secure Sockets Layer (SSL), übertragen werden müssen.

Analysieren Sie als Nächstes Ihre Anwendung, um:

- Verstehen Sie genau, welche Verschlüsselung Sie durchführen und welche Verschlüsselung von den von Ihnen verwendenden Plattformen und APIs bereitgestellt wird.
- Stellen Sie sicher, dass jede Verwendung auf jeder Ebene eines symmetrischen [Blockverschlüsselungsalgorithmus](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers), z. B. AES und 3DES, im CBC-Modus die Verwendung einer Überprüfung der Integrität geheimer Schlüssel (eine asymmetrische Signatur, ein HMAC oder das Ändern des Verschlüsselungsmodus in einen [authentifizierten Verschlüsselungsmodus](https://en.wikipedia.org/wiki/Authenticated_encryption) (AE) wie GCM oder CCM enthält.

Basierend auf der aktuellen Forschung wird allgemein angenommen, dass, wenn die Authentifizierungs- und Verschlüsselungsschritte unabhängig für Nicht-AE-Verschlüsselungsmodi ausgeführt werden, die Authentifizierung des Chiffretextes (Verschlüsselung des Zeichens) die beste allgemeine Option ist. Allerdings gibt es keine einheitliche richtige Antwort auf Kryptographie und diese Verallgemeinerung ist nicht so gut wie gerichtete Ratschläge von einem professionellen Kryptographen.

Anwendungen, die ihr Messagingformat nicht ändern können, aber nicht authentifizierte CBC-Entschlüsselung durchführen, sollten versuchen, Abschwächungen wie:

- Entschlüsseln, ohne dass der decryptor die Auffüllung überprüfen oder entfernen kann:
  - Alle aufgebrachten Auffüllungen müssen noch entfernt oder ignoriert werden, Sie verschieben die Last in Ihre Anwendung.
  - Der Vorteil besteht darin, dass die Überprüfung und Entfernung von Auffüllungen in andere Anwendungsdatenüberprüfungslogik integriert werden kann. Wenn die Überprüfung und Datenüberprüfung der Auffüllung in konstanter Zeit durchgeführt werden kann, wird die Bedrohung verringert.
  - Da die Interpretation der Auffüllung die wahrgenommene Nachrichtenlänge ändert, kann es immer noch Zeitinformationen geben, die von diesem Ansatz emittiert werden.
- Ändern Sie den Entschlüsselungsauffüllungsmodus in ISO10126:
  - ISO10126 Entschlüsselungsauffüllung ist kompatibel mit PKCS7-Verschlüsselungsauffüllung und ANSIX923-Verschlüsselungsauffüllung.
  - Durch das Ändern des Modus wird das Auffüllungs-Orakelwissen auf 1 Byte anstelle des gesamten Blocks reduziert. Wenn der Inhalt jedoch über eine bekannte Fußzeile verfügt, z. B. ein schließendes XML-Element, können verwandte Angriffe den Rest der Nachricht weiterhin angreifen.
  - Dies verhindert auch nicht die Wiederherstellung von Klartexten in Situationen, in denen der Angreifer den gleichen Klartext zwingen kann, mehrmals mit einem anderen Nachrichtenoffset verschlüsselt zu werden.
- Gate die Auswertung eines Entschlüsselungsaufrufs, um das Timing-Signal zu dämpfen:
  - Die Berechnung der Haltezeit muss mindestens die maximale Zeitspanne betragen, die der Entschlüsselungsvorgang für jedes Datensegment in Anspruch nehmen würde, das aufgetärgemäß ist.
  - Zeitberechnungen sollten gemäß den Anleitungen unter [Erfassen von hochauflösenden Zeitstempeln](/windows/desktop/sysinfo/acquiring-high-resolution-time-stamps)durchgeführt werden, nicht durch Verwendung <xref:System.Environment.TickCount?displayProperty=nameWithType> (vorbehaltlich Rollover/Überlauf) oder Subtrahieren von zwei Systemzeitstempeln (vorbehaltlich NTP-Anpassungsfehlern).
  - Zeitberechnungen müssen den Entschlüsselungsvorgang einschließlich aller potenziellen Ausnahmen in verwalteten oder C++-Anwendungen einschließen und nicht nur am Ende aufgepolstert werden.
  - Wenn Erfolg oder Misserfolg noch feststeht, muss das Timing-Gate einen Fehler zurückgeben, wenn es abläuft.
- Dienste, die eine nicht authentifizierte Entschlüsselung durchführen, sollten über eine Überwachung verfügen, um festzustellen, dass eine Flut von "ungültigen" Nachrichten durchgekommen ist.
  - Denken Sie daran, dass dieses Signal sowohl falsche Positivmeldungen (rechtmäßig beschädigte Daten) als auch falsche Negative (Verbreitung des Angriffs über einen ausreichend langen Zeitpunkt, um der Erkennung zu entgehen) enthält.

## <a name="finding-vulnerable-code---native-applications"></a>Suchen von anfälligem Code – systemeigene Anwendungen

Für Programme, die für die Windows Cryptography: Next Generation (CNG)-Bibliothek erstellt wurden:

- Der Entschlüsselungsaufruf ist [an BCryptDecrypt](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptdecrypt), die Angabe des `BCRYPT_BLOCK_PADDING` Flags.
- Das Schlüsselhandle wurde initialisiert, indem [BCryptSetProperty](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptsetproperty) mit [BCRYPT_CHAINING_MODE](/windows/desktop/SecCNG/cng-property-identifiers#BCRYPT_CHAINING_MODE) auf festgelegt `BCRYPT_CHAIN_MODE_CBC`wurde.
  - Da `BCRYPT_CHAIN_MODE_CBC` es sich um den Standardcode handelt, hat der betroffene Code möglicherweise keinen Wert für `BCRYPT_CHAINING_MODE`zugewiesen.

Für Programme, die für die ältere Windows Cryptographic API erstellt wurden:

- Der Entschlüsselungsaufruf ist `Final=TRUE` [CryptDecrypt](/windows/desktop/api/wincrypt/nf-wincrypt-cryptdecrypt) mit .
- Das Schlüsselhandle wurde initialisiert, indem [CryptSetKeyParam](/windows/desktop/api/wincrypt/nf-wincrypt-cryptsetkeyparam) aufgerufen wurde, wobei [KP_MODE](/windows/desktop/api/wincrypt/nf-wincrypt-cryptgetkeyparam) auf festgelegt `CRYPT_MODE_CBC`ist.
  - Da `CRYPT_MODE_CBC` es sich um den Standardcode handelt, hat der betroffene Code möglicherweise keinen Wert für `KP_MODE`zugewiesen.

## <a name="finding-vulnerable-code---managed-applications"></a>Suchen von anfälligem Code – verwaltete Anwendungen

- Der Entschlüsselungsaufruf <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor> ist <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])> an <xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>die oder Methoden auf .
  - Dies umfasst die folgenden abgeleiteten Typen innerhalb von .NET, kann aber auch Typen von Drittanbietern enthalten:
    - <xref:System.Security.Cryptography.Aes>
    - <xref:System.Security.Cryptography.AesCng>
    - <xref:System.Security.Cryptography.AesCryptoServiceProvider>
    - <xref:System.Security.Cryptography.AesManaged>
    - <xref:System.Security.Cryptography.DES>
    - <xref:System.Security.Cryptography.DESCryptoServiceProvider>
    - <xref:System.Security.Cryptography.RC2>
    - <xref:System.Security.Cryptography.RC2CryptoServiceProvider>
    - <xref:System.Security.Cryptography.Rijndael>
    - <xref:System.Security.Cryptography.RijndaelManaged>
    - <xref:System.Security.Cryptography.TripleDES>
    - <xref:System.Security.Cryptography.TripleDESCng>
    - <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider>
- Die <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> Eigenschaft wurde <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType>auf <xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType>, oder festgelegt.
  - Da <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> die Standardversion vorliegt, hat <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> der betroffene Code die Eigenschaft möglicherweise nie zugewiesen.
- Die <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> Eigenschaft wurde auf<xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType>
  - Da <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType> die Standardversion vorliegt, hat <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> der betroffene Code die Eigenschaft möglicherweise nie zugewiesen.

## <a name="finding-vulnerable-code---cryptographic-message-syntax"></a>Suchen von anfälligem Code - Kryptografie-Nachrichtensyntax

Eine nicht authentifizierte CMS EnvelopedData-Nachricht, deren verschlüsselter Inhalt den CBC-Modus von AES verwendet (2.16.840.1.101.3.4.1.2, 2.16.840.1.101.3.4.1.22, 2.16.840.1.101.3.4.1.42), DES (1.3.14.3.2.7), 3DES (1.2.840.113549.3.7) oder RC2 (1.2.840.113549.3.2) sowie Nachrichten, die andere Blockchiffrealgorithmen im CBC-Modus verwenden.

Während Streamchiffren für diese besondere Sicherheitsanfälligkeit nicht anfällig sind, empfiehlt Microsoft, die Daten immer über die Überprüfung des ContentEncryptionAlgorithm-Werts zu authentifizieren.

Bei verwalteten Anwendungen kann ein CMS EnvelopedData-Blob als <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>jeder Wert erkannt werden, der an übergeben wird.

Bei systemeigenen Anwendungen kann ein CMS EnvelopedData-Blob als beliebiger Wert erkannt werden, `CMSG_ENVELOPED` der einem CMS-Handle über `CMSG_CTRL_DECRYPT` [CryptMsgUpdate](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgupdate) bereitgestellt wird, dessen resultierende [CMSG_TYPE_PARAM](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsggetparam) ist und/oder das CMS-Handle später eine Anweisung über [CryptMsgControl](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgcontrol)gesendet wird.

## <a name="vulnerable-code-example---managed"></a>Beispiel für anfälligen Code - verwaltet

Diese Methode liest ein Cookie und entschlüsselt es, und es ist nicht sichtbar. Daher kann der Inhalt eines Cookies, das von dieser Methode gelesen wird, von dem Benutzer, der es empfangen hat, oder von einem Angreifer, der den verschlüsselten Cookie-Wert erhalten hat, angegriffen werden.

```csharp
private byte[] DecryptCookie(string cookieName)
{
    HttpCookie cookie = Request.Cookies[cookieName];

    if (cookie == null)
    {
        return null;
    }

    using (ICryptoTransform decryptor = _aes.CreateDecryptor())
    using (MemoryStream memoryStream = new MemoryStream())
    using (CryptoStream cryptoStream =
        new CryptoStream(memoryStream, decryptor, CryptoStreamMode.Write))
    {
        byte[] readCookie = Convert.FromBase64String(cookie.Value);
        cryptoStream.Write(readCookie, 0, readCookie.Length);
        cryptoStream.FlushFinalBlock();
        return memoryStream.ToArray();
    }
}
```

## <a name="example-code-following-recommended-practices---managed"></a>Beispielcode nach empfohlenen Vorgehensweisen - verwaltet

Der folgende Beispielcode verwendet ein nicht standardmäßiges Nachrichtenformat von

`cipher_algorithm_id || hmac_algorithm_id || hmac_tag || iv || ciphertext`

wobei `cipher_algorithm_id` die `hmac_algorithm_id` und-Algorithmus-Bezeichner anwendungslokal (nicht standardmäßige) Darstellungen dieser Algorithmen sind. Diese Bezeichner können in anderen Teilen Ihres vorhandenen Messagingprotokolls sinnvoll sein, anstatt als bloßer verketteter Bytestream.

In diesem Beispiel wird auch ein einzelner Hauptschlüssel verwendet, um sowohl einen Verschlüsselungsschlüssel als auch einen HMAC-Schlüssel abzuleiten. Dies dient sowohl als Bequemlichkeit, um eine Anwendung mit einem einzelnen Schlüssel in eine Anwendung mit zwei Schlüsseln zu verwandeln, als auch als Ermutigung, die beiden Schlüssel als unterschiedliche Werte zu behalten. Außerdem wird sichergestellt, dass der HMAC-Schlüssel und der Verschlüsselungsschlüssel nicht aus der Synchronisierung herauskommen.

Dieses Beispiel akzeptiert keine <xref:System.IO.Stream> für die Verschlüsselung oder Entschlüsselung. Das aktuelle Datenformat erschwert die Verschlüsselung von Einem Durchlauf, da der `hmac_tag` Wert dem Verschlüsselungstext vorangeht. Dieses Format wurde jedoch ausgewählt, da es alle Elemente fester Größe am Anfang hält, um den Parser einfacher zu halten. Mit diesem Datenformat ist eine Ein-Pass-Entschlüsselung möglich, obwohl ein Implementierer darauf hingewiesen wird, GetHashAndReset aufzurufen und das Ergebnis vor dem Aufruf von TransformFinalBlock zu überprüfen. Wenn Streaming-Verschlüsselung wichtig ist, ist möglicherweise ein anderer AE-Modus erforderlich.

```csharp
// ==++==
//
//   Copyright (c) Microsoft Corporation.  All rights reserved.
//
//   Shared under the terms of the Microsoft Public License,
//   https://opensource.org/licenses/MS-PL
//
// ==--==

using System;
using System.Diagnostics;
using System.IO;
using System.Runtime.CompilerServices;
using System.Security.Cryptography;

namespace Microsoft.Examples.Cryptography
{
    public enum AeCipher : byte
    {
        Unknown,
        Aes256CbcPkcs7,
    }

    public enum AeMac : byte
    {
        Unknown,
        HMACSHA256,
        HMACSHA384,
    }

    /// <summary>
    /// Provides extension methods to make HashAlgorithm look like .NET Core's
    /// IncrementalHash
    /// </summary>
    internal static class IncrementalHashExtensions
    {
        public static void AppendData(this HashAlgorithm hash, byte[] data)
        {
            hash.TransformBlock(data, 0, data.Length, null, 0);
        }

        public static void AppendData(
            this HashAlgorithm hash,
            byte[] data,
            int offset,
            int length)
        {
            hash.TransformBlock(data, offset, length, null, 0);
        }

        public static byte[] GetHashAndReset(this HashAlgorithm hash)
        {
            hash.TransformFinalBlock(Array.Empty<byte>(), 0, 0);
            return hash.Hash;
        }
    }

    public static partial class AuthenticatedEncryption
    {
        /// <summary>
        /// Use <paramref name="masterKey"/> to derive two keys (one cipher, one HMAC)
        /// to provide authenticated encryption for <paramref name="message"/>.
        /// </summary>
        /// <param name="masterKey">The master key from which other keys derive.</param>
        /// <param name="message">The message to encrypt</param>
        /// <returns>
        /// A concatenation of
        /// [cipher algorithm+chainmode+padding][mac algorithm][authtag][IV][ciphertext],
        /// suitable to be passed to <see cref="Decrypt"/>.
        /// </returns>
        /// <remarks>
        /// <paramref name="masterKey"/> should be a 128-bit (or bigger) value generated
        /// by a secure random number generator, such as the one returned from
        /// <see cref="RandomNumberGenerator.Create()"/>.
        /// This implementation chooses to block deficient inputs by length, but does not
        /// make any attempt at discerning the randomness of the key.
        ///
        /// If the master key is being input by a prompt (like a password/passphrase)
        /// then it should be properly turned into keying material via a Key Derivation
        /// Function like PBKDF2, represented by Rfc2898DeriveBytes. A 'password' should
        /// never be simply turned to bytes via an Encoding class and used as a key.
        /// </remarks>
        public static byte[] Encrypt(byte[] masterKey, byte[] message)
        {
            if (masterKey == null)
                throw new ArgumentNullException(nameof(masterKey));
            if (masterKey.Length < 16)
                throw new ArgumentOutOfRangeException(
                    nameof(masterKey),
                    "Master Key must be at least 128 bits (16 bytes)");
            if (message == null)
                throw new ArgumentNullException(nameof(message));

            // First, choose an encryption scheme.
            AeCipher aeCipher = AeCipher.Aes256CbcPkcs7;

            // Second, choose an authentication (message integrity) scheme.
            //
            // In this example we use the master key length to change from HMACSHA256 to
            // HMACSHA384, but that is completely arbitrary. This mostly represents a
            // "cryptographic needs change over time" scenario.
            AeMac aeMac = masterKey.Length < 48 ? AeMac.HMACSHA256 : AeMac.HMACSHA384;

            // It's good to be able to identify what choices were made when a message was
            // encrypted, so that the message can later be decrypted. This allows for
            // future versions to add support for new encryption schemes, but still be
            // able to read old data. A practice known as "cryptographic agility".
            //
            // This is similar in practice to PKCS#7 messaging, but this uses a
            // private-scoped byte rather than a public-scoped Object IDentifier (OID).
            // Please note that the scheme in this example adheres to no particular
            // standard, and is unlikely to survive to a more complete implementation in
            // the .NET Framework.
            //
            // You may be well-served by prepending a version number byte to this
            // message, but may want to avoid the value 0x30 (the leading byte value for
            // DER-encoded structures such as X.509 certificates and PKCS#7 messages).
            byte[] algorithmChoices = { (byte)aeCipher, (byte)aeMac };
            byte[] iv;
            byte[] cipherText;
            byte[] tag;

            // Using our algorithm choices, open an HMAC (as an authentication tag
            // generator) and a SymmetricAlgorithm which use different keys each derived
            // from the same master key.
            //
            // A custom implementation may very well have distinctly managed secret keys
            // for the MAC and cipher, this example merely demonstrates the master to
            // derived key methodology to encourage key separation from the MAC and
            // cipher keys.
            using (HMAC tagGenerator = GetMac(aeMac, masterKey))
            {
                using (SymmetricAlgorithm cipher = GetCipher(aeCipher, masterKey))
                using (ICryptoTransform encryptor = cipher.CreateEncryptor())
                {
                    // Since no IV was provided, a random one has been generated
                    // during the call to CreateEncryptor.
                    //
                    // But note that it only does the auto-generation once. If the cipher
                    // object were used again, a call to GenerateIV would have been
                    // required.
                    iv = cipher.IV;

                    cipherText = Transform(encryptor, message, 0, message.Length);
                }

                // The IV and ciphertest both need to be included in the MAC to prevent
                // tampering.
                //
                // By including the algorithm identifiers, we have technically moved from
                // simple Authenticated Encryption (AE) to Authenticated Encryption with
                // Additional Data (AEAD). By including the algorithm identifiers in the
                // MAC, it becomes harder for an attacker to change them as an attempt to
                // perform a downgrade attack.
                //
                // If you've added a data format version field, it can also be included
                // in the MAC to further inhibit an attacker's options for confusing the
                // data processor into believing the tampered message is valid.
                tagGenerator.AppendData(algorithmChoices);
                tagGenerator.AppendData(iv);
                tagGenerator.AppendData(cipherText);
                tag = tagGenerator.GetHashAndReset();
            }

            // Build the final result as the concatenation of everything except the keys.
            int totalLength =
                algorithmChoices.Length +
                tag.Length +
                iv.Length +
                cipherText.Length;

            byte[] output = new byte[totalLength];
            int outputOffset = 0;

            Append(algorithmChoices, output, ref outputOffset);
            Append(tag, output, ref outputOffset);
            Append(iv, output, ref outputOffset);
            Append(cipherText, output, ref outputOffset);

            Debug.Assert(outputOffset == output.Length);
            return output;
        }

        /// <summary>
        /// Reads a message produced by <see cref="Encrypt"/> after verifying it hasn't
        /// been tampered with.
        /// </summary>
        /// <param name="masterKey">The master key from which other keys derive.</param>
        /// <param name="cipherText">
        /// The output of <see cref="Encrypt"/>: a concatenation of a cipher ID, mac ID,
        /// authTag, IV, and cipherText.
        /// </param>
        /// <returns>The decrypted content.</returns>
        /// <exception cref="ArgumentNullException">
        /// <paramref name="masterKey"/> is <c>null</c>.
        /// </exception>
        /// <exception cref="ArgumentNullException">
        /// <paramref name="cipherText"/> is <c>null</c>.
        /// </exception>
        /// <exception cref="CryptographicException">
        /// <paramref name="cipherText"/> identifies unknown algorithms, is not long
        /// enough, fails a data integrity check, or fails to decrypt.
        /// </exception>
        /// <remarks>
        /// <paramref name="masterKey"/> should be a 128-bit (or larger) value
        /// generated by a secure random number generator, such as the one returned from
        /// <see cref="RandomNumberGenerator.Create()"/>. This implementation chooses to
        /// block deficient inputs by length, but doesn't make any attempt at
        /// discerning the randomness of the key.
        ///
        /// If the master key is being input by a prompt (like a password/passphrase),
        /// then it should be properly turned into keying material via a Key Derivation
        /// Function like PBKDF2, represented by Rfc2898DeriveBytes. A 'password' should
        /// never be simply turned to bytes via an Encoding class and used as a key.
        /// </remarks>
        public static byte[] Decrypt(byte[] masterKey, byte[] cipherText)
        {
            // This example continues the .NET practice of throwing exceptions for
            // failures. If you consider message tampering to be normal (and thus
            // "not exceptional") behavior, you may like the signature
            // bool Decrypt(byte[] messageKey, byte[] cipherText, out byte[] message)
            // better.
            if (masterKey == null)
                throw new ArgumentNullException(nameof(masterKey));
            if (masterKey.Length < 16)
                throw new ArgumentOutOfRangeException(
                    nameof(masterKey),
                    "Master Key must be at least 128 bits (16 bytes)");
            if (cipherText == null)
                throw new ArgumentNullException(nameof(cipherText));

            // The format of this message is assumed to be public, so there's no harm in
            // saying ahead of time that the message makes no sense.
            if (cipherText.Length < 2)
            {
                throw new CryptographicException();
            }

            // Use the message algorithm headers to determine what cipher algorithm and
            // MAC algorithm are going to be used. Since the same Key Derivation
            // Functions (KDFs) are being used in Decrypt as Encrypt, the keys are also
            // the same.
            AeCipher aeCipher = (AeCipher)cipherText[0];
            AeMac aeMac = (AeMac)cipherText[1];

            using (SymmetricAlgorithm cipher = GetCipher(aeCipher, masterKey))
            using (HMAC tagGenerator = GetMac(aeMac, masterKey))
            {
                int blockSizeInBytes = cipher.BlockSize / 8;
                int tagSizeInBytes = tagGenerator.HashSize / 8;
                int headerSizeInBytes = 2;
                int tagOffset = headerSizeInBytes;
                int ivOffset = tagOffset + tagSizeInBytes;
                int cipherTextOffset = ivOffset + blockSizeInBytes;
                int cipherTextLength = cipherText.Length - cipherTextOffset;
                int minLen = cipherTextOffset + blockSizeInBytes;

                // Again, the minimum length is still assumed to be public knowledge,
                // nothing has leaked out yet. The minimum length couldn't just be calculated
                // without reading the header.
                if (cipherText.Length < minLen)
                {
                    throw new CryptographicException();
                }

                // It's very important that the MAC be calculated and verified before
                // proceeding to decrypt the ciphertext, as this prevents any sort of
                // information leaking out to an attacker.
                //
                // Don't include the tag in the calculation, though.

                // First, everything before the tag (the cipher and MAC algorithm ids)
                tagGenerator.AppendData(cipherText, 0, tagOffset);

                // Skip the data before the tag and the tag, then read everything that
                // remains.
                tagGenerator.AppendData(
                    cipherText,
                    tagOffset + tagSizeInBytes,
                    cipherText.Length - tagSizeInBytes - tagOffset);

                byte[] generatedTag = tagGenerator.GetHashAndReset();

                // The time it took to get to this point has so far been a function only
                // of the length of the data, or of non-encrypted values (e.g. it could
                // take longer to prepare the *key* for the HMACSHA384 MAC than the
                // HMACSHA256 MAC, but the algorithm choice wasn't a secret).
                //
                // If the verification of the authentication tag aborts as soon as a
                // difference is found in the byte arrays then your program may be
                // acting as a timing oracle which helps an attacker to brute-force the
                // right answer for the MAC. So, it's very important that every possible
                // "no" (2^256-1 of them for HMACSHA256) be evaluated in as close to the
                // same amount of time as possible. For this, we call CryptographicEquals
                if (!CryptographicEquals(
                    generatedTag,
                    0,
                    cipherText,
                    tagOffset,
                    tagSizeInBytes))
                {
                    // Assuming every tampered message (of the same length) took the same
                    // amount of time to process, we can now safely say
                    // "this data makes no sense" without giving anything away.
                    throw new CryptographicException();
                }

                // Restore the IV into the symmetricAlgorithm instance.
                byte[] iv = new byte[blockSizeInBytes];
                Buffer.BlockCopy(cipherText, ivOffset, iv, 0, iv.Length);
                cipher.IV = iv;

                using (ICryptoTransform decryptor = cipher.CreateDecryptor())
                {
                    return Transform(
                        decryptor,
                        cipherText,
                        cipherTextOffset,
                        cipherTextLength);
                }
            }
        }

        private static byte[] Transform(
            ICryptoTransform transform,
            byte[] input,
            int inputOffset,
            int inputLength)
        {
            // Many of the implementations of ICryptoTransform report true for
            // CanTransformMultipleBlocks, and when the entire message is available in
            // one shot this saves on the allocation of the CryptoStream and the
            // intermediate structures it needs to properly chunk the message into blocks
            // (since the underlying stream won't always return the number of bytes
            // needed).
            if (transform.CanTransformMultipleBlocks)
            {
                return transform.TransformFinalBlock(input, inputOffset, inputLength);
            }

            // If our transform couldn't do multiple blocks at once, let CryptoStream
            // handle the chunking.
            using (MemoryStream messageStream = new MemoryStream())
            using (CryptoStream cryptoStream =
                new CryptoStream(messageStream, transform, CryptoStreamMode.Write))
            {
                cryptoStream.Write(input, inputOffset, inputLength);
                cryptoStream.FlushFinalBlock();
                return messageStream.ToArray();
            }
        }

        /// <summary>
        /// Open a properly configured <see cref="SymmetricAlgorithm"/> conforming to the
        /// scheme identified by <paramref name="aeCipher"/>.
        /// </summary>
        /// <param name="aeCipher">The cipher mode to open.</param>
        /// <param name="masterKey">The master key from which other keys derive.</param>
        /// <returns>
        /// A SymmetricAlgorithm object with the right key, cipher mode, and padding
        /// mode; or <c>null</c> on unknown algorithms.
        /// </returns>
        private static SymmetricAlgorithm GetCipher(AeCipher aeCipher, byte[] masterKey)
        {
            SymmetricAlgorithm symmetricAlgorithm;

            switch (aeCipher)
            {
                case AeCipher.Aes256CbcPkcs7:
                    symmetricAlgorithm = Aes.Create();
                    // While 256-bit, CBC, and PKCS7 are all the default values for these
                    // properties, being explicit helps comprehension more than it hurts
                    // performance.
                    symmetricAlgorithm.KeySize = 256;
                    symmetricAlgorithm.Mode = CipherMode.CBC;
                    symmetricAlgorithm.Padding = PaddingMode.PKCS7;
                    break;
                default:
                    // An algorithm we don't understand
                    throw new CryptographicException();
            }

            // Instead of using the master key directly, derive a key for our chosen
            // HMAC algorithm based upon the master key.
            //
            // Since none of the symmetric encryption algorithms currently in .NET
            // support key sizes greater than 256-bit, we can use HMACSHA256 with
            // NIST SP 800-108 5.1 (Counter Mode KDF) to derive a value that is
            // no smaller than the key size, then Array.Resize to trim it down as
            // needed.

            using (HMAC hmac = new HMACSHA256(masterKey))
            {
                // i=1, Label=ASCII(cipher)
                byte[] cipherKey = hmac.ComputeHash(
                    new byte[] { 1, 99, 105, 112, 104, 101, 114 });

                // Resize the array to the desired keysize. KeySize is in bits,
                // and Array.Resize wants the length in bytes.
                Array.Resize(ref cipherKey, symmetricAlgorithm.KeySize / 8);

                symmetricAlgorithm.Key = cipherKey;
            }

            return symmetricAlgorithm;
        }

        /// <summary>
        /// Open a properly configured <see cref="HMAC"/> conforming to the scheme
        /// identified by <paramref name="aeMac"/>.
        /// </summary>
        /// <param name="aeMac">The message authentication mode to open.</param>
        /// <param name="masterKey">The master key from which other keys derive.</param>
        /// <returns>
        /// An HMAC object with the proper key, or <c>null</c> on unknown algorithms.
        /// </returns>
        private static HMAC GetMac(AeMac aeMac, byte[] masterKey)
        {
            HMAC hmac;

            switch (aeMac)
            {
                case AeMac.HMACSHA256:
                    hmac = new HMACSHA256();
                    break;
                case AeMac.HMACSHA384:
                    hmac = new HMACSHA384();
                    break;
                default:
                    // An algorithm we don't understand
                    throw new CryptographicException();
            }

            // Instead of using the master key directly, derive a key for our chosen
            // HMAC algorithm based upon the master key.
            // Since the output size of the HMAC is the same as the ideal key size for
            // the HMAC, we can use the master key over a fixed input once to perform
            // NIST SP 800-108 5.1 (Counter Mode KDF):
            hmac.Key = masterKey;

            // i=1, Context=ASCII(MAC)
            byte[] newKey = hmac.ComputeHash(new byte[] { 1, 77, 65, 67 });

            hmac.Key = newKey;
            return hmac;
        }

        // A simple helper method to ensure that the offset (writePos) always moves
        // forward with new data.
        private static void Append(byte[] newData, byte[] combinedData, ref int writePos)
        {
            Buffer.BlockCopy(newData, 0, combinedData, writePos, newData.Length);
            writePos += newData.Length;
        }

        /// <summary>
        /// Compare the contents of two arrays in an amount of time which is only
        /// dependent on <paramref name="length"/>.
        /// </summary>
        /// <param name="a">An array to compare to <paramref name="b"/>.</param>
        /// <param name="aOffset">
        /// The starting position within <paramref name="a"/> for comparison.
        /// </param>
        /// <param name="b">An array to compare to <paramref name="a"/>.</param>
        /// <param name="bOffset">
        /// The starting position within <paramref name="b"/> for comparison.
        /// </param>
        /// <param name="length">
        /// The number of bytes to compare between <paramref name="a"/> and
        /// <paramref name="b"/>.</param>
        /// <returns>
        /// <c>true</c> if both <paramref name="a"/> and <paramref name="b"/> have
        /// sufficient length for the comparison and all of the applicable values are the
        /// same in both arrays; <c>false</c> otherwise.
        /// </returns>
        /// <remarks>
        /// An "insufficient data" <c>false</c> response can happen early, but otherwise
        /// a <c>true</c> or <c>false</c> response take the same amount of time.
        /// </remarks>
        [MethodImpl(MethodImplOptions.NoInlining | MethodImplOptions.NoOptimization)]
        private static bool CryptographicEquals(
            byte[] a,
            int aOffset,
            byte[] b,
            int bOffset,
            int length)
        {
            Debug.Assert(a != null);
            Debug.Assert(b != null);
            Debug.Assert(length >= 0);

            int result = 0;

            if (a.Length - aOffset < length || b.Length - bOffset < length)
            {
                return false;
            }

            unchecked
            {
                for (int i = 0; i < length; i++)
                {
                    // Bitwise-OR of subtraction has been found to have the most
                    // stable execution time.
                    //
                    // This cannot overflow because bytes are 1 byte in length, and
                    // result is 4 bytes.
                    // The OR propagates all set bytes, so the differences are only
                    // present in the lowest byte.
                    result = result | (a[i + aOffset] - b[i + bOffset]);
                }
            }

            return result == 0;
        }
    }
}
```
