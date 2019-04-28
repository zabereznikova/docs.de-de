---
title: 'Vorgehensweise: Abrufen eines Zertifikats (WCF)'
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], obtaining
ms.assetid: d53762fd-15ea-42dc-b0ea-6a6597aa23f7
ms.openlocfilehash: 21e9e0609ed63c4398f2df7ba718f8af17464b0a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61683635"
---
# <a name="how-to-obtain-a-certificate-wcf"></a>Vorgehensweise: Abrufen eines Zertifikats (WCF)
Funktionen, verwenden Sie x. 509-Zertifikate von Windows Communication Foundation (WCF) verwenden, rufen Sie zuerst Zertifikate.  
  
### <a name="to-obtain-an-x509-certificate"></a>So rufen Sie ein X.509-Zertifikat ab  
  
1. Wählen Sie eine der folgenden Optionen aus:  
  
    - Erwerben Sie ein Zertifikat von einer Zertifizierungsstelle, z. B. VeriSign, Inc.  
  
    - Richten Sie einen eigenen Zertifikatdienst ein, und lassen Sie die Zertifikate von einer Zertifizierungsstelle signieren. [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], Windows&amp;amp;#160;2000 Server, Windows&amp;amp;#160;2000 Server Datacenter und Windows&amp;amp;#160;2000 Datacenter Server verfügen alle über Zertifikatdienste mit Public Key Infrastructure (PKI)-Unterstützung. In Windows Server 2008 verwenden, die [Active Directory Certificate Services](https://go.microsoft.com/fwlink/?LinkID=153483) Rolle um eine Zertifizierungsstelle zu verwalten.  
  
    - Richten Sie einen eigenen Zertifikatsdienst ein, und lassen Sie die Zertifikate nicht signieren.  
  
    > [!NOTE]
    >  Unabhängig vom gewählten Ansatz muss der Empfänger der SOAP-Anforderung, die das X.509-Zertifikat enthält, dem X.509-Zertifikat vertrauen. Dies bedeutet, dass sich das X.509-Zertifikat oder ein Aussteller in der Zertifikatkette im Speicher für vertrauenswürdige Personen befindet und sich das X.509-Zertifikat nicht im Speicher für nicht vertrauenswürdige Zertifikate befindet.  
  
## <a name="see-also"></a>Siehe auch

- [Arbeiten mit Zertifikaten](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [Vorgehensweise: Erstellen von temporären Zertifikaten für die Verwendung während der Entwicklung](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)
