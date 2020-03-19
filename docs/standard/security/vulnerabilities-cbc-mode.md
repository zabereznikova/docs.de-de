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
# <a name="timing-vulnerabilities-with-cbc-mode-symmetric-decryption-using-padding"></a><span data-ttu-id="d220e-103">Verwenden der Auffüllung für die Zeitsteuerung bei Sicherheitsrisiken mit symmetrischer Entschlüsselung im CBC-Modus</span><span class="sxs-lookup"><span data-stu-id="d220e-103">Timing vulnerabilities with CBC-mode symmetric decryption using padding</span></span>

<span data-ttu-id="d220e-104">Microsoft ist der Ansicht, dass es nicht mehr sicher ist, Daten zu entschlüsseln, die mit dem CBC-Modus (Cipher-Block-Chaining) verschlüsselt sind, wenn überprüfbare Auffüllungen angewendet wurden, ohne zuvor die Integrität des Verschlüsselungstextes zu gewährleisten, mit Ausnahme von sehr spezifischen Umständen.</span><span class="sxs-lookup"><span data-stu-id="d220e-104">Microsoft believes that it's no longer safe to decrypt data encrypted with the Cipher-Block-Chaining (CBC) mode of symmetric encryption when verifiable padding has been applied without first ensuring the integrity of the ciphertext, except for very specific circumstances.</span></span> <span data-ttu-id="d220e-105">Dieses Urteil basiert auf derzeit bekannten kryptografischen Forschungen.</span><span class="sxs-lookup"><span data-stu-id="d220e-105">This judgement is based on currently known cryptographic research.</span></span>

## <a name="introduction"></a><span data-ttu-id="d220e-106">Einführung</span><span class="sxs-lookup"><span data-stu-id="d220e-106">Introduction</span></span>

<span data-ttu-id="d220e-107">Ein Auffüllungs-Orakelangriff ist eine Art von Angriff auf verschlüsselte Daten, die es dem Angreifer ermöglicht, den Inhalt der Daten zu entschlüsseln, ohne den Schlüssel zu kennen.</span><span class="sxs-lookup"><span data-stu-id="d220e-107">A padding oracle attack is a type of attack against encrypted data that allows the attacker to decrypt the contents of the data, without knowing the key.</span></span>

<span data-ttu-id="d220e-108">Ein Orakel bezieht sich auf ein "Tell", das einem Angreifer Informationen darüber gibt, ob die ausgeführte Aktion richtig ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="d220e-108">An oracle refers to a "tell" which gives an attacker information about whether the action they're executing is correct or not.</span></span> <span data-ttu-id="d220e-109">Stellen Sie sich vor, Sie spielen ein Brett- oder Kartenspiel mit einem Kind.</span><span class="sxs-lookup"><span data-stu-id="d220e-109">Imagine playing a board or card game with a child.</span></span> <span data-ttu-id="d220e-110">Wenn ihr Gesicht mit einem großen Lächeln aufleuchtet, weil sie denken, dass sie im Begriff sind, einen guten Zug zu machen, ist das ein Orakel.</span><span class="sxs-lookup"><span data-stu-id="d220e-110">When their face lights up with a big smile because they think they're about to make a good move, that's an oracle.</span></span> <span data-ttu-id="d220e-111">Sie als Gegner können dieses Orakel verwenden, um Ihren nächsten Zug entsprechend zu planen.</span><span class="sxs-lookup"><span data-stu-id="d220e-111">You, as the opponent, can use this oracle to plan your next move appropriately.</span></span>

<span data-ttu-id="d220e-112">Padding ist ein spezifischer kryptografischer Begriff.</span><span class="sxs-lookup"><span data-stu-id="d220e-112">Padding is a specific cryptographic term.</span></span> <span data-ttu-id="d220e-113">Einige Chiffren, d. h. die Algorithmen, die zum Verschlüsseln Ihrer Daten verwendet werden, arbeiten an Datenblöcken, bei denen jeder Block eine feste Größe hat.</span><span class="sxs-lookup"><span data-stu-id="d220e-113">Some ciphers, which are the algorithms used to encrypt your data, work on blocks of data where each block is a fixed size.</span></span> <span data-ttu-id="d220e-114">Wenn die Zuschlüsseln der Daten nicht die richtige Größe zum Ausfüllen der Blöcke haben, werden die Daten aufgefüllt, bis dies der Grund ist.</span><span class="sxs-lookup"><span data-stu-id="d220e-114">If the data you want to encrypt isn't the right size to fill the blocks, your data is padded until it does.</span></span> <span data-ttu-id="d220e-115">Viele Formen der Polsterung erfordern, dass Die polsterung immer vorhanden ist, auch wenn die ursprüngliche Eingabe die richtige Größe hatte.</span><span class="sxs-lookup"><span data-stu-id="d220e-115">Many forms of padding require that padding to always be present, even if the original input was of the right size.</span></span> <span data-ttu-id="d220e-116">Dies ermöglicht es, die Polsterung immer sicher bei der Entschlüsselung entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="d220e-116">This allows the padding to always be safely removed upon decryption.</span></span>

<span data-ttu-id="d220e-117">Zusammengenommen zeigt eine Softwareimplementierung mit einem Auffüllungsorakel, ob entschlüsselte Daten über eine gültige Auffüllung verfügen.</span><span class="sxs-lookup"><span data-stu-id="d220e-117">Putting the two things together, a software implementation with a padding oracle reveals whether decrypted data has valid padding.</span></span> <span data-ttu-id="d220e-118">Das Orakel könnte etwas so Einfaches sein, wie die Rückgabe eines Werts, der "Ungültige Auffüllung" sagt, oder etwas Komplizierteres, wie eine messbar andere Zeit zu nehmen, um einen gültigen Block zu verarbeiten, im Gegensatz zu einem ungültigen Block.</span><span class="sxs-lookup"><span data-stu-id="d220e-118">The oracle could be something as simple as returning a value that says "Invalid padding" or something more complicated like taking a measurably different time to process a valid block as opposed to an invalid block.</span></span>

