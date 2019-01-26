---
title: Zeitliche Steuerung Sicherheitsrisiken CBC-Modus symmetrische Entschlüsselung mithilfe von Abständen
description: Erfahren Sie, wie Sie erkennen und Minimieren von Sicherheitsrisiken der zeitlichen Steuerung mit Cipher Block Chaining (CBC) Modus symmetrische Entschlüsselung mithilfe von Abständen.
ms.date: 06/12/2018
author: blowdart
ms.author: mairaw
ms.openlocfilehash: 0f5f7d2032981d28445abe27f87a678ce2c74600
ms.sourcegitcommit: d9a0071d0fd490ae006c816f78a563b9946e269a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2019
ms.locfileid: "55066174"
---
# <a name="timing-vulnerabilities-with-cbc-mode-symmetric-decryption-using-padding"></a>Zeitliche Steuerung Sicherheitsrisiken CBC-Modus symmetrische Entschlüsselung mithilfe von Abständen

Microsoft ist davon überzeugt, dass es nicht mehr sicher ist, die Entschlüsselung von Daten, die mit dem Modus (Cipher Block Chaining, CBC), der symmetrischen Verschlüsselung verschlüsselt werden, wenn überprüfbare Auffüllung angewendet wurde, ohne zuerst die Integrität der verschlüsselte Text, sicherzustellen, mit Ausnahme von sehr spezifischen Bedingungen. Diese Bewertung basiert auf aktuell bekannte kryptografische Forschung. 

## <a name="introduction"></a>Einführung

Ein Abstand-Oracle-Angriff ist eine Art von Angriff auf verschlüsselte Daten, die den Angreifer den Inhalt der Daten, ohne zu wissen, den Schlüssel entschlüsseln können.

Eine Oracle bezieht sich auf eine "Informationen" dadurch eine Angreifer Informationen dazu, ob die Aktion, die sie ausführen richtig ist oder nicht. Stellen Sie sich vor einem Board Wiedergabe oder Karte Spiel mit einem untergeordneten Element. Wenn sie Face klicke, werden mit der ein Lächeln, da er davon ausgeht, sie ist zu einer Oracle ist ein guter Schachzug, Informationen zu. Sie können als der Gegner, der Oracle verwenden, entsprechend der Planung der nächsten Migration.

Auffüllung ist einem bestimmten kryptografischen Ausdruck. Einige Verschlüsselungen, die die Algorithmen, die zum Verschlüsseln Ihrer Daten verwendet werden, funktionieren auf Datenblöcke, wo jeder Block eine feste Größe hat. Wenn die Daten, die Sie verschlüsseln möchten nicht, die richtige Größe zum Ausfüllen der blockiert ist, werden Ihre Daten aufgefüllt, bis dies der Fall ist. Viele Formen der Auffüllung erfordern, Auffüllung immer vorhanden sein, auch wenn die ursprüngliche Eingabe der richtigen Größe war. Dadurch wird die Auffüllung bei der Entschlüsselung immer problemlos entfernt werden.

Zwei Dinge zusammenstellen, wird eine softwareimplementierung mit einer Oracle Auffüllung, ob die entschlüsselte Daten gültigen Auffüllung hat. Die Oracle ist möglicherweise etwas so einfaches wie Rückgabe eines Werts mit dem Text "Ungültigen Füllzeichen" oder etwas komplizierter ist vergleichbar mit dem Erstellen einer merklich anderen Zeit gültigen Block und ein ungültiger Block nicht verarbeitet.

Blockbasierte Verschlüsselungen haben eine andere Eigenschaft mit dem Namen des Modus, der die Beziehung zwischen Daten in den ersten Block auf die Daten in der zweite Block ermittelt, und so weiter. Einer der am häufigsten verwendeten Modi ist CBC. CBC führt einen erste zufällige Block, bekannt als den Initialisierungsvektor (IV), und den vorherigen Block mit dem Ergebnis der statischen Verschlüsselung soll so, dass dieselbe Nachricht verschlüsseln, mit dem gleichen Schlüssel immer die gleiche verschlüsselte Ausgabe erzeugt keine kombiniert.

