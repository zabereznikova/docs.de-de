---
title: 'Vorgehensweise: Entschlüsseln von XML-Elementen mit X.509-Zertifikaten'
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- System.Security.Cryptography.EncryptedXml class
- XML encryption
- System.Security.Cryptography.X509Certificate2 class
- decryption
- X.509 certificates
- certificates, X.509 certificates
ms.assetid: bd015722-d88d-408d-8ca8-e4e475c441ed
ms.openlocfilehash: 02a4a4ada6dcc242a96d630699797f2ea76987e3
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94820279"
---
# <a name="how-to-decrypt-xml-elements-with-x509-certificates"></a><span data-ttu-id="665fc-102">Vorgehensweise: Entschlüsseln von XML-Elementen mit X.509-Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="665fc-102">How to: Decrypt XML Elements with X.509 Certificates</span></span>

<span data-ttu-id="665fc-103">Sie können die Klassen im <xref:System.Security.Cryptography.Xml>-Namespace verwenden, um ein Element in einem XML-Dokument zu verschlüsseln und zu entschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="665fc-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to encrypt and decrypt an element within an XML document.</span></span>  <span data-ttu-id="665fc-104">XML-Verschlüsselung ist ein gängiges Verfahren zum Austauschen oder Speichern von verschlüsselten XML-Daten, ohne sich Gedanken machen zu müssen, dass die Daten einfach gelesen werden können.</span><span class="sxs-lookup"><span data-stu-id="665fc-104">XML Encryption is a standard way to exchange or store encrypted XML data, without worrying about the data being easily read.</span></span>  <span data-ttu-id="665fc-105">Weitere Informationen zum XML-Verschlüsselungsstandard finden Sie in der World Wide Web Consortium (W3C)-Spezifikation für die XML-Verschlüsselung unter <https://www.w3.org/TR/xmldsig-core/> .</span><span class="sxs-lookup"><span data-stu-id="665fc-105">For more information about the XML Encryption standard, see the World Wide Web Consortium (W3C) specification for XML Encryption located at <https://www.w3.org/TR/xmldsig-core/>.</span></span>  
  
 <span data-ttu-id="665fc-106">In diesem Beispiel wird ein XML-Element entschlüsselt, das mithilfe der in: Gewusst [wie: Verschlüsseln von XML-Elementen mit X. 509-Zertifikaten](how-to-encrypt-xml-elements-with-x-509-certificates.md)beschriebenen Methoden verschlüsselt wurde.</span><span class="sxs-lookup"><span data-stu-id="665fc-106">This example decrypts an XML element that was encrypted using the methods described in: [How to: Encrypt XML Elements with X.509 Certificates](how-to-encrypt-xml-elements-with-x-509-certificates.md).</span></span>  <span data-ttu-id="665fc-107">Er findet ein <`EncryptedData`>-Element, entschlüsselt das-Element und ersetzt dann das-Element durch das ursprüngliche Klartext-XML-Element.</span><span class="sxs-lookup"><span data-stu-id="665fc-107">It finds an <`EncryptedData`> element, decrypts the element, and then replaces the element with the original plaintext XML element.</span></span>  
  
<span data-ttu-id="665fc-108">Im Codebeispiel dieser Vorgehensweise wird ein XML-Element mithilfe eines X.059-Zertifikats entschlüsselt, das aus einem lokalen Zertifikatsspeicher des aktuellen Benutzerkontos stammt.</span><span class="sxs-lookup"><span data-stu-id="665fc-108">The code example in this procedure decrypts an XML element using an X.509 certificate from the local certificate store of the current user account.</span></span>  <span data-ttu-id="665fc-109">Im Beispiel wird die <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> -Methode verwendet, um automatisch das X. 509-Zertifikat abzurufen und einen Sitzungsschlüssel zu entschlüsseln, der im <`EncryptedKey`>-Element des <`EncryptedData`> Elements gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="665fc-109">The example uses the <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> method to automatically retrieve the X.509 certificate and decrypt a session key stored in the <`EncryptedKey`> element of the <`EncryptedData`> element.</span></span>  <span data-ttu-id="665fc-110">Die <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A>-Methode verwendet anschließend automatisch den Sitzungsschlüssel, um das XML-Element zu entschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="665fc-110">The <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> method then automatically uses the session key to decrypt the XML element.</span></span>  
  
<span data-ttu-id="665fc-111">Das Beispiel eignet sich für Situationen, in denen mehrere Anwendungen verschlüsselte Daten gemeinsam nutzen müssen, oder in denen eine Anwendung verschlüsselte Daten zwischen den Zeiten speichern muss, in denen sie ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="665fc-111">This example is appropriate for situations where multiple applications need to share encrypted data or where an application needs to save encrypted data between the times that it runs.</span></span>  
  
### <a name="to-decrypt-an-xml-element-with-an-x509-certificate"></a><span data-ttu-id="665fc-112">So entschlüsseln Sie ein XML-Element mit einem X.509-Zertifikat</span><span class="sxs-lookup"><span data-stu-id="665fc-112">To decrypt an XML element with an X.509 certificate</span></span>  
  
