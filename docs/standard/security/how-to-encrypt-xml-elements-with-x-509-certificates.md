---
title: 'Vorgehensweise: Verschlüsseln von XML-Elementen mit X.509-Zertifikaten'
ms.date: 07/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encryption [.NET], X.509 certificates
- cryptography [.NET], X.509 certificates
- System.Security.Cryptography.EncryptedXml class
- XML encryption
- System.Security.Cryptography.X509Certificate2 class
- X.509 certificates
- certificates, X.509 certificates
ms.assetid: 761f1c66-631c-47af-aa86-ad9c50cfa453
ms.openlocfilehash: c978bea7336e64d6622aca4d21c7ef3317d73957
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87555720"
---
# <a name="how-to-encrypt-xml-elements-with-x509-certificates"></a><span data-ttu-id="1681c-102">Vorgehensweise: Verschlüsseln von XML-Elementen mit X.509-Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="1681c-102">How to: Encrypt XML Elements with X.509 Certificates</span></span>

<span data-ttu-id="1681c-103">Sie können die Klassen im <xref:System.Security.Cryptography.Xml>-Namespace verwenden, um ein Element in einem XML-Dokument zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="1681c-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to encrypt an element within an XML document.</span></span>  <span data-ttu-id="1681c-104">XML-Verschlüsselung ist ein gängiges Verfahren zum Austauschen oder Speichern von verschlüsselten XML-Daten, ohne sich Gedanken machen zu müssen, dass die Daten einfach gelesen werden können.</span><span class="sxs-lookup"><span data-stu-id="1681c-104">XML Encryption is a standard way to exchange or store encrypted XML data, without worrying about the data being easily read.</span></span>  <span data-ttu-id="1681c-105">Weitere Informationen zum XML-Verschlüsselungsstandard finden Sie in der World Wide Web Consortium (W3C)-Spezifikation für die XML-Verschlüsselung unter <https://www.w3.org/TR/xmldsig-core/> .</span><span class="sxs-lookup"><span data-stu-id="1681c-105">For more information about the XML Encryption standard, see the World Wide Web Consortium (W3C) specification for XML Encryption located at <https://www.w3.org/TR/xmldsig-core/>.</span></span>  
  
 <span data-ttu-id="1681c-106">Sie können die XML-Verschlüsselung verwenden, um jedes XML-Element oder XML-Dokument durch ein <`EncryptedData`>-Element zu ersetzen, das die verschlüsselten XML-Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="1681c-106">You can use XML Encryption to replace any XML element or document with an <`EncryptedData`> element that contains the encrypted XML data.</span></span> <span data-ttu-id="1681c-107">Das <`EncryptedData`>-Element kann auch Unterelemente mit Informationen über die bei der Verschlüsselung verwendeten Schlüssel und Prozesse enthalten.</span><span class="sxs-lookup"><span data-stu-id="1681c-107">The <`EncryptedData`> element can contain sub elements that include information about the keys and processes used during encryption.</span></span>  <span data-ttu-id="1681c-108">XML-Verschlüsselung unterstützt, dass ein Dokument mehrere verschlüsselte Elemente enthält und dass ein Element mehrfach verschlüsselt ist.</span><span class="sxs-lookup"><span data-stu-id="1681c-108">XML Encryption allows a document to contain multiple encrypted elements and allows an element to be encrypted multiple times.</span></span>  <span data-ttu-id="1681c-109">Das Codebeispiel in dieser Vorgehensweise veranschaulicht das Erstellen eines <`EncryptedData`>-Elements zusammen mit weiteren Unterelementen, die Sie später bei der Entschlüsselung verwenden können.</span><span class="sxs-lookup"><span data-stu-id="1681c-109">The code example in this procedure shows you how to create an <`EncryptedData`> element along with several other sub elements that you can use later during decryption.</span></span>  
  
