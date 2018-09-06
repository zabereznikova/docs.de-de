---
title: Zeitliche Steuerung Sicherheitsrisiken CBC-Modus symmetrische Entschlüsselung mithilfe von Abständen
description: Erfahren Sie, wie Sie erkennen und Minimieren von Sicherheitsrisiken der zeitlichen Steuerung mit Cipher Block Chaining (CBC) Modus symmetrische Entschlüsselung mithilfe von Abständen.
ms.date: 06/12/2018
author: blowdart
ms.author: mairaw
ms.openlocfilehash: 6d16b6849bfd4744f1828cda38a537f842243c1d
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43881368"
---
# <a name="timing-vulnerabilities-with-cbc-mode-symmetric-decryption-using-padding"></a><span data-ttu-id="56a67-103">Zeitliche Steuerung Sicherheitsrisiken CBC-Modus symmetrische Entschlüsselung mithilfe von Abständen</span><span class="sxs-lookup"><span data-stu-id="56a67-103">Timing vulnerabilities with CBC-mode symmetric decryption using padding</span></span>

<span data-ttu-id="56a67-104">Microsoft ist davon überzeugt, dass es nicht mehr sicher ist, die Entschlüsselung von Daten, die mit dem Modus (Cipher Block Chaining, CBC), der symmetrischen Verschlüsselung verschlüsselt werden, wenn überprüfbare Auffüllung angewendet wurde, ohne zuerst die Integrität der verschlüsselte Text, sicherzustellen, mit Ausnahme von sehr spezifischen Bedingungen.</span><span class="sxs-lookup"><span data-stu-id="56a67-104">Microsoft believes that it's no longer safe to decrypt data encrypted with the Cipher-Block-Chaining (CBC) mode of symmetric encryption when verifiable padding has been applied without first ensuring the integrity of the ciphertext, except for very specific circumstances.</span></span> <span data-ttu-id="56a67-105">Diese Bewertung basiert auf aktuell bekannte kryptografische Forschung.</span><span class="sxs-lookup"><span data-stu-id="56a67-105">This judgement is based on currently known cryptographic research.</span></span> 

## <a name="introduction"></a><span data-ttu-id="56a67-106">Einführung</span><span class="sxs-lookup"><span data-stu-id="56a67-106">Introduction</span></span>

<span data-ttu-id="56a67-107">Ein Abstand-Oracle-Angriff ist eine Art von Angriff auf verschlüsselte Daten, die den Angreifer den Inhalt der Daten, ohne zu wissen, den Schlüssel entschlüsseln können.</span><span class="sxs-lookup"><span data-stu-id="56a67-107">A padding oracle attack is a type of attack against encrypted data that allows the attacker to decrypt the contents of the data, without knowing the key.</span></span>

<span data-ttu-id="56a67-108">Eine Oracle bezieht sich auf eine "Informationen" dadurch eine Angreifer Informationen dazu, ob die Aktion, die sie ausführen richtig ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="56a67-108">An oracle refers to a "tell" which gives an attacker information about whether the action they're executing is correct or not.</span></span> <span data-ttu-id="56a67-109">Stellen Sie sich vor einem Board Wiedergabe oder Karte Spiel mit einem untergeordneten Element.</span><span class="sxs-lookup"><span data-stu-id="56a67-109">Imagine playing a board or card game with a child.</span></span> <span data-ttu-id="56a67-110">Wenn sie Face klicke, werden mit der ein Lächeln, da er davon ausgeht, sie ist zu einer Oracle ist ein guter Schachzug, Informationen zu.</span><span class="sxs-lookup"><span data-stu-id="56a67-110">When her face lights up with a big smile because she thinks she's about to make a good move, that's an oracle.</span></span> <span data-ttu-id="56a67-111">Sie können als der Gegner, der Oracle verwenden, entsprechend der Planung der nächsten Migration.</span><span class="sxs-lookup"><span data-stu-id="56a67-111">You, as the opponent, can use this oracle to plan your next move appropriately.</span></span>

<span data-ttu-id="56a67-112">Auffüllung ist einem bestimmten kryptografischen Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="56a67-112">Padding is a specific cryptographic term.</span></span> <span data-ttu-id="56a67-113">Einige Verschlüsselungen, die die Algorithmen, die zum Verschlüsseln Ihrer Daten verwendet werden, funktionieren auf Datenblöcke, wo jeder Block eine feste Größe hat.</span><span class="sxs-lookup"><span data-stu-id="56a67-113">Some ciphers, which are the algorithms used to encrypt your data, work on blocks of data where each block is a fixed size.</span></span> <span data-ttu-id="56a67-114">Wenn die Daten, die Sie verschlüsseln möchten nicht, die richtige Größe zum Ausfüllen der blockiert ist, werden Ihre Daten aufgefüllt, bis dies der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="56a67-114">If the data you want to encrypt isn't the right size to fill the blocks, your data is padded until it does.</span></span> <span data-ttu-id="56a67-115">Viele Formen der Auffüllung erfordern, Auffüllung immer vorhanden sein, auch wenn die ursprüngliche Eingabe der richtigen Größe war.</span><span class="sxs-lookup"><span data-stu-id="56a67-115">Many forms of padding require that padding to always be present, even if the original input was of the right size.</span></span> <span data-ttu-id="56a67-116">Dadurch wird die Auffüllung bei der Entschlüsselung immer problemlos entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="56a67-116">This allows the padding to always be safely removed upon decryption.</span></span>

<span data-ttu-id="56a67-117">Zwei Dinge zusammenstellen, wird eine softwareimplementierung mit einer Oracle Auffüllung, ob die entschlüsselte Daten gültigen Auffüllung hat.</span><span class="sxs-lookup"><span data-stu-id="56a67-117">Putting the two things together, a software implementation with a padding oracle reveals whether decrypted data has valid padding.</span></span> <span data-ttu-id="56a67-118">Die Oracle ist möglicherweise etwas so einfaches wie Rückgabe eines Werts mit dem Text "Ungültigen Füllzeichen" oder etwas komplizierter ist vergleichbar mit dem Erstellen einer merklich anderen Zeit gültigen Block und ein ungültiger Block nicht verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="56a67-118">The oracle could be something as simple as returning a value that says "Invalid padding" or something more complicated like taking a measurably different time to process a valid block as opposed to an invalid block.</span></span>

