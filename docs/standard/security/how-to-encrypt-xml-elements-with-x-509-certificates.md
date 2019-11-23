---
title: 'Gewusst wie: Verschlüsseln von XML-Elementen mit X.509-Zertifikaten'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encryption [.NET Framework], X.509 certificates
- cryptography [.NET Framework], X.509 certificates
- System.Security.Cryptography.EncryptedXml class
- XML encryption
- System.Security.Cryptography.X509Certificate2 class
- X.509 certificates
- certificates, X.509 certificates
ms.assetid: 761f1c66-631c-47af-aa86-ad9c50cfa453
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d569d3c020e7329d987e957f181b34c8cfbf941a
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2019
ms.locfileid: "71353860"
---
# <a name="how-to-encrypt-xml-elements-with-x509-certificates"></a><span data-ttu-id="52be6-102">Gewusst wie: Verschlüsseln von XML-Elementen mit X.509-Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="52be6-102">How to: Encrypt XML Elements with X.509 Certificates</span></span>
<span data-ttu-id="52be6-103">Sie können die Klassen im <xref:System.Security.Cryptography.Xml>-Namespace verwenden, um ein Element in einem XML-Dokument zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="52be6-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to encrypt an element within an XML document.</span></span>  <span data-ttu-id="52be6-104">XML-Verschlüsselung ist ein gängiges Verfahren zum Austauschen oder Speichern von verschlüsselten XML-Daten, ohne sich Gedanken machen zu müssen, dass die Daten einfach gelesen werden können.</span><span class="sxs-lookup"><span data-stu-id="52be6-104">XML Encryption is a standard way to exchange or store encrypted XML data, without worrying about the data being easily read.</span></span>  <span data-ttu-id="52be6-105">Weitere Informationen zum XML-Verschlüsselungsstandard finden Sie in der World Wide Web Consortium (W3C)-Spezifikation für die XML-Verschlüsselung unter <https://www.w3.org/TR/xmldsig-core/>.</span><span class="sxs-lookup"><span data-stu-id="52be6-105">For more information about the XML Encryption standard, see the World Wide Web Consortium (W3C) specification for XML Encryption located at <https://www.w3.org/TR/xmldsig-core/>.</span></span>  
  
 <span data-ttu-id="52be6-106">Sie können die XML-Verschlüsselung verwenden, um jedes XML-Element oder XML-Dokument durch ein <`EncryptedData`>-Element zu ersetzen, das die verschlüsselten XML-Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="52be6-106">You can use XML Encryption to replace any XML element or document with an <`EncryptedData`> element that contains the encrypted XML data.</span></span> <span data-ttu-id="52be6-107">Das <`EncryptedData`>-Element kann auch Unterelemente mit Informationen über die bei der Verschlüsselung verwendeten Schlüssel und Prozesse enthalten.</span><span class="sxs-lookup"><span data-stu-id="52be6-107">The <`EncryptedData`> element can contain sub elements that include information about the keys and processes used during encryption.</span></span>  <span data-ttu-id="52be6-108">XML-Verschlüsselung unterstützt, dass ein Dokument mehrere verschlüsselte Elemente enthält und dass ein Element mehrfach verschlüsselt ist.</span><span class="sxs-lookup"><span data-stu-id="52be6-108">XML Encryption allows a document to contain multiple encrypted elements and allows an element to be encrypted multiple times.</span></span>  <span data-ttu-id="52be6-109">Das Codebeispiel in dieser Vorgehensweise veranschaulicht das Erstellen eines <`EncryptedData`>-Elements zusammen mit weiteren Unterelementen, die Sie später bei der Entschlüsselung verwenden können.</span><span class="sxs-lookup"><span data-stu-id="52be6-109">The code example in this procedure shows you how to create an <`EncryptedData`> element along with several other sub elements that you can use later during decryption.</span></span>  
  
 <span data-ttu-id="52be6-110">In diesem Beispiel wird ein XML-Element mithilfe zweier Schlüssel verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="52be6-110">This example encrypts an XML element using two keys.</span></span> <span data-ttu-id="52be6-111">Es wird ein X.509-Testzertifikat mithilfe von [Makecert.exe (Certificate Creation-Tool)](/windows/desktop/SecCrypto/makecert) generiert, und das Zertifikat wird in einem Zertifikatspeicher gespeichert.</span><span class="sxs-lookup"><span data-stu-id="52be6-111">It generates a test X.509 certificate using the [Certificate Creation Tool (Makecert.exe)](/windows/desktop/SecCrypto/makecert) and saves the certificate to a certificate store.</span></span> <span data-ttu-id="52be6-112">Im Beispiel wird das Zertifikat dann programmgesteuert abgerufen und verwendet, um ein XML-Element mithilfe der <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A>-Methode zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="52be6-112">The example then programmatically retrieves the certificate and uses it to encrypt an XML element using the <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> method.</span></span> <span data-ttu-id="52be6-113">Die <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A>-Methode erstellt intern einen separaten Sitzungsschlüssel und verwendet diesen, um das XML-Dokument zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="52be6-113">Internally, the <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> method creates a separate session key and uses it to encrypt the XML document.</span></span> <span data-ttu-id="52be6-114">Diese Methode verschlüsselt den Sitzungsschlüssel und speichert ihn mit dem verschlüsselten XML-Dokument in einem neuen <`EncryptedData`>-Element.</span><span class="sxs-lookup"><span data-stu-id="52be6-114">This method encrypts the session key and saves it along with the encrypted XML within a new <`EncryptedData`> element.</span></span>  
  
 <span data-ttu-id="52be6-115">Um das XML-Element zu entschlüsseln, rufen Sie einfach die <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A>-Methode auf, die automatisch das X.509-Zertifikat aus dem Speicher abruft und die notwendige Entschlüsselung vornimmt.</span><span class="sxs-lookup"><span data-stu-id="52be6-115">To decrypt the XML element, simply call the <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> method, which automatically retrieves the X.509 certificate from the store and performs the necessary decryption.</span></span>  <span data-ttu-id="52be6-116">Weitere Informationen zum Entschlüsseln eines XML-Elements, das mit dieser Vorgehensweise verschlüsselt wurde, finden Sie unter [Gewusst wie: Entschlüsseln von XML-Elementen mit X.509](../../../docs/standard/security/how-to-decrypt-xml-elements-with-x-509-certificates.md)-Zertifikaten.</span><span class="sxs-lookup"><span data-stu-id="52be6-116">For more information about how to decrypt an XML element that was encrypted using this procedure, see [How to: Decrypt XML Elements with X.509 Certificates](../../../docs/standard/security/how-to-decrypt-xml-elements-with-x-509-certificates.md).</span></span>  
  
 <span data-ttu-id="52be6-117">Das Beispiel eignet sich für Situationen, in denen mehrere Anwendungen verschlüsselte Daten gemeinsam nutzen müssen, oder in denen eine Anwendung verschlüsselte Daten zwischen den Zeiten speichern muss, in denen sie ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="52be6-117">This example is appropriate for situations where multiple applications need to share encrypted data or where an application needs to save encrypted data between the times that it runs.</span></span>  
  
