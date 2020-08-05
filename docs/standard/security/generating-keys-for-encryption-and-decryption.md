---
title: Erzeugen von Schlüsseln für die Ver- und Entschlüsselung
description: Erfahren Sie, wie symmetrische und asymmetrische Schlüssel für die Verschlüsselung und Entschlüsselung in .NET erstellt und verwaltet werden.
ms.date: 07/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keys, encryption and decryption
- keys, asymmetric
- keys, symmetric
- encryption [.NET], keys
- symmetric keys
- asymmetric keys [.NET]
- cryptography [.NET], keys
ms.assetid: c197dfc9-a453-4226-898d-37a16638056e
ms.openlocfilehash: 7ce19dc465fb1fac22545398e0724e6b76dd7098
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556942"
---
# <a name="generating-keys-for-encryption-and-decryption"></a><span data-ttu-id="b09c3-103">Erzeugen von Schlüsseln für die Ver- und Entschlüsselung</span><span class="sxs-lookup"><span data-stu-id="b09c3-103">Generating Keys for Encryption and Decryption</span></span>
<span data-ttu-id="b09c3-104">Das Erstellen und Verwalten von Schlüsseln ist ein wichtiger Bestandteil des kryptografischen Prozesses.</span><span class="sxs-lookup"><span data-stu-id="b09c3-104">Creating and managing keys is an important part of the cryptographic process.</span></span> <span data-ttu-id="b09c3-105">Bei symmetrischen Algorithmen müssen ein Schlüssel und ein Initialisierungsvektor (IV) erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="b09c3-105">Symmetric algorithms require the creation of a key and an initialization vector (IV).</span></span> <span data-ttu-id="b09c3-106">Der Schlüssel muss vor Unbefugten, die Ihre Daten nicht entschlüsseln können sollen, geheim gehalten werden.</span><span class="sxs-lookup"><span data-stu-id="b09c3-106">The key must be kept secret from anyone who should not decrypt your data.</span></span> <span data-ttu-id="b09c3-107">Der IV muss nicht geheim sein, sollte aber für jede Sitzung geändert werden.</span><span class="sxs-lookup"><span data-stu-id="b09c3-107">The IV does not have to be secret, but should be changed for each session.</span></span> <span data-ttu-id="b09c3-108">Bei asymmetrischen Algorithmen müssen ein öffentlicher und ein privater Schlüssel erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="b09c3-108">Asymmetric algorithms require the creation of a public key and a private key.</span></span> <span data-ttu-id="b09c3-109">Der öffentliche Schlüssel kann allgemein zugänglich sein, während der private Schlüssel nur dem Teilnehmer bekannt sein darf, der die mit dem öffentlichen Schlüssel verschlüsselten Daten entschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="b09c3-109">The public key can be made public to anyone, while the private key must known only by the party who will decrypt the data encrypted with the public key.</span></span> <span data-ttu-id="b09c3-110">In diesem Abschnitt wird beschrieben, wie Schlüssel für symmetrische und asymmetrische Algorithmen erzeugt und verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="b09c3-110">This section describes how to generate and manage keys for both symmetric and asymmetric algorithms.</span></span>  
  