<span data-ttu-id="56a67-119">Blockbasierte Verschlüsselungen haben eine andere Eigenschaft mit dem Namen des Modus, der die Beziehung zwischen Daten in den ersten Block auf die Daten in der zweite Block ermittelt, und so weiter.</span><span class="sxs-lookup"><span data-stu-id="56a67-119">Block-based ciphers have another property, called the mode, which determines the relationship of data in the first block to the data in the second block, and so on.</span></span> <span data-ttu-id="56a67-120">Einer der am häufigsten verwendeten Modi ist CBC.</span><span class="sxs-lookup"><span data-stu-id="56a67-120">One of the most commonly used modes is CBC.</span></span> <span data-ttu-id="56a67-121">CBC führt einen erste zufällige Block, bekannt als den Initialisierungsvektor (IV), und den vorherigen Block mit dem Ergebnis der statischen Verschlüsselung soll so, dass dieselbe Nachricht verschlüsseln, mit dem gleichen Schlüssel immer die gleiche verschlüsselte Ausgabe erzeugt keine kombiniert.</span><span class="sxs-lookup"><span data-stu-id="56a67-121">CBC introduces an initial random block, known as the Initialization Vector (IV), and combines the previous block with the result of static encryption to make it such that encrypting the same message with the same key doesn't always produce the same encrypted output.</span></span>

<span data-ttu-id="56a67-122">Ein Angreifer kann eine Auffüllung Oracle, in Kombination mit CBC-Daten Strukturierung verwenden, um etwas geänderten Nachrichten zu senden, auf den Code, der die Oracle verfügbar macht und Daten zu senden, bis die Oracle er darüber informiert wird die Daten korrekt sind.</span><span class="sxs-lookup"><span data-stu-id="56a67-122">An attacker can use a padding oracle, in combination with how CBC data is structured, to send slightly changed messages to the code that exposes the oracle, and keep sending data until the oracle tells them the data is correct.</span></span> <span data-ttu-id="56a67-123">Aus dieser Antwort kann der Angreifer die Nachricht byteweise entschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="56a67-123">From this response, the attacker can decrypt the message byte by byte.</span></span>

<span data-ttu-id="56a67-124">Moderne Computernetzwerke sind solche qualitativ hochwertige, dass ein Angreifer sehr klein (weniger als 0,1 ms) die Unterschiede bei der Ausführung auf Remotesystemen Zeit erkennen kann.</span><span class="sxs-lookup"><span data-stu-id="56a67-124">Modern computer networks are of such high quality that an attacker can detect very small (less than 0.1 ms) differences in execution time on remote systems.</span></span> <span data-ttu-id="56a67-125">Anwendungen, die, dass ein erfolgreicher Entschlüsselung kann nur passieren, wenn die Daten manipuliert wurde nicht angenommen werden, möglicherweise anfällig für Angriffe, Tools, die entwickelt wurden, um Unterschiede in der erfolgreiche und fehlgeschlagene Entschlüsselung zu beobachten.</span><span class="sxs-lookup"><span data-stu-id="56a67-125">Applications that are assuming that a successful decryption can only happen when the data wasn't tampered with may be vulnerable to attack from tools that are designed to observe differences in successful and unsuccessful decryption.</span></span> <span data-ttu-id="56a67-126">Während dieser Unterschied für die zeitliche Steuerung in einigen Sprachen und Bibliotheken wichtiger als andere sein mag, ist es nun davon ausgegangen, dass dies ist eine praktische Bedrohung für alle Sprachen und Bibliotheken, wenn die Anwendung für die Reaktion auf Fehler berücksichtigt wird.</span><span class="sxs-lookup"><span data-stu-id="56a67-126">While this timing difference may be more significant in some languages or libraries than others, it's now believed that this is a practical threat for all languages and libraries when the application's response to failure is taken into account.</span></span>

<span data-ttu-id="56a67-127">Dieser Angriff basiert auf der Fähigkeit, ändern die verschlüsselten Daten und testen das Ergebnis mit der Oracle.</span><span class="sxs-lookup"><span data-stu-id="56a67-127">This attack relies on the ability to change the encrypted data and test the result with the oracle.</span></span> <span data-ttu-id="56a67-128">Die einzige Möglichkeit, vollständig der Angriff zu entschärfen ist zum Erkennen von Änderungen auf die verschlüsselten Daten und zur Ausführung von Aktionen auf verweigern.</span><span class="sxs-lookup"><span data-stu-id="56a67-128">The only way to fully mitigate the attack is to detect changes to the encrypted data and refuse to perform any actions on it.</span></span> <span data-ttu-id="56a67-129">Die standardmäßige Möglichkeit hierzu ist eine Signatur für die Daten zu erstellen und dieser Signatur zu überprüfen, bevor Vorgänge ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="56a67-129">The standard way to do this is to create a signature for the data and validate that signature before any operations are performed.</span></span> <span data-ttu-id="56a67-130">Die Signatur muss überprüfbar sein, von der Angreifer kann nicht erstellt werden, andernfalls sie ändern die verschlüsselten Daten würden dann eine neue Signatur, die auf Grundlage der geänderten Daten zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="56a67-130">The signature must be verifiable, it cannot be created by the attacker, otherwise they'd change the encrypted data, then compute a new signature based on the changed data.</span></span> <span data-ttu-id="56a67-131">Eine häufige Art der entsprechenden Signatur wird als einen schlüsselgebundenen Hash Nachrichtenauthentifizierungscode (HMAC) bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="56a67-131">One common type of appropriate signature is known as a keyed-hash message authentication code (HMAC).</span></span> <span data-ttu-id="56a67-132">Ein HMAC, der verwendet wird, abweicht eine Prüfsumme, einen geheimen Schlüssel, bekannte nur für die Person, die den HMAC erzeugt und an die Person, die Überprüfung dauert.</span><span class="sxs-lookup"><span data-stu-id="56a67-132">An HMAC differs from a checksum in that it takes a secret key, known only to the person producing the HMAC and to the person validating it.</span></span> <span data-ttu-id="56a67-133">Sie können nicht ohne den Besitz des Schlüssels einen richtigen HMAC erzeugen.</span><span class="sxs-lookup"><span data-stu-id="56a67-133">Without possession of the key, you can't produce a correct HMAC.</span></span> <span data-ttu-id="56a67-134">Wenn Sie Ihre Daten erhalten, Sie die verschlüsselten Daten, die HMAC, der den geheimen Schlüssel unabhängig zu berechnen, Sie den Absender Freigabe ein, und Vergleichen der HMAC, die sie mit der Sie gesendet berechnet.</span><span class="sxs-lookup"><span data-stu-id="56a67-134">When you receive your data, you'd take the encrypted data, independently compute the HMAC using the secret key you and the sender share, then compare the HMAC they sent against the one you computed.</span></span> <span data-ttu-id="56a67-135">Dieser Vergleich muss ein konstanter Zeit, die andernfalls Sie hinzugefügt haben eine andere erkennbare Oracle, sodass eine andere Art von Angriff.</span><span class="sxs-lookup"><span data-stu-id="56a67-135">This comparison must be constant time, otherwise you've added another detectable oracle, allowing a different type of attack.</span></span>

