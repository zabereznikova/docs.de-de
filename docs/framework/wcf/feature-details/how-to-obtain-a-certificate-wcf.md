---
title: 'Vorgehensweise: Abrufen eines Zertifikats (WCF)'
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], obtaining
ms.assetid: d53762fd-15ea-42dc-b0ea-6a6597aa23f7
ms.openlocfilehash: 485741f98c4a120669eafe85d3a3810374f61378
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347142"
---
# <a name="how-to-obtain-a-certificate-wcf"></a>Vorgehensweise: Abrufen eines Zertifikats (WCF)
Um eine der Windows Communication Foundation (WCF)-Funktionen von verwenden zu können, die X. 509-Zertifikate verwenden, erhalten Sie zuerst Zertifikate.  
  
### <a name="to-obtain-an-x509-certificate"></a>So rufen Sie ein X.509-Zertifikat ab  
  
1. Wählen Sie eine der folgenden Optionen aus:  
  
    - Erwerben Sie ein Zertifikat von einer Zertifizierungsstelle, z. B. VeriSign, Inc.  
  
    - Richten Sie einen eigenen Zertifikatdienst ein, und lassen Sie die Zertifikate von einer Zertifizierungsstelle signieren. Windows Server 2003, Windows 2000 Server, Windows 2000 Server Datacenter und Windows 2000 Datacenter Server enthalten alle Zertifikat Dienste, die die Public Key-Infrastruktur (PKI) unterstützen. Verwenden Sie unter Windows Server 2008 die Rolle " [Active Directory-Zertifikat Dienste](https://go.microsoft.com/fwlink/?LinkID=153483) ", um eine Zertifizierungsstelle zu verwalten.  
  
    - Richten Sie einen eigenen Zertifikatsdienst ein, und lassen Sie die Zertifikate nicht signieren.  
  
    > [!NOTE]
    > Unabhängig vom gewählten Ansatz muss der Empfänger der SOAP-Anforderung, die das X.509-Zertifikat enthält, dem X.509-Zertifikat vertrauen. Dies bedeutet, dass sich das X.509-Zertifikat oder ein Aussteller in der Zertifikatkette im Speicher für vertrauenswürdige Personen befindet und sich das X.509-Zertifikat nicht im Speicher für nicht vertrauenswürdige Zertifikate befindet.  
  
## <a name="see-also"></a>Siehe auch

- [Arbeiten mit Zertifikaten](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [Vorgehensweise: Erstellen von temporären Zertifikaten für die Verwendung während der Entwicklung](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)
