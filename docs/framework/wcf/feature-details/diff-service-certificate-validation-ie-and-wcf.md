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
# <a name="differences-between-service-certificate-validation-done-by-internet-explorer-and-wcf"></a>Unterschiede zwischen von Internet Explorer und WCF durchgeführter Dienstzertifikatsvalidierung
Aufgrund der Differenz zwischen der Art und Weise, wie Internet Explorer und Windows Communication Foundation (WCF) Dienst Zertifikate überprüfen, wenn HTTPS verwendet wird, ist es möglich, dass Internet Explorer nicht auf die Hilfeseite oder Web Services Description Language (WSDL) eines Dienstanbieter zugreifen kann, obwohl ein WCF-Client erfolgreich Nachrichten an die Dienst Endpunkte senden kann. Dies liegt daran, dass Internet Explorer prüft, ob das Dienst Zertifikat über die Objekt-IDs `ServerAuthentication` (OID) in den erweiterten nutzungsflags verfügt, wohingegen WCF diese Einschränkung nicht erzwingt. Wenn Internet Explorer nicht auf die Diensthilfe Seite oder die WSDL für den Dienst zugreifen kann, verwenden Sie das Service [Model Metadata Utility-Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) , um auf die Dienst Metadaten zuzugreifen.  
  
## <a name="see-also"></a>Weitere Informationen

- [Unterschiede bei der Zertifikatsvalidierung zwischen HTTPS, SSL über TCP und SOAP-Sicherheit](cert-val-diff-https-ssl-over-tcp-and-soap.md)
- [Vorgehensweise: Abrufen von Metadaten und Implementieren eines kompatiblen Diensts](how-to-retrieve-metadata-and-implement-a-compliant-service.md)
