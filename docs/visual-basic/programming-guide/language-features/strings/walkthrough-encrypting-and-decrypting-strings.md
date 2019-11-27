---
title: Verschlüsseln und Entschlüsseln von Zeichenfolgen
ms.date: 07/20/2015
helpviewer_keywords:
- encryption [Visual Basic], strings
- strings [Visual Basic], encrypting
- decryption [Visual Basic], strings
- strings [Visual Basic], decrypting
ms.assetid: 1f51e40a-2f88-43e2-a83e-28a0b5c0d6fd
ms.openlocfilehash: 36e405c7362993471d3e6da8e319bccb854e1026
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343588"
---
# <a name="walkthrough-encrypting-and-decrypting-strings-in-visual-basic"></a>Exemplarische Vorgehensweise: Verschlüsseln und Entschlüsseln von Zeichenfolgen in Visual Basic
In dieser exemplarischen Vorgehensweise wird gezeigt, wie Sie mithilfe der <xref:System.Security.Cryptography.DESCryptoServiceProvider>-Klasse Zeichen folgen mithilfe der CSP-Version (kryptografischen Service Provider) des Triple Data Encryption Standard-Algorithmus (<xref:System.Security.Cryptography.TripleDES>) verschlüsseln und entschlüsseln. Der erste Schritt besteht darin, eine einfache Wrapper Klasse zu erstellen, die den 3DES-Algorithmus kapselt und die verschlüsselten Daten als Base-64-codierte Zeichenfolge speichert. Anschließend wird dieser Wrapper zum sicheren Speichern privater Benutzerdaten in einer öffentlich zugänglichen Textdatei verwendet.  
  
 Sie können die Verschlüsselung zum Schutz von Benutzer Geheimnissen (z. b. Kenn Wörter) und zum unlesbar von Anmelde Informationen durch nicht autorisierte Benutzer verwenden. Dadurch kann die Identität eines autorisierten Benutzers vor dem Diebstahl geschützt werden, wodurch die Objekte des Benutzers geschützt werden und Nichtabstreitbarkeit gewährleistet ist. Mit der Verschlüsselung können auch die Daten eines Benutzers vor dem Zugriff durch nicht autorisierte Benutzer geschützt werden.  
  
 Weitere Informationen finden Sie unter [Kryptografiedienste](../../../../standard/security/cryptographic-services.md).  
  
> [!IMPORTANT]
> Die Rijndael-Algorithmen (jetzt als Advanced Encryption Standard [AES]) und 3DES-Algorithmen (Triple Data Encryption Standard) bieten mehr Sicherheit als die des, da sie Rechen intensiver sind. Weitere Informationen finden Sie unter <xref:System.Security.Cryptography.DES> und <xref:System.Security.Cryptography.Rijndael>.  
  
### <a name="to-create-the-encryption-wrapper"></a>So erstellen Sie den Verschlüsselungs Wrapper  
  
1. Erstellen Sie die `Simple3Des`-Klasse, um die Verschlüsselungs-und Entschlüsselungs Methoden zu kapseln.  
  
     [!code-vb[VbVbalrStrings#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#38)]  
  
2. Fügen Sie am Anfang der Datei, die die `Simple3Des` Klasse enthält, einen Import des Kryptografienamespace hinzu.  
  
     [!code-vb[VbVbalrStrings#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#77)]  
  
3. Fügen Sie in der `Simple3Des`-Klasse ein privates Feld zum Speichern des 3DES-Kryptografiedienstanbieters hinzu.  
  
     [!code-vb[VbVbalrStrings#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#39)]  
  
4. Fügen Sie eine private Methode hinzu, mit der ein Bytearray mit einer angegebenen Länge aus dem Hashwert des angegebenen Schlüssels erstellt wird.  
  
     [!code-vb[VbVbalrStrings#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#41)]  
  
5. Fügen Sie einen Konstruktor hinzu, um den 3DES-Kryptografiedienstanbieter zu initialisieren.  
  
     Der `key`-Parameter steuert die Methoden `EncryptData` und `DecryptData`.  
  
     [!code-vb[VbVbalrStrings#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#40)]  
  
6. Fügen Sie eine öffentliche Methode hinzu, die eine Zeichenfolge verschlüsselt.  
  
     [!code-vb[VbVbalrStrings#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#42)]  
  
7. Fügen Sie eine öffentliche Methode hinzu, die eine Zeichenfolge entschlüsselt.  
  
     [!code-vb[VbVbalrStrings#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#43)]  
  
     Die Wrapper Klasse kann jetzt verwendet werden, um Benutzer Objekte zu schützen. In diesem Beispiel wird es verwendet, um private Benutzerdaten sicher in einer öffentlich zugänglichen Textdatei zu speichern.  
  
### <a name="to-test-the-encryption-wrapper"></a>So testen Sie den Verschlüsselungs Wrapper  
  
1. Fügen Sie in einer separaten Klasse eine Methode hinzu, die die `EncryptData`-Methode des Wrappers verwendet, um eine Zeichenfolge zu verschlüsseln und in den Ordner "eigene Dateien" des Benutzers zu schreiben.  
  
     [!code-vb[VbVbalrStrings#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#78)]  
  
2. Fügen Sie eine Methode hinzu, die die verschlüsselte Zeichenfolge aus dem Ordner "eigene Dateien" des Benutzers liest und die Zeichenfolge mit der `DecryptData`-Methode des Wrappers entschlüsselt.  
  
     [!code-vb[VbVbalrStrings#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#79)]  
  
3. Fügen Sie Benutzeroberflächen Code hinzu, um die Methoden `TestEncoding` und `TestDecoding` aufzurufen.  
  
4. Führen Sie die Anwendung aus.  
  
     Beachten Sie beim Testen der Anwendung, dass die Daten nicht entschlüsselt werden, wenn Sie das falsche Kennwort angeben.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Security.Cryptography>
- <xref:System.Security.Cryptography.DESCryptoServiceProvider>
- <xref:System.Security.Cryptography.DES>
- <xref:System.Security.Cryptography.TripleDES>
- <xref:System.Security.Cryptography.Rijndael>
- [Kryptografische Dienste](../../../../standard/security/cryptographic-services.md)