<span data-ttu-id="56a67-136">Mit Blockchiffren CBC sicher aufgefüllt werden, müssen Sie sie mit einem HMAC (oder eine andere datenintegritätsprüfung), die Sie überprüfen, verwenden einen Vergleich der Konstanten Zeit vor dem Versuch zum Entschlüsseln der Daten kombinieren, zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="56a67-136">In summary, to use padded CBC block ciphers safely, you must combine them with an HMAC (or another data integrity check) that you validate using a constant time comparison before trying to decrypt the data.</span></span> <span data-ttu-id="56a67-137">Da alle geänderte Nachrichten die gleiche Zeit eine Antwort erzeugt werden, wird der Angriff verhindert.</span><span class="sxs-lookup"><span data-stu-id="56a67-137">Since all altered messages take the same amount time to produce a response, the attack is prevented.</span></span>

## <a name="who-is-vulnerable"></a><span data-ttu-id="56a67-138">Wer ist anfällig</span><span class="sxs-lookup"><span data-stu-id="56a67-138">Who is vulnerable</span></span>

<span data-ttu-id="56a67-139">Dieses Sicherheitsrisiko gilt für verwalteten und systemeigenen Anwendungen, die ihre eigenen Ver- und Entschlüsselung ausführen.</span><span class="sxs-lookup"><span data-stu-id="56a67-139">This vulnerability applies to both managed and native applications that are performing their own encryption and decryption.</span></span> <span data-ttu-id="56a67-140">Hierzu zählen beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="56a67-140">This includes, for example:</span></span>

- <span data-ttu-id="56a67-141">Eine Anwendung, die ein Cookie für die spätere Entschlüsselung auf dem Server verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="56a67-141">An application that encrypts a cookie for later decryption on the server.</span></span>
- <span data-ttu-id="56a67-142">Eine datenbankanwendung, die bietet die Möglichkeit für Benutzer zum Einfügen von Daten in eine Tabelle, deren Spalten später entschlüsselt werden.</span><span class="sxs-lookup"><span data-stu-id="56a67-142">A database application that provides the ability for users to insert data into a table whose columns are later decrypted.</span></span>
- <span data-ttu-id="56a67-143">Eine Anwendung, die auf die Verschlüsselung mit einem gemeinsam verwendeten Schlüssel zum Schützen der Daten während der Übertragung basieren die Datenübertragung.</span><span class="sxs-lookup"><span data-stu-id="56a67-143">A data transfer application that relies on encryption using a shared key to protect the data in transit.</span></span>
- <span data-ttu-id="56a67-144">Eine Anwendung, die verschlüsselt und entschlüsselt die Nachrichten "der TLS-Tunnel innerhalb".</span><span class="sxs-lookup"><span data-stu-id="56a67-144">An application that encrypts and decrypts messages "inside" the TLS tunnel.</span></span>

<span data-ttu-id="56a67-145">Beachten Sie, mithilfe von TLS allein nicht in diesen Szenarien schützen kann.</span><span class="sxs-lookup"><span data-stu-id="56a67-145">Note that using TLS alone may not protect you in these scenarios.</span></span>

<span data-ttu-id="56a67-146">Betroffene Anwendung:</span><span class="sxs-lookup"><span data-stu-id="56a67-146">A vulnerable application:</span></span>

- <span data-ttu-id="56a67-147">Entschlüsselt Daten, die eine überprüfbare Paddingmodus, z. B. PKCS #7 oder ANSI X.923 mit CBC-Verschlüsselungsverfahren-Modus.</span><span class="sxs-lookup"><span data-stu-id="56a67-147">Decrypts data using the CBC cipher mode with a verifiable padding mode, such as PKCS#7 or ANSI X.923.</span></span>
- <span data-ttu-id="56a67-148">Die Entschlüsselung vornimmt, ohne dass keine datenintegritätsprüfung (über einen MAC oder ein asymmetrischer digitale Signatur) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="56a67-148">Performs the decryption without having performed a data integrity check (via a MAC or an asymmetric digital signature).</span></span>

