---
title: Verschlüsseln und Entschlüsseln von Zeichenfolgen in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- encryption [Visual Basic], strings
- strings [Visual Basic], encrypting
- decryption [Visual Basic], strings
- strings [Visual Basic], decrypting
ms.assetid: 1f51e40a-2f88-43e2-a83e-28a0b5c0d6fd
ms.openlocfilehash: ee3bcd1358536e6fd9bed5c4fec7845fdf441d86
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54723484"
---
# <a name="walkthrough-encrypting-and-decrypting-strings-in-visual-basic"></a>Exemplarische Vorgehensweise: Verschlüsseln und Entschlüsseln von Zeichenfolgen in Visual Basic
In dieser exemplarischen Vorgehensweise erfahren Sie, wie Sie mit der <xref:System.Security.Cryptography.DESCryptoServiceProvider> -Klasse zum Verschlüsseln und Entschlüsseln von Zeichenfolgen mithilfe der Service Provider (CSP)-Version des Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>) Algorithmus. Der erste Schritt ist die Erstellung eine einfachen Wrapperklasse, die den 3DES-Algorithmus verwendet kapselt und speichert die verschlüsselten Daten als Base64-codierte Zeichenfolge. Anschließend wird diesen Wrapper verwendet, das sichere Speichern von persönlichen Daten in eine Textdatei für die öffentlich zugegriffen werden kann.  
  
 Sie können Verschlüsselung verwenden, um vertrauliche Informationen eines Benutzers (z. B. Kennwörter) zu schützen und um Anmeldeinformationen durch nicht autorisierte Benutzer nicht lesbar zu machen. Dies kann ein autorisierter Benutzer-Identität aus, die gestohlen, schützen, die des Benutzers Assets und bei der nichtabstreitbarkeits. Verschlüsselung kann die Daten eines Benutzers auch vor dem Zugriff durch nicht autorisierte Benutzer schützen.  
  
 Weitere Informationen finden Sie unter [Kryptografiedienste](../../../../standard/security/cryptographic-services.md).  
  
> [!IMPORTANT]
>  Die Rijndael (jetzt als Advanced Encryption Standard [AES] bezeichnet) und die Triple Data Encryption Standard (3DES) Algorithmen bieten mehr Sicherheit als DES auf, da sie weitere sind rechenintensiv. Weitere Informationen finden Sie unter <xref:System.Security.Cryptography.DES> und <xref:System.Security.Cryptography.Rijndael>.  
  
### <a name="to-create-the-encryption-wrapper"></a>So erstellen Sie die Verschlüsselungswrapper  
  
1.  Erstellen der `Simple3Des` Klasse, die Methoden zum Ver- und Entschlüsselung zu kapseln.  
  
     [!code-vb[VbVbalrStrings#38](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_1.vb)]  
  
2.  Fügen Sie einen Import der Kryptografie-Namespace am Anfang der Datei mit den `Simple3Des` Klasse.  
  
     [!code-vb[VbVbalrStrings#77](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_2.vb)]  
  
3.  In der `Simple3Des` -Klasse ein privates Feld zum Speichern von 3DES cryptographic Service Provider hinzu.  
  
     [!code-vb[VbVbalrStrings#39](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_3.vb)]  
  
4.  Fügen Sie eine private Methode, die ein Bytearray mit einer angegebenen Länge aus dem Hash des dem angegebenen Schlüssel erstellt.  
  
     [!code-vb[VbVbalrStrings#41](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_4.vb)]  
  
5.  Fügen Sie einen Konstruktor zum Initialisieren des 3DES-Kryptografiedienstanbieter hinzu.  
  
     Die `key` Parameter steuert die `EncryptData` und `DecryptData` Methoden.  
  
     [!code-vb[VbVbalrStrings#40](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_5.vb)]  
  
6.  Fügen Sie eine öffentliche Methode, die eine Zeichenfolge verschlüsselt.  
  
     [!code-vb[VbVbalrStrings#42](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_6.vb)]  
  
7.  Fügen Sie eine öffentliche Methode, die eine Zeichenfolge entschlüsselt.  
  
     [!code-vb[VbVbalrStrings#43](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_7.vb)]  
  
     Die Wrapperklasse kann jetzt zum Schützen von Benutzerdaten verwendet werden. In diesem Beispiel wird es verwendet das sichere Speichern von persönlichen Daten in eine Textdatei für die öffentlich zugegriffen werden kann.  
  
### <a name="to-test-the-encryption-wrapper"></a>Zum Testen des Verschlüsselungswrapper  
  
1.  Fügen Sie in einer separaten Klasse eine Methode, die des Wrappers verwendet `EncryptData` Methode zum Verschlüsseln einer Zeichenfolge und der Benutzer in den Ordner "Eigene Dokumente".  
  
     [!code-vb[VbVbalrStrings#78](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_8.vb)]  
  
2.  Hinzufügen einer Methode, die die verschlüsselte Zeichenfolge aus der Benutzer liest Ordner Eigene Dokumente des und entschlüsselt die Zeichenfolge mit des Wrappers `DecryptData` Methode.  
  
     [!code-vb[VbVbalrStrings#79](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_9.vb)]  
  
3.  Hinzufügen von Code für die Benutzeroberfläche aufrufen, die `TestEncoding` und `TestDecoding` Methoden.  
  
4.  Führen Sie die Anwendung aus.  
  
     Wenn Sie die Anwendung testen, beachten Sie, dass die Daten nicht entschlüsselt werden, wenn Sie das falsche Kennwort angeben.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Security.Cryptography>
- <xref:System.Security.Cryptography.DESCryptoServiceProvider>
- <xref:System.Security.Cryptography.DES>
- <xref:System.Security.Cryptography.TripleDES>
- <xref:System.Security.Cryptography.Rijndael>
- [Cryptographic Services](../../../../standard/security/cryptographic-services.md)
