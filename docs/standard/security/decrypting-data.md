---
title: Entschlüsseln von Daten
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [.NET Framework], decryption
- symmetric decryption
- asymmetric decryption
- decryption
ms.assetid: 9b266b6c-a9b2-4d20-afd8-b3a0d8fd48a0
ms.openlocfilehash: 844561c0d207106a183243f5f2b3e0cea3e70422
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288367"
---
# <a name="decrypting-data"></a>Entschlüsseln von Daten

Entschlüsselung ist die Umkehrung einer Verschlüsselung. Bei einer Entschlüsselung mit geheimem Schlüssel müssen sowohl der Schlüssel als auch der Initialisierungsvektor (IV) bekannt sein, die zum Verschlüsseln der Daten verwendet wurden. Bei einer Entschlüsselung mit öffentlichem Schlüssel muss entweder der öffentliche Schlüssel (wenn die Daten mit dem privaten Schlüssel verschlüsselt wurden) oder der private Schlüssel (wenn die Daten mit dem öffentlichen Schlüssel verschlüsselt wurden) bekannt sein.

## <a name="symmetric-decryption"></a>Symmetrische Entschlüsselung

Die Entschlüsselung von Daten, die mit einem symmetrischen Algorithmus verschlüsselt wurden, ist mit der Vorgehensweise zum Verschlüsseln der Daten mit einem symmetrischen Algorithmus vergelichbar. Um Daten zu entschlüsseln, die aus einem beliebigen verwalteten Streamobjekt gelesen wurden, wird die <xref:System.Security.Cryptography.CryptoStream> -Klasse zusammen mit den von .NET Framework bereitgestellten symmetrischen Kryptografieklassen verwendet.

Im folgenden Beispiel wird veranschaulicht, wie eine neue Instanz der <xref:System.Security.Cryptography.RijndaelManaged> -Klasse erstellt und dann dazu verwendet wird, ein <xref:System.Security.Cryptography.CryptoStream> -Objekt zu entschlüsseln. In diesem Beispiel wird zunächst eine neue Instanz der **RijndaelManaged** -Klasse erstellt. Danach wird ein **CryptoStream** -Objekt erstellt und mit dem Wert eines verwalteten Streams namens `myStream`initialisiert. Anschließend werden der **CreateDecryptor** -Methode aus der **RijndaelManaged** -Klasse der Schlüssel und der IV übergeben, die für die Verschlüsselung verwendet wurden, und die Methode wird danach an den **CryptoStream** -Konstruktor übergeben. Zum Schluss wird die **CryptoStreamMode.Read** -Enumeration an den **CryptoStream** -Konstruktor übergeben, um Lesezugriff auf den Stream anzugeben.

```vb
Dim rmCrypto As New RijndaelManaged()
Dim cryptStream As New CryptoStream(myStream, rmCrypto.CreateDecryptor(rmCrypto.Key, rmCrypto.IV), CryptoStreamMode.Read)
```

```csharp
RijndaelManaged rmCrypto = new RijndaelManaged();
CryptoStream cryptStream = new CryptoStream(myStream, rmCrypto.CreateDecryptor(Key, IV), CryptoStreamMode.Read);
```

Das folgende Beispiel veranschaulicht den gesamten Prozess: das Erzeugen des Streams, das Verschlüsseln des Streams, das Lesen aus dem Stream und das Schließen des Streams. Es wird ein <xref:System.Net.Sockets.TcpListener> -Objekt erstellt, durch das ein Netzwerkstream initialisiert wird, wenn eine Verbindung zum lauschenden Objekt hergestellt wurde. Der Netzwerkstream wird anschließend mit der **CryptoStream** -Klasse und der **RijndaelManaged** -Klasse entschlüsselt. Für dieses Beispiel wird angenommen, dass die Wert des Schlüssels und der Wert des IVs entweder erfolgreich übertragen oder zuvor vereinbart wurden. Das Beispiel enthält nicht den Code, der zum Verschlüsseln und Übertragen dieser Werte erforderlich ist.

```vb
Imports System.IO
Imports System.Net
Imports System.Net.Sockets
Imports System.Security.Cryptography
Imports System.Threading

Module Module1
    Sub Main()
            'The key and IV must be the same values that were used
            'to encrypt the stream.
            Dim key As Byte() = {&H1, &H2, &H3, &H4, &H5, &H6, &H7, &H8, &H9, &H10, &H11, &H12, &H13, &H14, &H15, &H16}
            Dim iv As Byte() = {&H1, &H2, &H3, &H4, &H5, &H6, &H7, &H8, &H9, &H10, &H11, &H12, &H13, &H14, &H15, &H16}
        Try
            'Initialize a TCPListener on port 11000
            'using the current IP address.
            Dim tcpListen As New TcpListener(IPAddress.Any, 11000)

            'Start the listener.
            tcpListen.Start()

            'Check for a connection every five seconds.
            While Not tcpListen.Pending()
                Console.WriteLine("Still listening. Will try in 5 seconds.")

                Thread.Sleep(5000)
            End While

            'Accept the client if one is found.
            Dim tcp As TcpClient = tcpListen.AcceptTcpClient()

            'Create a network stream from the connection.
            Dim netStream As NetworkStream = tcp.GetStream()

            'Create a new instance of the RijndaelManaged class
            'and decrypt the stream.
            Dim rmCrypto As New RijndaelManaged()

            'Create an instance of the CryptoStream class, pass it the NetworkStream, and decrypt
            'it with the Rijndael class using the key and IV.
            Dim cryptStream As New CryptoStream(netStream, rmCrypto.CreateDecryptor(key, iv), CryptoStreamMode.Read)

            'Read the stream.
            Dim sReader As New StreamReader(cryptStream)

            'Display the message.
            Console.WriteLine("The decrypted original message: {0}", sReader.ReadToEnd())

            'Close the streams.
            sReader.Close()
            netStream.Close()
            tcp.Close()
            'Catch any exceptions.
        Catch
            Console.WriteLine("The Listener Failed.")
        End Try
    End Sub
End Module
```

