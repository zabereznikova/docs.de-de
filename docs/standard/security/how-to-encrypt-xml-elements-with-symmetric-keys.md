---
title: 'Gewusst wie: Verschlüsseln von XML-Elementen mit symmetrischen Schlüsseln'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- AES algorithm
- cryptography [.NET Framework], symmetric keys
- encryption [.NET Framework], symmetric keys
- symmetric keys
- System.Security.Cryptography.EncryptedXml class
- System.Security.Cryptography.RijndaelManaged class
- XML encryption
- Advanced Encryption Standard algorithm
- Rijndael
ms.assetid: d8461a44-aa2c-4ef4-b3e4-ab7cbaaee1b5
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b792fd6eea0a33b0143fafa03641a78947d7e127
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458075"
---
# <a name="how-to-encrypt-xml-elements-with-symmetric-keys"></a>Gewusst wie: Verschlüsseln von XML-Elementen mit symmetrischen Schlüsseln
Sie können die Klassen im <xref:System.Security.Cryptography.Xml>-Namespace verwenden, um ein Element in einem XML-Dokument zu verschlüsseln.  Die XML-Verschlüsselung ermöglicht Ihnen das Speichern oder Transportieren von vertraulichen XML-Dokumenten, ohne befürchten zu müssen, dass die Daten einfach gelesen werden können.  Diese Prozedur verschlüsselt ein XML-Element mit dem Advanced Encryption Standard (AES)-Algorithmus, auch als Rijndael bezeichnet.  
  
 Informationen zum Entschlüsseln eines XML-Elements, das mit dieser Prozedur verschlüsselt wurde, finden Sie unter Gewusst [wie: Entschlüsseln von XML-Elementen mit symmetrischen Schlüsseln](../../../docs/standard/security/how-to-decrypt-xml-elements-with-symmetric-keys.md).  
  
 Wenn Sie einen symmetrischen Algorithmus wie AES verwenden, um XML-Daten zu verschlüsseln, müssen Sie für das Verschlüsseln und Entschlüsseln der XML-Daten denselben Schlüssel verwenden.  Für das Beispiel in dieser Vorgehensweise wird angenommen, dass das verschlüsselte XML-Element mit demselben Schlüssel entschlüsselt wird und dass sich die verschlüsselnden und die entschlüsselnden Beteiligten über den zu verwendenden Algorithmus und Schlüssel verständigt haben.  In diesem Beispiel wird der AES-Schlüssel weder im verschlüsselten XML-Element gespeichert noch dort verschlüsselt.  
  
 Dieses Beispiel ist für Situationen geeignet, in denen eine einzelne Anwendung Daten auf Basis eines Sitzungsschlüssels, der sich im Arbeitsspeicher befindet, oder auf Basis eines starken kryptografischen Schlüssels verschlüsseln muss, der aus einem Kennwort abgeleitet wurde.  Für Situationen, in denen zwei oder mehr Anwendungen verschlüsselte XML-Daten gemeinsam verwenden müssen, empfiehlt sich die Verwendung eines Verschlüsselungsschemas, dem ein asymmetrischer Algorithmus oder ein X.509-Zertifikat zugrunde liegt.  
  
### <a name="to-encrypt-an-xml-element-with-a-symmetric-key"></a>So verschlüsseln Sie ein XML-Element mit einem symmetrischen Schlüssel  
  
