---
title: CBC-Entschlüsselungs Anfälligkeit
description: Erfahren Sie, wie Sie zeitliche Sicherheitsrisiken mit der symmetrischen Entschlüsselung des Cipher-Block-Chaining (CBC)-Modus mithilfe von Padding erkennen und beheben.
ms.date: 06/12/2018
author: blowdart
ms.author: mairaw
ms.openlocfilehash: 1d570cf3da197e7af5c1a1ab4e4df0d21f2cb2d7
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347235"
---
# <a name="timing-vulnerabilities-with-cbc-mode-symmetric-decryption-using-padding"></a>Verwenden der Auffüllung für die Zeitsteuerung bei Sicherheitsrisiken mit symmetrischer Entschlüsselung im CBC-Modus

Microsoft ist der Meinung, dass es nicht mehr sicher ist, dass Daten entschlüsselt werden, die mit dem CBC-Modus (Cipher Block-Chaining) der symmetrischen Verschlüsselung verschlüsselt sind, wenn eine überprüfbare Auffüll Funktion angewendet wurde, ohne zuvor die Integrität des Chiffre Texts sicherzustellen, außer sehr spezifisch. Umständen. Dieses Urteil basiert auf der zurzeit bekannten kryptografieforschung. 

## <a name="introduction"></a>Einführung

Bei einem Auffüll-Oracle-Angriff handelt es sich um eine Art von Angriffen gegen verschlüsselte Daten, die es dem Angreifer ermöglichen, den Inhalt der Daten zu entschlüsseln, ohne den Schlüssel zu kennen.

Ein Oracle verweist auf ein "Tell", das einem Angreifer Informationen darüber gibt, ob die ausgeführte Aktion korrekt ist oder nicht. Stellen Sie sich vor, Sie spielen ein Board oder Kartenspiel mit einem untergeordneten Wenn das Gesicht mit einem großen Lächeln hervorgeht, weil Sie meint, dass Sie eine gute Bewegung machen möchten, ist dies ein Oracle. Als Gegner können Sie mit diesem Oracle die nächste Verschiebung entsprechend planen.

Padding ist ein spezifischer kryptografiebegriff. Einige Chiffren, bei denen es sich um die Algorithmen handelt, die zum Verschlüsseln der Daten verwendet werden, arbeiten an Datenblöcken, in denen jeder Block eine festgelegte Größe hat. Wenn die zu verschlüsselnden Daten nicht die richtige Größe zum Ausfüllen der Blöcke sind, werden die Daten bis zu Ihrem Zeitpunkt aufgefüllt. Viele Auffüll Formen erfordern, dass die Auffüll Zeichen immer vorhanden sind, auch wenn die ursprüngliche Eingabe von der richtigen Größe war. Dadurch kann die Auffüll Zeichen bei der Entschlüsselung immer sicher entfernt werden.

Wenn die beiden Dinge zusammengefasst werden, gibt eine Software Implementierung mit einem Auffüllung-Oracle an, ob entschlüsselte Daten einen gültigen Abstand haben. Das Oracle könnte etwas so einfach sein wie das Zurückgeben eines Werts, der besagt, dass es sich um einen "ungültigen Auffüll Vorgang" handelt, oder etwas komplizierter ist, wenn ein gültiger Block nicht in einem ungültigen Block verarbeitet werden soll

Block basierte Chiffren verfügen über eine andere Eigenschaft, die als-Modus bezeichnet wird und die Beziehung der Daten im ersten Block zu den Daten im zweiten Block bestimmt usw. Einer der am häufigsten verwendeten Modi ist CBC. CBC führt einen anfänglichen zufälligen Block ein, der als Initialisierungs Vektor (IV) bezeichnet wird, und kombiniert den vorherigen Block mit dem Ergebnis der statischen Verschlüsselung, um ihn so zu gestalten, dass die Verschlüsselung derselben Nachricht mit demselben Schlüssel nicht immer die gleiche verschlüsselte Ausgabe erzeugt.

Ein Angreifer kann in Kombination mit der Struktur von CBC-Daten ein Auffüll Zeichen verwenden, um leicht geänderte Nachrichten an den Code zu senden, der das Oracle verfügbar macht, und das Senden von Daten so lange, bis das Oracle Ihnen mitteilt, dass die Daten korrekt sind. Aus dieser Antwort kann der Angreifer das Nachrichten Byte nach Byte entschlüsseln.

