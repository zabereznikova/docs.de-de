---
title: Verschlüsseln von Daten
description: Erfahren Sie, wie Daten in .NET mithilfe eines symmetrischen Algorithmus oder eines asymmetrischen Algorithmus verschlüsselt werden.
ms.date: 07/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encryption [.NET], symmetric
- symmetric encryption
- cryptography [.NET], asymmetric
- asymmetric encryption
ms.assetid: 7ecce51f-db5f-4bd4-9321-cceb6fcb2a77
ms.openlocfilehash: 8a8b5988a13ab571284b08c7aaece3542467aa71
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556968"
---
# <a name="encrypting-data"></a><span data-ttu-id="96e13-103">Verschlüsseln von Daten</span><span class="sxs-lookup"><span data-stu-id="96e13-103">Encrypting Data</span></span>

<span data-ttu-id="96e13-104">Symmetrische Verschlüsselung und asymmetrische Verschlüsselung werden mit unterschiedlichen Prozesse ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="96e13-104">Symmetric encryption and asymmetric encryption are performed using different processes.</span></span> <span data-ttu-id="96e13-105">Die symmetrische Verschlüsselung wird für Streams ausgeführt und ist daher für die Verschlüsselung großer Datenmengen geeignet.</span><span class="sxs-lookup"><span data-stu-id="96e13-105">Symmetric encryption is performed on streams and is therefore useful to encrypt large amounts of data.</span></span> <span data-ttu-id="96e13-106">Die asymmetrische Verschlüsselung wird für eine kleine Anzahl von Bytes ausgeführt und ist daher nur für kleine Datenmengen geeignet.</span><span class="sxs-lookup"><span data-stu-id="96e13-106">Asymmetric encryption is performed on a small number of bytes and is therefore useful only for small amounts of data.</span></span>  
  
## <a name="symmetric-encryption"></a><span data-ttu-id="96e13-107">Symmetrische Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="96e13-107">Symmetric Encryption</span></span>  

<span data-ttu-id="96e13-108">Die verwalteten symmetrischen Kryptografieklassen werden mit einer speziellen Streamklasse namens <xref:System.Security.Cryptography.CryptoStream> verwendet, die Daten verschlüsselt, die in den jeweiligen Stream eingelesen wurden.</span><span class="sxs-lookup"><span data-stu-id="96e13-108">The managed symmetric cryptography classes are used with a special stream class called a <xref:System.Security.Cryptography.CryptoStream> that encrypts data read into the stream.</span></span> <span data-ttu-id="96e13-109">Die **CryptoStream** -Klasse wird mit einer verwalteten Streamklasse initialisiert, einer Klasse, die die- <xref:System.Security.Cryptography.ICryptoTransform> Schnittstelle (erstellt aus einer Klasse, die einen kryptografischen Algorithmus implementiert) implementiert, und einer- <xref:System.Security.Cryptography.CryptoStreamMode> Enumeration, die den Typ des Zugriffs beschreibt, der für den **kryptostream**zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="96e13-109">The **CryptoStream** class is initialized with a managed stream class, a class that implements the <xref:System.Security.Cryptography.ICryptoTransform> interface (created from a class that implements a cryptographic algorithm), and a <xref:System.Security.Cryptography.CryptoStreamMode> enumeration that describes the type of access permitted to the **CryptoStream**.</span></span> <span data-ttu-id="96e13-110">Die **CryptoStream** -Klasse kann mit jeder Klasse initialisiert werden, die von der-Klasse abgeleitet wird <xref:System.IO.Stream> , einschließlich <xref:System.IO.FileStream> , <xref:System.IO.MemoryStream> und <xref:System.Net.Sockets.NetworkStream> .</span><span class="sxs-lookup"><span data-stu-id="96e13-110">The **CryptoStream** class can be initialized using any class that derives from the <xref:System.IO.Stream> class, including <xref:System.IO.FileStream>, <xref:System.IO.MemoryStream>, and <xref:System.Net.Sockets.NetworkStream>.</span></span> <span data-ttu-id="96e13-111">Mit diesen Klassen können Sie die unterschiedlichsten Streamobjekte symmetrisch verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="96e13-111">Using these classes, you can perform symmetric encryption on a variety of stream objects.</span></span>  
  
