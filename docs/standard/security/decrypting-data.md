---
title: Entschlüsseln von Daten
description: Erfahren Sie, wie Daten in .NET mithilfe eines symmetrischen Algorithmus oder eines asymmetrischen Algorithmus entschlüsselt werden.
ms.date: 07/16/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [.NET], decryption
- symmetric decryption
- asymmetric decryption
- decryption
ms.assetid: 9b266b6c-a9b2-4d20-afd8-b3a0d8fd48a0
ms.openlocfilehash: cf286eeca8a9372c6532c56701e4775d5e09d786
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94831103"
---
# <a name="decrypting-data"></a><span data-ttu-id="67082-103">Entschlüsseln von Daten</span><span class="sxs-lookup"><span data-stu-id="67082-103">Decrypting Data</span></span>

<span data-ttu-id="67082-104">Entschlüsselung ist die Umkehrung einer Verschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="67082-104">Decryption is the reverse operation of encryption.</span></span> <span data-ttu-id="67082-105">Bei einer Entschlüsselung mit geheimem Schlüssel müssen sowohl der Schlüssel als auch der Initialisierungsvektor (IV) bekannt sein, die zum Verschlüsseln der Daten verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="67082-105">For secret-key encryption, you must know both the key and IV that were used to encrypt the data.</span></span> <span data-ttu-id="67082-106">Bei einer Entschlüsselung mit öffentlichem Schlüssel muss entweder der öffentliche Schlüssel (wenn die Daten mit dem privaten Schlüssel verschlüsselt wurden) oder der private Schlüssel (wenn die Daten mit dem öffentlichen Schlüssel verschlüsselt wurden) bekannt sein.</span><span class="sxs-lookup"><span data-stu-id="67082-106">For public-key encryption, you must know either the public key (if the data was encrypted using the private key) or the private key (if the data was encrypted using the public key).</span></span>

## <a name="symmetric-decryption"></a><span data-ttu-id="67082-107">Symmetrische Entschlüsselung</span><span class="sxs-lookup"><span data-stu-id="67082-107">Symmetric Decryption</span></span>

<span data-ttu-id="67082-108">Die Entschlüsselung von Daten, die mit einem symmetrischen Algorithmus verschlüsselt wurden, ist mit der Vorgehensweise zum Verschlüsseln der Daten mit einem symmetrischen Algorithmus vergelichbar.</span><span class="sxs-lookup"><span data-stu-id="67082-108">The decryption of data encrypted with symmetric algorithms is similar to the process used to encrypt data with symmetric algorithms.</span></span> <span data-ttu-id="67082-109">Die- <xref:System.Security.Cryptography.CryptoStream> Klasse wird mit symmetrischen Kryptografieklassen verwendet, die von .NET bereitgestellt werden, um Daten zu entschlüsseln, die aus einem beliebigen verwalteten Streamobjekt gelesen</span><span class="sxs-lookup"><span data-stu-id="67082-109">The <xref:System.Security.Cryptography.CryptoStream> class is used with symmetric cryptography classes provided by .NET to decrypt data read from any managed stream object.</span></span>

<span data-ttu-id="67082-110">Im folgenden Beispiel wird veranschaulicht, wie eine neue Instanz der Standard Implementierungs Klasse für den- <xref:System.Security.Cryptography.Aes> Algorithmus erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="67082-110">The following example illustrates how to create a new instance of the default implementation class for the <xref:System.Security.Cryptography.Aes> algorithm.</span></span> <span data-ttu-id="67082-111">Die-Instanz wird verwendet, um die Entschlüsselung für ein- <xref:System.Security.Cryptography.CryptoStream> Objekt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="67082-111">The instance is used to perform decryption on a <xref:System.Security.Cryptography.CryptoStream> object.</span></span> <span data-ttu-id="67082-112">In diesem Beispiel wird zunächst eine neue Instanz der <xref:System.Security.Cryptography.Aes> Implementierungs Klasse erstellt.</span><span class="sxs-lookup"><span data-stu-id="67082-112">This example first creates a new instance of the <xref:System.Security.Cryptography.Aes> implementation class.</span></span> <span data-ttu-id="67082-113">Er liest den Initialisierungs Vektor (IV)-Wert aus einer verwalteten Datenstrom Variablen, `myStream` .</span><span class="sxs-lookup"><span data-stu-id="67082-113">It reads the initialization vector (IV) value from a managed stream variable, `myStream`.</span></span> <span data-ttu-id="67082-114">Als nächstes instanziiert ein <xref:System.Security.Cryptography.CryptoStream> -Objekt und initialisiert es mit dem Wert der- `myStream` Instanz.</span><span class="sxs-lookup"><span data-stu-id="67082-114">Next it instantiates a <xref:System.Security.Cryptography.CryptoStream> object and initializes it to the value of the `myStream` instance.</span></span> <span data-ttu-id="67082-115">Der <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor%2A?displayProperty=nameWithType> -Methode aus der <xref:System.Security.Cryptography.Aes> -Instanz werden der IV-Wert und derselbe Schlüssel, der für die Verschlüsselung verwendet wurde, übermittelt.</span><span class="sxs-lookup"><span data-stu-id="67082-115">The <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor%2A?displayProperty=nameWithType> method from the <xref:System.Security.Cryptography.Aes> instance is passed the IV value and the same key that was used for encryption.</span></span>

