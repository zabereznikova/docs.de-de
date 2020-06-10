---
title: Verschlüsseln von Daten
description: Erfahren Sie, wie Sie Daten in .net verschlüsseln. Sie können die symmetrische Verschlüsselung für Datenströme verwenden, oder Sie können die asymmetrische Verschlüsselung für eine kleine Anzahl von Bytes verwenden.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encryption [.NET Framework], symmetric
- symmetric encryption
- cryptography [.NET Framework], asymmetric
- asymmetric encryption
ms.assetid: 7ecce51f-db5f-4bd4-9321-cceb6fcb2a77
ms.openlocfilehash: 6cebdecd461f28f8228ebb8440dbff218dc211db
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2020
ms.locfileid: "84662523"
---
# <a name="encrypting-data"></a><span data-ttu-id="ba029-104">Verschlüsseln von Daten</span><span class="sxs-lookup"><span data-stu-id="ba029-104">Encrypting Data</span></span>
<span data-ttu-id="ba029-105">Symmetrische Verschlüsselung und asymmetrische Verschlüsselung werden mit unterschiedlichen Prozesse ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ba029-105">Symmetric encryption and asymmetric encryption are performed using different processes.</span></span> <span data-ttu-id="ba029-106">Die symmetrische Verschlüsselung wird für Streams ausgeführt und ist daher für die Verschlüsselung großer Datenmengen geeignet.</span><span class="sxs-lookup"><span data-stu-id="ba029-106">Symmetric encryption is performed on streams and is therefore useful to encrypt large amounts of data.</span></span> <span data-ttu-id="ba029-107">Die asymmetrische Verschlüsselung wird für eine kleine Anzahl von Bytes ausgeführt und ist daher nur für kleine Datenmengen geeignet.</span><span class="sxs-lookup"><span data-stu-id="ba029-107">Asymmetric encryption is performed on a small number of bytes and is therefore useful only for small amounts of data.</span></span>  
  
## <a name="symmetric-encryption"></a><span data-ttu-id="ba029-108">Symmetrische Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="ba029-108">Symmetric Encryption</span></span>  
 <span data-ttu-id="ba029-109">Die verwalteten symmetrischen Kryptografieklassen werden mit einer speziellen Streamklasse namens <xref:System.Security.Cryptography.CryptoStream> verwendet, die Daten verschlüsselt, die in den jeweiligen Stream eingelesen wurden.</span><span class="sxs-lookup"><span data-stu-id="ba029-109">The managed symmetric cryptography classes are used with a special stream class called a <xref:System.Security.Cryptography.CryptoStream> that encrypts data read into the stream.</span></span> <span data-ttu-id="ba029-110">Die **CryptoStream** -Klasse wird mit einer verwalteten Streamklasse, mit einer Klasse, die die <xref:System.Security.Cryptography.ICryptoTransform> -Schnittstelle (erstellt aus einer Klasse, durch die ein kryptografischer Algorithmus implementiert wird) implementiert, und mit einer <xref:System.Security.Cryptography.CryptoStreamMode> -Enumeration implementiert, die die zulässige Art des Zugriffs auf die **CryptoStream**-Klasse beschreibt.</span><span class="sxs-lookup"><span data-stu-id="ba029-110">The **CryptoStream** class is initialized with a managed stream class, a class implements the <xref:System.Security.Cryptography.ICryptoTransform> interface (created from a class that implements a cryptographic algorithm), and a <xref:System.Security.Cryptography.CryptoStreamMode> enumeration that describes the type of access permitted to the **CryptoStream**.</span></span> <span data-ttu-id="ba029-111">Die **CryptoStream** -Klasse kann mit jeder Klasse initialisiert werden, die von der-Klasse abgeleitet wird <xref:System.IO.Stream> , einschließlich <xref:System.IO.FileStream> , <xref:System.IO.MemoryStream> und <xref:System.Net.Sockets.NetworkStream> .</span><span class="sxs-lookup"><span data-stu-id="ba029-111">The **CryptoStream** class can be initialized using any class that derives from the <xref:System.IO.Stream> class, including <xref:System.IO.FileStream>, <xref:System.IO.MemoryStream>, and <xref:System.Net.Sockets.NetworkStream>.</span></span> <span data-ttu-id="ba029-112">Mit diesen Klassen können Sie die unterschiedlichsten Streamobjekte symmetrisch verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="ba029-112">Using these classes, you can perform symmetric encryption on a variety of stream objects.</span></span>  
  
 <span data-ttu-id="ba029-113">Das folgende Beispiel veranschaulicht, wie eine neue Instanz der <xref:System.Security.Cryptography.RijndaelManaged> -Klasse, durch die der Rijndael-Verschlüsselungsalgorithmus implementiert wird, erstellt und zum Verschlüsseln einer **CryptoStream** -Klasse verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ba029-113">The following example illustrates how to create a new instance of the <xref:System.Security.Cryptography.RijndaelManaged> class, which implements the Rijndael encryption algorithm, and use it to perform encryption on a **CryptoStream** class.</span></span> <span data-ttu-id="ba029-114">In diesem Beispiel wird die **CryptoStream** -Klasse mit einem Streamobjekt namens `myStream` initialisiert, bei dem es sich um einen beliebigen Typ eines verwalteten Streams handeln kann.</span><span class="sxs-lookup"><span data-stu-id="ba029-114">In this example, the **CryptoStream** is initialized with a stream object called `myStream` that can be any type of managed stream.</span></span> <span data-ttu-id="ba029-115">Der **CreateEncryptor** -Methode der **RijndaelManaged** -Klasse werden der Schlüssel und der Initialisierungsvektor (IV) übergeben, die für die Verschlüsselung benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="ba029-115">The **CreateEncryptor** method from the **RijndaelManaged** class is passed the key and IV that are used for encryption.</span></span> <span data-ttu-id="ba029-116">In diesem Fall werden der Standardschlüssel und der IV verwendet, die von `rmCrypto` erzeugt wurden.</span><span class="sxs-lookup"><span data-stu-id="ba029-116">In this case, the default key and IV generated from `rmCrypto` are used.</span></span> <span data-ttu-id="ba029-117">Schließlich wird **CryptoStreamMode.Write** übergeben, wodurch Schreibzugriff auf den Stream angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="ba029-117">Finally, the **CryptoStreamMode.Write** is passed, specifying write access to the stream.</span></span>  
  
