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
ms.openlocfilehash: 1de6b3f2eb30df270339910e7b8287101bde65ca
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706252"
---
# <a name="cryptographic-signatures"></a><span data-ttu-id="e53c9-102">Kryptografische Signaturen</span><span class="sxs-lookup"><span data-stu-id="e53c9-102">Cryptographic Signatures</span></span>

<span data-ttu-id="e53c9-103">Kryptografische digitale Signaturen verwenden Algorithmen für öffentliche Schlüssel, um die Datenintegrität sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="e53c9-103">Cryptographic digital signatures use public key algorithms to provide data integrity.</span></span> <span data-ttu-id="e53c9-104">Wenn Sie Daten mit einer digitalen Signatur signieren, kann eine andere Person die Signatur überprüfen und kann nachweisen, dass die Daten von Ihnen stammen und nicht geändert wurde, nachdem Sie sie signiert haben.</span><span class="sxs-lookup"><span data-stu-id="e53c9-104">When you sign data with a digital signature, someone else can verify the signature, and can prove that the data originated from you and was not altered after you signed it.</span></span> <span data-ttu-id="e53c9-105">Weitere Informationen zu digitalen Signaturen finden Sie unter [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md).</span><span class="sxs-lookup"><span data-stu-id="e53c9-105">For more information about digital signatures, see [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md).</span></span>

<span data-ttu-id="e53c9-106">In diesem Thema wird erläutert, wie Sie zum Generieren und Überprüfen von digitalen Signaturen Klassen im <xref:System.Security.Cryptography?displayProperty=nameWithType> -Namespace verwenden.</span><span class="sxs-lookup"><span data-stu-id="e53c9-106">This topic explains how to generate and verify digital signatures using classes in the <xref:System.Security.Cryptography?displayProperty=nameWithType> namespace.</span></span>

## <a name="generating-signatures"></a><span data-ttu-id="e53c9-107">Generieren von Signaturen</span><span class="sxs-lookup"><span data-stu-id="e53c9-107">Generating Signatures</span></span>

<span data-ttu-id="e53c9-108">Digitale Signaturen werden in der Regel auf Hashwerte angewendet, die größere Datenmengen darstellen.</span><span class="sxs-lookup"><span data-stu-id="e53c9-108">Digital signatures are usually applied to hash values that represent larger data.</span></span> <span data-ttu-id="e53c9-109">Das folgende Beispiel wendet eine digitale Signatur auf einen Hashwert an.</span><span class="sxs-lookup"><span data-stu-id="e53c9-109">The following example applies a digital signature to a hash value.</span></span> <span data-ttu-id="e53c9-110">Zuerst wird eine neue Instanz der <xref:System.Security.Cryptography.RSACryptoServiceProvider> -Klasse erstellt, um ein öffentliches/privates Schlüsselpaar zu generieren.</span><span class="sxs-lookup"><span data-stu-id="e53c9-110">First, a new instance of the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class is created to generate a public/private key pair.</span></span> <span data-ttu-id="e53c9-111">Als Nächstes wird <xref:System.Security.Cryptography.RSACryptoServiceProvider> ein eine neue Instanz der <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> -Klasse übergeben.</span><span class="sxs-lookup"><span data-stu-id="e53c9-111">Next, the <xref:System.Security.Cryptography.RSACryptoServiceProvider> is passed to a new instance of the <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> class.</span></span> <span data-ttu-id="e53c9-112">Dadurch wird der private Schlüssel an die <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter>-Klasse übertragen, die letztlich die digitale Signatur vornimmt.</span><span class="sxs-lookup"><span data-stu-id="e53c9-112">This transfers the private key to the <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter>, which actually performs the digital signing.</span></span> <span data-ttu-id="e53c9-113">Bevor Sie den Hashcode signieren können, müssen Sie einen zu verwendenden Hashalgorithmus angeben.</span><span class="sxs-lookup"><span data-stu-id="e53c9-113">Before you can sign the hash code, you must specify a hash algorithm to use.</span></span> <span data-ttu-id="e53c9-114">Dieses Beispiel verwendet den SHA1-Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="e53c9-114">This example uses the SHA1 algorithm.</span></span> <span data-ttu-id="e53c9-115">Schließlich wird die <xref:System.Security.Cryptography.AsymmetricSignatureFormatter.CreateSignature%2A> -Methode aufgerufen, um das Signieren vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="e53c9-115">Finally, the <xref:System.Security.Cryptography.AsymmetricSignatureFormatter.CreateSignature%2A> method is called to perform the signing.</span></span>

