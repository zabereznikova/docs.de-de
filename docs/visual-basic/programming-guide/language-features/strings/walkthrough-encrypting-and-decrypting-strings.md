---
title: Verschlüsseln und Entschlüsseln von Zeichenfolgen in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- encryption [Visual Basic], strings
- strings [Visual Basic], encrypting
- decryption [Visual Basic], strings
- strings [Visual Basic], decrypting
ms.assetid: 1f51e40a-2f88-43e2-a83e-28a0b5c0d6fd
ms.openlocfilehash: 96e56ab315a739fef9d5499b076a077f5294f39e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651222"
---
# <a name="walkthrough-encrypting-and-decrypting-strings-in-visual-basic"></a><span data-ttu-id="eb690-102">Exemplarische Vorgehensweise: Verschlüsseln und Entschlüsseln von Zeichenfolgen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="eb690-102">Walkthrough: Encrypting and Decrypting Strings in Visual Basic</span></span>
<span data-ttu-id="eb690-103">Diese exemplarische Vorgehensweise veranschaulicht das Verwenden der <xref:System.Security.Cryptography.DESCryptoServiceProvider> Klasse zum Verschlüsseln und Entschlüsseln von Zeichenfolgen mithilfe von cryptographic Service Provider (CSP)-Version von Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>) Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="eb690-103">This walkthrough shows you how to use the <xref:System.Security.Cryptography.DESCryptoServiceProvider> class to encrypt and decrypt strings using the cryptographic service provider (CSP) version of the Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>) algorithm.</span></span> <span data-ttu-id="eb690-104">Der erste Schritt ist zum Erstellen einer einfachen Wrapperklasse, die den 3DES-Algorithmus kapselt und speichert die verschlüsselten Daten als Base64-codierte Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="eb690-104">The first step is to create a simple wrapper class that encapsulates the 3DES algorithm and stores the encrypted data as a base-64 encoded string.</span></span> <span data-ttu-id="eb690-105">Anschließend wird dieser Wrapper verwendet, um private Benutzerdaten in einem öffentlich zugänglichen Textdatei sicher zu speichern.</span><span class="sxs-lookup"><span data-stu-id="eb690-105">Then, that wrapper is used to securely store private user data in a publicly accessible text file.</span></span>  
  
 <span data-ttu-id="eb690-106">Sie können Verschlüsselung verwenden, um vertrauliche Benutzerdaten (z. B. Kennwörter) zu schützen und um Anmeldeinformationen durch nicht autorisierte Benutzer nicht lesbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="eb690-106">You can use encryption to protect user secrets (for example, passwords) and to make credentials unreadable by unauthorized users.</span></span> <span data-ttu-id="eb690-107">Dies kann ein autorisierter Benutzer Identität gestohlen werden, schützen, die des Benutzers Bestand schützt und Nachweisbarkeit enthält.</span><span class="sxs-lookup"><span data-stu-id="eb690-107">This can protect an authorized user's identity from being stolen, which protects the user's assets and provides non-repudiation.</span></span> <span data-ttu-id="eb690-108">Verschlüsselung kann auch verhindern, dass Daten eines Benutzers durch nicht autorisierte Benutzer zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="eb690-108">Encryption can also protect a user's data from being accessed by unauthorized users.</span></span>  
  
 <span data-ttu-id="eb690-109">Weitere Informationen finden Sie unter [Kryptografiedienste](../../../../standard/security/cryptographic-services.md).</span><span class="sxs-lookup"><span data-stu-id="eb690-109">For more information, see [Cryptographic Services](../../../../standard/security/cryptographic-services.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="eb690-110">Die Rijndael (jetzt als Advanced Encryption Standard [AES] bezeichnet) und die Triple Data Encryption Standard (3DES) Algorithmen bieten mehr Sicherheit als DES, da sie weitere sind zur Ausführung rechenintensiver.</span><span class="sxs-lookup"><span data-stu-id="eb690-110">The Rijndael (now referred to as Advanced Encryption Standard [AES]) and Triple Data Encryption Standard (3DES) algorithms provide greater security than DES because they are more computationally intensive.</span></span> <span data-ttu-id="eb690-111">Weitere Informationen finden Sie unter <xref:System.Security.Cryptography.DES> und <xref:System.Security.Cryptography.Rijndael>.</span><span class="sxs-lookup"><span data-stu-id="eb690-111">For more information, see <xref:System.Security.Cryptography.DES> and <xref:System.Security.Cryptography.Rijndael>.</span></span>  
  
### <a name="to-create-the-encryption-wrapper"></a><span data-ttu-id="eb690-112">Zum Erstellen des Verschlüsselungswrapper</span><span class="sxs-lookup"><span data-stu-id="eb690-112">To create the encryption wrapper</span></span>  
  
1.  <span data-ttu-id="eb690-113">Erstellen der `Simple3Des` Klasse, um die Verschlüsselung und Entschlüsselung Methoden zu kapseln.</span><span class="sxs-lookup"><span data-stu-id="eb690-113">Create the `Simple3Des` class to encapsulate the encryption and decryption methods.</span></span>  
  
     [!code-vb[VbVbalrStrings#38](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_1.vb)]  
  
2.  <span data-ttu-id="eb690-114">Fügen Sie einen Import eines Kryptografie-Namespace am Anfang der Datei mit der `Simple3Des` Klasse.</span><span class="sxs-lookup"><span data-stu-id="eb690-114">Add an import of the cryptography namespace to the start of the file that contains the `Simple3Des` class.</span></span>  
  
     [!code-vb[VbVbalrStrings#77](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_2.vb)]  
  
3.  <span data-ttu-id="eb690-115">In der `Simple3Des` -Klasse, fügen Sie ein privates Feld zum Speichern von 3DES cryptographic Service Provider hinzu.</span><span class="sxs-lookup"><span data-stu-id="eb690-115">In the `Simple3Des` class, add a private field to store the 3DES cryptographic service provider.</span></span>  
  
     [!code-vb[VbVbalrStrings#39](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_3.vb)]  
  
4.  <span data-ttu-id="eb690-116">Fügen Sie eine private Methode, die ein Bytearray mit einer angegebenen Länge aus dem Hash mit dem angegebenen Schlüssel erstellt.</span><span class="sxs-lookup"><span data-stu-id="eb690-116">Add a private method that creates a byte array of a specified length from the hash of the specified key.</span></span>  
  
     [!code-vb[VbVbalrStrings#41](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_4.vb)]  
  
5.  <span data-ttu-id="eb690-117">Fügen Sie einen Konstruktor, um den 3DES-Kryptografiedienstanbieter zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="eb690-117">Add a constructor to initialize the 3DES cryptographic service provider.</span></span>  
  
     <span data-ttu-id="eb690-118">Die `key` -Parameter steuert der `EncryptData` und `DecryptData` Methoden.</span><span class="sxs-lookup"><span data-stu-id="eb690-118">The `key` parameter controls the `EncryptData` and `DecryptData` methods.</span></span>  
  
     [!code-vb[VbVbalrStrings#40](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_5.vb)]  
  
6.  <span data-ttu-id="eb690-119">Fügen Sie eine öffentliche Methode, die eine Zeichenfolge verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="eb690-119">Add a public method that encrypts a string.</span></span>  
  
     [!code-vb[VbVbalrStrings#42](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_6.vb)]  
  
7.  <span data-ttu-id="eb690-120">Fügen Sie eine öffentliche Methode, die eine Zeichenfolge entschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="eb690-120">Add a public method that decrypts a string.</span></span>  
  
     [!code-vb[VbVbalrStrings#43](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_7.vb)]  
  
     <span data-ttu-id="eb690-121">Die Wrapperklasse kann jetzt verwendet werden, um Benutzer zu schützen.</span><span class="sxs-lookup"><span data-stu-id="eb690-121">The wrapper class can now be used to protect user assets.</span></span> <span data-ttu-id="eb690-122">In diesem Beispiel dient es Lagern Sie private Benutzerdaten in einer Textdatei öffentlich zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="eb690-122">In this example, it is used to securely store private user data in a publicly accessible text file.</span></span>  
  
### <a name="to-test-the-encryption-wrapper"></a><span data-ttu-id="eb690-123">So testen Sie den Verschlüsselungswrapper</span><span class="sxs-lookup"><span data-stu-id="eb690-123">To test the encryption wrapper</span></span>  
  
1.  <span data-ttu-id="eb690-124">Fügen Sie in einer separaten Klasse eine Methode, die des Wrappers verwendet `EncryptData` Methode, um eine Zeichenfolge zu verschlüsseln und Schreiben Sie ihn an den Benutzer Ordner Eigene Dokumente des.</span><span class="sxs-lookup"><span data-stu-id="eb690-124">In a separate class, add a method that uses the wrapper's `EncryptData` method to encrypt a string and write it to the user's My Documents folder.</span></span>  
  
     [!code-vb[VbVbalrStrings#78](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_8.vb)]  
  
2.  <span data-ttu-id="eb690-125">Fügen Sie eine Methode, die die verschlüsselte Zeichenfolge aus der Benutzer liest Ordner Eigene Dokumente des und entschlüsselt die Zeichenfolge mit des Wrappers `DecryptData` Methode.</span><span class="sxs-lookup"><span data-stu-id="eb690-125">Add a method that reads the encrypted string from the user's My Documents folder and decrypts the string with the wrapper's `DecryptData` method.</span></span>  
  
     [!code-vb[VbVbalrStrings#79](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_9.vb)]  
  
3.  <span data-ttu-id="eb690-126">Hinzufügen von Code für die Benutzeroberfläche zum Aufrufen der `TestEncoding` und `TestDecoding` Methoden.</span><span class="sxs-lookup"><span data-stu-id="eb690-126">Add user interface code to call the `TestEncoding` and `TestDecoding` methods.</span></span>  
  
4.  <span data-ttu-id="eb690-127">Führen Sie die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="eb690-127">Run the application.</span></span>  
  
     <span data-ttu-id="eb690-128">Wenn Sie die Anwendung testen, beachten Sie, dass die Daten nicht entschlüsselt werden, wenn Sie das falsche Kennwort angeben.</span><span class="sxs-lookup"><span data-stu-id="eb690-128">When you test the application, notice that it will not decrypt the data if you provide the wrong password.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb690-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eb690-129">See Also</span></span>  
 <xref:System.Security.Cryptography>  
 <xref:System.Security.Cryptography.DESCryptoServiceProvider>  
 <xref:System.Security.Cryptography.DES>  
 <xref:System.Security.Cryptography.TripleDES>  
 <xref:System.Security.Cryptography.Rijndael>  
 [<span data-ttu-id="eb690-130">Kryptografische Dienste</span><span class="sxs-lookup"><span data-stu-id="eb690-130">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