```csharp
using System;
using System.IO;
using System.Net;
using System.Net.Sockets;
using System.Security.Cryptography;
using System.Threading;

class Class1
{
   static void Main(string[] args)
   {
      //The key and IV must be the same values that were used
      //to encrypt the stream.
      byte[] key = {0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07, 0x08, 0x09, 0x10, 0x11, 0x12, 0x13, 0x14, 0x15, 0x16};
      byte[] iv = {0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07, 0x08, 0x09, 0x10, 0x11, 0x12, 0x13, 0x14, 0x15, 0x16};
      try
      {
         //Initialize a TCPListener on port 11000
         //using the current IP address.
         TcpListener tcpListen = new TcpListener(IPAddress.Any, 11000);

         //Start the listener.
         tcpListen.Start();

         //Check for a connection every five seconds.
         while(!tcpListen.Pending())
         {
            Console.WriteLine("Still listening. Will try in 5 seconds.");
            Thread.Sleep(5000);
         }

         //Accept the client if one is found.
         TcpClient tcp = tcpListen.AcceptTcpClient();

         //Create a network stream from the connection.
         NetworkStream netStream = tcp.GetStream();

         //Create a new instance of the RijndaelManaged class
         // and decrypt the stream.
         RijndaelManaged rmCrypto = new RijndaelManaged();

         //Create a CryptoStream, pass it the NetworkStream, and decrypt
         //it with the Rijndael class using the key and IV.
         CryptoStream cryptStream = new CryptoStream(netStream,
            rmCrypto.CreateDecryptor(key, iv),
            CryptoStreamMode.Read);

         //Read the stream.
         StreamReader sReader = new StreamReader(cryptStream);

         //Display the message.
         Console.WriteLine("The decrypted original message: {0}", sReader.ReadToEnd());

         //Close the streams.
         sReader.Close();
         netStream.Close();
         tcp.Close();
      }
      //Catch any exceptions.
      catch
      {
         Console.WriteLine("The Listener Failed.");
      }
   }
}
```

Damit das obige Beispiel funktioniert, muss eine verschlüsselte Verbindung zum Listener hergestellt werden. Für die Verbindung müssen derselbe Schlüssel, IV und Algorithmus wie im Listener verwendet werden. Wenn eine solche Verbindung hergestellt ist, wird die Nachricht entschlüsselt und in der Konsole angezeigt.

## <a name="asymmetric-decryption"></a>Asymmetrische Entschlüsselung

In der Regel generiert ein Teilnehmer (Teilnehmer A) sowohl einen öffentlichen als auch einen privaten Schlüssel und speichert diese entweder im Arbeitsspeicher oder in einem kryptografischen Schlüsselcontainer. Teilnehmer A sendet dann den öffentlichen Schlüssel an einen anderen Teilnehmer (Teilnehmer B). Mit dem öffentlichen Schlüssel verschlüsselt Teilnehmer B Daten und sendet die Daten an Partei A zurück. Nach dem Empfang der Daten entschlüsselt Partei A Sie mithilfe des privaten Schlüssels, der entspricht. Die Entschlüsselung kann nur dann erfolgreich sein, wenn Teilnehmer A den privaten Schlüssel verwendet, der dem öffentlichen Schlüssel entspricht, den Teilnehmer B zum Verschlüsseln der Daten verwendet hat.

Informationen dazu, wie Sie einen asymmetrischen Schlüssel in einem sicheren Container für kryptografische Schlüssel speichern und später diesen asymmetrischen Schlüssel abrufen, finden Sie unter [How to: Store Asymmetric Keys in a Key Container](how-to-store-asymmetric-keys-in-a-key-container.md).

Das folgende Beispiel veranschaulicht die Entschlüsselung von zwei Bytearrays, die einen symmetrischen Schlüssel und einen IV darstellen. Informationen dazu, wie der asymmetrische öffentliche Schlüssel aus dem <xref:System.Security.Cryptography.RSACryptoServiceProvider> -Objekt in ein Format extrahiert wird, das auf einfache Weise an andere Beteiligte gesendet werden kann, finden Sie unter [Encrypting Data](encrypting-data.md)initialisiert.

```vb
'Create a new instance of the RSACryptoServiceProvider class.
Dim rsa As New RSACryptoServiceProvider()

' Export the public key information and send it to a third party.
' Wait for the third party to encrypt some data and send it back.

'Decrypt the symmetric key and IV.
symmetricKey = rsa.Decrypt(encryptedSymmetricKey, False)
symmetricIV = rsa.Decrypt(encryptedSymmetricIV, False)
```

```csharp
//Create a new instance of the RSACryptoServiceProvider class.
RSACryptoServiceProvider rsa = new RSACryptoServiceProvider();

// Export the public key information and send it to a third party.
// Wait for the third party to encrypt some data and send it back.

//Decrypt the symmetric key and IV.
symmetricKey = rsa.Decrypt(encryptedSymmetricKey, false);
symmetricIV = rsa.Decrypt(encryptedSymmetricIV , false);
```

## <a name="see-also"></a>Siehe auch

- [Erzeugen von Schlüsseln für die Ver- und Entschlüsselung](generating-keys-for-encryption-and-decryption.md)
- [Verschlüsseln von Daten](encrypting-data.md)
- [Kryptografiedienste](cryptographic-services.md)
