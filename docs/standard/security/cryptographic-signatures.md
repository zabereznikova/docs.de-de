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
ms.openlocfilehash: 3f9d83a0edb6dc2261931e422b0ae4c735d2e0d1
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44086095"
---
# <a name="cryptographic-signatures"></a><span data-ttu-id="e0cdf-102">Kryptografische Signaturen</span><span class="sxs-lookup"><span data-stu-id="e0cdf-102">Cryptographic Signatures</span></span>
<a name="top"></a> <span data-ttu-id="e0cdf-103">Kryptografische digitale Signaturen verwenden Algorithmen für öffentliche Schlüssel, um die Datenintegrität sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="e0cdf-103">Cryptographic digital signatures use public key algorithms to provide data integrity.</span></span> <span data-ttu-id="e0cdf-104">Wenn Sie Daten mit einer digitalen Signatur signieren, kann eine andere Person die Signatur überprüfen und kann nachweisen, dass die Daten von Ihnen stammen und nicht geändert wurde, nachdem Sie sie signiert haben.</span><span class="sxs-lookup"><span data-stu-id="e0cdf-104">When you sign data with a digital signature, someone else can verify the signature, and can prove that the data originated from you and was not altered after you signed it.</span></span> <span data-ttu-id="e0cdf-105">Weitere Informationen zu digitalen Signaturen finden Sie unter [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md).</span><span class="sxs-lookup"><span data-stu-id="e0cdf-105">For more information about digital signatures, see [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md).</span></span>  
  
 <span data-ttu-id="e0cdf-106">In diesem Thema wird erläutert, wie Sie zum Generieren und Überprüfen von digitalen Signaturen Klassen im <xref:System.Security.Cryptography?displayProperty=nameWithType>-Namespace verwenden.</span><span class="sxs-lookup"><span data-stu-id="e0cdf-106">This topic explains how to generate and verify digital signatures using classes in the <xref:System.Security.Cryptography?displayProperty=nameWithType> namespace.</span></span>  
  
