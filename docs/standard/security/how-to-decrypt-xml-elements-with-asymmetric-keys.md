---
title: 'Vorgehensweise: Entschlüsseln von XML-Elementen mit asymmetrischen Schlüsseln'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- System.Security.Cryptography.RSACryptoServiceProvider class
- asymmetric keys
- System.Security.Cryptography.EncryptedXml class
- XML encryption
- decryption
ms.assetid: dd5de491-dafe-4b94-966d-99714b2e754a
ms.openlocfilehash: b3d5d91ff8cf268e4e7a1330ff596a97924dfe55
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290849"
---
# <a name="how-to-decrypt-xml-elements-with-asymmetric-keys"></a><span data-ttu-id="d258d-102">Vorgehensweise: Entschlüsseln von XML-Elementen mit asymmetrischen Schlüsseln</span><span class="sxs-lookup"><span data-stu-id="d258d-102">How to: Decrypt XML Elements with Asymmetric Keys</span></span>
<span data-ttu-id="d258d-103">Sie können die Klassen im <xref:System.Security.Cryptography.Xml>-Namespace verwenden, um ein Element in einem XML-Dokument zu verschlüsseln und zu entschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="d258d-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to encrypt and decrypt an element within an XML document.</span></span>  <span data-ttu-id="d258d-104">XML-Verschlüsselung ist ein gängiges Verfahren zum Austauschen oder Speichern von verschlüsselten XML-Daten, ohne sich Gedanken machen zu müssen, dass die Daten einfach gelesen werden können.</span><span class="sxs-lookup"><span data-stu-id="d258d-104">XML Encryption is a standard way to exchange or store encrypted XML data, without worrying about the data being easily read.</span></span>  <span data-ttu-id="d258d-105">Weitere Informationen zum XML-Verschlüsselungsstandard finden Sie unter World Wide Web Consortium (W3C) Empfehlungs [Syntax für XML-Signaturen und Verarbeitung](https://www.w3.org/TR/xmldsig-core/).</span><span class="sxs-lookup"><span data-stu-id="d258d-105">For more information about the XML Encryption standard, see the World Wide Web Consortium (W3C) recommendation [XML Signature Syntax and Processing](https://www.w3.org/TR/xmldsig-core/).</span></span>  
  
 <span data-ttu-id="d258d-106">Im Beispiel in dieser Prozedur wird ein XML-Element entschlüsselt, das mithilfe der in Gewusst [wie: Verschlüsseln von XML-Elementen mit asymmetrischen Schlüsseln](how-to-encrypt-xml-elements-with-asymmetric-keys.md)beschriebenen Methoden verschlüsselt wurde.</span><span class="sxs-lookup"><span data-stu-id="d258d-106">The example in this procedure decrypts an XML element that was encrypted using the methods described in [How to: Encrypt XML Elements with Asymmetric Keys](how-to-encrypt-xml-elements-with-asymmetric-keys.md).</span></span>  <span data-ttu-id="d258d-107">Er findet ein <`EncryptedData`>-Element, entschlüsselt das-Element und ersetzt dann das-Element durch das ursprüngliche Klartext-XML-Element.</span><span class="sxs-lookup"><span data-stu-id="d258d-107">It finds an <`EncryptedData`> element, decrypts the element, and then replaces the element with the original plaintext XML element.</span></span>  
  
 <span data-ttu-id="d258d-108">In diesem Beispiel wird ein XML-Element mithilfe zweier Schlüssel entschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="d258d-108">This example decrypts an XML element using two keys.</span></span>  <span data-ttu-id="d258d-109">Dabei wird ein zuvor generierter anderer RSA-Schlüssel aus einem Schlüssel Container abgerufen. Anschließend wird der RSA-Schlüssel verwendet, um einen Sitzungsschlüssel zu entschlüsseln, der im <`EncryptedKey`>-Element des <`EncryptedData`> Elements gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="d258d-109">It retrieves a previously generated RSA private key from a key container, and then uses the RSA key to decrypt a session key stored in the <`EncryptedKey`> element of the <`EncryptedData`> element.</span></span>  <span data-ttu-id="d258d-110">In dem Beispiel wird dann der Sitzungsschlüssel verwendet, um das XML-Element zu entschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="d258d-110">The example then uses the session key to decrypt the XML element.</span></span>  
  
 <span data-ttu-id="d258d-111">Das Beispiel eignet sich für Situationen, in denen mehrere Anwendungen verschlüsselte Daten gemeinsam nutzen müssen, oder in denen eine Anwendung verschlüsselte Daten zwischen den Zeiten speichern muss, in denen sie ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d258d-111">This example is appropriate for situations where multiple applications have to share encrypted data or where an application has to save encrypted data between the times that it runs.</span></span>  
  