<span data-ttu-id="56a67-149">Dies gilt auch für Anwendungen, die Abstraktionen baut auf den über den oberen Rand dieser Primitive Typen, z. B. die Cryptographic Message Syntax (PKCS #7/CMS) EnvelopedData-Struktur.</span><span class="sxs-lookup"><span data-stu-id="56a67-149">This also applies to applications built on top of abstractions over top of these primitives, such as the Cryptographic Message Syntax (PKCS#7/CMS) EnvelopedData structure.</span></span>

## <a name="related-areas-of-concern"></a><span data-ttu-id="56a67-150">Verwandte Interessenbereiche</span><span class="sxs-lookup"><span data-stu-id="56a67-150">Related areas of concern</span></span>

<span data-ttu-id="56a67-151">Research führte Microsoft, um weitere Informationen zu CBC-Meldungen befassen, die mit ISO 10126 äquivalente aufgefüllt, wenn die Nachricht eine bekannte oder vorhersagbaren Fußzeile-Struktur hat aufgefüllt werden.</span><span class="sxs-lookup"><span data-stu-id="56a67-151">Research has led Microsoft to be further concerned about CBC messages that are padded with ISO 10126-equivalent padding when the message has a well-known or predictable footer structure.</span></span> <span data-ttu-id="56a67-152">Inhalt ist z. B. gemäß den Regeln der W3C-XML-Verschlüsselungssyntax und Verarbeitung Empfehlung (Xmlenc, EncryptedXml) vorbereitet.</span><span class="sxs-lookup"><span data-stu-id="56a67-152">For example, content prepared under the rules of the W3C XML Encryption Syntax and Processing Recommendation (xmlenc, EncryptedXml).</span></span> <span data-ttu-id="56a67-153">Während die W3C-Anweisungen, die Nachricht signieren und Verschlüsseln von geeigneten Zeitpunkt angesehen wurde, empfiehlt Microsoft jetzt immer verschlüsselt dann-Anmeldung.</span><span class="sxs-lookup"><span data-stu-id="56a67-153">While the W3C guidance to sign the message then encrypt was considered appropriate at the time, Microsoft now recommends always doing encrypt-then-sign.</span></span>

<span data-ttu-id="56a67-154">Anwendungsentwickler sollten immer überprüfen, ob ein asymmetrischer Signaturschlüssel, die Anwendbarkeit berücksichtigen, wie es keine inhärente Vertrauensstellung zwischen einem asymmetrischen Schlüssel und eine beliebige Nachricht ist.</span><span class="sxs-lookup"><span data-stu-id="56a67-154">Application developers should always be mindful of verifying the applicability of an asymmetric signature key, as there's no inherent trust relationship between an asymmetric key and an arbitrary message.</span></span>

## <a name="details"></a><span data-ttu-id="56a67-155">Details</span><span class="sxs-lookup"><span data-stu-id="56a67-155">Details</span></span>

<span data-ttu-id="56a67-156">In der Vergangenheit gab es Konsens, die es wichtig ist, Verschlüsselung und wichtige Daten mithilfe von bedeutet z. B. HMAC oder RSA-Signaturen zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="56a67-156">Historically, there has been consensus that it's important to both encrypt and authenticate important data, using means such as HMAC or RSA signatures.</span></span> <span data-ttu-id="56a67-157">Es wurde jedoch weniger klare Anleitungen, wie die Verschlüsselung und Authentifizierung Vorgänge zu sequenzieren.</span><span class="sxs-lookup"><span data-stu-id="56a67-157">However, there has been less clear guidance as to how to sequence the encryption and authentication operations.</span></span> <span data-ttu-id="56a67-158">Aufgrund der Sicherheitsrisiken, die in diesem Artikel beschriebene ist die Microsoft Leitfaden jetzt immer das Paradigma "encrypt-Then-Sign" verwenden.</span><span class="sxs-lookup"><span data-stu-id="56a67-158">Due to the vulnerability detailed in this article, Microsoft's guidance is now to always use the "encrypt-then-sign" paradigm.</span></span> <span data-ttu-id="56a67-159">D.h. zunächst verschlüsseln Sie Daten mithilfe eines symmetrischen Schlüssels, dann berechnen Sie ein MAC oder ein asymmetrisches über den verschlüsselten Text (verschlüsselte Daten).</span><span class="sxs-lookup"><span data-stu-id="56a67-159">That is, first encrypt data using a symmetric key, then compute a MAC or asymmetric signature over the ciphertext (encrypted data).</span></span> <span data-ttu-id="56a67-160">Daten entschlüsseln zu können, führen Sie das Gegenteil.</span><span class="sxs-lookup"><span data-stu-id="56a67-160">When decrypting data, perform the reverse.</span></span> <span data-ttu-id="56a67-161">Klicken Sie zunächst überprüfen, ob der MAC oder die Signatur der verschlüsselte Text, dann zu entschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="56a67-161">First, confirm the MAC or signature of the ciphertext, then decrypt it.</span></span>

<span data-ttu-id="56a67-162">Eine Klasse von Sicherheitslücken bekannt als "Auffüllung von Oracle-Angriffen" bekanntermaßen sich 10 Jahre lang vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="56a67-162">A class of vulnerabilities known as "padding oracle attacks" have been known to exist for over 10 years.</span></span> <span data-ttu-id="56a67-163">Diese Sicherheitsrisiken Angreifer ein zum Entschlüsseln von Daten, die nicht mehr als 4096 versuchen pro Block von Daten mithilfe von symmetrischer Blöcke Algorithmen, wie z. B. AES und 3DES verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="56a67-163">These vulnerabilities allow an attacker to decrypt data encrypted by symmetric block algorithms, such as AES and 3DES, using no more than 4096 attempts per block of data.</span></span> <span data-ttu-id="56a67-164">Stellen Sie diese Sicherheitsrisiken verwenden die Tatsache, die eine Blockierung Verschlüsselungen werden am häufigsten verwendet, mit überprüfbare Auffüllung Daten am Ende.</span><span class="sxs-lookup"><span data-stu-id="56a67-164">These vulnerabilities make use of the fact that block ciphers are most frequently used with verifiable padding data at the end.</span></span> <span data-ttu-id="56a67-165">Es wurde gefunden, wenn ein Angreifer verschlüsselten Text manipulieren und finden Sie heraus, ob die Manipulation einen Fehler im Format der Abstand am Ende verursacht, der Angreifer die Daten entschlüsselt werden kann.</span><span class="sxs-lookup"><span data-stu-id="56a67-165">It was found that if an attacker can tamper with ciphertext and find out whether the tampering caused an error in the format of the padding at the end, the attacker can decrypt the data.</span></span>

<span data-ttu-id="56a67-166">Praktische Angriffe zunächst basieren auf Diensten, die verschiedenen Fehlercodes, je nachdem ob Auffüllung gültig sind, beispielsweise das Sicherheitsrisiko ASP.NET war zurückgibt [MS10-070](https://technet.microsoft.com/library/security/ms10-070.aspx).</span><span class="sxs-lookup"><span data-stu-id="56a67-166">Initially, practical attacks were based on services that would return different error codes based on whether padding was valid, such as the ASP.NET vulnerability [MS10-070](https://technet.microsoft.com/library/security/ms10-070.aspx).</span></span> <span data-ttu-id="56a67-167">Allerdings ist der Auffassung Microsoft jetzt, dass es sehr praktisch, führen Sie ähnliche Angriffe. hierfür wird nur die Unterschiede beim Timing zwischen der Verarbeitung von gültigen und ungültigen Auffüllung handelt.</span><span class="sxs-lookup"><span data-stu-id="56a67-167">However, Microsoft now believes that it's practical to conduct similar attacks using only the differences in timing between processing valid and invalid padding.</span></span>

<span data-ttu-id="56a67-168">Vorausgesetzt, dass das Verschlüsselungsschema eine Signatur setzt und, die die Überprüfung der Signatur mit einer festen Runtime für eine bestimmte Länge der Daten (unabhängig von der der Inhalt) ausgeführt wird, kann die Integrität der Daten überprüft werden, alle Informationen zu verlassen, ohne ein Angreifer über eine [Seite Kanal](https://en.wikipedia.org/wiki/Side-channel_attack).</span><span class="sxs-lookup"><span data-stu-id="56a67-168">Provided that the encryption scheme employs a signature and that the signature verification is performed with a fixed runtime for a given length of data (irrespective of the contents), the data integrity can be verified without emitting any information to an attacker via a [side channel](https://en.wikipedia.org/wiki/Side-channel_attack).</span></span> <span data-ttu-id="56a67-169">Da die integritätsprüfung von manipulierten Nachrichten ablehnt, wird die Auffüllung Oracle Bedrohung verringert.</span><span class="sxs-lookup"><span data-stu-id="56a67-169">Since the integrity check rejects any tampered messages, the padding oracle threat is mitigated.</span></span>

## <a name="guidance"></a><span data-ttu-id="56a67-170">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="56a67-170">Guidance</span></span>

<span data-ttu-id="56a67-171">Zuallererst empfiehlt Microsoft, alle Daten, die Vertraulichkeit für Transport Layer Security (TLS), dem Nachfolger, Secure Sockets Layer (SSL) übertragen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="56a67-171">First and foremost, Microsoft recommends that any data that has confidentiality needs be transmitted over Transport Layer Security (TLS), the successor to Secure Sockets Layer (SSL).</span></span>

<span data-ttu-id="56a67-172">Als Nächstes wird die Anwendung zu analysieren:</span><span class="sxs-lookup"><span data-stu-id="56a67-172">Next, analyze your application to:</span></span>

- <span data-ttu-id="56a67-173">Verstehen Sie genau, welche Verschlüsselung, die Sie durchführen und von den Plattformen und APIs, die Sie verwenden, welche Verschlüsselung bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="56a67-173">Understand precisely what encryption you're performing and what encryption is being provided by the platforms and APIs you're using.</span></span>
- <span data-ttu-id="56a67-174">Werden Sie sicher, dass jede Nutzung auf allen Ebenen des ein symmetrisches [Block Verschlüsselungsalgorithmus](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers), z. B. AES und 3DES im CBC-Modus wird die Verwendung von geheimen Schlüsseln datenintegritätsprüfung integrieren (einer asymmetrischen Signatur ein HMAC, oder den Verschlüsselungsmodus zu ändern. ein [authentifizierte Verschlüsselung](https://en.wikipedia.org/wiki/Authenticated_encryption) (AE) verwendet, z.B. GCM oder CCM).</span><span class="sxs-lookup"><span data-stu-id="56a67-174">Be certain that each usage at each layer of a symmetric [block cipher algorithm](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers), such as AES and 3DES, in CBC mode incorporate the use of a secret-keyed data integrity check (an asymmetric signature, an HMAC, or to change the cipher mode to an [authenticated encryption](https://en.wikipedia.org/wiki/Authenticated_encryption) (AE) mode such as GCM or CCM).</span></span>

<span data-ttu-id="56a67-175">Basierend auf dem neuesten forschungsstand, ist es im Allgemeinen davon ausgegangen, dass wenn Schritte für die Authentifizierung und Verschlüsselung nicht AE-Modi für die Verschlüsselung unabhängig voneinander ausgeführt werden, authentifizieren den verschlüsselten Text (verschlüsseln-dann-Anmeldung) die beste Option für die allgemeine ist.</span><span class="sxs-lookup"><span data-stu-id="56a67-175">Based on the current research, it's generally believed that when the authentication and encryption steps are performed independently for non-AE modes of encryption, authenticating the ciphertext (encrypt-then-sign) is the best general option.</span></span> <span data-ttu-id="56a67-176">Jedoch keine allgemeingültige richtige Antwort zur Kryptografie, und diese Generalisierung ist nicht so gut wie gerichteten Ratschläge von einer professionellen Cryptographer.</span><span class="sxs-lookup"><span data-stu-id="56a67-176">However, there's no one-size-fits-all correct answer to cryptography and this generalization isn't as good as directed advice from a professional cryptographer.</span></span>

<span data-ttu-id="56a67-177">Anwendungen, die nicht ihre messaging-Format zu ändern, aber nicht authentifizierte CBC Entschlüsselung werden empfohlen, um zu versuchen, z. B. Lösungen zu integrieren:</span><span class="sxs-lookup"><span data-stu-id="56a67-177">Applications that are unable to change their messaging format but perform unauthenticated CBC decryption are encouraged to try to incorporate mitigations such as:</span></span>

- <span data-ttu-id="56a67-178">Entschlüsseln Sie ohne den Entschlüsselungsmechanismus, um zu überprüfen oder Entfernen der Auffüllung:</span><span class="sxs-lookup"><span data-stu-id="56a67-178">Decrypt without allowing the decryptor to verify or remove padding:</span></span>
  - <span data-ttu-id="56a67-179">Möglicher Abstände, die angewendet wurde, weiterhin benötigt, entfernt oder ignoriert werden, verschieben Sie die Last in Ihrer Anwendung.</span><span class="sxs-lookup"><span data-stu-id="56a67-179">Any padding that was applied still needs to be removed or ignored, you're moving the burden into your application.</span></span>
  - <span data-ttu-id="56a67-180">Der Vorteil ist, dass die Überprüfung von Abstand und die Entfernung in andere Anwendung Daten Überprüfung Logik integriert werden können.</span><span class="sxs-lookup"><span data-stu-id="56a67-180">The benefit is that the padding verification and removal can be incorporated into other application data verification logic.</span></span> <span data-ttu-id="56a67-181">Wenn die Überprüfung von Abstand und die bei der Überprüfung in konstanter Zeit ausgeführt werden können, wird das Risiko reduziert.</span><span class="sxs-lookup"><span data-stu-id="56a67-181">If the padding verification and data verification can be done in constant time, the threat is reduced.</span></span>
  - <span data-ttu-id="56a67-182">Da die Interpretation des Abstands um die wahrgenommene Nachrichtenlänge ändert, werden ggf. noch Informationen zur zeitlichen Steuerung, die von diesem Ansatz ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="56a67-182">Since the interpretation of the padding changes the perceived message length, there may still be timing information emitted from this approach.</span></span>
- <span data-ttu-id="56a67-183">Ändern Sie den Paddingmodus Entschlüsselung ISO10126:</span><span class="sxs-lookup"><span data-stu-id="56a67-183">Change the decryption padding mode to ISO10126:</span></span>
  - <span data-ttu-id="56a67-184">ISO10126 Entschlüsselung Auffüllung ist kompatibel mit PKCS7 Verschlüsselung Auffüllung und ANSIX923 Verschlüsselung Auffüllung.</span><span class="sxs-lookup"><span data-stu-id="56a67-184">ISO10126 decryption padding is compatible with both PKCS7 encryption padding and ANSIX923 encryption padding.</span></span>
  - <span data-ttu-id="56a67-185">Ändern des Modus reduziert die Auffüllung-Oracle-Kenntnisse um 1 Byte und nicht den gesamten Block.</span><span class="sxs-lookup"><span data-stu-id="56a67-185">Changing the mode reduces the padding oracle knowledge to 1 byte instead of the entire block.</span></span> <span data-ttu-id="56a67-186">Wenn der Inhalt eine bekannte Fußzeile, z. B. eine schließende XML-Element besitzt können jedoch verwandte Angriffe weiterhin, für den Rest der Nachricht Angriffe.</span><span class="sxs-lookup"><span data-stu-id="56a67-186">However, if the content has a well-known footer, such as a closing XML element, related attacks can continue to attack the rest of the message.</span></span>
  - <span data-ttu-id="56a67-187">Dies auch verhindert nur-Text-Wiederherstellung in Situationen nicht, in denen der Angreifer Klartext mehrere Male mit einem Offset für die unterschiedlichen Nachrichten, die verschlüsselt werden umgewandelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="56a67-187">This also doesn't prevent plaintext recovery in situations where the attacker can coerce the same plaintext to be encrypted multiple times with a different message offset.</span></span>
- <span data-ttu-id="56a67-188">Die Auswertung eines Aufrufs Entschlüsselung der zeitlichen Steuerung Signal Befeuchten-Gate:</span><span class="sxs-lookup"><span data-stu-id="56a67-188">Gate the evaluation of a decryption call to dampen the timing signal:</span></span>
  - <span data-ttu-id="56a67-189">Die Berechnung des Haltezeit müssen mindestens über die maximale Zeitspanne, die der Entschlüsselungsvorgang für alle Datensegment dauern würde, die Auffüllung enthält.</span><span class="sxs-lookup"><span data-stu-id="56a67-189">The computation of hold time must have a minimum in excess of the maximum amount of time the decryption operation would take for any data segment that contains padding.</span></span>
  - <span data-ttu-id="56a67-190">Time Berechnungen sollte durchgeführt werden, gemäß den Anweisungen unter [Abrufen mit hoher Auflösung Zeitstempel](https://msdn.microsoft.com/library/windows/desktop/dn55340.aspx), nicht mithilfe von <xref:System.Environment.TickCount?displayProperty=nameWithType> (je nach Roll-Over/Überlauf) oder Subtraktion von zwei System Zeitstempel (gemäß den NTP-Anpassung (Fehler).</span><span class="sxs-lookup"><span data-stu-id="56a67-190">Time computations should be done according to the guidance in [Acquiring high-resolution time stamps](https://msdn.microsoft.com/library/windows/desktop/dn55340.aspx), not by using <xref:System.Environment.TickCount?displayProperty=nameWithType> (subject to roll-over/overflow) or subtracting two system timestamps (subject to NTP adjustment errors).</span></span>
  - <span data-ttu-id="56a67-191">Zeit Berechnungen müssen einschließlich der Entschlüsselungsvorgang, einschließlich aller mögliche Ausnahmen in verwaltet werden oder C++-Anwendungen, die nicht nur am Ende aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="56a67-191">Time computations must be inclusive of the decryption operation including all potential exceptions in managed or C++ applications, not just padded onto the end.</span></span>
  - <span data-ttu-id="56a67-192">Wenn noch Erfolg oder Fehler ermittelt wurde, muss das Timing-Gate nach dessen Ablauf ein Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="56a67-192">If success or failure has been determined yet, the timing gate needs to return failure when it expires.</span></span>
- <span data-ttu-id="56a67-193">Dienste, die nicht authentifizierte Entschlüsselung durchführen müssen erkennen, dass eine Flut von "ungültig" Nachrichten über stammten überwachungslösung.</span><span class="sxs-lookup"><span data-stu-id="56a67-193">Services that are performing unauthenticated decryption should have monitoring in place to detect that a flood of "invalid" messages has come through.</span></span>
  - <span data-ttu-id="56a67-194">Beachten Sie, dass dieses Signal sowohl falsch positive Ergebnisse (legitimen beschädigte Daten) und falschen negativen Ergebnissen (Verteilen des Angriffs über einen ausreichend langen Zeitraum auf die Erkennung zu verhindern) enthält.</span><span class="sxs-lookup"><span data-stu-id="56a67-194">Bear in mind that this signal carries both false positives (legitimately corrupted data) and false negatives (spreading out the attack over a sufficiently long time to evade detection).</span></span>

## <a name="finding-vulnerable-code---native-applications"></a><span data-ttu-id="56a67-195">Suchen Sie nach anfälligen Codes - systemeigene Anwendungen</span><span class="sxs-lookup"><span data-stu-id="56a67-195">Finding vulnerable code - native applications</span></span>

<span data-ttu-id="56a67-196">Für Programme, die für die Windows-Kryptografie erstellt: Next Generation (CNG)-Bibliothek:</span><span class="sxs-lookup"><span data-stu-id="56a67-196">For programs built against the Windows Cryptography: Next Generation (CNG) library:</span></span>

- <span data-ttu-id="56a67-197">Der Entschlüsselung Aufruf [BCryptDecrypt](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptdecrypt)unter Angabe der `BCRYPT_BLOCK_PADDING` Flag.</span><span class="sxs-lookup"><span data-stu-id="56a67-197">The decryption call is to [BCryptDecrypt](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptdecrypt), specifying the `BCRYPT_BLOCK_PADDING` flag.</span></span>
- <span data-ttu-id="56a67-198">Das Schlüsselhandle wurde durch den Aufruf initialisiert ["BCryptSetProperty"](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptsetproperty) mit [BCRYPT_CHAINING_MODE](https://msdn.microsoft.com/library/windows/desktop/aa376211.aspx#BCRYPT_CHAINING_MODE) festgelegt `BCRYPT_CHAIN_MODE_CBC`.</span><span class="sxs-lookup"><span data-stu-id="56a67-198">The key handle has been initialized by calling [BCryptSetProperty](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptsetproperty) with [BCRYPT_CHAINING_MODE](https://msdn.microsoft.com/library/windows/desktop/aa376211.aspx#BCRYPT_CHAINING_MODE) set to `BCRYPT_CHAIN_MODE_CBC`.</span></span>
  - <span data-ttu-id="56a67-199">Da `BCRYPT_CHAIN_MODE_CBC` ist die Standardeinstellung. betroffene Code möglicherweise keine Werte für zugewiesen `BCRYPT_CHAINING_MODE`.</span><span class="sxs-lookup"><span data-stu-id="56a67-199">Since `BCRYPT_CHAIN_MODE_CBC` is the default, affected code may not have assigned any value for `BCRYPT_CHAINING_MODE`.</span></span>

<span data-ttu-id="56a67-200">Für Programme, die für die älteren Windows Kryptografie-API erstellt werden:</span><span class="sxs-lookup"><span data-stu-id="56a67-200">For programs built against the older Windows Cryptographic API:</span></span>

- <span data-ttu-id="56a67-201">Der Entschlüsselung Aufruf [CryptDecrypt](/windows/desktop/api/wincrypt/nf-wincrypt-cryptdecrypt) mit `Final=TRUE`.</span><span class="sxs-lookup"><span data-stu-id="56a67-201">The decryption call is to [CryptDecrypt](/windows/desktop/api/wincrypt/nf-wincrypt-cryptdecrypt) with `Final=TRUE`.</span></span>
- <span data-ttu-id="56a67-202">Das Schlüsselhandle wurde durch den Aufruf initialisiert [CryptSetKeyParam](/windows/desktop/api/wincrypt/nf-wincrypt-cryptsetkeyparam) mit [KP_MODE](https://msdn.microsoft.com/library/windows/desktop/aa379949.aspx#KP_MODE) festgelegt `CRYPT_MODE_CBC`.</span><span class="sxs-lookup"><span data-stu-id="56a67-202">The key handle has been initialized by calling [CryptSetKeyParam](/windows/desktop/api/wincrypt/nf-wincrypt-cryptsetkeyparam) with [KP_MODE](https://msdn.microsoft.com/library/windows/desktop/aa379949.aspx#KP_MODE) set to `CRYPT_MODE_CBC`.</span></span>
  - <span data-ttu-id="56a67-203">Da `CRYPT_MODE_CBC` ist die Standardeinstellung. betroffene Code möglicherweise keine Werte für zugewiesen `KP_MODE`.</span><span class="sxs-lookup"><span data-stu-id="56a67-203">Since `CRYPT_MODE_CBC` is the default, affected code may not have assigned any value for `KP_MODE`.</span></span>

## <a name="finding-vulnerable-code---managed-applications"></a><span data-ttu-id="56a67-204">Suchen nach anfälligen Codes - verwalteten Anwendungen</span><span class="sxs-lookup"><span data-stu-id="56a67-204">Finding vulnerable code - managed applications</span></span>

- <span data-ttu-id="56a67-205">Der Entschlüsselung Aufruf der <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor> oder <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])> Methoden <xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="56a67-205">The decryption call is to the <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor> or <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])> methods on <xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>.</span></span>
  - <span data-ttu-id="56a67-206">Dies umfasst die folgenden abgeleiteten Typen in .NET, aber es kann auch von Drittanbietern Typen enthalten:</span><span class="sxs-lookup"><span data-stu-id="56a67-206">This includes the following derived types within the .NET, but may also include third-party types:</span></span>
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
- <span data-ttu-id="56a67-207">Die <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> -Eigenschaft wurde festgelegt, um <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType>, <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType>, oder <xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="56a67-207">The <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> property was set to <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType>, <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType>, or <xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType>.</span></span>
  - <span data-ttu-id="56a67-208">Da <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> ist die Standardeinstellung. betroffene Code nie zugewiesen haben die <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="56a67-208">Since <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> is the default, affected code may never have assigned the <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> property.</span></span>
- <span data-ttu-id="56a67-209">Die <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> Eigenschaft auf festgelegt wurde <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="56a67-209">The <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> property was set to <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType></span></span>
  - <span data-ttu-id="56a67-210">Da <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType> ist die Standardeinstellung. betroffene Code nie zugewiesen haben die <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="56a67-210">Since <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType> is the default, affected code may never have assigned the <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> property.</span></span>

## <a name="finding-vulnerable-code---cryptographic-message-syntax"></a><span data-ttu-id="56a67-211">Suchen Sie nach anfälligen Codes - cryptographic Message syntax</span><span class="sxs-lookup"><span data-stu-id="56a67-211">Finding vulnerable code - cryptographic message syntax</span></span>

<span data-ttu-id="56a67-212">Eine nicht authentifizierte CMS EnvelopedData-Nachricht, deren verschlüsselte Inhalte CBC-Modus von AES (2.16.840.1.101.3.4.1.2, 2.16.840.1.101.3.4.1.22, 2.16.840.1.101.3.4.1.42), DES (1.3.14.3.2.7), 3DES verwendet (1.2.840.113549.3.7) oder RC2 (1.2.840.113549.3.2) ist anfällig ist, Nachrichten, die auch als mit anderen Blockverschlüsselungsalgorithmen im CBC-Modus.</span><span class="sxs-lookup"><span data-stu-id="56a67-212">An unauthenticated CMS EnvelopedData message whose encrypted content uses the CBC mode of AES (2.16.840.1.101.3.4.1.2, 2.16.840.1.101.3.4.1.22, 2.16.840.1.101.3.4.1.42), DES (1.3.14.3.2.7), 3DES (1.2.840.113549.3.7) or RC2 (1.2.840.113549.3.2) is vulnerable, as well as messages using any other block cipher algorithms in CBC mode.</span></span>

<span data-ttu-id="56a67-213">Während streamchiffren nicht anfällig für diese Sicherheitslücke sind, empfiehlt Microsoft immer die Daten über das Überprüfen des Wertes ContentEncryptionAlgorithm authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="56a67-213">While stream ciphers aren't susceptible to this particular vulnerability, Microsoft recommends always authenticating the data over inspecting the ContentEncryptionAlgorithm value.</span></span>

<span data-ttu-id="56a67-214">Für verwaltete Anwendungen erkannt eine CMS-EnvelopedData Blob sein kann als beliebiger Wert, der an <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="56a67-214">For managed applications, a CMS EnvelopedData blob can be detected as any value that is passed to <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>.</span></span>

<span data-ttu-id="56a67-215">Für native Anwendungen kann als jeder Wert bereitgestellt, um ein Handle CMS über ein CMS EnvelopedData Blob erkannt werden [CryptMsgUpdate](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgupdate) , dessen resultierende [CMSG_TYPE_PARAM](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsggetparam) ist `CMSG_ENVELOPED` und/oder das CMS-Handle ist später gesendet eine `CMSG_CTRL_DECRYPT` Anweisung über [CryptMsgControl](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgcontrol).</span><span class="sxs-lookup"><span data-stu-id="56a67-215">For native applications, a CMS EnvelopedData blob can be detected as any value provided to a CMS handle via [CryptMsgUpdate](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgupdate) whose resulting [CMSG_TYPE_PARAM](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsggetparam) is `CMSG_ENVELOPED` and/or the CMS handle is later sent a `CMSG_CTRL_DECRYPT` instruction via [CryptMsgControl](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgcontrol).</span></span>

## <a name="vulnerable-code-example---managed"></a><span data-ttu-id="56a67-216">Anfälligen Codes-Beispiel – verwaltet</span><span class="sxs-lookup"><span data-stu-id="56a67-216">Vulnerable code example - managed</span></span>

<span data-ttu-id="56a67-217">Diese Methode liest einen Cookie und entschlüsselt, und keine datenintegritätsprüfung wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="56a67-217">This method reads a cookie and decrypts it and no data integrity check is visible.</span></span> <span data-ttu-id="56a67-218">Aus diesem Grund können den Inhalt eines Cookies, die von dieser Methode gelesen wird angegriffen werden, indem der Benutzer, die sie empfangen oder jeder Angreifer, der den Wert des verschlüsselten Cookie erhalten hat.</span><span class="sxs-lookup"><span data-stu-id="56a67-218">Therefore, the contents of a cookie that is read by this method can be attacked by the user who received it, or by any attacker who has obtained the encrypted cookie value.</span></span>

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

## <a name="example-code-following-recommended-practices---managed"></a><span data-ttu-id="56a67-219">Beispiel für Code folgenden empfohlenen Methoden - verwaltet</span><span class="sxs-lookup"><span data-stu-id="56a67-219">Example code following recommended practices - managed</span></span>

<span data-ttu-id="56a67-220">Der folgende Code verwendet das Format nicht standardmäßige nachrichtenerstellung</span><span class="sxs-lookup"><span data-stu-id="56a67-220">The following sample code uses a non-standard message format of</span></span>

`cipher_algorithm_id || hmac_algorithm_id || hmac_tag || iv || ciphertext`

<span data-ttu-id="56a67-221">in denen die `cipher_algorithm_id` und `hmac_algorithm_id` Algorithmusbezeichner werden lokalen (nicht standardmäßige) Darstellungen dieser Algorithmen.</span><span class="sxs-lookup"><span data-stu-id="56a67-221">where the `cipher_algorithm_id` and `hmac_algorithm_id` algorithm identifiers are application-local (non-standard) representations of those algorithms.</span></span> <span data-ttu-id="56a67-222">Dieser Bezeichner können in andere Teile Ihrer vorhandenen messaging-Protokoll statt als ein bare verketteten Bytestream sinnvoll.</span><span class="sxs-lookup"><span data-stu-id="56a67-222">These identifiers may make sense in other parts of your existing messaging protocol instead of as a bare concatenated bytestream.</span></span>

<span data-ttu-id="56a67-223">Dieses Beispiel verwendet auch einen einzelnen Hauptschlüssel sowohl einen Verschlüsselungsschlüssel und HMAC-Schlüssel abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="56a67-223">This example also uses a single master key to derive both an encryption key and an HMAC key.</span></span> <span data-ttu-id="56a67-224">Dies wird sowohl zur Vereinfachung bereitgestellt, für das Aktivieren einer Anwendung einfach als Schlüssel, der in einer Dual-verschlüsselt-Anwendung, und ermutigen, halten die beiden Schlüssel als unterschiedliche Werte.</span><span class="sxs-lookup"><span data-stu-id="56a67-224">This is provided both as a convenience for turning a singly-keyed application into a dual-keyed application, and to encourage keeping the two keys as different values.</span></span> <span data-ttu-id="56a67-225">Es wird weiter sichergestellt, dass die HMAC-Schlüssel und den Verschlüsselungsschlüssel für nicht synchronisierte erhalten.</span><span class="sxs-lookup"><span data-stu-id="56a67-225">It further guarantees that the HMAC key and encryption key can't get out of synchronization.</span></span>

<span data-ttu-id="56a67-226">In diesem Beispiel akzeptiert keine <xref:System.IO.Stream> für die Verschlüsselung oder Entschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="56a67-226">This sample doesn't accept a <xref:System.IO.Stream> for either encryption or decryption.</span></span> <span data-ttu-id="56a67-227">Die aktuellen Daten Format erleichtert das einmalige verschlüsseln schwierig da die `hmac_tag` Wert vorangestellt ist, den verschlüsselten Text.</span><span class="sxs-lookup"><span data-stu-id="56a67-227">The current data format makes one-pass encrypt difficult because the `hmac_tag` value precedes the ciphertext.</span></span> <span data-ttu-id="56a67-228">Allerdings wurde dieses Format gewählt, da es alle Elemente der fester Größe beibehält, zu den Parser einfacher zu halten.</span><span class="sxs-lookup"><span data-stu-id="56a67-228">However, this format was chosen because it keeps all of the fixed-size elements at the beginning to keep the parser simpler.</span></span> <span data-ttu-id="56a67-229">Dieses Format für Daten ist eine durchlaufende entschlüsseln möglich, obwohl ein Implementierer GetHashAndReset aufrufen, und überprüfen das Ergebnis vor dem Aufrufen von TransformFinalBlock hingewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="56a67-229">With this data format, one-pass decrypt is possible, though an implementer is cautioned to call GetHashAndReset and verify the result before calling TransformFinalBlock.</span></span> <span data-ttu-id="56a67-230">Wenn die streaming-Verschlüsselung wichtig ist, kann ein anderen AE-Modus erforderlich sein.</span><span class="sxs-lookup"><span data-stu-id="56a67-230">If streaming encryption is important, then a different AE mode may be required.</span></span>

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