### <a name="to-encrypt-an-xml-element-with-an-x509-certificate"></a><span data-ttu-id="52be6-118">So verschlüsseln Sie ein XML-Element mit einem X.509-Zertifikat</span><span class="sxs-lookup"><span data-stu-id="52be6-118">To encrypt an XML element with an X.509 certificate</span></span>  
  
1. <span data-ttu-id="52be6-119">Verwenden Sie [Makecert.exe (Certificate Creation-Tool)](/windows/desktop/SecCrypto/makecert), um ein X.509-Testzertifikat zu generieren und dieses Zertifikat im lokalen Benutzerspeicher abzulegen.</span><span class="sxs-lookup"><span data-stu-id="52be6-119">Use the [Certificate Creation Tool (Makecert.exe)](/windows/desktop/SecCrypto/makecert) to generate a test X.509 certificate and place it in the local user store.</span></span> <span data-ttu-id="52be6-120">Sie müssen einen exportierbaren Austauschschlüssel generieren.</span><span class="sxs-lookup"><span data-stu-id="52be6-120">You must generate an exchange key and you must make the key exportable.</span></span> <span data-ttu-id="52be6-121">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="52be6-121">Run the following command:</span></span>  
  
    ```console  
    makecert -r -pe -n "CN=XML_ENC_TEST_CERT" -b 01/01/2005 -e 01/01/2010 -sky exchange -ss my  
    ```  
  