<span data-ttu-id="96e13-112">Im folgenden Beispiel wird veranschaulicht, wie eine neue Instanz der Standard Implementierungs Klasse für den- <xref:System.Security.Cryptography.Aes> Algorithmus erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="96e13-112">The following example illustrates how to create a new instance of the default implementation class for the <xref:System.Security.Cryptography.Aes> algorithm.</span></span> <span data-ttu-id="96e13-113">Die-Instanz wird verwendet, um die Verschlüsselung für eine **CryptoStream** -Klasse auszuführen.</span><span class="sxs-lookup"><span data-stu-id="96e13-113">The instance is used to perform encryption on a **CryptoStream** class.</span></span> <span data-ttu-id="96e13-114">In diesem Beispiel wird die **CryptoStream** -Klasse mit einem Streamobjekt namens `myStream` initialisiert, bei dem es sich um einen beliebigen Typ eines verwalteten Streams handeln kann.</span><span class="sxs-lookup"><span data-stu-id="96e13-114">In this example, the **CryptoStream** is initialized with a stream object called `myStream` that can be any type of managed stream.</span></span> <span data-ttu-id="96e13-115">An **die Methode "** -Methode" von der **AES** -Klasse werden der Schlüssel und der IV übergeben, die für die Verschlüsselung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="96e13-115">The **CreateEncryptor** method from the **Aes** class is passed the key and IV that are used for encryption.</span></span> <span data-ttu-id="96e13-116">In diesem Fall werden der Standardschlüssel und der IV verwendet, die von `aes` erzeugt wurden.</span><span class="sxs-lookup"><span data-stu-id="96e13-116">In this case, the default key and IV generated from `aes` are used.</span></span>
  
```vb  
Dim aes As Aes = Aes.Create()  
Dim cryptStream As New CryptoStream(myStream, aes.CreateEncryptor(key, iv), CryptoStreamMode.Write)  
```  
  
```csharp  
Aes aes = Aes.Create();  
CryptoStream cryptStream = new CryptoStream(myStream, aes.CreateEncryptor(key, iv), CryptoStreamMode.Write);  
```  
  
<span data-ttu-id="96e13-117">Nachdem dieser Code ausgeführt wurde, werden alle Daten, die in das **CryptoStream** -Objekt geschrieben werden, mithilfe des AES-Algorithmus verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="96e13-117">After this code is executed, any data written to the **CryptoStream** object is encrypted using the AES algorithm.</span></span>  
  
<span data-ttu-id="96e13-118">Das folgende Beispiel veranschaulicht den gesamten Prozess: das Erzeugen und Verschlüsseln des Streams, das Schreiben in den Stream und das Schließen des Streams.</span><span class="sxs-lookup"><span data-stu-id="96e13-118">The following example shows the entire process of creating a stream, encrypting the stream, writing to the stream, and closing the stream.</span></span> <span data-ttu-id="96e13-119">In diesem Beispiel wird ein Dateistream erstellt, der mit der **CryptoStream** -Klasse und der **AES** -Klasse verschlüsselt wird.</span><span class="sxs-lookup"><span data-stu-id="96e13-119">This example creates a file stream that is encrypted using the **CryptoStream** class and the **Aes** class.</span></span> <span data-ttu-id="96e13-120">Mit der <xref:System.IO.StreamWriter> -Klasse wird eine Nachricht in den verschlüsselten Stream geschrieben.</span><span class="sxs-lookup"><span data-stu-id="96e13-120">A message is written to the encrypted stream with the <xref:System.IO.StreamWriter> class.</span></span>
  
:::code language="csharp" source="snippets/encrypting-data/csharp/aes-encrypt.cs":::
:::code language="vb" source="snippets/encrypting-data/vb/aes-encrypt.vb":::

<span data-ttu-id="96e13-121">Der Code verschlüsselt den Stream mit dem symmetrischen AES-Algorithmus und schreibt "Hallo Welt!"</span><span class="sxs-lookup"><span data-stu-id="96e13-121">The code encrypts the stream using the AES symmetric algorithm, and writes "Hello World!"</span></span> <span data-ttu-id="96e13-122">in den Stream.</span><span class="sxs-lookup"><span data-stu-id="96e13-122">to the stream.</span></span> <span data-ttu-id="96e13-123">Wenn der Code erfolgreich ist, erstellt er eine verschlüsselte Datei mit dem Namen *TestData.txt* und zeigt den folgenden Text in der Konsole an:</span><span class="sxs-lookup"><span data-stu-id="96e13-123">If the code is successful, it creates an encrypted file named *TestData.txt* and displays the following text to the console:</span></span>  
  
```console  
The text was encrypted.  
```  

<span data-ttu-id="96e13-124">Sie können die Datei mithilfe des symmetrischen Entschlüsselungs Beispiels in Entschlüsseln von [Daten](decrypting-data.md)entschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="96e13-124">You can decrypt the file by using the symmetric decryption example in [Decrypting Data](decrypting-data.md).</span></span> <span data-ttu-id="96e13-125">In diesem Beispiel und in diesem Beispiel wird derselbe Schlüssel und IV angegeben.</span><span class="sxs-lookup"><span data-stu-id="96e13-125">That example and this example specify the same key and IV.</span></span>

