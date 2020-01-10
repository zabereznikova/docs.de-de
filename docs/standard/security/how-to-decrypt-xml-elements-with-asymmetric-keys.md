---
title: 'Gewusst wie: Entschlüsseln von XML-Elementen mit asymmetrischen Schlüsseln'
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
ms.openlocfilehash: 5ed1e2eb2518366da0a57655d7a8691e23f725d5
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706135"
---
# <a name="how-to-decrypt-xml-elements-with-asymmetric-keys"></a>Gewusst wie: Entschlüsseln von XML-Elementen mit asymmetrischen Schlüsseln
Sie können die Klassen im <xref:System.Security.Cryptography.Xml>-Namespace verwenden, um ein Element in einem XML-Dokument zu verschlüsseln und zu entschlüsseln.  XML-Verschlüsselung ist ein gängiges Verfahren zum Austauschen oder Speichern von verschlüsselten XML-Daten, ohne sich Gedanken machen zu müssen, dass die Daten einfach gelesen werden können.  Weitere Informationen zum XML-Verschlüsselungsstandard finden Sie unter World Wide Web Consortium (W3C) Empfehlungs [Syntax für XML-Signaturen und Verarbeitung](https://www.w3.org/TR/xmldsig-core/).  
  
 Im Beispiel in dieser Prozedur wird ein XML-Element entschlüsselt, das mithilfe der in Gewusst [wie: Verschlüsseln von XML-Elementen mit asymmetrischen Schlüsseln](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md)beschriebenen Methoden verschlüsselt wurde.  Es findet eine <`EncryptedData`>-Element, entschlüsselt das-Element und ersetzt dann das-Element durch das ursprüngliche Klartext-XML-Element.  
  
 In diesem Beispiel wird ein XML-Element mithilfe zweier Schlüssel entschlüsselt.  Dabei wird ein zuvor generierter anderer RSA-Schlüssel aus einem Schlüssel Container abgerufen. Anschließend wird der RSA-Schlüssel verwendet, um einen Sitzungsschlüssel zu entschlüsseln, der im <`EncryptedKey`>-Element des <`EncryptedData`>-Elements gespeichert ist.  In dem Beispiel wird dann der Sitzungsschlüssel verwendet, um das XML-Element zu entschlüsseln.  
  
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
  
4. Fügen Sie eine Schlüssel/Name-Zuordnung hinzu, um den RSA-Schlüssel dem Element im Dokument zuzuordnen, das entschlüsselt werden soll.  Sie müssen für den Schlüssel den Namen verwenden, den Sie beim Verschlüsseln des Dokuments verwendet haben.  Beachten Sie, dass dieser Name nicht mit dem Namen identisch ist, mit dem der Schlüssel in dem Schlüsselcontainer identifiziert wird, der in Schritt 1 angegeben wurde.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#6)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#6)]  
  
5. Ruft die <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A>-Methode auf, um die <`EncryptedData`> Element zu entschlüsseln.  Diese Methode verwendet den RSA-Schlüssel, um den Sitzungsschlüssel zu entschlüsseln, und verwendet diesen dann automatisch, um das XML-Element zu entschlüsseln.  Außerdem wird der <`EncryptedData`>-Element automatisch durch den ursprünglichen Klartext ersetzt.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#7)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#7)]  
  
6. Speichern Sie das XML-Dokument.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#8)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#8)]  
  
## <a name="example"></a>Beispiel  
 Für dieses Beispiel wird angenommen, dass eine Datei namens `test.xml` im selben Verzeichnis wie das kompilierte Programm vorhanden ist.  Außerdem wird davon ausgegangen, dass `test.xml` ein XML-Element enthält, das mithilfe der in Gewusst [wie: Verschlüsseln von XML-Elementen mit asymmetrischen Schlüsseln](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md)beschriebenen Verfahren verschlüsselt wurde.  
  
 [!code-csharp[HowToDecryptXMLElementAsymmetric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#1)]
 [!code-vb[HowToDecryptXMLElementAsymmetric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
- Um dieses Beispiel zu kompilieren, müssen Sie einen Verweis auf `System.Security.dll` einfügen.  
  
- Fügen Sie die folgenden Namespaces hinzu: <xref:System.Xml>, <xref:System.Security.Cryptography> und <xref:System.Security.Cryptography.Xml>.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Speichern Sie einen symmetrischen kryptografischen Schlüssel nie im Klartextformat, und übertragen Sie einen symmetrischen Schlüssel nie im Klartextformat zwischen Computern.  Außerdem sollten Sie den privaten Schlüssel eines asymmetrischen Schlüsselpaars niemals in Klartext speichern oder übertragen.  Weitere Informationen zu symmetrischen und asymmetrischen Kryptografieschlüsseln finden Sie unter [Erstellen von Schlüsseln für die Verschlüsselung und Entschlüsselung](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md).  
  
 Sie sollten einen Schlüssel niemals direkt in Ihren Quellcode einbetten.  Eingebettete Schlüssel können problemlos aus einer Assembly gelesen werden, indem [Ildasm. exe (IL-Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) verwendet oder die Assembly in einem Text-Editor wie Editor geöffnet wird.  
  
 Wenn Sie einen kryptografischen Schlüssel nicht mehr benötigen, entfernen Sie ihn aus dem Arbeitsspeicher, indem Sie jedes Byte auf 0 (null) festlegen oder indem Sie die <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A>-Methode der verwalteten Kryptografieklasse aufrufen.  Kryptografische Schlüssel können manchmal von einem Debugger aus dem Arbeitsspeicher oder von einer Festplatte gelesen werden, falls der entsprechende Arbeitsspeicherbereich auf den Datenträger ausgelagert wurde.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Security.Cryptography.Xml>
- [Gewusst wie: Verschlüsseln von XML-Elementen mit asymmetrischen Schlüsseln](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md)
