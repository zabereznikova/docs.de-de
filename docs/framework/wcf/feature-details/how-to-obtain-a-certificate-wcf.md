---
title: 'Vorgehensweise: Abrufen eines Zertifikats (WCF)'
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], obtaining
ms.assetid: d53762fd-15ea-42dc-b0ea-6a6597aa23f7
ms.openlocfilehash: 20e936feb5839a7e71f6579583d558abfc2fd9cf
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96234491"
---
# <a name="how-to-obtain-a-certificate-wcf"></a>Vorgehensweise: Abrufen eines Zertifikats (WCF)

Um eine der Windows Communication Foundation (WCF)-Funktionen von verwenden zu können, die X. 509-Zertifikate verwenden, erhalten Sie zuerst Zertifikate.  
  
### <a name="to-obtain-an-x509-certificate"></a>So rufen Sie ein X.509-Zertifikat ab  
  
1. Wählen Sie eine der folgenden Optionen aus:  
  
    - Erwerben Sie ein Zertifikat von einer Zertifizierungsstelle, z. B. VeriSign, Inc.  
  
    - Richten Sie einen eigenen Zertifikatdienst ein, und lassen Sie die Zertifikate von einer Zertifizierungsstelle signieren. Windows Server 2003, Windows 2000 Server, Windows 2000 Server Datacenter und Windows 2000 Datacenter Server enthalten alle Zertifikat Dienste, die die Public Key-Infrastruktur (PKI) unterstützen. Verwenden Sie unter Windows Server 2008 die Rolle " [Active Directory-Zertifikat Dienste](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731564(v=ws.10)) ", um eine Zertifizierungsstelle zu verwalten.  
  
    - Richten Sie einen eigenen Zertifikatsdienst ein, und lassen Sie die Zertifikate nicht signieren.  
  
    > [!NOTE]
    > Unabhängig vom gewählten Ansatz muss der Empfänger der SOAP-Anforderung, die das X.509-Zertifikat enthält, dem X.509-Zertifikat vertrauen. Dies bedeutet, dass sich das X.509-Zertifikat oder ein Aussteller in der Zertifikatkette im Speicher für vertrauenswürdige Personen befindet und sich das X.509-Zertifikat nicht im Speicher für nicht vertrauenswürdige Zertifikate befindet.  
  
## <a name="see-also"></a>Weitere Informationen

- [Verwenden von Zertifikaten](working-with-certificates.md)
- [Vorgehensweise: Erstellen von temporären Zertifikaten für die Verwendung während der Entwicklung](how-to-create-temporary-certificates-for-use-during-development.md)
