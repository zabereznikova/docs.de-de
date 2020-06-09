---
title: 'Vorgehensweise: Sichern eines Diensts mit einem X.509-Zertifikat'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2d06c2aa-d0d7-4e5e-ad7e-77416aa1c10b
ms.openlocfilehash: 10d6db63368ee55040f85f922b9483982e8ff264
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596967"
---
# <a name="how-to-secure-a-service-with-an-x509-certificate"></a>Vorgehensweise: Sichern eines Diensts mit einem X.509-Zertifikat
Das Sichern eines Dienstanbieter mit einem X. 509-Zertifikat ist eine grundlegende Technik, die von den meisten Bindungen in Windows Communication Foundation (WCF) verwendet wird. Dieses Thema führt durch die Schritte der Konfiguration eines selbst gehosteten Diensts mit einem X.509-Zertifikat.  
  
 Eine Voraussetzung ist ein gültiges Zertifikat, das zur Authentifizierung des Diensts verwendet werden kann. Das Zertifikat muss von einer vertrauenswürdigen Zertifizierungsstelle zum Server ausgegeben werden. Wenn das Zertifikat ungültig ist, vertrauen die Clients, die versuchen, den Dienst zu verwenden, dem Dienst nicht, und es wird keine Verbindung aufgebaut. Weitere Informationen zur Verwendung von Zertifikaten finden Sie unter [Arbeiten mit Zertifikaten](working-with-certificates.md).  
  
### <a name="to-configure-a-service-with-a-certificate-using-code"></a>So konfigurieren Sie einen Dienst mit einem Zertifikat mithilfe von Code  
  
1. Erstellen Sie den Dienstvertrag und den implementierten Dienst. Weitere Informationen finden Sie unter [Entwerfen und Implementieren von Diensten](../designing-and-implementing-services.md).  
  
2. Erstellen Sie eine Instanz der <xref:System.ServiceModel.WSHttpBinding>-Klasse, und legen Sie deren Sicherheitsmodus auf <xref:System.ServiceModel.SecurityMode.Message> fest. Dies wird im folgenden Code veranschaulicht.  
  
     [!code-csharp[C_SecureWithCertificate#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#1)]
     [!code-vb[C_SecureWithCertificate#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#1)]  
  
3. Erstellen Sie zwei <xref:System.Type>-Variablen, je eine für den Vertragstyp und den implementierten Vertrag. Dies wird im folgenden Code veranschaulicht.  
  
     [!code-csharp[C_SecureWithCertificate#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#2)]
     [!code-vb[C_SecureWithCertificate#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#2)]  
  
4. Erstellen Sie eine Instanz der <xref:System.Uri>-Klasse für die Basisadresse des Diensts. Da den `WSHttpBinding` http-Transport verwendet, muss der Uniform Resource Identifier (URI) mit diesem Schema beginnen, oder Windows Communication Foundation (WCF) löst eine Ausnahme aus, wenn der Dienst geöffnet wird.  
  
     [!code-csharp[C_SecureWithCertificate#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#3)]
     [!code-vb[C_SecureWithCertificate#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#3)]  
  
5. Erstellen Sie eine neue Instanz der <xref:System.ServiceModel.ServiceHost>-Klasse mit der Variablen des implementierten Vertragstyps und dem URI.  
  
     [!code-csharp[C_SecureWithCertificate#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#4)]
     [!code-vb[C_SecureWithCertificate#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#4)]  
  
6. Fügen Sie einen <xref:System.ServiceModel.Description.ServiceEndpoint> zum Dienst hinzu, indem Sie die <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>-Methode verwenden. Übergeben Sie den Vertrag, die Bindung und eine Endpunktadresse an den Konstruktor. Dies wird im folgenden Code veranschaulicht.  
  
     [!code-csharp[C_SecureWithCertificate#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#5)]
     [!code-vb[C_SecureWithCertificate#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#5)]  
  
7. Optional. Um Metadaten vom Dienst abzufragen, erstellen Sie ein neues <xref:System.ServiceModel.Description.ServiceMetadataBehavior>-Objekt und legen Sie die <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A>-Eigenschaft auf `true` fest.  
  
     [!code-csharp[C_SecureWithCertificate#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#6)]
     [!code-vb[C_SecureWithCertificate#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#6)]  
  
8. Verwenden Sie die <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>-Methode der <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>-Klasse, um das gültige Zertifikat zum Dienst hinzuzufügen. Die Methode kann eine von diversen Methoden nutzen, um ein Zertifikat zu suchen. In diesem Beispiel wird die <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindBySubjectName>-Enumeration verwendet. Die Enumeration gibt an, dass der gelieferte Wert der Name der Entität ist, an die das Zertifikat herausgegeben wurde.  
  
     [!code-csharp[C_SecureWithCertificate#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#7)]
     [!code-vb[C_SecureWithCertificate#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#7)]  
  
9. Rufen Sie die <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>-Methode auf, um die Dienstüberwachung zu starten. Sollten Sie eine Konsolenanwendung erstellen, rufen Sie die <xref:System.Console.ReadLine%2A>-Methode auf, um den Dienst im Überwachungsstatus zu halten.  
  
     [!code-csharp[C_SecureWithCertificate#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#8)]
     [!code-vb[C_SecureWithCertificate#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#8)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>-Methode verwendet, um einen Dienst mit einem X.509-Zertifikat zu konfigurieren.  
  
 [!code-csharp[C_SecureWithCertificate#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#9)]
 [!code-vb[C_SecureWithCertificate#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#9)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Die folgenden Namespaces sind zum Kompilieren des Codes erforderlich:  
  
- <xref:System>  
  
- <xref:System.ServiceModel>  
  
- <xref:System.ServiceModel.Channels>  
  
- <xref:System.Web.Services.Description>  
  
- <xref:System.Security.Cryptography.X509Certificates>  
  
- <xref:System.Runtime.Serialization>  
  
## <a name="see-also"></a>Weitere Informationen

- [Verwenden von Zertifikaten](working-with-certificates.md)