<span data-ttu-id="96e13-126">Wenn jedoch eine Ausnahme ausgelöst wird, zeigt der Code den folgenden Text in der Konsole an:</span><span class="sxs-lookup"><span data-stu-id="96e13-126">However, if an exception is raised, the code displays the following text to the console:</span></span>  
  
```console  
The encryption failed.  
```

## <a name="asymmetric-encryption"></a><span data-ttu-id="96e13-127">Asymmetrische Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="96e13-127">Asymmetric Encryption</span></span>

<span data-ttu-id="96e13-128">Asymmetrische Algorithmen werden in der Regel zum Verschlüsseln kleiner Datenmengen verwendet, beispielsweise zum Verschlüsseln eines symmetrischen Schlüssels und eines Initialisierungsvektors (IV).</span><span class="sxs-lookup"><span data-stu-id="96e13-128">Asymmetric algorithms are usually used to encrypt small amounts of data such as the encryption of a symmetric key and IV.</span></span> <span data-ttu-id="96e13-129">Üblicherweise verwendet eine Person, die eine asymmetrische Verschlüsselung ausführt, einen öffentlichen Schlüssel, den eine andere Person erzeugt hat.</span><span class="sxs-lookup"><span data-stu-id="96e13-129">Typically, an individual performing asymmetric encryption uses the public key generated by another party.</span></span> <span data-ttu-id="96e13-130">Die- <xref:System.Security.Cryptography.RSA> Klasse wird zu diesem Zweck von .NET bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="96e13-130">The <xref:System.Security.Cryptography.RSA> class is provided by .NET for this purpose.</span></span>  
  
<span data-ttu-id="96e13-131">Im folgenden Beispiel werden die Informationen eines öffentlichen Schlüssels verwendet, um einen symmetrischen Schlüssel und eine IV zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="96e13-131">The following example uses public key information to encrypt a symmetric key and IV.</span></span> <span data-ttu-id="96e13-132">Zwei Bytearrays werden initialisiert, die den öffentlichen Schlüssel einer dritten Person darstellen.</span><span class="sxs-lookup"><span data-stu-id="96e13-132">Two byte arrays are initialized that represent the public key of a third party.</span></span> <span data-ttu-id="96e13-133">Ein <xref:System.Security.Cryptography.RSAParameters> -Objekt wird mit diesen Werten initialisiert.</span><span class="sxs-lookup"><span data-stu-id="96e13-133">An <xref:System.Security.Cryptography.RSAParameters> object is initialized to these values.</span></span> <span data-ttu-id="96e13-134">Anschließend wird das **RSAParameters** -Objekt (zusammen mit dem öffentlichen Schlüssel, das es darstellt) mithilfe der-Methode in eine **RSA** -Instanz importiert <xref:System.Security.Cryptography.RSA.ImportParameters%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="96e13-134">Next, the **RSAParameters** object (along with the public key it represents) is imported into an **RSA** instance using the <xref:System.Security.Cryptography.RSA.ImportParameters%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="96e13-135">Schließlich werden der von einer-Klasse erstellte private Schlüssel und IV <xref:System.Security.Cryptography.Aes> verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="96e13-135">Finally, the private key and IV created by an <xref:System.Security.Cryptography.Aes> class are encrypted.</span></span> <span data-ttu-id="96e13-136">Für dieses Beispiel ist ein System erforderlich, auf dem 128-Bit-Verschlüsselung installiert ist.</span><span class="sxs-lookup"><span data-stu-id="96e13-136">This example requires systems to have 128-bit encryption installed.</span></span>  
  
