---
title: Erzeugen von Schlüsseln für die Ver- und Entschlüsselung
description: Erfahren Sie, wie symmetrische und asymmetrische Schlüssel für die Verschlüsselung und Entschlüsselung in .NET erstellt und verwaltet werden.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keys, encryption and decryption
- keys, asymmetric
- keys, symmetric
- encryption [.NET Framework], keys
- symmetric keys
- asymmetric keys [.NET Framework]
- cryptography [.NET Framework], keys
ms.assetid: c197dfc9-a453-4226-898d-37a16638056e
ms.openlocfilehash: f8c3633d18e200037235502487d0d91d42083241
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2020
ms.locfileid: "84661808"
---
# <a name="generating-keys-for-encryption-and-decryption"></a><span data-ttu-id="816e3-103">Erzeugen von Schlüsseln für die Ver- und Entschlüsselung</span><span class="sxs-lookup"><span data-stu-id="816e3-103">Generating Keys for Encryption and Decryption</span></span>
<span data-ttu-id="816e3-104">Das Erstellen und Verwalten von Schlüsseln ist ein wichtiger Bestandteil des kryptografischen Prozesses.</span><span class="sxs-lookup"><span data-stu-id="816e3-104">Creating and managing keys is an important part of the cryptographic process.</span></span> <span data-ttu-id="816e3-105">Bei symmetrischen Algorithmen müssen ein Schlüssel und ein Initialisierungsvektor (IV) erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="816e3-105">Symmetric algorithms require the creation of a key and an initialization vector (IV).</span></span> <span data-ttu-id="816e3-106">Der Schlüssel muss vor Unbefugten, die Ihre Daten nicht entschlüsseln können sollen, geheim gehalten werden.</span><span class="sxs-lookup"><span data-stu-id="816e3-106">The key must be kept secret from anyone who should not decrypt your data.</span></span> <span data-ttu-id="816e3-107">Der IV muss nicht geheim sein, sollte aber für jede Sitzung geändert werden.</span><span class="sxs-lookup"><span data-stu-id="816e3-107">The IV does not have to be secret, but should be changed for each session.</span></span> <span data-ttu-id="816e3-108">Bei asymmetrischen Algorithmen müssen ein öffentlicher und ein privater Schlüssel erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="816e3-108">Asymmetric algorithms require the creation of a public key and a private key.</span></span> <span data-ttu-id="816e3-109">Der öffentliche Schlüssel kann allgemein zugänglich sein, während der private Schlüssel nur dem Teilnehmer bekannt sein darf, der die mit dem öffentlichen Schlüssel verschlüsselten Daten entschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="816e3-109">The public key can be made public to anyone, while the private key must known only by the party who will decrypt the data encrypted with the public key.</span></span> <span data-ttu-id="816e3-110">In diesem Abschnitt wird beschrieben, wie Schlüssel für symmetrische und asymmetrische Algorithmen erzeugt und verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="816e3-110">This section describes how to generate and manage keys for both symmetric and asymmetric algorithms.</span></span>  
  