## <a name="symmetric-keys"></a><span data-ttu-id="b09c3-111">Symmetrische Schlüssel</span><span class="sxs-lookup"><span data-stu-id="b09c3-111">Symmetric Keys</span></span>  
 <span data-ttu-id="b09c3-112">Für die von .NET bereitgestellten symmetrischen Verschlüsselungs Klassen sind ein Schlüssel und ein neuer Initialisierungs Vektor (IV) erforderlich, um Daten zu verschlüsseln und zu entschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="b09c3-112">The symmetric encryption classes supplied by .NET require a key and a new initialization vector (IV) to encrypt and decrypt data.</span></span> <span data-ttu-id="b09c3-113">Wenn Sie eine neue Instanz einer der verwalteten symmetrischen Kryptografieklassen mithilfe der Parameter losen `Create()` -Methode erstellen, werden automatisch ein neuer Schlüssel und IV erstellt.</span><span class="sxs-lookup"><span data-stu-id="b09c3-113">Whenever you create a new instance of one of the managed symmetric cryptographic classes using the parameterless `Create()` method, a new key and IV are automatically created.</span></span> <span data-ttu-id="b09c3-114">Alle Benutzer, die zum Entschlüsseln der Daten berechtigt sind, müssen über den gleichen Schlüssel und IV verfügen und den gleichen Algorithmus verwenden.</span><span class="sxs-lookup"><span data-stu-id="b09c3-114">Anyone that you allow to decrypt your data must possess the same key and IV and use the same algorithm.</span></span> <span data-ttu-id="b09c3-115">Generell sollten für jede Sitzung ein neuer Schlüssel und IV erstellt und weder Schlüssel noch IV für eine spätere Sitzung gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="b09c3-115">Generally, a new key and IV should be created for every session, and neither the key nor IV should be stored for use in a later session.</span></span>  
  
 <span data-ttu-id="b09c3-116">Um den symmetrischen Schlüssel und IV der Gegenseite mitzuteilen, wird der symmetrische Schlüssel in der Regel asymmetrisch verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="b09c3-116">To communicate a symmetric key and IV to a remote party, you would usually encrypt the symmetric key by using asymmetric encryption.</span></span> <span data-ttu-id="b09c3-117">Das Senden des unverschlüsselten Schlüssels über ein nicht sicheres Netzwerk birgt ein großes Sicherheitsrisiko, da jeder, der den Schlüssel und den IV abfängt, die Daten entschlüsseln kann.</span><span class="sxs-lookup"><span data-stu-id="b09c3-117">Sending the key across an insecure network without encrypting it is unsafe, because anyone who intercepts the key and IV can then decrypt your data.</span></span>  
  
 <span data-ttu-id="b09c3-118">Das folgende Beispiel zeigt die Erstellung einer neuen Instanz der standardmäßigen Implementierungs Klasse für den- <xref:System.Security.Cryptography.Aes> Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="b09c3-118">The following example shows the creation of a new instance of the default implementation class for the <xref:System.Security.Cryptography.Aes> algorithm.</span></span>  
  
```vb  
Dim aes As Aes = Aes.Create()  
```  
  
```csharp  
Aes aes = Aes.Create();  
```  
  
 <span data-ttu-id="b09c3-119">Beim Ausführen des obigen Codes werden ein neuer Schlüssel und IV erzeugt und in die **Key** -Eigenschaft bzw. die **IV** -Eigenschaft aufgenommen.</span><span class="sxs-lookup"><span data-stu-id="b09c3-119">When the previous code is executed, a new key and IV are generated and placed in the **Key** and **IV** properties, respectively.</span></span>  
  
 <span data-ttu-id="b09c3-120">Manchmal müssen u. U. mehrere Schlüssel erzeugt werden.</span><span class="sxs-lookup"><span data-stu-id="b09c3-120">Sometimes you might need to generate multiple keys.</span></span> <span data-ttu-id="b09c3-121">In diesem Fall können Sie zuerst eine neue Instanz einer Klasse, durch die ein symmetrischer Algorithmus implementiert wird, erstellen und erzeugen dann durch den Aufruf der **GenerateKey** -Methode und der **GenerateIV** -Methode einen neuen Schlüssel und IV.</span><span class="sxs-lookup"><span data-stu-id="b09c3-121">In this situation, you can create a new instance of a class that implements a symmetric algorithm and then create a new key and IV by calling the **GenerateKey** and **GenerateIV** methods.</span></span> <span data-ttu-id="b09c3-122">Im folgenden Codebeispiel wird veranschaulicht, wie neue Schlüssel und IVS erstellt werden, nachdem eine neue Instanz der symmetrischen Kryptografieklasse erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="b09c3-122">The following code example illustrates how to create new keys and IVs after a new instance of the symmetric cryptographic class has been made.</span></span>  
  
```vb  
Dim aes As Aes = Aes.Create()  
aes.GenerateIV()  
aes.GenerateKey()  
```  
  
```csharp  
Aes aes = Aes.Create();  
aes.GenerateIV();  
aes.GenerateKey();  
```  
  
 <span data-ttu-id="b09c3-123">Wenn der vorangehende Code ausgeführt wird, werden ein Schlüssel und ein IV generiert, wenn die neue Instanz von **AES** erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="b09c3-123">When the preceding code is executed, a key and IV are generated when the new instance of **Aes** is made.</span></span> <span data-ttu-id="b09c3-124">Ein weiterer Schlüssel und ein weiterer IV werden beim Aufruf der **GenerateKey** -Methode und der **GenerateIV** -Methode erstellt.</span><span class="sxs-lookup"><span data-stu-id="b09c3-124">Another key and IV are created when the **GenerateKey** and **GenerateIV** methods are called.</span></span>
  