1. Generieren Sie mit der <xref:System.Security.Cryptography.RijndaelManaged>-Klasse einen symmetrischen Schlüssel.  Dieser Schlüssel wird dazu verwendet, das XML-Element zu verschlüsseln.  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#2)]
     [!code-vb[HowToEncryptXMLElementSymmetric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#2)]  
  
2. Erstellen Sie ein <xref:System.Xml.XmlDocument>-Objekt, indem Sie eine XML-Datei von einem Datenträger laden.  Das <xref:System.Xml.XmlDocument>-Objekt enthält das zu verschlüsselnde XML-Element.  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#3)]
     [!code-vb[HowToEncryptXMLElementSymmetric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#3)]  
  
3. Suchen Sie das angegebene Element im <xref:System.Xml.XmlDocument>-Objekt, und erstellen Sie ein neues <xref:System.Xml.XmlElement>-Objekt, das dem Element entspricht, das Sie verschlüsseln möchten.  In diesem Beispiel wird das `"creditcard"`-Element verschlüsselt.  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#4)]
     [!code-vb[HowToEncryptXMLElementSymmetric#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#4)]  
  
4. Erstellen Sie eine neue Instanz der <xref:System.Security.Cryptography.Xml.EncryptedXml>-Klasse, und verwenden Sie diese Instanz, um das <xref:System.Xml.XmlElement> mit dem symmetrischen Schlüssel zu verschlüsseln.  Die <xref:System.Security.Cryptography.Xml.EncryptedXml.EncryptData%2A>-Methode gibt das verschlüsselte Element als Array von verschlüsselten Bytes zurück.  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#5)]
     [!code-vb[HowToEncryptXMLElementSymmetric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#5)]  
  
5. Erstellen Sie ein <xref:System.Security.Cryptography.Xml.EncryptedData>-Objekt, und weisen Sie ihm den URL-Bezeichner des XML-Verschlüsselungselements zu.  Dieser URL-Bezeichner teilt einem entschlüsselnden Teilnehmer mit, dass das XML-Dokument ein verschlüsseltes Element enthält.  Sie können das <xref:System.Security.Cryptography.Xml.EncryptedXml.XmlEncElementUrl>-Feld verwenden, um den URL-Bezeichner anzugeben.  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#6)]
     [!code-vb[HowToEncryptXMLElementSymmetric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#6)]  
  
6. Erstellen Sie ein <xref:System.Security.Cryptography.Xml.EncryptionMethod>-Objekt, das mit dem URL-Bezeichner des kryptografischen Algorithmus initialisiert wird, mit dem der Schlüssel generiert wurde.  Übergeben Sie das <xref:System.Security.Cryptography.Xml.EncryptionMethod>-Objekt an die <xref:System.Security.Cryptography.Xml.EncryptedType.EncryptionMethod%2A>-Eigenschaft.  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#7)]
     [!code-vb[HowToEncryptXMLElementSymmetric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#7)]  
  
7. Fügen Sie die verschlüsselten Elementdaten dem <xref:System.Security.Cryptography.Xml.EncryptedData>-Objekt hinzu.  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#8)]
     [!code-vb[HowToEncryptXMLElementSymmetric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#8)]  
  
8. Ersetzen Sie das Element aus dem ursprünglichen <xref:System.Xml.XmlDocument>-Objekt durch das <xref:System.Security.Cryptography.Xml.EncryptedData>-Element.  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#9)]
     [!code-vb[HowToEncryptXMLElementSymmetric#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#9)]  
  
## <a name="example"></a>Beispiel  
  
```xml  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
```  
  
 [!code-csharp[HowToEncryptXMLElementSymmetric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#1)]
 [!code-vb[HowToEncryptXMLElementSymmetric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
- Um dieses Beispiel zu kompilieren, müssen Sie einen Verweis auf `System.Security.dll` einfügen.  
  
- Fügen Sie die folgenden Namespaces hinzu: <xref:System.Xml>, <xref:System.Security.Cryptography> und <xref:System.Security.Cryptography.Xml>.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Speichern Sie einen kryptografischen Schlüssel nie im Klartextformat, und übertragen Sie einen Schlüssel nie im Klartextformat zwischen Computern.  Verwenden Sie stattdessen einen sicheren Schlüsselcontainer, um kryptografische Schlüssel zu speichern.  
  
 Wenn Sie einen kryptografischen Schlüssel nicht mehr benötigen, entfernen Sie ihn aus dem Arbeitsspeicher, indem Sie jedes Byte auf 0 (null) festlegen oder indem Sie die <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A>-Methode der verwalteten Kryptografieklasse aufrufen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Security.Cryptography.Xml>
- [Gewusst wie: Entschlüsseln von XML-Elementen mit symmetrischen Schlüsseln](../../../docs/standard/security/how-to-decrypt-xml-elements-with-symmetric-keys.md)