```vb  
Dim rmCrypto As New RijndaelManaged()  
Dim cryptStream As New CryptoStream(myStream, rmCrypto.CreateEncryptor(rmCrypto.Key, rmCrypto.IV), CryptoStreamMode.Write)  
```  
  
```csharp  
RijndaelManaged rmCrypto = new RijndaelManaged();  
CryptoStream cryptStream = new CryptoStream(myStream, rmCrypto.CreateEncryptor(), CryptoStreamMode.Write);  
```  
  
 <span data-ttu-id="ba029-118">Nach der Ausführung dieses Codes werden alle in das **CryptoStream** -Objekt geschriebenen Daten mit dem Rijndael-Algorithmus verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="ba029-118">After this code is executed, any data written to the **CryptoStream** object is encrypted using the Rijndael algorithm.</span></span>  
  
 <span data-ttu-id="ba029-119">Das folgende Beispiel veranschaulicht den gesamten Prozess: das Erzeugen und Verschlüsseln des Streams, das Schreiben in den Stream und das Schließen des Streams.</span><span class="sxs-lookup"><span data-stu-id="ba029-119">The following example shows the entire process of creating a stream, encrypting the stream, writing to the stream, and closing the stream.</span></span> <span data-ttu-id="ba029-120">In diesem Beispiel wird ein Netzwerkstream erzeugt, der mit der **CryptoStream** -Klasse und der **RijndaelManaged** -Klasse verschlüsselt wird.</span><span class="sxs-lookup"><span data-stu-id="ba029-120">This example creates a network stream that is encrypted using the **CryptoStream** class and the **RijndaelManaged** class.</span></span> <span data-ttu-id="ba029-121">Mit der <xref:System.IO.StreamWriter> -Klasse wird eine Nachricht in den verschlüsselten Stream geschrieben.</span><span class="sxs-lookup"><span data-stu-id="ba029-121">A message is written to the encrypted stream with the <xref:System.IO.StreamWriter> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ba029-122">Sie können dieses Beispiel auch dazu verwenden, in eine Datei zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="ba029-122">You can also use this example to write to a file.</span></span> <span data-ttu-id="ba029-123">Löschen Sie hierzu den <xref:System.Net.Sockets.TcpClient> -Verweis, und ersetzen Sie den <xref:System.Net.Sockets.NetworkStream> durch einen <xref:System.IO.FileStream>.</span><span class="sxs-lookup"><span data-stu-id="ba029-123">To do that, delete the <xref:System.Net.Sockets.TcpClient> reference and replace the <xref:System.Net.Sockets.NetworkStream> with a <xref:System.IO.FileStream>.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Security.Cryptography  
Imports System.Net.Sockets  
  
