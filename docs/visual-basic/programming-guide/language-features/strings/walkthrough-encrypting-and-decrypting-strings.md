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
# <a name="walkthrough-encrypting-and-decrypting-strings-in-visual-basic"></a>Exemplarische Vorgehensweise: Verschlüsseln und Entschlüsseln von Zeichenfolgen in Visual Basic
Diese exemplarische Vorgehensweise veranschaulicht das Verwenden der <xref:System.Security.Cryptography.DESCryptoServiceProvider> Klasse zum Verschlüsseln und Entschlüsseln von Zeichenfolgen mithilfe von cryptographic Service Provider (CSP)-Version von Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>) Algorithmus. Der erste Schritt ist zum Erstellen einer einfachen Wrapperklasse, die den 3DES-Algorithmus kapselt und speichert die verschlüsselten Daten als Base64-codierte Zeichenfolge. Anschließend wird dieser Wrapper verwendet, um private Benutzerdaten in einem öffentlich zugänglichen Textdatei sicher zu speichern.  
  
 Sie können Verschlüsselung verwenden, um vertrauliche Benutzerdaten (z. B. Kennwörter) zu schützen und um Anmeldeinformationen durch nicht autorisierte Benutzer nicht lesbar zu machen. Dies kann ein autorisierter Benutzer Identität gestohlen werden, schützen, die des Benutzers Bestand schützt und Nachweisbarkeit enthält. Verschlüsselung kann auch verhindern, dass Daten eines Benutzers durch nicht autorisierte Benutzer zugegriffen wird.  
  
 Weitere Informationen finden Sie unter [Kryptografiedienste](../../../../standard/security/cryptographic-services.md).  
  
> [!IMPORTANT]
>  Die Rijndael (jetzt als Advanced Encryption Standard [AES] bezeichnet) und die Triple Data Encryption Standard (3DES) Algorithmen bieten mehr Sicherheit als DES, da sie weitere sind zur Ausführung rechenintensiver. Weitere Informationen finden Sie unter <xref:System.Security.Cryptography.DES> und <xref:System.Security.Cryptography.Rijndael>.  
  
### <a name="to-create-the-encryption-wrapper"></a>Zum Erstellen des Verschlüsselungswrapper  
  
1.  Erstellen der `Simple3Des` Klasse, um die Verschlüsselung und Entschlüsselung Methoden zu kapseln.  
  
     [!code-vb[VbVbalrStrings#38](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_1.vb)]  
  
2.  Fügen Sie einen Import eines Kryptografie-Namespace am Anfang der Datei mit der `Simple3Des` Klasse.  
  
     [!code-vb[VbVbalrStrings#77](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_2.vb)]  
  
3.  In der `Simple3Des` -Klasse, fügen Sie ein privates Feld zum Speichern von 3DES cryptographic Service Provider hinzu.  
  
     [!code-vb[VbVbalrStrings#39](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_3.vb)]  
  
4.  Fügen Sie eine private Methode, die ein Bytearray mit einer angegebenen Länge aus dem Hash mit dem angegebenen Schlüssel erstellt.  
  
     [!code-vb[VbVbalrStrings#41](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_4.vb)]  
  
5.  Fügen Sie einen Konstruktor, um den 3DES-Kryptografiedienstanbieter zu initialisieren.  
  
     Die `key` -Parameter steuert der `EncryptData` und `DecryptData` Methoden.  
  
     [!code-vb[VbVbalrStrings#40](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_5.vb)]  
  
6.  Fügen Sie eine öffentliche Methode, die eine Zeichenfolge verschlüsselt.  
  
     [!code-vb[VbVbalrStrings#42](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_6.vb)]  
  
7.  Fügen Sie eine öffentliche Methode, die eine Zeichenfolge entschlüsselt.  
  
     [!code-vb[VbVbalrStrings#43](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_7.vb)]  
  
     Die Wrapperklasse kann jetzt verwendet werden, um Benutzer zu schützen. In diesem Beispiel dient es Lagern Sie private Benutzerdaten in einer Textdatei öffentlich zugegriffen werden kann.  
  
### <a name="to-test-the-encryption-wrapper"></a>So testen Sie den Verschlüsselungswrapper  
  
1.  Fügen Sie in einer separaten Klasse eine Methode, die des Wrappers verwendet `EncryptData` Methode, um eine Zeichenfolge zu verschlüsseln und Schreiben Sie ihn an den Benutzer Ordner Eigene Dokumente des.  
  
     [!code-vb[VbVbalrStrings#78](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_8.vb)]  
  
2.  Fügen Sie eine Methode, die die verschlüsselte Zeichenfolge aus der Benutzer liest Ordner Eigene Dokumente des und entschlüsselt die Zeichenfolge mit des Wrappers `DecryptData` Methode.  
  
     [!code-vb[VbVbalrStrings#79](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_9.vb)]  
  
3.  Hinzufügen von Code für die Benutzeroberfläche zum Aufrufen der `TestEncoding` und `TestDecoding` Methoden.  
  
4.  Führen Sie die Anwendung aus.  
  
     Wenn Sie die Anwendung testen, beachten Sie, dass die Daten nicht entschlüsselt werden, wenn Sie das falsche Kennwort angeben.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Security.Cryptography>  
 <xref:System.Security.Cryptography.DESCryptoServiceProvider>  
 <xref:System.Security.Cryptography.DES>  
 <xref:System.Security.Cryptography.TripleDES>  
 <xref:System.Security.Cryptography.Rijndael>  
 [Kryptografische Dienste](../../../../standard/security/cryptographic-services.md)