Moderne Computernetzwerke sind so hochwertig, dass ein Angreifer sehr kleine (weniger als 0,1 ms) Unterschiede in der Ausführungszeit auf Remote Systemen erkennen kann. Anwendungen, die davon ausgehen, dass eine erfolgreiche Entschlüsselung nur durchgeführt werden kann, wenn die Daten nicht manipuliert wurden, sind möglicherweise anfällig für Angriffe von Tools, die für die Unterschiede bei erfolgreicher und nicht erfolgreicher Entschlüsselung konzipiert sind. Diese zeitliche Unterschiede können in einigen Sprachen oder Bibliotheken signifikanter sein als andere, aber es ist mittlerweile der Meinung, dass dies eine praktische Bedrohung für alle Sprachen und Bibliotheken ist, wenn die Antwort auf den Fehler der Anwendung berücksichtigt wird.

Dieser Angriff basiert auf der Möglichkeit, die verschlüsselten Daten zu ändern und das Ergebnis mit dem Oracle zu testen. Die einzige Möglichkeit, den Angriff vollständig zu mindern, besteht darin, Änderungen an den verschlüsselten Daten zu erkennen und die Ausführung von Aktionen daran abzulehnen. Die Standardmethode hierfür ist, eine Signatur für die Daten zu erstellen und diese Signatur zu validieren, bevor Vorgänge ausgeführt werden. Die Signatur muss überprüfbar sein, Sie kann nicht vom Angreifer erstellt werden. andernfalls ändern Sie die verschlüsselten Daten und berechnen dann basierend auf den geänderten Daten eine neue Signatur. Ein allgemeiner Typ der entsprechenden Signatur wird als Schlüssel für die Authentifizierung per Hashwert (Hash Message Authentication Code, HMAC) bezeichnet. Ein HMAC unterscheidet sich von einer Prüfsumme darin, dass er einen geheimen Schlüssel annimmt, der nur für die Person bekannt ist, die den HMAC erstellt, und für die Person, die Sie überprüft. Ohne den Besitz des Schlüssels kann kein korrekter HMAC erstellt werden. Wenn Sie Ihre Daten empfangen, nehmen Sie die verschlüsselten Daten unabhängig, indem Sie den HMAC unabhängig von dem geheimen Schlüssel verwenden, den Sie und die Absender Freigabe verwenden, und vergleichen Sie dann den HMAC, den Sie mit dem berechneten Server gesendet haben. Dieser Vergleich muss konstant sein, da Sie andernfalls ein weiteres erkennbares Oracle-Flag hinzugefügt haben, das eine andere Art von Angriff zulässt.

Zusammenfassend müssen Sie zur sicheren Verwendung von aufgefüllten CBC-Blockchiffren mit einem HMAC (oder einer anderen Daten Integritäts Überprüfung) kombiniert werden, die Sie mithilfe eines konstanten Zeit Vergleichs validieren, bevor Sie versuchen, die Daten zu entschlüsseln. Da alle geänderten Nachrichten die gleiche Zeit benötigen, um eine Antwort zu erhalten, wird der Angriff verhindert.

## <a name="who-is-vulnerable"></a>Wer ist anfällig

Dieses Sicherheitsrisiko gilt für verwaltete und native Anwendungen, die ihre eigene Verschlüsselung und Entschlüsselung durchführen. Dies schließt z. b. Folgendes ein:

- Eine Anwendung, die ein Cookie für die spätere Entschlüsselung auf dem Server verschlüsselt.
- Eine Datenbankanwendung, die es Benutzern ermöglicht, Daten in eine Tabelle einzufügen, deren Spalten später entschlüsselt werden.
- Eine Datenübertragungs Anwendung, die mithilfe eines gemeinsam genutzten Schlüssels zum Schutz der Daten während der Übertragung auf Verschlüsselung basiert.
- Eine Anwendung, die Nachrichten "innerhalb" des TLS-Tunnels verschlüsselt und entschlüsselt.

