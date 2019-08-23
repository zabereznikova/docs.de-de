---
title: Verschlüsseln und Entschlüsseln von Zeichen folgen in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- encryption [Visual Basic], strings
- strings [Visual Basic], encrypting
- decryption [Visual Basic], strings
- strings [Visual Basic], decrypting
ms.assetid: 1f51e40a-2f88-43e2-a83e-28a0b5c0d6fd
ms.openlocfilehash: ee8691fedb537d1aa588eaac61624b445da64d1f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944431"
---
# <a name="walkthrough-encrypting-and-decrypting-strings-in-visual-basic"></a><span data-ttu-id="4d34d-102">Exemplarische Vorgehensweise: Verschlüsseln und Entschlüsseln von Zeichen folgen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4d34d-102">Walkthrough: Encrypting and Decrypting Strings in Visual Basic</span></span>
<span data-ttu-id="4d34d-103">In dieser exemplarischen Vorgehensweise erfahren Sie, <xref:System.Security.Cryptography.DESCryptoServiceProvider> wie Sie die-Klasse verwenden, um Zeichen folgen mithilfe der CSP-Version (kryptografischen Service Provider) des Triple Data<xref:System.Security.Cryptography.TripleDES>Encryption Standard-Algorithmus () zu verschlüsseln und zu entschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="4d34d-103">This walkthrough shows you how to use the <xref:System.Security.Cryptography.DESCryptoServiceProvider> class to encrypt and decrypt strings using the cryptographic service provider (CSP) version of the Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>) algorithm.</span></span> <span data-ttu-id="4d34d-104">Der erste Schritt besteht darin, eine einfache Wrapper Klasse zu erstellen, die den 3DES-Algorithmus kapselt und die verschlüsselten Daten als Base-64-codierte Zeichenfolge speichert.</span><span class="sxs-lookup"><span data-stu-id="4d34d-104">The first step is to create a simple wrapper class that encapsulates the 3DES algorithm and stores the encrypted data as a base-64 encoded string.</span></span> <span data-ttu-id="4d34d-105">Anschließend wird dieser Wrapper zum sicheren Speichern privater Benutzerdaten in einer öffentlich zugänglichen Textdatei verwendet.</span><span class="sxs-lookup"><span data-stu-id="4d34d-105">Then, that wrapper is used to securely store private user data in a publicly accessible text file.</span></span>  
  
 <span data-ttu-id="4d34d-106">Sie können die Verschlüsselung zum Schutz von Benutzer Geheimnissen (z. b. Kenn Wörter) und zum unlesbar von Anmelde Informationen durch nicht autorisierte Benutzer verwenden.</span><span class="sxs-lookup"><span data-stu-id="4d34d-106">You can use encryption to protect user secrets (for example, passwords) and to make credentials unreadable by unauthorized users.</span></span> <span data-ttu-id="4d34d-107">Dadurch kann die Identität eines autorisierten Benutzers vor dem Diebstahl geschützt werden, wodurch die Objekte des Benutzers geschützt werden und Nichtabstreitbarkeit gewährleistet ist.</span><span class="sxs-lookup"><span data-stu-id="4d34d-107">This can protect an authorized user's identity from being stolen, which protects the user's assets and provides non-repudiation.</span></span> <span data-ttu-id="4d34d-108">Mit der Verschlüsselung können auch die Daten eines Benutzers vor dem Zugriff durch nicht autorisierte Benutzer geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="4d34d-108">Encryption can also protect a user's data from being accessed by unauthorized users.</span></span>  
  
 <span data-ttu-id="4d34d-109">Weitere Informationen finden Sie unter [Kryptografiedienste](../../../../standard/security/cryptographic-services.md).</span><span class="sxs-lookup"><span data-stu-id="4d34d-109">For more information, see [Cryptographic Services](../../../../standard/security/cryptographic-services.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="4d34d-110">Die Rijndael-Algorithmen (jetzt als Advanced Encryption Standard [AES]) und 3DES-Algorithmen (Triple Data Encryption Standard) bieten mehr Sicherheit als die des, da sie Rechen intensiver sind.</span><span class="sxs-lookup"><span data-stu-id="4d34d-110">The Rijndael (now referred to as Advanced Encryption Standard [AES]) and Triple Data Encryption Standard (3DES) algorithms provide greater security than DES because they are more computationally intensive.</span></span> <span data-ttu-id="4d34d-111">Weitere Informationen finden Sie unter <xref:System.Security.Cryptography.DES> und <xref:System.Security.Cryptography.Rijndael>.</span><span class="sxs-lookup"><span data-stu-id="4d34d-111">For more information, see <xref:System.Security.Cryptography.DES> and <xref:System.Security.Cryptography.Rijndael>.</span></span>  
  
### <a name="to-create-the-encryption-wrapper"></a><span data-ttu-id="4d34d-112">So erstellen Sie den Verschlüsselungs Wrapper</span><span class="sxs-lookup"><span data-stu-id="4d34d-112">To create the encryption wrapper</span></span>  
  
1. <span data-ttu-id="4d34d-113">Erstellen Sie `Simple3Des` die-Klasse, um die Verschlüsselungs-und Entschlüsselungs Methoden zu kapseln.</span><span class="sxs-lookup"><span data-stu-id="4d34d-113">Create the `Simple3Des` class to encapsulate the encryption and decryption methods.</span></span>  
  
     [!code-vb[VbVbalrStrings#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#38)]  
  
2. <span data-ttu-id="4d34d-114">Fügen Sie am Anfang der Datei, die die `Simple3Des` -Klasse enthält, einen Import des Kryptografie-Namespace hinzu.</span><span class="sxs-lookup"><span data-stu-id="4d34d-114">Add an import of the cryptography namespace to the start of the file that contains the `Simple3Des` class.</span></span>  
  
     [!code-vb[VbVbalrStrings#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#77)]  
  
3. <span data-ttu-id="4d34d-115">Fügen Sie `Simple3Des` in der-Klasse ein privates Feld zum Speichern des 3DES-Kryptografiedienstanbieters hinzu.</span><span class="sxs-lookup"><span data-stu-id="4d34d-115">In the `Simple3Des` class, add a private field to store the 3DES cryptographic service provider.</span></span>  
  
     [!code-vb[VbVbalrStrings#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#39)]  
  
4. <span data-ttu-id="4d34d-116">Fügen Sie eine private Methode hinzu, mit der ein Bytearray mit einer angegebenen Länge aus dem Hashwert des angegebenen Schlüssels erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="4d34d-116">Add a private method that creates a byte array of a specified length from the hash of the specified key.</span></span>  
  
     [!code-vb[VbVbalrStrings#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#41)]  
  
5. <span data-ttu-id="4d34d-117">Fügen Sie einen Konstruktor hinzu, um den 3DES-Kryptografiedienstanbieter zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="4d34d-117">Add a constructor to initialize the 3DES cryptographic service provider.</span></span>  
  
     <span data-ttu-id="4d34d-118">Der `key` -Parameter steuert `EncryptData` die `DecryptData` -Methode und die-Methode.</span><span class="sxs-lookup"><span data-stu-id="4d34d-118">The `key` parameter controls the `EncryptData` and `DecryptData` methods.</span></span>  
  
     [!code-vb[VbVbalrStrings#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#40)]  
  
6. <span data-ttu-id="4d34d-119">Fügen Sie eine öffentliche Methode hinzu, die eine Zeichenfolge verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="4d34d-119">Add a public method that encrypts a string.</span></span>  
  
     [!code-vb[VbVbalrStrings#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#42)]  
  
7. <span data-ttu-id="4d34d-120">Fügen Sie eine öffentliche Methode hinzu, die eine Zeichenfolge entschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="4d34d-120">Add a public method that decrypts a string.</span></span>  
  
     [!code-vb[VbVbalrStrings#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#43)]  
  
     <span data-ttu-id="4d34d-121">Die Wrapper Klasse kann jetzt verwendet werden, um Benutzer Objekte zu schützen.</span><span class="sxs-lookup"><span data-stu-id="4d34d-121">The wrapper class can now be used to protect user assets.</span></span> <span data-ttu-id="4d34d-122">In diesem Beispiel wird es verwendet, um private Benutzerdaten sicher in einer öffentlich zugänglichen Textdatei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="4d34d-122">In this example, it is used to securely store private user data in a publicly accessible text file.</span></span>  
  
### <a name="to-test-the-encryption-wrapper"></a><span data-ttu-id="4d34d-123">So testen Sie den Verschlüsselungs Wrapper</span><span class="sxs-lookup"><span data-stu-id="4d34d-123">To test the encryption wrapper</span></span>  
  
1. <span data-ttu-id="4d34d-124">Fügen Sie in einer separaten Klasse eine Methode hinzu, die die- `EncryptData` Methode des Wrappers verwendet, um eine Zeichenfolge zu verschlüsseln und in den Ordner "eigene Dateien" des Benutzers zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="4d34d-124">In a separate class, add a method that uses the wrapper's `EncryptData` method to encrypt a string and write it to the user's My Documents folder.</span></span>  
  
     [!code-vb[VbVbalrStrings#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#78)]  
  
2. <span data-ttu-id="4d34d-125">Fügen Sie eine Methode hinzu, die die verschlüsselte Zeichenfolge aus dem Ordner "eigene Dateien" des Benutzers liest und die Zeichenfolge `DecryptData` mit der-Methode des Wrappers entschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="4d34d-125">Add a method that reads the encrypted string from the user's My Documents folder and decrypts the string with the wrapper's `DecryptData` method.</span></span>  
  
     [!code-vb[VbVbalrStrings#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#79)]  
  
3. <span data-ttu-id="4d34d-126">Fügen Sie Benutzeroberflächen Code hinzu, `TestEncoding` um `TestDecoding` die Methoden und aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="4d34d-126">Add user interface code to call the `TestEncoding` and `TestDecoding` methods.</span></span>  
  
4. <span data-ttu-id="4d34d-127">Führen Sie die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="4d34d-127">Run the application.</span></span>  
  
     <span data-ttu-id="4d34d-128">Beachten Sie beim Testen der Anwendung, dass die Daten nicht entschlüsselt werden, wenn Sie das falsche Kennwort angeben.</span><span class="sxs-lookup"><span data-stu-id="4d34d-128">When you test the application, notice that it will not decrypt the data if you provide the wrong password.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d34d-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4d34d-129">See also</span></span>

- <xref:System.Security.Cryptography>
- <xref:System.Security.Cryptography.DESCryptoServiceProvider>
- <xref:System.Security.Cryptography.DES>
- <xref:System.Security.Cryptography.TripleDES>
- <xref:System.Security.Cryptography.Rijndael>
- [<span data-ttu-id="4d34d-130">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="4d34d-130">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
