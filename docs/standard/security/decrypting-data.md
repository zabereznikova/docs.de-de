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
ms.openlocfilehash: 2ba4c3ba43d688aeb66c67ec3f94f4a503d47892
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556981"
---
# <a name="decrypting-data"></a><span data-ttu-id="853b5-103">Entschlüsseln von Daten</span><span class="sxs-lookup"><span data-stu-id="853b5-103">Decrypting Data</span></span>

<span data-ttu-id="853b5-104">Entschlüsselung ist die Umkehrung einer Verschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="853b5-104">Decryption is the reverse operation of encryption.</span></span> <span data-ttu-id="853b5-105">Bei einer Entschlüsselung mit geheimem Schlüssel müssen sowohl der Schlüssel als auch der Initialisierungsvektor (IV) bekannt sein, die zum Verschlüsseln der Daten verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="853b5-105">For secret-key encryption, you must know both the key and IV that were used to encrypt the data.</span></span> <span data-ttu-id="853b5-106">Bei einer Entschlüsselung mit öffentlichem Schlüssel muss entweder der öffentliche Schlüssel (wenn die Daten mit dem privaten Schlüssel verschlüsselt wurden) oder der private Schlüssel (wenn die Daten mit dem öffentlichen Schlüssel verschlüsselt wurden) bekannt sein.</span><span class="sxs-lookup"><span data-stu-id="853b5-106">For public-key encryption, you must know either the public key (if the data was encrypted using the private key) or the private key (if the data was encrypted using the public key).</span></span>

## <a name="symmetric-decryption"></a><span data-ttu-id="853b5-107">Symmetrische Entschlüsselung</span><span class="sxs-lookup"><span data-stu-id="853b5-107">Symmetric Decryption</span></span>

<span data-ttu-id="853b5-108">Die Entschlüsselung von Daten, die mit einem symmetrischen Algorithmus verschlüsselt wurden, ist mit der Vorgehensweise zum Verschlüsseln der Daten mit einem symmetrischen Algorithmus vergelichbar.</span><span class="sxs-lookup"><span data-stu-id="853b5-108">The decryption of data encrypted with symmetric algorithms is similar to the process used to encrypt data with symmetric algorithms.</span></span> <span data-ttu-id="853b5-109">Die- <xref:System.Security.Cryptography.CryptoStream> Klasse wird mit symmetrischen Kryptografieklassen verwendet, die von .NET bereitgestellt werden, um Daten zu entschlüsseln, die aus einem beliebigen verwalteten Streamobjekt gelesen</span><span class="sxs-lookup"><span data-stu-id="853b5-109">The <xref:System.Security.Cryptography.CryptoStream> class is used with symmetric cryptography classes provided by .NET to decrypt data read from any managed stream object.</span></span>

<span data-ttu-id="853b5-110">Im folgenden Beispiel wird veranschaulicht, wie eine neue Instanz der Standard Implementierungs Klasse für den- <xref:System.Security.Cryptography.Aes> Algorithmus erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="853b5-110">The following example illustrates how to create a new instance of the default implementation class for the <xref:System.Security.Cryptography.Aes> algorithm.</span></span> <span data-ttu-id="853b5-111">Die-Instanz wird verwendet, um die Entschlüsselung für ein- <xref:System.Security.Cryptography.CryptoStream> Objekt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="853b5-111">The instance is used to perform decryption on a <xref:System.Security.Cryptography.CryptoStream> object.</span></span> <span data-ttu-id="853b5-112">In diesem Beispiel wird zunächst eine neue Instanz der **AES** -Implementierungs Klasse erstellt.</span><span class="sxs-lookup"><span data-stu-id="853b5-112">This example first creates a new instance of the **Aes** implementation class.</span></span> <span data-ttu-id="853b5-113">Danach wird ein **CryptoStream** -Objekt erstellt und mit dem Wert eines verwalteten Streams namens `myStream`initialisiert.</span><span class="sxs-lookup"><span data-stu-id="853b5-113">Next it creates a **CryptoStream** object and initializes it to the value of a managed stream called `myStream`.</span></span> <span data-ttu-id="853b5-114">Als nächstes wird die Methode " **kreatedecryptor** " aus der **AES** -Klasse mit demselben Schlüssel und IV übergeben, die für die Verschlüsselung verwendet wurde, und dann an den **CryptoStream** -Konstruktor übergeben.</span><span class="sxs-lookup"><span data-stu-id="853b5-114">Next, the **CreateDecryptor** method from the **Aes** class is passed the same key and IV that was used for encryption and is then passed to the **CryptoStream** constructor.</span></span>

```vb
Dim aes As Aes = Aes.Create()
Dim cryptStream As New CryptoStream(myStream, aes.CreateDecryptor(key, iv), CryptoStreamMode.Read)
```

```csharp
Aes aes = Aes.Create();
CryptoStream cryptStream = new CryptoStream(myStream, aes.CreateDecryptor(key, iv), CryptoStreamMode.Read);
```

