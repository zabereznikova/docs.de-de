---
title: Kryptografische Signaturen
ms.date: 07/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- digital signatures
- cryptography [.NET], signatures
- digital signatures, XML signing
- signatures, cryptographic
- digital signatures, generating
- verifying signatures
- generating signatures
- digital signatures, about
- encryption [.NET], signatures
- security [.NET], signatures
- XML signing
- digital signatures, verifying
- signing XML
ms.assetid: aa87cb7f-e608-4a81-948b-c9b8a1225783
ms.openlocfilehash: ce2be1d509da4e399bf87e1c8df7ba061fc2707c
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87557007"
---
# <a name="cryptographic-signatures"></a><span data-ttu-id="6c450-102">Kryptografische Signaturen</span><span class="sxs-lookup"><span data-stu-id="6c450-102">Cryptographic Signatures</span></span>

<span data-ttu-id="6c450-103">Kryptografische digitale Signaturen verwenden Algorithmen für öffentliche Schlüssel, um die Datenintegrität sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="6c450-103">Cryptographic digital signatures use public key algorithms to provide data integrity.</span></span> <span data-ttu-id="6c450-104">Wenn Sie Daten mit einer digitalen Signatur signieren, kann eine andere Person die Signatur überprüfen und kann nachweisen, dass die Daten von Ihnen stammen und nicht geändert wurde, nachdem Sie sie signiert haben.</span><span class="sxs-lookup"><span data-stu-id="6c450-104">When you sign data with a digital signature, someone else can verify the signature, and can prove that the data originated from you and was not altered after you signed it.</span></span> <span data-ttu-id="6c450-105">Weitere Informationen zu digitalen Signaturen finden Sie unter [Cryptographic Services](cryptographic-services.md).</span><span class="sxs-lookup"><span data-stu-id="6c450-105">For more information about digital signatures, see [Cryptographic Services](cryptographic-services.md).</span></span>

<span data-ttu-id="6c450-106">In diesem Thema wird erläutert, wie Sie zum Generieren und Überprüfen von digitalen Signaturen Klassen im <xref:System.Security.Cryptography> -Namespace verwenden.</span><span class="sxs-lookup"><span data-stu-id="6c450-106">This topic explains how to generate and verify digital signatures using classes in the <xref:System.Security.Cryptography> namespace.</span></span>

## <a name="generating-signatures"></a><span data-ttu-id="6c450-107">Generieren von Signaturen</span><span class="sxs-lookup"><span data-stu-id="6c450-107">Generating Signatures</span></span>

<span data-ttu-id="6c450-108">Digitale Signaturen werden in der Regel auf Hashwerte angewendet, die größere Datenmengen darstellen.</span><span class="sxs-lookup"><span data-stu-id="6c450-108">Digital signatures are usually applied to hash values that represent larger data.</span></span> <span data-ttu-id="6c450-109">Das folgende Beispiel wendet eine digitale Signatur auf einen Hashwert an.</span><span class="sxs-lookup"><span data-stu-id="6c450-109">The following example applies a digital signature to a hash value.</span></span> <span data-ttu-id="6c450-110">Zuerst wird eine neue Instanz der <xref:System.Security.Cryptography.RSA> -Klasse erstellt, um ein öffentliches/privates Schlüsselpaar zu generieren.</span><span class="sxs-lookup"><span data-stu-id="6c450-110">First, a new instance of the <xref:System.Security.Cryptography.RSA> class is created to generate a public/private key pair.</span></span> <span data-ttu-id="6c450-111">Als Nächstes wird <xref:System.Security.Cryptography.RSA> ein eine neue Instanz der <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> -Klasse übergeben.</span><span class="sxs-lookup"><span data-stu-id="6c450-111">Next, the <xref:System.Security.Cryptography.RSA> is passed to a new instance of the <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> class.</span></span> <span data-ttu-id="6c450-112">Dadurch wird der private Schlüssel an die <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter>-Klasse übertragen, die letztlich die digitale Signatur vornimmt.</span><span class="sxs-lookup"><span data-stu-id="6c450-112">This transfers the private key to the <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter>, which actually performs the digital signing.</span></span> <span data-ttu-id="6c450-113">Bevor Sie den Hashcode signieren können, müssen Sie einen zu verwendenden Hashalgorithmus angeben.</span><span class="sxs-lookup"><span data-stu-id="6c450-113">Before you can sign the hash code, you must specify a hash algorithm to use.</span></span> <span data-ttu-id="6c450-114">Dieses Beispiel verwendet den SHA1-Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="6c450-114">This example uses the SHA1 algorithm.</span></span> <span data-ttu-id="6c450-115">Schließlich wird die <xref:System.Security.Cryptography.AsymmetricSignatureFormatter.CreateSignature%2A> -Methode aufgerufen, um das Signieren vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="6c450-115">Finally, the <xref:System.Security.Cryptography.AsymmetricSignatureFormatter.CreateSignature%2A> method is called to perform the signing.</span></span>

