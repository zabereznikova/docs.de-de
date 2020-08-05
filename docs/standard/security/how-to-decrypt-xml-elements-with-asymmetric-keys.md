---
title: 'Vorgehensweise: Entschlüsseln von XML-Elementen mit asymmetrischen Schlüsseln'
ms.date: 07/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- System.Security.Cryptography.RSA class
- asymmetric keys
- System.Security.Cryptography.EncryptedXml class
- XML encryption
- decryption
ms.assetid: dd5de491-dafe-4b94-966d-99714b2e754a
ms.openlocfilehash: 4a06628ddde0920133bfd74568786fbca6d5cf09
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556773"
---
# <a name="how-to-decrypt-xml-elements-with-asymmetric-keys"></a><span data-ttu-id="52bfd-102">Vorgehensweise: Entschlüsseln von XML-Elementen mit asymmetrischen Schlüsseln</span><span class="sxs-lookup"><span data-stu-id="52bfd-102">How to: Decrypt XML Elements with Asymmetric Keys</span></span>

<span data-ttu-id="52bfd-103">Sie können die Klassen im <xref:System.Security.Cryptography.Xml>-Namespace verwenden, um ein Element in einem XML-Dokument zu verschlüsseln und zu entschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="52bfd-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to encrypt and decrypt an element within an XML document.</span></span>  <span data-ttu-id="52bfd-104">XML-Verschlüsselung ist ein gängiges Verfahren zum Austauschen oder Speichern von verschlüsselten XML-Daten, ohne sich Gedanken machen zu müssen, dass die Daten einfach gelesen werden können.</span><span class="sxs-lookup"><span data-stu-id="52bfd-104">XML Encryption is a standard way to exchange or store encrypted XML data, without worrying about the data being easily read.</span></span>  <span data-ttu-id="52bfd-105">Weitere Informationen zum XML-Verschlüsselungsstandard finden Sie unter World Wide Web Consortium (W3C) Empfehlungs [Syntax für XML-Signaturen und Verarbeitung](https://www.w3.org/TR/xmldsig-core/).</span><span class="sxs-lookup"><span data-stu-id="52bfd-105">For more information about the XML Encryption standard, see the World Wide Web Consortium (W3C) recommendation [XML Signature Syntax and Processing](https://www.w3.org/TR/xmldsig-core/).</span></span>  

> [!NOTE]
> <span data-ttu-id="52bfd-106">Der Code in diesem Artikel gilt für Windows.</span><span class="sxs-lookup"><span data-stu-id="52bfd-106">The code in this article applies to Windows.</span></span>

<span data-ttu-id="52bfd-107">Im Beispiel in dieser Prozedur wird ein XML-Element entschlüsselt, das mithilfe der in Gewusst [wie: Verschlüsseln von XML-Elementen mit asymmetrischen Schlüsseln](how-to-encrypt-xml-elements-with-asymmetric-keys.md)beschriebenen Methoden verschlüsselt wurde.</span><span class="sxs-lookup"><span data-stu-id="52bfd-107">The example in this procedure decrypts an XML element that was encrypted using the methods described in [How to: Encrypt XML Elements with Asymmetric Keys](how-to-encrypt-xml-elements-with-asymmetric-keys.md).</span></span>  <span data-ttu-id="52bfd-108">Er findet ein <`EncryptedData`>-Element, entschlüsselt das-Element und ersetzt dann das-Element durch das ursprüngliche Klartext-XML-Element.</span><span class="sxs-lookup"><span data-stu-id="52bfd-108">It finds an <`EncryptedData`> element, decrypts the element, and then replaces the element with the original plaintext XML element.</span></span>  
  