<span data-ttu-id="853b5-115">Das folgende Beispiel veranschaulicht den gesamten Prozess: das Erzeugen des Streams, das Verschlüsseln des Streams, das Lesen aus dem Stream und das Schließen des Streams.</span><span class="sxs-lookup"><span data-stu-id="853b5-115">The following example shows the entire process of creating a stream, decrypting the stream, reading from the stream, and closing the streams.</span></span> <span data-ttu-id="853b5-116">Ein Dateistream-Objekt wird erstellt, das eine Datei mit dem Namen *TestData.txt*liest.</span><span class="sxs-lookup"><span data-stu-id="853b5-116">A file stream object is created that reads a file named *TestData.txt*.</span></span> <span data-ttu-id="853b5-117">Der Dateistream wird dann mithilfe der **CryptoStream** -Klasse und der **AES** -Klasse entschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="853b5-117">The file stream is then decrypted using the **CryptoStream** class and the **Aes** class.</span></span> <span data-ttu-id="853b5-118">In diesem Beispiel werden Schlüssel-und IV-Werte angegeben, die im Beispiel für die symmetrische Verschlüsselung zum [Verschlüsseln von Daten](encrypting-data.md)verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="853b5-118">This example specifies key and IV values that are used in the symmetric encryption example for [Encrypting Data](encrypting-data.md).</span></span> <span data-ttu-id="853b5-119">Das Beispiel enthält nicht den Code, der zum Verschlüsseln und Übertragen dieser Werte erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="853b5-119">It does not show the code needed to encrypt and transfer these values.</span></span>

```vb
Imports System
Imports System.IO
Imports System.Security.Cryptography

Module Module1
    Sub Main()
            'The key and IV must be the same values that were used
            'to encrypt the stream.
            Dim key As Byte() = {&H1, &H2, &H3, &H4, &H5, &H6, &H7, &H8, &H9, &H10, &H11, &H12, &H13, &H14, &H15, &H16}
            Dim iv As Byte() = {&H1, &H2, &H3, &H4, &H5, &H6, &H7, &H8, &H9, &H10, &H11, &H12, &H13, &H14, &H15, &H16}
        Try
            'Create a file stream.
            Dim myStream As FileStream = new FileStream("TestData.txt", FileMode.Open)

            'Create a new instance of the default Aes implementation class
            'and decrypt the stream.
            Dim aes As Aes = Aes.Create()

            'Create an instance of the CryptoStream class, pass it the file stream, and decrypt
            'it with the Rijndael class using the key and IV.
            Dim cryptStream As New CryptoStream(myStream, aes.CreateDecryptor(key, iv), CryptoStreamMode.Read)

            'Read the stream.
            Dim sReader As New StreamReader(cryptStream)

            'Display the message.
            Console.WriteLine("The decrypted original message: {0}", sReader.ReadToEnd())

            'Close the streams.
            sReader.Close()
            myStream.Close()
            'Catch any exceptions.
        Catch
            Console.WriteLine("The decryption Failed.")
            Throw
        End Try
    End Sub
End Module
```

```csharp
using System;
using System.IO;
using System.Security.Cryptography;

class Class1
{
    static void Main(string[] args)
    {
        //The key and IV must be the same values that were used
        //to encrypt the stream.
        byte[] key = { 0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07, 0x08, 0x09, 0x10, 0x11, 0x12, 0x13, 0x14, 0x15, 0x16 };
        byte[] iv = { 0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07, 0x08, 0x09, 0x10, 0x11, 0x12, 0x13, 0x14, 0x15, 0x16 };
        try
        {
            //Create a file stream.
            FileStream myStream = new FileStream("TestData.txt", FileMode.Open);

            //Create a new instance of the default Aes implementation class
            Aes aes = Aes.Create();

            //Create a CryptoStream, pass it the file stream, and decrypt
            //it with the Aes class using the key and IV.
            CryptoStream cryptStream = new CryptoStream(
               myStream,
               aes.CreateDecryptor(key, iv),
               CryptoStreamMode.Read);

            //Read the stream.
            StreamReader sReader = new StreamReader(cryptStream);

            //Display the message.
            Console.WriteLine("The decrypted original message: {0}", sReader.ReadToEnd());

            //Close the streams.
            sReader.Close();
            myStream.Close();
        }
        //Catch any exceptions.
        catch
        {
            Console.WriteLine("The decryption failed.");
            throw;
        }
    }
}
```

<span data-ttu-id="853b5-120">Im vorherigen Beispiel werden derselbe Schlüssel, IV und Algorithmus verwendet, die im Beispiel für die symmetrische Verschlüsselung zum [Verschlüsseln von Daten](encrypting-data.md)verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="853b5-120">The preceding example uses the same key, IV, and algorithm used in the symmetric encryption example for [Encrypting Data](encrypting-data.md).</span></span> <span data-ttu-id="853b5-121">Sie entschlüsselt die *TestData.txt* Datei, die in diesem Beispiel erstellt wurde, und zeigt den ursprünglichen Text in der Konsole an.</span><span class="sxs-lookup"><span data-stu-id="853b5-121">It decrypts the *TestData.txt* file that is created by that example and displays the original text on the console.</span></span>

