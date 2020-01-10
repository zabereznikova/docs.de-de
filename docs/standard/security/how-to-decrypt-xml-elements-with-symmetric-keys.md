---
title: 'Gewusst wie: Entschlüsseln von XML-Elementen mit symmetrischen Schlüsseln'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- symmetric keys
- System.Security.Cryptography.EncryptedXml class
- System.Security.Cryptography.RijndaelManaged class
- XML encryption
- Rijndael
- decryption
ms.assetid: 6038aff0-f92c-4e29-a618-d793410410d8
ms.openlocfilehash: fd377cd470d361f5a46c662ab37780713a2d3804
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706122"
---
# <a name="how-to-decrypt-xml-elements-with-symmetric-keys"></a><span data-ttu-id="6f537-102">Gewusst wie: Entschlüsseln von XML-Elementen mit symmetrischen Schlüsseln</span><span class="sxs-lookup"><span data-stu-id="6f537-102">How to: Decrypt XML Elements with Symmetric Keys</span></span>
<span data-ttu-id="6f537-103">Sie können die Klassen im <xref:System.Security.Cryptography.Xml>-Namespace verwenden, um ein Element in einem XML-Dokument zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="6f537-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to encrypt an element within an XML document.</span></span>  <span data-ttu-id="6f537-104">Die XML-Verschlüsselung ermöglicht Ihnen das Speichern oder Transportieren von vertraulichen XML-Dokumenten, ohne befürchten zu müssen, dass die Daten einfach gelesen werden können.</span><span class="sxs-lookup"><span data-stu-id="6f537-104">XML Encryption allows you to store or transport sensitive XML, without worrying about the data being easily read.</span></span>  <span data-ttu-id="6f537-105">In diesem Codebeispiel wird ein XML-Element mithilfe des AES-Algorithmus (Advanced Encryption Standard) entschlüsselt, der auch unter dem Namen Rijndael bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="6f537-105">This code example decrypts an XML element using the Advanced Encryption Standard (AES) algorithm, also known as Rijndael.</span></span>  
  
 <span data-ttu-id="6f537-106">Informationen dazu, wie Sie ein XML-Element mithilfe dieser Prozedur verschlüsseln, finden Sie unter Gewusst [wie: Verschlüsseln von XML-Elementen mit symmetrischen Schlüsseln](../../../docs/standard/security/how-to-encrypt-xml-elements-with-symmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="6f537-106">For information about how to encrypt an XML element using this procedure, see [How to: Encrypt XML Elements with Symmetric Keys](../../../docs/standard/security/how-to-encrypt-xml-elements-with-symmetric-keys.md).</span></span>  
  
 <span data-ttu-id="6f537-107">Wenn Sie einen symmetrischen Algorithmus wie AES verwenden, um XML-Daten zu verschlüsseln, müssen Sie für das Verschlüsseln und Entschlüsseln der XML-Daten denselben Schlüssel verwenden.</span><span class="sxs-lookup"><span data-stu-id="6f537-107">When you use a symmetric algorithm like AES to encrypt XML data, you must use the same key to encrypt and decrypt the XML data.</span></span>  <span data-ttu-id="6f537-108">Für das Beispiel in dieser Prozedur wird angenommen, dass das verschlüsselte XML-Element mit demselben Schlüssel verschlüsselt wurde und dass sich die verschlüsselnden und die entschlüsselnden Beteiligten über den zu verwendenden Algorithmus und Schlüssel verständigt haben.</span><span class="sxs-lookup"><span data-stu-id="6f537-108">The example in this procedure assumes that the encrypted XML was encrypted using the same key, and that the encrypting and decrypting parties agree on the algorithm and key to use.</span></span>  <span data-ttu-id="6f537-109">In diesem Beispiel wird der AES-Schlüssel weder im verschlüsselten XML-Element gespeichert noch dort verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="6f537-109">This example does not store or encrypt the AES key within the encrypted XML.</span></span>  
  
 <span data-ttu-id="6f537-110">Dieses Beispiel ist für Situationen geeignet, in denen eine einzelne Anwendung Daten auf Basis eines Sitzungsschlüssels, der sich im Arbeitsspeicher befindet, oder auf Basis eines starken kryptografischen Schlüssels verschlüsseln muss, der aus einem Kennwort abgeleitet wurde.</span><span class="sxs-lookup"><span data-stu-id="6f537-110">This example is appropriate for situations where a single application needs to encrypt data based on a session key stored in memory, or based on a cryptographically strong key derived from a password.</span></span>  <span data-ttu-id="6f537-111">Für Situationen, in denen zwei oder mehr Anwendungen verschlüsselte XML-Daten gemeinsam verwenden müssen, empfiehlt sich die Verwendung eines Verschlüsselungsschemas, dem ein asymmetrischer Algorithmus oder ein X.509-Zertifikat zugrunde liegt.</span><span class="sxs-lookup"><span data-stu-id="6f537-111">For situations where two or more applications need to share encrypted XML data, consider using an encryption scheme based on an asymmetric algorithm or an X.509 certificate.</span></span>  
  
### <a name="to-decrypt-an-xml-element-with-a-symmetric-key"></a><span data-ttu-id="6f537-112">So entschlüsseln Sie ein XML-Element mit einem symmetrischen Schlüssel</span><span class="sxs-lookup"><span data-stu-id="6f537-112">To decrypt an XML element with a symmetric key</span></span>  
  
1. <span data-ttu-id="6f537-113">Verschlüsseln Sie ein XML-Element mit dem zuvor generierten Schlüssel mithilfe der in Gewusst [wie: Verschlüsseln von XML-Elementen mit symmetrischen Schlüsseln](../../../docs/standard/security/how-to-encrypt-xml-elements-with-symmetric-keys.md)beschriebenen Techniken.</span><span class="sxs-lookup"><span data-stu-id="6f537-113">Encrypt an XML element with the previously generated key using the techniques described in [How to: Encrypt XML Elements with Symmetric Keys](../../../docs/standard/security/how-to-encrypt-xml-elements-with-symmetric-keys.md).</span></span>  
  
2. <span data-ttu-id="6f537-114">Suchen Sie die <`EncryptedData`>-Element (definiert durch den XML-Verschlüsselungsstandard) in einem <xref:System.Xml.XmlDocument> Objekt, das den verschlüsselten XML-Code enthält, und erstellen Sie ein neues <xref:System.Xml.XmlElement> Objekt, das dieses Element darstellt.</span><span class="sxs-lookup"><span data-stu-id="6f537-114">Find the <`EncryptedData`> element (defined by the XML Encryption standard) in an <xref:System.Xml.XmlDocument> object that contains the encrypted XML and create a new <xref:System.Xml.XmlElement> object to represent that element.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#10)]
     [!code-vb[HowToEncryptXMLElementSymmetric#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#10)]  
  
3. <span data-ttu-id="6f537-115">Erstellen Sie ein <xref:System.Security.Cryptography.Xml.EncryptedData>-Objekt, indem Sie die unformatierten XML-Daten aus dem zuvor erstellten <xref:System.Xml.XmlElement>-Objekt laden.</span><span class="sxs-lookup"><span data-stu-id="6f537-115">Create an <xref:System.Security.Cryptography.Xml.EncryptedData> object by loading the raw XML data from the previously created <xref:System.Xml.XmlElement> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#11)]
     [!code-vb[HowToEncryptXMLElementSymmetric#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#11)]  
  
4. <span data-ttu-id="6f537-116">Erstellen Sie ein neues <xref:System.Security.Cryptography.Xml.EncryptedXml>-Objekt, und verwenden Sie dieses Objekt, um die XML-Daten zu entschlüsseln. Verwenden Sie dazu den Schlüssel, der für die Verschlüsselung verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="6f537-116">Create a new <xref:System.Security.Cryptography.Xml.EncryptedXml> object and use it to decrypt the XML data using the same key that was used for encryption.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#12)]
     [!code-vb[HowToEncryptXMLElementSymmetric#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#12)]  
  
5. <span data-ttu-id="6f537-117">Ersetzen Sie das verschlüsselte Element durch das neu entschlüsselte Nur-Text Element innerhalb des XML-Dokuments.</span><span class="sxs-lookup"><span data-stu-id="6f537-117">Replace the encrypted element with the newly decrypted plaintext element within the XML document.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#13](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#13)]
     [!code-vb[HowToEncryptXMLElementSymmetric#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#13)]  
  
## <a name="example"></a><span data-ttu-id="6f537-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6f537-118">Example</span></span>  
 <span data-ttu-id="6f537-119">Für dieses Beispiel wird angenommen, dass eine Datei namens `"test.xml"` im selben Verzeichnis wie das kompilierte Programm vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="6f537-119">This example assumes that a file named `"test.xml"` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="6f537-120">Außerdem wird angenommen, dass `"test.xml"` ein `"creditcard"`-Element enthält.</span><span class="sxs-lookup"><span data-stu-id="6f537-120">It also assumes that `"test.xml"` contains a `"creditcard"` element.</span></span>  <span data-ttu-id="6f537-121">Sie können den folgenden XML-Code in eine Datei namens `test.xml` einfügen und mit diesem Beispiel verwenden.</span><span class="sxs-lookup"><span data-stu-id="6f537-121">You can place the following XML into a file called `test.xml` and use it with this example.</span></span>  
  
```xml  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
```  
  
 [!code-csharp[HowToEncryptXMLElementSymmetric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#1)]
 [!code-vb[HowToEncryptXMLElementSymmetric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6f537-122">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="6f537-122">Compiling the Code</span></span>  
  
- <span data-ttu-id="6f537-123">Um dieses Beispiel zu kompilieren, müssen Sie einen Verweis auf `System.Security.dll` einfügen.</span><span class="sxs-lookup"><span data-stu-id="6f537-123">To compile this example, you need to include a reference to `System.Security.dll`.</span></span>  
  
- <span data-ttu-id="6f537-124">Fügen Sie die folgenden Namespaces hinzu: <xref:System.Xml>, <xref:System.Security.Cryptography> und <xref:System.Security.Cryptography.Xml>.</span><span class="sxs-lookup"><span data-stu-id="6f537-124">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="6f537-125">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="6f537-125">.NET Framework Security</span></span>  
 <span data-ttu-id="6f537-126">Speichern Sie einen kryptografischen Schlüssel nie im Klartextformat, und übertragen Sie einen Schlüssel nie im Klartextformat zwischen Computern.</span><span class="sxs-lookup"><span data-stu-id="6f537-126">Never store a cryptographic key in plaintext or transfer a key between machines in plaintext.</span></span>  
  
 <span data-ttu-id="6f537-127">Wenn Sie einen symmetrischen kryptografischen Schlüssel nicht mehr benötigen, entfernen Sie ihn aus dem Arbeitsspeicher, indem Sie jedes Byte auf 0 (null) festlegen oder indem Sie die <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A>-Methode der verwalteten Kryptografieklasse aufrufen.</span><span class="sxs-lookup"><span data-stu-id="6f537-127">When you are done using a symmetric cryptographic key, clear it from memory by setting each byte to zero or by calling the <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> method of the managed cryptography class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f537-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6f537-128">See also</span></span>

- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="6f537-129">Gewusst wie: Verschlüsseln von XML-Elementen mit symmetrischen Schlüsseln</span><span class="sxs-lookup"><span data-stu-id="6f537-129">How to: Encrypt XML Elements with Symmetric Keys</span></span>](../../../docs/standard/security/how-to-encrypt-xml-elements-with-symmetric-keys.md)
