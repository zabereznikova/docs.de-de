---
title: "Verschlüsseln und Entschlüsseln von Zeichenfolgen in Visual Basic | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- encryption, strings
- strings [Visual Basic], encrypting
- decryption, strings
- strings [Visual Basic], decrypting
ms.assetid: 1f51e40a-2f88-43e2-a83e-28a0b5c0d6fd
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 460b0e6e84f5be23f0c811e48daf36d3d4af3d23
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="walkthrough-encrypting-and-decrypting-strings-in-visual-basic"></a><span data-ttu-id="e76f5-102">Exemplarische Vorgehensweise: Verschlüsseln und Entschlüsseln von Zeichenfolgen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e76f5-102">Walkthrough: Encrypting and Decrypting Strings in Visual Basic</span></span>
<span data-ttu-id="e76f5-103">In dieser exemplarischen Vorgehensweise erfahren Sie, wie Sie die <xref:System.Security.Cryptography.DESCryptoServiceProvider>-Klasse zum Verschlüsseln und Entschlüsseln von Zeichenfolgen mithilfe der Service Provider (CSP)-Version des Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>)-Algorithmus.</xref:System.Security.Cryptography.TripleDES> </xref:System.Security.Cryptography.DESCryptoServiceProvider></span><span class="sxs-lookup"><span data-stu-id="e76f5-103">This walkthrough shows you how to use the <xref:System.Security.Cryptography.DESCryptoServiceProvider> class to encrypt and decrypt strings using the cryptographic service provider (CSP) version of the Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>) algorithm.</span></span> <span data-ttu-id="e76f5-104">Der erste Schritt ist zum Erstellen einer einfachen Wrapper-Klasse, die den 3DES-Algorithmus kapselt und speichert die verschlüsselten Daten als Base64-codierte Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="e76f5-104">The first step is to create a simple wrapper class that encapsulates the 3DES algorithm and stores the encrypted data as a base-64 encoded string.</span></span> <span data-ttu-id="e76f5-105">Anschließend wird dieser Wrapper verwendet, um private Benutzerdaten in einer öffentlich zugänglichen Textdatei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="e76f5-105">Then, that wrapper is used to securely store private user data in a publicly accessible text file.</span></span>  
  
 <span data-ttu-id="e76f5-106">Verschlüsselung können vertrauliche Benutzerdaten (z. B. Kennwörter) schützen und Anmeldeinformationen durch nicht autorisierte Benutzer nicht lesbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="e76f5-106">You can use encryption to protect user secrets (for example, passwords) and to make credentials unreadable by unauthorized users.</span></span> <span data-ttu-id="e76f5-107">Dies kann ein autorisierter Benutzer Identität gestohlen werden, schützen, die Objekte des Benutzers und Nichtabstreitbarkeit.</span><span class="sxs-lookup"><span data-stu-id="e76f5-107">This can protect an authorized user's identity from being stolen, which protects the user's assets and provides non-repudiation.</span></span> <span data-ttu-id="e76f5-108">Verschlüsselung kann auch ein Benutzer Daten schützen, vor dem Zugriff durch nicht autorisierte Benutzer.</span><span class="sxs-lookup"><span data-stu-id="e76f5-108">Encryption can also protect a user's data from being accessed by unauthorized users.</span></span>  
  
 <span data-ttu-id="e76f5-109">Weitere Informationen finden Sie unter [Kryptografiedienste](http://msdn.microsoft.com/library/f96284bc-7b73-44b5-ac59-fac613ad09f8).</span><span class="sxs-lookup"><span data-stu-id="e76f5-109">For more information, see [Cryptographic Services](http://msdn.microsoft.com/library/f96284bc-7b73-44b5-ac59-fac613ad09f8).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e76f5-110">Die Rijndael (jetzt als Advanced Encryption Standard [AES] bezeichnet) und Triple Data Encryption Standard (3DES) Algorithmen bieten mehr Sicherheit als DES, da sie mehrere sind rechenintensive.</span><span class="sxs-lookup"><span data-stu-id="e76f5-110">The Rijndael (now referred to as Advanced Encryption Standard [AES]) and Triple Data Encryption Standard (3DES) algorithms provide greater security than DES because they are more computationally intensive.</span></span> <span data-ttu-id="e76f5-111">Weitere Informationen finden Sie unter <xref:System.Security.Cryptography.DES>und <xref:System.Security.Cryptography.Rijndael>.</xref:System.Security.Cryptography.Rijndael> </xref:System.Security.Cryptography.DES></span><span class="sxs-lookup"><span data-stu-id="e76f5-111">For more information, see <xref:System.Security.Cryptography.DES> and <xref:System.Security.Cryptography.Rijndael>.</span></span>  
  
### <a name="to-create-the-encryption-wrapper"></a><span data-ttu-id="e76f5-112">Erstellen Sie den Verschlüsselungswrapper</span><span class="sxs-lookup"><span data-stu-id="e76f5-112">To create the encryption wrapper</span></span>  
  
1.  <span data-ttu-id="e76f5-113">Erstellen der `Simple3Des` Klasse, um die Verschlüsselung und Entschlüsselung Methoden kapseln.</span><span class="sxs-lookup"><span data-stu-id="e76f5-113">Create the `Simple3Des` class to encapsulate the encryption and decryption methods.</span></span>  
  
     <span data-ttu-id="e76f5-114">[!code-vb[VbVbalrStrings&#38;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="e76f5-114">[!code-vb[VbVbalrStrings#38](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_1.vb)]</span></span>  
  
2.  <span data-ttu-id="e76f5-115">Fügen Sie am Anfang der Datei mit der Kryptografie-Namespace Importieren der `Simple3Des` Klasse.</span><span class="sxs-lookup"><span data-stu-id="e76f5-115">Add an import of the cryptography namespace to the start of the file that contains the `Simple3Des` class.</span></span>  
  
     <span data-ttu-id="e76f5-116">[!code-vb[VbVbalrStrings&#77;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="e76f5-116">[!code-vb[VbVbalrStrings#77](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_2.vb)]</span></span>  
  
3.  <span data-ttu-id="e76f5-117">In der `Simple3Des` -Klasse ein privates Feld zum Speichern von 3DES cryptographic Service Provider hinzu.</span><span class="sxs-lookup"><span data-stu-id="e76f5-117">In the `Simple3Des` class, add a private field to store the 3DES cryptographic service provider.</span></span>  
  
     <span data-ttu-id="e76f5-118">[!code-vb[VbVbalrStrings Nr.&39;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="e76f5-118">[!code-vb[VbVbalrStrings#39](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_3.vb)]</span></span>  
  
4.  <span data-ttu-id="e76f5-119">Fügen Sie eine private Methode, die ein Bytearray mit einer angegebenen Länge aus dem Hash mit dem angegebenen Schlüssel erstellt.</span><span class="sxs-lookup"><span data-stu-id="e76f5-119">Add a private method that creates a byte array of a specified length from the hash of the specified key.</span></span>  
  
     <span data-ttu-id="e76f5-120">[!code-vb[VbVbalrStrings&#41;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="e76f5-120">[!code-vb[VbVbalrStrings#41](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_4.vb)]</span></span>  
  
5.  <span data-ttu-id="e76f5-121">Fügen Sie einen Konstruktor, um 3DES cryptographic Service Provider zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="e76f5-121">Add a constructor to initialize the 3DES cryptographic service provider.</span></span>  
  
     <span data-ttu-id="e76f5-122">Die `key` -Parameter steuert die `EncryptData` und `DecryptData` Methoden.</span><span class="sxs-lookup"><span data-stu-id="e76f5-122">The `key` parameter controls the `EncryptData` and `DecryptData` methods.</span></span>  
  
     <span data-ttu-id="e76f5-123">[!code-vb[VbVbalrStrings&#40;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="e76f5-123">[!code-vb[VbVbalrStrings#40](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_5.vb)]</span></span>  
  
6.  <span data-ttu-id="e76f5-124">Fügen Sie eine öffentliche Methode, die eine Zeichenfolge verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="e76f5-124">Add a public method that encrypts a string.</span></span>  
  
     <span data-ttu-id="e76f5-125">[!code-vb[VbVbalrStrings&#42;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="e76f5-125">[!code-vb[VbVbalrStrings#42](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_6.vb)]</span></span>  
  
7.  <span data-ttu-id="e76f5-126">Fügen Sie eine öffentliche Methode, die eine Zeichenfolge entschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="e76f5-126">Add a public method that decrypts a string.</span></span>  
  
     <span data-ttu-id="e76f5-127">[!code-vb[VbVbalrStrings&#43;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="e76f5-127">[!code-vb[VbVbalrStrings#43](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_7.vb)]</span></span>  
  
     <span data-ttu-id="e76f5-128">Die Wrapperklasse kann jetzt zum Schützen von Benutzerdaten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e76f5-128">The wrapper class can now be used to protect user assets.</span></span> <span data-ttu-id="e76f5-129">In diesem Beispiel wird es verwendet, um private Benutzerdaten in einer öffentlich zugänglichen Textdatei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="e76f5-129">In this example, it is used to securely store private user data in a publicly accessible text file.</span></span>  
  
### <a name="to-test-the-encryption-wrapper"></a><span data-ttu-id="e76f5-130">So testen Sie den Verschlüsselungswrapper</span><span class="sxs-lookup"><span data-stu-id="e76f5-130">To test the encryption wrapper</span></span>  
  
1.  <span data-ttu-id="e76f5-131">Fügen Sie in einer separaten Klasse, eine Methode, die des Wrappers verwendet `EncryptData` Methode zum Verschlüsseln einer Zeichenfolge und zum Schreiben, die dem Benutzer den Ordner Eigene Dateien.</span><span class="sxs-lookup"><span data-stu-id="e76f5-131">In a separate class, add a method that uses the wrapper's `EncryptData` method to encrypt a string and write it to the user's My Documents folder.</span></span>  
  
     <span data-ttu-id="e76f5-132">[!code-vb[VbVbalrStrings&#78;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="e76f5-132">[!code-vb[VbVbalrStrings#78](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_8.vb)]</span></span>  
  
2.  <span data-ttu-id="e76f5-133">Hinzufügen eine Methode, die die verschlüsselte Zeichenfolge aus der Benutzer liest Ordner Eigene Dokumente des Ver- und entschlüsselt die Zeichenfolge mit des Wrappers `DecryptData` Methode.</span><span class="sxs-lookup"><span data-stu-id="e76f5-133">Add a method that reads the encrypted string from the user's My Documents folder and decrypts the string with the wrapper's `DecryptData` method.</span></span>  
  
     <span data-ttu-id="e76f5-134">[!code-vb[VbVbalrStrings&#79;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="e76f5-134">[!code-vb[VbVbalrStrings#79](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_9.vb)]</span></span>  
  
3.  <span data-ttu-id="e76f5-135">Hinzufügen von Code für die Benutzeroberfläche aufrufen, die `TestEncoding` und `TestDecoding` Methoden.</span><span class="sxs-lookup"><span data-stu-id="e76f5-135">Add user interface code to call the `TestEncoding` and `TestDecoding` methods.</span></span>  
  
4.  <span data-ttu-id="e76f5-136">Führen Sie die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="e76f5-136">Run the application.</span></span>  
  
     <span data-ttu-id="e76f5-137">Wenn Sie die Anwendung testen, beachten Sie, dass die Daten nicht entschlüsselt werden, wenn Sie das falsche Kennwort angeben.</span><span class="sxs-lookup"><span data-stu-id="e76f5-137">When you test the application, notice that it will not decrypt the data if you provide the wrong password.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e76f5-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e76f5-138">See Also</span></span>  
 <span data-ttu-id="e76f5-139"><xref:System.Security.Cryptography></xref:System.Security.Cryptography></span><span class="sxs-lookup"><span data-stu-id="e76f5-139"><xref:System.Security.Cryptography></span></span>   
 <span data-ttu-id="e76f5-140"><xref:System.Security.Cryptography.DESCryptoServiceProvider></xref:System.Security.Cryptography.DESCryptoServiceProvider></span><span class="sxs-lookup"><span data-stu-id="e76f5-140"><xref:System.Security.Cryptography.DESCryptoServiceProvider></span></span>   
 <span data-ttu-id="e76f5-141"><xref:System.Security.Cryptography.DES></xref:System.Security.Cryptography.DES></span><span class="sxs-lookup"><span data-stu-id="e76f5-141"><xref:System.Security.Cryptography.DES></span></span>   
 <span data-ttu-id="e76f5-142"><xref:System.Security.Cryptography.TripleDES></xref:System.Security.Cryptography.TripleDES></span><span class="sxs-lookup"><span data-stu-id="e76f5-142"><xref:System.Security.Cryptography.TripleDES></span></span>   
 <span data-ttu-id="e76f5-143"><xref:System.Security.Cryptography.Rijndael></xref:System.Security.Cryptography.Rijndael></span><span class="sxs-lookup"><span data-stu-id="e76f5-143"><xref:System.Security.Cryptography.Rijndael></span></span>   
<span data-ttu-id="e76f5-144"> [Kryptografische Dienste](http://msdn.microsoft.com/library/f96284bc-7b73-44b5-ac59-fac613ad09f8)</span><span class="sxs-lookup"><span data-stu-id="e76f5-144"> [Cryptographic Services](http://msdn.microsoft.com/library/f96284bc-7b73-44b5-ac59-fac613ad09f8)</span></span>
