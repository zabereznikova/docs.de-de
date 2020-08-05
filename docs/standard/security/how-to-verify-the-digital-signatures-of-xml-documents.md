---
title: 'Vorgehensweise: Überprüfen der digitalen Signaturen von XML-Dokumenten'
ms.date: 07/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- System.Security.Cryptography.SignedXml class
- signatures, cryptographic
- System.Security.Cryptography.RSA class
- verifying signatures
- checking signatures
- XML digital signatures
- digital signatures, verifying
ms.assetid: a4d5ceb1-b9f5-47e8-9e4a-a2b39110002f
ms.openlocfilehash: b9b2dc6a558d1fd6acd2922a7c8ad82ce8776c26
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87557046"
---
# <a name="how-to-verify-the-digital-signatures-of-xml-documents"></a><span data-ttu-id="30bd0-102">Vorgehensweise: Überprüfen der digitalen Signaturen von XML-Dokumenten</span><span class="sxs-lookup"><span data-stu-id="30bd0-102">How to: Verify the Digital Signatures of XML Documents</span></span>

<span data-ttu-id="30bd0-103">Um XML-Daten zu überprüfen, die mit einer digitalen Signatur signiert sind, können Sie die Klassen im <xref:System.Security.Cryptography.Xml>-Namespace verwenden.</span><span class="sxs-lookup"><span data-stu-id="30bd0-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to verify XML data signed with a digital signature.</span></span> <span data-ttu-id="30bd0-104">Über digitale XML-Signaturen (XMLDSIG) können Sie sich vergewissern, dass Daten nicht mehr geändert wurden, nachdem sie signiert wurden.</span><span class="sxs-lookup"><span data-stu-id="30bd0-104">XML digital signatures (XMLDSIG) allow you to verify that data was not altered after it was signed.</span></span> <span data-ttu-id="30bd0-105">Weitere Informationen zum XMLDSIG-Standard finden Sie in der World Wide Web Consortium-Spezifikation (W3C) unter <https://www.w3.org/TR/xmldsig-core/> .</span><span class="sxs-lookup"><span data-stu-id="30bd0-105">For more information about the XMLDSIG standard, see the World Wide Web Consortium (W3C) specification at <https://www.w3.org/TR/xmldsig-core/>.</span></span>
  
> [!NOTE]
> <span data-ttu-id="30bd0-106">Der Code in diesem Artikel gilt für Windows.</span><span class="sxs-lookup"><span data-stu-id="30bd0-106">The code in this article applies to Windows.</span></span>

<span data-ttu-id="30bd0-107">Das Codebeispiel in dieser Prozedur veranschaulicht, wie eine digitale XML-Signatur, die in einem <>-Element enthalten ist, überprüft wird `Signature` .</span><span class="sxs-lookup"><span data-stu-id="30bd0-107">The code example in this procedure demonstrates how to verify an XML digital signature contained in a <`Signature`> element.</span></span>  <span data-ttu-id="30bd0-108">Im Beispiel wird ein öffentlicher RSA-Schlüssel aus einem Schlüsselcontainer abgerufen und anschließend zum Überprüfen der Signatur verwendet. </span><span class="sxs-lookup"><span data-stu-id="30bd0-108">The example retrieves an RSA public key from a key container and then uses the key to verify the signature.</span></span>  
  
<span data-ttu-id="30bd0-109">Informationen dazu, wie eine digitale Signatur erstellt wird, die mithilfe dieser Technik überprüft werden kann, finden Sie unter Gewusst [wie: Signieren von XML-Dokumenten mit digitalen Signaturen](how-to-sign-xml-documents-with-digital-signatures.md).</span><span class="sxs-lookup"><span data-stu-id="30bd0-109">For information about how create a digital signature that can be verified using this technique, see [How to: Sign XML Documents with Digital Signatures](how-to-sign-xml-documents-with-digital-signatures.md).</span></span>  
  
### <a name="to-verify-the-digital-signature-of-an-xml-document"></a><span data-ttu-id="30bd0-110">So überprüfen Sie die digitale Signatur eines XML-Dokuments</span><span class="sxs-lookup"><span data-stu-id="30bd0-110">To verify the digital signature of an XML document</span></span>  
  