<span data-ttu-id="d220e-119">Blockbasierte Verschlüsselungen haben eine andere Eigenschaft, den so genannten Modus, der die Beziehung der Daten im ersten Block zu den Daten im zweiten Block bestimmt usw.</span><span class="sxs-lookup"><span data-stu-id="d220e-119">Block-based ciphers have another property, called the mode, which determines the relationship of data in the first block to the data in the second block, and so on.</span></span> <span data-ttu-id="d220e-120">Einer der am häufigsten verwendeten Modi ist CBC.</span><span class="sxs-lookup"><span data-stu-id="d220e-120">One of the most commonly used modes is CBC.</span></span> <span data-ttu-id="d220e-121">CBC führt einen anfänglichen zuzufälligen Block ein, der als Initialisierungsvektor (IV) bekannt ist, und kombiniert den vorherigen Block mit dem Ergebnis statischer Verschlüsselung, um ihn so zu machen, dass die Verschlüsselung derselben Nachricht mit demselben Schlüssel nicht immer die gleiche verschlüsselte Ausgabe erzeugt.</span><span class="sxs-lookup"><span data-stu-id="d220e-121">CBC introduces an initial random block, known as the Initialization Vector (IV), and combines the previous block with the result of static encryption to make it such that encrypting the same message with the same key doesn't always produce the same encrypted output.</span></span>

<span data-ttu-id="d220e-122">Ein Angreifer kann ein Auffüllungsorakel in Kombination mit der Struktur von CBC-Daten verwenden, um leicht geänderte Nachrichten an den Code zu senden, der das Orakel verfügbar macht, und weiterhin Daten senden, bis das Orakel ihnen mitteilt, dass die Daten korrekt sind.</span><span class="sxs-lookup"><span data-stu-id="d220e-122">An attacker can use a padding oracle, in combination with how CBC data is structured, to send slightly changed messages to the code that exposes the oracle, and keep sending data until the oracle tells them the data is correct.</span></span> <span data-ttu-id="d220e-123">Aus dieser Antwort kann der Angreifer das Nachrichtenbyte byte entschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="d220e-123">From this response, the attacker can decrypt the message byte by byte.</span></span>

<span data-ttu-id="d220e-124">Moderne Computernetzwerke sind von so hoher Qualität, dass ein Angreifer sehr kleine (weniger als 0,1 ms) Unterschiede in der Ausführungszeit auf Remote-Systemen erkennen kann.</span><span class="sxs-lookup"><span data-stu-id="d220e-124">Modern computer networks are of such high quality that an attacker can detect very small (less than 0.1 ms) differences in execution time on remote systems.</span></span><span data-ttu-id="d220e-125">Anwendungen, die davon ausgehen, dass eine erfolgreiche Entschlüsselung nur erfolgen kann, wenn die Daten nicht manipuliert wurden, können anfällig für Angriffe von Tools sein, die entworfen wurden, um Unterschiede bei der erfolgreichen und erfolglosen Entschlüsselung zu beobachten.</span><span class="sxs-lookup"><span data-stu-id="d220e-125"> Applications that are assuming that a successful decryption can only happen when the data wasn't tampered with may be vulnerable to attack from tools that are designed to observe differences in successful and unsuccessful decryption.</span></span> <span data-ttu-id="d220e-126">Obwohl dieser zeitliche Unterschied in einigen Sprachen oder Bibliotheken erheblicher sein kann als in anderen, wird nun angenommen, dass dies eine praktische Bedrohung für alle Sprachen und Bibliotheken ist, wenn die Reaktion der Anwendung auf Fehler berücksichtigt wird.</span><span class="sxs-lookup"><span data-stu-id="d220e-126">While this timing difference may be more significant in some languages or libraries than others, it's now believed that this is a practical threat for all languages and libraries when the application's response to failure is taken into account.</span></span>

<span data-ttu-id="d220e-127">Dieser Angriff basiert auf der Fähigkeit, die verschlüsselten Daten zu ändern und das Ergebnis mit dem Orakel zu testen.</span><span class="sxs-lookup"><span data-stu-id="d220e-127">This attack relies on the ability to change the encrypted data and test the result with the oracle.</span></span> <span data-ttu-id="d220e-128">Die einzige Möglichkeit, den Angriff vollständig zu mildern, besteht darin, Änderungen an den verschlüsselten Daten zu erkennen und keine Aktionen darauf auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d220e-128">The only way to fully mitigate the attack is to detect changes to the encrypted data and refuse to perform any actions on it.</span></span> <span data-ttu-id="d220e-129">Die Standardmethode hierzu besteht darin, eine Signatur für die Daten zu erstellen und diese Signatur zu überprüfen, bevor Vorgänge ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d220e-129">The standard way to do this is to create a signature for the data and validate that signature before any operations are performed.</span></span> <span data-ttu-id="d220e-130">Die Signatur muss überprüfbar sein, sie kann nicht vom Angreifer erstellt werden, da sie andernfalls die verschlüsselten Daten ändern und dann eine neue Signatur basierend auf den geänderten Daten berechnen würde.</span><span class="sxs-lookup"><span data-stu-id="d220e-130">The signature must be verifiable, it cannot be created by the attacker, otherwise they'd change the encrypted data, then compute a new signature based on the changed data.</span></span> <span data-ttu-id="d220e-131">Ein häufiger Typ geeigneter Signatur wird als Keyed-Hash-Nachrichtenauthentifizierungscode (Keyed-Hash Message Authentication Code, HMAC) bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="d220e-131">One common type of appropriate signature is known as a keyed-hash message authentication code (HMAC).</span></span> <span data-ttu-id="d220e-132">Ein HMAC unterscheidet sich von einer Prüfsumme dadurch, dass er einen geheimen Schlüssel benötigt, der nur der Person bekannt ist, die den HMAC herstellt, und der Person, die ihn validiert.</span><span class="sxs-lookup"><span data-stu-id="d220e-132">An HMAC differs from a checksum in that it takes a secret key, known only to the person producing the HMAC and to the person validating it.</span></span> <span data-ttu-id="d220e-133">Ohne den Besitz des Schlüssels können Sie keinen korrekten HMAC produzieren.</span><span class="sxs-lookup"><span data-stu-id="d220e-133">Without possession of the key, you can't produce a correct HMAC.</span></span> <span data-ttu-id="d220e-134">Wenn Sie Ihre Daten erhalten, nehmen Sie die verschlüsselten Daten, berechnen sie unabhängig voneinander den HMAC mit dem geheimen Schlüssel, den Sie und den Absender gemeinsam verwenden, und vergleichen dann den hMAC, den sie gesendet haben, mit dem von Ihnen berechneten.</span><span class="sxs-lookup"><span data-stu-id="d220e-134">When you receive your data, you'd take the encrypted data, independently compute the HMAC using the secret key you and the sender share, then compare the HMAC they sent against the one you computed.</span></span> <span data-ttu-id="d220e-135">Dieser Vergleich muss konstante Zeit sein, da Sie sonst ein anderes nachweisbares Orakel hinzugefügt haben, das eine andere Art von Angriff ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="d220e-135">This comparison must be constant time, otherwise you've added another detectable oracle, allowing a different type of attack.</span></span>