<span data-ttu-id="52bfd-109">In diesem Beispiel wird ein XML-Element mithilfe zweier Schlüssel entschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="52bfd-109">This example decrypts an XML element using two keys.</span></span>  <span data-ttu-id="52bfd-110">Dabei wird ein zuvor generierter anderer RSA-Schlüssel aus einem Schlüssel Container abgerufen. Anschließend wird der RSA-Schlüssel verwendet, um einen Sitzungsschlüssel zu entschlüsseln, der im <`EncryptedKey`>-Element des <`EncryptedData`> Elements gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="52bfd-110">It retrieves a previously generated RSA private key from a key container, and then uses the RSA key to decrypt a session key stored in the <`EncryptedKey`> element of the <`EncryptedData`> element.</span></span>  <span data-ttu-id="52bfd-111">In dem Beispiel wird dann der Sitzungsschlüssel verwendet, um das XML-Element zu entschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="52bfd-111">The example then uses the session key to decrypt the XML element.</span></span>  
  
<span data-ttu-id="52bfd-112">Das Beispiel eignet sich für Situationen, in denen mehrere Anwendungen verschlüsselte Daten gemeinsam nutzen müssen, oder in denen eine Anwendung verschlüsselte Daten zwischen den Zeiten speichern muss, in denen sie ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="52bfd-112">This example is appropriate for situations where multiple applications have to share encrypted data or where an application has to save encrypted data between the times that it runs.</span></span>  
  
### <a name="to-decrypt-an-xml-element-with-an-asymmetric-key"></a><span data-ttu-id="52bfd-113">So entschlüsseln Sie ein XML-Element mit einem asymmetrischen Schlüsseln</span><span class="sxs-lookup"><span data-stu-id="52bfd-113">To decrypt an XML element with an asymmetric key</span></span>  
  
1. <span data-ttu-id="52bfd-114">Erstellen Sie ein <xref:System.Security.Cryptography.CspParameters>-Objekt, und geben Sie den Namen des Schlüsselcontainers an.</span><span class="sxs-lookup"><span data-stu-id="52bfd-114">Create a <xref:System.Security.Cryptography.CspParameters> object and specify the name of the key container.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#2)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#2)]  
  
2. <span data-ttu-id="52bfd-115">Rufen Sie einen zuvor generierten asymmetrischen Schlüssel aus dem Schlüsselcontainer mithilfe des <xref:System.Security.Cryptography.RSACryptoServiceProvider>-Objekts ab.</span><span class="sxs-lookup"><span data-stu-id="52bfd-115">Retrieve a previously generated asymmetric key from the container using the <xref:System.Security.Cryptography.RSACryptoServiceProvider> object.</span></span>  <span data-ttu-id="52bfd-116">Der Schlüssel wird automatisch aus dem Schlüsselcontainer abgerufen, wenn Sie das <xref:System.Security.Cryptography.CspParameters>-Objekt an den <xref:System.Security.Cryptography.RSACryptoServiceProvider>-Konstruktor übergeben.</span><span class="sxs-lookup"><span data-stu-id="52bfd-116">The key is automatically retrieved from the key container when you pass the <xref:System.Security.Cryptography.CspParameters> object to the <xref:System.Security.Cryptography.RSACryptoServiceProvider> constructor.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#3)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#3)]  
  
3. <span data-ttu-id="52bfd-117">Erstellen Sie ein neues <xref:System.Security.Cryptography.Xml.EncryptedXml>-Objekt, um das Dokument zu entschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="52bfd-117">Create a new <xref:System.Security.Cryptography.Xml.EncryptedXml> object to decrypt the document.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#5)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#5)]  
  
4. <span data-ttu-id="52bfd-118">Fügen Sie eine Schlüssel/Name-Zuordnung hinzu, um den RSA-Schlüssel dem Element im Dokument zuzuordnen, das entschlüsselt werden soll. </span><span class="sxs-lookup"><span data-stu-id="52bfd-118">Add a key/name mapping to associate the RSA key with the element within the document that should be decrypted.</span></span>  <span data-ttu-id="52bfd-119">Sie müssen für den Schlüssel den Namen verwenden, den Sie beim Verschlüsseln des Dokuments verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="52bfd-119">You must use the same name for the key that you used when you encrypted the document.</span></span>  <span data-ttu-id="52bfd-120">Beachten Sie, dass dieser Name nicht mit dem Namen identisch ist, mit dem der Schlüssel in dem Schlüsselcontainer identifiziert wird, der in Schritt 1 angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="52bfd-120">Note that this name is separate from the name used to identify the key in the key container specified in step 1.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#6)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#6)]  
  
