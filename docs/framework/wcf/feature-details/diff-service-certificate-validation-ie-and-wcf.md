---
title: Unterschiede zwischen von Internet Explorer und WCF durchgeführter Dienstzertifikatsvalidierung
ms.date: 03/30/2017
helpviewer_keywords:
- service certificate validation [WCF]
- certificates [WCF], service certificate validation
ms.assetid: 9dffcab2-70a9-40f0-99fd-d3a0b296028f
ms.openlocfilehash: 574a6fa5411bcb662514982923e5c51200f98ae2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272201"
---
# <a name="differences-between-service-certificate-validation-done-by-internet-explorer-and-wcf"></a><span data-ttu-id="143cf-102">Unterschiede zwischen von Internet Explorer und WCF durchgeführter Dienstzertifikatsvalidierung</span><span class="sxs-lookup"><span data-stu-id="143cf-102">Differences Between Service Certificate Validation Done by Internet Explorer and WCF</span></span>

<span data-ttu-id="143cf-103">Aufgrund der Differenz zwischen der Art und Weise, wie Internet Explorer und Windows Communication Foundation (WCF) Dienst Zertifikate überprüfen, wenn HTTPS verwendet wird, ist es möglich, dass Internet Explorer nicht auf die Hilfeseite oder Web Services Description Language (WSDL) eines Dienstanbieter zugreifen kann, obwohl ein WCF-Client erfolgreich Nachrichten an die Dienst Endpunkte senden kann.</span><span class="sxs-lookup"><span data-stu-id="143cf-103">Because of difference between the way Internet Explorer and Windows Communication Foundation (WCF) validate service certificates when HTTPS is used, it is possible that Internet Explorer will not be able to access the Help page or Web Services Description Language (WSDL) of a service even though a WCF client is able to successfully send messages to the service endpoints.</span></span> <span data-ttu-id="143cf-104">Dies liegt daran, dass Internet Explorer prüft, ob das Dienst Zertifikat über die Objekt-IDs `ServerAuthentication` (OID) in den erweiterten nutzungsflags verfügt, wohingegen WCF diese Einschränkung nicht erzwingt.</span><span class="sxs-lookup"><span data-stu-id="143cf-104">This is because Internet Explorer checks whether the service certificate has the `ServerAuthentication` object identifiers (OID) in the enhanced usage flags, whereas WCF does not enforce such a constraint.</span></span> <span data-ttu-id="143cf-105">Wenn Internet Explorer nicht auf die Diensthilfe Seite oder die WSDL für den Dienst zugreifen kann, verwenden Sie das Service [Model Metadata Utility-Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) , um auf die Dienst Metadaten zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="143cf-105">If Internet Explorer is unable to access the service Help page or the WSDL for the service, use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to access the service metadata.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="143cf-106">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="143cf-106">See also</span></span>

- [<span data-ttu-id="143cf-107">Unterschiede bei der Zertifikatsvalidierung zwischen HTTPS, SSL über TCP und SOAP-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="143cf-107">Certificate Validation Differences Between HTTPS, SSL over TCP, and SOAP Security</span></span>](cert-val-diff-https-ssl-over-tcp-and-soap.md)
- [<span data-ttu-id="143cf-108">Vorgehensweise: Abrufen von Metadaten und Implementieren eines kompatiblen Diensts</span><span class="sxs-lookup"><span data-stu-id="143cf-108">How to: Retrieve Metadata and Implement a Compliant Service</span></span>](how-to-retrieve-metadata-and-implement-a-compliant-service.md)
