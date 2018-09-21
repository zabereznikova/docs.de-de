---
title: 'Vorgehensweise: Angeben der Zertifizierungsstellenzertifikatskette, die verwendet wird, um Signaturen (WCF) zu überprüfen'
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], specifying the certificate authority certificate chain
- certificates [WCF], verifying signatures
ms.assetid: 7c719355-aa41-4567-80d0-5115a8cf73fd
ms.openlocfilehash: 9e2ba9f3550442602cab217fec329e6c19efd3b3
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2018
ms.locfileid: "46481688"
---
# <a name="how-to-specify-the-certificate-authority-certificate-chain-used-to-verify-signatures-wcf"></a>Vorgehensweise: Angeben der Zertifizierungsstellenzertifikatskette, die verwendet wird, um Signaturen (WCF) zu überprüfen
Wenn Windows Communication Foundation (WCF) eine mit einem x. 509-Zertifikat signierte SOAP-Nachricht empfängt, wird standardmäßig überprüft er, ob das x. 509-Zertifikat von einer vertrauenswürdigen Zertifizierungsstelle ausgestellt wurde. Dies erfolgt, indem ein Zertifikatspeicher überprüft und bestimmt wird, ob das Zertifikat für diese Zertifizierungsstelle als vertrauenswürdig bestimmt wurde. In der Reihenfolge für WCF, um diese Entscheidung zu treffen muss die zertifizierungsstellenzertifikatkette im richtigen Zertifikatspeicher installiert werden.  
  
### <a name="to-install-a-certification-authority-certificate-chain"></a>So installieren Sie eine Zertifizierungsstellenzertifikatkette  
  
-   Installieren Sie für jede Zertifizierungsstelle, die ein SOAP-Nachrichtenempfänger vertrauen möchte x. 509-Zertifikate ausgestellt, die zertifizierungsstellenzertifikatkette in den Zertifikatspeicher an, dass WCF so konfiguriert ist, um das x. 509-Zertifikate abrufen.  
  
     Z. B. will, dass ein SOAP-Nachrichtenempfänger von Microsoft ausgestellte x. 509-Zertifikaten zu vertrauen, muss die zertifizierungsstellenzertifikatkette für Microsoft im Zertifikatspeicher installiert sein, die WCF so eingerichtet ist, nach x. 509-Zertifikaten sucht. Der Zertifikatspeicher, in dem sich WCF für die x. 509-Zertifikaten sucht, kann in Code oder Konfiguration angegeben werden. Dies kann beispielsweise angegeben werden, im Code mithilfe der <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> Methode oder in der Konfiguration einige Möglichkeiten, einschließlich der [ \<ServiceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) .  
  
     Da Windows mit einem Satz an Standardzertifikatsketten für vertrauenswürdige Zertifizierungsstellen geliefert wird, ist es u. U. nicht erforderlich, die Zertifikatskette für alle Zertifizierungsstellen zu installieren.  
  
    1.  Exportieren Sie die Zertifizierungsstellenzertifikatkette.  
  
         Wie dies genau erfolgt, hängt von der Zertifizierungsstelle ab. Wenn es sich bei die Zertifizierungsstelle Microsoft-Zertifikatdienste ausgeführt wird, wählen Sie **herunterladen, eine Zertifizierungsstelle, einer Zertifikatkette oder Zertifikatsperrlisten**, und wählen Sie dann **Download des Zertifizierungsstellenzertifikats**.  
  
    2.  Importieren Sie die Zertifizierungsstellenzertifikatkette.  
  
         Öffnen Sie das Zertifikats-Snap-in in der Microsoft Management Console (MMC). Für den Zertifikatspeicher, WCF so konfiguriert wird zum Abrufen von x. 509-Zertifikate aus, wählen Sie die **vertrauenswürdigen Stamm** **Zertifizierungsstellen** Ordner. Unter den **Trusted Root Certification Authorities** Ordner mit der rechten Maustaste die **Zertifikate** Ordner, zeigen Sie auf **alle Aufgaben**, und klicken Sie dann auf **importieren** . Geben Sie die in Schritt a exportierte Datei an.  
  
         Weitere Informationen zur Verwendung von das Zertifikate-Snap-in mit MMC finden Sie unter [Vorgehensweise: Anzeigen von Zertifikaten mit dem MMC-Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Arbeiten mit Zertifikaten](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