Ein Angreifer kann eine Auffüllung Oracle, in Kombination mit CBC-Daten Strukturierung verwenden, um etwas geänderten Nachrichten zu senden, auf den Code, der die Oracle verfügbar macht und Daten zu senden, bis die Oracle er darüber informiert wird die Daten korrekt sind. Aus dieser Antwort kann der Angreifer die Nachricht byteweise entschlüsseln.

Moderne Computernetzwerke sind solche qualitativ hochwertige, dass ein Angreifer sehr klein (weniger als 0,1 ms) die Unterschiede bei der Ausführung auf Remotesystemen Zeit erkennen kann. Anwendungen, die, dass ein erfolgreicher Entschlüsselung kann nur passieren, wenn die Daten manipuliert wurde nicht angenommen werden, möglicherweise anfällig für Angriffe, Tools, die entwickelt wurden, um Unterschiede in der erfolgreiche und fehlgeschlagene Entschlüsselung zu beobachten. Während dieser Unterschied für die zeitliche Steuerung in einigen Sprachen und Bibliotheken wichtiger als andere sein mag, ist es nun davon ausgegangen, dass dies ist eine praktische Bedrohung für alle Sprachen und Bibliotheken, wenn die Anwendung für die Reaktion auf Fehler berücksichtigt wird.

Dieser Angriff basiert auf der Fähigkeit, ändern die verschlüsselten Daten und testen das Ergebnis mit der Oracle. Die einzige Möglichkeit, vollständig der Angriff zu entschärfen ist zum Erkennen von Änderungen auf die verschlüsselten Daten und zur Ausführung von Aktionen auf verweigern. Die standardmäßige Möglichkeit hierzu ist eine Signatur für die Daten zu erstellen und dieser Signatur zu überprüfen, bevor Vorgänge ausgeführt werden. Die Signatur muss überprüfbar sein, von der Angreifer kann nicht erstellt werden, andernfalls sie ändern die verschlüsselten Daten würden dann eine neue Signatur, die auf Grundlage der geänderten Daten zu berechnen. Eine häufige Art der entsprechenden Signatur wird als einen schlüsselgebundenen Hash Nachrichtenauthentifizierungscode (HMAC) bezeichnet. Ein HMAC, der verwendet wird, abweicht eine Prüfsumme, einen geheimen Schlüssel, bekannte nur für die Person, die den HMAC erzeugt und an die Person, die Überprüfung dauert. Sie können nicht ohne den Besitz des Schlüssels einen richtigen HMAC erzeugen. Wenn Sie Ihre Daten erhalten, Sie die verschlüsselten Daten, die HMAC, der den geheimen Schlüssel unabhängig zu berechnen, Sie den Absender Freigabe ein, und Vergleichen der HMAC, die sie mit der Sie gesendet berechnet. Dieser Vergleich muss ein konstanter Zeit, die andernfalls Sie hinzugefügt haben eine andere erkennbare Oracle, sodass eine andere Art von Angriff.

Mit Blockchiffren CBC sicher aufgefüllt werden, müssen Sie sie mit einem HMAC (oder eine andere datenintegritätsprüfung), die Sie überprüfen, verwenden einen Vergleich der Konstanten Zeit vor dem Versuch zum Entschlüsseln der Daten kombinieren, zusammengefasst. Da alle geänderte Nachrichten die gleiche Zeit eine Antwort erzeugt werden, wird der Angriff verhindert.

## <a name="who-is-vulnerable"></a>Wer ist anfällig

Dieses Sicherheitsrisiko gilt für verwalteten und systemeigenen Anwendungen, die ihre eigenen Ver- und Entschlüsselung ausführen. Hierzu zählen beispielsweise:

- Eine Anwendung, die ein Cookie für die spätere Entschlüsselung auf dem Server verschlüsselt.
- Eine datenbankanwendung, die bietet die Möglichkeit für Benutzer zum Einfügen von Daten in eine Tabelle, deren Spalten später entschlüsselt werden.
- Eine Anwendung, die auf die Verschlüsselung mit einem gemeinsam verwendeten Schlüssel zum Schützen der Daten während der Übertragung basieren die Datenübertragung.
- Eine Anwendung, die verschlüsselt und entschlüsselt die Nachrichten "der TLS-Tunnel innerhalb".