Module Module1  
Sub Main()  
   Try  
      'Create a TCP connection to a listening TCP process.  
      'Use "localhost" to specify the current computer or  
      'replace "localhost" with the IP address of the
      'listening process.
      Dim tcp As New TcpClient("localhost", 11000)  
  
      'Create a network stream from the TCP connection.
      Dim netStream As NetworkStream = tcp.GetStream()  
  
      'Create a new instance of the RijndaelManaged class  
      'and encrypt the stream.  
      Dim rmCrypto As New RijndaelManaged()  
  
            Dim key As Byte() = {&H1, &H2, &H3, &H4, &H5, &H6, &H7, &H8, &H9, &H10, &H11, &H12, &H13, &H14, &H15, &H16}  
            Dim iv As Byte() = {&H1, &H2, &H3, &H4, &H5, &H6, &H7, &H8, &H9, &H10, &H11, &H12, &H13, &H14, &H15, &H16}  
  
      'Create a CryptoStream, pass it the NetworkStream, and encrypt
      'it with the Rijndael class.  
      Dim cryptStream As New CryptoStream(netStream, rmCrypto.CreateEncryptor(key, iv), CryptoStreamMode.Write)  
  
      'Create a StreamWriter for easy writing to the
      'network stream.  
      Dim sWriter As New StreamWriter(cryptStream)  
  
      'Write to the stream.  
      sWriter.WriteLine("Hello World!")  
  
      'Inform the user that the message was written  
      'to the stream.  
      Console.WriteLine("The message was sent.")  
  
      'Close all the connections.  
      sWriter.Close()  
      cryptStream.Close()  
      netStream.Close()  
      tcp.Close()  
   Catch  
      'Inform the user that an exception was raised.  
      Console.WriteLine("The connection failed.")  
   End Try  
End Sub  
End Module  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Security.Cryptography;  
using System.Net.Sockets;  
  