2. <span data-ttu-id="52be6-122">Erstellen Sie ein <xref:System.Security.Cryptography.X509Certificates.X509Store>-Objekt, und initialisieren Sie dieses, um den aktuellen Benutzerspeicher zu öffnen</span><span class="sxs-lookup"><span data-stu-id="52be6-122">Create an <xref:System.Security.Cryptography.X509Certificates.X509Store> object and initialize it to open the current user store.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#2)]
     [!code-vb[HowToEncryptXMLElementX509#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#2)]  
  
3. <span data-ttu-id="52be6-123">Öffnen Sie den Speicher im schreibgeschützten Modus.</span><span class="sxs-lookup"><span data-stu-id="52be6-123">Open the store in read-only mode.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#3)]
     [!code-vb[HowToEncryptXMLElementX509#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#3)]  
  
4. <span data-ttu-id="52be6-124">Initialisieren Sie eine <xref:System.Security.Cryptography.X509Certificates.X509Certificate2Collection> mit allen im Speicher enthaltenen Zertifikaten.</span><span class="sxs-lookup"><span data-stu-id="52be6-124">Initialize an <xref:System.Security.Cryptography.X509Certificates.X509Certificate2Collection> with all of the certificates in the store.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#4)]
     [!code-vb[HowToEncryptXMLElementX509#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#4)]  
  
5. <span data-ttu-id="52be6-125">Durchlaufen Sie die Zertifikate im Speicher, und suchen Sie nach dem Zertifikat mit dem entsprechenden Namen.</span><span class="sxs-lookup"><span data-stu-id="52be6-125">Enumerate through the certificates in the store and find the certificate with the appropriate name.</span></span>  <span data-ttu-id="52be6-126">In diesem Beispiel hat das Zertifikat den Namen `"CN=XML_ENC_TEST_CERT"`.</span><span class="sxs-lookup"><span data-stu-id="52be6-126">In this example, the certificate is named `"CN=XML_ENC_TEST_CERT"`.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#5)]
     [!code-vb[HowToEncryptXMLElementX509#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#5)]  
  
6. <span data-ttu-id="52be6-127">Schließen Sie den Speicher, nachdem Sie das Zertifikat gefunden haben.</span><span class="sxs-lookup"><span data-stu-id="52be6-127">Close the store after the certificate is located.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#6)]
     [!code-vb[HowToEncryptXMLElementX509#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#6)]  
  
7. <span data-ttu-id="52be6-128">Erstellen Sie ein <xref:System.Xml.XmlDocument>-Objekt, indem Sie eine XML-Datei von einem Datenträger laden.</span><span class="sxs-lookup"><span data-stu-id="52be6-128">Create an <xref:System.Xml.XmlDocument> object by loading an XML file from disk.</span></span>  <span data-ttu-id="52be6-129">Das <xref:System.Xml.XmlDocument>-Objekt enthält das zu verschlüsselnde XML-Element.</span><span class="sxs-lookup"><span data-stu-id="52be6-129">The <xref:System.Xml.XmlDocument> object contains the XML element to encrypt.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#7)]
     [!code-vb[HowToEncryptXMLElementX509#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#7)]  
  
8. <span data-ttu-id="52be6-130">Suchen Sie das angegebene Element im <xref:System.Xml.XmlDocument>-Objekt, und erstellen Sie ein neues <xref:System.Xml.XmlElement>-Objekt, das dem Element entspricht, das Sie verschlüsseln möchten.</span><span class="sxs-lookup"><span data-stu-id="52be6-130">Find the specified element in the <xref:System.Xml.XmlDocument> object and create a new <xref:System.Xml.XmlElement> object to represent the element you want to encrypt.</span></span>  <span data-ttu-id="52be6-131">In diesem Beispiel wird das `"creditcard"`-Element verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="52be6-131">In this example, the `"creditcard"` element is encrypted.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#8)]
     [!code-vb[HowToEncryptXMLElementX509#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#8)]  
  
9. <span data-ttu-id="52be6-132">Erstellen Sie eine neue Instanz der <xref:System.Security.Cryptography.Xml.EncryptedXml>-Klasse, und verwenden Sie diese, um das angegebene Element mit dem X.059-Zertifikat zu verschlüsseln .</span><span class="sxs-lookup"><span data-stu-id="52be6-132">Create a new instance of the <xref:System.Security.Cryptography.Xml.EncryptedXml> class and use it to encrypt the specified element using the X.509 certificate.</span></span>  <span data-ttu-id="52be6-133">Die <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A>-Methode gibt das verschlüsselte Element als ein <xref:System.Security.Cryptography.Xml.EncryptedData>-Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="52be6-133">The <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> method returns the encrypted element as an <xref:System.Security.Cryptography.Xml.EncryptedData> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#9)]
     [!code-vb[HowToEncryptXMLElementX509#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#9)]  
  
10. <span data-ttu-id="52be6-134">Ersetzen Sie das Element aus dem ursprünglichen <xref:System.Xml.XmlDocument>-Objekt durch das <xref:System.Security.Cryptography.Xml.EncryptedData>-Element.</span><span class="sxs-lookup"><span data-stu-id="52be6-134">Replace the element from the original <xref:System.Xml.XmlDocument> object with the <xref:System.Security.Cryptography.Xml.EncryptedData> element.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#10)]
     [!code-vb[HowToEncryptXMLElementX509#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#10)]  
  
11. <span data-ttu-id="52be6-135">Speichern Sie das <xref:System.Xml.XmlDocument>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="52be6-135">Save the <xref:System.Xml.XmlDocument> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#11)]
     [!code-vb[HowToEncryptXMLElementX509#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#11)]  
  
## <a name="example"></a><span data-ttu-id="52be6-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="52be6-136">Example</span></span>  
 <span data-ttu-id="52be6-137">Für dieses Beispiel wird angenommen, dass eine Datei namens `"test.xml"` im selben Verzeichnis wie das kompilierte Programm vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="52be6-137">This example assumes that a file named `"test.xml"` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="52be6-138">Außerdem wird angenommen, dass `"test.xml"` ein `"creditcard"`-Element enthält.</span><span class="sxs-lookup"><span data-stu-id="52be6-138">It also assumes that `"test.xml"` contains a `"creditcard"` element.</span></span>  <span data-ttu-id="52be6-139">Sie können den folgenden XML-Code in eine Datei namens `test.xml` einfügen und mit diesem Beispiel verwenden.</span><span class="sxs-lookup"><span data-stu-id="52be6-139">You can place the following XML into a file called `test.xml` and use it with this example.</span></span>  
  
```xml  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
```  
  
 [!code-csharp[HowToEncryptXMLElementX509#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#1)]
 [!code-vb[HowToEncryptXMLElementX509#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="52be6-140">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="52be6-140">Compiling the Code</span></span>  
  
- <span data-ttu-id="52be6-141">Um dieses Beispiel zu kompilieren, müssen Sie einen Verweis auf `System.Security.dll` einfügen.</span><span class="sxs-lookup"><span data-stu-id="52be6-141">To compile this example, you need to include a reference to `System.Security.dll`.</span></span>  
  
- <span data-ttu-id="52be6-142">Fügen Sie die folgenden Namespaces hinzu: <xref:System.Xml>, <xref:System.Security.Cryptography> und <xref:System.Security.Cryptography.Xml>.</span><span class="sxs-lookup"><span data-stu-id="52be6-142">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="52be6-143">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="52be6-143">.NET Framework Security</span></span>  
 <span data-ttu-id="52be6-144">Das in diesem Beispiel verwendete X.509-Zertifikat ist nur für Testzwecke vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="52be6-144">The X.509 certificate used in this example is for test purposes only.</span></span>  <span data-ttu-id="52be6-145">Anwendungen sollten ein X.059-Zertifikat verwenden, das entweder von einer vertrauenswürdigen Zertifizierungsstelle oder vom Microsoft Windows-Zertifikatsserver generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="52be6-145">Applications should use an X.509 certificate generated by a trusted certificate authority or use a certificate generated by the Microsoft Windows Certificate Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52be6-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="52be6-146">See also</span></span>

- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="52be6-147">Gewusst wie: Entschlüsseln von XML-Elementen mit X.509-Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="52be6-147">How to: Decrypt XML Elements with X.509 Certificates</span></span>](../../../docs/standard/security/how-to-decrypt-xml-elements-with-x-509-certificates.md)
