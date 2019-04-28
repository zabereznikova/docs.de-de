---
title: Unterschiede zwischen von Internet Explorer und WCF durchgeführter Dienstzertifikatsvalidierung
ms.date: 03/30/2017
helpviewer_keywords:
- service certificate validation [WCF]
- certificates [WCF], service certificate validation
ms.assetid: 9dffcab2-70a9-40f0-99fd-d3a0b296028f
ms.openlocfilehash: 0bced548cdc9423d1907de09e8b52ebe078d7c19
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61857700"
---
# <a name="differences-between-service-certificate-validation-done-by-internet-explorer-and-wcf"></a>Unterschiede zwischen von Internet Explorer und WCF durchgeführter Dienstzertifikatsvalidierung
Aufgrund der Unterschiede zwischen die Möglichkeit, die Internet Explorer und Windows Communication Foundation (WCF)-Dienstzertifikate überprüfen, wenn HTTPS verwendet wird, ist es möglich, dass Internet Explorer nicht auf die Hilfeseite oder Web Services Description Language zugreifen (WSDL) eines Diensts, obwohl ein WCF-Client erfolgreich kann Senden von Nachrichten an die Dienstendpunkte. Grund hierfür ist Internet Explorer überprüft, ob das Dienstzertifikat verfügt die `ServerAuthentication` -Objektbezeichner (OIDS) in die erweiterte Schlüsselverwendung Usage-Flags, wohingegen WCF eine solche Einschränkung nicht erzwingt. Wenn Internet Explorer die Hilfeseite oder WSDL für den Dienst zugreifen kann, verwenden Sie die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) Zugriff auf die Dienstmetadaten.  
  
## <a name="see-also"></a>Siehe auch

- [Unterschiede bei der Zertifikatvalidierung zwischen HTTPS, SSL über TCP und SOAP-Sicherheit](../../../../docs/framework/wcf/feature-details/cert-val-diff-https-ssl-over-tcp-and-soap.md)
- [Vorgehensweise: Abrufen von Metadaten und Implementieren eines kompatiblen Diensts](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)