## <a name="asymmetric-keys"></a><span data-ttu-id="b09c3-125">Asymmetrische Schlüssel</span><span class="sxs-lookup"><span data-stu-id="b09c3-125">Asymmetric Keys</span></span>

 <span data-ttu-id="b09c3-126">.NET stellt die- <xref:System.Security.Cryptography.RSA> Klasse für die asymmetrische Verschlüsselung bereit.</span><span class="sxs-lookup"><span data-stu-id="b09c3-126">.NET provides the <xref:System.Security.Cryptography.RSA> class for asymmetric encryption.</span></span> <span data-ttu-id="b09c3-127">Diese Klasse erstellt ein öffentliches/privates Schlüsselpaar, wenn Sie die Parameter lose- `Create()` Methode verwenden, um eine neue-Instanz zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b09c3-127">This class creates a public/private key pair when you use the parameterless `Create()` method to create a new instance.</span></span> <span data-ttu-id="b09c3-128">Asymmetrische Schlüssel können entweder nur für eine Sitzung erzeugt oder gespeichert und für mehrere Sitzungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b09c3-128">Asymmetric keys can be either stored for use in multiple sessions or generated for one session only.</span></span> <span data-ttu-id="b09c3-129">Während der öffentliche Schlüssel öffentlich verfügbar sein kann, sollte der private Schlüssel streng geheim gehalten werden.</span><span class="sxs-lookup"><span data-stu-id="b09c3-129">While the public key can be made generally available, the private key should be closely guarded.</span></span>  
  
 <span data-ttu-id="b09c3-130">Bei jedem Erstellen einer neuen Instanz einer asymmetrischen Algorithmusklasse wird ein öffentliches/privates Schlüsselpaar erzeugt.</span><span class="sxs-lookup"><span data-stu-id="b09c3-130">A public/private key pair is generated whenever a new instance of an asymmetric algorithm class is created.</span></span> <span data-ttu-id="b09c3-131">Nachdem eine neue Instanz der-Klasse erstellt wurde, können die Schlüsselinformationen mit der-Methode extrahiert werden <xref:System.Security.Cryptography.RSA.ExportParameters%2A> , die eine-Struktur zurückgibt, die <xref:System.Security.Cryptography.RSAParameters> die Schlüsselinformationen enthält.</span><span class="sxs-lookup"><span data-stu-id="b09c3-131">After a new instance of the class is created, the key information can be extracted using the <xref:System.Security.Cryptography.RSA.ExportParameters%2A> method, which returns an <xref:System.Security.Cryptography.RSAParameters> structure that holds the key information.</span></span> <span data-ttu-id="b09c3-132">Die-Methode akzeptiert einen booleschen Wert, der angibt, ob nur die Informationen des öffentlichen Schlüssels oder die Informationen des öffentlichen Schlüssels und des privaten Schlüssels zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b09c3-132">The method accepts a Boolean value that indicates whether to return only the public key information or to return both the public-key and the private-key information.</span></span>

<span data-ttu-id="b09c3-133">Es gibt auch andere Methoden, mit denen Sie wichtige Informationen extrahieren können, wie z. b.:</span><span class="sxs-lookup"><span data-stu-id="b09c3-133">There are also other methods that let you extract key information, such as:</span></span>

* <xref:System.Security.Cryptography.RSA.ExportRSAPublicKey%2A?displayProperty=nameWithType>
* <xref:System.Security.Cryptography.RSA.ExportRSAPrivateKey%2A?displayProperty=nameWithType>
* <xref:System.Security.Cryptography.AsymmetricAlgorithm.ExportSubjectPublicKeyInfo%2A?displayProperty=nameWithType>
* <xref:System.Security.Cryptography.AsymmetricAlgorithm.ExportPkcs8PrivateKey%2A?displayProperty=nameWithType>
* <xref:System.Security.Cryptography.AsymmetricAlgorithm.ExportEncryptedPkcs8PrivateKey%2A?displayProperty=nameWithType>

