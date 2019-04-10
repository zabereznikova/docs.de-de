---
title: 'Vorgehensweise: Entschlüsseln von XML-Elementen mit asymmetrischen Schlüsseln'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- System.Security.Cryptography.RSACryptoServiceProvider class
- asymmetric keys
- System.Security.Cryptography.EncryptedXml class
- XML encryption
- decryption
ms.assetid: dd5de491-dafe-4b94-966d-99714b2e754a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 303c7db984b682d24a8f0e00160eb2d0827a84e6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59314424"
---
# <a name="how-to-decrypt-xml-elements-with-asymmetric-keys"></a>Vorgehensweise: Entschlüsseln von XML-Elementen mit asymmetrischen Schlüsseln
Sie können die Klassen im <xref:System.Security.Cryptography.Xml>-Namespace verwenden, um ein Element in einem XML-Dokument zu verschlüsseln und zu entschlüsseln.  XML-Verschlüsselung ist ein gängiges Verfahren zum Austauschen oder Speichern von verschlüsselten XML-Daten, ohne sich Gedanken machen zu müssen, dass die Daten einfach gelesen werden können.  Weitere Informationen zu XML-Verschlüsselungsstandard, finden Sie unter der Empfehlung des World Wide Web Consortium (W3C) [XML Signature Syntax and Processing](https://www.w3.org/TR/xmldsig-core/).  
  
 Im Beispiel in diesem Verfahren wird ein XML-Element, das mit den beschriebenen Methoden verschlüsselt wurde entschlüsselt [Vorgehensweise: Verschlüsseln von XML-Elementen mit asymmetrischen Schlüsseln](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md).  Er findet eine <`EncryptedData`> Element, wird dieses Element entschlüsselt, und klicken Sie dann das Element mit dem ursprünglichen nur-Text-XML-Element ersetzt.  
  
 In diesem Beispiel wird ein XML-Element mithilfe zweier Schlüssel entschlüsselt.  Einen zuvor generierten privaten RSA-Schlüssel aus einem Schlüsselcontainer abgerufen und anschließend verwendet der RSA-Schlüssel zum Entschlüsseln eines Sitzungsschlüssels gespeichert, der <`EncryptedKey`> Element der <`EncryptedData`> Element.  In dem Beispiel wird dann der Sitzungsschlüssel verwendet, um das XML-Element zu entschlüsseln.  
  
 Das Beispiel eignet sich für Situationen, in denen mehrere Anwendungen verschlüsselte Daten gemeinsam nutzen müssen, oder in denen eine Anwendung verschlüsselte Daten zwischen den Zeiten speichern muss, in denen sie ausgeführt wird.  
  
### <a name="to-decrypt-an-xml-element-with-an-asymmetric-key"></a>So entschlüsseln Sie ein XML-Element mit einem asymmetrischen Schlüsseln  
  
1. Erstellen Sie ein <xref:System.Security.Cryptography.CspParameters>-Objekt, und geben Sie den Namen des Schlüsselcontainers an.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#2)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#2)]  
  
2. Rufen Sie einen zuvor generierten asymmetrischen Schlüssel aus dem Schlüsselcontainer mithilfe des <xref:System.Security.Cryptography.RSACryptoServiceProvider>-Objekts ab.  Der Schlüssel wird automatisch aus dem Schlüsselcontainer abgerufen, wenn Sie das <xref:System.Security.Cryptography.CspParameters>-Objekt an den <xref:System.Security.Cryptography.RSACryptoServiceProvider>-Konstruktor übergeben.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#3)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#3)]  
  
3. Erstellen Sie ein neues <xref:System.Security.Cryptography.Xml.EncryptedXml>-Objekt, um das Dokument zu entschlüsseln.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#5)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#5)]  
  
4. Fügen Sie eine Schlüssel/Name-Zuordnung hinzu, um den RSA-Schlüssel dem Element im Dokument zuzuordnen, das entschlüsselt werden soll.   Sie müssen für den Schlüssel den Namen verwenden, den Sie beim Verschlüsseln des Dokuments verwendet haben.  Beachten Sie, dass dieser Name nicht mit dem Namen identisch ist, mit dem der Schlüssel in dem Schlüsselcontainer identifiziert wird, der in Schritt 1 angegeben wurde.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#6)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#6)]  
  
5. Rufen Sie die <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> Methode zum Entschlüsseln der <`EncryptedData`> Element.  Diese Methode verwendet den RSA-Schlüssel, um den Sitzungsschlüssel zu entschlüsseln, und verwendet diesen dann automatisch, um das XML-Element zu entschlüsseln.  Er auch automatisch ersetzt die <`EncryptedData`>-Element mit den ursprünglichen Klartext.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#7)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#7)]  
  
6. Speichern Sie das XML-Dokument.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#8)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#8)]  
  
## <a name="example"></a>Beispiel  
 Für dieses Beispiel wird angenommen, dass eine Datei namens `test.xml` im selben Verzeichnis wie das kompilierte Programm vorhanden ist.  Außerdem wird angenommen, die `test.xml` enthält ein XML‑Element, das mit den in beschriebenen Methoden verschlüsselt wurde [Vorgehensweise: Verschlüsseln von XML-Elementen mit asymmetrischen Schlüsseln](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md).  
  
 [!code-csharp[HowToDecryptXMLElementAsymmetric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#1)]
 [!code-vb[HowToDecryptXMLElementAsymmetric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
-   Um dieses Beispiel zu kompilieren, müssen Sie einen Verweis auf `System.Security.dll` einfügen.  
  
-   Fügen Sie die folgenden Namespaces hinzu: <xref:System.Xml>, <xref:System.Security.Cryptography> und <xref:System.Security.Cryptography.Xml>.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Speichern Sie einen symmetrischen kryptografischen Schlüssel nie im Klartextformat, und übertragen Sie einen symmetrischen Schlüssel nie im Klartextformat zwischen Computern.  Außerdem sollten Sie den privaten Schlüssel eines asymmetrischen Schlüsselpaars niemals in Klartext speichern oder übertragen.  Weitere Informationen über symmetrische und asymmetrische kryptografische Schlüssel finden Sie unter [Erzeugen von Schlüsseln für die Ver- und Entschlüsselung](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md).  
  
 Sie sollten einen Schlüssel niemals direkt in Ihren Quellcode einbetten.  Eingebettete Schlüssel können problemlos aus einer Assembly gelesen werden, mithilfe von [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) oder durch die Assembly in einem Text-Editor wie Editor geöffnet.  
  
 Wenn Sie einen kryptografischen Schlüssel nicht mehr benötigen, entfernen Sie ihn aus dem Arbeitsspeicher, indem Sie jedes Byte auf 0 (null) festlegen oder indem Sie die <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A>-Methode der verwalteten Kryptografieklasse aufrufen.  Kryptografische Schlüssel können manchmal von einem Debugger aus dem Arbeitsspeicher oder von einer Festplatte gelesen werden, falls der entsprechende Arbeitsspeicherbereich auf den Datenträger ausgelagert wurde.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Security.Cryptography.Xml>
- [Vorgehensweise: Entschlüsseln von XML-Elementen mit asymmetrischen Schlüsseln](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md)