Beachten Sie, dass die Verwendung von TLS allein in diesen Szenarien möglicherweise nicht geschützt ist.

Eine anfällige Anwendung:

- Entschlüsselt Daten mit dem CBC-Chiffre Modus mit einem überprüfbaren Auffüllung-Modus, z. b. PKCS # 7 oder ANSI X. 923.
- Führt die Entschlüsselung aus, ohne dass eine Überprüfung der Datenintegrität durchgeführt wurde (über eine Mac-oder eine asymmetrische digitale Signatur).

Dies gilt auch für Anwendungen, die auf Abstraktionen oberhalb dieser primitiven basieren, wie z. b. die "Cryptographic Message Syntax (PKCS # 7/CMS) EnvelopedData"-Struktur.

## <a name="related-areas-of-concern"></a>Relevante Bereiche

Research hat Microsoft dabei geführt, sich über CBC-Nachrichten, die mit ISO 10126-Entsprechung aufgefüllt werden, genauer zu beschäftigen, wenn die Nachricht über eine bekannte oder vorhersagbare footerstruktur verfügt. Dies ist beispielsweise der Inhalt, der unter den Regeln der W3C-XML-Verschlüsselungs Syntax und-Verarbeitungs Empfehlung (xmlenc, verschlüsseltedxml) vorbereitet wurde. Obwohl die W3C-Anleitung zum Signieren der Nachricht als geeignet eingestuft wurde, sollte Microsoft nun immer "verschlüsseln-dann-signieren" empfehlen.

Anwendungsentwickler sollten stets bedenken, dass die Anwendbarkeit eines asymmetrischen Signatur Schlüssels überprüft werden muss, da es keine inhärente Vertrauensstellung zwischen einem asymmetrischen Schlüssel und einer willkürlichen Nachricht gibt.

## <a name="details"></a>Details

In der Vergangenheit gab es einen Konsens, dass es wichtig ist, wichtige Daten zu verschlüsseln und zu authentifizieren, indem Sie beispielsweise HMAC-oder RSA-Signaturen verwenden. Es gab jedoch weniger klare Hinweise zum Sequenzieren der Verschlüsselungs-und Authentifizierungs Vorgänge. Aufgrund der in diesem Artikel beschriebenen Sicherheits Anfälligkeit besteht die Anleitung von Microsoft darin, immer das Paradigma "verschlüsseln, dann signieren" zu verwenden. Das heißt, Sie verschlüsseln zuerst Daten mit einem symmetrischen Schlüssel und berechnen dann eine Mac-oder asymmetrische Signatur über den Chiffre Text (verschlüsselte Daten). Führen Sie beim Entschlüsseln von Daten den umgekehrten Vorgang aus. Bestätigen Sie zunächst den Mac oder die Signatur des Chiffre Texts, und entschlüsseln Sie ihn anschließend.

Eine Klasse von Sicherheitsrisiken, die als "Auffüllen von Oracle-Angriffen" bezeichnet werden, ist seit mehr als 10 Jahren bekannt. Diese Sicherheitsrisiken ermöglichen einem Angreifer das Entschlüsseln von Daten, die von symmetrischen Block Algorithmen (z. b. AES und 3DES) verschlüsselt werden, wobei nicht mehr als 4096 Versuche pro Datenblock verwendet werden. Diese Sicherheitslücken nutzen die Tatsache, dass Blockchiffren am Ende mit überprüfbaren Auffüll Daten verwendet werden. Es wurde festgestellt, dass der Angreifer die Daten entschlüsseln kann, wenn ein Angreifer Chiffre Text manipulieren und feststellen kann, ob die Manipulation zu einem Fehler im Format des Auffüll Zeichens geführt hat.

Zunächst waren praktische Angriffe auf Dienste basiert, die je nach Gültigkeit des Auffüll Zeichens andere Fehlercodes zurückgeben, z. b. das ASP.net-Sicherheitsrisiko [MS10-070](/security-updates/SecurityBulletins/2010/ms10-070). Microsoft ist nun jedoch der Meinung, dass es praktisch ist, ähnliche Angriffe durchzuführen, indem nur die Unterschiede in der zeitlichen Steuerung zwischen der Verarbeitung gültiger und Ungültiger Auffüll Vorgänge

