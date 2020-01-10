---
title: Verschlüsseln von Daten
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
ms.openlocfilehash: b335e0d39c1809b028e2005a472fe77729e9d267
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706213"
---
# <a name="encrypting-data"></a>Verschlüsseln von Daten
Symmetrische Verschlüsselung und asymmetrische Verschlüsselung werden mit unterschiedlichen Prozesse ausgeführt. Die symmetrische Verschlüsselung wird für Streams ausgeführt und ist daher für die Verschlüsselung großer Datenmengen geeignet. Die asymmetrische Verschlüsselung wird für eine kleine Anzahl von Bytes ausgeführt und ist daher nur für kleine Datenmengen geeignet.  
  
## <a name="symmetric-encryption"></a>Symmetrische Verschlüsselung  
 Die verwalteten symmetrischen Kryptografieklassen werden mit einer speziellen Streamklasse namens <xref:System.Security.Cryptography.CryptoStream> verwendet, die Daten verschlüsselt, die in den jeweiligen Stream eingelesen wurden. Die **CryptoStream** -Klasse wird mit einer verwalteten Streamklasse, mit einer Klasse, die die <xref:System.Security.Cryptography.ICryptoTransform> -Schnittstelle (erstellt aus einer Klasse, durch die ein kryptografischer Algorithmus implementiert wird) implementiert, und mit einer <xref:System.Security.Cryptography.CryptoStreamMode> -Enumeration implementiert, die die zulässige Art des Zugriffs auf die **CryptoStream**-Klasse beschreibt. Die **CryptoStream** -Klasse kann mit jeder Klasse initialisiert werden, die aus der <xref:System.IO.Stream> -Klasse abgeleitet wurde. Dazu zählen auch die Klassen <xref:System.IO.FileStream>, <xref:System.IO.MemoryStream>und <xref:System.Net.Sockets.NetworkStream>. Mit diesen Klassen können Sie die unterschiedlichsten Streamobjekte symmetrisch verschlüsseln.  
  
 Das folgende Beispiel veranschaulicht, wie eine neue Instanz der <xref:System.Security.Cryptography.RijndaelManaged> -Klasse, durch die der Rijndael-Verschlüsselungsalgorithmus implementiert wird, erstellt und zum Verschlüsseln einer **CryptoStream** -Klasse verwendet wird. In diesem Beispiel wird die **CryptoStream** -Klasse mit einem Streamobjekt namens `myStream` initialisiert, bei dem es sich um einen beliebigen Typ eines verwalteten Streams handeln kann. Der **CreateEncryptor** -Methode der **RijndaelManaged** -Klasse werden der Schlüssel und der Initialisierungsvektor (IV) übergeben, die für die Verschlüsselung benötigt werden. In diesem Fall werden der Standardschlüssel und der IV verwendet, die von `rmCrypto` erzeugt wurden. Schließlich wird **CryptoStreamMode.Write** übergeben, wodurch Schreibzugriff auf den Stream angegeben ist.  
  
```vb  
Dim rmCrypto As New RijndaelManaged()  
Dim cryptStream As New CryptoStream(myStream, rmCrypto.CreateEncryptor(rmCrypto.Key, rmCrypto.IV), CryptoStreamMode.Write)  
```  
  
```csharp  
RijndaelManaged rmCrypto = new RijndaelManaged();  
CryptoStream cryptStream = new CryptoStream(myStream, rmCrypto.CreateEncryptor(), CryptoStreamMode.Write);  
```  
  
 Nach der Ausführung dieses Codes werden alle in das **CryptoStream** -Objekt geschriebenen Daten mit dem Rijndael-Algorithmus verschlüsselt.  
  
 Das folgende Beispiel veranschaulicht den gesamten Prozess: das Erzeugen und Verschlüsseln des Streams, das Schreiben in den Stream und das Schließen des Streams. In diesem Beispiel wird ein Netzwerkstream erzeugt, der mit der **CryptoStream** -Klasse und der **RijndaelManaged** -Klasse verschlüsselt wird. Mit der <xref:System.IO.StreamWriter> -Klasse wird eine Nachricht in den verschlüsselten Stream geschrieben.  
  
> [!NOTE]
> Sie können dieses Beispiel auch dazu verwenden, in eine Datei zu schreiben. Löschen Sie hierzu den <xref:System.Net.Sockets.TcpClient> -Verweis, und ersetzen Sie den <xref:System.Net.Sockets.NetworkStream> durch einen <xref:System.IO.FileStream>.  
  
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
  
 Damit das vorherige Beispiel erfolgreich ausgeführt werden kann, muss es einen Prozess geben, der an der IP‑Adresse und der Portnummer lauscht, die in der <xref:System.Net.Sockets.TcpClient> -Klasse angegeben sind. Wenn ein lauschender Prozess vorhanden ist, stellt der Code eine Verbindung mit diesem Prozess her, verschlüsselt den Stream mit dem symmetrischen Rijndael-Algorithmus und schreibt „Hello World!“ in den Stream. Wenn der Code erfolgreich ausgeführt wurde, wird in der Konsole folgender Text angezeigt:  
  
```console  
The message was sent.  
```  
  
 Wenn jedoch kein lauschender Prozess gefunden oder eine Ausnahme ausgelöst wurde, wird in der Konsole folgender Text angezeigt:  
  
```console  
The connection failed.  
```  
  
## <a name="asymmetric-encryption"></a>Asymmetrische Verschlüsselung  
 Asymmetrische Algorithmen werden in der Regel zum Verschlüsseln kleiner Datenmengen verwendet, beispielsweise zum Verschlüsseln eines symmetrischen Schlüssels und eines Initialisierungsvektors (IV). Üblicherweise verwendet eine Person, die eine asymmetrische Verschlüsselung ausführt, einen öffentlichen Schlüssel, den eine andere Person erzeugt hat. Zu diesem Zweck wird von .NET Framework die <xref:System.Security.Cryptography.RSACryptoServiceProvider> -Klasse bereitgestellt.  
  
 Im folgenden Beispiel werden die Informationen eines öffentlichen Schlüssels verwendet, um einen symmetrischen Schlüssel und eine IV zu verschlüsseln. Zwei Bytearrays werden initialisiert, die den öffentlichen Schlüssel einer dritten Person darstellen. Ein <xref:System.Security.Cryptography.RSAParameters> -Objekt wird mit diesen Werten initialisiert. Anschließend wird das **RSAParameters** -Objekt (zusammen mit dem öffentlichen Schlüssel, den es darstellt) mit der **-Methode in ein** RSACryptoServiceProvider <xref:System.Security.Cryptography.RSACryptoServiceProvider.ImportParameters%2A?displayProperty=nameWithType> -Objekt importiert. Zum Schluss werden der von einer <xref:System.Security.Cryptography.RijndaelManaged> -Klasse erstellte private Schlüssel und erstellte IV verschlüsselt. Für dieses Beispiel ist ein System erforderlich, auf dem 128-Bit-Verschlüsselung installiert ist.  
  
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
  
## <a name="see-also"></a>Siehe auch

- [Erzeugen von Schlüsseln für die Ver- und Entschlüsselung](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md)
- [Entschlüsseln von Daten](../../../docs/standard/security/decrypting-data.md)
- [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)
