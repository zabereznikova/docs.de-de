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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: ae3d599f7173162c07fbaeda60435615f101b10d
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-encrypting-and-decrypting-strings-in-visual-basic"></a>Exemplarische Vorgehensweise: Verschlüsseln und Entschlüsseln von Zeichenfolgen in Visual Basic
In dieser exemplarischen Vorgehensweise erfahren Sie, wie Sie die <xref:System.Security.Cryptography.DESCryptoServiceProvider>-Klasse zum Verschlüsseln und Entschlüsseln von Zeichenfolgen mithilfe der Service Provider (CSP)-Version des Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>)-Algorithmus.</xref:System.Security.Cryptography.TripleDES> </xref:System.Security.Cryptography.DESCryptoServiceProvider> Der erste Schritt ist zum Erstellen einer einfachen Wrapper-Klasse, die den 3DES-Algorithmus kapselt und speichert die verschlüsselten Daten als Base64-codierte Zeichenfolge. Anschließend wird dieser Wrapper verwendet, um private Benutzerdaten in einer öffentlich zugänglichen Textdatei zu speichern.  
  
 Verschlüsselung können vertrauliche Benutzerdaten (z. B. Kennwörter) schützen und Anmeldeinformationen durch nicht autorisierte Benutzer nicht lesbar zu machen. Dies kann ein autorisierter Benutzer Identität gestohlen werden, schützen, die Objekte des Benutzers und Nichtabstreitbarkeit. Verschlüsselung kann auch ein Benutzer Daten schützen, vor dem Zugriff durch nicht autorisierte Benutzer.  
  
 Weitere Informationen finden Sie unter [Kryptografiedienste](http://msdn.microsoft.com/library/f96284bc-7b73-44b5-ac59-fac613ad09f8).  
  
> [!IMPORTANT]
>  Die Rijndael (jetzt als Advanced Encryption Standard [AES] bezeichnet) und Triple Data Encryption Standard (3DES) Algorithmen bieten mehr Sicherheit als DES, da sie mehrere sind rechenintensive. Weitere Informationen finden Sie unter <xref:System.Security.Cryptography.DES>und <xref:System.Security.Cryptography.Rijndael>.</xref:System.Security.Cryptography.Rijndael> </xref:System.Security.Cryptography.DES>  
  
### <a name="to-create-the-encryption-wrapper"></a>Erstellen Sie den Verschlüsselungswrapper  
  
1.  Erstellen der `Simple3Des` Klasse, um die Verschlüsselung und Entschlüsselung Methoden kapseln.  
  
     [!code-vb[VbVbalrStrings&#38;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_1.vb)]  
  
2.  Fügen Sie am Anfang der Datei mit der Kryptografie-Namespace Importieren der `Simple3Des` Klasse.  
  
     [!code-vb[VbVbalrStrings&#77;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_2.vb)]  
  
3.  In der `Simple3Des` -Klasse ein privates Feld zum Speichern von 3DES cryptographic Service Provider hinzu.  
  
     [!code-vb[VbVbalrStrings Nr.&39;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_3.vb)]  
  
4.  Fügen Sie eine private Methode, die ein Bytearray mit einer angegebenen Länge aus dem Hash mit dem angegebenen Schlüssel erstellt.  
  
     [!code-vb[VbVbalrStrings&#41;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_4.vb)]  
  
5.  Fügen Sie einen Konstruktor, um 3DES cryptographic Service Provider zu initialisieren.  
  
     Die `key` -Parameter steuert die `EncryptData` und `DecryptData` Methoden.  
  
     [!code-vb[VbVbalrStrings&#40;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_5.vb)]  
  
6.  Fügen Sie eine öffentliche Methode, die eine Zeichenfolge verschlüsselt.  
  
     [!code-vb[VbVbalrStrings&#42;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_6.vb)]  
  
7.  Fügen Sie eine öffentliche Methode, die eine Zeichenfolge entschlüsselt.  
  
     [!code-vb[VbVbalrStrings&#43;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_7.vb)]  
  
     Die Wrapperklasse kann jetzt zum Schützen von Benutzerdaten verwendet werden. In diesem Beispiel wird es verwendet, um private Benutzerdaten in einer öffentlich zugänglichen Textdatei zu speichern.  
  
### <a name="to-test-the-encryption-wrapper"></a>So testen Sie den Verschlüsselungswrapper  
  
1.  Fügen Sie in einer separaten Klasse, eine Methode, die des Wrappers verwendet `EncryptData` Methode zum Verschlüsseln einer Zeichenfolge und zum Schreiben, die dem Benutzer den Ordner Eigene Dateien.  
  
     [!code-vb[VbVbalrStrings&#78;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_8.vb)]  
  
2.  Hinzufügen eine Methode, die die verschlüsselte Zeichenfolge aus der Benutzer liest Ordner Eigene Dokumente des Ver- und entschlüsselt die Zeichenfolge mit des Wrappers `DecryptData` Methode.  
  
     [!code-vb[VbVbalrStrings&#79;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_9.vb)]  
  
3.  Hinzufügen von Code für die Benutzeroberfläche aufrufen, die `TestEncoding` und `TestDecoding` Methoden.  
  
4.  Führen Sie die Anwendung aus.  
  
     Wenn Sie die Anwendung testen, beachten Sie, dass die Daten nicht entschlüsselt werden, wenn Sie das falsche Kennwort angeben.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Security.Cryptography></xref:System.Security.Cryptography>   
 <xref:System.Security.Cryptography.DESCryptoServiceProvider></xref:System.Security.Cryptography.DESCryptoServiceProvider>   
 <xref:System.Security.Cryptography.DES></xref:System.Security.Cryptography.DES>   
 <xref:System.Security.Cryptography.TripleDES></xref:System.Security.Cryptography.TripleDES>   
 <xref:System.Security.Cryptography.Rijndael></xref:System.Security.Cryptography.Rijndael>   
 [Kryptografische Dienste](http://msdn.microsoft.com/library/f96284bc-7b73-44b5-ac59-fac613ad09f8)