<span data-ttu-id="1681c-110">In diesem Beispiel wird ein XML-Element mithilfe zweier Schlüssel verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="1681c-110">This example encrypts an XML element using two keys.</span></span> <span data-ttu-id="1681c-111">Das Beispiel ruft Programm gesteuert ein Zertifikat ab und verwendet es, um ein XML-Element mithilfe der-Methode zu verschlüsseln <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> .</span><span class="sxs-lookup"><span data-stu-id="1681c-111">The example programmatically retrieves a certificate and uses it to encrypt an XML element using the <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> method.</span></span> <span data-ttu-id="1681c-112">Die <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A>-Methode erstellt intern einen separaten Sitzungsschlüssel und verwendet diesen, um das XML-Dokument zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="1681c-112">Internally, the <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> method creates a separate session key and uses it to encrypt the XML document.</span></span> <span data-ttu-id="1681c-113">Diese Methode verschlüsselt den Sitzungsschlüssel und speichert ihn mit dem verschlüsselten XML-Dokument in einem neuen <`EncryptedData`>-Element.</span><span class="sxs-lookup"><span data-stu-id="1681c-113">This method encrypts the session key and saves it along with the encrypted XML within a new <`EncryptedData`> element.</span></span>  

<span data-ttu-id="1681c-114">Um das XML-Element zu entschlüsseln, rufen Sie die- <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> Methode auf, die automatisch das X. 509-Zertifikat aus dem Speicher abruft und die erforderliche Entschlüsselung ausführt.</span><span class="sxs-lookup"><span data-stu-id="1681c-114">To decrypt the XML element, call the <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> method, which automatically retrieves the X.509 certificate from the store and performs the necessary decryption.</span></span>  <span data-ttu-id="1681c-115">Weitere Informationen zum Entschlüsseln eines XML-Elements, das mit dieser Vorgehensweise verschlüsselt wurde, finden Sie unter [Gewusst wie: Entschlüsseln von XML-Elementen mit X.509](how-to-decrypt-xml-elements-with-x-509-certificates.md)-Zertifikaten.</span><span class="sxs-lookup"><span data-stu-id="1681c-115">For more information about how to decrypt an XML element that was encrypted using this procedure, see [How to: Decrypt XML Elements with X.509 Certificates](how-to-decrypt-xml-elements-with-x-509-certificates.md).</span></span>  
  
<span data-ttu-id="1681c-116">Das Beispiel eignet sich für Situationen, in denen mehrere Anwendungen verschlüsselte Daten gemeinsam nutzen müssen, oder in denen eine Anwendung verschlüsselte Daten zwischen den Zeiten speichern muss, in denen sie ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1681c-116">This example is appropriate for situations where multiple applications need to share encrypted data or where an application needs to save encrypted data between the times that it runs.</span></span>  
  
### <a name="to-encrypt-an-xml-element-with-an-x509-certificate"></a><span data-ttu-id="1681c-117">So verschlüsseln Sie ein XML-Element mit einem X.509-Zertifikat</span><span class="sxs-lookup"><span data-stu-id="1681c-117">To encrypt an XML element with an X.509 certificate</span></span>  

<span data-ttu-id="1681c-118">Zum Ausführen dieses Beispiels müssen Sie ein Test Zertifikat erstellen und in einem Zertifikat Speicher speichern.</span><span class="sxs-lookup"><span data-stu-id="1681c-118">To run this example, you need to create a test certificate and save it in a certificate store.</span></span> <span data-ttu-id="1681c-119">Die Anweisungen für diese Aufgabe werden nur für das Windows- [Zertifikaterstellungs-Tool (Makecert.exe)](/windows/desktop/SecCrypto/makecert)bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="1681c-119">Instructions for that task are provided only for the Windows [Certificate Creation Tool (Makecert.exe)](/windows/desktop/SecCrypto/makecert).</span></span>

1. <span data-ttu-id="1681c-120">Verwenden Sie [Makecert.exe](/windows/desktop/SecCrypto/makecert) , um ein X. 509-Test Zertifikat zu generieren und im lokalen Benutzerspeicher zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="1681c-120">Use [Makecert.exe](/windows/desktop/SecCrypto/makecert) to generate a test X.509 certificate and place it in the local user store.</span></span> <span data-ttu-id="1681c-121">Sie müssen einen exportierbaren Austauschschlüssel generieren.</span><span class="sxs-lookup"><span data-stu-id="1681c-121">You must generate an exchange key and you must make the key exportable.</span></span> <span data-ttu-id="1681c-122">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="1681c-122">Run the following command:</span></span>  
  
    ```console  
    makecert -r -pe -n "CN=XML_ENC_TEST_CERT" -b 01/01/2020 -e 01/01/2025 -sky exchange -ss my  
    ```  
  
