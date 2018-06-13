---
title: Unterschiede zwischen von Internet Explorer und WCF durchgeführter Dienstzertifikatsvalidierung
ms.date: 03/30/2017
helpviewer_keywords:
- service certificate validation [WCF]
- certificates [WCF], service certificate validation
ms.assetid: 9dffcab2-70a9-40f0-99fd-d3a0b296028f
ms.openlocfilehash: ecc2b16eae5428e305f5f6096d6d7994256d86c2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33488685"
---
# <a name="differences-between-service-certificate-validation-done-by-internet-explorer-and-wcf"></a><span data-ttu-id="8a0e1-102">Unterschiede zwischen von Internet Explorer und WCF durchgeführter Dienstzertifikatsvalidierung</span><span class="sxs-lookup"><span data-stu-id="8a0e1-102">Differences Between Service Certificate Validation Done by Internet Explorer and WCF</span></span>
<span data-ttu-id="8a0e1-103">Aufgrund der Unterschied zwischen der von Internet Explorer und Windows Communication Foundation (WCF)-Dienstzertifikate überprüfen, wenn HTTPS verwendet wird, ist es möglich, dass Internet Explorer nicht auf die Hilfeseite oder Web Services Description Language zugreifen (WSDL) eines Diensts, obwohl ein WCF-Client erfolgreich kann Nachrichten an die Dienstendpunkte.</span><span class="sxs-lookup"><span data-stu-id="8a0e1-103">Because of difference between the way Internet Explorer and Windows Communication Foundation (WCF) validate service certificates when HTTPS is used, it is possible that Internet Explorer will not be able to access the Help page or Web Services Description Language (WSDL) of a service even though a WCF client is able to successfully send messages to the service endpoints.</span></span> <span data-ttu-id="8a0e1-104">Grund hierfür ist, Internet Explorer überprüft, ob das Dienstzertifikat enthält die `ServerAuthentication` -Objektbezeichner (OIDS) in den verbesserten Verwendungsflags, wohingegen WCF eine solche Einschränkung nicht erzwingt.</span><span class="sxs-lookup"><span data-stu-id="8a0e1-104">This is because Internet Explorer checks whether the service certificate has the `ServerAuthentication` object identifiers (OID) in the enhanced usage flags, whereas WCF does not enforce such a constraint.</span></span> <span data-ttu-id="8a0e1-105">Wenn Internet Explorer nicht auf die Diensthilfeseite oder die WSDL für den Dienst zugreifen kann, verwenden Sie die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) Zugriff auf die Dienstmetadaten.</span><span class="sxs-lookup"><span data-stu-id="8a0e1-105">If Internet Explorer is unable to access the service Help page or the WSDL for the service, use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to access the service metadata.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a0e1-106">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8a0e1-106">See Also</span></span>  
 [<span data-ttu-id="8a0e1-107">Unterschiede bei der Zertifikatvalidierung zwischen HTTPS, SSL über TCP und SOAP-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="8a0e1-107">Certificate Validation Differences Between HTTPS, SSL over TCP, and SOAP Security</span></span>](../../../../docs/framework/wcf/feature-details/cert-val-diff-https-ssl-over-tcp-and-soap.md)  
 [<span data-ttu-id="8a0e1-108">Vorgehensweise: Abrufen von Metadaten und Implementieren eines kompatiblen Diensts</span><span class="sxs-lookup"><span data-stu-id="8a0e1-108">How to: Retrieve Metadata and Implement a Compliant Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)