<span data-ttu-id="e53c9-116">Aufgrund von Konnektivitätsproblemen mit SHA1 empfiehlt Microsoft SHA256 oder eine bessere.</span><span class="sxs-lookup"><span data-stu-id="e53c9-116">Due to collision problems with SHA1, Microsoft recommends SHA256 or better.</span></span>

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

### <a name="signing-xml-files"></a><span data-ttu-id="e53c9-117">Signieren von XML-Dateien</span><span class="sxs-lookup"><span data-stu-id="e53c9-117">Signing XML Files</span></span>

<span data-ttu-id="e53c9-118">.NET Framework stellt den <xref:System.Security.Cryptography.Xml> -Namespace bereit, der es Ihnen ermöglicht, XML-Dateien zu signieren.</span><span class="sxs-lookup"><span data-stu-id="e53c9-118">The .NET Framework provides the <xref:System.Security.Cryptography.Xml> namespace, which enables you sign XML.</span></span> <span data-ttu-id="e53c9-119">Das Signieren von XML-Dateien ist wichtig, wenn Sie überprüfen möchten, ob der XML-Code aus einer bestimmten Quelle stammt.</span><span class="sxs-lookup"><span data-stu-id="e53c9-119">Signing XML is important when you want to verify that the XML originates from a certain source.</span></span> <span data-ttu-id="e53c9-120">Wenn Sie z. B. einen Aktienkursdienst verwenden, der XML verwendet, können Sie die Quelle der XML-Datei überprüfen, wenn sie signiert ist.</span><span class="sxs-lookup"><span data-stu-id="e53c9-120">For example, if you are using a stock quote service that uses XML, you can verify the source of the XML if it is signed.</span></span>