<span data-ttu-id="6c450-116">Aufgrund von Konnektivitätsproblemen mit SHA1 empfehlen wir SHA256 oder eine bessere.</span><span class="sxs-lookup"><span data-stu-id="6c450-116">Due to collision problems with SHA1, we recommend SHA256 or better.</span></span>

```vb
Imports System.Security.Cryptography

Module Module1
    Sub Main()
        'The hash value to sign.
        Dim hashValue As Byte() = {59, 4, 248, 102, 77, 97, 142, 201, 210, 12, 224, 93, 25, 41, 100, 197, 213, 134, 130, 135}

        'The value to hold the signed value.
        Dim signedHashValue() As Byte

        'Generate a public/private key pair.
        Dim rsa As RSA = RSA.Create()

        'Create an RSAPKCS1SignatureFormatter object and pass it
        'the RSA instance to transfer the private key.
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
      RSA rsa = RSA.Create();

      //Create an RSAPKCS1SignatureFormatter object and pass it the
      //RSA instance to transfer the private key.
      RSAPKCS1SignatureFormatter rsaFormatter = new RSAPKCS1SignatureFormatter(rsa);

      //Set the hash algorithm to SHA1.
      rsaFormatter.SetHashAlgorithm("SHA1");

      //Create a signature for hashValue and assign it to
      //signedHashValue.
      signedHashValue = rsaFormatter.CreateSignature(hashValue);
   }
}
```

## <a name="verifying-signatures"></a><span data-ttu-id="6c450-117">Verifizieren von Signaturen</span><span class="sxs-lookup"><span data-stu-id="6c450-117">Verifying Signatures</span></span>

<span data-ttu-id="6c450-118">Um sicherzustellen, dass Daten von einem bestimmten Anbieter signiert wurden, benötigen Sie die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="6c450-118">To verify that data was signed by a particular party, you must have the following information:</span></span>

- <span data-ttu-id="6c450-119">Der öffentliche Schlüssel des Anbieters, der die Daten signiert hat.</span><span class="sxs-lookup"><span data-stu-id="6c450-119">The public key of the party that signed the data.</span></span>

- <span data-ttu-id="6c450-120">Die digitale XML-Signatur.</span><span class="sxs-lookup"><span data-stu-id="6c450-120">The digital signature.</span></span>

- <span data-ttu-id="6c450-121">Die Daten, die signiert wurden.</span><span class="sxs-lookup"><span data-stu-id="6c450-121">The data that was signed.</span></span>

- <span data-ttu-id="6c450-122">Der vom Signaturgeber verwendete Hashalgorithmus.</span><span class="sxs-lookup"><span data-stu-id="6c450-122">The hash algorithm used by the signer.</span></span>

<span data-ttu-id="6c450-123">Zum Überprüfen einer Signatur, die von der <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> -Klasse signiert wurde, verwenden Sie die <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> -Klasse.</span><span class="sxs-lookup"><span data-stu-id="6c450-123">To verify a signature signed by the <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> class, use the <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> class.</span></span> <span data-ttu-id="6c450-124">Die <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> -Klasse muss dem öffentlichen Schlüssel des Signaturgebers bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6c450-124">The <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> class must be supplied the public key of the signer.</span></span> <span data-ttu-id="6c450-125">Für RSA benötigen Sie die Werte für den Modulo und den Exponenten, um den öffentlichen Schlüssel anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6c450-125">For RSA, you will need the values of the modulus and the exponent to specify the public key.</span></span> <span data-ttu-id="6c450-126">(Die Partei, die das Paar aus öffentlichem und privatem Schlüssel generiert hat, sollte diese Werte bereitstellen.) Erstellen Sie zuerst ein <xref:System.Security.Cryptography.RSA> -Objekt, das den öffentlichen Schlüssel enthält, mit dem die Signatur überprüft wird, und initialisieren Sie dann eine <xref:System.Security.Cryptography.RSAParameters> -Struktur mit den Modulo-und Exponent-Werten, die den öffentlichen Schlüssel angeben.</span><span class="sxs-lookup"><span data-stu-id="6c450-126">(The party that generated the public/private key pair should provide these values.) First create an <xref:System.Security.Cryptography.RSA> object to hold the public key that will verify the signature, and then initialize an <xref:System.Security.Cryptography.RSAParameters> structure to the modulus and exponent values that specify the public key.</span></span>