```vb
Dim aes As Aes = Aes.Create()
Dim cryptStream As New CryptoStream(myStream, aes.CreateDecryptor(key, iv), CryptoStreamMode.Read)
```

```csharp
Aes aes = Aes.Create();
CryptoStream cryptStream = new CryptoStream(myStream, aes.CreateDecryptor(key, iv), CryptoStreamMode.Read);
```

<span data-ttu-id="67082-116">Das folgende Beispiel veranschaulicht den gesamten Prozess: das Erzeugen des Streams, das Verschlüsseln des Streams, das Lesen aus dem Stream und das Schließen des Streams.</span><span class="sxs-lookup"><span data-stu-id="67082-116">The following example shows the entire process of creating a stream, decrypting the stream, reading from the stream, and closing the streams.</span></span> <span data-ttu-id="67082-117">Ein Dateistream-Objekt wird erstellt, das eine Datei mit dem Namen *TestData.txt* liest.</span><span class="sxs-lookup"><span data-stu-id="67082-117">A file stream object is created that reads a file named *TestData.txt*.</span></span> <span data-ttu-id="67082-118">Der Dateistream wird dann mithilfe der **CryptoStream** -Klasse und der **AES** -Klasse entschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="67082-118">The file stream is then decrypted using the **CryptoStream** class and the **Aes** class.</span></span> <span data-ttu-id="67082-119">In diesem Beispiel wird der Schlüsselwert angegeben, der im Beispiel für die symmetrische Verschlüsselung zum [Verschlüsseln von Daten](encrypting-data.md)verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="67082-119">This example specifies key value that is used in the symmetric encryption example for [Encrypting Data](encrypting-data.md).</span></span> <span data-ttu-id="67082-120">Das Beispiel enthält nicht den Code, der zum Verschlüsseln und Übertragen dieser Werte erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="67082-120">It does not show the code needed to encrypt and transfer these values.</span></span>

:::code language="csharp" source="snippets/decrypting-data/csharp/aes-decrypt.cs":::
:::code language="vb" source="snippets/decrypting-data/vb/aes-decrypt.vb":::

<span data-ttu-id="67082-121">Im vorangehenden Beispiel wird derselbe Schlüssel und Algorithmus verwendet, der im Beispiel für die symmetrische Verschlüsselung zum [Verschlüsseln von Daten](encrypting-data.md)verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="67082-121">The preceding example uses the same key, and algorithm used in the symmetric encryption example for [Encrypting Data](encrypting-data.md).</span></span> <span data-ttu-id="67082-122">Sie entschlüsselt die *TestData.txt* Datei, die in diesem Beispiel erstellt wurde, und zeigt den ursprünglichen Text in der Konsole an.</span><span class="sxs-lookup"><span data-stu-id="67082-122">It decrypts the *TestData.txt* file that is created by that example and displays the original text on the console.</span></span>

## <a name="asymmetric-decryption"></a><span data-ttu-id="67082-123">Asymmetrische Entschlüsselung</span><span class="sxs-lookup"><span data-stu-id="67082-123">Asymmetric Decryption</span></span>