-   [<span data-ttu-id="e0cdf-107">Generieren von Signaturen</span><span class="sxs-lookup"><span data-stu-id="e0cdf-107">Generating Signatures</span></span>](#generate)  
  
-   [<span data-ttu-id="e0cdf-108">Verifizieren von Signaturen</span><span class="sxs-lookup"><span data-stu-id="e0cdf-108">Verifying Signatures</span></span>](#verify)  
  
<a name="generate"></a>   
## <a name="generating-signatures"></a><span data-ttu-id="e0cdf-109">Generieren von Signaturen</span><span class="sxs-lookup"><span data-stu-id="e0cdf-109">Generating Signatures</span></span>  
 <span data-ttu-id="e0cdf-110">Digitale Signaturen werden in der Regel auf Hashwerte angewendet, die größere Datenmengen darstellen.</span><span class="sxs-lookup"><span data-stu-id="e0cdf-110">Digital signatures are usually applied to hash values that represent larger data.</span></span> <span data-ttu-id="e0cdf-111">Das folgende Beispiel wendet eine digitale Signatur auf einen Hashwert an.</span><span class="sxs-lookup"><span data-stu-id="e0cdf-111">The following example applies a digital signature to a hash value.</span></span> <span data-ttu-id="e0cdf-112">Zuerst wird eine neue Instanz der <xref:System.Security.Cryptography.RSACryptoServiceProvider> -Klasse erstellt, um ein öffentliches/privates Schlüsselpaar zu generieren.</span><span class="sxs-lookup"><span data-stu-id="e0cdf-112">First, a new instance of the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class is created to generate a public/private key pair.</span></span> <span data-ttu-id="e0cdf-113">Als Nächstes wird <xref:System.Security.Cryptography.RSACryptoServiceProvider> ein eine neue Instanz der <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> -Klasse übergeben.</span><span class="sxs-lookup"><span data-stu-id="e0cdf-113">Next, the <xref:System.Security.Cryptography.RSACryptoServiceProvider> is passed to a new instance of the <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> class.</span></span> <span data-ttu-id="e0cdf-114">Dadurch wird der private Schlüssel an die <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter>-Klasse übertragen, die letztlich die digitale Signatur vornimmt.</span><span class="sxs-lookup"><span data-stu-id="e0cdf-114">This transfers the private key to the <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter>, which actually performs the digital signing.</span></span> <span data-ttu-id="e0cdf-115">Bevor Sie den Hashcode signieren können, müssen Sie einen zu verwendenden Hashalgorithmus angeben.</span><span class="sxs-lookup"><span data-stu-id="e0cdf-115">Before you can sign the hash code, you must specify a hash algorithm to use.</span></span> <span data-ttu-id="e0cdf-116">Dieses Beispiel verwendet den SHA1-Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="e0cdf-116">This example uses the SHA1 algorithm.</span></span> <span data-ttu-id="e0cdf-117">Schließlich wird die <xref:System.Security.Cryptography.AsymmetricSignatureFormatter.CreateSignature%2A> -Methode aufgerufen, um das Signieren vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="e0cdf-117">Finally, the <xref:System.Security.Cryptography.AsymmetricSignatureFormatter.CreateSignature%2A> method is called to perform the signing.</span></span>  
  
```vb  
Imports System  
Imports System.Security.Cryptography  
  
Module Module1  
    Sub Main()  
        'The hash value to sign.  
        Dim HashValue As Byte() = {59, 4, 248, 102, 77, 97, 142, 201, 210, 12, 224, 93, 25, 41, 100, 197, 213, 134, 130, 135}  
  
        'The value to hold the signed value.  
        Dim SignedHashValue() As Byte  
  
        'Generate a public/private key pair.  
        Dim RSA As New RSACryptoServiceProvider()  
  
        'Create an RSAPKCS1SignatureFormatter object and pass it   
        'the RSACryptoServiceProvider to transfer the private key.  
        Dim RSAFormatter As New RSAPKCS1SignatureFormatter(RSA)  
  
        'Set the hash algorithm to SHA1.  
        RSAFormatter.SetHashAlgorithm("SHA1")  
  
        'Create a signature for HashValue and assign it to   
        'SignedHashValue.  
        SignedHashValue = RSAFormatter.CreateSignature(HashValue)  
    End Sub  
End Module  
  
using System;  
using System.Security.Cryptography;  
```  
  
```csharp  
class Class1  
{  
   static void Main()  
   {  
      //The hash value to sign.  
      byte[] HashValue = {59,4,248,102,77,97,142,201,210,12,224,93,25,41,100,197,213,134,130,135};  
  
      //The value to hold the signed value.  
      byte[] SignedHashValue;  
  
      //Generate a public/private key pair.  
      RSACryptoServiceProvider RSA = new RSACryptoServiceProvider();  
  
      //Create an RSAPKCS1SignatureFormatter object and pass it the   
      //RSACryptoServiceProvider to transfer the private key.  
      RSAPKCS1SignatureFormatter RSAFormatter = new RSAPKCS1SignatureFormatter(RSA);  
  
      //Set the hash algorithm to SHA1.  
      RSAFormatter.SetHashAlgorithm("SHA1");  
  
      //Create a signature for HashValue and assign it to   
      //SignedHashValue.  
      SignedHashValue = RSAFormatter.CreateSignature(HashValue);  
   }  
}  
```  
  
### <a name="signing-xml-files"></a><span data-ttu-id="e0cdf-118">Signieren von XML-Dateien</span><span class="sxs-lookup"><span data-stu-id="e0cdf-118">Signing XML Files</span></span>  
 <span data-ttu-id="e0cdf-119">.NET Framework stellt den <xref:System.Security.Cryptography.Xml> -Namespace bereit, der es Ihnen ermöglicht, XML-Dateien zu signieren.</span><span class="sxs-lookup"><span data-stu-id="e0cdf-119">The .NET Framework provides the <xref:System.Security.Cryptography.Xml> namespace, which enables you sign XML.</span></span> <span data-ttu-id="e0cdf-120">Das Signieren von XML-Dateien ist wichtig, wenn Sie überprüfen möchten, ob der XML-Code aus einer bestimmten Quelle stammt.</span><span class="sxs-lookup"><span data-stu-id="e0cdf-120">Signing XML is important when you want to verify that the XML originates from a certain source.</span></span> <span data-ttu-id="e0cdf-121">Wenn Sie z. B. einen Aktienkursdienst verwenden, der XML verwendet, können Sie die Quelle der XML-Datei überprüfen, wenn sie signiert ist.</span><span class="sxs-lookup"><span data-stu-id="e0cdf-121">For example, if you are using a stock quote service that uses XML, you can verify the source of the XML if it is signed.</span></span>  
  
 <span data-ttu-id="e0cdf-122">Die Klassen in diesem Namespace entsprechen den [XML Signature Syntax and Processing-Empfehlungen](https://www.w3.org/TR/xmldsig-core/) des World Wide Web Consortium.</span><span class="sxs-lookup"><span data-stu-id="e0cdf-122">The classes in this namespace follow the [XML-Signature Syntax and Processing recommendation](https://www.w3.org/TR/xmldsig-core/) from the World Wide Web Consortium.</span></span>  
  
 [<span data-ttu-id="e0cdf-123">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="e0cdf-123">Back to top</span></span>](#top)  
  
<a name="verify"></a>   
## <a name="verifying-signatures"></a><span data-ttu-id="e0cdf-124">Verifizieren von Signaturen</span><span class="sxs-lookup"><span data-stu-id="e0cdf-124">Verifying Signatures</span></span>  
 <span data-ttu-id="e0cdf-125">Um sicherzustellen, dass Daten von einem bestimmten Anbieter signiert wurden, benötigen Sie die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="e0cdf-125">To verify that data was signed by a particular party, you must have the following information:</span></span>  
  
-   <span data-ttu-id="e0cdf-126">Der öffentliche Schlüssel des Anbieters, der die Daten signiert hat.</span><span class="sxs-lookup"><span data-stu-id="e0cdf-126">The public key of the party that signed the data.</span></span>  
  
-   <span data-ttu-id="e0cdf-127">Die digitale XML-Signatur.</span><span class="sxs-lookup"><span data-stu-id="e0cdf-127">The digital signature.</span></span>  
  
-   <span data-ttu-id="e0cdf-128">Die Daten, die signiert wurden.</span><span class="sxs-lookup"><span data-stu-id="e0cdf-128">The data that was signed.</span></span>  
  
-   <span data-ttu-id="e0cdf-129">Der vom Signaturgeber verwendete Hashalgorithmus.</span><span class="sxs-lookup"><span data-stu-id="e0cdf-129">The hash algorithm used by the signer.</span></span>  
  
 <span data-ttu-id="e0cdf-130">Zum Überprüfen einer Signatur, die von der <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> -Klasse signiert wurde, verwenden Sie die <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> -Klasse.</span><span class="sxs-lookup"><span data-stu-id="e0cdf-130">To verify a signature signed by the <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> class, use the <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> class.</span></span> <span data-ttu-id="e0cdf-131">Die <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> -Klasse muss dem öffentlichen Schlüssel des Signaturgebers bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="e0cdf-131">The <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> class must be supplied the public key of the signer.</span></span> <span data-ttu-id="e0cdf-132">Sie benötigen die Werte für den Modulo und den Exponenten, um den öffentlichen Schlüssel anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e0cdf-132">You will need the values of the modulus and the exponent to specify the public key.</span></span> <span data-ttu-id="e0cdf-133">(Der Anbieter, der das öffentliche/private Schlüsselpaar generiert hat, sollte diese Werte bereitstellen.) Erstellen Sie zunächst eine <xref:System.Security.Cryptography.RSACryptoServiceProvider> Objekt, das den öffentlichen Schlüssel enthält, die die Signatur überprüft wird, und initialisieren Sie ein <xref:System.Security.Cryptography.RSAParameters> Struktur mit den Modulo- und Exponentenwerte-Werten, die den öffentlichen Schlüssel angeben.</span><span class="sxs-lookup"><span data-stu-id="e0cdf-133">(The party that generated the public/private key pair should provide these values.) First create an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object to hold the public key that will verify the signature, and then initialize an <xref:System.Security.Cryptography.RSAParameters> structure to the modulus and exponent values that specify the public key.</span></span>  
  
 <span data-ttu-id="e0cdf-134">Der folgende Code zeigt die Erstellung einer <xref:System.Security.Cryptography.RSAParameters> -Struktur.</span><span class="sxs-lookup"><span data-stu-id="e0cdf-134">The following code shows the creation of an <xref:System.Security.Cryptography.RSAParameters> structure.</span></span> <span data-ttu-id="e0cdf-135">Die `Modulus` -Eigenschaft wird auf den Wert eines Bytearrays namens `ModulusData` und die `Exponent` -Eigenschaft auf den Wert eines Bytearrays namens `ExponentData`festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e0cdf-135">The `Modulus` property is set to the value of a byte array called `ModulusData` and the `Exponent` property is set to the value of a byte array called `ExponentData`.</span></span>  
  
```vb  
Dim RSAKeyInfo As RSAParameters  
RSAKeyInfo.Modulus = ModulusData  
RSAKeyInfo.Exponent = ExponentData  
```  
  
```csharp  
RSAParameters RSAKeyInfo;  
RSAKeyInfo.Modulus = ModulusData;  
RSAKeyInfo.Exponent = ExponentData;  
```  
  
 <span data-ttu-id="e0cdf-136">Nach der Erstellung des <xref:System.Security.Cryptography.RSAParameters> -Objekts können Sie eine neue Instanz der <xref:System.Security.Cryptography.RSACryptoServiceProvider> -Klasse mit den Wert initialisieren, die in <xref:System.Security.Cryptography.RSAParameters>angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="e0cdf-136">After you have created the <xref:System.Security.Cryptography.RSAParameters> object, you can initialize a new instance of the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class to the values specified in <xref:System.Security.Cryptography.RSAParameters>.</span></span> <span data-ttu-id="e0cdf-137"><xref:System.Security.Cryptography.RSACryptoServiceProvider> wird dann an den Konstruktor von <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> übergeben, um den Schlüssel zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="e0cdf-137">The <xref:System.Security.Cryptography.RSACryptoServiceProvider> is, in turn, passed to the constructor of an <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> to transfer the key.</span></span>  
  
 <span data-ttu-id="e0cdf-138">Dieser Prozess wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="e0cdf-138">The following example illustrates this process.</span></span> <span data-ttu-id="e0cdf-139">In diesem Beispiel sind `HashValue` und `SignedHashValue` Bytearrays, die von einem Remoteanbieter bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="e0cdf-139">In this example, `HashValue` and `SignedHashValue` are arrays of bytes provided by a remote party.</span></span> <span data-ttu-id="e0cdf-140">Der Remoteanbieter hat `HashValue` mithilfe des SHA1-Algorithmus signiert und so die digitale Signatur `SignedHashValue`erzeugt.</span><span class="sxs-lookup"><span data-stu-id="e0cdf-140">The remote party has signed the `HashValue` using the SHA1 algorithm, producing the digital signature `SignedHashValue`.</span></span> <span data-ttu-id="e0cdf-141">Die</span><span class="sxs-lookup"><span data-stu-id="e0cdf-141">The</span></span>  
  
 <span data-ttu-id="e0cdf-142"><xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter.VerifySignature%2A?displayProperty=nameWithType>-Methode überprüft, ob die digitale Signatur gültig ist und zum Signieren von `HashValue` verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="e0cdf-142"><xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter.VerifySignature%2A?displayProperty=nameWithType> method verifies that the digital signature is valid and was used to sign the `HashValue`.</span></span>  
  
```vb  
Dim RSA As New RSACryptoServiceProvider()  
RSA.ImportParameters(RSAKeyInfo)  
Dim RSADeformatter As New RSAPKCS1SignatureDeformatter(RSA)  
RSADeformatter.SetHashAlgorithm("SHA1")  
If RSADeformatter.VerifySignature(HashValue, SignedHashValue) Then  
   Console.WriteLine("The signature is valid.")  
Else  
   Console.WriteLine("The signture is not valid.")  
End If  
```  
  
```csharp  
RSACryptoServiceProvider RSA = new RSACryptoServiceProvider();  
RSA.ImportParameters(RSAKeyInfo);  
RSAPKCS1SignatureDeformatter RSADeformatter = new RSAPKCS1SignatureDeformatter(RSA);  
RSADeformatter.SetHashAlgorithm("SHA1");  
if(RSADeformatter.VerifySignature(HashValue, SignedHashValue))  
{  
   Console.WriteLine("The signature is valid.");  
}  
else  
{  
   Console.WriteLine("The signature is not valid.");  
}  
```  
  
 <span data-ttu-id="e0cdf-143">Dieses Codefragment zeigt "`The signature is valid`" an, wenn die Signatur gültig ist, und "`The signature is not valid`", wenn sie ungültig ist.</span><span class="sxs-lookup"><span data-stu-id="e0cdf-143">This code fragment will display "`The signature is valid`" if the signature is valid and "`The signature is not valid`" if it is not.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0cdf-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e0cdf-144">See also</span></span>

- [<span data-ttu-id="e0cdf-145">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="e0cdf-145">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