<span data-ttu-id="e53c9-121">Die Klassen in diesem Namespace entsprechen den [XML Signature Syntax and Processing-Empfehlungen](https://www.w3.org/TR/xmldsig-core/) des World Wide Web Consortium.</span><span class="sxs-lookup"><span data-stu-id="e53c9-121">The classes in this namespace follow the [XML-Signature Syntax and Processing recommendation](https://www.w3.org/TR/xmldsig-core/) from the World Wide Web Consortium.</span></span>

## <a name="verifying-signatures"></a><span data-ttu-id="e53c9-122">Verifizieren von Signaturen</span><span class="sxs-lookup"><span data-stu-id="e53c9-122">Verifying Signatures</span></span>

<span data-ttu-id="e53c9-123">Um sicherzustellen, dass Daten von einem bestimmten Anbieter signiert wurden, benötigen Sie die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="e53c9-123">To verify that data was signed by a particular party, you must have the following information:</span></span>

- <span data-ttu-id="e53c9-124">Der öffentliche Schlüssel des Anbieters, der die Daten signiert hat.</span><span class="sxs-lookup"><span data-stu-id="e53c9-124">The public key of the party that signed the data.</span></span>

- <span data-ttu-id="e53c9-125">Die digitale XML-Signatur.</span><span class="sxs-lookup"><span data-stu-id="e53c9-125">The digital signature.</span></span>

- <span data-ttu-id="e53c9-126">Die Daten, die signiert wurden.</span><span class="sxs-lookup"><span data-stu-id="e53c9-126">The data that was signed.</span></span>

- <span data-ttu-id="e53c9-127">Der vom Signaturgeber verwendete Hashalgorithmus.</span><span class="sxs-lookup"><span data-stu-id="e53c9-127">The hash algorithm used by the signer.</span></span>

<span data-ttu-id="e53c9-128">Zum Überprüfen einer Signatur, die von der <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> -Klasse signiert wurde, verwenden Sie die <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> -Klasse.</span><span class="sxs-lookup"><span data-stu-id="e53c9-128">To verify a signature signed by the <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> class, use the <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> class.</span></span> <span data-ttu-id="e53c9-129">Die <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> -Klasse muss dem öffentlichen Schlüssel des Signaturgebers bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="e53c9-129">The <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> class must be supplied the public key of the signer.</span></span> <span data-ttu-id="e53c9-130">Sie benötigen die Werte für den Modulo und den Exponenten, um den öffentlichen Schlüssel anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e53c9-130">You will need the values of the modulus and the exponent to specify the public key.</span></span> <span data-ttu-id="e53c9-131">(Die Partei, die das Paar aus öffentlichem und privatem Schlüssel generiert hat, sollte diese Werte bereitstellen.) Erstellen Sie zuerst ein <xref:System.Security.Cryptography.RSACryptoServiceProvider> Objekt, das den öffentlichen Schlüssel enthält, mit dem die Signatur überprüft wird, und initialisieren Sie dann eine <xref:System.Security.Cryptography.RSAParameters> Struktur mit den Modulo-und Exponent-Werten, die den öffentlichen Schlüssel angeben.</span><span class="sxs-lookup"><span data-stu-id="e53c9-131">(The party that generated the public/private key pair should provide these values.) First create an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object to hold the public key that will verify the signature, and then initialize an <xref:System.Security.Cryptography.RSAParameters> structure to the modulus and exponent values that specify the public key.</span></span>

<span data-ttu-id="e53c9-132">Der folgende Code zeigt die Erstellung einer <xref:System.Security.Cryptography.RSAParameters> -Struktur.</span><span class="sxs-lookup"><span data-stu-id="e53c9-132">The following code shows the creation of an <xref:System.Security.Cryptography.RSAParameters> structure.</span></span> <span data-ttu-id="e53c9-133">Die `Modulus` -Eigenschaft wird auf den Wert eines Bytearrays namens `modulusData` und die `Exponent` -Eigenschaft auf den Wert eines Bytearrays namens `exponentData`festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e53c9-133">The `Modulus` property is set to the value of a byte array called `modulusData` and the `Exponent` property is set to the value of a byte array called `exponentData`.</span></span>

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

<span data-ttu-id="e53c9-134">Nach der Erstellung des <xref:System.Security.Cryptography.RSAParameters> -Objekts können Sie eine neue Instanz der <xref:System.Security.Cryptography.RSACryptoServiceProvider> -Klasse mit den Wert initialisieren, die in <xref:System.Security.Cryptography.RSAParameters>angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="e53c9-134">After you have created the <xref:System.Security.Cryptography.RSAParameters> object, you can initialize a new instance of the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class to the values specified in <xref:System.Security.Cryptography.RSAParameters>.</span></span> <span data-ttu-id="e53c9-135"><xref:System.Security.Cryptography.RSACryptoServiceProvider> wird dann an den Konstruktor von <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> übergeben, um den Schlüssel zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="e53c9-135">The <xref:System.Security.Cryptography.RSACryptoServiceProvider> is, in turn, passed to the constructor of an <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> to transfer the key.</span></span>

<span data-ttu-id="e53c9-136">Dieser Prozess wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="e53c9-136">The following example illustrates this process.</span></span> <span data-ttu-id="e53c9-137">In diesem Beispiel sind `hashValue` und `signedHashValue` Bytearrays, die von einem Remoteanbieter bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="e53c9-137">In this example, `hashValue` and `signedHashValue` are arrays of bytes provided by a remote party.</span></span> <span data-ttu-id="e53c9-138">Der Remoteanbieter hat `hashValue` mithilfe des SHA1-Algorithmus signiert und so die digitale Signatur `signedHashValue`erzeugt.</span><span class="sxs-lookup"><span data-stu-id="e53c9-138">The remote party has signed the `hashValue` using the SHA1 algorithm, producing the digital signature `signedHashValue`.</span></span> <span data-ttu-id="e53c9-139">Mit der <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter.VerifySignature%2A?displayProperty=nameWithType>-Methode wird überprüft, ob die digitale Signatur gültig ist und zum Signieren der `hashValue`verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="e53c9-139">The <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter.VerifySignature%2A?displayProperty=nameWithType> method verifies that the digital signature is valid and was used to sign the `hashValue`.</span></span>

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

<span data-ttu-id="e53c9-140">Dieses Codefragment zeigt "`The signature is valid`" an, wenn die Signatur gültig ist, und "`The signature is not valid`", wenn sie ungültig ist.</span><span class="sxs-lookup"><span data-stu-id="e53c9-140">This code fragment will display "`The signature is valid`" if the signature is valid and "`The signature is not valid`" if it is not.</span></span>

## <a name="see-also"></a><span data-ttu-id="e53c9-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e53c9-141">See also</span></span>

- [<span data-ttu-id="e53c9-142">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="e53c9-142">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