public class main  
{  
   public static void Main(string[] args)  
   {  
      try  
      {  
         //Create a TCP connection to a listening TCP process.  
         //Use "localhost" to specify the current computer or  
         //replace "localhost" with the IP address of the
         //listening process.
         TcpClient tcp = new TcpClient("localhost",11000);  
  
         //Create a network stream from the TCP connection.
         NetworkStream netStream = tcp.GetStream();  
  
         //Create a new instance of the RijndaelManaged class  
         // and encrypt the stream.  
         RijndaelManaged rmCrypto = new RijndaelManaged();  
  
         byte[] key = {0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07, 0x08, 0x09, 0x10, 0x11, 0x12, 0x13, 0x14, 0x15, 0x16};  
         byte[] iv = {0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07, 0x08, 0x09, 0x10, 0x11, 0x12, 0x13, 0x14, 0x15, 0x16};  
  
         //Create a CryptoStream, pass it the NetworkStream, and encrypt
         //it with the Rijndael class.  
         CryptoStream cryptStream = new CryptoStream(netStream,
         rmCrypto.CreateEncryptor(key, iv),
         CryptoStreamMode.Write);  
  
         //Create a StreamWriter for easy writing to the
         //network stream.  
         StreamWriter sWriter = new StreamWriter(cryptStream);  
  
         //Write to the stream.  
         sWriter.WriteLine("Hello World!");  
  
         //Inform the user that the message was written  
         //to the stream.  
         Console.WriteLine("The message was sent.");  
  
         //Close all the connections.  
         sWriter.Close();  
         cryptStream.Close();  
         netStream.Close();  
         tcp.Close();  
      }  
      catch  
      {  
         //Inform the user that an exception was raised.  
         Console.WriteLine("The connection failed.");  
      }  
   }  
}  
```  
  
 <span data-ttu-id="ba029-124">Damit das vorherige Beispiel erfolgreich ausgeführt werden kann, muss es einen Prozess geben, der an der IP‑Adresse und der Portnummer lauscht, die in der <xref:System.Net.Sockets.TcpClient> -Klasse angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="ba029-124">For the previous example to execute successfully, there must be a process listening on the IP address and port number specified in the <xref:System.Net.Sockets.TcpClient> class.</span></span> <span data-ttu-id="ba029-125">Wenn ein lauschender Prozess vorhanden ist, stellt der Code eine Verbindung mit diesem Prozess her, verschlüsselt den Stream mit dem symmetrischen Rijndael-Algorithmus und schreibt „Hello World!“</span><span class="sxs-lookup"><span data-stu-id="ba029-125">If a listening process exists, the code will connect to the listening process, encrypt the stream using the Rijndael symmetric algorithm, and write "Hello World!"</span></span> <span data-ttu-id="ba029-126">in den Stream.</span><span class="sxs-lookup"><span data-stu-id="ba029-126">to the stream.</span></span> <span data-ttu-id="ba029-127">Wenn der Code erfolgreich ausgeführt wurde, wird in der Konsole folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="ba029-127">If the code is successful, it displays the following text to the console:</span></span>  
  
```console  
The message was sent.  
```  
  
 <span data-ttu-id="ba029-128">Wenn jedoch kein lauschender Prozess gefunden oder eine Ausnahme ausgelöst wurde, wird in der Konsole folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="ba029-128">However, if no listening process is found or an exception is raised, the code displays the following text to the console:</span></span>  
  
```console  
The connection failed.  
```  
  
## <a name="asymmetric-encryption"></a><span data-ttu-id="ba029-129">Asymmetrische Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="ba029-129">Asymmetric Encryption</span></span>  
 <span data-ttu-id="ba029-130">Asymmetrische Algorithmen werden in der Regel zum Verschlüsseln kleiner Datenmengen verwendet, beispielsweise zum Verschlüsseln eines symmetrischen Schlüssels und eines Initialisierungsvektors (IV).</span><span class="sxs-lookup"><span data-stu-id="ba029-130">Asymmetric algorithms are usually used to encrypt small amounts of data such as the encryption of a symmetric key and IV.</span></span> <span data-ttu-id="ba029-131">Üblicherweise verwendet eine Person, die eine asymmetrische Verschlüsselung ausführt, einen öffentlichen Schlüssel, den eine andere Person erzeugt hat.</span><span class="sxs-lookup"><span data-stu-id="ba029-131">Typically, an individual performing asymmetric encryption uses the public key generated by another party.</span></span> <span data-ttu-id="ba029-132">Zu diesem Zweck wird von .NET Framework die <xref:System.Security.Cryptography.RSACryptoServiceProvider> -Klasse bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="ba029-132">The <xref:System.Security.Cryptography.RSACryptoServiceProvider> class is provided by the .NET Framework for this purpose.</span></span>  
  
 <span data-ttu-id="ba029-133">Im folgenden Beispiel werden die Informationen eines öffentlichen Schlüssels verwendet, um einen symmetrischen Schlüssel und eine IV zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="ba029-133">The following example uses public key information to encrypt a symmetric key and IV.</span></span> <span data-ttu-id="ba029-134">Zwei Bytearrays werden initialisiert, die den öffentlichen Schlüssel einer dritten Person darstellen.</span><span class="sxs-lookup"><span data-stu-id="ba029-134">Two byte arrays are initialized that represent the public key of a third party.</span></span> <span data-ttu-id="ba029-135">Ein <xref:System.Security.Cryptography.RSAParameters> -Objekt wird mit diesen Werten initialisiert.</span><span class="sxs-lookup"><span data-stu-id="ba029-135">An <xref:System.Security.Cryptography.RSAParameters> object is initialized to these values.</span></span> <span data-ttu-id="ba029-136">Anschließend wird das **RSAParameters** -Objekt (zusammen mit dem öffentlichen Schlüssel, den es darstellt) mit der **-Methode in ein** RSACryptoServiceProvider <xref:System.Security.Cryptography.RSACryptoServiceProvider.ImportParameters%2A?displayProperty=nameWithType> -Objekt importiert.</span><span class="sxs-lookup"><span data-stu-id="ba029-136">Next, the **RSAParameters** object (along with the public key it represents) is imported into an **RSACryptoServiceProvider** using the <xref:System.Security.Cryptography.RSACryptoServiceProvider.ImportParameters%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="ba029-137">Zum Schluss werden der von einer <xref:System.Security.Cryptography.RijndaelManaged> -Klasse erstellte private Schlüssel und erstellte IV verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="ba029-137">Finally, the private key and IV created by a <xref:System.Security.Cryptography.RijndaelManaged> class are encrypted.</span></span> <span data-ttu-id="ba029-138">Für dieses Beispiel ist ein System erforderlich, auf dem 128-Bit-Verschlüsselung installiert ist.</span><span class="sxs-lookup"><span data-stu-id="ba029-138">This example requires systems to have 128-bit encryption installed.</span></span>  
  
```vb  
Imports System  
Imports System.Security.Cryptography  
  
