---
title: 'Vorgehensweise: Verschlüsseln von XML-Elementen mit symmetrischen Schlüsseln'
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- AES algorithm
- cryptography [.NET], symmetric keys
- encryption [.NET], symmetric keys
- symmetric keys
- System.Security.Cryptography.EncryptedXml class
- System.Security.Cryptography.Aes class
- XML encryption
- Advanced Encryption Standard algorithm
ms.assetid: d8461a44-aa2c-4ef4-b3e4-ab7cbaaee1b5
ms.openlocfilehash: cfda1835a1390b025f2ee0509a91c59104a77ae9
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94820227"
---
# <a name="how-to-encrypt-xml-elements-with-symmetric-keys"></a><span data-ttu-id="c38c7-102">Vorgehensweise: Verschlüsseln von XML-Elementen mit symmetrischen Schlüsseln</span><span class="sxs-lookup"><span data-stu-id="c38c7-102">How to: Encrypt XML Elements with Symmetric Keys</span></span>

<span data-ttu-id="c38c7-103">Sie können die Klassen im <xref:System.Security.Cryptography.Xml>-Namespace verwenden, um ein Element in einem XML-Dokument zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="c38c7-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to encrypt an element within an XML document.</span></span>  <span data-ttu-id="c38c7-104">Die XML-Verschlüsselung ermöglicht Ihnen das Speichern oder Transportieren von vertraulichen XML-Dokumenten, ohne befürchten zu müssen, dass die Daten einfach gelesen werden können.</span><span class="sxs-lookup"><span data-stu-id="c38c7-104">XML Encryption allows you to store or transport sensitive XML, without worrying about the data being easily read.</span></span>  <span data-ttu-id="c38c7-105">Mit dieser Prozedur wird ein XML-Element mit dem Advanced Encryption Standard-Algorithmus (AES) verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="c38c7-105">This procedure encrypts an XML element using the Advanced Encryption Standard (AES) algorithm.</span></span>  
  
 <span data-ttu-id="c38c7-106">Informationen zum Entschlüsseln eines XML-Elements, das mit dieser Prozedur verschlüsselt wurde, finden Sie unter Gewusst [wie: Entschlüsseln von XML-Elementen mit symmetrischen Schlüsseln](how-to-decrypt-xml-elements-with-symmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="c38c7-106">For information about how to decrypt an XML element that was encrypted using this procedure, see [How to: Decrypt XML Elements with Symmetric Keys](how-to-decrypt-xml-elements-with-symmetric-keys.md).</span></span>  
  
 <span data-ttu-id="c38c7-107">Wenn Sie einen symmetrischen Algorithmus wie AES verwenden, um XML-Daten zu verschlüsseln, müssen Sie für das Verschlüsseln und Entschlüsseln der XML-Daten denselben Schlüssel verwenden.</span><span class="sxs-lookup"><span data-stu-id="c38c7-107">When you use a symmetric algorithm like AES to encrypt XML data, you must use the same key to encrypt and decrypt the XML data.</span></span>  <span data-ttu-id="c38c7-108">Für das Beispiel in dieser Vorgehensweise wird angenommen, dass das verschlüsselte XML-Element mit demselben Schlüssel entschlüsselt wird und dass sich die verschlüsselnden und die entschlüsselnden Beteiligten über den zu verwendenden Algorithmus und Schlüssel verständigt haben.</span><span class="sxs-lookup"><span data-stu-id="c38c7-108">The example in this procedure assumes that the encrypted XML will be decrypted using the same key, and that the encrypting and decrypting parties agree on the algorithm and key to use.</span></span>  <span data-ttu-id="c38c7-109">In diesem Beispiel wird der AES-Schlüssel weder im verschlüsselten XML-Element gespeichert noch dort verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="c38c7-109">This example does not store or encrypt the AES key within the encrypted XML.</span></span>  
  
 <span data-ttu-id="c38c7-110">Dieses Beispiel ist für Situationen geeignet, in denen eine einzelne Anwendung Daten auf Basis eines Sitzungsschlüssels, der sich im Arbeitsspeicher befindet, oder auf Basis eines starken kryptografischen Schlüssels verschlüsseln muss, der aus einem Kennwort abgeleitet wurde.</span><span class="sxs-lookup"><span data-stu-id="c38c7-110">This example is appropriate for situations where a single application needs to encrypt data based on a session key stored in memory, or based on a cryptographically strong key derived from a password.</span></span>  <span data-ttu-id="c38c7-111">Für Situationen, in denen zwei oder mehr Anwendungen verschlüsselte XML-Daten gemeinsam verwenden müssen, empfiehlt sich die Verwendung eines Verschlüsselungsschemas, dem ein asymmetrischer Algorithmus oder ein X.509-Zertifikat zugrunde liegt.</span><span class="sxs-lookup"><span data-stu-id="c38c7-111">For situations where two or more applications need to share encrypted XML data, consider using an encryption scheme based on an asymmetric algorithm or an X.509 certificate.</span></span>  
  
### <a name="to-encrypt-an-xml-element-with-a-symmetric-key"></a><span data-ttu-id="c38c7-112">So verschlüsseln Sie ein XML-Element mit einem symmetrischen Schlüssel</span><span class="sxs-lookup"><span data-stu-id="c38c7-112">To encrypt an XML element with a symmetric key</span></span>  
  
1. <span data-ttu-id="c38c7-113">Generieren Sie mit der <xref:System.Security.Cryptography.Aes>-Klasse einen symmetrischen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="c38c7-113">Generate a symmetric key using the <xref:System.Security.Cryptography.Aes> class.</span></span>  <span data-ttu-id="c38c7-114">Dieser Schlüssel wird dazu verwendet, das XML-Element zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="c38c7-114">This key will be used to encrypt the XML element.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#2)]
     [!code-vb[HowToEncryptXMLElementSymmetric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#2)]  
  
2. <span data-ttu-id="c38c7-115">Erstellen Sie ein <xref:System.Xml.XmlDocument>-Objekt, indem Sie eine XML-Datei von einem Datenträger laden.</span><span class="sxs-lookup"><span data-stu-id="c38c7-115">Create an <xref:System.Xml.XmlDocument> object by loading an XML file from disk.</span></span>  <span data-ttu-id="c38c7-116">Das <xref:System.Xml.XmlDocument>-Objekt enthält das zu verschlüsselnde XML-Element.</span><span class="sxs-lookup"><span data-stu-id="c38c7-116">The <xref:System.Xml.XmlDocument> object contains the XML element to encrypt.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#3)]
     [!code-vb[HowToEncryptXMLElementSymmetric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#3)]  
  
3. <span data-ttu-id="c38c7-117">Suchen Sie das angegebene Element im <xref:System.Xml.XmlDocument>-Objekt, und erstellen Sie ein neues <xref:System.Xml.XmlElement>-Objekt, das dem Element entspricht, das Sie verschlüsseln möchten.</span><span class="sxs-lookup"><span data-stu-id="c38c7-117">Find the specified element in the <xref:System.Xml.XmlDocument> object and create a new <xref:System.Xml.XmlElement> object to represent the element you want to encrypt.</span></span>  <span data-ttu-id="c38c7-118">In diesem Beispiel wird das `"creditcard"`-Element verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="c38c7-118">In this example, the `"creditcard"` element is encrypted.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#4)]
     [!code-vb[HowToEncryptXMLElementSymmetric#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#4)]  
  
4. <span data-ttu-id="c38c7-119">Erstellen Sie eine neue Instanz der <xref:System.Security.Cryptography.Xml.EncryptedXml>-Klasse, und verwenden Sie diese Instanz, um das <xref:System.Xml.XmlElement> mit dem symmetrischen Schlüssel zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="c38c7-119">Create a new instance of the <xref:System.Security.Cryptography.Xml.EncryptedXml> class and use it to encrypt the <xref:System.Xml.XmlElement> with the symmetric key.</span></span>  <span data-ttu-id="c38c7-120">Die <xref:System.Security.Cryptography.Xml.EncryptedXml.EncryptData%2A>-Methode gibt das verschlüsselte Element als Array von verschlüsselten Bytes zurück.</span><span class="sxs-lookup"><span data-stu-id="c38c7-120">The <xref:System.Security.Cryptography.Xml.EncryptedXml.EncryptData%2A> method returns the encrypted element as an array of encrypted bytes.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#5)]
     [!code-vb[HowToEncryptXMLElementSymmetric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#5)]  
  
5. <span data-ttu-id="c38c7-121">Erstellen Sie ein <xref:System.Security.Cryptography.Xml.EncryptedData>-Objekt, und weisen Sie ihm den URL-Bezeichner des XML-Verschlüsselungselements zu.</span><span class="sxs-lookup"><span data-stu-id="c38c7-121">Construct an <xref:System.Security.Cryptography.Xml.EncryptedData> object and populate it with the URL identifier of the XML Encryption element.</span></span>  <span data-ttu-id="c38c7-122">Dieser URL-Bezeichner teilt einem entschlüsselnden Teilnehmer mit, dass das XML-Dokument ein verschlüsseltes Element enthält.</span><span class="sxs-lookup"><span data-stu-id="c38c7-122">This URL identifier lets a decrypting party know that the XML contains an encrypted element.</span></span>  <span data-ttu-id="c38c7-123">Sie können das <xref:System.Security.Cryptography.Xml.EncryptedXml.XmlEncElementUrl>-Feld verwenden, um den URL-Bezeichner anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c38c7-123">You can use the <xref:System.Security.Cryptography.Xml.EncryptedXml.XmlEncElementUrl> field to specify the URL identifier.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#6)]
     [!code-vb[HowToEncryptXMLElementSymmetric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#6)]  
  
6. <span data-ttu-id="c38c7-124">Erstellen Sie ein <xref:System.Security.Cryptography.Xml.EncryptionMethod>-Objekt, das mit dem URL-Bezeichner des kryptografischen Algorithmus initialisiert wird, mit dem der Schlüssel generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="c38c7-124">Create an <xref:System.Security.Cryptography.Xml.EncryptionMethod> object that is initialized to the URL identifier of the cryptographic algorithm used to generate the key.</span></span>  <span data-ttu-id="c38c7-125">Übergeben Sie das <xref:System.Security.Cryptography.Xml.EncryptionMethod>-Objekt an die <xref:System.Security.Cryptography.Xml.EncryptedType.EncryptionMethod%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="c38c7-125">Pass the <xref:System.Security.Cryptography.Xml.EncryptionMethod> object to the <xref:System.Security.Cryptography.Xml.EncryptedType.EncryptionMethod%2A> property.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#7)]
     [!code-vb[HowToEncryptXMLElementSymmetric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#7)]  
  
7. <span data-ttu-id="c38c7-126">Fügen Sie die verschlüsselten Elementdaten dem <xref:System.Security.Cryptography.Xml.EncryptedData>-Objekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="c38c7-126">Add the encrypted element data to the <xref:System.Security.Cryptography.Xml.EncryptedData> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#8)]
     [!code-vb[HowToEncryptXMLElementSymmetric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#8)]  
  
8. <span data-ttu-id="c38c7-127">Ersetzen Sie das Element aus dem ursprünglichen <xref:System.Xml.XmlDocument>-Objekt durch das <xref:System.Security.Cryptography.Xml.EncryptedData>-Element.</span><span class="sxs-lookup"><span data-stu-id="c38c7-127">Replace the element from the original <xref:System.Xml.XmlDocument> object with the <xref:System.Security.Cryptography.Xml.EncryptedData> element.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#9)]
     [!code-vb[HowToEncryptXMLElementSymmetric#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#9)]  
  
## <a name="example"></a><span data-ttu-id="c38c7-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c38c7-128">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="c38c7-129">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="c38c7-129">Compiling the Code</span></span>  
  
- <span data-ttu-id="c38c7-130">Fügen Sie in einem Projekt, das .NET Framework als Ziel hat, einen Verweis auf ein `System.Security.dll` .</span><span class="sxs-lookup"><span data-stu-id="c38c7-130">In a project that targets .NET Framework, include a reference to `System.Security.dll`.</span></span>

- <span data-ttu-id="c38c7-131">Installieren Sie in einem Projekt, das .net Core oder .net 5 als Ziel hat, das nuget-Paket [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span><span class="sxs-lookup"><span data-stu-id="c38c7-131">In a project that targets .NET Core or .NET 5, install NuGet package [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span></span>
  
- <span data-ttu-id="c38c7-132">Fügen Sie die folgenden Namespaces hinzu: <xref:System.Xml>, <xref:System.Security.Cryptography> und <xref:System.Security.Cryptography.Xml>.</span><span class="sxs-lookup"><span data-stu-id="c38c7-132">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="c38c7-133">.NET-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="c38c7-133">.NET Security</span></span>

<span data-ttu-id="c38c7-134">Speichern Sie einen kryptografischen Schlüssel nie im Klartextformat, und übertragen Sie einen Schlüssel nie im Klartextformat zwischen Computern.</span><span class="sxs-lookup"><span data-stu-id="c38c7-134">Never store a cryptographic key in plaintext or transfer a key between machines in plaintext.</span></span>  <span data-ttu-id="c38c7-135">Verwenden Sie stattdessen einen sicheren Schlüsselcontainer, um kryptografische Schlüssel zu speichern.</span><span class="sxs-lookup"><span data-stu-id="c38c7-135">Instead, use a secure key container to store cryptographic keys.</span></span>  
  
<span data-ttu-id="c38c7-136">Wenn Sie einen kryptografischen Schlüssel nicht mehr benötigen, entfernen Sie ihn aus dem Arbeitsspeicher, indem Sie jedes Byte auf 0 (null) festlegen oder indem Sie die <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A>-Methode der verwalteten Kryptografieklasse aufrufen.</span><span class="sxs-lookup"><span data-stu-id="c38c7-136">When you are done using a cryptographic key, clear it from memory by setting each byte to zero or by calling the <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> method of the managed cryptography class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c38c7-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c38c7-137">See also</span></span>

- <span data-ttu-id="c38c7-138">[Kryptografiemodell](cryptography-model.md) : Beschreibt, wie Kryptografie in der Basisklassen Bibliothek implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="c38c7-138">[Cryptography Model](cryptography-model.md) - Describes how cryptography is implemented in the base class library.</span></span>
- [<span data-ttu-id="c38c7-139">Kryptografische Dienste</span><span class="sxs-lookup"><span data-stu-id="c38c7-139">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="c38c7-140">Plattformübergreifende Kryptografie</span><span class="sxs-lookup"><span data-stu-id="c38c7-140">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="c38c7-141">Vorgehensweise: Entschlüsseln von XML-Elementen mit symmetrischen Schlüsseln</span><span class="sxs-lookup"><span data-stu-id="c38c7-141">How to: Decrypt XML Elements with Symmetric Keys</span></span>](how-to-decrypt-xml-elements-with-symmetric-keys.md)
- [<span data-ttu-id="c38c7-142">ASP.net Core Datenschutz</span><span class="sxs-lookup"><span data-stu-id="c38c7-142">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
