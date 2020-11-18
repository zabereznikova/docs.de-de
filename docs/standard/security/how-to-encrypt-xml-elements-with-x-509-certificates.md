---
title: 'Vorgehensweise: Verschlüsseln von XML-Elementen mit X.509-Zertifikaten'
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encryption [.NET], X.509 certificates
- cryptography [.NET], X.509 certificates
- System.Security.Cryptography.EncryptedXml class
- XML encryption
- System.Security.Cryptography.X509Certificate2 class
- X.509 certificates
- certificates, X.509 certificates
ms.assetid: 761f1c66-631c-47af-aa86-ad9c50cfa453
ms.openlocfilehash: 5007404c1e6e872c169ce7ce71425f14d20d3a25
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94820188"
---
# <a name="how-to-encrypt-xml-elements-with-x509-certificates"></a>Vorgehensweise: Verschlüsseln von XML-Elementen mit X.509-Zertifikaten

Sie können die Klassen im <xref:System.Security.Cryptography.Xml>-Namespace verwenden, um ein Element in einem XML-Dokument zu verschlüsseln.  XML-Verschlüsselung ist ein gängiges Verfahren zum Austauschen oder Speichern von verschlüsselten XML-Daten, ohne sich Gedanken machen zu müssen, dass die Daten einfach gelesen werden können.  Weitere Informationen zum XML-Verschlüsselungsstandard finden Sie in der World Wide Web Consortium (W3C)-Spezifikation für die XML-Verschlüsselung unter <https://www.w3.org/TR/xmldsig-core/> .  
  
 Sie können die XML-Verschlüsselung verwenden, um jedes XML-Element oder XML-Dokument durch ein <`EncryptedData`>-Element zu ersetzen, das die verschlüsselten XML-Daten enthält. Das <`EncryptedData`>-Element kann auch Unterelemente mit Informationen über die bei der Verschlüsselung verwendeten Schlüssel und Prozesse enthalten.  XML-Verschlüsselung unterstützt, dass ein Dokument mehrere verschlüsselte Elemente enthält und dass ein Element mehrfach verschlüsselt ist.  Das Codebeispiel in dieser Vorgehensweise veranschaulicht das Erstellen eines <`EncryptedData`>-Elements zusammen mit weiteren Unterelementen, die Sie später bei der Entschlüsselung verwenden können.  
  
In diesem Beispiel wird ein XML-Element mithilfe zweier Schlüssel verschlüsselt. Das Beispiel ruft Programm gesteuert ein Zertifikat ab und verwendet es, um ein XML-Element mithilfe der-Methode zu verschlüsseln <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> . Die <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A>-Methode erstellt intern einen separaten Sitzungsschlüssel und verwendet diesen, um das XML-Dokument zu verschlüsseln. Diese Methode verschlüsselt den Sitzungsschlüssel und speichert ihn mit dem verschlüsselten XML-Dokument in einem neuen <`EncryptedData`>-Element.  

Um das XML-Element zu entschlüsseln, rufen Sie die- <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> Methode auf, die automatisch das X. 509-Zertifikat aus dem Speicher abruft und die erforderliche Entschlüsselung ausführt.  Weitere Informationen zum Entschlüsseln eines XML-Elements, das mit dieser Vorgehensweise verschlüsselt wurde, finden Sie unter [Gewusst wie: Entschlüsseln von XML-Elementen mit X.509](how-to-decrypt-xml-elements-with-x-509-certificates.md)-Zertifikaten.  
  
Das Beispiel eignet sich für Situationen, in denen mehrere Anwendungen verschlüsselte Daten gemeinsam nutzen müssen, oder in denen eine Anwendung verschlüsselte Daten zwischen den Zeiten speichern muss, in denen sie ausgeführt wird.  
  
### <a name="to-encrypt-an-xml-element-with-an-x509-certificate"></a>So verschlüsseln Sie ein XML-Element mit einem X.509-Zertifikat  

Zum Ausführen dieses Beispiels müssen Sie ein Test Zertifikat erstellen und in einem Zertifikat Speicher speichern. Die Anweisungen für diese Aufgabe werden nur für das Windows- [Zertifikaterstellungs-Tool (Makecert.exe)](/windows/desktop/SecCrypto/makecert)bereitgestellt.

1. Verwenden Sie [Makecert.exe](/windows/desktop/SecCrypto/makecert) , um ein X. 509-Test Zertifikat zu generieren und im lokalen Benutzerspeicher zu platzieren. Sie müssen einen exportierbaren Austauschschlüssel generieren. Führen Sie den folgenden Befehl aus:  
  
    ```console  
    makecert -r -pe -n "CN=XML_ENC_TEST_CERT" -b 01/01/2020 -e 01/01/2025 -sky exchange -ss my  
    ```  
  