<span data-ttu-id="6c450-127">Der folgende Code zeigt die Erstellung einer <xref:System.Security.Cryptography.RSAParameters> -Struktur.</span><span class="sxs-lookup"><span data-stu-id="6c450-127">The following code shows the creation of an <xref:System.Security.Cryptography.RSAParameters> structure.</span></span> <span data-ttu-id="6c450-128">Die `Modulus` -Eigenschaft wird auf den Wert eines Bytearrays namens `modulusData` und die `Exponent` -Eigenschaft auf den Wert eines Bytearrays namens `exponentData`festgelegt.</span><span class="sxs-lookup"><span data-stu-id="6c450-128">The `Modulus` property is set to the value of a byte array called `modulusData` and the `Exponent` property is set to the value of a byte array called `exponentData`.</span></span>

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

<span data-ttu-id="6c450-129">Nachdem Sie das-Objekt erstellt haben <xref:System.Security.Cryptography.RSAParameters> , können Sie eine neue Instanz der <xref:System.Security.Cryptography.RSA> Implementierungs Klasse mit den Werten initialisieren, die in angegeben sind <xref:System.Security.Cryptography.RSAParameters> .</span><span class="sxs-lookup"><span data-stu-id="6c450-129">After you have created the <xref:System.Security.Cryptography.RSAParameters> object, you can initialize a new instance of the <xref:System.Security.Cryptography.RSA> implementation class to the values specified in <xref:System.Security.Cryptography.RSAParameters>.</span></span> <span data-ttu-id="6c450-130">Die- <xref:System.Security.Cryptography.RSA> Instanz wird wiederum an den Konstruktor von übergeben, <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> um den Schlüssel zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="6c450-130">The <xref:System.Security.Cryptography.RSA> instance is, in turn, passed to the constructor of an <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> to transfer the key.</span></span>

<span data-ttu-id="6c450-131">Dieser Prozess wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="6c450-131">The following example illustrates this process.</span></span> <span data-ttu-id="6c450-132">In diesem Beispiel sind `hashValue` und `signedHashValue` Bytearrays, die von einem Remoteanbieter bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6c450-132">In this example, `hashValue` and `signedHashValue` are arrays of bytes provided by a remote party.</span></span> <span data-ttu-id="6c450-133">Der Remoteanbieter hat `hashValue` mithilfe des SHA1-Algorithmus signiert und so die digitale Signatur `signedHashValue`erzeugt.</span><span class="sxs-lookup"><span data-stu-id="6c450-133">The remote party has signed the `hashValue` using the SHA1 algorithm, producing the digital signature `signedHashValue`.</span></span> <span data-ttu-id="6c450-134">Die <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter.VerifySignature%2A?displayProperty=nameWithType> -Methode überprüft, ob die digitale Signatur gültig ist und zum Signieren von verwendet wurde `hashValue` .</span><span class="sxs-lookup"><span data-stu-id="6c450-134">The <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter.VerifySignature%2A?displayProperty=nameWithType> method verifies that the digital signature is valid and was used to sign the `hashValue`.</span></span>

<span data-ttu-id="6c450-135">Aufgrund von Konnektivitätsproblemen mit SHA1 empfehlen wir SHA256 oder eine bessere.</span><span class="sxs-lookup"><span data-stu-id="6c450-135">Due to collision problems with SHA1, we recommend SHA256 or better.</span></span>  <span data-ttu-id="6c450-136">Wenn SHA1 jedoch zum Erstellen der Signatur verwendet wurde, müssen Sie SHA1 verwenden, um die Signatur zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="6c450-136">However, if SHA1 was used to create the signature, you have to use SHA1 to verify the signature.</span></span>

```vb
Dim rsa As RSA = RSA.Create()
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
RSA rsa = RSA.Create();
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

<span data-ttu-id="6c450-137">Dieses Codefragment zeigt "`The signature is valid`" an, wenn die Signatur gültig ist, und "`The signature is not valid`", wenn sie ungültig ist.</span><span class="sxs-lookup"><span data-stu-id="6c450-137">This code fragment will display "`The signature is valid`" if the signature is valid and "`The signature is not valid`" if it is not.</span></span>

## <a name="see-also"></a><span data-ttu-id="6c450-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6c450-138">See also</span></span>

- [<span data-ttu-id="6c450-139">Kryptografische Dienste</span><span class="sxs-lookup"><span data-stu-id="6c450-139">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="6c450-140">Kryptografiemodell</span><span class="sxs-lookup"><span data-stu-id="6c450-140">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="6c450-141">Plattformübergreifende Kryptografie</span><span class="sxs-lookup"><span data-stu-id="6c450-141">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="6c450-142">ASP.net Core Datenschutz</span><span class="sxs-lookup"><span data-stu-id="6c450-142">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
