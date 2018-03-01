---
title: "Unterschiede bei der Zertifikatsvalidierung zwischen HTTPS, SSL über TCP und SOAP-Sicherheit"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- certificates [WCF], validation differences
ms.assetid: 953a219f-4745-4019-9894-c70704f352e6
caps.latest.revision: 
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: 34be2fbc5b8148d7bfdeb5e5d07e5b73ac89a97e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="certificate-validation-differences-between-https-ssl-over-tcp-and-soap-security"></a><span data-ttu-id="7e5cf-102">Unterschiede bei der Zertifikatsvalidierung zwischen HTTPS, SSL über TCP und SOAP-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="7e5cf-102">Certificate Validation Differences Between HTTPS, SSL over TCP, and SOAP Security</span></span>
<span data-ttu-id="7e5cf-103">Sie können in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Zertifikate mit Sicherheit (SOAP) auf Nachrichtenebene neben der Transport Layer Security (TLS) über HTTP (HTTPS) oder TCP verwenden.</span><span class="sxs-lookup"><span data-stu-id="7e5cf-103">You can use certificates in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] with message-layer (SOAP) security in addition to transport-layer security (TLS) over HTTP (HTTPS) or TCP.</span></span> <span data-ttu-id="7e5cf-104">In diesem Thema werden die Unterschiede bei der Überprüfung solcher Zertifikate beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7e5cf-104">This topic describes differences in the way such certificates are validated.</span></span>  
  
## <a name="validation-of-https-client-certificates"></a><span data-ttu-id="7e5cf-105">Validierung der HTTPS-Clientzertifikate</span><span class="sxs-lookup"><span data-stu-id="7e5cf-105">Validation of HTTPS Client Certificates</span></span>  
 <span data-ttu-id="7e5cf-106">Wenn Sie HTTPS zur Kommunikation zwischen einem Client und einem Dienst verwenden, muss das Zertifikat, das der Client zur Authentifizierung für den Dienst verwendet, Vertrauensketten unterstützen.</span><span class="sxs-lookup"><span data-stu-id="7e5cf-106">When using HTTPS to communicate between a client and a service, the certificate that the client uses to authenticate to the service must support chain trust.</span></span> <span data-ttu-id="7e5cf-107">Es muss eine Verkettung zu einer vertrauenswerten Stammzertifizierungsstelle herstellen,</span><span class="sxs-lookup"><span data-stu-id="7e5cf-107">That is, it must chain to a trusted root certificate authority.</span></span> <span data-ttu-id="7e5cf-108">anderenfalls gibt die HTTP-Ebene eine <xref:System.Net.WebException> mit der Meldung "Der Remoteserver hat einen Fehler zurückgegeben: (403) Unzulässig" aus.</span><span class="sxs-lookup"><span data-stu-id="7e5cf-108">If not, the HTTP layer raises a <xref:System.Net.WebException> with the message "The remote server returned an error: (403) Forbidden."</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7e5cf-109"> gibt diese Ausnahme als <xref:System.ServiceModel.Security.MessageSecurityException> aus.</span><span class="sxs-lookup"><span data-stu-id="7e5cf-109"> surfaces this exception as a <xref:System.ServiceModel.Security.MessageSecurityException>.</span></span>  
  