## <a name="asymmetric-decryption"></a><span data-ttu-id="853b5-122">Asymmetrische Entschlüsselung</span><span class="sxs-lookup"><span data-stu-id="853b5-122">Asymmetric Decryption</span></span>

<span data-ttu-id="853b5-123">In der Regel generiert ein Teilnehmer (Teilnehmer A) sowohl einen öffentlichen als auch einen privaten Schlüssel und speichert diese entweder im Arbeitsspeicher oder in einem kryptografischen Schlüsselcontainer.</span><span class="sxs-lookup"><span data-stu-id="853b5-123">Typically, a party (party A) generates both a public and private key and stores the key either in memory or in a cryptographic key container.</span></span> <span data-ttu-id="853b5-124">Teilnehmer A sendet dann den öffentlichen Schlüssel an einen anderen Teilnehmer (Teilnehmer B).</span><span class="sxs-lookup"><span data-stu-id="853b5-124">Party A then sends the public key to another party (party B).</span></span> <span data-ttu-id="853b5-125">Mit dem öffentlichen Schlüssel verschlüsselt Teilnehmer B Daten und sendet die Daten an Partei A zurück. Nach dem Empfang der Daten entschlüsselt Partei A Sie mithilfe des privaten Schlüssels, der entspricht.</span><span class="sxs-lookup"><span data-stu-id="853b5-125">Using the public key, party B encrypts data and sends the data back to party A. After receiving the data, party A decrypts it using the private key that corresponds.</span></span> <span data-ttu-id="853b5-126">Die Entschlüsselung kann nur dann erfolgreich sein, wenn Teilnehmer A den privaten Schlüssel verwendet, der dem öffentlichen Schlüssel entspricht, den Teilnehmer B zum Verschlüsseln der Daten verwendet hat.</span><span class="sxs-lookup"><span data-stu-id="853b5-126">Decryption will be successful only if party A uses the private key that corresponds to the public key Party B used to encrypt the data.</span></span>

<span data-ttu-id="853b5-127">Informationen dazu, wie Sie einen asymmetrischen Schlüssel in einem sicheren Container für kryptografische Schlüssel speichern und später diesen asymmetrischen Schlüssel abrufen, finden Sie unter [How to: Store Asymmetric Keys in a Key Container](how-to-store-asymmetric-keys-in-a-key-container.md).</span><span class="sxs-lookup"><span data-stu-id="853b5-127">For information on how to store an asymmetric key in secure cryptographic key container and how to later retrieve the asymmetric key, see [How to: Store Asymmetric Keys in a Key Container](how-to-store-asymmetric-keys-in-a-key-container.md).</span></span>

<span data-ttu-id="853b5-128">Das folgende Beispiel veranschaulicht die Entschlüsselung von zwei Bytearrays, die einen symmetrischen Schlüssel und einen IV darstellen.</span><span class="sxs-lookup"><span data-stu-id="853b5-128">The following example illustrates the decryption of two arrays of bytes that represent a symmetric key and IV.</span></span> <span data-ttu-id="853b5-129">Informationen dazu, wie der asymmetrische öffentliche Schlüssel aus dem <xref:System.Security.Cryptography.RSA> -Objekt in ein Format extrahiert wird, das auf einfache Weise an andere Beteiligte gesendet werden kann, finden Sie unter [Encrypting Data](encrypting-data.md)initialisiert.</span><span class="sxs-lookup"><span data-stu-id="853b5-129">For information on how to extract the asymmetric public key from the <xref:System.Security.Cryptography.RSA> object in a format that you can easily send to a third party, see [Encrypting Data](encrypting-data.md).</span></span>

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

## <a name="see-also"></a><span data-ttu-id="853b5-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="853b5-130">See also</span></span>

- [<span data-ttu-id="853b5-131">Erzeugen von Schlüsseln für die Ver- und Entschlüsselung</span><span class="sxs-lookup"><span data-stu-id="853b5-131">Generating Keys for Encryption and Decryption</span></span>](generating-keys-for-encryption-and-decryption.md)
- [<span data-ttu-id="853b5-132">Verschlüsseln von Daten</span><span class="sxs-lookup"><span data-stu-id="853b5-132">Encrypting Data</span></span>](encrypting-data.md)
- [<span data-ttu-id="853b5-133">Kryptografische Dienste</span><span class="sxs-lookup"><span data-stu-id="853b5-133">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="853b5-134">Kryptografiemodell</span><span class="sxs-lookup"><span data-stu-id="853b5-134">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="853b5-135">Plattformübergreifende Kryptografie</span><span class="sxs-lookup"><span data-stu-id="853b5-135">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="853b5-136">Verwenden der Auffüllung für die Zeitsteuerung bei Sicherheitsrisiken mit symmetrischer Entschlüsselung im CBC-Modus</span><span class="sxs-lookup"><span data-stu-id="853b5-136">Timing vulnerabilities with CBC-mode symmetric decryption using padding</span></span>](vulnerabilities-cbc-mode.md)
- [<span data-ttu-id="853b5-137">ASP.net Core Datenschutz</span><span class="sxs-lookup"><span data-stu-id="853b5-137">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
