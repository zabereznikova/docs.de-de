---
title: 'Gewusst wie: Überprüfen der digitalen Signaturen von XML-Dokumenten'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- System.Security.Cryptography.SignedXml class
- signatures, cryptographic
- System.Security.Cryptography.RSACryptoServiceProvider class
- verifying signatures
- checking signatures
- XML digital signatures
- digital signatures, verifying
ms.assetid: a4d5ceb1-b9f5-47e8-9e4a-a2b39110002f
ms.openlocfilehash: 5d562c23d3b0fd7eda5dc273932ada77709641a1
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706005"
---
# <a name="how-to-verify-the-digital-signatures-of-xml-documents"></a><span data-ttu-id="d7bc9-102">Gewusst wie: Überprüfen der digitalen Signaturen von XML-Dokumenten</span><span class="sxs-lookup"><span data-stu-id="d7bc9-102">How to: Verify the Digital Signatures of XML Documents</span></span>
<span data-ttu-id="d7bc9-103">Um XML-Daten zu überprüfen, die mit einer digitalen Signatur signiert sind, können Sie die Klassen im <xref:System.Security.Cryptography.Xml>-Namespace verwenden.</span><span class="sxs-lookup"><span data-stu-id="d7bc9-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to verify XML data signed with a digital signature.</span></span> <span data-ttu-id="d7bc9-104">Über digitale XML-Signaturen (XMLDSIG) können Sie sich vergewissern, dass Daten nicht mehr geändert wurden, nachdem sie signiert wurden.</span><span class="sxs-lookup"><span data-stu-id="d7bc9-104">XML digital signatures (XMLDSIG) allow you to verify that data was not altered after it was signed.</span></span> <span data-ttu-id="d7bc9-105">Weitere Informationen zum XMLDSIG-Standard finden Sie in der World Wide Web Consortium-Spezifikation (W3C) unter <https://www.w3.org/TR/xmldsig-core/>.</span><span class="sxs-lookup"><span data-stu-id="d7bc9-105">For more information about the XMLDSIG standard, see the World Wide Web Consortium (W3C) specification at <https://www.w3.org/TR/xmldsig-core/>.</span></span>
  
 <span data-ttu-id="d7bc9-106">Das Codebeispiel in dieser Prozedur veranschaulicht, wie eine digitale XML-Signatur, die in einem <`Signature`>-Element enthalten ist, überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="d7bc9-106">The code example in this procedure demonstrates how to verify an XML digital signature contained in a <`Signature`> element.</span></span>  <span data-ttu-id="d7bc9-107">Im Beispiel wird ein öffentlicher RSA-Schlüssel aus einem Schlüsselcontainer abgerufen und anschließend zum Überprüfen der Signatur verwendet.</span><span class="sxs-lookup"><span data-stu-id="d7bc9-107">The example retrieves an RSA public key from a key container and then uses the key to verify the signature.</span></span>  
  
 <span data-ttu-id="d7bc9-108">Informationen dazu, wie eine digitale Signatur erstellt wird, die mithilfe dieser Technik überprüft werden kann, finden Sie unter Gewusst [wie: Signieren von XML-Dokumenten mit digitalen Signaturen](../../../docs/standard/security/how-to-sign-xml-documents-with-digital-signatures.md).</span><span class="sxs-lookup"><span data-stu-id="d7bc9-108">For information about how create a digital signature that can be verified using this technique, see [How to: Sign XML Documents with Digital Signatures](../../../docs/standard/security/how-to-sign-xml-documents-with-digital-signatures.md).</span></span>  
  
### <a name="to-verify-the-digital-signature-of-an-xml-document"></a><span data-ttu-id="d7bc9-109">So überprüfen Sie die digitale Signatur eines XML-Dokuments</span><span class="sxs-lookup"><span data-stu-id="d7bc9-109">To verify the digital signature of an XML document</span></span>  
  