5. <span data-ttu-id="52bfd-121">Ruft die- <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> Methode auf, um das <>-Element zu entschlüsseln `EncryptedData` .</span><span class="sxs-lookup"><span data-stu-id="52bfd-121">Call the <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> method to decrypt the <`EncryptedData`> element.</span></span>  <span data-ttu-id="52bfd-122">Diese Methode verwendet den RSA-Schlüssel, um den Sitzungsschlüssel zu entschlüsseln, und verwendet diesen dann automatisch, um das XML-Element zu entschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="52bfd-122">This method uses the RSA key to decrypt the session key and automatically uses the session key to decrypt the XML element.</span></span>  <span data-ttu-id="52bfd-123">Außerdem wird das <>- `EncryptedData` Element automatisch durch den ursprünglichen Klartext ersetzt.</span><span class="sxs-lookup"><span data-stu-id="52bfd-123">It also automatically replaces the <`EncryptedData`> element with the original plaintext.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#7)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#7)]  
  
6. <span data-ttu-id="52bfd-124">Speichern Sie das XML-Dokument.</span><span class="sxs-lookup"><span data-stu-id="52bfd-124">Save the XML document.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#8)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="52bfd-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="52bfd-125">Example</span></span>

<span data-ttu-id="52bfd-126">Für dieses Beispiel wird angenommen, dass eine Datei namens `test.xml` im selben Verzeichnis wie das kompilierte Programm vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="52bfd-126">This example assumes that a file named `test.xml` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="52bfd-127">Außerdem wird davon ausgegangen, dass `test.xml` ein XML-Element enthält, das mithilfe der in Gewusst [wie: Verschlüsseln von XML-Elementen mit asymmetrischen Schlüsseln](how-to-encrypt-xml-elements-with-asymmetric-keys.md)beschriebenen Verfahren verschlüsselt wurde.</span><span class="sxs-lookup"><span data-stu-id="52bfd-127">It also assumes that `test.xml` contains an XML element that was encrypted using the techniques described in [How to: Encrypt XML Elements with Asymmetric Keys](how-to-encrypt-xml-elements-with-asymmetric-keys.md).</span></span>  
  