2. <span data-ttu-id="1681c-123">Erstellen Sie ein <xref:System.Security.Cryptography.X509Certificates.X509Store>-Objekt, und initialisieren Sie dieses, um den aktuellen Benutzerspeicher zu öffnen</span><span class="sxs-lookup"><span data-stu-id="1681c-123">Create an <xref:System.Security.Cryptography.X509Certificates.X509Store> object and initialize it to open the current user store.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#2)]
     [!code-vb[HowToEncryptXMLElementX509#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#2)]  
  
3. <span data-ttu-id="1681c-124">Öffnen Sie den Speicher im schreibgeschützten Modus.</span><span class="sxs-lookup"><span data-stu-id="1681c-124">Open the store in read-only mode.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#3)]
     [!code-vb[HowToEncryptXMLElementX509#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#3)]  
  
4. <span data-ttu-id="1681c-125">Initialisieren Sie eine <xref:System.Security.Cryptography.X509Certificates.X509Certificate2Collection> mit allen im Speicher enthaltenen Zertifikaten.</span><span class="sxs-lookup"><span data-stu-id="1681c-125">Initialize an <xref:System.Security.Cryptography.X509Certificates.X509Certificate2Collection> with all of the certificates in the store.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#4)]
     [!code-vb[HowToEncryptXMLElementX509#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#4)]  
  
5. <span data-ttu-id="1681c-126">Durchlaufen Sie die Zertifikate im Speicher, und suchen Sie nach dem Zertifikat mit dem entsprechenden Namen.</span><span class="sxs-lookup"><span data-stu-id="1681c-126">Enumerate through the certificates in the store and find the certificate with the appropriate name.</span></span>  <span data-ttu-id="1681c-127">In diesem Beispiel hat das Zertifikat den Namen `"CN=XML_ENC_TEST_CERT"`.</span><span class="sxs-lookup"><span data-stu-id="1681c-127">In this example, the certificate is named `"CN=XML_ENC_TEST_CERT"`.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#5)]
     [!code-vb[HowToEncryptXMLElementX509#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#5)]  
  
6. <span data-ttu-id="1681c-128">Schließen Sie den Speicher, nachdem Sie das Zertifikat gefunden haben.</span><span class="sxs-lookup"><span data-stu-id="1681c-128">Close the store after the certificate is located.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#6)]
     [!code-vb[HowToEncryptXMLElementX509#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#6)]  
  
7. <span data-ttu-id="1681c-129">Erstellen Sie ein <xref:System.Xml.XmlDocument>-Objekt, indem Sie eine XML-Datei von einem Datenträger laden.</span><span class="sxs-lookup"><span data-stu-id="1681c-129">Create an <xref:System.Xml.XmlDocument> object by loading an XML file from disk.</span></span>  <span data-ttu-id="1681c-130">Das <xref:System.Xml.XmlDocument>-Objekt enthält das zu verschlüsselnde XML-Element.</span><span class="sxs-lookup"><span data-stu-id="1681c-130">The <xref:System.Xml.XmlDocument> object contains the XML element to encrypt.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#7)]
     [!code-vb[HowToEncryptXMLElementX509#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#7)]  
  
8. <span data-ttu-id="1681c-131">Suchen Sie das angegebene Element im <xref:System.Xml.XmlDocument>-Objekt, und erstellen Sie ein neues <xref:System.Xml.XmlElement>-Objekt, das dem Element entspricht, das Sie verschlüsseln möchten.</span><span class="sxs-lookup"><span data-stu-id="1681c-131">Find the specified element in the <xref:System.Xml.XmlDocument> object and create a new <xref:System.Xml.XmlElement> object to represent the element you want to encrypt.</span></span>  <span data-ttu-id="1681c-132">In diesem Beispiel wird das `"creditcard"`-Element verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="1681c-132">In this example, the `"creditcard"` element is encrypted.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#8)]
     [!code-vb[HowToEncryptXMLElementX509#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#8)]  
  
9. <span data-ttu-id="1681c-133">Erstellen Sie eine neue Instanz der <xref:System.Security.Cryptography.Xml.EncryptedXml>-Klasse, und verwenden Sie diese, um das angegebene Element mit dem X.059-Zertifikat zu verschlüsseln .</span><span class="sxs-lookup"><span data-stu-id="1681c-133">Create a new instance of the <xref:System.Security.Cryptography.Xml.EncryptedXml> class and use it to encrypt the specified element using the X.509 certificate.</span></span>  <span data-ttu-id="1681c-134">Die <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A>-Methode gibt das verschlüsselte Element als ein <xref:System.Security.Cryptography.Xml.EncryptedData>-Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="1681c-134">The <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> method returns the encrypted element as an <xref:System.Security.Cryptography.Xml.EncryptedData> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#9)]
     [!code-vb[HowToEncryptXMLElementX509#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#9)]  
  
10. <span data-ttu-id="1681c-135">Ersetzen Sie das Element aus dem ursprünglichen <xref:System.Xml.XmlDocument>-Objekt durch das <xref:System.Security.Cryptography.Xml.EncryptedData>-Element.</span><span class="sxs-lookup"><span data-stu-id="1681c-135">Replace the element from the original <xref:System.Xml.XmlDocument> object with the <xref:System.Security.Cryptography.Xml.EncryptedData> element.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#10)]
     [!code-vb[HowToEncryptXMLElementX509#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#10)]  
  
11. <span data-ttu-id="1681c-136">Speichern Sie das <xref:System.Xml.XmlDocument>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="1681c-136">Save the <xref:System.Xml.XmlDocument> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#11)]
     [!code-vb[HowToEncryptXMLElementX509#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#11)]  
  
## <a name="example"></a><span data-ttu-id="1681c-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1681c-137">Example</span></span>  
 <span data-ttu-id="1681c-138">Für dieses Beispiel wird angenommen, dass eine Datei namens `"test.xml"` im selben Verzeichnis wie das kompilierte Programm vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="1681c-138">This example assumes that a file named `"test.xml"` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="1681c-139">Außerdem wird angenommen, dass `"test.xml"` ein `"creditcard"`-Element enthält.</span><span class="sxs-lookup"><span data-stu-id="1681c-139">It also assumes that `"test.xml"` contains a `"creditcard"` element.</span></span>  <span data-ttu-id="1681c-140">Sie können den folgenden XML-Code in eine Datei namens `test.xml` einfügen und mit diesem Beispiel verwenden.</span><span class="sxs-lookup"><span data-stu-id="1681c-140">You can place the following XML into a file called `test.xml` and use it with this example.</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="1681c-141">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="1681c-141">Compiling the Code</span></span>  
  
- <span data-ttu-id="1681c-142">Fügen Sie in einem Projekt, das .NET Framework als Ziel hat, einen Verweis auf ein `System.Security.dll` .</span><span class="sxs-lookup"><span data-stu-id="1681c-142">In a project that targets .NET Framework, include a reference to `System.Security.dll`.</span></span>

- <span data-ttu-id="1681c-143">Installieren Sie in einem Projekt, das .net Core oder .net 5 als Ziel hat, das nuget-Paket [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span><span class="sxs-lookup"><span data-stu-id="1681c-143">In a project that targets .NET Core or .NET 5, install NuGet package [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span></span>
  
- <span data-ttu-id="1681c-144">Fügen Sie die folgenden Namespaces hinzu: <xref:System.Xml>, <xref:System.Security.Cryptography> und <xref:System.Security.Cryptography.Xml>.</span><span class="sxs-lookup"><span data-stu-id="1681c-144">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="1681c-145">.NET-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="1681c-145">.NET Security</span></span>
  
<span data-ttu-id="1681c-146">Das in diesem Beispiel verwendete X.509-Zertifikat ist nur für Testzwecke vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="1681c-146">The X.509 certificate used in this example is for test purposes only.</span></span>  <span data-ttu-id="1681c-147">Anwendungen sollten ein X. 509-Zertifikat verwenden, das von einer vertrauenswürdigen Zertifizierungsstelle generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="1681c-147">Applications should use an X.509 certificate generated by a trusted certificate authority.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1681c-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1681c-148">See also</span></span>

- [<span data-ttu-id="1681c-149">Kryptografiemodell</span><span class="sxs-lookup"><span data-stu-id="1681c-149">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="1681c-150">Kryptografische Dienste</span><span class="sxs-lookup"><span data-stu-id="1681c-150">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="1681c-151">Plattformübergreifende Kryptografie</span><span class="sxs-lookup"><span data-stu-id="1681c-151">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="1681c-152">Vorgehensweise: Entschlüsseln von XML-Elementen mit X.509-Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="1681c-152">How to: Decrypt XML Elements with X.509 Certificates</span></span>](how-to-decrypt-xml-elements-with-x-509-certificates.md)
- [<span data-ttu-id="1681c-153">ASP.net Core Datenschutz</span><span class="sxs-lookup"><span data-stu-id="1681c-153">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
