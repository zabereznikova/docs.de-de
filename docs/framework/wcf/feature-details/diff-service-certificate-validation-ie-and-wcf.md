---
title: Unterschiede zwischen von Internet Explorer und WCF durchgeführter Dienstzertifikatsvalidierung
ms.date: 03/30/2017
helpviewer_keywords:
- service certificate validation [WCF]
- certificates [WCF], service certificate validation
ms.assetid: 9dffcab2-70a9-40f0-99fd-d3a0b296028f
ms.openlocfilehash: 08a790dbbc8bc51a1e47bbcbcf90ec7c035bf3df
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549784"
---
# <a name="differences-between-service-certificate-validation-done-by-internet-explorer-and-wcf"></a><span data-ttu-id="b0fb5-102">Unterschiede zwischen von Internet Explorer und WCF durchgeführter Dienstzertifikatsvalidierung</span><span class="sxs-lookup"><span data-stu-id="b0fb5-102">Differences Between Service Certificate Validation Done by Internet Explorer and WCF</span></span>
<span data-ttu-id="b0fb5-103">Aufgrund der Unterschiede zwischen die Möglichkeit, die Internet Explorer und Windows Communication Foundation (WCF)-Dienstzertifikate überprüfen, wenn HTTPS verwendet wird, ist es möglich, dass Internet Explorer nicht auf die Hilfeseite oder Web Services Description Language zugreifen (WSDL) eines Diensts, obwohl ein WCF-Client erfolgreich kann Senden von Nachrichten an die Dienstendpunkte.</span><span class="sxs-lookup"><span data-stu-id="b0fb5-103">Because of difference between the way Internet Explorer and Windows Communication Foundation (WCF) validate service certificates when HTTPS is used, it is possible that Internet Explorer will not be able to access the Help page or Web Services Description Language (WSDL) of a service even though a WCF client is able to successfully send messages to the service endpoints.</span></span> <span data-ttu-id="b0fb5-104">Grund hierfür ist Internet Explorer überprüft, ob das Dienstzertifikat verfügt die `ServerAuthentication` -Objektbezeichner (OIDS) in die erweiterte Schlüsselverwendung Usage-Flags, wohingegen WCF eine solche Einschränkung nicht erzwingt.</span><span class="sxs-lookup"><span data-stu-id="b0fb5-104">This is because Internet Explorer checks whether the service certificate has the `ServerAuthentication` object identifiers (OID) in the enhanced usage flags, whereas WCF does not enforce such a constraint.</span></span> <span data-ttu-id="b0fb5-105">Wenn Internet Explorer die Hilfeseite oder WSDL für den Dienst zugreifen kann, verwenden Sie die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) Zugriff auf die Dienstmetadaten.</span><span class="sxs-lookup"><span data-stu-id="b0fb5-105">If Internet Explorer is unable to access the service Help page or the WSDL for the service, use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to access the service metadata.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0fb5-106">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0fb5-106">See also</span></span>
- [<span data-ttu-id="b0fb5-107">Unterschiede bei der Zertifikatvalidierung zwischen HTTPS, SSL über TCP und SOAP-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="b0fb5-107">Certificate Validation Differences Between HTTPS, SSL over TCP, and SOAP Security</span></span>](../../../../docs/framework/wcf/feature-details/cert-val-diff-https-ssl-over-tcp-and-soap.md)
- [<span data-ttu-id="b0fb5-108">Vorgehensweise: Abrufen von Metadaten und Implementieren eines kompatiblen Diensts</span><span class="sxs-lookup"><span data-stu-id="b0fb5-108">How to: Retrieve Metadata and Implement a Compliant Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)