1. <span data-ttu-id="665fc-113">Erstellen Sie ein <xref:System.Xml.XmlDocument>-Objekt, indem Sie eine XML-Datei von einem Datenträger laden.</span><span class="sxs-lookup"><span data-stu-id="665fc-113">Create an <xref:System.Xml.XmlDocument> object by loading an XML file from disk.</span></span>  <span data-ttu-id="665fc-114">Das <xref:System.Xml.XmlDocument>-Objekt enthält das zu entschlüsselnde XML-Element.</span><span class="sxs-lookup"><span data-stu-id="665fc-114">The <xref:System.Xml.XmlDocument> object contains the XML element to decrypt.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementX509#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#2)]
     [!code-vb[HowToDecryptXMLElementX509#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#2)]  
  
2. <span data-ttu-id="665fc-115">Erstellen Sie ein neues <xref:System.Security.Cryptography.Xml.EncryptedXml>-Objekt, indem Sie das <xref:System.Xml.XmlDocument>-Objekt an den Konstruktor übergeben.</span><span class="sxs-lookup"><span data-stu-id="665fc-115">Create a new <xref:System.Security.Cryptography.Xml.EncryptedXml> object by passing the <xref:System.Xml.XmlDocument> object to the constructor.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementX509#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#3)]
     [!code-vb[HowToDecryptXMLElementX509#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#3)]  
  
3. <span data-ttu-id="665fc-116">Entschlüsseln Sie das XML-Dokument mit der <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="665fc-116">Decrypt the XML document using the <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> method.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementX509#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#4)]
     [!code-vb[HowToDecryptXMLElementX509#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#4)]  
  
4. <span data-ttu-id="665fc-117">Speichern Sie das <xref:System.Xml.XmlDocument>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="665fc-117">Save the <xref:System.Xml.XmlDocument> object.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementX509#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#5)]
     [!code-vb[HowToDecryptXMLElementX509#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="665fc-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="665fc-118">Example</span></span>

<span data-ttu-id="665fc-119">Für dieses Beispiel wird angenommen, dass eine Datei namens `"test.xml"` im selben Verzeichnis wie das kompilierte Programm vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="665fc-119">This example assumes that a file named `"test.xml"` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="665fc-120">Außerdem wird angenommen, dass `"test.xml"` ein `"creditcard"`-Element enthält.</span><span class="sxs-lookup"><span data-stu-id="665fc-120">It also assumes that `"test.xml"` contains a `"creditcard"` element.</span></span>  <span data-ttu-id="665fc-121">Sie können den folgenden XML-Code in eine Datei namens `test.xml` einfügen und mit diesem Beispiel verwenden.</span><span class="sxs-lookup"><span data-stu-id="665fc-121">You can place the following XML into a file called `test.xml` and use it with this example.</span></span>  
  
```xml  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
```  
  
[!code-csharp[HowToDecryptXMLElementX509#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#1)]
[!code-vb[HowToDecryptXMLElementX509#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="665fc-122">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="665fc-122">Compiling the Code</span></span>  
  
- <span data-ttu-id="665fc-123">Fügen Sie in einem Projekt, das .NET Framework als Ziel hat, einen Verweis auf ein `System.Security.dll` .</span><span class="sxs-lookup"><span data-stu-id="665fc-123">In a project that targets .NET Framework, include a reference to `System.Security.dll`.</span></span>

- <span data-ttu-id="665fc-124">Installieren Sie in einem Projekt, das .net Core oder .net 5 als Ziel hat, das nuget-Paket [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span><span class="sxs-lookup"><span data-stu-id="665fc-124">In a project that targets .NET Core or .NET 5, install NuGet package [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span></span>

- <span data-ttu-id="665fc-125">Fügen Sie die folgenden Namespaces hinzu: <xref:System.Xml>, <xref:System.Security.Cryptography> und <xref:System.Security.Cryptography.Xml>.</span><span class="sxs-lookup"><span data-stu-id="665fc-125">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="665fc-126">.NET-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="665fc-126">.NET Security</span></span>

<span data-ttu-id="665fc-127">Das in diesem Beispiel verwendete X.509-Zertifikat ist nur für Testzwecke vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="665fc-127">The X.509 certificate used in this example is for test purposes only.</span></span>  <span data-ttu-id="665fc-128">Anwendungen sollten ein X. 509-Zertifikat verwenden, das von einer vertrauenswürdigen Zertifizierungsstelle generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="665fc-128">Applications should use an X.509 certificate generated by a trusted certificate authority.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="665fc-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="665fc-129">See also</span></span>

- [<span data-ttu-id="665fc-130">Kryptografiemodell</span><span class="sxs-lookup"><span data-stu-id="665fc-130">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="665fc-131">Kryptografische Dienste</span><span class="sxs-lookup"><span data-stu-id="665fc-131">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="665fc-132">Plattformübergreifende Kryptografie</span><span class="sxs-lookup"><span data-stu-id="665fc-132">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="665fc-133">Vorgehensweise: Verschlüsseln von XML-Elementen mit X.509-Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="665fc-133">How to: Encrypt XML Elements with X.509 Certificates</span></span>](how-to-encrypt-xml-elements-with-x-509-certificates.md)
- [<span data-ttu-id="665fc-134">ASP.net Core Datenschutz</span><span class="sxs-lookup"><span data-stu-id="665fc-134">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