## <a name="validation-of-https-service-certificates"></a><span data-ttu-id="7e5cf-110">Validierung der HTTPS-Dienstzertifikate</span><span class="sxs-lookup"><span data-stu-id="7e5cf-110">Validation of HTTPS Service Certificates</span></span>  
 <span data-ttu-id="7e5cf-111">Wenn Sie HTTPS zur Kommunikation zwischen einem Client und einem Dienst verwenden, muss das Zertifikat, mit dem der Server die Authentifizierung durchführt, standardmäßig Vertrauensketten unterstützen.</span><span class="sxs-lookup"><span data-stu-id="7e5cf-111">When using HTTPS to communicate between a client and a service, the certificate that the server authenticates with must support chain trust by default.</span></span> <span data-ttu-id="7e5cf-112">Es muss eine Verkettung zu einer vertrauenswerten Stammzertifizierungsstelle herstellen,</span><span class="sxs-lookup"><span data-stu-id="7e5cf-112">That is, it must chain to a trusted root certificate authority.</span></span> <span data-ttu-id="7e5cf-113">Es wird keine Online-Überprüfung durchgeführt, um herauszufinden, ob das Zertifikat widerrufen wurde.</span><span class="sxs-lookup"><span data-stu-id="7e5cf-113">No online check is performed to see whether the certificate has been revoked.</span></span> <span data-ttu-id="7e5cf-114">Sie können dieses Verhalten auch überschreiben, indem Sie einen <xref:System.Net.Security.RemoteCertificateValidationCallback>-Rückruf registrieren, wie mit dem nachfolgenden Code dargestellt.</span><span class="sxs-lookup"><span data-stu-id="7e5cf-114">You can override this behavior by registering a <xref:System.Net.Security.RemoteCertificateValidationCallback> callback, as shown in the following code.</span></span>  
  
 [!code-csharp[c_CertificateValidationDifferences#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_certificatevalidationdifferences/cs/source.cs#1)] 
 [!code-vb[c_CertificateValidationDifferences#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_certificatevalidationdifferences/vb/source.vb#1)]  
  
 <span data-ttu-id="7e5cf-115">Die Signatur für `ValidateServerCertificate` sieht folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="7e5cf-115">where the signature for `ValidateServerCertificate` is as follows:</span></span>  
  
 [!code-csharp[c_CertificateValidationDifferences#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_certificatevalidationdifferences/cs/source.cs#2)]
 [!code-vb[c_CertificateValidationDifferences#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_certificatevalidationdifferences/vb/source.vb#2)]  
  
 <span data-ttu-id="7e5cf-116">Durch die Implementierung des `ValidateServerCertificate` können beliebige Überprüfungen durchgeführt werden, die der Entwickler der Clientanwendung für notwendig erachtet, um das Dienstzertifikat zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="7e5cf-116">Implementing `ValidateServerCertificate` can perform any checks that the client application developer deems necessary to validate the service certificate.</span></span>  
  
## <a name="validation-of-client-certificates-in-ssl-over-tcp-or-soap-security"></a><span data-ttu-id="7e5cf-117">Validierung der Clientzertifikate in SSL-über-TCP-Sicherheit oder SOAP-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="7e5cf-117">Validation of Client Certificates in SSL over TCP or SOAP Security</span></span>  
 <span data-ttu-id="7e5cf-118">Wenn Sie Secure Sockets Layer (SSL) über TCP oder die Nachrichtensicherheit (SOAP) verwenden, werden Clientzertifikate anhand des <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A>-Eigenschaftswerts der <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>-Klasse überprüft.</span><span class="sxs-lookup"><span data-stu-id="7e5cf-118">When using Secure Sockets Layer (SSL) over TCP or message (SOAP) security, client certificates are validated according to the <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A> property value of the <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication> class.</span></span> <span data-ttu-id="7e5cf-119">Die Eigenschaft wird auf einen der <xref:System.ServiceModel.Security.X509CertificateValidationMode>-Werte festgelegt.</span><span class="sxs-lookup"><span data-stu-id="7e5cf-119">The property is set to one of the <xref:System.ServiceModel.Security.X509CertificateValidationMode> values.</span></span> <span data-ttu-id="7e5cf-120">Die Sperrüberprüfung kann anhand der Werte des <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.RevocationMode%2A>-Eigenschaftswerts der <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>-Klasse durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="7e5cf-120">Revocation checking is performed according to the values of the <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.RevocationMode%2A> property value of the <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication> class.</span></span> <span data-ttu-id="7e5cf-121">Die Eigenschaft wird auf einen der <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>-Werte festgelegt.</span><span class="sxs-lookup"><span data-stu-id="7e5cf-121">The property is set to one of the <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> values.</span></span>  
  
 [!code-csharp[c_CertificateValidationDifferences#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_certificatevalidationdifferences/cs/source.cs#3)]
 [!code-vb[c_CertificateValidationDifferences#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_certificatevalidationdifferences/vb/source.vb#3)]  
  
## <a name="validation-of-service-certificate-in-ssl-over-tcp-and-soap-security"></a><span data-ttu-id="7e5cf-122">Validierung der Dienstzertifikate in SSL-über-TCP-Sicherheit und SOAP-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="7e5cf-122">Validation of Service Certificate in SSL over TCP and SOAP Security</span></span>  
 <span data-ttu-id="7e5cf-123">Wenn Sie SSL über TCP oder die (SOAP)-Nachrichtensicherheit verwenden, werden Dienstzertifikate anhand des <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A>-Eigenschaftswerts der <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>-Klasse überprüft.</span><span class="sxs-lookup"><span data-stu-id="7e5cf-123">When using SSL over TCP or (SOAP) message security, service certificates are validated according to the <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> property value of the <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication> class.</span></span> <span data-ttu-id="7e5cf-124">Die Eigenschaft wird auf einen der <xref:System.ServiceModel.Security.X509CertificateValidationMode>-Werte festgelegt.</span><span class="sxs-lookup"><span data-stu-id="7e5cf-124">The property is set to one of the <xref:System.ServiceModel.Security.X509CertificateValidationMode> values.</span></span>  
  
 <span data-ttu-id="7e5cf-125">Die Sperrüberprüfung kann anhand der Werte des <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.RevocationMode%2A>-Eigenschaftswerts der <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>-Klasse durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="7e5cf-125">Revocation checking is performed according to the values of the <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.RevocationMode%2A> property value of the <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication> class.</span></span> <span data-ttu-id="7e5cf-126">Die Eigenschaft wird auf einen der <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>-Werte festgelegt.</span><span class="sxs-lookup"><span data-stu-id="7e5cf-126">The property is set to one of the <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> values.</span></span>  
  
 [!code-csharp[c_CertificateValidationDifferences#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_certificatevalidationdifferences/cs/source.cs#4)]
 [!code-vb[c_CertificateValidationDifferences#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_certificatevalidationdifferences/vb/source.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="7e5cf-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7e5cf-127">See Also</span></span>  
 <xref:System.Net.Security.RemoteCertificateValidationCallback>  
 [<span data-ttu-id="7e5cf-128">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="7e5cf-128">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
