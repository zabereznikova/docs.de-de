---
title: 'Gewusst wie: Entschlüsseln von XML-Elementen mit X.509-Zertifikaten'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- System.Security.Cryptography.EncryptedXml class
- XML encryption
- System.Security.Cryptography.X509Certificate2 class
- decryption
- X.509 certificates
- certificates, X.509 certificates
ms.assetid: bd015722-d88d-408d-8ca8-e4e475c441ed
ms.openlocfilehash: 46fbefbf7a427ec0d60a34ecc2166f8499d08575
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708887"
---
# <a name="how-to-decrypt-xml-elements-with-x509-certificates"></a>Gewusst wie: Entschlüsseln von XML-Elementen mit X.509-Zertifikaten
Sie können die Klassen im <xref:System.Security.Cryptography.Xml>-Namespace verwenden, um ein Element in einem XML-Dokument zu verschlüsseln und zu entschlüsseln.  XML-Verschlüsselung ist ein gängiges Verfahren zum Austauschen oder Speichern von verschlüsselten XML-Daten, ohne sich Gedanken machen zu müssen, dass die Daten einfach gelesen werden können.  Weitere Informationen zum XML-Verschlüsselungsstandard finden Sie in der World Wide Web Consortium (W3C)-Spezifikation für die XML-Verschlüsselung unter <https://www.w3.org/TR/xmldsig-core/>.  
  
 In diesem Beispiel wird ein XML-Element entschlüsselt, das mithilfe der in: Gewusst [wie: Verschlüsseln von XML-Elementen mit X. 509-Zertifikaten](../../../docs/standard/security/how-to-encrypt-xml-elements-with-x-509-certificates.md)beschriebenen Methoden verschlüsselt wurde.  Es findet eine <`EncryptedData`>-Element, entschlüsselt das-Element und ersetzt dann das-Element durch das ursprüngliche Klartext-XML-Element.  
  
 Im Codebeispiel dieser Vorgehensweise wird ein XML-Element mithilfe eines X.059-Zertifikats entschlüsselt, das aus einem lokalen Zertifikatsspeicher des aktuellen Benutzerkontos stammt.  Im Beispiel wird die <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A>-Methode verwendet, um automatisch das X. 509-Zertifikat abzurufen und einen Sitzungsschlüssel zu entschlüsseln, der im <`EncryptedKey`> Element des <`EncryptedData`-Elements gespeichert ist.  Die <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A>-Methode verwendet anschließend automatisch den Sitzungsschlüssel, um das XML-Element zu entschlüsseln.  
  
 Das Beispiel eignet sich für Situationen, in denen mehrere Anwendungen verschlüsselte Daten gemeinsam nutzen müssen, oder in denen eine Anwendung verschlüsselte Daten zwischen den Zeiten speichern muss, in denen sie ausgeführt wird.  
  
### <a name="to-decrypt-an-xml-element-with-an-x509-certificate"></a>So entschlüsseln Sie ein XML-Element mit einem X.509-Zertifikat  
  
1. Erstellen Sie ein <xref:System.Xml.XmlDocument>-Objekt, indem Sie eine XML-Datei von einem Datenträger laden.  Das <xref:System.Xml.XmlDocument>-Objekt enthält das zu entschlüsselnde XML-Element.  
  
     [!code-csharp[HowToDecryptXMLElementX509#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#2)]
     [!code-vb[HowToDecryptXMLElementX509#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#2)]  
  
2. Erstellen Sie ein neues <xref:System.Security.Cryptography.Xml.EncryptedXml>-Objekt, indem Sie das <xref:System.Xml.XmlDocument>-Objekt an den Konstruktor übergeben.  
  
     [!code-csharp[HowToDecryptXMLElementX509#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#3)]
     [!code-vb[HowToDecryptXMLElementX509#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#3)]  
  
3. Entschlüsseln Sie das XML-Dokument mit der <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A>-Methode.  
  
     [!code-csharp[HowToDecryptXMLElementX509#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#4)]
     [!code-vb[HowToDecryptXMLElementX509#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#4)]  
  
4. Speichern Sie das <xref:System.Xml.XmlDocument>-Objekt.  
  
     [!code-csharp[HowToDecryptXMLElementX509#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#5)]
     [!code-vb[HowToDecryptXMLElementX509#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#5)]  
  
## <a name="example"></a>Beispiel  
 Für dieses Beispiel wird angenommen, dass eine Datei namens `"test.xml"` im selben Verzeichnis wie das kompilierte Programm vorhanden ist.  Außerdem wird angenommen, dass `"test.xml"` ein `"creditcard"`-Element enthält.  Sie können den folgenden XML-Code in eine Datei namens `test.xml` einfügen und mit diesem Beispiel verwenden.  
  
```xml  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
```  
  
 [!code-csharp[HowToDecryptXMLElementX509#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#1)]
 [!code-vb[HowToDecryptXMLElementX509#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
- Um dieses Beispiel zu kompilieren, müssen Sie einen Verweis auf `System.Security.dll` einfügen.  
  
- Fügen Sie die folgenden Namespaces hinzu: <xref:System.Xml>, <xref:System.Security.Cryptography> und <xref:System.Security.Cryptography.Xml>.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Das in diesem Beispiel verwendete X.509-Zertifikat ist nur für Testzwecke vorgesehen.  Anwendungen sollten ein X.059-Zertifikat verwenden, das entweder von einer vertrauenswürdigen Zertifizierungsstelle oder vom Microsoft Windows-Zertifikatsserver generiert wurde.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Security.Cryptography.Xml>
- [Gewusst wie: Verschlüsseln von XML-Elementen mit X.509-Zertifikaten](../../../docs/standard/security/how-to-encrypt-xml-elements-with-x-509-certificates.md)