<span data-ttu-id="67082-124">In der Regel generiert ein Teilnehmer (Teilnehmer A) sowohl einen öffentlichen als auch einen privaten Schlüssel und speichert diese entweder im Arbeitsspeicher oder in einem kryptografischen Schlüsselcontainer.</span><span class="sxs-lookup"><span data-stu-id="67082-124">Typically, a party (party A) generates both a public and private key and stores the key either in memory or in a cryptographic key container.</span></span> <span data-ttu-id="67082-125">Teilnehmer A sendet dann den öffentlichen Schlüssel an einen anderen Teilnehmer (Teilnehmer B).</span><span class="sxs-lookup"><span data-stu-id="67082-125">Party A then sends the public key to another party (party B).</span></span> <span data-ttu-id="67082-126">Mit dem öffentlichen Schlüssel verschlüsselt Teilnehmer B Daten und sendet die Daten an Partei A zurück. Nach dem Empfang der Daten entschlüsselt Partei A Sie mithilfe des privaten Schlüssels, der entspricht.</span><span class="sxs-lookup"><span data-stu-id="67082-126">Using the public key, party B encrypts data and sends the data back to party A. After receiving the data, party A decrypts it using the private key that corresponds.</span></span> <span data-ttu-id="67082-127">Die Entschlüsselung kann nur dann erfolgreich sein, wenn Teilnehmer A den privaten Schlüssel verwendet, der dem öffentlichen Schlüssel entspricht, den Teilnehmer B zum Verschlüsseln der Daten verwendet hat.</span><span class="sxs-lookup"><span data-stu-id="67082-127">Decryption will be successful only if party A uses the private key that corresponds to the public key Party B used to encrypt the data.</span></span>

<span data-ttu-id="67082-128">Informationen dazu, wie Sie einen asymmetrischen Schlüssel in einem sicheren Container für kryptografische Schlüssel speichern und später diesen asymmetrischen Schlüssel abrufen, finden Sie unter [How to: Store Asymmetric Keys in a Key Container](how-to-store-asymmetric-keys-in-a-key-container.md).</span><span class="sxs-lookup"><span data-stu-id="67082-128">For information on how to store an asymmetric key in secure cryptographic key container and how to later retrieve the asymmetric key, see [How to: Store Asymmetric Keys in a Key Container](how-to-store-asymmetric-keys-in-a-key-container.md).</span></span>

<span data-ttu-id="67082-129">Das folgende Beispiel veranschaulicht die Entschlüsselung von zwei Bytearrays, die einen symmetrischen Schlüssel und einen IV darstellen.</span><span class="sxs-lookup"><span data-stu-id="67082-129">The following example illustrates the decryption of two arrays of bytes that represent a symmetric key and IV.</span></span> <span data-ttu-id="67082-130">Informationen dazu, wie der asymmetrische öffentliche Schlüssel aus dem <xref:System.Security.Cryptography.RSA> -Objekt in ein Format extrahiert wird, das auf einfache Weise an andere Beteiligte gesendet werden kann, finden Sie unter [Encrypting Data](encrypting-data.md)initialisiert.</span><span class="sxs-lookup"><span data-stu-id="67082-130">For information on how to extract the asymmetric public key from the <xref:System.Security.Cryptography.RSA> object in a format that you can easily send to a third party, see [Encrypting Data](encrypting-data.md).</span></span>

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

## <a name="see-also"></a><span data-ttu-id="67082-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67082-131">See also</span></span>

- [<span data-ttu-id="67082-132">Erzeugen von Schlüsseln für die Ver- und Entschlüsselung</span><span class="sxs-lookup"><span data-stu-id="67082-132">Generating Keys for Encryption and Decryption</span></span>](generating-keys-for-encryption-and-decryption.md)
- [<span data-ttu-id="67082-133">Verschlüsseln von Daten</span><span class="sxs-lookup"><span data-stu-id="67082-133">Encrypting Data</span></span>](encrypting-data.md)
- [<span data-ttu-id="67082-134">Kryptografische Dienste</span><span class="sxs-lookup"><span data-stu-id="67082-134">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="67082-135">Kryptografiemodell</span><span class="sxs-lookup"><span data-stu-id="67082-135">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="67082-136">Plattformübergreifende Kryptografie</span><span class="sxs-lookup"><span data-stu-id="67082-136">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="67082-137">Verwenden der Auffüllung für die Zeitsteuerung bei Sicherheitsrisiken mit symmetrischer Entschlüsselung im CBC-Modus</span><span class="sxs-lookup"><span data-stu-id="67082-137">Timing vulnerabilities with CBC-mode symmetric decryption using padding</span></span>](vulnerabilities-cbc-mode.md)
- [<span data-ttu-id="67082-138">ASP.net Core Datenschutz</span><span class="sxs-lookup"><span data-stu-id="67082-138">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