[!code-csharp[HowToDecryptXMLElementAsymmetric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#1)]
[!code-vb[HowToDecryptXMLElementAsymmetric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="52bfd-128">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="52bfd-128">Compiling the Code</span></span>  
  
- <span data-ttu-id="52bfd-129">Fügen Sie in einem Projekt, das .NET Framework als Ziel hat, einen Verweis auf ein `System.Security.dll` .</span><span class="sxs-lookup"><span data-stu-id="52bfd-129">In a project that targets .NET Framework, include a reference to `System.Security.dll`.</span></span>

- <span data-ttu-id="52bfd-130">Installieren Sie in einem Projekt, das .net Core oder .net 5 als Ziel hat, das nuget-Paket [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span><span class="sxs-lookup"><span data-stu-id="52bfd-130">In a project that targets .NET Core or .NET 5, install NuGet package [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span></span>
  
- <span data-ttu-id="52bfd-131">Fügen Sie die folgenden Namespaces hinzu: <xref:System.Xml>, <xref:System.Security.Cryptography> und <xref:System.Security.Cryptography.Xml>.</span><span class="sxs-lookup"><span data-stu-id="52bfd-131">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="52bfd-132">.NET-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="52bfd-132">.NET Security</span></span>  

<span data-ttu-id="52bfd-133">Speichern Sie einen symmetrischen kryptografischen Schlüssel nie im Klartextformat, und übertragen Sie einen symmetrischen Schlüssel nie im Klartextformat zwischen Computern.</span><span class="sxs-lookup"><span data-stu-id="52bfd-133">Never store a symmetric cryptographic key in plaintext or transfer a symmetric key between machines in plaintext.</span></span>  <span data-ttu-id="52bfd-134">Außerdem sollten Sie den privaten Schlüssel eines asymmetrischen Schlüsselpaars niemals in Klartext speichern oder übertragen.</span><span class="sxs-lookup"><span data-stu-id="52bfd-134">Additionally, never store or transfer the private key of an asymmetric key pair in plaintext.</span></span>  <span data-ttu-id="52bfd-135">Weitere Informationen zu symmetrischen und asymmetrischen Kryptografieschlüsseln finden Sie unter [Erstellen von Schlüsseln für die Verschlüsselung und Entschlüsselung](generating-keys-for-encryption-and-decryption.md).</span><span class="sxs-lookup"><span data-stu-id="52bfd-135">For more information about symmetric and asymmetric cryptographic keys, see [Generating Keys for Encryption and Decryption](generating-keys-for-encryption-and-decryption.md).</span></span>  
  
 <span data-ttu-id="52bfd-136">Sie sollten einen Schlüssel niemals direkt in Ihren Quellcode einbetten.</span><span class="sxs-lookup"><span data-stu-id="52bfd-136">Never embed a key directly into your source code.</span></span>  <span data-ttu-id="52bfd-137">Eingebettete Schlüssel können problemlos aus einer Assembly gelesen werden, indem Sie [Ildasm.exe (IL-Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md) verwenden oder die Assembly in einem Text-Editor wie Notepad öffnen.</span><span class="sxs-lookup"><span data-stu-id="52bfd-137">Embedded keys can be easily read from an assembly by using [Ildasm.exe (IL Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md) or by opening the assembly in a text editor such as Notepad.</span></span>  
  
 <span data-ttu-id="52bfd-138">Wenn Sie einen kryptografischen Schlüssel nicht mehr benötigen, entfernen Sie ihn aus dem Arbeitsspeicher, indem Sie jedes Byte auf 0 (null) festlegen oder indem Sie die <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A>-Methode der verwalteten Kryptografieklasse aufrufen.</span><span class="sxs-lookup"><span data-stu-id="52bfd-138">When you are done using a cryptographic key, clear it from memory by setting each byte to zero or by calling the <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> method of the managed cryptography class.</span></span>  <span data-ttu-id="52bfd-139">Kryptografische Schlüssel können manchmal von einem Debugger aus dem Arbeitsspeicher oder von einer Festplatte gelesen werden, falls der entsprechende Arbeitsspeicherbereich auf den Datenträger ausgelagert wurde.</span><span class="sxs-lookup"><span data-stu-id="52bfd-139">Cryptographic keys can sometimes be read from memory by a debugger or read from a hard drive if the memory location is paged to disk.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52bfd-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="52bfd-140">See also</span></span>

- [<span data-ttu-id="52bfd-141">Kryptografiemodell</span><span class="sxs-lookup"><span data-stu-id="52bfd-141">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="52bfd-142">Kryptografische Dienste</span><span class="sxs-lookup"><span data-stu-id="52bfd-142">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="52bfd-143">Plattformübergreifende Kryptografie</span><span class="sxs-lookup"><span data-stu-id="52bfd-143">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="52bfd-144">Vorgehensweise: Entschlüsseln von XML-Elementen mit asymmetrischen Schlüsseln</span><span class="sxs-lookup"><span data-stu-id="52bfd-144">How to: Encrypt XML Elements with Asymmetric Keys</span></span>](how-to-encrypt-xml-elements-with-asymmetric-keys.md)
- [<span data-ttu-id="52bfd-145">ASP.net Core Datenschutz</span><span class="sxs-lookup"><span data-stu-id="52bfd-145">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
