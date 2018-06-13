---
title: 'Vorgehensweise: Angeben der Zertifizierungsstellenzertifikatskette, die verwendet wird, um Signaturen (WCF) zu überprüfen'
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], specifying the certificate authority certificate chain
- certificates [WCF], verifying signatures
ms.assetid: 7c719355-aa41-4567-80d0-5115a8cf73fd
ms.openlocfilehash: 14f7691046f9512e25006bd6cd02749eed825003
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33498074"
---
# <a name="how-to-specify-the-certificate-authority-certificate-chain-used-to-verify-signatures-wcf"></a>Vorgehensweise: Angeben der Zertifizierungsstellenzertifikatskette, die verwendet wird, um Signaturen (WCF) zu überprüfen
Wenn Windows Communication Foundation (WCF) über ein x. 509-Zertifikat signierte SOAP-Nachricht empfängt, in der Standardeinstellung überprüft er, ob das x. 509-Zertifikat von einer vertrauenswürdigen Zertifizierungsstelle ausgestellt wurde. Dies erfolgt, indem ein Zertifikatspeicher überprüft und bestimmt wird, ob das Zertifikat für diese Zertifizierungsstelle als vertrauenswürdig bestimmt wurde. Damit für WCF, um diese Entscheidung zu treffen muss die zertifizierungsstellenzertifikatkette im richtigen Zertifikatspeicher installiert werden.  
  
### <a name="to-install-a-certification-authority-certificate-chain"></a>So installieren Sie eine Zertifizierungsstellenzertifikatkette  
  
-   Installieren Sie für jede Zertifizierungsstelle, die eine SOAP-Nachricht zertifizierungsstellenzertifikatkette vertrauen x. 509-Zertifikate, die zertifizierungsstellenzertifikatkette in den Zertifikatspeicher, dass WCF für die x. 509-Zertifikate abrufen konfiguriert ist.  
  
     Z. B. will, dass der Empfänger einer SOAP-Nachricht von Microsoft ausgestellte x. 509-Zertifikate zu vertrauen, muss die zertifizierungsstellenzertifikatkette für Microsoft im Zertifikatspeicher installiert werden, die WCF so eingerichtet ist, suchen Sie für x. 509-Zertifikate aus. Der Zertifikatspeicher, in dem WCF nach x. 509-Zertifikate sucht, kann im Code oder Konfiguration angegeben werden. Dies kann beispielsweise angegeben werden, im Code mithilfe der <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> Methode oder in der Konfiguration einige Möglichkeiten, einschließlich der [ \<ServiceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) .  
  
     Da Windows mit einem Satz an Standardzertifikatsketten für vertrauenswürdige Zertifizierungsstellen geliefert wird, ist es u. U. nicht erforderlich, die Zertifikatskette für alle Zertifizierungsstellen zu installieren.  
  
    1.  Exportieren Sie die Zertifizierungsstellenzertifikatkette.  
  
         Wie dies genau erfolgt, hängt von der Zertifizierungsstelle ab. Wenn die Zertifizierungsstelle Microsoft-Zertifikatdienste ausgeführt wird, wählen Sie **Herunterladen einer Zertifizierungsstelle, einer Zertifikatkette oder CRL**, und wählen Sie dann **Download des Zertifizierungsstellenzertifikats**.  
  
    2.  Importieren Sie die Zertifizierungsstellenzertifikatkette.  
  
         Öffnen Sie das Zertifikats-Snap-in in der Microsoft Management Console (MMC). Für den Zertifikatspeicher, WCF konfiguriert ist, zum Abrufen von x. 509-Zertifikate aus, wählen Sie die **vertrauenswürdigen Stamm** **Zertifizierungsstellen**Ordner. Unter den **Trusted Root Certification Authorities** Ordner mit der rechten Maustaste die **Zertifikate**Ordner, zeigen Sie auf **alle Aufgaben**, und klicken Sie dann auf **importieren** . Geben Sie die in Schritt a exportierte Datei an.  
  
         Weitere Informationen zur Verwendung von mit MMC das Zertifikate-Snap-in finden Sie unter [Vorgehensweise: Anzeigen von Zertifikaten mit dem MMC-Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Arbeiten mit Zertifikaten](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
