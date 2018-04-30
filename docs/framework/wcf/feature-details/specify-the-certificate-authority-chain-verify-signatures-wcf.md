---
title: 'Vorgehensweise: Angeben der Zertifizierungsstellenzertifikatskette, die verwendet wird, um Signaturen (WCF) zu überprüfen'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates [WCF], specifying the certificate authority certificate chain
- certificates [WCF], verifying signatures
ms.assetid: 7c719355-aa41-4567-80d0-5115a8cf73fd
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 29637ea7f0a1e533a6735ebfa6f428fe20039e48
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-specify-the-certificate-authority-certificate-chain-used-to-verify-signatures-wcf"></a>Vorgehensweise: Angeben der Zertifizierungsstellenzertifikatskette, die verwendet wird, um Signaturen (WCF) zu überprüfen
Wenn [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] eine mit einem X.509-Zertifikat signierte SOAP-Nachricht empfängt, wird standardmäßig überprüft, ob das X.509-Zertifikat von einer vertrauenswürdigen Zertifizierungsstelle ausgestellt wurde. Dies erfolgt, indem ein Zertifikatspeicher überprüft und bestimmt wird, ob das Zertifikat für diese Zertifizierungsstelle als vertrauenswürdig bestimmt wurde. Damit diese Bestimmung durch [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] erfolgen kann, muss die Zertifizierungsstellenzertifikatkette im richtigen Zertifikatspeicher installiert werden.  
  
### <a name="to-install-a-certification-authority-certificate-chain"></a>So installieren Sie eine Zertifizierungsstellenzertifikatkette  
  
-   Installieren Sie für jede Zertifizierungsstelle, deren ausgestellte X.509-Zertifikate ein SOAP-Nachrichtenempfänger als vertrauenswürdig behandeln möchte, die Zertifizierungsstellenzertifikatkette in dem Zertifikatspeicher, von dem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] aufgrund der Konfiguration X.509-Zertifikate abrufen kann.  
  
     Wenn z. B. ein SOAP-Nachrichtenempfänger von Microsoft ausgestellte X.509-Zertifikate als vertrauenswürdig behandeln möchte, muss die Zertifizierungsstellenzertifikatkette für Microsoft in dem Zertifikatspeicher installiert werden, in dem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] aufgrund der Einrichtung nach X.509-Zertifikaten sucht. Der Zertifikatspeicher, in dem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] nach X.509-Zertifikaten sucht, kann im Code oder in der Konfiguration festgelegt werden. Dies kann beispielsweise angegeben werden, im Code mithilfe der <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> Methode oder in der Konfiguration einige Möglichkeiten, einschließlich der [ \<ServiceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) .  
  
     Da Windows mit einem Satz an Standardzertifikatsketten für vertrauenswürdige Zertifizierungsstellen geliefert wird, ist es u. U. nicht erforderlich, die Zertifikatskette für alle Zertifizierungsstellen zu installieren.  
  
    1.  Exportieren Sie die Zertifizierungsstellenzertifikatkette.  
  
         Wie dies genau erfolgt, hängt von der Zertifizierungsstelle ab. Wenn die Zertifizierungsstelle Microsoft-Zertifikatdienste ausgeführt wird, wählen Sie **Herunterladen einer Zertifizierungsstelle, einer Zertifikatkette oder CRL**, und wählen Sie dann **Download des Zertifizierungsstellenzertifikats**.  
  
    2.  Importieren Sie die Zertifizierungsstellenzertifikatkette.  
  
         Öffnen Sie das Zertifikats-Snap-in in der Microsoft Management Console (MMC). Für das Zertifikat zu speichern, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] konfiguriert ist, zum Abrufen von x. 509-Zertifikate aus, wählen Sie die **vertrauenswürdigen Stamm** **Zertifizierungsstellen**Ordner. Unter den **Trusted Root Certification Authorities** Ordner mit der rechten Maustaste die **Zertifikate**Ordner, zeigen Sie auf **alle Aufgaben**, und klicken Sie dann auf **importieren** . Geben Sie die in Schritt a exportierte Datei an.  
  
         Weitere Informationen zur Verwendung von mit MMC das Zertifikate-Snap-in finden Sie unter [Vorgehensweise: Anzeigen von Zertifikaten mit dem MMC-Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Arbeiten mit Zertifikaten](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