1. <span data-ttu-id="30bd0-111">Um das Dokument zu überprüfen, müssen Sie denselben asymmetrischen Schlüssel wie für die Signierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="30bd0-111">To verify the document, you must use the same asymmetric key that was used for signing.</span></span>  <span data-ttu-id="30bd0-112">Erstellen Sie ein <xref:System.Security.Cryptography.CspParameters>-Objekt, und geben Sie den Namen des Schlüsselcontainers an, der zum Signieren verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="30bd0-112">Create a <xref:System.Security.Cryptography.CspParameters> object and specify the name of the key container that was used for signing.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#2)]
     [!code-vb[HowToVerifyXMLDocumentRSA#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#2)]  
  
2. <span data-ttu-id="30bd0-113">Rufen Sie den öffentlichen Schlüssel mit der <xref:System.Security.Cryptography.RSACryptoServiceProvider>-Klasse ab.</span><span class="sxs-lookup"><span data-stu-id="30bd0-113">Retrieve the public key using the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class.</span></span>  <span data-ttu-id="30bd0-114">Der Schlüssel wird automatisch nach Name aus dem Schlüsselcontainer geladen, wenn Sie das <xref:System.Security.Cryptography.CspParameters>-Objekt an den Konstruktor der <xref:System.Security.Cryptography.RSACryptoServiceProvider>-Klasse übergeben.</span><span class="sxs-lookup"><span data-stu-id="30bd0-114">The key is automatically loaded from the key container by name when you pass the <xref:System.Security.Cryptography.CspParameters> object to the constructor of the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#3)]
     [!code-vb[HowToVerifyXMLDocumentRSA#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#3)]  
  
3. <span data-ttu-id="30bd0-115">Erstellen Sie ein <xref:System.Xml.XmlDocument>-Objekt, indem Sie eine XML-Datei von einem Datenträger laden.</span><span class="sxs-lookup"><span data-stu-id="30bd0-115">Create an <xref:System.Xml.XmlDocument> object by loading an XML file from disk.</span></span>  <span data-ttu-id="30bd0-116">Das <xref:System.Xml.XmlDocument>-Objekt enthält das signierte XML-Dokument, das überprüft werden soll.</span><span class="sxs-lookup"><span data-stu-id="30bd0-116">The <xref:System.Xml.XmlDocument> object contains the signed XML document to verify.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#4)]
     [!code-vb[HowToVerifyXMLDocumentRSA#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#4)]  
  
4. <span data-ttu-id="30bd0-117">Erstellen Sie ein neues <xref:System.Security.Cryptography.Xml.SignedXml>-Objekt, und übergeben Sie diesem das <xref:System.Xml.XmlDocument>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="30bd0-117">Create a new <xref:System.Security.Cryptography.Xml.SignedXml> object and pass the <xref:System.Xml.XmlDocument> object to it.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#5)]
     [!code-vb[HowToVerifyXMLDocumentRSA#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#5)]  
  
5. <span data-ttu-id="30bd0-118">Suchen Sie das <`signature`>-Element, und erstellen Sie ein neues- <xref:System.Xml.XmlNodeList> Objekt.</span><span class="sxs-lookup"><span data-stu-id="30bd0-118">Find the <`signature`> element and create a new <xref:System.Xml.XmlNodeList> object.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#6)]
     [!code-vb[HowToVerifyXMLDocumentRSA#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#6)]  
  
6. <span data-ttu-id="30bd0-119">Laden Sie den XML-Code des ersten <`signature`>-Elements in das- <xref:System.Security.Cryptography.Xml.SignedXml> Objekt.</span><span class="sxs-lookup"><span data-stu-id="30bd0-119">Load the XML of the first <`signature`> element into the <xref:System.Security.Cryptography.Xml.SignedXml> object.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#7)]
     [!code-vb[HowToVerifyXMLDocumentRSA#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#7)]  
  
7. <span data-ttu-id="30bd0-120">Überprüfen Sie die Signatur mit der <xref:System.Security.Cryptography.Xml.SignedXml.CheckSignature%2A>-Methode und dem öffentlichen RSA-Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="30bd0-120">Check the signature using the <xref:System.Security.Cryptography.Xml.SignedXml.CheckSignature%2A> method and the RSA public key.</span></span>  <span data-ttu-id="30bd0-121">Diese Methode gibt einen booleschen Wert zurück, mit dem Erfolg oder Fehlschlagen des Vorgangs angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="30bd0-121">This method returns a Boolean value that indicates success or failure.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#8)]
     [!code-vb[HowToVerifyXMLDocumentRSA#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="30bd0-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="30bd0-122">Example</span></span>

<span data-ttu-id="30bd0-123">Für dieses Beispiel wird angenommen, dass eine Datei namens `"test.xml"` im selben Verzeichnis wie das kompilierte Programm vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="30bd0-123">This example assumes that a file named `"test.xml"` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="30bd0-124">Die `"test.xml"` Datei muss mithilfe der in Gewusst [wie: Signieren von XML-Dokumenten mit digitalen Signaturen](how-to-sign-xml-documents-with-digital-signatures.md)beschriebenen Techniken signiert werden.</span><span class="sxs-lookup"><span data-stu-id="30bd0-124">The `"test.xml"` file must be signed using the techniques described in [How to: Sign XML Documents with Digital Signatures](how-to-sign-xml-documents-with-digital-signatures.md).</span></span>  
  
[!code-csharp[HowToVerifyXMLDocumentRSA#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#1)]
[!code-vb[HowToVerifyXMLDocumentRSA#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="30bd0-125">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="30bd0-125">Compiling the Code</span></span>  
  
- <span data-ttu-id="30bd0-126">Fügen Sie in einem Projekt, das .NET Framework als Ziel hat, einen Verweis auf ein `System.Security.dll` .</span><span class="sxs-lookup"><span data-stu-id="30bd0-126">In a project that targets .NET Framework, include a reference to `System.Security.dll`.</span></span>

- <span data-ttu-id="30bd0-127">Installieren Sie in einem Projekt, das .net Core oder .net 5 als Ziel hat, das nuget-Paket [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span><span class="sxs-lookup"><span data-stu-id="30bd0-127">In a project that targets .NET Core or .NET 5, install NuGet package [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span></span>
  
- <span data-ttu-id="30bd0-128">Fügen Sie die folgenden Namespaces hinzu: <xref:System.Xml>, <xref:System.Security.Cryptography> und <xref:System.Security.Cryptography.Xml>.</span><span class="sxs-lookup"><span data-stu-id="30bd0-128">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="30bd0-129">.NET-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="30bd0-129">.NET Security</span></span>

<span data-ttu-id="30bd0-130">Sie sollten den privaten Schlüssel eines asymmetrischen Schlüsselpaars niemals in Klartext speichern oder übertragen.</span><span class="sxs-lookup"><span data-stu-id="30bd0-130">Never store or transfer the private key of an asymmetric key pair in plaintext.</span></span>  <span data-ttu-id="30bd0-131">Weitere Informationen zu symmetrischen und asymmetrischen Kryptografieschlüsseln finden Sie unter [Erstellen von Schlüsseln für die Verschlüsselung und Entschlüsselung](generating-keys-for-encryption-and-decryption.md).</span><span class="sxs-lookup"><span data-stu-id="30bd0-131">For more information about symmetric and asymmetric cryptographic keys, see [Generating Keys for Encryption and Decryption](generating-keys-for-encryption-and-decryption.md).</span></span>  
  
<span data-ttu-id="30bd0-132">Sie sollten einen privaten Schlüssel niemals direkt in Ihren Quellcode einbetten.</span><span class="sxs-lookup"><span data-stu-id="30bd0-132">Never embed a private key directly into your source code.</span></span>  <span data-ttu-id="30bd0-133">Eingebettete Schlüssel können problemlos aus einer Assembly gelesen werden, indem Sie die [Ildasm.exe (IL-Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md) verwenden, oder Sie öffnen die Assembly in einem Text-Editor wie Notepad.</span><span class="sxs-lookup"><span data-stu-id="30bd0-133">Embedded keys can be easily read from an assembly using the [Ildasm.exe (IL Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md) or by opening the assembly in a text editor such as Notepad.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30bd0-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="30bd0-134">See also</span></span>

- [<span data-ttu-id="30bd0-135">Kryptografiemodell</span><span class="sxs-lookup"><span data-stu-id="30bd0-135">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="30bd0-136">Kryptografische Dienste</span><span class="sxs-lookup"><span data-stu-id="30bd0-136">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="30bd0-137">Plattformübergreifende Kryptografie</span><span class="sxs-lookup"><span data-stu-id="30bd0-137">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="30bd0-138">Vorgehensweise: Signieren von XML-Dokumenten mit digitalen Signaturen</span><span class="sxs-lookup"><span data-stu-id="30bd0-138">How to: Sign XML Documents with Digital Signatures</span></span>](how-to-sign-xml-documents-with-digital-signatures.md)
- [<span data-ttu-id="30bd0-139">ASP.net Core Datenschutz</span><span class="sxs-lookup"><span data-stu-id="30bd0-139">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
