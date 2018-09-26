---
title: 'Vorgehensweise: Abrufen des Fingerabdrucks eines Zertifikats'
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], retrieving thumbprint
ms.assetid: da3101aa-78cd-4c34-9652-d1f24777eeab
ms.openlocfilehash: f520e897ad467686e0dc151548a61ea8370eb07a
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2018
ms.locfileid: "47205225"
---
# <a name="how-to-retrieve-the-thumbprint-of-a-certificate"></a>Vorgehensweise: Abrufen des Fingerabdrucks eines Zertifikats
Wenn Sie einer Windows Communication Foundation (WCF)-Anwendung schreiben, das ein x. 509-Zertifikat für die Authentifizierung verwendet, ist es oft notwendig, geben Sie die Ansprüche im Zertifikat gefunden. Sie müssen z. B. einen Fingerabdruckanspruch bereitstellen, wenn Sie die <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindByThumbprint> -Enumeration in der <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> -Methode verwenden. Zum Suchen des Anspruchswerts sind zwei Schritte erforderlich. Öffnen Sie zuerst in der Microsoft Management Console (MMC) das Snap-In für Zertifikate. (Siehe [Vorgehensweise: Anzeigen von Zertifikaten mit dem MMC-Snap-In](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).) Suchen Sie dann, wie hier beschrieben, ein entsprechendes Zertifikat, und kopieren Sie seinen Fingerabdruck (oder andere Anspruchswerte).  
  
 Wenn Sie ein Zertifikat für die Dienstauthentifizierung verwenden, ist es wichtig, den Wert der Spalte **Ausgestellt für** zu notieren (die erste Spalte in der Konsole). Beim Verwenden von SSL (Secure Sockets Layer) als Transportsicherheit wird als eine der ersten Überprüfungen der URI (Uniform Resource Identifier) der Basisadresse des Dienstes mit dem Wert **Ausgestellt für** verglichen. Die Werte müssen übereinstimmen, sonst wird die Authentifizierungsvorgang angehalten.  
  
 Sie können auch das Powershell-New-SelfSignedCertificate-Cmdlet verwenden, zum Erstellen von temporären Zertifikaten für die Verwendung nur während der Entwicklung. In der Standardeinstellung jedoch solches Zertifikat wird nicht von einer Zertifizierungsstelle ausgestellt, und kann nicht für Produktionszwecke verwendet werden. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen temporärer Zertifikate für die Verwendung während der Entwicklung](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md).  
  
### <a name="to-retrieve-a-certificates-thumbprint"></a>So rufen Sie den Fingerabdruck eines Zertifikats ab  
  
1.  Öffnen Sie in der Microsoft Management Console (MMC) das Snap-In für Zertifikate. (Siehe [Vorgehensweise: Anzeigen von Zertifikaten mit dem MMC-Snap-In](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).)  
  
2.  Klicken Sie im linken Bereich des Fensters **Konsolenstamm** auf **Zertifikate (Lokaler Computer)**.  
  
3.  Klicken Sie auf den Ordner **Persönlich** , um ihn zu erweitern.  
  
4.  Klicken Sie auf den Ordner **Zertifikate** , um ihn zu erweitern.  
  
5.  Suchen Sie in der Liste der Zertifikate die Überschrift **Beabsichtigte Zwecke** . Suchen Sie ein Zertifikat, für das **Clientauthentifizierung** als beabsichtigter Zweck aufgeführt wird.  
  
6.  Doppelklicken Sie auf das Zertifikat.  
  
7.  Klicken Sie im Dialogfeld **Zertifikat** auf die Registerkarte **Details** .  
  
8.  Verschieben Sie den Inhalt der Feldliste, und klicken Sie auf **Fingerabdruck**.  
  
9. Kopieren Sie die hexadezimalen Zeichen aus dem Feld. Wenn dieser Fingerabdruck im Code für `X509FindType`verwendet wird, entfernen Sie die Leerzeichen zwischen den hexadezimalen Zahlen. Beispielsweise muss der Fingerabdruck "a9 09 50 2d d8 2a e4 14 33 e6 f8 38 86 b0 0d 42 77 a3 2a 7b" im Code als "a909502dd82ae41433e6f83886b00d4277a32a7b" angegeben werden.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindByThumbprint>  
 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A>  
 [Vorgehensweise: Konfigurieren eines Ports mit einem SSL-Zertifikat](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)  
 [Vorgehensweise: Anzeigen von Zertifikaten mit dem MMC-Snap-In](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)  
 [Vorgehensweise: Erstellen von temporären Zertifikaten für die Verwendung während der Entwicklung](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)
