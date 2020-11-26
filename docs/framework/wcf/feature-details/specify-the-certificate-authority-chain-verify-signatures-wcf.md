---
title: 'Vorgehensweise: Angeben der Zertifizierungsstellenzertifikatskette, die verwendet wird, um Signaturen (WCF) zu überprüfen'
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], specifying the certificate authority certificate chain
- certificates [WCF], verifying signatures
ms.assetid: 7c719355-aa41-4567-80d0-5115a8cf73fd
ms.openlocfilehash: 0a03902c9a0d36ebd6e2c38f4a827737cacec447
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96245031"
---
# <a name="how-to-specify-the-certificate-authority-certificate-chain-used-to-verify-signatures-wcf"></a>Vorgehensweise: Angeben der Zertifizierungsstellenzertifikatskette, die verwendet wird, um Signaturen (WCF) zu überprüfen

Wenn Windows Communication Foundation (WCF) eine mit einem X. 509-Zertifikat signierte SOAP-Nachricht empfängt, wird standardmäßig überprüft, ob das X. 509-Zertifikat von einer vertrauenswürdigen Zertifizierungsstelle ausgestellt wurde. Dies erfolgt, indem ein Zertifikatspeicher überprüft und bestimmt wird, ob das Zertifikat für diese Zertifizierungsstelle als vertrauenswürdig bestimmt wurde. Damit WCF diese Entscheidung treffen kann, muss die Zertifizierungsstellen-Zertifikat Kette im richtigen Zertifikat Speicher installiert werden.  
  
### <a name="to-install-a-certification-authority-certificate-chain"></a>So installieren Sie eine Zertifizierungsstellenzertifikatkette  
  
- Installieren Sie für jede Zertifizierungsstelle, für die ein SOAP-Nachrichtenempfänger x. 509-Zertifikate als vertrauenswürdig einstufen möchte, die Zertifizierungsstellen-Zertifikat Kette in dem Zertifikat Speicher, von dem WCF zum Abrufen von x. 509-Zertifikaten konfiguriert ist.  
  
     Wenn beispielsweise ein SOAP-Nachrichtenempfänger von Microsoft ausgestellte x. 509-Zertifikate als vertrauenswürdig einstuft, muss die Zertifizierungsstellen-Zertifikat Kette für Microsoft im Zertifikat Speicher installiert werden, in dem WCF für die Suche nach X. 509-Zertifikaten eingerichtet ist. Der Zertifikat Speicher, in dem WCF nach X. 509-Zertifikaten sucht, kann im Code oder in der Konfiguration angegeben werden. Dies kann z. b. im Code mithilfe der- <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> Methode oder in der Konfiguration auf verschiedene Weise angegeben werden, einschließlich der [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) .  
  
     Da Windows mit einem Satz an Standardzertifikatsketten für vertrauenswürdige Zertifizierungsstellen geliefert wird, ist es u. U. nicht erforderlich, die Zertifikatskette für alle Zertifizierungsstellen zu installieren.  
  
    1. Exportieren Sie die Zertifizierungsstellenzertifikatkette.  
  
         Wie dies genau erfolgt, hängt von der Zertifizierungsstelle ab. Wenn die Zertifizierungsstelle Microsoft-Zertifikat Dienste ausgeführt wird, wählen Sie ein Zertifizierungsstellen **Zertifikat, eine Zertifikat Kette oder eine CRL Herunterladen** aus, und wählen Sie dann **Zertifizierungsstellen Zertifikat herunterladen** aus.  
  
    2. Importieren Sie die Zertifizierungsstellenzertifikatkette.  
  
         Öffnen Sie das Zertifikats-Snap-in in der Microsoft Management Console (MMC). Für den Zertifikat Speicher, von dem WCF zum Abrufen von X. 509-Zertifikaten konfiguriert ist, wählen Sie den Ordner **Vertrauenswürdige** Stamm **Zertifizierungs** stellen aus. Klicken Sie im Ordner **Vertrauenswürdige Stamm Zertifizierungs** stellen mit der rechten Maustaste auf den Ordner **Zertifikate** , zeigen Sie auf **Alle Tasks**, und klicken Sie dann auf **importieren**. Geben Sie die in Schritt a exportierte Datei an.  
  
         Weitere Informationen zur Verwendung des Zertifikate-Snap-Ins mit MMC finden Sie unter Gewusst [wie: Anzeigen von Zertifikaten mit dem MMC-Snap-in](how-to-view-certificates-with-the-mmc-snap-in.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Verwenden von Zertifikaten](working-with-certificates.md)
