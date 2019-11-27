---
title: Kryptografische Signaturen
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- digital signatures
- cryptography [.NET Framework], signatures
- digital signatures, XML signing
- signatures, cryptographic
- digital signatures, generating
- verifying signatures
- generating signatures
- digital signatures, about
- encryption [.NET Framework], signatures
- security [.NET Framework], signatures
- XML signing
- digital signatures, verifying
- signing XML
ms.assetid: aa87cb7f-e608-4a81-948b-c9b8a1225783
author: mairaw
ms.author: mairaw
ms.openlocfilehash: de64af1a4617af39b0ef8e054292a402d6a145e6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350457"
---
# <a name="cryptographic-signatures"></a>Kryptografische Signaturen

Kryptografische digitale Signaturen verwenden Algorithmen für öffentliche Schlüssel, um die Datenintegrität sicherzustellen. Wenn Sie Daten mit einer digitalen Signatur signieren, kann eine andere Person die Signatur überprüfen und kann nachweisen, dass die Daten von Ihnen stammen und nicht geändert wurde, nachdem Sie sie signiert haben. Weitere Informationen zu digitalen Signaturen finden Sie unter [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md).

In diesem Thema wird erläutert, wie Sie zum Generieren und Überprüfen von digitalen Signaturen Klassen im <xref:System.Security.Cryptography?displayProperty=nameWithType> -Namespace verwenden.

## <a name="generating-signatures"></a>Generieren von Signaturen

Digitale Signaturen werden in der Regel auf Hashwerte angewendet, die größere Datenmengen darstellen. Das folgende Beispiel wendet eine digitale Signatur auf einen Hashwert an. Zuerst wird eine neue Instanz der <xref:System.Security.Cryptography.RSACryptoServiceProvider> -Klasse erstellt, um ein öffentliches/privates Schlüsselpaar zu generieren. Als Nächstes wird <xref:System.Security.Cryptography.RSACryptoServiceProvider> ein eine neue Instanz der <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> -Klasse übergeben. Dadurch wird der private Schlüssel an die <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter>-Klasse übertragen, die letztlich die digitale Signatur vornimmt. Bevor Sie den Hashcode signieren können, müssen Sie einen zu verwendenden Hashalgorithmus angeben. Dieses Beispiel verwendet den SHA1-Algorithmus. Schließlich wird die <xref:System.Security.Cryptography.AsymmetricSignatureFormatter.CreateSignature%2A> -Methode aufgerufen, um das Signieren vorzunehmen.

Aufgrund von Konnektivitätsproblemen mit SHA1 empfiehlt Microsoft SHA256 oder eine bessere.

```vb
Imports System.Security.Cryptography

Module Module1
    Sub Main()
        'The hash value to sign.
        Dim hashValue As Byte() = {59, 4, 248, 102, 77, 97, 142, 201, 210, 12, 224, 93, 25, 41, 100, 197, 213, 134, 130, 135}

        'The value to hold the signed value.
        Dim signedHashValue() As Byte

        'Generate a public/private key pair.
        Dim rsa As New RSACryptoServiceProvider()

        'Create an RSAPKCS1SignatureFormatter object and pass it
        'the RSACryptoServiceProvider to transfer the private key.
        Dim rsaFormatter As New RSAPKCS1SignatureFormatter(rsa)

        'Set the hash algorithm to SHA1.
        rsaFormatter.SetHashAlgorithm("SHA1")

        'Create a signature for hashValue and assign it to
        'signedHashValue.
        signedHashValue = rsaFormatter.CreateSignature(hashValue)
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
      //The hash value to sign.
      byte[] hashValue = {59,4,248,102,77,97,142,201,210,12,224,93,25,41,100,197,213,134,130,135};

      //The value to hold the signed value.
      byte[] signedHashValue;

      //Generate a public/private key pair.
      RSACryptoServiceProvider rsa = new RSACryptoServiceProvider();

      //Create an RSAPKCS1SignatureFormatter object and pass it the
      //RSACryptoServiceProvider to transfer the private key.
      RSAPKCS1SignatureFormatter rsaFormatter = new RSAPKCS1SignatureFormatter(rsa);

      //Set the hash algorithm to SHA1.
      rsaFormatter.SetHashAlgorithm("SHA1");

      //Create a signature for hashValue and assign it to
      //signedHashValue.
      signedHashValue = rsaFormatter.CreateSignature(hashValue);
   }
}
```

### <a name="signing-xml-files"></a>Signieren von XML-Dateien

.NET Framework stellt den <xref:System.Security.Cryptography.Xml> -Namespace bereit, der es Ihnen ermöglicht, XML-Dateien zu signieren. Das Signieren von XML-Dateien ist wichtig, wenn Sie überprüfen möchten, ob der XML-Code aus einer bestimmten Quelle stammt. Wenn Sie z. B. einen Aktienkursdienst verwenden, der XML verwendet, können Sie die Quelle der XML-Datei überprüfen, wenn sie signiert ist.