### <a name="to-decrypt-an-xml-element-with-an-asymmetric-key"></a><span data-ttu-id="d258d-112">So entschlüsseln Sie ein XML-Element mit einem asymmetrischen Schlüsseln</span><span class="sxs-lookup"><span data-stu-id="d258d-112">To decrypt an XML element with an asymmetric key</span></span>  
  
1. <span data-ttu-id="d258d-113">Erstellen Sie ein <xref:System.Security.Cryptography.CspParameters>-Objekt, und geben Sie den Namen des Schlüsselcontainers an.</span><span class="sxs-lookup"><span data-stu-id="d258d-113">Create a <xref:System.Security.Cryptography.CspParameters> object and specify the name of the key container.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#2)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#2)]  
  
2. <span data-ttu-id="d258d-114">Rufen Sie einen zuvor generierten asymmetrischen Schlüssel aus dem Schlüsselcontainer mithilfe des <xref:System.Security.Cryptography.RSACryptoServiceProvider>-Objekts ab.</span><span class="sxs-lookup"><span data-stu-id="d258d-114">Retrieve a previously generated asymmetric key from the container using the <xref:System.Security.Cryptography.RSACryptoServiceProvider> object.</span></span>  <span data-ttu-id="d258d-115">Der Schlüssel wird automatisch aus dem Schlüsselcontainer abgerufen, wenn Sie das <xref:System.Security.Cryptography.CspParameters>-Objekt an den <xref:System.Security.Cryptography.RSACryptoServiceProvider>-Konstruktor übergeben.</span><span class="sxs-lookup"><span data-stu-id="d258d-115">The key is automatically retrieved from the key container when you pass the <xref:System.Security.Cryptography.CspParameters> object to the <xref:System.Security.Cryptography.RSACryptoServiceProvider> constructor.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#3)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#3)]  
  
3. <span data-ttu-id="d258d-116">Erstellen Sie ein neues <xref:System.Security.Cryptography.Xml.EncryptedXml>-Objekt, um das Dokument zu entschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="d258d-116">Create a new <xref:System.Security.Cryptography.Xml.EncryptedXml> object to decrypt the document.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#5)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#5)]  
  
4. <span data-ttu-id="d258d-117">Fügen Sie eine Schlüssel/Name-Zuordnung hinzu, um den RSA-Schlüssel dem Element im Dokument zuzuordnen, das entschlüsselt werden soll. </span><span class="sxs-lookup"><span data-stu-id="d258d-117">Add a key/name mapping to associate the RSA key with the element within the document that should be decrypted.</span></span>  <span data-ttu-id="d258d-118">Sie müssen für den Schlüssel den Namen verwenden, den Sie beim Verschlüsseln des Dokuments verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="d258d-118">You must use the same name for the key that you used when you encrypted the document.</span></span>  <span data-ttu-id="d258d-119">Beachten Sie, dass dieser Name nicht mit dem Namen identisch ist, mit dem der Schlüssel in dem Schlüsselcontainer identifiziert wird, der in Schritt 1 angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="d258d-119">Note that this name is separate from the name used to identify the key in the key container specified in step 1.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#6)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#6)]  
  
5. <span data-ttu-id="d258d-120">Ruft die- <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> Methode auf, um das <>-Element zu entschlüsseln `EncryptedData` .</span><span class="sxs-lookup"><span data-stu-id="d258d-120">Call the <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> method to decrypt the <`EncryptedData`> element.</span></span>  <span data-ttu-id="d258d-121">Diese Methode verwendet den RSA-Schlüssel, um den Sitzungsschlüssel zu entschlüsseln, und verwendet diesen dann automatisch, um das XML-Element zu entschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="d258d-121">This method uses the RSA key to decrypt the session key and automatically uses the session key to decrypt the XML element.</span></span>  <span data-ttu-id="d258d-122">Außerdem wird das <>- `EncryptedData` Element automatisch durch den ursprünglichen Klartext ersetzt.</span><span class="sxs-lookup"><span data-stu-id="d258d-122">It also automatically replaces the <`EncryptedData`> element with the original plaintext.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#7)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#7)]  
  