## <a name="symmetric-keys"></a><span data-ttu-id="816e3-111">Symmetrische Schlüssel</span><span class="sxs-lookup"><span data-stu-id="816e3-111">Symmetric Keys</span></span>  
 <span data-ttu-id="816e3-112">Für die von .NET Framework bereitgestellten symmetrischen Verschlüsselungsklassen sind ein Schlüssel und ein neuer Initialisierungsvektor (IV) erforderlich, damit Daten verschlüsselt und entschlüsselt werden können.</span><span class="sxs-lookup"><span data-stu-id="816e3-112">The symmetric encryption classes supplied by the .NET Framework require a key and a new initialization vector (IV) to encrypt and decrypt data.</span></span> <span data-ttu-id="816e3-113">Jedes Mal, wenn Sie eine neue Instanz einer der verwalteten symmetrischen Kryptografieklassen mit dem Parameter losen Konstruktor erstellen, werden automatisch ein neuer Schlüssel und IV erstellt.</span><span class="sxs-lookup"><span data-stu-id="816e3-113">Whenever you create a new instance of one of the managed symmetric cryptographic classes using the parameterless constructor, a new key and IV are automatically created.</span></span> <span data-ttu-id="816e3-114">Alle Benutzer, die zum Entschlüsseln der Daten berechtigt sind, müssen über den gleichen Schlüssel und IV verfügen und den gleichen Algorithmus verwenden.</span><span class="sxs-lookup"><span data-stu-id="816e3-114">Anyone that you allow to decrypt your data must possess the same key and IV and use the same algorithm.</span></span> <span data-ttu-id="816e3-115">Generell sollten für jede Sitzung ein neuer Schlüssel und IV erstellt und weder Schlüssel noch IV für eine spätere Sitzung gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="816e3-115">Generally, a new key and IV should be created for every session, and neither the key nor IV should be stored for use in a later session.</span></span>  
  
 <span data-ttu-id="816e3-116">Um den symmetrischen Schlüssel und IV der Gegenseite mitzuteilen, wird der symmetrische Schlüssel in der Regel asymmetrisch verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="816e3-116">To communicate a symmetric key and IV to a remote party, you would usually encrypt the symmetric key by using asymmetric encryption.</span></span> <span data-ttu-id="816e3-117">Das Senden des unverschlüsselten Schlüssels über ein nicht sicheres Netzwerk birgt ein großes Sicherheitsrisiko, da jeder, der den Schlüssel und den IV abfängt, die Daten entschlüsseln kann.</span><span class="sxs-lookup"><span data-stu-id="816e3-117">Sending the key across an insecure network without encrypting it is unsafe, because anyone who intercepts the key and IV can then decrypt your data.</span></span> <span data-ttu-id="816e3-118">Weitere Informationen zum verschlüsselten Datenaustausch finden Sie unter [Erstellen eines kryptografischen Schemas](creating-a-cryptographic-scheme.md).</span><span class="sxs-lookup"><span data-stu-id="816e3-118">For more information about exchanging data by using encryption, see [Creating a Cryptographic Scheme](creating-a-cryptographic-scheme.md).</span></span>  
  
 <span data-ttu-id="816e3-119">Im folgenden Beispiel wird eine neue Instanz der <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider> -Klasse erstellt, durch die der TripleDES-Algorithmus implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="816e3-119">The following example shows the creation of a new instance of the <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider> class that implements the TripleDES algorithm.</span></span>  
  
```vb  
Dim tdes As TripleDESCryptoServiceProvider = new TripleDESCryptoServiceProvider()  
```  
  
```csharp  
TripleDESCryptoServiceProvider tdes = new TripleDESCryptoServiceProvider();  
```  
  
 <span data-ttu-id="816e3-120">Beim Ausführen des obigen Codes werden ein neuer Schlüssel und IV erzeugt und in die **Key** -Eigenschaft bzw. die **IV** -Eigenschaft aufgenommen.</span><span class="sxs-lookup"><span data-stu-id="816e3-120">When the previous code is executed, a new key and IV are generated and placed in the **Key** and **IV** properties, respectively.</span></span>  
  
 <span data-ttu-id="816e3-121">Manchmal müssen u. U. mehrere Schlüssel erzeugt werden.</span><span class="sxs-lookup"><span data-stu-id="816e3-121">Sometimes you might need to generate multiple keys.</span></span> <span data-ttu-id="816e3-122">In diesem Fall können Sie zuerst eine neue Instanz einer Klasse, durch die ein symmetrischer Algorithmus implementiert wird, erstellen und erzeugen dann durch den Aufruf der **GenerateKey** -Methode und der **GenerateIV** -Methode einen neuen Schlüssel und IV.</span><span class="sxs-lookup"><span data-stu-id="816e3-122">In this situation, you can create a new instance of a class that implements a symmetric algorithm and then create a new key and IV by calling the **GenerateKey** and **GenerateIV** methods.</span></span> <span data-ttu-id="816e3-123">Im folgenden Codebeispiel wird veranschaulicht, wie neue Schlüssel und IVS erstellt werden, nachdem eine neue Instanz der symmetrischen Kryptografieklasse erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="816e3-123">The following code example illustrates how to create new keys and IVs after a new instance of the symmetric cryptographic class has been made.</span></span>  
  
```vb  
Dim tdes As TripleDESCryptoServiceProvider = new TripleDESCryptoServiceProvider()  
tdes.GenerateIV()  
tdes.GenerateKey()  
```  
  