2. Erstellen Sie ein <xref:System.Security.Cryptography.X509Certificates.X509Store>-Objekt, und initialisieren Sie dieses, um den aktuellen Benutzerspeicher zu öffnen  
  
     [!code-csharp[HowToEncryptXMLElementX509#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#2)]
     [!code-vb[HowToEncryptXMLElementX509#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#2)]  
  
3. Öffnen Sie den Speicher im schreibgeschützten Modus.  
  
     [!code-csharp[HowToEncryptXMLElementX509#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#3)]
     [!code-vb[HowToEncryptXMLElementX509#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#3)]  
  
4. Initialisieren Sie eine <xref:System.Security.Cryptography.X509Certificates.X509Certificate2Collection> mit allen im Speicher enthaltenen Zertifikaten.  
  
     [!code-csharp[HowToEncryptXMLElementX509#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#4)]
     [!code-vb[HowToEncryptXMLElementX509#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#4)]  
  
5. Durchlaufen Sie die Zertifikate im Speicher, und suchen Sie nach dem Zertifikat mit dem entsprechenden Namen.  In diesem Beispiel hat das Zertifikat den Namen `"CN=XML_ENC_TEST_CERT"`.  
  
     [!code-csharp[HowToEncryptXMLElementX509#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#5)]
     [!code-vb[HowToEncryptXMLElementX509#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#5)]  
  
6. Schließen Sie den Speicher, nachdem Sie das Zertifikat gefunden haben.  
  
     [!code-csharp[HowToEncryptXMLElementX509#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#6)]
     [!code-vb[HowToEncryptXMLElementX509#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#6)]  
  
7. Erstellen Sie ein <xref:System.Xml.XmlDocument>-Objekt, indem Sie eine XML-Datei von einem Datenträger laden.  Das <xref:System.Xml.XmlDocument>-Objekt enthält das zu verschlüsselnde XML-Element.  
  
     [!code-csharp[HowToEncryptXMLElementX509#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#7)]
     [!code-vb[HowToEncryptXMLElementX509#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#7)]  
  
8. Suchen Sie das angegebene Element im <xref:System.Xml.XmlDocument>-Objekt, und erstellen Sie ein neues <xref:System.Xml.XmlElement>-Objekt, das dem Element entspricht, das Sie verschlüsseln möchten.  In diesem Beispiel wird das `"creditcard"`-Element verschlüsselt.  
  
     [!code-csharp[HowToEncryptXMLElementX509#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#8)]
     [!code-vb[HowToEncryptXMLElementX509#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#8)]  
  
9. Erstellen Sie eine neue Instanz der <xref:System.Security.Cryptography.Xml.EncryptedXml>-Klasse, und verwenden Sie diese, um das angegebene Element mit dem X.059-Zertifikat zu verschlüsseln .  Die <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A>-Methode gibt das verschlüsselte Element als ein <xref:System.Security.Cryptography.Xml.EncryptedData>-Objekt zurück.  
  
     [!code-csharp[HowToEncryptXMLElementX509#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#9)]
     [!code-vb[HowToEncryptXMLElementX509#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#9)]  
  
10. Ersetzen Sie das Element aus dem ursprünglichen <xref:System.Xml.XmlDocument>-Objekt durch das <xref:System.Security.Cryptography.Xml.EncryptedData>-Element.  
  
     [!code-csharp[HowToEncryptXMLElementX509#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#10)]
     [!code-vb[HowToEncryptXMLElementX509#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#10)]  
  
11. Speichern Sie das <xref:System.Xml.XmlDocument>-Objekt.  
  
     [!code-csharp[HowToEncryptXMLElementX509#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#11)]
     [!code-vb[HowToEncryptXMLElementX509#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#11)]  
  
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
  
 [!code-csharp[HowToEncryptXMLElementX509#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#1)]
 [!code-vb[HowToEncryptXMLElementX509#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
- Fügen Sie in einem Projekt, das .NET Framework als Ziel hat, einen Verweis auf ein `System.Security.dll` .

- Installieren Sie in einem Projekt, das .net Core oder .net 5 als Ziel hat, das nuget-Paket [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).
  
- Fügen Sie die folgenden Namespaces hinzu: <xref:System.Xml>, <xref:System.Security.Cryptography> und <xref:System.Security.Cryptography.Xml>.  
  
## <a name="net-security"></a>.NET-Sicherheit
  
Das in diesem Beispiel verwendete X.509-Zertifikat ist nur für Testzwecke vorgesehen.  Anwendungen sollten ein X. 509-Zertifikat verwenden, das von einer vertrauenswürdigen Zertifizierungsstelle generiert wurde.  
  
## <a name="see-also"></a>Siehe auch

- [Kryptografiemodell](cryptography-model.md)
- [Kryptografische Dienste](cryptographic-services.md)
- [Plattformübergreifende Kryptografie](cross-platform-cryptography.md)
- <xref:System.Security.Cryptography.Xml>
- [Vorgehensweise: Entschlüsseln von XML-Elementen mit X.509-Zertifikaten](how-to-decrypt-xml-elements-with-x-509-certificates.md)
- [ASP.net Core Datenschutz](/aspnet/core/security/data-protection/introduction)
