---
title: Unterschiede zwischen von Internet Explorer und WCF durchgeführter Dienstzertifikatsvalidierung
ms.date: 03/30/2017
helpviewer_keywords:
- service certificate validation [WCF]
- certificates [WCF], service certificate validation
ms.assetid: 9dffcab2-70a9-40f0-99fd-d3a0b296028f
ms.openlocfilehash: 151075f2894b895ab90418748df9face3aa70252
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599190"
---
# <a name="differences-between-service-certificate-validation-done-by-internet-explorer-and-wcf"></a><span data-ttu-id="78b93-102">Unterschiede zwischen von Internet Explorer und WCF durchgeführter Dienstzertifikatsvalidierung</span><span class="sxs-lookup"><span data-stu-id="78b93-102">Differences Between Service Certificate Validation Done by Internet Explorer and WCF</span></span>
<span data-ttu-id="78b93-103">Aufgrund der Differenz zwischen der Art und Weise, wie Internet Explorer und Windows Communication Foundation (WCF) Dienst Zertifikate überprüfen, wenn HTTPS verwendet wird, ist es möglich, dass Internet Explorer nicht auf die Hilfeseite oder Web Services Description Language (WSDL) eines Dienstanbieter zugreifen kann, obwohl ein WCF-Client erfolgreich Nachrichten an die Dienst Endpunkte senden kann.</span><span class="sxs-lookup"><span data-stu-id="78b93-103">Because of difference between the way Internet Explorer and Windows Communication Foundation (WCF) validate service certificates when HTTPS is used, it is possible that Internet Explorer will not be able to access the Help page or Web Services Description Language (WSDL) of a service even though a WCF client is able to successfully send messages to the service endpoints.</span></span> <span data-ttu-id="78b93-104">Dies liegt daran, dass Internet Explorer prüft, ob das Dienst Zertifikat über die Objekt-IDs `ServerAuthentication` (OID) in den erweiterten nutzungsflags verfügt, wohingegen WCF diese Einschränkung nicht erzwingt.</span><span class="sxs-lookup"><span data-stu-id="78b93-104">This is because Internet Explorer checks whether the service certificate has the `ServerAuthentication` object identifiers (OID) in the enhanced usage flags, whereas WCF does not enforce such a constraint.</span></span> <span data-ttu-id="78b93-105">Wenn Internet Explorer nicht auf die Diensthilfe Seite oder die WSDL für den Dienst zugreifen kann, verwenden Sie das Service [Model Metadata Utility-Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) , um auf die Dienst Metadaten zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="78b93-105">If Internet Explorer is unable to access the service Help page or the WSDL for the service, use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to access the service metadata.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78b93-106">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="78b93-106">See also</span></span>

- [<span data-ttu-id="78b93-107">Unterschiede bei der Zertifikatsvalidierung zwischen HTTPS, SSL über TCP und SOAP-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="78b93-107">Certificate Validation Differences Between HTTPS, SSL over TCP, and SOAP Security</span></span>](cert-val-diff-https-ssl-over-tcp-and-soap.md)
- [<span data-ttu-id="78b93-108">Vorgehensweise: Abrufen von Metadaten und Implementieren eines kompatiblen Diensts</span><span class="sxs-lookup"><span data-stu-id="78b93-108">How to: Retrieve Metadata and Implement a Compliant Service</span></span>](how-to-retrieve-metadata-and-implement-a-compliant-service.md)