```vb  
Imports System
Imports System.Security.Cryptography

Module Module1

    Sub Main()
        'Initialize the byte arrays to the public key information.  
        Dim modulus As Byte() = {214, 46, 220, 83, 160, 73, 40, 39, 201, 155, 19, 202, 3, 11, 191, 178, 56, 74, 90, 36, 248, 103, 18, 144, 170, 163, 145, 87, 54, 61, 34, 220, 222, 207, 137, 149, 173, 14, 92, 120, 206, 222, 158, 28, 40, 24, 30, 16, 175, 108, 128, 35, 230, 118, 40, 121, 113, 125, 216, 130, 11, 24, 90, 48, 194, 240, 105, 44, 76, 34, 57, 249, 228, 125, 80, 38, 9, 136, 29, 117, 207, 139, 168, 181, 85, 137, 126, 10, 126, 242, 120, 247, 121, 8, 100, 12, 201, 171, 38, 226, 193, 180, 190, 117, 177, 87, 143, 242, 213, 11, 44, 180, 113, 93, 106, 99, 179, 68, 175, 211, 164, 116, 64, 148, 226, 254, 172, 147}

        Dim exponent As Byte() = {1, 0, 1}

        'Create values to store encrypted symmetric keys.  
        Dim encryptedSymmetricKey() As Byte
        Dim encryptedSymmetricIV() As Byte

        'Create a new instance of the default RSA implementation class.
        Dim rsa As RSA = RSA.Create()

        'Create a new instance of the RSAParameters structure.  
        Dim rsaKeyInfo As New RSAParameters()

        'Set rsaKeyInfo to the public key values.
        rsaKeyInfo.Modulus = modulus
        rsaKeyInfo.Exponent = exponent

        'Import key parameters into rsa
        rsa.ImportParameters(rsaKeyInfo)

        'Create a new instance of the default Aes implementation class.  
        Dim aes As Aes = Aes.Create()

        'Encrypt the symmetric key and IV.  
        encryptedSymmetricKey = rsa.Encrypt(aes.Key, RSAEncryptionPadding.Pkcs1)
        encryptedSymmetricIV = rsa.Encrypt(aes.IV, RSAEncryptionPadding.Pkcs1)
    End Sub

End Module
```  
  
```csharp  
using System;
using System.Security.Cryptography;

class Class1
{
    static void Main()
    {
        //Initialize the byte arrays to the public key information.  
        byte[] modulus = {214,46,220,83,160,73,40,39,201,155,19,202,3,11,191,178,56,
            74,90,36,248,103,18,144,170,163,145,87,54,61,34,220,222,
            207,137,149,173,14,92,120,206,222,158,28,40,24,30,16,175,
            108,128,35,230,118,40,121,113,125,216,130,11,24,90,48,194,
            240,105,44,76,34,57,249,228,125,80,38,9,136,29,117,207,139,
            168,181,85,137,126,10,126,242,120,247,121,8,100,12,201,171,
            38,226,193,180,190,117,177,87,143,242,213,11,44,180,113,93,
            106,99,179,68,175,211,164,116,64,148,226,254,172,147};

        byte[] exponent = { 1, 0, 1 };

        //Create values to store encrypted symmetric keys.  
        byte[] encryptedSymmetricKey;
        byte[] encryptedSymmetricIV;

        //Create a new instance of the RSA class.  
        RSA rsa = RSA.Create();

        //Create a new instance of the RSAParameters structure.  
        RSAParameters rsaKeyInfo = new RSAParameters();

        //Set rsaKeyInfo to the public key values.
        rsaKeyInfo.Modulus = modulus;
        rsaKeyInfo.Exponent = exponent;

        //Import key parameters into rsa.  
        rsa.ImportParameters(rsaKeyInfo);

        //Create a new instance of the default Aes implementation class.  
        Aes aes = Aes.Create();

        //Encrypt the symmetric key and IV.  
        encryptedSymmetricKey = rsa.Encrypt(aes.Key, RSAEncryptionPadding.Pkcs1);
        encryptedSymmetricIV = rsa.Encrypt(aes.IV, RSAEncryptionPadding.Pkcs1);
    }
}
```  
  
## <a name="see-also"></a><span data-ttu-id="96e13-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="96e13-137">See also</span></span>

- [<span data-ttu-id="96e13-138">Erzeugen von Schlüsseln für die Ver- und Entschlüsselung</span><span class="sxs-lookup"><span data-stu-id="96e13-138">Generating Keys for Encryption and Decryption</span></span>](generating-keys-for-encryption-and-decryption.md)
- [<span data-ttu-id="96e13-139">Entschlüsseln von Daten</span><span class="sxs-lookup"><span data-stu-id="96e13-139">Decrypting Data</span></span>](decrypting-data.md)
- [<span data-ttu-id="96e13-140">Kryptografische Dienste</span><span class="sxs-lookup"><span data-stu-id="96e13-140">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="96e13-141">Plattformübergreifende Kryptografie</span><span class="sxs-lookup"><span data-stu-id="96e13-141">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="96e13-142">Verwenden der Auffüllung für die Zeitsteuerung bei Sicherheitsrisiken mit symmetrischer Entschlüsselung im CBC-Modus</span><span class="sxs-lookup"><span data-stu-id="96e13-142">Timing vulnerabilities with CBC-mode symmetric decryption using padding</span></span>](vulnerabilities-cbc-mode.md)
- [<span data-ttu-id="96e13-143">ASP.net Core Datenschutz</span><span class="sxs-lookup"><span data-stu-id="96e13-143">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