Die Klassen in diesem Namespace entsprechen den [XML Signature Syntax and Processing-Empfehlungen](https://www.w3.org/TR/xmldsig-core/) des World Wide Web Consortium.

## <a name="verifying-signatures"></a>Verifizieren von Signaturen

Um sicherzustellen, dass Daten von einem bestimmten Anbieter signiert wurden, benötigen Sie die folgenden Informationen:

- Der öffentliche Schlüssel des Anbieters, der die Daten signiert hat.

- Die digitale XML-Signatur.

- Die Daten, die signiert wurden.

- Der vom Signaturgeber verwendete Hashalgorithmus.

Zum Überprüfen einer Signatur, die von der <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> -Klasse signiert wurde, verwenden Sie die <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> -Klasse. Die <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> -Klasse muss dem öffentlichen Schlüssel des Signaturgebers bereitgestellt werden. Sie benötigen die Werte für den Modulo und den Exponenten, um den öffentlichen Schlüssel anzugeben. (Die Partei, die das Paar aus öffentlichem und privatem Schlüssel generiert hat, sollte diese Werte bereitstellen.) Erstellen Sie zuerst ein <xref:System.Security.Cryptography.RSACryptoServiceProvider> Objekt, das den öffentlichen Schlüssel enthält, mit dem die Signatur überprüft wird, und initialisieren Sie dann eine <xref:System.Security.Cryptography.RSAParameters> Struktur mit den Modulo-und Exponent-Werten, die den öffentlichen Schlüssel angeben.

Der folgende Code zeigt die Erstellung einer <xref:System.Security.Cryptography.RSAParameters> -Struktur. Die `Modulus` -Eigenschaft wird auf den Wert eines Bytearrays namens `modulusData` und die `Exponent` -Eigenschaft auf den Wert eines Bytearrays namens `exponentData`festgelegt.

```vb
Dim rsaKeyInfo As RSAParameters
rsaKeyInfo.Modulus = modulusData
rsaKeyInfo.Exponent = exponentData
```

```csharp
RSAParameters rsaKeyInfo;
rsaKeyInfo.Modulus = modulusData;
rsaKeyInfo.Exponent = exponentData;
```

Nach der Erstellung des <xref:System.Security.Cryptography.RSAParameters> -Objekts können Sie eine neue Instanz der <xref:System.Security.Cryptography.RSACryptoServiceProvider> -Klasse mit den Wert initialisieren, die in <xref:System.Security.Cryptography.RSAParameters>angegeben sind. <xref:System.Security.Cryptography.RSACryptoServiceProvider> wird dann an den Konstruktor von <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> übergeben, um den Schlüssel zu übertragen.

Dieser Prozess wird anhand des folgenden Beispiels veranschaulicht. In diesem Beispiel sind `hashValue` und `signedHashValue` Bytearrays, die von einem Remoteanbieter bereitgestellt werden. Der Remoteanbieter hat `hashValue` mithilfe des SHA1-Algorithmus signiert und so die digitale Signatur `signedHashValue`erzeugt. Mit der <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter.VerifySignature%2A?displayProperty=nameWithType>-Methode wird überprüft, ob die digitale Signatur gültig ist und zum Signieren der `hashValue`verwendet wurde.

```vb
Dim rsa As New RSACryptoServiceProvider()
rsa.ImportParameters(rsaKeyInfo)
Dim rsaDeformatter As New RSAPKCS1SignatureDeformatter(rsa)
rsaDeformatter.SetHashAlgorithm("SHA1")
If rsaDeformatter.VerifySignature(hashValue, signedHashValue) Then
   Console.WriteLine("The signature is valid.")
Else
   Console.WriteLine("The signature is not valid.")
End If
```

```csharp
RSACryptoServiceProvider rsa = new RSACryptoServiceProvider();
rsa.ImportParameters(rsaKeyInfo);
RSAPKCS1SignatureDeformatter rsaDeformatter = new RSAPKCS1SignatureDeformatter(rsa);
rsaDeformatter.SetHashAlgorithm("SHA1");
if(rsaDeformatter.VerifySignature(hashValue, signedHashValue))
{
   Console.WriteLine("The signature is valid.");
}
else
{
   Console.WriteLine("The signature is not valid.");
}
```

Dieses Codefragment zeigt "`The signature is valid`" an, wenn die Signatur gültig ist, und "`The signature is not valid`", wenn sie ungültig ist.

## <a name="see-also"></a>Siehe auch

- [Kryptografische Dienste](../../../docs/standard/security/cryptographic-services.md)