<span data-ttu-id="d220e-136">Zusammenfassend müssen Sie diese mit einem HMAC (oder einer anderen Datenintegritätsprüfung) kombinieren, den Sie mit einem konstanten Zeitvergleich überprüfen, bevor Sie versuchen, die Daten zu entschlüsseln, um gepolsterte CBC-Blockchiffren sicher zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d220e-136">In summary, to use padded CBC block ciphers safely, you must combine them with an HMAC (or another data integrity check) that you validate using a constant time comparison before trying to decrypt the data.</span></span> <span data-ttu-id="d220e-137">Da alle geänderten Nachrichten die gleiche Zeit in Anspruch nehmen, um eine Antwort zu erzeugen, wird der Angriff verhindert.</span><span class="sxs-lookup"><span data-stu-id="d220e-137">Since all altered messages take the same amount time to produce a response, the attack is prevented.</span></span>

## <a name="who-is-vulnerable"></a><span data-ttu-id="d220e-138">Wer ist verwundbar?</span><span class="sxs-lookup"><span data-stu-id="d220e-138">Who is vulnerable</span></span>

<span data-ttu-id="d220e-139">Diese Sicherheitsanfälligkeit gilt sowohl für verwaltete als auch für systemeigene Anwendungen, die ihre eigene Verschlüsselung und Entschlüsselung durchführen.</span><span class="sxs-lookup"><span data-stu-id="d220e-139">This vulnerability applies to both managed and native applications that are performing their own encryption and decryption.</span></span> <span data-ttu-id="d220e-140">Dazu gehören z. B.:</span><span class="sxs-lookup"><span data-stu-id="d220e-140">This includes, for example:</span></span>

- <span data-ttu-id="d220e-141">Eine Anwendung, die ein Cookie für die spätere Entschlüsselung auf dem Server verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="d220e-141">An application that encrypts a cookie for later decryption on the server.</span></span>
- <span data-ttu-id="d220e-142">Eine Datenbankanwendung, die Benutzern die Möglichkeit bietet, Daten in eine Tabelle einzufügen, deren Spalten später entschlüsselt werden.</span><span class="sxs-lookup"><span data-stu-id="d220e-142">A database application that provides the ability for users to insert data into a table whose columns are later decrypted.</span></span>
- <span data-ttu-id="d220e-143">Eine Datenübertragungsanwendung, die auf Verschlüsselung mit einem freigegebenen Schlüssel basiert, um die Daten während der Übertragung zu schützen.</span><span class="sxs-lookup"><span data-stu-id="d220e-143">A data transfer application that relies on encryption using a shared key to protect the data in transit.</span></span>
- <span data-ttu-id="d220e-144">Eine Anwendung, die Nachrichten "innerhalb" des TLS-Tunnels verschlüsselt und entschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="d220e-144">An application that encrypts and decrypts messages "inside" the TLS tunnel.</span></span>

<span data-ttu-id="d220e-145">Beachten Sie, dass die Verwendung von TLS allein Sie in diesen Szenarien möglicherweise nicht schützt.</span><span class="sxs-lookup"><span data-stu-id="d220e-145">Note that using TLS alone may not protect you in these scenarios.</span></span>

<span data-ttu-id="d220e-146">Eine anfällige Anwendung:</span><span class="sxs-lookup"><span data-stu-id="d220e-146">A vulnerable application:</span></span>

- <span data-ttu-id="d220e-147">Entschlüsselt Daten im CBC-Verschlüsselungsmodus mit einem überprüfbaren Auffüllungsmodus, z. B. PKCS-7 oder ANSI X.923.</span><span class="sxs-lookup"><span data-stu-id="d220e-147">Decrypts data using the CBC cipher mode with a verifiable padding mode, such as PKCS#7 or ANSI X.923.</span></span>
- <span data-ttu-id="d220e-148">Führt die Entschlüsselung durch, ohne eine Datenintegritätsprüfung durchgeführt zu haben (über einen MAC oder eine asymmetrische digitale Signatur).</span><span class="sxs-lookup"><span data-stu-id="d220e-148">Performs the decryption without having performed a data integrity check (via a MAC or an asymmetric digital signature).</span></span>