<span data-ttu-id="b09c3-134">Eine **RSA** -Instanz kann mit dem Wert einer **RSAParameters** -Struktur initialisiert werden, indem die-Methode verwendet wird <xref:System.Security.Cryptography.RSA.ImportParameters%2A> .</span><span class="sxs-lookup"><span data-stu-id="b09c3-134">An **RSA** instance can be initialized to the value of an **RSAParameters** structure by using the <xref:System.Security.Cryptography.RSA.ImportParameters%2A> method.</span></span> <span data-ttu-id="b09c3-135">Oder erstellen Sie eine neue-Instanz, indem Sie die- <xref:System.Security.Cryptography.RSA.Create(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType> Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="b09c3-135">Or create a new instance by using the <xref:System.Security.Cryptography.RSA.Create(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="b09c3-136">Asymmetrische private Schlüssel sollten in keinem Fall in vollem Wortlaut oder in Klartext auf dem lokalen Computer gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="b09c3-136">Asymmetric private keys should never be stored verbatim or in plain text on the local computer.</span></span> <span data-ttu-id="b09c3-137">Wenn ein privater Schlüssel gespeichert werden muss, sollten Sie einen Schlüsselcontainer verwenden.</span><span class="sxs-lookup"><span data-stu-id="b09c3-137">If you need to store a private key, you should use a key container.</span></span> <span data-ttu-id="b09c3-138">Weitere Informationen zum Speichern eines privaten Schlüssels in einem Schlüssel Container finden Sie unter Gewusst [wie: Speichern von asymmetrischen Schlüsseln in einem Schlüssel Container](how-to-store-asymmetric-keys-in-a-key-container.md).</span><span class="sxs-lookup"><span data-stu-id="b09c3-138">For more information about how to store a private key in a key container, see [How to: Store Asymmetric Keys in a Key Container](how-to-store-asymmetric-keys-in-a-key-container.md).</span></span>  
  
 <span data-ttu-id="b09c3-139">Im folgenden Codebeispiel wird eine neue Instanz der **RSA** -Klasse erstellt, wodurch ein öffentliches/privates Schlüsselpaar erstellt und die Informationen des öffentlichen Schlüssels in einer **RSAParameters** -Struktur gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="b09c3-139">The following code example creates a new instance of the **RSA** class, creating a public/private key pair, and saves the public key information to an **RSAParameters** structure.</span></span>  
  
```vb  
'Generate a public/private key pair.  
Dim rsa as RSA = RSA.Create()  
'Save the public key information to an RSAParameters structure.  
Dim rsaKeyInfo As RSAParameters = rsa.ExportParameters(false)  
```  
  
```csharp  
//Generate a public/private key pair.  
RSA rsa = RSA.Create();  
//Save the public key information to an RSAParameters structure.  
RSAParameters rsaKeyInfo = rsa.ExportParameters(false);  
```  
  
## <a name="see-also"></a><span data-ttu-id="b09c3-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b09c3-140">See also</span></span>

- [<span data-ttu-id="b09c3-141">Verschlüsseln von Daten</span><span class="sxs-lookup"><span data-stu-id="b09c3-141">Encrypting Data</span></span>](encrypting-data.md)
- [<span data-ttu-id="b09c3-142">Entschlüsseln von Daten</span><span class="sxs-lookup"><span data-stu-id="b09c3-142">Decrypting Data</span></span>](decrypting-data.md)
- [<span data-ttu-id="b09c3-143">Kryptografische Dienste</span><span class="sxs-lookup"><span data-stu-id="b09c3-143">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="b09c3-144">Vorgehensweise: Speichern asymmetrischer Schlüssel in einem Schlüsselcontainer</span><span class="sxs-lookup"><span data-stu-id="b09c3-144">How to: Store Asymmetric Keys in a Key Container</span></span>](how-to-store-asymmetric-keys-in-a-key-container.md)
- [<span data-ttu-id="b09c3-145">Plattformübergreifende Kryptografie</span><span class="sxs-lookup"><span data-stu-id="b09c3-145">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="b09c3-146">ASP.net Core Datenschutz</span><span class="sxs-lookup"><span data-stu-id="b09c3-146">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