Vorausgesetzt, dass das Verschlüsselungsschema eine Signatur verwendet und die Signatur Überprüfung mit einer festgelegten Laufzeit für eine bestimmte Daten Länge (unabhängig vom Inhalt) erfolgt, kann die Datenintegrität überprüft werden, ohne dass Informationen über einen [seitigen Kanal](https://en.wikipedia.org/wiki/Side-channel_attack)an einen Angreifer ausgegeben werden. Da bei der Integritäts Überprüfung alle manipulierten Nachrichten abgelehnt werden, wird das Auffüllen von Oracle-Bedrohungen verringert.

## <a name="guidance"></a>Anleitung

Vor allem empfiehlt Microsoft, dass alle Daten, die Vertraulichkeit aufweisen, über Transport Layer Security (TLS), den Nachfolger an Secure Sockets Layer (SSL) übertragen werden.

Analysieren Sie dann Ihre Anwendung wie folgt:

- Verstehen Sie genau, welche Verschlüsselung Sie durchführen und welche Verschlüsselung von den verwendeten Plattformen und APIs bereitgestellt wird.
- Stellen Sie sicher, dass jede Verwendung auf jeder Ebene eines symmetrischen [Blockchiffre Algorithmus](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers)(z. b. AES und 3DES) im CBC-Modus die Verwendung einer geheimen Daten Integritäts Überprüfung (eine asymmetrische Signatur, ein HMAC) oder den Verschlüsselungs Modus in einen [authentifizierten Verschlüsselungs](https://en.wikipedia.org/wiki/Authenticated_encryption) Modus (z. b. GCM oder CCM) einschließt.

Basierend auf der aktuellen Forschung ist es in der Regel der Meinung, dass die Authentifizierung des Chiffre Texts (Encryption-then-Sign) die beste Option ist, wenn die Authentifizierungs-und Verschlüsselungs Schritte unabhängig für nicht-AE-Verschlüsselungs Modi durchgeführt werden. Allerdings gibt es keine richtige Lösung für die Kryptografie, und diese Generalisierung ist nicht so gut wie eine gezielte Empfehlung von einem professionellen Kryptographen.

Anwendungen, die Ihr Messaging Format nicht ändern können, aber nicht authentifizierte CBC-Entschlüsselung ausführen, werden empfohlen, um Lösungen wie die folgenden zu integrieren:

- Entschlüsseln, ohne dass der Entschlüsselungs Mechanismus das Auffüllen überprüfen oder entfernen kann:
  - Alle Auffüll Zeichen, die angewendet wurden, müssen entfernt oder ignoriert werden, Sie verschieben die Belastung in Ihre Anwendung.
  - Der Vorteil besteht darin, dass die Auffüll-und Entfernungs Überprüfungen in andere Anwendungsdaten-Überprüfungs Logik integriert werden können. Wenn die Auffüll-und Datenüberprüfung in konstanter Zeit ausgeführt werden kann, wird die Bedrohung reduziert.
  - Da die Interpretation des Paddings die übergebene Nachrichten Länge ändert, werden möglicherweise weiterhin Zeit Steuerungsinformationen von diesem Ansatz ausgegeben.
- Ändern Sie den Modus für die Entschlüsselungs Auffüll Modus in ISO10126:
  - Der ISO10126-Entschlüsselungs Abstand ist sowohl mit dem PKCS7-Auffüll Auffüll Zeichen als auch mit der ANSIX923-Verschlüsselung kompatibel.
  - Wenn Sie den Modus ändern, wird das Auffüllen des Oracle-Wissens auf 1 Byte statt auf den gesamten Block reduziert. Wenn der Inhalt jedoch über eine bekannte Fußzeile verfügt, z. b. ein abschließendes XML-Element, können verwandte Angriffe weiterhin den Rest der Nachricht angreifen.
  - Dies verhindert auch eine Klartext-Wiederherstellung in Situationen, in denen der Angreifer denselben Klartext umwandeln kann, um mehrmals mit einem anderen Nachrichten Offset verschlüsselt zu werden.
- Gate die Auswertung eines Entschlüsselungs Aufrufs, um das zeitliche Signal zu dämpfen:
  - Die Berechnung der Haltezeit muss mindestens den maximalen Zeitraum überschreiten, den der Entschlüsselungsvorgang für ein beliebiges Daten Segment benötigt, das Auffüll Vorgänge enthält.
  - Zeit Berechnungen sollten gemäß der Anleitung zum Abrufen von [Zeitstempeln mit hoher Auflösung](/windows/desktop/sysinfo/acquiring-high-resolution-time-stamps)erfolgen, nicht mithilfe <xref:System.Environment.TickCount?displayProperty=nameWithType> (bei Rollover/Überlauf) oder durch Subtraktion von zwei Systemzeit Stempeln (unterliegen NTP-Anpassungs Fehlern).
  - Zeit Berechnungen müssen den Entschlüsselungsvorgang einschließen, einschließlich aller potenziellen Ausnahmen in verwalteten Anwendungen oder C++ Anwendungen, die nicht nur am Ende aufgefüllt werden.
  - Wenn erfolgreich oder Fehler ermittelt wurde, muss das Zeit Steuerungs Gate einen Fehler zurückgeben, wenn es abläuft.
- Für Dienste, die eine nicht authentifizierte Entschlüsselung ausführen, sollte eine Überwachung vorhanden sein, um zu erkennen, dass eine Flut von "ungültigen" Nachrichten durchlaufen wurde.
  - Beachten Sie, dass dieses Signal sowohl falsch positive Ergebnisse (Recht beschädigte Daten) als auch falsch negative negative Werte enthält (die Verteilung des Angriffs über einen ausreichend langen Zeitraum, um die Erkennung zu umgehen).

## <a name="finding-vulnerable-code---native-applications"></a>Auffinden von systemeigenen, anfälligen Code Anwendungen

Für Programme, die mit der Windows Cryptography: Next Generation (CNG)-Bibliothek erstellt werden:

- Der Entschlüsselungs Rückruf ist [bcryptentschlüsseln](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptdecrypt)und gibt das `BCRYPT_BLOCK_PADDING`-Flag an.
- Das Schlüssel Handle wurde initialisiert, indem [BCryptSetProperty](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptsetproperty) aufgerufen wurde und [BCRYPT_CHAINING_MODE](/windows/desktop/SecCNG/cng-property-identifiers#BCRYPT_CHAINING_MODE) auf `BCRYPT_CHAIN_MODE_CBC`festgelegt ist.
  - Da `BCRYPT_CHAIN_MODE_CBC` der Standardwert ist, hat der betroffene Code möglicherweise keinen Wert für `BCRYPT_CHAINING_MODE`zugewiesen.

Für Programme, die mit der älteren Windows-kryptografieapi erstellt werden:

- Der Entschlüsselungs Rückruf ist die Verwendung von [cryptentschlüsseln](/windows/desktop/api/wincrypt/nf-wincrypt-cryptdecrypt) mit `Final=TRUE`.
- Das Schlüssel Handle wurde initialisiert, indem [cryptsetkeyparam](/windows/desktop/api/wincrypt/nf-wincrypt-cryptsetkeyparam) mit [KP_MODE](/windows/desktop/api/wincrypt/nf-wincrypt-cryptgetkeyparam) auf `CRYPT_MODE_CBC`festgelegt wurde.
  - Da `CRYPT_MODE_CBC` der Standardwert ist, hat der betroffene Code möglicherweise keinen Wert für `KP_MODE`zugewiesen.

## <a name="finding-vulnerable-code---managed-applications"></a>Suchen von durch anfälligen Code verwalteten Anwendungen

- Der Entschlüsselungs Rückruf erfolgt an die <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor>-Methode oder die <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])>-Methode auf <xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>.
  - Dies umfasst die folgenden abgeleiteten Typen in .net, kann jedoch auch Typen von Drittanbietern einschließen:
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
- Die <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType>-Eigenschaft wurde auf <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType>, <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType>oder <xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType>festgelegt.
  - Da <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> der Standardwert ist, hat der betroffene Code möglicherweise nie die <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType>-Eigenschaft zugewiesen.
- Die <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType>-Eigenschaft wurde auf festgelegt <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType>
  - Da <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType> der Standardwert ist, hat der betroffene Code möglicherweise nie die <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType>-Eigenschaft zugewiesen.

## <a name="finding-vulnerable-code---cryptographic-message-syntax"></a>Auffinden von anfälligen Code-kryptografische Nachrichten Syntax

Eine nicht authentifizierte CMS EnvelopedData-Nachricht, deren verschlüsselter Inhalt den CBC-Modus von AES (2.16.840.1.101.3.4.1.2, 2.16.840.1.101.3.4.1.22, 2.16.840.1.101.3.4.1.42), des (1.3.14.3.2.7), 3DES (1.2.840.113549.3.7) oder RC2 (1.2.840.113549.3.2) verwendet, ist anfällig und Nachrichten, die beliebige andere Blockverschlüsselungsalgorithmen im CBC-Modus verwenden.

Obwohl streamchiffren nicht anfällig für diese besondere Schwachstelle sind, empfiehlt Microsoft, die Daten immer über die Überprüfung des contentverschlüsseltionalgorithmuswerts zu authentifizieren.

Bei verwalteten Anwendungen kann ein CMS EnvelopedData-BLOB als beliebiger Wert erkannt werden, der an <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>übermittelt wird.

Für native Anwendungen kann ein CMS EnvelopedData-BLOB als beliebiger Wert erkannt werden, der einem CMS-Handle über [cryptmsgupdate](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgupdate) bereitgestellt wird, dessen resultierende [CMSG_TYPE_PARAM](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsggetparam) `CMSG_ENVELOPED` und/oder der CMS-handle später eine `CMSG_CTRL_DECRYPT`-Anweisung über [cryptmsgcontrol](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgcontrol)sendet.

## <a name="vulnerable-code-example---managed"></a>Beispiel für anfälligen Code: verwaltet

Diese Methode liest ein Cookie und entschlüsselt es. es ist keine Daten Integritätsprüfung sichtbar. Daher kann der Inhalt eines Cookies, das von dieser Methode gelesen wird, vom Benutzer, der es empfangen hat, oder von einem Angreifer, der den verschlüsselten Cookie-Wert erhalten hat, angegriffen werden.

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

## <a name="example-code-following-recommended-practices---managed"></a>Beispielcode im Anschluss an Empfohlene Vorgehensweisen: verwaltet

Der folgende Beispielcode verwendet ein nicht standardmäßiges Nachrichtenformat

`cipher_algorithm_id || hmac_algorithm_id || hmac_tag || iv || ciphertext`

Dabei sind die `cipher_algorithm_id`-und `hmac_algorithm_id` Algorithmusbezeichner Anwendungs lokale (nicht standardmäßige) Darstellungen dieser Algorithmen. Diese Bezeichner sind in anderen Teilen des vorhandenen Messaging Protokolls möglicherweise sinnvoll, anstatt als bare, verketteten Bytestream.

In diesem Beispiel wird auch ein einzelner Hauptschlüssel verwendet, um einen Verschlüsselungsschlüssel und einen HMAC-Schlüssel abzuleiten. Dies dient als praktische Möglichkeit, eine einzeln verschlüsselte Anwendung in eine Dual-Key-Anwendung umzuwandeln und die beiden Schlüssel als unterschiedliche Werte beizubehalten. Außerdem wird sichergestellt, dass der HMAC-Schlüssel und der Verschlüsselungsschlüssel nicht aus der Synchronisierung kommen.

In diesem Beispiel wird eine <xref:System.IO.Stream> für die Verschlüsselung oder Entschlüsselung nicht akzeptiert. Mit dem aktuellen Datenformat wird die Verschlüsselung mit einem Durchlauf erschwert, da der `hmac_tag` Wert vor dem Chiffre Text liegt. Dieses Format wurde jedoch ausgewählt, da es alle Elemente fester Größe am Anfang beibehält, damit der Parser einfacher bleibt. Bei diesem Datenformat ist die One-Pass-Entschlüsselung möglich, obwohl ein Implementierer darauf hingewiesen wird, gethashandreset aufzurufen und das Ergebnis vor dem Aufruf von TransformFinalBlock zu überprüfen. Wenn Streaming-Verschlüsselung wichtig ist, ist möglicherweise ein anderer AE-Modus erforderlich.

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