```csharp  
TripleDESCryptoServiceProvider tdes = new TripleDESCryptoServiceProvider();  
tdes.GenerateIV();  
tdes.GenerateKey();  
```  
  
 <span data-ttu-id="816e3-124">Beim Ausführen des obigen Codes werden beim Erstellen der neuen **TripleDESCryptoServiceProvider** -Instanz ein Schlüssel und IV erzeugt.</span><span class="sxs-lookup"><span data-stu-id="816e3-124">When the previous code is executed, a key and IV are generated when the new instance of **TripleDESCryptoServiceProvider** is made.</span></span> <span data-ttu-id="816e3-125">Ein weiterer Schlüssel und ein weiterer IV werden beim Aufruf der **GenerateKey** -Methode und der **GenerateIV** -Methode erstellt.</span><span class="sxs-lookup"><span data-stu-id="816e3-125">Another key and IV are created when the **GenerateKey** and **GenerateIV** methods are called.</span></span>  
  
## <a name="asymmetric-keys"></a><span data-ttu-id="816e3-126">Asymmetrische Schlüssel</span><span class="sxs-lookup"><span data-stu-id="816e3-126">Asymmetric Keys</span></span>  
 <span data-ttu-id="816e3-127">.NET Framework stellt die Klassen <xref:System.Security.Cryptography.RSACryptoServiceProvider> und <xref:System.Security.Cryptography.DSACryptoServiceProvider> für asymmetrische Verschlüsselung bereit.</span><span class="sxs-lookup"><span data-stu-id="816e3-127">The .NET Framework provides the <xref:System.Security.Cryptography.RSACryptoServiceProvider> and <xref:System.Security.Cryptography.DSACryptoServiceProvider> classes for asymmetric encryption.</span></span> <span data-ttu-id="816e3-128">Diese Klassen erstellen ein öffentliches/privates Schlüsselpaar, wenn Sie den Parameter losen Konstruktor verwenden, um eine neue Instanz zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="816e3-128">These classes create a public/private key pair when you use the parameterless constructor to create a new instance.</span></span> <span data-ttu-id="816e3-129">Asymmetrische Schlüssel können entweder nur für eine Sitzung erzeugt oder gespeichert und für mehrere Sitzungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="816e3-129">Asymmetric keys can be either stored for use in multiple sessions or generated for one session only.</span></span> <span data-ttu-id="816e3-130">Während der öffentliche Schlüssel öffentlich verfügbar sein kann, sollte der private Schlüssel streng geheim gehalten werden.</span><span class="sxs-lookup"><span data-stu-id="816e3-130">While the public key can be made generally available, the private key should be closely guarded.</span></span>  
  
 <span data-ttu-id="816e3-131">Bei jedem Erstellen einer neuen Instanz einer asymmetrischen Algorithmusklasse wird ein öffentliches/privates Schlüsselpaar erzeugt.</span><span class="sxs-lookup"><span data-stu-id="816e3-131">A public/private key pair is generated whenever a new instance of an asymmetric algorithm class is created.</span></span> <span data-ttu-id="816e3-132">Nachdem eine neue Instanz der Klasse erstellt worden ist, können die Schlüsselinformationen mit einer der folgenden beiden Methoden extrahiert werden:</span><span class="sxs-lookup"><span data-stu-id="816e3-132">After a new instance of the class is created, the key information can be extracted using one of two methods:</span></span>  
  
- <span data-ttu-id="816e3-133">mit der <xref:System.Security.Cryptography.RSA.ToXmlString%2A> -Methode, die eine XML-Darstellung der Schlüsselinformationen zurückgibt;</span><span class="sxs-lookup"><span data-stu-id="816e3-133">The <xref:System.Security.Cryptography.RSA.ToXmlString%2A> method, which returns an XML representation of the key information.</span></span>  
  