Beachten Sie, mithilfe von TLS allein nicht in diesen Szenarien schützen kann.

Betroffene Anwendung:

- Entschlüsselt Daten, die eine überprüfbare Paddingmodus, z. B. PKCS #7 oder ANSI X.923 mit CBC-Verschlüsselungsverfahren-Modus.
- Die Entschlüsselung vornimmt, ohne dass keine datenintegritätsprüfung (über einen MAC oder ein asymmetrischer digitale Signatur) ausgeführt.

Dies gilt auch für Anwendungen, die Abstraktionen baut auf den über den oberen Rand dieser Primitive Typen, z. B. die Cryptographic Message Syntax (PKCS #7/CMS) EnvelopedData-Struktur.

## <a name="related-areas-of-concern"></a>Verwandte Interessenbereiche

Research führte Microsoft, um weitere Informationen zu CBC-Meldungen befassen, die mit ISO 10126 äquivalente aufgefüllt, wenn die Nachricht eine bekannte oder vorhersagbaren Fußzeile-Struktur hat aufgefüllt werden. Inhalt ist z. B. gemäß den Regeln der W3C-XML-Verschlüsselungssyntax und Verarbeitung Empfehlung (Xmlenc, EncryptedXml) vorbereitet. Während die W3C-Anweisungen, die Nachricht signieren und Verschlüsseln von geeigneten Zeitpunkt angesehen wurde, empfiehlt Microsoft jetzt immer verschlüsselt dann-Anmeldung.

Anwendungsentwickler sollten immer überprüfen, ob ein asymmetrischer Signaturschlüssel, die Anwendbarkeit berücksichtigen, wie es keine inhärente Vertrauensstellung zwischen einem asymmetrischen Schlüssel und eine beliebige Nachricht ist.

## <a name="details"></a>Details

In der Vergangenheit gab es Konsens, die es wichtig ist, Verschlüsselung und wichtige Daten mithilfe von bedeutet z. B. HMAC oder RSA-Signaturen zu authentifizieren. Es wurde jedoch weniger klare Anleitungen, wie die Verschlüsselung und Authentifizierung Vorgänge zu sequenzieren. Aufgrund der Sicherheitsrisiken, die in diesem Artikel beschriebene ist die Microsoft Leitfaden jetzt immer das Paradigma "encrypt-Then-Sign" verwenden. D.h. zunächst verschlüsseln Sie Daten mithilfe eines symmetrischen Schlüssels, dann berechnen Sie ein MAC oder ein asymmetrisches über den verschlüsselten Text (verschlüsselte Daten). Daten entschlüsseln zu können, führen Sie das Gegenteil. Klicken Sie zunächst überprüfen, ob der MAC oder die Signatur der verschlüsselte Text, dann zu entschlüsseln.

Eine Klasse von Sicherheitslücken bekannt als "Auffüllung von Oracle-Angriffen" bekanntermaßen sich 10 Jahre lang vorhanden sind. Diese Sicherheitsrisiken Angreifer ein zum Entschlüsseln von Daten, die nicht mehr als 4096 versuchen pro Block von Daten mithilfe von symmetrischer Blöcke Algorithmen, wie z. B. AES und 3DES verschlüsselt. Stellen Sie diese Sicherheitsrisiken verwenden die Tatsache, die eine Blockierung Verschlüsselungen werden am häufigsten verwendet, mit überprüfbare Auffüllung Daten am Ende. Es wurde gefunden, wenn ein Angreifer verschlüsselten Text manipulieren und finden Sie heraus, ob die Manipulation einen Fehler im Format der Abstand am Ende verursacht, der Angreifer die Daten entschlüsselt werden kann.

Praktische Angriffe zunächst basieren auf Diensten, die verschiedenen Fehlercodes, je nachdem ob Auffüllung gültig sind, beispielsweise das Sicherheitsrisiko ASP.NET war zurückgibt [MS10-070](/security-updates/SecurityBulletins/2010/ms10-070). Allerdings ist der Auffassung Microsoft jetzt, dass es sehr praktisch, führen Sie ähnliche Angriffe. hierfür wird nur die Unterschiede beim Timing zwischen der Verarbeitung von gültigen und ungültigen Auffüllung handelt.

Vorausgesetzt, dass das Verschlüsselungsschema eine Signatur setzt und, die die Überprüfung der Signatur mit einer festen Runtime für eine bestimmte Länge der Daten (unabhängig von der der Inhalt) ausgeführt wird, kann die Integrität der Daten überprüft werden, alle Informationen zu verlassen, ohne ein Angreifer über eine [Seite Kanal](https://en.wikipedia.org/wiki/Side-channel_attack). Da die integritätsprüfung von manipulierten Nachrichten ablehnt, wird die Auffüllung Oracle Bedrohung verringert.

## <a name="guidance"></a>Empfehlungen

Zuallererst empfiehlt Microsoft, alle Daten, die Vertraulichkeit für Transport Layer Security (TLS), dem Nachfolger, Secure Sockets Layer (SSL) übertragen werden müssen.

Als Nächstes wird die Anwendung zu analysieren:

- Verstehen Sie genau, welche Verschlüsselung, die Sie durchführen und von den Plattformen und APIs, die Sie verwenden, welche Verschlüsselung bereitgestellt wird.
- Werden Sie sicher, dass jede Nutzung auf allen Ebenen des ein symmetrisches [Block Verschlüsselungsalgorithmus](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers), z. B. AES und 3DES im CBC-Modus wird die Verwendung von geheimen Schlüsseln datenintegritätsprüfung integrieren (einer asymmetrischen Signatur ein HMAC, oder den Verschlüsselungsmodus zu ändern. ein [authentifizierte Verschlüsselung](https://en.wikipedia.org/wiki/Authenticated_encryption) (AE) verwendet, z.B. GCM oder CCM).

Basierend auf dem neuesten forschungsstand, ist es im Allgemeinen davon ausgegangen, dass wenn Schritte für die Authentifizierung und Verschlüsselung nicht AE-Modi für die Verschlüsselung unabhängig voneinander ausgeführt werden, authentifizieren den verschlüsselten Text (verschlüsseln-dann-Anmeldung) die beste Option für die allgemeine ist. Jedoch keine allgemeingültige richtige Antwort zur Kryptografie, und diese Generalisierung ist nicht so gut wie gerichteten Ratschläge von einer professionellen Cryptographer.

Anwendungen, die nicht ihre messaging-Format zu ändern, aber nicht authentifizierte CBC Entschlüsselung werden empfohlen, um zu versuchen, z. B. Lösungen zu integrieren:

- Entschlüsseln Sie ohne den Entschlüsselungsmechanismus, um zu überprüfen oder Entfernen der Auffüllung:
  - Möglicher Abstände, die angewendet wurde, weiterhin benötigt, entfernt oder ignoriert werden, verschieben Sie die Last in Ihrer Anwendung.
  - Der Vorteil ist, dass die Überprüfung von Abstand und die Entfernung in andere Anwendung Daten Überprüfung Logik integriert werden können. Wenn die Überprüfung von Abstand und die bei der Überprüfung in konstanter Zeit ausgeführt werden können, wird das Risiko reduziert.
  - Da die Interpretation des Abstands um die wahrgenommene Nachrichtenlänge ändert, werden ggf. noch Informationen zur zeitlichen Steuerung, die von diesem Ansatz ausgegeben.
- Ändern Sie den Paddingmodus Entschlüsselung ISO10126:
  - ISO10126 Entschlüsselung Auffüllung ist kompatibel mit PKCS7 Verschlüsselung Auffüllung und ANSIX923 Verschlüsselung Auffüllung.
  - Ändern des Modus reduziert die Auffüllung-Oracle-Kenntnisse um 1 Byte und nicht den gesamten Block. Wenn der Inhalt eine bekannte Fußzeile, z. B. eine schließende XML-Element besitzt können jedoch verwandte Angriffe weiterhin, für den Rest der Nachricht Angriffe.
  - Dies auch verhindert nur-Text-Wiederherstellung in Situationen nicht, in denen der Angreifer Klartext mehrere Male mit einem Offset für die unterschiedlichen Nachrichten, die verschlüsselt werden umgewandelt werden kann.
- Die Auswertung eines Aufrufs Entschlüsselung der zeitlichen Steuerung Signal Befeuchten-Gate:
  - Die Berechnung des Haltezeit müssen mindestens über die maximale Zeitspanne, die der Entschlüsselungsvorgang für alle Datensegment dauern würde, die Auffüllung enthält.
  - Time Berechnungen sollte durchgeführt werden, gemäß den Anweisungen unter [Abrufen mit hoher Auflösung Zeitstempel](https://msdn.microsoft.com/library/windows/desktop/dn55340.aspx), nicht mithilfe von <xref:System.Environment.TickCount?displayProperty=nameWithType> (je nach Roll-Over/Überlauf) oder Subtraktion von zwei System Zeitstempel (gemäß den NTP-Anpassung (Fehler).
  - Zeit Berechnungen müssen einschließlich der Entschlüsselungsvorgang, einschließlich aller mögliche Ausnahmen in verwaltet werden oder C++-Anwendungen, die nicht nur am Ende aufgefüllt.
  - Wenn noch Erfolg oder Fehler ermittelt wurde, muss das Timing-Gate nach dessen Ablauf ein Fehler zurückgegeben.
- Dienste, die nicht authentifizierte Entschlüsselung durchführen müssen erkennen, dass eine Flut von "ungültig" Nachrichten über stammten überwachungslösung.
  - Beachten Sie, dass dieses Signal sowohl falsch positive Ergebnisse (legitimen beschädigte Daten) und falschen negativen Ergebnissen (Verteilen des Angriffs über einen ausreichend langen Zeitraum auf die Erkennung zu verhindern) enthält.

## <a name="finding-vulnerable-code---native-applications"></a>Suchen Sie nach anfälligen Codes - systemeigene Anwendungen

Für Programme, die für die Windows-Kryptografie erstellt werden: Next Generation (CNG)-Bibliothek:

- Der Entschlüsselung Aufruf [BCryptDecrypt](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptdecrypt)unter Angabe der `BCRYPT_BLOCK_PADDING` Flag.
- Das Schlüsselhandle wurde durch den Aufruf initialisiert ["BCryptSetProperty"](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptsetproperty) mit [BCRYPT_CHAINING_MODE](https://msdn.microsoft.com/library/windows/desktop/aa376211.aspx#BCRYPT_CHAINING_MODE) festgelegt `BCRYPT_CHAIN_MODE_CBC`.
  - Da `BCRYPT_CHAIN_MODE_CBC` ist die Standardeinstellung. betroffene Code möglicherweise keine Werte für zugewiesen `BCRYPT_CHAINING_MODE`.

Für Programme, die für die älteren Windows Kryptografie-API erstellt werden:

- Der Entschlüsselung Aufruf [CryptDecrypt](/windows/desktop/api/wincrypt/nf-wincrypt-cryptdecrypt) mit `Final=TRUE`.
- Das Schlüsselhandle wurde durch den Aufruf initialisiert [CryptSetKeyParam](/windows/desktop/api/wincrypt/nf-wincrypt-cryptsetkeyparam) mit [KP_MODE](/windows/desktop/api/wincrypt/nf-wincrypt-cryptgetkeyparam) festgelegt `CRYPT_MODE_CBC`.
  - Da `CRYPT_MODE_CBC` ist die Standardeinstellung. betroffene Code möglicherweise keine Werte für zugewiesen `KP_MODE`.

## <a name="finding-vulnerable-code---managed-applications"></a>Suchen nach anfälligen Codes - verwalteten Anwendungen

- Der Entschlüsselung Aufruf der <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor> oder <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])> Methoden <xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>.
  - Dies umfasst die folgenden abgeleiteten Typen in .NET, aber es kann auch von Drittanbietern Typen enthalten:
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
- Die <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> -Eigenschaft wurde festgelegt, um <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType>, <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType>, oder <xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType>.
  - Da <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> ist die Standardeinstellung. betroffene Code nie zugewiesen haben die <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> Eigenschaft.
- Die <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> Eigenschaft auf festgelegt wurde <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType>
  - Da <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType> ist die Standardeinstellung. betroffene Code nie zugewiesen haben die <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> Eigenschaft.

## <a name="finding-vulnerable-code---cryptographic-message-syntax"></a>Suchen Sie nach anfälligen Codes - cryptographic Message syntax

Eine nicht authentifizierte CMS EnvelopedData-Nachricht, deren verschlüsselte Inhalte CBC-Modus von AES (2.16.840.1.101.3.4.1.2, 2.16.840.1.101.3.4.1.22, 2.16.840.1.101.3.4.1.42), DES (1.3.14.3.2.7), 3DES verwendet (1.2.840.113549.3.7) oder RC2 (1.2.840.113549.3.2) ist anfällig ist, Nachrichten, die auch als mit anderen Blockverschlüsselungsalgorithmen im CBC-Modus.

Während streamchiffren nicht anfällig für diese Sicherheitslücke sind, empfiehlt Microsoft immer die Daten über das Überprüfen des Wertes ContentEncryptionAlgorithm authentifizieren.

Für verwaltete Anwendungen erkannt eine CMS-EnvelopedData Blob sein kann als beliebiger Wert, der an <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>.

Für native Anwendungen kann als jeder Wert bereitgestellt, um ein Handle CMS über ein CMS EnvelopedData Blob erkannt werden [CryptMsgUpdate](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgupdate) , dessen resultierende [CMSG_TYPE_PARAM](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsggetparam) ist `CMSG_ENVELOPED` und/oder das CMS-Handle ist später gesendet eine `CMSG_CTRL_DECRYPT` Anweisung über [CryptMsgControl](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgcontrol).

## <a name="vulnerable-code-example---managed"></a>Anfälligen Codes-Beispiel – verwaltet

Diese Methode liest einen Cookie und entschlüsselt, und keine datenintegritätsprüfung wird angezeigt. Aus diesem Grund können den Inhalt eines Cookies, die von dieser Methode gelesen wird angegriffen werden, indem der Benutzer, die sie empfangen oder jeder Angreifer, der den Wert des verschlüsselten Cookie erhalten hat.

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

## <a name="example-code-following-recommended-practices---managed"></a>Beispiel für Code folgenden empfohlenen Methoden - verwaltet

Der folgende Code verwendet das Format nicht standardmäßige nachrichtenerstellung

`cipher_algorithm_id || hmac_algorithm_id || hmac_tag || iv || ciphertext`

in denen die `cipher_algorithm_id` und `hmac_algorithm_id` Algorithmusbezeichner werden lokalen (nicht standardmäßige) Darstellungen dieser Algorithmen. Dieser Bezeichner können in andere Teile Ihrer vorhandenen messaging-Protokoll statt als ein bare verketteten Bytestream sinnvoll.

Dieses Beispiel verwendet auch einen einzelnen Hauptschlüssel sowohl einen Verschlüsselungsschlüssel und HMAC-Schlüssel abgeleitet werden. Dies wird sowohl zur Vereinfachung bereitgestellt, für das Aktivieren einer Anwendung einfach als Schlüssel, der in einer Dual-verschlüsselt-Anwendung, und ermutigen, halten die beiden Schlüssel als unterschiedliche Werte. Es wird weiter sichergestellt, dass die HMAC-Schlüssel und den Verschlüsselungsschlüssel für nicht synchronisierte erhalten.

In diesem Beispiel akzeptiert keine <xref:System.IO.Stream> für die Verschlüsselung oder Entschlüsselung. Die aktuellen Daten Format erleichtert das einmalige verschlüsseln schwierig da die `hmac_tag` Wert vorangestellt ist, den verschlüsselten Text. Allerdings wurde dieses Format gewählt, da es alle Elemente der fester Größe beibehält, zu den Parser einfacher zu halten. Dieses Format für Daten ist eine durchlaufende entschlüsseln möglich, obwohl ein Implementierer GetHashAndReset aufrufen, und überprüfen das Ergebnis vor dem Aufrufen von TransformFinalBlock hingewiesen wird. Wenn die streaming-Verschlüsselung wichtig ist, kann ein anderen AE-Modus erforderlich sein.

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