6. <span data-ttu-id="d258d-123">Speichern Sie das XML-Dokument.</span><span class="sxs-lookup"><span data-stu-id="d258d-123">Save the XML document.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#8)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="d258d-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d258d-124">Example</span></span>  
 <span data-ttu-id="d258d-125">Für dieses Beispiel wird angenommen, dass eine Datei namens `test.xml` im selben Verzeichnis wie das kompilierte Programm vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="d258d-125">This example assumes that a file named `test.xml` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="d258d-126">Außerdem wird davon ausgegangen, dass `test.xml` ein XML-Element enthält, das mithilfe der in Gewusst [wie: Verschlüsseln von XML-Elementen mit asymmetrischen Schlüsseln](how-to-encrypt-xml-elements-with-asymmetric-keys.md)beschriebenen Verfahren verschlüsselt wurde.</span><span class="sxs-lookup"><span data-stu-id="d258d-126">It also assumes that `test.xml` contains an XML element that was encrypted using the techniques described in [How to: Encrypt XML Elements with Asymmetric Keys](how-to-encrypt-xml-elements-with-asymmetric-keys.md).</span></span>  
  
 [!code-csharp[HowToDecryptXMLElementAsymmetric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#1)]
 [!code-vb[HowToDecryptXMLElementAsymmetric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d258d-127">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="d258d-127">Compiling the Code</span></span>  
  
- <span data-ttu-id="d258d-128">Um dieses Beispiel zu kompilieren, müssen Sie einen Verweis auf `System.Security.dll` einfügen.</span><span class="sxs-lookup"><span data-stu-id="d258d-128">To compile this example, you need to include a reference to `System.Security.dll`.</span></span>  
  
- <span data-ttu-id="d258d-129">Fügen Sie die folgenden Namespaces hinzu: <xref:System.Xml>, <xref:System.Security.Cryptography> und <xref:System.Security.Cryptography.Xml>.</span><span class="sxs-lookup"><span data-stu-id="d258d-129">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="d258d-130">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="d258d-130">.NET Framework Security</span></span>  
 <span data-ttu-id="d258d-131">Speichern Sie einen symmetrischen kryptografischen Schlüssel nie im Klartextformat, und übertragen Sie einen symmetrischen Schlüssel nie im Klartextformat zwischen Computern.</span><span class="sxs-lookup"><span data-stu-id="d258d-131">Never store a symmetric cryptographic key in plaintext or transfer a symmetric key between machines in plaintext.</span></span>  <span data-ttu-id="d258d-132">Außerdem sollten Sie den privaten Schlüssel eines asymmetrischen Schlüsselpaars niemals in Klartext speichern oder übertragen.</span><span class="sxs-lookup"><span data-stu-id="d258d-132">Additionally, never store or transfer the private key of an asymmetric key pair in plaintext.</span></span>  <span data-ttu-id="d258d-133">Weitere Informationen zu symmetrischen und asymmetrischen Kryptografieschlüsseln finden Sie unter [Erstellen von Schlüsseln für die Verschlüsselung und Entschlüsselung](generating-keys-for-encryption-and-decryption.md).</span><span class="sxs-lookup"><span data-stu-id="d258d-133">For more information about symmetric and asymmetric cryptographic keys, see [Generating Keys for Encryption and Decryption](generating-keys-for-encryption-and-decryption.md).</span></span>  
  
 <span data-ttu-id="d258d-134">Sie sollten einen Schlüssel niemals direkt in Ihren Quellcode einbetten.</span><span class="sxs-lookup"><span data-stu-id="d258d-134">Never embed a key directly into your source code.</span></span>  <span data-ttu-id="d258d-135">Eingebettete Schlüssel können problemlos aus einer Assembly gelesen werden, indem [Ildasm. exe (IL-Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md) verwendet oder die Assembly in einem Text-Editor wie Editor geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="d258d-135">Embedded keys can be easily read from an assembly by using [Ildasm.exe (IL Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md) or by opening the assembly in a text editor such as Notepad.</span></span>  
  
 <span data-ttu-id="d258d-136">Wenn Sie einen kryptografischen Schlüssel nicht mehr benötigen, entfernen Sie ihn aus dem Arbeitsspeicher, indem Sie jedes Byte auf 0 (null) festlegen oder indem Sie die <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A>-Methode der verwalteten Kryptografieklasse aufrufen.</span><span class="sxs-lookup"><span data-stu-id="d258d-136">When you are done using a cryptographic key, clear it from memory by setting each byte to zero or by calling the <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> method of the managed cryptography class.</span></span>  <span data-ttu-id="d258d-137">Kryptografische Schlüssel können manchmal von einem Debugger aus dem Arbeitsspeicher oder von einer Festplatte gelesen werden, falls der entsprechende Arbeitsspeicherbereich auf den Datenträger ausgelagert wurde.</span><span class="sxs-lookup"><span data-stu-id="d258d-137">Cryptographic keys can sometimes be read from memory by a debugger or read from a hard drive if the memory location is paged to disk.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d258d-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d258d-138">See also</span></span>

- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="d258d-139">Vorgehensweise: Entschlüsseln von XML-Elementen mit asymmetrischen Schlüsseln</span><span class="sxs-lookup"><span data-stu-id="d258d-139">How to: Encrypt XML Elements with Asymmetric Keys</span></span>](how-to-encrypt-xml-elements-with-asymmetric-keys.md)
