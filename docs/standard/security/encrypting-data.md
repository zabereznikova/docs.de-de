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
ms.openlocfilehash: 75bb0fa52b8002efe0027f026de8c0910735e55e
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440971"
---
# <a name="encrypting-data"></a>Verschlüsseln von Daten

Symmetrische Verschlüsselung und asymmetrische Verschlüsselung werden mit unterschiedlichen Prozesse ausgeführt. Die symmetrische Verschlüsselung wird für Streams ausgeführt und ist daher für die Verschlüsselung großer Datenmengen geeignet. Die asymmetrische Verschlüsselung wird für eine kleine Anzahl von Bytes ausgeführt und ist daher nur für kleine Datenmengen geeignet.  
  
## <a name="symmetric-encryption"></a>Symmetrische Verschlüsselung  

Die verwalteten symmetrischen Kryptografieklassen werden mit einer speziellen Streamklasse namens <xref:System.Security.Cryptography.CryptoStream> verwendet, die Daten verschlüsselt, die in den jeweiligen Stream eingelesen wurden. Die **CryptoStream** -Klasse wird mit einer verwalteten Streamklasse initialisiert, einer Klasse, die die- <xref:System.Security.Cryptography.ICryptoTransform> Schnittstelle (erstellt aus einer Klasse, die einen kryptografischen Algorithmus implementiert) implementiert, und einer- <xref:System.Security.Cryptography.CryptoStreamMode> Enumeration, die den Typ des Zugriffs beschreibt, der für den **kryptostream** zulässig ist. Die **CryptoStream** -Klasse kann mit jeder Klasse initialisiert werden, die von der-Klasse abgeleitet wird <xref:System.IO.Stream> , einschließlich <xref:System.IO.FileStream> , <xref:System.IO.MemoryStream> und <xref:System.Net.Sockets.NetworkStream> . Mit diesen Klassen können Sie die unterschiedlichsten Streamobjekte symmetrisch verschlüsseln.  
  
Im folgenden Beispiel wird veranschaulicht, wie eine neue Instanz der Standard Implementierungs Klasse für den- <xref:System.Security.Cryptography.Aes> Algorithmus erstellt wird. Die-Instanz wird verwendet, um die Verschlüsselung für eine **CryptoStream** -Klasse auszuführen. In diesem Beispiel wird die **CryptoStream** -Klasse mit einem Streamobjekt namens `myStream` initialisiert, bei dem es sich um einen beliebigen Typ eines verwalteten Streams handeln kann. An **die Methode "** -Methode" von der **AES** -Klasse werden der Schlüssel und der IV übergeben, die für die Verschlüsselung verwendet werden. In diesem Fall werden der Standardschlüssel und der IV verwendet, die von `aes` erzeugt wurden.
  
```vb  
Dim aes As Aes = Aes.Create()  
Dim cryptStream As New CryptoStream(myStream, aes.CreateEncryptor(key, iv), CryptoStreamMode.Write)  
```  
  
```csharp  
Aes aes = Aes.Create();  
CryptoStream cryptStream = new CryptoStream(myStream, aes.CreateEncryptor(key, iv), CryptoStreamMode.Write);  
```  
  
Nachdem dieser Code ausgeführt wurde, werden alle Daten, die in das **CryptoStream** -Objekt geschrieben werden, mithilfe des AES-Algorithmus verschlüsselt.  
  
Das folgende Beispiel veranschaulicht den gesamten Prozess: das Erzeugen und Verschlüsseln des Streams, das Schreiben in den Stream und das Schließen des Streams. In diesem Beispiel wird ein Dateistream erstellt, der mit der **CryptoStream** -Klasse und der **AES** -Klasse verschlüsselt wird. Generierter IV wird an den Anfang von geschrieben <xref:System.IO.FileStream> , sodass er gelesen und für die Entschlüsselung verwendet werden kann. Anschließend wird eine Nachricht mit der-Klasse in den verschlüsselten Stream geschrieben <xref:System.IO.StreamWriter> . Derselbe Schlüssel kann mehrmals zum Verschlüsseln und Entschlüsseln von Daten verwendet werden, es wird jedoch empfohlen, jedes Mal einen neuen zufälligen IV zu generieren. Auf diese Weise unterscheiden sich die verschlüsselten Daten immer, auch wenn nur Text gleich ist.
  
:::code language="csharp" source="snippets/encrypting-data/csharp/aes-encrypt.cs":::
:::code language="vb" source="snippets/encrypting-data/vb/aes-encrypt.vb":::

Der Code verschlüsselt den Stream mit dem symmetrischen AES-Algorithmus und schreibt IV und verschlüsselt dann "Hallo Welt!" in den Stream. Wenn der Code erfolgreich ist, erstellt er eine verschlüsselte Datei mit dem Namen *TestData.txt* und zeigt den folgenden Text in der Konsole an:
  
```console  
The text was encrypted.
```  

Sie können die Datei mithilfe des symmetrischen Entschlüsselungs Beispiels in Entschlüsseln von [Daten](decrypting-data.md)entschlüsseln. In diesem Beispiel und diesem Beispiel wird derselbe Schlüssel angegeben.

Wenn jedoch eine Ausnahme ausgelöst wird, zeigt der Code den folgenden Text in der Konsole an:
  
```console  
The encryption failed.
```

## <a name="asymmetric-encryption"></a>Asymmetrische Verschlüsselung

Asymmetrische Algorithmen werden in der Regel zum Verschlüsseln kleiner Datenmengen verwendet, beispielsweise zum Verschlüsseln eines symmetrischen Schlüssels und eines Initialisierungsvektors (IV). Üblicherweise verwendet eine Person, die eine asymmetrische Verschlüsselung ausführt, einen öffentlichen Schlüssel, den eine andere Person erzeugt hat. Die- <xref:System.Security.Cryptography.RSA> Klasse wird zu diesem Zweck von .NET bereitgestellt.  
  
Im folgenden Beispiel werden die Informationen eines öffentlichen Schlüssels verwendet, um einen symmetrischen Schlüssel und eine IV zu verschlüsseln. Zwei Bytearrays werden initialisiert, die den öffentlichen Schlüssel einer dritten Person darstellen. Ein <xref:System.Security.Cryptography.RSAParameters> -Objekt wird mit diesen Werten initialisiert. Anschließend wird das **RSAParameters** -Objekt (zusammen mit dem öffentlichen Schlüssel, das es darstellt) mithilfe der-Methode in eine **RSA** -Instanz importiert <xref:System.Security.Cryptography.RSA.ImportParameters%2A?displayProperty=nameWithType> . Schließlich werden der von einer-Klasse erstellte private Schlüssel und IV <xref:System.Security.Cryptography.Aes> verschlüsselt. Für dieses Beispiel ist ein System erforderlich, auf dem 128-Bit-Verschlüsselung installiert ist.  
  
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
  
## <a name="see-also"></a>Siehe auch

- [Erzeugen von Schlüsseln für die Ver- und Entschlüsselung](generating-keys-for-encryption-and-decryption.md)
- [Entschlüsseln von Daten](decrypting-data.md)
- [Kryptografische Dienste](cryptographic-services.md)
- [Plattformübergreifende Kryptografie](cross-platform-cryptography.md)
- [Verwenden der Auffüllung für die Zeitsteuerung bei Sicherheitsrisiken mit symmetrischer Entschlüsselung im CBC-Modus](vulnerabilities-cbc-mode.md)
- [ASP.net Core Datenschutz](/aspnet/core/security/data-protection/introduction)
