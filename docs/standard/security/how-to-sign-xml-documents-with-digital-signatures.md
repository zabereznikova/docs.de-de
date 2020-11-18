---
title: 'Vorgehensweise: Signieren von XML-Dokumenten mit digitalen Signaturen'
description: Erfahren Sie, wie Sie XML-Dokumente mit digitalen Signaturen signieren. Verwenden Sie Klassen im System.Security.Cryptography.Xml-Namespace in .net.
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- signatures, XML signing
- System.Security.Cryptography.SignedXml class
- digital signatures, XML signing
- System.Security.Cryptography.RSA class
- XML digital signatures
- XML signing
- signing XML
ms.assetid: 99692ac1-d8c9-42d7-b1bf-2737b01037e4
ms.openlocfilehash: 3265417d806104f9c4de96cb98de2330d62d1e48
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94820162"
---
# <a name="how-to-sign-xml-documents-with-digital-signatures"></a><span data-ttu-id="8195f-104">Vorgehensweise: Signieren von XML-Dokumenten mit digitalen Signaturen</span><span class="sxs-lookup"><span data-stu-id="8195f-104">How to: Sign XML Documents with Digital Signatures</span></span>

<span data-ttu-id="8195f-105">Um ein XML-Dokument teilweise oder vollständig mit einer digitalen Signatur zu versehen, können Sie die Klassen im <xref:System.Security.Cryptography.Xml>-Namespace verwenden.</span><span class="sxs-lookup"><span data-stu-id="8195f-105">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to sign an XML document or part of an XML document with a digital signature.</span></span>  <span data-ttu-id="8195f-106">Über digitale XML-Signaturen (XMLDSIG) können Sie sich vergewissern, dass Daten nicht mehr geändert wurden, nachdem sie signiert wurden.</span><span class="sxs-lookup"><span data-stu-id="8195f-106">XML digital signatures (XMLDSIG) allow you to verify that data was not altered after it was signed.</span></span>  <span data-ttu-id="8195f-107">Weitere Informationen zum XMLDSIG-Standard finden Sie unter World Wide Web Consortium (W3C) Empfehlungs [Syntax für XML-Signaturen und Verarbeitung](https://www.w3.org/TR/xmldsig-core/).</span><span class="sxs-lookup"><span data-stu-id="8195f-107">For more information about the XMLDSIG standard, see the World Wide Web Consortium (W3C) recommendation [XML Signature Syntax and Processing](https://www.w3.org/TR/xmldsig-core/).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8195f-108">Der Code in diesem Artikel gilt für Windows.</span><span class="sxs-lookup"><span data-stu-id="8195f-108">The code in this article applies to Windows.</span></span>

<span data-ttu-id="8195f-109">Das Codebeispiel in dieser Prozedur veranschaulicht, wie ein gesamtes XML-Dokument digital signiert und die Signatur an das Dokument in einem <>-Element angefügt wird `Signature` .</span><span class="sxs-lookup"><span data-stu-id="8195f-109">The code example in this procedure demonstrates how to digitally sign an entire XML document and attach the signature to the document in a <`Signature`> element.</span></span>  <span data-ttu-id="8195f-110">Im Beispiel wird ein RSA-Signaturschlüssel erstellt, wird der Schlüssel einem sicheren Schlüsselcontainer hinzugefügt und wird der Schlüssel dann verwendet, um ein XML-Dokument digital zu signieren.</span><span class="sxs-lookup"><span data-stu-id="8195f-110">The example creates an RSA signing key, adds the key to a secure key container, and then uses the key to digitally sign an XML document.</span></span>  <span data-ttu-id="8195f-111">Der Schlüssel kann danach abgerufen werden, um die digitale Signatur des XML-Dokuments zu überprüfen oder ein anderes XML-Dokument zu signieren.</span><span class="sxs-lookup"><span data-stu-id="8195f-111">The key can then be retrieved to verify the XML digital signature, or can be used to sign another XML document.</span></span>  
  
<span data-ttu-id="8195f-112">Informationen zum Überprüfen einer digitalen XML-Signatur, die mit diesem Verfahren erstellt wurde, finden Sie unter Gewusst [wie: Überprüfen der digitalen Signaturen von XML-Dokumenten](how-to-verify-the-digital-signatures-of-xml-documents.md).</span><span class="sxs-lookup"><span data-stu-id="8195f-112">For information about how to verify an XML digital signature that was created using this procedure, see [How to: Verify the Digital Signatures of XML Documents](how-to-verify-the-digital-signatures-of-xml-documents.md).</span></span>  
  
### <a name="to-digitally-sign-an-xml-document"></a><span data-ttu-id="8195f-113">So signieren Sie ein XML-Dokument digital</span><span class="sxs-lookup"><span data-stu-id="8195f-113">To digitally sign an XML document</span></span>  
  
1. <span data-ttu-id="8195f-114">Erstellen Sie ein <xref:System.Security.Cryptography.CspParameters>-Objekt, und geben Sie den Namen des Schlüsselcontainers an.</span><span class="sxs-lookup"><span data-stu-id="8195f-114">Create a <xref:System.Security.Cryptography.CspParameters> object and specify the name of the key container.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#2)]
     [!code-vb[HowToSignXMLDocumentRSA#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#2)]  
  
2. <span data-ttu-id="8195f-115">Generieren Sie mit der <xref:System.Security.Cryptography.RSACryptoServiceProvider>-Klasse einen asymmetrischen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="8195f-115">Generate an asymmetric key using the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class.</span></span>  <span data-ttu-id="8195f-116">Der Schlüssel wird automatisch im Schlüsselcontainer gespeichert, wenn Sie das <xref:System.Security.Cryptography.CspParameters>-Objekt an den Konstruktor der <xref:System.Security.Cryptography.RSACryptoServiceProvider>-Klasse übergeben.</span><span class="sxs-lookup"><span data-stu-id="8195f-116">The key is automatically saved to the key container when you pass the <xref:System.Security.Cryptography.CspParameters> object to the constructor of the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class.</span></span>  <span data-ttu-id="8195f-117">Dieser Schlüssel wird zum Signieren des XML-Dokuments verwendet.</span><span class="sxs-lookup"><span data-stu-id="8195f-117">This key will be used to sign the XML document.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#3)]
     [!code-vb[HowToSignXMLDocumentRSA#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#3)]  
  
3. <span data-ttu-id="8195f-118">Erstellen Sie ein <xref:System.Xml.XmlDocument>-Objekt, indem Sie eine XML-Datei von einem Datenträger laden.</span><span class="sxs-lookup"><span data-stu-id="8195f-118">Create an <xref:System.Xml.XmlDocument> object by loading an XML file from disk.</span></span>  <span data-ttu-id="8195f-119">Das <xref:System.Xml.XmlDocument>-Objekt enthält das zu verschlüsselnde XML-Element.</span><span class="sxs-lookup"><span data-stu-id="8195f-119">The <xref:System.Xml.XmlDocument> object contains the XML element to encrypt.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#4)]
     [!code-vb[HowToSignXMLDocumentRSA#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#4)]  
  
4. <span data-ttu-id="8195f-120">Erstellen Sie ein neues <xref:System.Security.Cryptography.Xml.SignedXml>-Objekt, und übergeben Sie diesem das <xref:System.Xml.XmlDocument>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="8195f-120">Create a new <xref:System.Security.Cryptography.Xml.SignedXml> object and pass the <xref:System.Xml.XmlDocument> object to it.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#5)]
     [!code-vb[HowToSignXMLDocumentRSA#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#5)]  
  
5. <span data-ttu-id="8195f-121">Fügen Sie den RSA-Signaturschlüssel dem <xref:System.Security.Cryptography.Xml.SignedXml>-Objekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="8195f-121">Add the signing RSA key to the <xref:System.Security.Cryptography.Xml.SignedXml> object.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#6)]
     [!code-vb[HowToSignXMLDocumentRSA#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#6)]  
  
6. <span data-ttu-id="8195f-122">Erstellen Sie ein <xref:System.Security.Cryptography.Xml.Reference>-Objekt, das beschreibt, was signiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="8195f-122">Create a <xref:System.Security.Cryptography.Xml.Reference> object that describes what to sign.</span></span>  <span data-ttu-id="8195f-123">Um das gesamte Dokument zu signieren, legen Sie die <xref:System.Security.Cryptography.Xml.Reference.Uri%2A>-Eigenschaft auf `""` fest.</span><span class="sxs-lookup"><span data-stu-id="8195f-123">To sign the entire document, set the <xref:System.Security.Cryptography.Xml.Reference.Uri%2A> property to `""`.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#7)]
     [!code-vb[HowToSignXMLDocumentRSA#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#7)]  
  
7. <span data-ttu-id="8195f-124">Fügen Sie dem <xref:System.Security.Cryptography.Xml.Reference>-Objekt ein <xref:System.Security.Cryptography.Xml.XmlDsigEnvelopedSignatureTransform>-Objekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="8195f-124">Add an <xref:System.Security.Cryptography.Xml.XmlDsigEnvelopedSignatureTransform> object to the <xref:System.Security.Cryptography.Xml.Reference> object.</span></span>  <span data-ttu-id="8195f-125">Eine Transformation ermöglicht es dem Prüfer, die XML-Daten auf genau die Weise darzustellen, die der Signaturgeber verwendet hat.</span><span class="sxs-lookup"><span data-stu-id="8195f-125">A transformation allows the verifier to represent the XML data in the identical manner that the signer used.</span></span>  <span data-ttu-id="8195f-126">XML-Daten können auf unterschiedliche Weise dargestellt werden, weshalb dieser Schritt für die Überprüfung unverzichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="8195f-126">XML data can be represented in different ways, so this step is vital to verification.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#8)]
     [!code-vb[HowToSignXMLDocumentRSA#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#8)]  
  
8. <span data-ttu-id="8195f-127">Fügen Sie dem <xref:System.Security.Cryptography.Xml.SignedXml>-Objekt das <xref:System.Security.Cryptography.Xml.Reference>-Objekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="8195f-127">Add the <xref:System.Security.Cryptography.Xml.Reference> object to the <xref:System.Security.Cryptography.Xml.SignedXml> object.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#9)]
     [!code-vb[HowToSignXMLDocumentRSA#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#9)]  
  
9. <span data-ttu-id="8195f-128">Berechnen Sie die Signatur, indem Sie die <xref:System.Security.Cryptography.Xml.SignedXml.ComputeSignature%2A>-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="8195f-128">Compute the signature by calling the <xref:System.Security.Cryptography.Xml.SignedXml.ComputeSignature%2A> method.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#10)]
     [!code-vb[HowToSignXMLDocumentRSA#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#10)]  
  
10. <span data-ttu-id="8195f-129">Rufen Sie die XML-Darstellung der Signatur (ein <`Signature`>-Element) ab, und speichern Sie Sie in einem neuen- <xref:System.Xml.XmlElement> Objekt.</span><span class="sxs-lookup"><span data-stu-id="8195f-129">Retrieve the XML representation of the signature (a <`Signature`> element) and save it to a new <xref:System.Xml.XmlElement> object.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#11)]
     [!code-vb[HowToSignXMLDocumentRSA#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#11)]  
  
11. <span data-ttu-id="8195f-130">Fügen Sie das Element an das <xref:System.Xml.XmlDocument>-Objekt an.</span><span class="sxs-lookup"><span data-stu-id="8195f-130">Append the element to the <xref:System.Xml.XmlDocument> object.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#12)]
     [!code-vb[HowToSignXMLDocumentRSA#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#12)]  
  
12. <span data-ttu-id="8195f-131">Speichern Sie das Dokument.</span><span class="sxs-lookup"><span data-stu-id="8195f-131">Save the document.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#13](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#13)]
     [!code-vb[HowToSignXMLDocumentRSA#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#13)]  
  
## <a name="example"></a><span data-ttu-id="8195f-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8195f-132">Example</span></span>  
 <span data-ttu-id="8195f-133">Für dieses Beispiel wird angenommen, dass eine Datei namens `test.xml` im selben Verzeichnis wie das kompilierte Programm vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="8195f-133">This example assumes that a file named `test.xml` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="8195f-134">Sie können den folgenden XML-Code in eine Datei namens `test.xml` einfügen und mit diesem Beispiel verwenden.</span><span class="sxs-lookup"><span data-stu-id="8195f-134">You can place the following XML into a file called `test.xml` and use it with this example.</span></span>  
  
```xml  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
```  
  
 [!code-csharp[HowToSignXMLDocumentRSA#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#1)]
 [!code-vb[HowToSignXMLDocumentRSA#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8195f-135">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="8195f-135">Compiling the Code</span></span>  
  
- <span data-ttu-id="8195f-136">Fügen Sie in einem Projekt, das .NET Framework als Ziel hat, einen Verweis auf ein `System.Security.dll` .</span><span class="sxs-lookup"><span data-stu-id="8195f-136">In a project that targets .NET Framework, include a reference to `System.Security.dll`.</span></span>

- <span data-ttu-id="8195f-137">Installieren Sie in einem Projekt, das .net Core oder .net 5 als Ziel hat, das nuget-Paket [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span><span class="sxs-lookup"><span data-stu-id="8195f-137">In a project that targets .NET Core or .NET 5, install NuGet package [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span></span>
  
- <span data-ttu-id="8195f-138">Fügen Sie die folgenden Namespaces hinzu: <xref:System.Xml>, <xref:System.Security.Cryptography> und <xref:System.Security.Cryptography.Xml>.</span><span class="sxs-lookup"><span data-stu-id="8195f-138">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="8195f-139">.NET-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="8195f-139">.NET Security</span></span>

<span data-ttu-id="8195f-140">Sie sollten den privaten Schlüssel eines asymmetrischen Schlüsselpaars niemals in Klartext speichern oder übertragen.</span><span class="sxs-lookup"><span data-stu-id="8195f-140">Never store or transfer the private key of an asymmetric key pair in plaintext.</span></span>  <span data-ttu-id="8195f-141">Weitere Informationen zu symmetrischen und asymmetrischen Kryptografieschlüsseln finden Sie unter [Erstellen von Schlüsseln für die Verschlüsselung und Entschlüsselung](generating-keys-for-encryption-and-decryption.md).</span><span class="sxs-lookup"><span data-stu-id="8195f-141">For more information about symmetric and asymmetric cryptographic keys, see [Generating Keys for Encryption and Decryption](generating-keys-for-encryption-and-decryption.md).</span></span>  
  
<span data-ttu-id="8195f-142">Sie sollten einen privaten Schlüssel niemals direkt in Ihren Quellcode einbetten.</span><span class="sxs-lookup"><span data-stu-id="8195f-142">Never embed a private key directly into your source code.</span></span>  <span data-ttu-id="8195f-143">Eingebettete Schlüssel können problemlos aus einer Assembly gelesen werden, indem Sie die [Ildasm.exe (IL-Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md) verwenden, oder Sie öffnen die Assembly in einem Text-Editor wie Notepad.</span><span class="sxs-lookup"><span data-stu-id="8195f-143">Embedded keys can be easily read from an assembly using the [Ildasm.exe (IL Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md) or by opening the assembly in a text editor such as Notepad.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8195f-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8195f-144">See also</span></span>

- [<span data-ttu-id="8195f-145">Kryptografiemodell</span><span class="sxs-lookup"><span data-stu-id="8195f-145">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="8195f-146">Kryptografische Dienste</span><span class="sxs-lookup"><span data-stu-id="8195f-146">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="8195f-147">Plattformübergreifende Kryptografie</span><span class="sxs-lookup"><span data-stu-id="8195f-147">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="8195f-148">Gewusst wie: Überprüfen der digitalen Signaturen von XML-Dokumenten</span><span class="sxs-lookup"><span data-stu-id="8195f-148">How to: Verify the Digital Signatures of XML Documents</span></span>](how-to-verify-the-digital-signatures-of-xml-documents.md)
- [<span data-ttu-id="8195f-149">ASP.net Core Datenschutz</span><span class="sxs-lookup"><span data-stu-id="8195f-149">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
