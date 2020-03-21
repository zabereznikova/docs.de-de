---
title: Unterschiede bei der Zertifikatsvalidierung zwischen HTTPS, SSL über TCP und SOAP-Sicherheit
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- certificates [WCF], validation differences
ms.assetid: 953a219f-4745-4019-9894-c70704f352e6
ms.openlocfilehash: 0e82d1898bec7cda474a5a92958b5af1b30c9de7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185405"
---
# <a name="certificate-validation-differences-between-https-ssl-over-tcp-and-soap-security"></a>Unterschiede bei der Zertifikatsvalidierung zwischen HTTPS, SSL über TCP und SOAP-Sicherheit
Sie können Zertifikate in Windows Communication Foundation (WCF) mit Message-Layer(SOAP)-Sicherheit zusätzlich zur Transport-Layer-Sicherheit (TLS) über HTTP (HTTPS) oder TCP verwenden. In diesem Thema werden die Unterschiede bei der Überprüfung solcher Zertifikate beschrieben.  
  
## <a name="validation-of-https-client-certificates"></a>Validierung der HTTPS-Clientzertifikate  
 Wenn Sie HTTPS zur Kommunikation zwischen einem Client und einem Dienst verwenden, muss das Zertifikat, das der Client zur Authentifizierung für den Dienst verwendet, Vertrauensketten unterstützen. Es muss eine Verkettung zu einer vertrauenswerten Stammzertifizierungsstelle herstellen, anderenfalls gibt die HTTP-Ebene eine <xref:System.Net.WebException> mit der Meldung "Der Remoteserver hat einen Fehler zurückgegeben: (403) Unzulässig" aus. WCF stellt diese <xref:System.ServiceModel.Security.MessageSecurityException>Ausnahme als an.  
  
## <a name="validation-of-https-service-certificates"></a>Validierung der HTTPS-Dienstzertifikate  
 Wenn Sie HTTPS zur Kommunikation zwischen einem Client und einem Dienst verwenden, muss das Zertifikat, mit dem der Server die Authentifizierung durchführt, standardmäßig Vertrauensketten unterstützen. Es muss eine Verkettung zu einer vertrauenswerten Stammzertifizierungsstelle herstellen, Es wird keine Online-Überprüfung durchgeführt, um herauszufinden, ob das Zertifikat widerrufen wurde. Sie können dieses Verhalten auch überschreiben, indem Sie einen <xref:System.Net.Security.RemoteCertificateValidationCallback>-Rückruf registrieren, wie mit dem nachfolgenden Code dargestellt.  
  
 [!code-csharp[c_CertificateValidationDifferences#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_certificatevalidationdifferences/cs/source.cs#1)]
 [!code-vb[c_CertificateValidationDifferences#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_certificatevalidationdifferences/vb/source.vb#1)]  
  
 Die Signatur für `ValidateServerCertificate` sieht folgendermaßen aus:  
  
 [!code-csharp[c_CertificateValidationDifferences#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_certificatevalidationdifferences/cs/source.cs#2)]
 [!code-vb[c_CertificateValidationDifferences#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_certificatevalidationdifferences/vb/source.vb#2)]  
  
 Durch die Implementierung des `ValidateServerCertificate` können beliebige Überprüfungen durchgeführt werden, die der Entwickler der Clientanwendung für notwendig erachtet, um das Dienstzertifikat zu überprüfen.  
  
## <a name="validation-of-client-certificates-in-ssl-over-tcp-or-soap-security"></a>Validierung der Clientzertifikate in SSL-über-TCP-Sicherheit oder SOAP-Sicherheit  
 Wenn Sie Secure Sockets Layer (SSL) über TCP oder die Nachrichtensicherheit (SOAP) verwenden, werden Clientzertifikate anhand des <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A>-Eigenschaftswerts der <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>-Klasse überprüft. Die Eigenschaft wird auf einen der <xref:System.ServiceModel.Security.X509CertificateValidationMode>-Werte festgelegt. Die Sperrüberprüfung kann anhand der Werte des <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.RevocationMode%2A>-Eigenschaftswerts der <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>-Klasse durchgeführt werden. Die Eigenschaft wird auf einen der <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>-Werte festgelegt.  
  
 [!code-csharp[c_CertificateValidationDifferences#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_certificatevalidationdifferences/cs/source.cs#3)]
 [!code-vb[c_CertificateValidationDifferences#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_certificatevalidationdifferences/vb/source.vb#3)]  
  
## <a name="validation-of-service-certificate-in-ssl-over-tcp-and-soap-security"></a>Validierung der Dienstzertifikate in SSL-über-TCP-Sicherheit und SOAP-Sicherheit  
 Wenn Sie SSL über TCP oder die (SOAP)-Nachrichtensicherheit verwenden, werden Dienstzertifikate anhand des <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A>-Eigenschaftswerts der <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>-Klasse überprüft. Die Eigenschaft wird auf einen der <xref:System.ServiceModel.Security.X509CertificateValidationMode>-Werte festgelegt.  
  
 Die Sperrüberprüfung kann anhand der Werte des <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.RevocationMode%2A>-Eigenschaftswerts der <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>-Klasse durchgeführt werden. Die Eigenschaft wird auf einen der <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>-Werte festgelegt.  
  
 [!code-csharp[c_CertificateValidationDifferences#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_certificatevalidationdifferences/cs/source.cs#4)]
 [!code-vb[c_CertificateValidationDifferences#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_certificatevalidationdifferences/vb/source.vb#4)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Net.Security.RemoteCertificateValidationCallback>
- [Verwenden von Zertifikaten](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
