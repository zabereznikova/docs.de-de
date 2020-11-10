---
title: Entschlüsseln von Daten
description: Erfahren Sie, wie Daten in .NET mithilfe eines symmetrischen Algorithmus oder eines asymmetrischen Algorithmus entschlüsselt werden.
ms.date: 07/16/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [.NET], decryption
- symmetric decryption
- asymmetric decryption
- decryption
ms.assetid: 9b266b6c-a9b2-4d20-afd8-b3a0d8fd48a0
ms.openlocfilehash: 7e8fe5a8b7ed7c217a31a8ee91a5d111257fed45
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440984"
---
# <a name="decrypting-data"></a>Entschlüsseln von Daten

Entschlüsselung ist die Umkehrung einer Verschlüsselung. Bei einer Entschlüsselung mit geheimem Schlüssel müssen sowohl der Schlüssel als auch der Initialisierungsvektor (IV) bekannt sein, die zum Verschlüsseln der Daten verwendet wurden. Bei einer Entschlüsselung mit öffentlichem Schlüssel muss entweder der öffentliche Schlüssel (wenn die Daten mit dem privaten Schlüssel verschlüsselt wurden) oder der private Schlüssel (wenn die Daten mit dem öffentlichen Schlüssel verschlüsselt wurden) bekannt sein.

## <a name="symmetric-decryption"></a>Symmetrische Entschlüsselung

Die Entschlüsselung von Daten, die mit einem symmetrischen Algorithmus verschlüsselt wurden, ist mit der Vorgehensweise zum Verschlüsseln der Daten mit einem symmetrischen Algorithmus vergelichbar. Die- <xref:System.Security.Cryptography.CryptoStream> Klasse wird mit symmetrischen Kryptografieklassen verwendet, die von .NET bereitgestellt werden, um Daten zu entschlüsseln, die aus einem beliebigen verwalteten Streamobjekt gelesen

Im folgenden Beispiel wird veranschaulicht, wie eine neue Instanz der Standard Implementierungs Klasse für den- <xref:System.Security.Cryptography.Aes> Algorithmus erstellt wird. Die-Instanz wird verwendet, um die Entschlüsselung für ein- <xref:System.Security.Cryptography.CryptoStream> Objekt auszuführen. In diesem Beispiel wird zunächst eine neue Instanz der <xref:System.Security.Cryptography.Aes> Implementierungs Klasse erstellt. Er liest den Initialisierungs Vektor (IV)-Wert aus einer verwalteten Datenstrom Variablen, `myStream` . Als nächstes instanziiert ein <xref:System.Security.Cryptography.CryptoStream> -Objekt und initialisiert es mit dem Wert der- `myStream` Instanz. Der <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor%2A?displayProperty=nameWithType> -Methode aus der <xref:System.Security.Cryptography.Aes> -Instanz werden der IV-Wert und derselbe Schlüssel, der für die Verschlüsselung verwendet wurde, übermittelt.

```vb
Dim aes As Aes = Aes.Create()
Dim cryptStream As New CryptoStream(myStream, aes.CreateDecryptor(key, iv), CryptoStreamMode.Read)
```

```csharp
Aes aes = Aes.Create();
CryptoStream cryptStream = new CryptoStream(myStream, aes.CreateDecryptor(key, iv), CryptoStreamMode.Read);
```

Das folgende Beispiel veranschaulicht den gesamten Prozess: das Erzeugen des Streams, das Verschlüsseln des Streams, das Lesen aus dem Stream und das Schließen des Streams. Ein Dateistream-Objekt wird erstellt, das eine Datei mit dem Namen *TestData.txt* liest. Der Dateistream wird dann mithilfe der **CryptoStream** -Klasse und der **AES** -Klasse entschlüsselt. In diesem Beispiel wird der Schlüsselwert angegeben, der im Beispiel für die symmetrische Verschlüsselung zum [Verschlüsseln von Daten](encrypting-data.md)verwendet wird. Das Beispiel enthält nicht den Code, der zum Verschlüsseln und Übertragen dieser Werte erforderlich ist.