Module Module1  
  
    Sub Main()  
        'Initialize the byte arrays to the public key information.  
      Dim publicKey As Byte() =  {214, 46, 220, 83, 160, 73, 40, 39, 201, 155, 19,202, 3, 11, 191, 178, 56, 74, 90, 36, 248, 103, 18, 144, 170, 163, 145, 87, 54, 61, 34, 220, 222, 207, 137, 149, 173, 14, 92, 120, 206, 222, 158, 28, 40, 24, 30, 16, 175, 108, 128, 35, 230, 118, 40, 121, 113, 125, 216, 130, 11, 24, 90, 48, 194, 240, 105, 44, 76, 34, 57, 249, 228, 125, 80, 38, 9, 136, 29, 117, 207, 139, 168, 181, 85, 137, 126, 10, 126, 242, 120, 247, 121, 8, 100, 12, 201, 171, 38, 226, 193, 180, 190, 117, 177, 87, 143, 242, 213, 11, 44, 180, 113, 93, 106, 99, 179, 68, 175, 211, 164, 116, 64, 148, 226, 254, 172, 147}  
  
        Dim exponent As Byte() = {1, 0, 1}  
  
        'Create values to store encrypted symmetric keys.  
        Dim encryptedSymmetricKey() As Byte  
        Dim encryptedSymmetricIV() As Byte  
  
        'Create a new instance of the RSACryptoServiceProvider class.  
        Dim rsa As New RSACryptoServiceProvider()  
  
        'Create a new instance of the RSAParameters structure.  
        Dim rsaKeyInfo As New RSAParameters()  
  
        'Set rsaKeyInfo to the public key values.
        rsaKeyInfo.Modulus = publicKey  
        rsaKeyInfo.Exponent = exponent  
  
        'Import key parameters into rsa.  
        rsa.ImportParameters(rsaKeyInfo)  
  
        'Create a new instance of the RijndaelManaged class.  
        Dim RM As New RijndaelManaged()  
  
        'Encrypt the symmetric key and IV.  
        encryptedSymmetricKey = rsa.Encrypt(RM.Key, False)  
        encryptedSymmetricIV = rsa.Encrypt(RM.IV, False)  
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
      byte[] publicKey = {214,46,220,83,160,73,40,39,201,155,19,202,3,11,191,178,56,  
            74,90,36,248,103,18,144,170,163,145,87,54,61,34,220,222,  
            207,137,149,173,14,92,120,206,222,158,28,40,24,30,16,175,  
            108,128,35,230,118,40,121,113,125,216,130,11,24,90,48,194,  
            240,105,44,76,34,57,249,228,125,80,38,9,136,29,117,207,139,  
            168,181,85,137,126,10,126,242,120,247,121,8,100,12,201,171,  
            38,226,193,180,190,117,177,87,143,242,213,11,44,180,113,93,  
            106,99,179,68,175,211,164,116,64,148,226,254,172,147};  
  
      byte[] exponent = {1,0,1};  
  
      //Create values to store encrypted symmetric keys.  
      byte[] encryptedSymmetricKey;  
      byte[] encryptedSymmetricIV;  
  
      //Create a new instance of the RSACryptoServiceProvider class.  
      RSACryptoServiceProvider rsa = new RSACryptoServiceProvider();  
  
      //Create a new instance of the RSAParameters structure.  
      RSAParameters rsaKeyInfo = new RSAParameters();  
  
      //Set rsaKeyInfo to the public key values.
      rsaKeyInfo.Modulus = publicKey;  
      rsaKeyInfo.Exponent = exponent;  
  
      //Import key parameters into RSA.  
      rsa.ImportParameters(rsaKeyInfo);  
  
      //Create a new instance of the RijndaelManaged class.  
      RijndaelManaged rm = new RijndaelManaged();  
  
      //Encrypt the symmetric key and IV.  
      encryptedSymmetricKey = rsa.Encrypt(rm.Key, false);  
      encryptedSymmetricIV = rsa.Encrypt(rm.IV, false);  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="ba029-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ba029-139">See also</span></span>

- [<span data-ttu-id="ba029-140">Erzeugen von Schlüsseln für die Ver- und Entschlüsselung</span><span class="sxs-lookup"><span data-stu-id="ba029-140">Generating Keys for Encryption and Decryption</span></span>](generating-keys-for-encryption-and-decryption.md)
- [<span data-ttu-id="ba029-141">Entschlüsseln von Daten</span><span class="sxs-lookup"><span data-stu-id="ba029-141">Decrypting Data</span></span>](decrypting-data.md)
- [<span data-ttu-id="ba029-142">Kryptografiedienste</span><span class="sxs-lookup"><span data-stu-id="ba029-142">Cryptographic Services</span></span>](cryptographic-services.md)