- <span data-ttu-id="816e3-134">mit der <xref:System.Security.Cryptography.RSACryptoServiceProvider.ExportParameters%2A> -Methode, die eine <xref:System.Security.Cryptography.RSAParameters> -Struktur mit den Schlüsselinformationen zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="816e3-134">The <xref:System.Security.Cryptography.RSACryptoServiceProvider.ExportParameters%2A> method, which returns an <xref:System.Security.Cryptography.RSAParameters> structure that holds the key information.</span></span>  
  
 <span data-ttu-id="816e3-135">Bei beiden Methoden wird ein boolescher Wert akzeptiert, der angibt, ob nur die Informationen des öffentlichen Schlüssels oder die Informationen beider Schlüssel (öffentlich und privat) zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="816e3-135">Both methods accept a Boolean value that indicates whether to return only the public key information or to return both the public-key and the private-key information.</span></span> <span data-ttu-id="816e3-136">Eine **RSACryptoServiceProvider** -Klasse kann mit dem Wert einer **RSAParameters** -Struktur initialisiert werden, indem die <xref:System.Security.Cryptography.RSACryptoServiceProvider.ImportParameters%2A> -Methode verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="816e3-136">An **RSACryptoServiceProvider** class can be initialized to the value of an **RSAParameters** structure by using the <xref:System.Security.Cryptography.RSACryptoServiceProvider.ImportParameters%2A> method.</span></span>  
  
 <span data-ttu-id="816e3-137">Asymmetrische private Schlüssel sollten in keinem Fall in vollem Wortlaut oder in Klartext auf dem lokalen Computer gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="816e3-137">Asymmetric private keys should never be stored verbatim or in plain text on the local computer.</span></span> <span data-ttu-id="816e3-138">Wenn ein privater Schlüssel gespeichert werden muss, sollten Sie einen Schlüsselcontainer verwenden.</span><span class="sxs-lookup"><span data-stu-id="816e3-138">If you need to store a private key, you should use a key container.</span></span> <span data-ttu-id="816e3-139">Weitere Informationen zum Speichern eines privaten Schlüssels in einem Schlüsselcontainer finden Sie unter [How to: Store Asymmetric Keys in a Key Container](how-to-store-asymmetric-keys-in-a-key-container.md).</span><span class="sxs-lookup"><span data-stu-id="816e3-139">For more on how to store a private key in a key container, see [How to: Store Asymmetric Keys in a Key Container](how-to-store-asymmetric-keys-in-a-key-container.md).</span></span>  
  
 <span data-ttu-id="816e3-140">Im folgenden Codebeispiel wird eine neue Instanz der **RSACryptoServiceProvider** -Klasse erstellt, wodurch ein öffentliches/privates Schlüsselpaar erzeugt wird. Dann werden die Informationen des öffentlichen Schlüssels in einer **RSAParameters-** Struktur gespeichert.</span><span class="sxs-lookup"><span data-stu-id="816e3-140">The following code example creates a new instance of the **RSACryptoServiceProvider** class, creating a public/private key pair, and saves the public key information to an **RSAParameters** structure.</span></span>  
  
```vb  
'Generate a public/private key pair.  
Dim rsa as RSACryptoServiceProvider = new RSACryptoServiceProvider()  
'Save the public key information to an RSAParameters structure.  
Dim rsaKeyInfo As RSAParameters = rsa.ExportParameters(false)  
```  
  
```csharp  
//Generate a public/private key pair.  
RSACryptoServiceProvider rsa = new RSACryptoServiceProvider();  
//Save the public key information to an RSAParameters structure.  
RSAParameters rsaKeyInfo = rsa.ExportParameters(false);  
```  
  
## <a name="see-also"></a><span data-ttu-id="816e3-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="816e3-141">See also</span></span>

- [<span data-ttu-id="816e3-142">Verschlüsseln von Daten</span><span class="sxs-lookup"><span data-stu-id="816e3-142">Encrypting Data</span></span>](encrypting-data.md)
- [<span data-ttu-id="816e3-143">Entschlüsseln von Daten</span><span class="sxs-lookup"><span data-stu-id="816e3-143">Decrypting Data</span></span>](decrypting-data.md)
- [<span data-ttu-id="816e3-144">Kryptografiedienste</span><span class="sxs-lookup"><span data-stu-id="816e3-144">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="816e3-145">Vorgehensweise: Speichern asymmetrischer Schlüssel in einem Schlüsselcontainer</span><span class="sxs-lookup"><span data-stu-id="816e3-145">How to: Store Asymmetric Keys in a Key Container</span></span>](how-to-store-asymmetric-keys-in-a-key-container.md)