<span data-ttu-id="d220e-149">Dies gilt auch für Anwendungen, die auf Abstraktionen über diesen Primitiven basieren, z. B. die EnvelopedData-Struktur für Kryptografische Nachrichtensyntax (PKCS-7/CMS).</span><span class="sxs-lookup"><span data-stu-id="d220e-149">This also applies to applications built on top of abstractions over top of these primitives, such as the Cryptographic Message Syntax (PKCS#7/CMS) EnvelopedData structure.</span></span>

## <a name="related-areas-of-concern"></a><span data-ttu-id="d220e-150">Verwandte Bereiche, die Anlass zur Sorge geben</span><span class="sxs-lookup"><span data-stu-id="d220e-150">Related areas of concern</span></span>

<span data-ttu-id="d220e-151">Untersuchungen haben Microsoft dazu veranlasst, sich weiter sorgen über CBC-Nachrichten zu sein, die mit ISO 10126-äquivalenter Auffüllung gepolstert sind, wenn die Nachricht eine bekannte oder vorhersehbare Fußzeilenstruktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="d220e-151">Research has led Microsoft to be further concerned about CBC messages that are padded with ISO 10126-equivalent padding when the message has a well-known or predictable footer structure.</span></span> <span data-ttu-id="d220e-152">Beispielsweise Inhalte, die gemäß den Regeln der W3C XML Encryption Syntax and Processing Recommendation (xmlenc, EncryptedXml) erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="d220e-152">For example, content prepared under the rules of the W3C XML Encryption Syntax and Processing Recommendation (xmlenc, EncryptedXml).</span></span> <span data-ttu-id="d220e-153">Während die W3C-Anleitung zum Signieren der Nachricht dann als angemessen angesehen wurde, empfiehlt Microsoft nun, immer verschlüsselungs-dann-signieren zu tun.</span><span class="sxs-lookup"><span data-stu-id="d220e-153">While the W3C guidance to sign the message then encrypt was considered appropriate at the time, Microsoft now recommends always doing encrypt-then-sign.</span></span>

<span data-ttu-id="d220e-154">Anwendungsentwickler sollten immer darauf achten, die Anwendbarkeit eines asymmetrischen Signaturschlüssels zu überprüfen, da keine inhärente Vertrauensstellung zwischen einem asymmetrischen Schlüssel und einer beliebigen Nachricht besteht.</span><span class="sxs-lookup"><span data-stu-id="d220e-154">Application developers should always be mindful of verifying the applicability of an asymmetric signature key, as there's no inherent trust relationship between an asymmetric key and an arbitrary message.</span></span>

## <a name="details"></a><span data-ttu-id="d220e-155">Details</span><span class="sxs-lookup"><span data-stu-id="d220e-155">Details</span></span>

<span data-ttu-id="d220e-156">In der Vergangenheit gab es Konsens, dass es wichtig ist, wichtige Daten zu verschlüsseln und zu authentifizieren, indem Mittel wie HMAC- oder RSA-Signaturen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d220e-156">Historically, there has been consensus that it's important to both encrypt and authenticate important data, using means such as HMAC or RSA signatures.</span></span> <span data-ttu-id="d220e-157">Es gab jedoch weniger klare Anleitungen, wie die Verschlüsselungs- und Authentifizierungsvorgänge sequenziert werden.</span><span class="sxs-lookup"><span data-stu-id="d220e-157">However, there has been less clear guidance as to how to sequence the encryption and authentication operations.</span></span> <span data-ttu-id="d220e-158">Aufgrund der in diesem Artikel beschriebenen Sicherheitsanfälligkeit ist microsoftes Anleitung nun immer das Paradigma "verschlüsseln-dann-zeichen" zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d220e-158">Due to the vulnerability detailed in this article, Microsoft's guidance is now to always use the "encrypt-then-sign" paradigm.</span></span> <span data-ttu-id="d220e-159">Das heißt, zuerst Daten mit einem symmetrischen Schlüssel verschlüsseln, dann einen MAC oder eine asymmetrische Signatur über den Chiffretext (verschlüsselte Daten) berechnen.</span><span class="sxs-lookup"><span data-stu-id="d220e-159">That is, first encrypt data using a symmetric key, then compute a MAC or asymmetric signature over the ciphertext (encrypted data).</span></span> <span data-ttu-id="d220e-160">Führen Sie beim Entschlüsseln von Daten das Gegenteil aus.</span><span class="sxs-lookup"><span data-stu-id="d220e-160">When decrypting data, perform the reverse.</span></span> <span data-ttu-id="d220e-161">Bestätigen Sie zunächst den MAC oder die Signatur des Chiffretexts, und entschlüsseln Sie ihn dann.</span><span class="sxs-lookup"><span data-stu-id="d220e-161">First, confirm the MAC or signature of the ciphertext, then decrypt it.</span></span>

<span data-ttu-id="d220e-162">Eine Klasse von Schwachstellen, die als "Padding-Orakel-Angriffe" bekannt sind, gibt es seit über 10 Jahren.</span><span class="sxs-lookup"><span data-stu-id="d220e-162">A class of vulnerabilities known as "padding oracle attacks" have been known to exist for over 10 years.</span></span> <span data-ttu-id="d220e-163">Diese Sicherheitsanfälligkeiten ermöglichen es einem Angreifer, Daten zu entschlüsseln, die durch symmetrische Blockalgorithmen wie AES und 3DES verschlüsselt wurden, und verwenden nicht mehr als 4096 Versuche pro Datenblock.</span><span class="sxs-lookup"><span data-stu-id="d220e-163">These vulnerabilities allow an attacker to decrypt data encrypted by symmetric block algorithms, such as AES and 3DES, using no more than 4096 attempts per block of data.</span></span> <span data-ttu-id="d220e-164">Diese Sicherheitsanfälligkeiten nutzen die Tatsache, dass Blockchiffren am häufigsten mit überprüfbaren Auffüllungsdaten am Ende verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d220e-164">These vulnerabilities make use of the fact that block ciphers are most frequently used with verifiable padding data at the end.</span></span> <span data-ttu-id="d220e-165">Es wurde festgestellt, dass ein Angreifer die Daten entschlüsseln kann, wenn ein Angreifer mit Demischertext manipuliert und herausfinden kann, ob die Manipulation einen Fehler im Format des Auffüllens verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="d220e-165">It was found that if an attacker can tamper with ciphertext and find out whether the tampering caused an error in the format of the padding at the end, the attacker can decrypt the data.</span></span>

<span data-ttu-id="d220e-166">Anfänglich basierten praktische Angriffe auf Diensten, die unterschiedliche Fehlercodes zurückgeben würden, je nach, ob die Auffüllung gültig war, wie z. B. die ASP.NET Sicherheitsanfälligkeit [MS10-070](/security-updates/SecurityBulletins/2010/ms10-070).</span><span class="sxs-lookup"><span data-stu-id="d220e-166">Initially, practical attacks were based on services that would return different error codes based on whether padding was valid, such as the ASP.NET vulnerability [MS10-070](/security-updates/SecurityBulletins/2010/ms10-070).</span></span> <span data-ttu-id="d220e-167">Microsoft ist jedoch nun der Ansicht, dass es praktisch ist, ähnliche Angriffe durchzuführen, indem nur die zeitlichen Unterschiede zwischen gültiger und ungültiger Auffüllung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d220e-167">However, Microsoft now believes that it's practical to conduct similar attacks using only the differences in timing between processing valid and invalid padding.</span></span>

<span data-ttu-id="d220e-168">Sofern das Verschlüsselungsschema eine Signatur verwendet und die Signaturüberprüfung mit einer festen Laufzeit für eine bestimmte Datenlänge (unabhängig vom Inhalt) durchgeführt wird, kann die Datenintegrität überprüft werden, ohne dass informationen über einen [Seitenkanal](https://en.wikipedia.org/wiki/Side-channel_attack)an einen Angreifer abgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d220e-168">Provided that the encryption scheme employs a signature and that the signature verification is performed with a fixed runtime for a given length of data (irrespective of the contents), the data integrity can be verified without emitting any information to an attacker via a [side channel](https://en.wikipedia.org/wiki/Side-channel_attack).</span></span> <span data-ttu-id="d220e-169">Da die Integritätsprüfung alle manipulierten Nachrichten ablehnt, wird die Bedrohung durch das Auffüllen von Orakelen verringert.</span><span class="sxs-lookup"><span data-stu-id="d220e-169">Since the integrity check rejects any tampered messages, the padding oracle threat is mitigated.</span></span>

## <a name="guidance"></a><span data-ttu-id="d220e-170">Anleitungen</span><span class="sxs-lookup"><span data-stu-id="d220e-170">Guidance</span></span>

<span data-ttu-id="d220e-171">Zuallererst empfiehlt Microsoft, dass alle Daten, die vertraulich sind, über Transport Layer Security (TLS), den Nachfolger von Secure Sockets Layer (SSL), übertragen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="d220e-171">First and foremost, Microsoft recommends that any data that has confidentiality needs be transmitted over Transport Layer Security (TLS), the successor to Secure Sockets Layer (SSL).</span></span>

<span data-ttu-id="d220e-172">Analysieren Sie als Nächstes Ihre Anwendung, um:</span><span class="sxs-lookup"><span data-stu-id="d220e-172">Next, analyze your application to:</span></span>

- <span data-ttu-id="d220e-173">Verstehen Sie genau, welche Verschlüsselung Sie durchführen und welche Verschlüsselung von den von Ihnen verwendenden Plattformen und APIs bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="d220e-173">Understand precisely what encryption you're performing and what encryption is being provided by the platforms and APIs you're using.</span></span>
- <span data-ttu-id="d220e-174">Stellen Sie sicher, dass jede Verwendung auf jeder Ebene eines symmetrischen [Blockverschlüsselungsalgorithmus](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers), z. B. AES und 3DES, im CBC-Modus die Verwendung einer Überprüfung der Integrität geheimer Schlüssel (eine asymmetrische Signatur, ein HMAC oder das Ändern des Verschlüsselungsmodus in einen [authentifizierten Verschlüsselungsmodus](https://en.wikipedia.org/wiki/Authenticated_encryption) (AE) wie GCM oder CCM enthält.</span><span class="sxs-lookup"><span data-stu-id="d220e-174">Be certain that each usage at each layer of a symmetric [block cipher algorithm](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers), such as AES and 3DES, in CBC mode incorporate the use of a secret-keyed data integrity check (an asymmetric signature, an HMAC, or to change the cipher mode to an [authenticated encryption](https://en.wikipedia.org/wiki/Authenticated_encryption) (AE) mode such as GCM or CCM).</span></span>

<span data-ttu-id="d220e-175">Basierend auf der aktuellen Forschung wird allgemein angenommen, dass, wenn die Authentifizierungs- und Verschlüsselungsschritte unabhängig für Nicht-AE-Verschlüsselungsmodi ausgeführt werden, die Authentifizierung des Chiffretextes (Verschlüsselung des Zeichens) die beste allgemeine Option ist.</span><span class="sxs-lookup"><span data-stu-id="d220e-175">Based on the current research, it's generally believed that when the authentication and encryption steps are performed independently for non-AE modes of encryption, authenticating the ciphertext (encrypt-then-sign) is the best general option.</span></span> <span data-ttu-id="d220e-176">Allerdings gibt es keine einheitliche richtige Antwort auf Kryptographie und diese Verallgemeinerung ist nicht so gut wie gerichtete Ratschläge von einem professionellen Kryptographen.</span><span class="sxs-lookup"><span data-stu-id="d220e-176">However, there's no one-size-fits-all correct answer to cryptography and this generalization isn't as good as directed advice from a professional cryptographer.</span></span>

<span data-ttu-id="d220e-177">Anwendungen, die ihr Messagingformat nicht ändern können, aber nicht authentifizierte CBC-Entschlüsselung durchführen, sollten versuchen, Abschwächungen wie:</span><span class="sxs-lookup"><span data-stu-id="d220e-177">Applications that are unable to change their messaging format but perform unauthenticated CBC decryption are encouraged to try to incorporate mitigations such as:</span></span>

- <span data-ttu-id="d220e-178">Entschlüsseln, ohne dass der decryptor die Auffüllung überprüfen oder entfernen kann:</span><span class="sxs-lookup"><span data-stu-id="d220e-178">Decrypt without allowing the decryptor to verify or remove padding:</span></span>
  - <span data-ttu-id="d220e-179">Alle aufgebrachten Auffüllungen müssen noch entfernt oder ignoriert werden, Sie verschieben die Last in Ihre Anwendung.</span><span class="sxs-lookup"><span data-stu-id="d220e-179">Any padding that was applied still needs to be removed or ignored, you're moving the burden into your application.</span></span>
  - <span data-ttu-id="d220e-180">Der Vorteil besteht darin, dass die Überprüfung und Entfernung von Auffüllungen in andere Anwendungsdatenüberprüfungslogik integriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="d220e-180">The benefit is that the padding verification and removal can be incorporated into other application data verification logic.</span></span> <span data-ttu-id="d220e-181">Wenn die Überprüfung und Datenüberprüfung der Auffüllung in konstanter Zeit durchgeführt werden kann, wird die Bedrohung verringert.</span><span class="sxs-lookup"><span data-stu-id="d220e-181">If the padding verification and data verification can be done in constant time, the threat is reduced.</span></span>
  - <span data-ttu-id="d220e-182">Da die Interpretation der Auffüllung die wahrgenommene Nachrichtenlänge ändert, kann es immer noch Zeitinformationen geben, die von diesem Ansatz emittiert werden.</span><span class="sxs-lookup"><span data-stu-id="d220e-182">Since the interpretation of the padding changes the perceived message length, there may still be timing information emitted from this approach.</span></span>
- <span data-ttu-id="d220e-183">Ändern Sie den Entschlüsselungsauffüllungsmodus in ISO10126:</span><span class="sxs-lookup"><span data-stu-id="d220e-183">Change the decryption padding mode to ISO10126:</span></span>
  - <span data-ttu-id="d220e-184">ISO10126 Entschlüsselungsauffüllung ist kompatibel mit PKCS7-Verschlüsselungsauffüllung und ANSIX923-Verschlüsselungsauffüllung.</span><span class="sxs-lookup"><span data-stu-id="d220e-184">ISO10126 decryption padding is compatible with both PKCS7 encryption padding and ANSIX923 encryption padding.</span></span>
  - <span data-ttu-id="d220e-185">Durch das Ändern des Modus wird das Auffüllungs-Orakelwissen auf 1 Byte anstelle des gesamten Blocks reduziert.</span><span class="sxs-lookup"><span data-stu-id="d220e-185">Changing the mode reduces the padding oracle knowledge to 1 byte instead of the entire block.</span></span> <span data-ttu-id="d220e-186">Wenn der Inhalt jedoch über eine bekannte Fußzeile verfügt, z. B. ein schließendes XML-Element, können verwandte Angriffe den Rest der Nachricht weiterhin angreifen.</span><span class="sxs-lookup"><span data-stu-id="d220e-186">However, if the content has a well-known footer, such as a closing XML element, related attacks can continue to attack the rest of the message.</span></span>
  - <span data-ttu-id="d220e-187">Dies verhindert auch nicht die Wiederherstellung von Klartexten in Situationen, in denen der Angreifer den gleichen Klartext zwingen kann, mehrmals mit einem anderen Nachrichtenoffset verschlüsselt zu werden.</span><span class="sxs-lookup"><span data-stu-id="d220e-187">This also doesn't prevent plaintext recovery in situations where the attacker can coerce the same plaintext to be encrypted multiple times with a different message offset.</span></span>
- <span data-ttu-id="d220e-188">Gate die Auswertung eines Entschlüsselungsaufrufs, um das Timing-Signal zu dämpfen:</span><span class="sxs-lookup"><span data-stu-id="d220e-188">Gate the evaluation of a decryption call to dampen the timing signal:</span></span>
  - <span data-ttu-id="d220e-189">Die Berechnung der Haltezeit muss mindestens die maximale Zeitspanne betragen, die der Entschlüsselungsvorgang für jedes Datensegment in Anspruch nehmen würde, das aufgetärgemäß ist.</span><span class="sxs-lookup"><span data-stu-id="d220e-189">The computation of hold time must have a minimum in excess of the maximum amount of time the decryption operation would take for any data segment that contains padding.</span></span>
  - <span data-ttu-id="d220e-190">Zeitberechnungen sollten gemäß den Anleitungen unter [Erfassen von hochauflösenden Zeitstempeln](/windows/desktop/sysinfo/acquiring-high-resolution-time-stamps)durchgeführt werden, nicht durch Verwendung <xref:System.Environment.TickCount?displayProperty=nameWithType> (vorbehaltlich Rollover/Überlauf) oder Subtrahieren von zwei Systemzeitstempeln (vorbehaltlich NTP-Anpassungsfehlern).</span><span class="sxs-lookup"><span data-stu-id="d220e-190">Time computations should be done according to the guidance in [Acquiring high-resolution time stamps](/windows/desktop/sysinfo/acquiring-high-resolution-time-stamps), not by using <xref:System.Environment.TickCount?displayProperty=nameWithType> (subject to roll-over/overflow) or subtracting two system timestamps (subject to NTP adjustment errors).</span></span>
  - <span data-ttu-id="d220e-191">Zeitberechnungen müssen den Entschlüsselungsvorgang einschließlich aller potenziellen Ausnahmen in verwalteten oder C++-Anwendungen einschließen und nicht nur am Ende aufgepolstert werden.</span><span class="sxs-lookup"><span data-stu-id="d220e-191">Time computations must be inclusive of the decryption operation including all potential exceptions in managed or C++ applications, not just padded onto the end.</span></span>
  - <span data-ttu-id="d220e-192">Wenn Erfolg oder Misserfolg noch feststeht, muss das Timing-Gate einen Fehler zurückgeben, wenn es abläuft.</span><span class="sxs-lookup"><span data-stu-id="d220e-192">If success or failure has been determined yet, the timing gate needs to return failure when it expires.</span></span>
- <span data-ttu-id="d220e-193">Dienste, die eine nicht authentifizierte Entschlüsselung durchführen, sollten über eine Überwachung verfügen, um festzustellen, dass eine Flut von "ungültigen" Nachrichten durchgekommen ist.</span><span class="sxs-lookup"><span data-stu-id="d220e-193">Services that are performing unauthenticated decryption should have monitoring in place to detect that a flood of "invalid" messages has come through.</span></span>
  - <span data-ttu-id="d220e-194">Denken Sie daran, dass dieses Signal sowohl falsche Positivmeldungen (rechtmäßig beschädigte Daten) als auch falsche Negative (Verbreitung des Angriffs über einen ausreichend langen Zeitpunkt, um der Erkennung zu entgehen) enthält.</span><span class="sxs-lookup"><span data-stu-id="d220e-194">Bear in mind that this signal carries both false positives (legitimately corrupted data) and false negatives (spreading out the attack over a sufficiently long time to evade detection).</span></span>

## <a name="finding-vulnerable-code---native-applications"></a><span data-ttu-id="d220e-195">Suchen von anfälligem Code – systemeigene Anwendungen</span><span class="sxs-lookup"><span data-stu-id="d220e-195">Finding vulnerable code - native applications</span></span>

<span data-ttu-id="d220e-196">Für Programme, die für die Windows Cryptography: Next Generation (CNG)-Bibliothek erstellt wurden:</span><span class="sxs-lookup"><span data-stu-id="d220e-196">For programs built against the Windows Cryptography: Next Generation (CNG) library:</span></span>

- <span data-ttu-id="d220e-197">Der Entschlüsselungsaufruf ist [an BCryptDecrypt](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptdecrypt), die Angabe des `BCRYPT_BLOCK_PADDING` Flags.</span><span class="sxs-lookup"><span data-stu-id="d220e-197">The decryption call is to [BCryptDecrypt](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptdecrypt), specifying the `BCRYPT_BLOCK_PADDING` flag.</span></span>
- <span data-ttu-id="d220e-198">Das Schlüsselhandle wurde initialisiert, indem [BCryptSetProperty](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptsetproperty) mit [BCRYPT_CHAINING_MODE](/windows/desktop/SecCNG/cng-property-identifiers#BCRYPT_CHAINING_MODE) auf festgelegt `BCRYPT_CHAIN_MODE_CBC`wurde.</span><span class="sxs-lookup"><span data-stu-id="d220e-198">The key handle has been initialized by calling [BCryptSetProperty](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptsetproperty) with [BCRYPT_CHAINING_MODE](/windows/desktop/SecCNG/cng-property-identifiers#BCRYPT_CHAINING_MODE) set to `BCRYPT_CHAIN_MODE_CBC`.</span></span>
  - <span data-ttu-id="d220e-199">Da `BCRYPT_CHAIN_MODE_CBC` es sich um den Standardcode handelt, hat der betroffene Code möglicherweise keinen Wert für `BCRYPT_CHAINING_MODE`zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="d220e-199">Since `BCRYPT_CHAIN_MODE_CBC` is the default, affected code may not have assigned any value for `BCRYPT_CHAINING_MODE`.</span></span>

<span data-ttu-id="d220e-200">Für Programme, die für die ältere Windows Cryptographic API erstellt wurden:</span><span class="sxs-lookup"><span data-stu-id="d220e-200">For programs built against the older Windows Cryptographic API:</span></span>

- <span data-ttu-id="d220e-201">Der Entschlüsselungsaufruf ist `Final=TRUE` [CryptDecrypt](/windows/desktop/api/wincrypt/nf-wincrypt-cryptdecrypt) mit .</span><span class="sxs-lookup"><span data-stu-id="d220e-201">The decryption call is to [CryptDecrypt](/windows/desktop/api/wincrypt/nf-wincrypt-cryptdecrypt) with `Final=TRUE`.</span></span>
- <span data-ttu-id="d220e-202">Das Schlüsselhandle wurde initialisiert, indem [CryptSetKeyParam](/windows/desktop/api/wincrypt/nf-wincrypt-cryptsetkeyparam) aufgerufen wurde, wobei [KP_MODE](/windows/desktop/api/wincrypt/nf-wincrypt-cryptgetkeyparam) auf festgelegt `CRYPT_MODE_CBC`ist.</span><span class="sxs-lookup"><span data-stu-id="d220e-202">The key handle has been initialized by calling [CryptSetKeyParam](/windows/desktop/api/wincrypt/nf-wincrypt-cryptsetkeyparam) with [KP_MODE](/windows/desktop/api/wincrypt/nf-wincrypt-cryptgetkeyparam) set to `CRYPT_MODE_CBC`.</span></span>
  - <span data-ttu-id="d220e-203">Da `CRYPT_MODE_CBC` es sich um den Standardcode handelt, hat der betroffene Code möglicherweise keinen Wert für `KP_MODE`zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="d220e-203">Since `CRYPT_MODE_CBC` is the default, affected code may not have assigned any value for `KP_MODE`.</span></span>

## <a name="finding-vulnerable-code---managed-applications"></a><span data-ttu-id="d220e-204">Suchen von anfälligem Code – verwaltete Anwendungen</span><span class="sxs-lookup"><span data-stu-id="d220e-204">Finding vulnerable code - managed applications</span></span>

- <span data-ttu-id="d220e-205">Der Entschlüsselungsaufruf <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor> ist <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])> an <xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>die oder Methoden auf .</span><span class="sxs-lookup"><span data-stu-id="d220e-205">The decryption call is to the <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor> or <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])> methods on <xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>.</span></span>
  - <span data-ttu-id="d220e-206">Dies umfasst die folgenden abgeleiteten Typen innerhalb von .NET, kann aber auch Typen von Drittanbietern enthalten:</span><span class="sxs-lookup"><span data-stu-id="d220e-206">This includes the following derived types within the .NET, but may also include third-party types:</span></span>
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
- <span data-ttu-id="d220e-207">Die <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> Eigenschaft wurde <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType>auf <xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType>, oder festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d220e-207">The <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> property was set to <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType>, <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType>, or <xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType>.</span></span>
  - <span data-ttu-id="d220e-208">Da <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> die Standardversion vorliegt, hat <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> der betroffene Code die Eigenschaft möglicherweise nie zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="d220e-208">Since <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> is the default, affected code may never have assigned the <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> property.</span></span>
- <span data-ttu-id="d220e-209">Die <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> Eigenschaft wurde auf<xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="d220e-209">The <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> property was set to <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType></span></span>
  - <span data-ttu-id="d220e-210">Da <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType> die Standardversion vorliegt, hat <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> der betroffene Code die Eigenschaft möglicherweise nie zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="d220e-210">Since <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType> is the default, affected code may never have assigned the <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> property.</span></span>

## <a name="finding-vulnerable-code---cryptographic-message-syntax"></a><span data-ttu-id="d220e-211">Suchen von anfälligem Code - Kryptografie-Nachrichtensyntax</span><span class="sxs-lookup"><span data-stu-id="d220e-211">Finding vulnerable code - cryptographic message syntax</span></span>

<span data-ttu-id="d220e-212">Eine nicht authentifizierte CMS EnvelopedData-Nachricht, deren verschlüsselter Inhalt den CBC-Modus von AES verwendet (2.16.840.1.101.3.4.1.2, 2.16.840.1.101.3.4.1.22, 2.16.840.1.101.3.4.1.42), DES (1.3.14.3.2.7), 3DES (1.2.840.113549.3.7) oder RC2 (1.2.840.113549.3.2) sowie Nachrichten, die andere Blockchiffrealgorithmen im CBC-Modus verwenden.</span><span class="sxs-lookup"><span data-stu-id="d220e-212">An unauthenticated CMS EnvelopedData message whose encrypted content uses the CBC mode of AES (2.16.840.1.101.3.4.1.2, 2.16.840.1.101.3.4.1.22, 2.16.840.1.101.3.4.1.42), DES (1.3.14.3.2.7), 3DES (1.2.840.113549.3.7) or RC2 (1.2.840.113549.3.2) is vulnerable, as well as messages using any other block cipher algorithms in CBC mode.</span></span>

<span data-ttu-id="d220e-213">Während Streamchiffren für diese besondere Sicherheitsanfälligkeit nicht anfällig sind, empfiehlt Microsoft, die Daten immer über die Überprüfung des ContentEncryptionAlgorithm-Werts zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="d220e-213">While stream ciphers aren't susceptible to this particular vulnerability, Microsoft recommends always authenticating the data over inspecting the ContentEncryptionAlgorithm value.</span></span>

<span data-ttu-id="d220e-214">Bei verwalteten Anwendungen kann ein CMS EnvelopedData-Blob als <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>jeder Wert erkannt werden, der an übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="d220e-214">For managed applications, a CMS EnvelopedData blob can be detected as any value that is passed to <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>.</span></span>

<span data-ttu-id="d220e-215">Bei systemeigenen Anwendungen kann ein CMS EnvelopedData-Blob als beliebiger Wert erkannt werden, `CMSG_ENVELOPED` der einem CMS-Handle über `CMSG_CTRL_DECRYPT` [CryptMsgUpdate](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgupdate) bereitgestellt wird, dessen resultierende [CMSG_TYPE_PARAM](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsggetparam) ist und/oder das CMS-Handle später eine Anweisung über [CryptMsgControl](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgcontrol)gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="d220e-215">For native applications, a CMS EnvelopedData blob can be detected as any value provided to a CMS handle via [CryptMsgUpdate](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgupdate) whose resulting [CMSG_TYPE_PARAM](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsggetparam) is `CMSG_ENVELOPED` and/or the CMS handle is later sent a `CMSG_CTRL_DECRYPT` instruction via [CryptMsgControl](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgcontrol).</span></span>

## <a name="vulnerable-code-example---managed"></a><span data-ttu-id="d220e-216">Beispiel für anfälligen Code - verwaltet</span><span class="sxs-lookup"><span data-stu-id="d220e-216">Vulnerable code example - managed</span></span>

<span data-ttu-id="d220e-217">Diese Methode liest ein Cookie und entschlüsselt es, und es ist nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="d220e-217">This method reads a cookie and decrypts it and no data integrity check is visible.</span></span> <span data-ttu-id="d220e-218">Daher kann der Inhalt eines Cookies, das von dieser Methode gelesen wird, von dem Benutzer, der es empfangen hat, oder von einem Angreifer, der den verschlüsselten Cookie-Wert erhalten hat, angegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="d220e-218">Therefore, the contents of a cookie that is read by this method can be attacked by the user who received it, or by any attacker who has obtained the encrypted cookie value.</span></span>

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

## <a name="example-code-following-recommended-practices---managed"></a><span data-ttu-id="d220e-219">Beispielcode nach empfohlenen Vorgehensweisen - verwaltet</span><span class="sxs-lookup"><span data-stu-id="d220e-219">Example code following recommended practices - managed</span></span>

<span data-ttu-id="d220e-220">Der folgende Beispielcode verwendet ein nicht standardmäßiges Nachrichtenformat von</span><span class="sxs-lookup"><span data-stu-id="d220e-220">The following sample code uses a non-standard message format of</span></span>

`cipher_algorithm_id || hmac_algorithm_id || hmac_tag || iv || ciphertext`

<span data-ttu-id="d220e-221">wobei `cipher_algorithm_id` die `hmac_algorithm_id` und-Algorithmus-Bezeichner anwendungslokal (nicht standardmäßige) Darstellungen dieser Algorithmen sind.</span><span class="sxs-lookup"><span data-stu-id="d220e-221">where the `cipher_algorithm_id` and `hmac_algorithm_id` algorithm identifiers are application-local (non-standard) representations of those algorithms.</span></span> <span data-ttu-id="d220e-222">Diese Bezeichner können in anderen Teilen Ihres vorhandenen Messagingprotokolls sinnvoll sein, anstatt als bloßer verketteter Bytestream.</span><span class="sxs-lookup"><span data-stu-id="d220e-222">These identifiers may make sense in other parts of your existing messaging protocol instead of as a bare concatenated bytestream.</span></span>

<span data-ttu-id="d220e-223">In diesem Beispiel wird auch ein einzelner Hauptschlüssel verwendet, um sowohl einen Verschlüsselungsschlüssel als auch einen HMAC-Schlüssel abzuleiten.</span><span class="sxs-lookup"><span data-stu-id="d220e-223">This example also uses a single master key to derive both an encryption key and an HMAC key.</span></span> <span data-ttu-id="d220e-224">Dies dient sowohl als Bequemlichkeit, um eine Anwendung mit einem einzelnen Schlüssel in eine Anwendung mit zwei Schlüsseln zu verwandeln, als auch als Ermutigung, die beiden Schlüssel als unterschiedliche Werte zu behalten.</span><span class="sxs-lookup"><span data-stu-id="d220e-224">This is provided both as a convenience for turning a singly-keyed application into a dual-keyed application, and to encourage keeping the two keys as different values.</span></span> <span data-ttu-id="d220e-225">Außerdem wird sichergestellt, dass der HMAC-Schlüssel und der Verschlüsselungsschlüssel nicht aus der Synchronisierung herauskommen.</span><span class="sxs-lookup"><span data-stu-id="d220e-225">It further guarantees that the HMAC key and encryption key can't get out of synchronization.</span></span>

<span data-ttu-id="d220e-226">Dieses Beispiel akzeptiert keine <xref:System.IO.Stream> für die Verschlüsselung oder Entschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="d220e-226">This sample doesn't accept a <xref:System.IO.Stream> for either encryption or decryption.</span></span> <span data-ttu-id="d220e-227">Das aktuelle Datenformat erschwert die Verschlüsselung von Einem Durchlauf, da der `hmac_tag` Wert dem Verschlüsselungstext vorangeht.</span><span class="sxs-lookup"><span data-stu-id="d220e-227">The current data format makes one-pass encrypt difficult because the `hmac_tag` value precedes the ciphertext.</span></span> <span data-ttu-id="d220e-228">Dieses Format wurde jedoch ausgewählt, da es alle Elemente fester Größe am Anfang hält, um den Parser einfacher zu halten.</span><span class="sxs-lookup"><span data-stu-id="d220e-228">However, this format was chosen because it keeps all of the fixed-size elements at the beginning to keep the parser simpler.</span></span> <span data-ttu-id="d220e-229">Mit diesem Datenformat ist eine Ein-Pass-Entschlüsselung möglich, obwohl ein Implementierer darauf hingewiesen wird, GetHashAndReset aufzurufen und das Ergebnis vor dem Aufruf von TransformFinalBlock zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="d220e-229">With this data format, one-pass decrypt is possible, though an implementer is cautioned to call GetHashAndReset and verify the result before calling TransformFinalBlock.</span></span> <span data-ttu-id="d220e-230">Wenn Streaming-Verschlüsselung wichtig ist, ist möglicherweise ein anderer AE-Modus erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d220e-230">If streaming encryption is important, then a different AE mode may be required.</span></span>

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
