---
title: Verschlüsseln und Entschlüsseln von Zeichenfolgen in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- encryption [Visual Basic], strings
- strings [Visual Basic], encrypting
- decryption [Visual Basic], strings
- strings [Visual Basic], decrypting
ms.assetid: 1f51e40a-2f88-43e2-a83e-28a0b5c0d6fd
ms.openlocfilehash: 1d003df87327e14a6cbd65222f86c3dc4df169ff
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59334041"
---
# <a name="walkthrough-encrypting-and-decrypting-strings-in-visual-basic"></a><span data-ttu-id="3babc-102">Exemplarische Vorgehensweise: Verschlüsseln und Entschlüsseln von Zeichenfolgen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3babc-102">Walkthrough: Encrypting and Decrypting Strings in Visual Basic</span></span>
<span data-ttu-id="3babc-103">In dieser exemplarischen Vorgehensweise erfahren Sie, wie Sie mit der <xref:System.Security.Cryptography.DESCryptoServiceProvider> -Klasse zum Verschlüsseln und Entschlüsseln von Zeichenfolgen mithilfe der Service Provider (CSP)-Version des Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>) Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="3babc-103">This walkthrough shows you how to use the <xref:System.Security.Cryptography.DESCryptoServiceProvider> class to encrypt and decrypt strings using the cryptographic service provider (CSP) version of the Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>) algorithm.</span></span> <span data-ttu-id="3babc-104">Der erste Schritt ist die Erstellung eine einfachen Wrapperklasse, die den 3DES-Algorithmus verwendet kapselt und speichert die verschlüsselten Daten als Base64-codierte Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="3babc-104">The first step is to create a simple wrapper class that encapsulates the 3DES algorithm and stores the encrypted data as a base-64 encoded string.</span></span> <span data-ttu-id="3babc-105">Anschließend wird diesen Wrapper verwendet, das sichere Speichern von persönlichen Daten in eine Textdatei für die öffentlich zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="3babc-105">Then, that wrapper is used to securely store private user data in a publicly accessible text file.</span></span>  
  
 <span data-ttu-id="3babc-106">Sie können Verschlüsselung verwenden, um vertrauliche Informationen eines Benutzers (z. B. Kennwörter) zu schützen und um Anmeldeinformationen durch nicht autorisierte Benutzer nicht lesbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="3babc-106">You can use encryption to protect user secrets (for example, passwords) and to make credentials unreadable by unauthorized users.</span></span> <span data-ttu-id="3babc-107">Dies kann ein autorisierter Benutzer-Identität aus, die gestohlen, schützen, die des Benutzers Assets und bei der nichtabstreitbarkeits.</span><span class="sxs-lookup"><span data-stu-id="3babc-107">This can protect an authorized user's identity from being stolen, which protects the user's assets and provides non-repudiation.</span></span> <span data-ttu-id="3babc-108">Verschlüsselung kann die Daten eines Benutzers auch vor dem Zugriff durch nicht autorisierte Benutzer schützen.</span><span class="sxs-lookup"><span data-stu-id="3babc-108">Encryption can also protect a user's data from being accessed by unauthorized users.</span></span>  
  
 <span data-ttu-id="3babc-109">Weitere Informationen finden Sie unter [Kryptografiedienste](../../../../standard/security/cryptographic-services.md).</span><span class="sxs-lookup"><span data-stu-id="3babc-109">For more information, see [Cryptographic Services](../../../../standard/security/cryptographic-services.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3babc-110">Die Rijndael (jetzt als Advanced Encryption Standard [AES] bezeichnet) und die Triple Data Encryption Standard (3DES) Algorithmen bieten mehr Sicherheit als DES auf, da sie weitere sind rechenintensiv.</span><span class="sxs-lookup"><span data-stu-id="3babc-110">The Rijndael (now referred to as Advanced Encryption Standard [AES]) and Triple Data Encryption Standard (3DES) algorithms provide greater security than DES because they are more computationally intensive.</span></span> <span data-ttu-id="3babc-111">Weitere Informationen finden Sie unter <xref:System.Security.Cryptography.DES> und <xref:System.Security.Cryptography.Rijndael>.</span><span class="sxs-lookup"><span data-stu-id="3babc-111">For more information, see <xref:System.Security.Cryptography.DES> and <xref:System.Security.Cryptography.Rijndael>.</span></span>  
  
### <a name="to-create-the-encryption-wrapper"></a><span data-ttu-id="3babc-112">So erstellen Sie die Verschlüsselungswrapper</span><span class="sxs-lookup"><span data-stu-id="3babc-112">To create the encryption wrapper</span></span>  
  
1. <span data-ttu-id="3babc-113">Erstellen der `Simple3Des` Klasse, die Methoden zum Ver- und Entschlüsselung zu kapseln.</span><span class="sxs-lookup"><span data-stu-id="3babc-113">Create the `Simple3Des` class to encapsulate the encryption and decryption methods.</span></span>  
  
     [!code-vb[VbVbalrStrings#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#38)]  
  
2. <span data-ttu-id="3babc-114">Fügen Sie einen Import der Kryptografie-Namespace am Anfang der Datei mit den `Simple3Des` Klasse.</span><span class="sxs-lookup"><span data-stu-id="3babc-114">Add an import of the cryptography namespace to the start of the file that contains the `Simple3Des` class.</span></span>  
  
     [!code-vb[VbVbalrStrings#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#77)]  
  
3. <span data-ttu-id="3babc-115">In der `Simple3Des` -Klasse ein privates Feld zum Speichern von 3DES cryptographic Service Provider hinzu.</span><span class="sxs-lookup"><span data-stu-id="3babc-115">In the `Simple3Des` class, add a private field to store the 3DES cryptographic service provider.</span></span>  
  
     [!code-vb[VbVbalrStrings#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#39)]  
  
4. <span data-ttu-id="3babc-116">Fügen Sie eine private Methode, die ein Bytearray mit einer angegebenen Länge aus dem Hash des dem angegebenen Schlüssel erstellt.</span><span class="sxs-lookup"><span data-stu-id="3babc-116">Add a private method that creates a byte array of a specified length from the hash of the specified key.</span></span>  
  
     [!code-vb[VbVbalrStrings#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#41)]  
  
5. <span data-ttu-id="3babc-117">Fügen Sie einen Konstruktor zum Initialisieren des 3DES-Kryptografiedienstanbieter hinzu.</span><span class="sxs-lookup"><span data-stu-id="3babc-117">Add a constructor to initialize the 3DES cryptographic service provider.</span></span>  
  
     <span data-ttu-id="3babc-118">Die `key` Parameter steuert die `EncryptData` und `DecryptData` Methoden.</span><span class="sxs-lookup"><span data-stu-id="3babc-118">The `key` parameter controls the `EncryptData` and `DecryptData` methods.</span></span>  
  
     [!code-vb[VbVbalrStrings#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#40)]  
  
6. <span data-ttu-id="3babc-119">Fügen Sie eine öffentliche Methode, die eine Zeichenfolge verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="3babc-119">Add a public method that encrypts a string.</span></span>  
  
     [!code-vb[VbVbalrStrings#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#42)]  
  
7. <span data-ttu-id="3babc-120">Fügen Sie eine öffentliche Methode, die eine Zeichenfolge entschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="3babc-120">Add a public method that decrypts a string.</span></span>  
  
     [!code-vb[VbVbalrStrings#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#43)]  
  
     <span data-ttu-id="3babc-121">Die Wrapperklasse kann jetzt zum Schützen von Benutzerdaten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3babc-121">The wrapper class can now be used to protect user assets.</span></span> <span data-ttu-id="3babc-122">In diesem Beispiel wird es verwendet das sichere Speichern von persönlichen Daten in eine Textdatei für die öffentlich zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="3babc-122">In this example, it is used to securely store private user data in a publicly accessible text file.</span></span>  
  
### <a name="to-test-the-encryption-wrapper"></a><span data-ttu-id="3babc-123">Zum Testen des Verschlüsselungswrapper</span><span class="sxs-lookup"><span data-stu-id="3babc-123">To test the encryption wrapper</span></span>  
  
1. <span data-ttu-id="3babc-124">Fügen Sie in einer separaten Klasse eine Methode, die des Wrappers verwendet `EncryptData` Methode zum Verschlüsseln einer Zeichenfolge und der Benutzer in den Ordner "Eigene Dokumente".</span><span class="sxs-lookup"><span data-stu-id="3babc-124">In a separate class, add a method that uses the wrapper's `EncryptData` method to encrypt a string and write it to the user's My Documents folder.</span></span>  
  
     [!code-vb[VbVbalrStrings#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#78)]  
  
2. <span data-ttu-id="3babc-125">Hinzufügen einer Methode, die die verschlüsselte Zeichenfolge aus der Benutzer liest Ordner Eigene Dokumente des und entschlüsselt die Zeichenfolge mit des Wrappers `DecryptData` Methode.</span><span class="sxs-lookup"><span data-stu-id="3babc-125">Add a method that reads the encrypted string from the user's My Documents folder and decrypts the string with the wrapper's `DecryptData` method.</span></span>  
  
     [!code-vb[VbVbalrStrings#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#79)]  
  
3. <span data-ttu-id="3babc-126">Hinzufügen von Code für die Benutzeroberfläche aufrufen, die `TestEncoding` und `TestDecoding` Methoden.</span><span class="sxs-lookup"><span data-stu-id="3babc-126">Add user interface code to call the `TestEncoding` and `TestDecoding` methods.</span></span>  
  
4. <span data-ttu-id="3babc-127">Führen Sie die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="3babc-127">Run the application.</span></span>  
  
     <span data-ttu-id="3babc-128">Wenn Sie die Anwendung testen, beachten Sie, dass die Daten nicht entschlüsselt werden, wenn Sie das falsche Kennwort angeben.</span><span class="sxs-lookup"><span data-stu-id="3babc-128">When you test the application, notice that it will not decrypt the data if you provide the wrong password.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3babc-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3babc-129">See also</span></span>

- <xref:System.Security.Cryptography>
- <xref:System.Security.Cryptography.DESCryptoServiceProvider>
- <xref:System.Security.Cryptography.DES>
- <xref:System.Security.Cryptography.TripleDES>
- <xref:System.Security.Cryptography.Rijndael>
- [<span data-ttu-id="3babc-130">Kryptografische Dienste</span><span class="sxs-lookup"><span data-stu-id="3babc-130">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