:::code language="csharp" source="snippets/decrypting-data/csharp/aes-decrypt.cs":::
:::code language="vb" source="snippets/decrypting-data/vb/aes-decrypt.vb":::

Im vorangehenden Beispiel wird derselbe Schlüssel und Algorithmus verwendet, der im Beispiel für die symmetrische Verschlüsselung zum [Verschlüsseln von Daten](encrypting-data.md)verwendet wird. Sie entschlüsselt die *TestData.txt* Datei, die in diesem Beispiel erstellt wurde, und zeigt den ursprünglichen Text in der Konsole an.

## <a name="asymmetric-decryption"></a>Asymmetrische Entschlüsselung

In der Regel generiert ein Teilnehmer (Teilnehmer A) sowohl einen öffentlichen als auch einen privaten Schlüssel und speichert diese entweder im Arbeitsspeicher oder in einem kryptografischen Schlüsselcontainer. Teilnehmer A sendet dann den öffentlichen Schlüssel an einen anderen Teilnehmer (Teilnehmer B). Mit dem öffentlichen Schlüssel verschlüsselt Teilnehmer B Daten und sendet die Daten an Partei A zurück. Nach dem Empfang der Daten entschlüsselt Partei A Sie mithilfe des privaten Schlüssels, der entspricht. Die Entschlüsselung kann nur dann erfolgreich sein, wenn Teilnehmer A den privaten Schlüssel verwendet, der dem öffentlichen Schlüssel entspricht, den Teilnehmer B zum Verschlüsseln der Daten verwendet hat.

Informationen dazu, wie Sie einen asymmetrischen Schlüssel in einem sicheren Container für kryptografische Schlüssel speichern und später diesen asymmetrischen Schlüssel abrufen, finden Sie unter [How to: Store Asymmetric Keys in a Key Container](how-to-store-asymmetric-keys-in-a-key-container.md).

Das folgende Beispiel veranschaulicht die Entschlüsselung von zwei Bytearrays, die einen symmetrischen Schlüssel und einen IV darstellen. Informationen dazu, wie der asymmetrische öffentliche Schlüssel aus dem <xref:System.Security.Cryptography.RSA> -Objekt in ein Format extrahiert wird, das auf einfache Weise an andere Beteiligte gesendet werden kann, finden Sie unter [Encrypting Data](encrypting-data.md)initialisiert.

```vb
'Create a new instance of the RSA class.
Dim rsa As RSA = RSA.Create()

' Export the public key information and send it to a third party.
' Wait for the third party to encrypt some data and send it back.

'Decrypt the symmetric key and IV.
symmetricKey = rsa.Decrypt(encryptedSymmetricKey, RSAEncryptionPadding.Pkcs1)
symmetricIV = rsa.Decrypt(encryptedSymmetricIV, RSAEncryptionPadding.Pkcs1)
```

```csharp
//Create a new instance of the RSA class.
RSA rsa = RSA.Create();

// Export the public key information and send it to a third party.
// Wait for the third party to encrypt some data and send it back.

//Decrypt the symmetric key and IV.
symmetricKey = rsa.Decrypt(encryptedSymmetricKey, RSAEncryptionPadding.Pkcs1);
symmetricIV = rsa.Decrypt(encryptedSymmetricIV , RSAEncryptionPadding.Pkcs1);
```

## <a name="see-also"></a>Siehe auch

- [Erzeugen von Schlüsseln für die Ver- und Entschlüsselung](generating-keys-for-encryption-and-decryption.md)
- [Verschlüsseln von Daten](encrypting-data.md)
- [Kryptografische Dienste](cryptographic-services.md)
- [Kryptografiemodell](cryptography-model.md)
- [Plattformübergreifende Kryptografie](cross-platform-cryptography.md)
- [Verwenden der Auffüllung für die Zeitsteuerung bei Sicherheitsrisiken mit symmetrischer Entschlüsselung im CBC-Modus](vulnerabilities-cbc-mode.md)
- [ASP.net Core Datenschutz](/aspnet/core/security/data-protection/introduction)