1. <span data-ttu-id="d7bc9-110">Um das Dokument zu überprüfen, müssen Sie denselben asymmetrischen Schlüssel wie für die Signierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="d7bc9-110">To verify the document, you must use the same asymmetric key that was used for signing.</span></span>  <span data-ttu-id="d7bc9-111">Erstellen Sie ein <xref:System.Security.Cryptography.CspParameters>-Objekt, und geben Sie den Namen des Schlüsselcontainers an, der zum Signieren verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="d7bc9-111">Create a <xref:System.Security.Cryptography.CspParameters> object and specify the name of the key container that was used for signing.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#2)]
     [!code-vb[HowToVerifyXMLDocumentRSA#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#2)]  
  
2. <span data-ttu-id="d7bc9-112">Rufen Sie den öffentlichen Schlüssel mit der <xref:System.Security.Cryptography.RSACryptoServiceProvider>-Klasse ab.</span><span class="sxs-lookup"><span data-stu-id="d7bc9-112">Retrieve the public key using the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class.</span></span>  <span data-ttu-id="d7bc9-113">Der Schlüssel wird automatisch nach Name aus dem Schlüsselcontainer geladen, wenn Sie das <xref:System.Security.Cryptography.CspParameters>-Objekt an den Konstruktor der <xref:System.Security.Cryptography.RSACryptoServiceProvider>-Klasse übergeben.</span><span class="sxs-lookup"><span data-stu-id="d7bc9-113">The key is automatically loaded from the key container by name when you pass the <xref:System.Security.Cryptography.CspParameters> object to the constructor of the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#3)]
     [!code-vb[HowToVerifyXMLDocumentRSA#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#3)]  
  
3. <span data-ttu-id="d7bc9-114">Erstellen Sie ein <xref:System.Xml.XmlDocument>-Objekt, indem Sie eine XML-Datei von einem Datenträger laden.</span><span class="sxs-lookup"><span data-stu-id="d7bc9-114">Create an <xref:System.Xml.XmlDocument> object by loading an XML file from disk.</span></span>  <span data-ttu-id="d7bc9-115">Das <xref:System.Xml.XmlDocument>-Objekt enthält das signierte XML-Dokument, das überprüft werden soll.</span><span class="sxs-lookup"><span data-stu-id="d7bc9-115">The <xref:System.Xml.XmlDocument> object contains the signed XML document to verify.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#4)]
     [!code-vb[HowToVerifyXMLDocumentRSA#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#4)]  
  
4. <span data-ttu-id="d7bc9-116">Erstellen Sie ein neues <xref:System.Security.Cryptography.Xml.SignedXml>-Objekt, und übergeben Sie diesem das <xref:System.Xml.XmlDocument>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="d7bc9-116">Create a new <xref:System.Security.Cryptography.Xml.SignedXml> object and pass the <xref:System.Xml.XmlDocument> object to it.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#5)]
     [!code-vb[HowToVerifyXMLDocumentRSA#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#5)]  
  
5. <span data-ttu-id="d7bc9-117">Suchen Sie die <`signature`>-Element, und erstellen Sie ein neues <xref:System.Xml.XmlNodeList>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="d7bc9-117">Find the <`signature`> element and create a new <xref:System.Xml.XmlNodeList> object.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#6)]
     [!code-vb[HowToVerifyXMLDocumentRSA#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#6)]  
  
6. <span data-ttu-id="d7bc9-118">Laden Sie den XML-Code des ersten <`signature`>-Element in das <xref:System.Security.Cryptography.Xml.SignedXml> Objekt.</span><span class="sxs-lookup"><span data-stu-id="d7bc9-118">Load the XML of the first <`signature`> element into the <xref:System.Security.Cryptography.Xml.SignedXml> object.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#7)]
     [!code-vb[HowToVerifyXMLDocumentRSA#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#7)]  
  
7. <span data-ttu-id="d7bc9-119">Überprüfen Sie die Signatur mit der <xref:System.Security.Cryptography.Xml.SignedXml.CheckSignature%2A>-Methode und dem öffentlichen RSA-Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="d7bc9-119">Check the signature using the <xref:System.Security.Cryptography.Xml.SignedXml.CheckSignature%2A> method and the RSA public key.</span></span>  <span data-ttu-id="d7bc9-120">Diese Methode gibt einen booleschen Wert zurück, mit dem Erfolg oder Fehlschlagen des Vorgangs angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d7bc9-120">This method returns a Boolean value that indicates success or failure.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#8)]
     [!code-vb[HowToVerifyXMLDocumentRSA#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="d7bc9-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d7bc9-121">Example</span></span>  
 <span data-ttu-id="d7bc9-122">Für dieses Beispiel wird angenommen, dass eine Datei namens `"test.xml"` im selben Verzeichnis wie das kompilierte Programm vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="d7bc9-122">This example assumes that a file named `"test.xml"` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="d7bc9-123">Die `"test.xml"` Datei muss mithilfe der in Gewusst [wie: Signieren von XML-Dokumenten mit digitalen Signaturen](../../../docs/standard/security/how-to-sign-xml-documents-with-digital-signatures.md)beschriebenen Techniken signiert werden.</span><span class="sxs-lookup"><span data-stu-id="d7bc9-123">The `"test.xml"` file must be signed using the techniques described in [How to: Sign XML Documents with Digital Signatures](../../../docs/standard/security/how-to-sign-xml-documents-with-digital-signatures.md).</span></span>  
  
 [!code-csharp[HowToVerifyXMLDocumentRSA#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#1)]
 [!code-vb[HowToVerifyXMLDocumentRSA#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d7bc9-124">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="d7bc9-124">Compiling the Code</span></span>  
  
- <span data-ttu-id="d7bc9-125">Um dieses Beispiel zu kompilieren, müssen Sie einen Verweis auf `System.Security.dll` einfügen.</span><span class="sxs-lookup"><span data-stu-id="d7bc9-125">To compile this example, you need to include a reference to `System.Security.dll`.</span></span>  
  
- <span data-ttu-id="d7bc9-126">Fügen Sie die folgenden Namespaces hinzu: <xref:System.Xml>, <xref:System.Security.Cryptography> und <xref:System.Security.Cryptography.Xml>.</span><span class="sxs-lookup"><span data-stu-id="d7bc9-126">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="d7bc9-127">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="d7bc9-127">.NET Framework Security</span></span>  
 <span data-ttu-id="d7bc9-128">Sie sollten den privaten Schlüssel eines asymmetrischen Schlüsselpaars niemals in Klartext speichern oder übertragen.</span><span class="sxs-lookup"><span data-stu-id="d7bc9-128">Never store or transfer the private key of an asymmetric key pair in plaintext.</span></span>  <span data-ttu-id="d7bc9-129">Weitere Informationen zu symmetrischen und asymmetrischen Kryptografieschlüsseln finden Sie unter [Erstellen von Schlüsseln für die Verschlüsselung und Entschlüsselung](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md).</span><span class="sxs-lookup"><span data-stu-id="d7bc9-129">For more information about symmetric and asymmetric cryptographic keys, see [Generating Keys for Encryption and Decryption](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md).</span></span>  
  
 <span data-ttu-id="d7bc9-130">Sie sollten einen privaten Schlüssel niemals direkt in Ihren Quellcode einbetten.</span><span class="sxs-lookup"><span data-stu-id="d7bc9-130">Never embed a private key directly into your source code.</span></span>  <span data-ttu-id="d7bc9-131">Eingebettete Schlüssel können problemlos aus einer Assembly gelesen werden, indem [Ildasm. exe (IL-Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) verwendet wird, oder indem die Assembly in einem Texteditor wie dem Editor geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="d7bc9-131">Embedded keys can be easily read from an assembly using the [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) or by opening the assembly in a text editor such as Notepad.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7bc9-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7bc9-132">See also</span></span>

- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="d7bc9-133">Gewusst wie: Signieren von XML-Dokumenten mit digitalen Signaturen</span><span class="sxs-lookup"><span data-stu-id="d7bc9-133">How to: Sign XML Documents with Digital Signatures</span></span>](../../../docs/standard/security/how-to-sign-xml-documents-with-digital-signatures.md)
