---
title: "Gewusst wie: Erstellen von temporären Zertifikaten für die Verwendung während der Entwicklung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- certificates [WCF], creating temporary certificates
- temporary certificates [WCF]
ms.assetid: bc5f6637-5513-4d27-99bb-51aad7741e4a
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4d6c955c3498c830403f628b4805611fadc44d68
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-temporary-certificates-for-use-during-development"></a>Gewusst wie: Erstellen von temporären Zertifikaten für die Verwendung während der Entwicklung
Wenn Sie mithilfe von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]einen sicheren Dienst oder Client entwickeln, müssen Sie häufig ein X.509-Zertifikat angeben, das für die Anmeldeinformationen verwendet wird. Das Zertifikat ist normalerweise Teil einer Zertifikatskette mit einer Stammstelle, die im Speicher mit den vertrauenswürdigen Stammzertifizierungsstellen des Computers enthalten ist. Wenn Sie über eine Zertifikatskette verfügen, können Sie einen Bereich mit Zertifikatsätzen angeben, wobei die Stammzertifizierungsstelle normalerweise von Ihrer Organisation bzw. Ihrem Geschäftsbereich stammt. Um dies zur Entwicklungszeit zu emulieren, können Sie zwei Zertifikate erstellen, um die Sicherheitsanforderungen zu erfüllen. Beim ersten Zertifikat handelt es sich um ein selbstsigniertes Zertifikat, das in den Speicher mit den vertrauenswürdigen Stammzertifizierungsstellen eingefügt wird. Das zweite Zertifikat wird aus dem ersten Zertifikat erstellt und entweder in den persönlichen Speicher unter "Lokaler Computer" oder in den persönlichen Speicher unter "Aktueller Benutzer" eingefügt. In diesem Thema sind die Schritte zur Erstellung dieser beiden Zertifikate beschrieben. Dabei wird das [Certificate Creation-Tool (MakeCert.exe)](http://go.microsoft.com/fwlink/?LinkId=248185)verwendet, das im [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -SDK enthalten ist.  
  
> [!IMPORTANT]
>  Die Zertifikate, die das Certificate Creation-Tool generiert, werden nur zu Testzwecken bereitgestellt. Beim Bereitstellen eines Diensts oder Clients sollten Sie ein geeignetes Zertifikat einer Zertifizierungsstelle verwenden. Dies kann entweder von einem [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] -Zertifikatsserver Ihrer Organisation oder von einem Drittanbieter stammen.  
>   
>  Wird standardmäßig die [Makecert.exe (Certificate Creation-Tool)](http://msdn.microsoft.com/library/b0343f8e-9c41-4852-a85c-f8a0c408cf0d) erstellt Zertifikate, deren Stammzertifizierungsstelle heißt "Root Agency**."** Da sich die Stammzertifizierungsstelle ("Root Agency") nicht im Speicher mit den vertrauenswürdigen Stammzertifizierungsstellen befindet, sind diese Zertifikate nicht sicher. Indem Sie ein selbstsigniertes Zertifikat erstellen, das in den Speicher mit den vertrauenswürdigen Stammzertifizierungsstellen eingefügt wird, können sie eine Entwicklungsumgebung anlegen, die eine bessere Simulation Ihrer Bereitstellungsumgebung darstellt.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zum Erstellen und Verwenden von Zertifikaten finden Sie unter [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md). [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zum Verwenden eines Zertifikats für die Anmeldeinformationen finden Sie unter [Securing Services and Clients](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md). Ein Lernprogramm zur Verwendung der Microsoft Authenticode-Technologie finden Sie unter [Authenticode Overviews and Tutorials](http://go.microsoft.com/fwlink/?LinkId=88919).  
  
### <a name="to-create-a-self-signed-root-authority-certificate-and-export-the-private-key"></a>So erstellen Sie ein selbstsigniertes Stammzertifizierungsstellen-Zertifikat und exportieren den privaten Schlüssel  
  
1.  Verwenden Sie das Tool MakeCert.exe mit den folgenden Schaltern:  
  
    1.  `-n` `subjectName`. Gibt den Namen des Antragstellers an. Normalerweise wird dem Namen des Antragstellers als Präfix "CN = " ("Common Name", gemeinsamer Name) hinzugefügt.  
  
    2.  `-r`. Gibt an, dass das Zertifikat selbstsigniert ist.  
  
    3.  `-sv` `privateKeyFile`. Gibt die Datei an, die den Container für den privaten Schlüssel enthält.  
  
     Der folgende Befehl erstellt zum Beispiel ein selbstsigniertes Zertifikat mit dem Antragstellernamen "CN=TempCA".  
  
    ```  
    makecert -n "CN=TempCA" -r -sv TempCA.pvk TempCA.cer  
    ```  
  
     Sie werden aufgefordert, ein Kennwort anzugeben, um den privaten Schlüssel zu schützen. Dieses Kennwort ist erforderlich, wenn sie ein von diesem Stammzertifikat signiertes Zertifikat erstellen.  
  
### <a name="to-create-a-new-certificate-signed-by-a-root-authority-certificate"></a>So erstellen Sie ein neues von einem Stammzertifizierungsstellen-Zertifikat signiertes Zertifikat  
  
1.  Verwenden Sie das Tool MakeCert.exe mit den folgenden Schaltern:  
  
    1.  `-sk` `subjectKey`. Der Speicherort des Schlüsselcontainers des Antragstellers, in dem der private Schlüssel gespeichert ist. Wenn kein Schlüsselcontainer vorhanden ist, wird ein Schlüsselcontainer erstellt. Wenn weder die Option "-sk" noch die Option "-sv" verwendet wird, wird standardmäßig ein Schlüsselcontainer mit dem Namen "JoeSoft" erstellt.  
  
    2.  `-n` `subjectName`. Gibt den Namen des Antragstellers an. Normalerweise wird dem Namen des Antragstellers als Präfix "CN = " ("Common Name", gemeinsamer Name) hinzugefügt.  
  
    3.  `-iv` `issuerKeyFile`. Gibt die Datei für den privaten Schlüssel des Herausgebers an.  
  
    4.  `-ic` `issuerCertFile`. Gibt den Speicherort für das Zertifikat des Herausgebers an.  
  
     Der folgende Befehl erstellt zum Beispiel ein Zertifikat, das von der Stammzertifizierungsstelle `TempCA` mit dem Antragstellernamen `"CN=SignedByCA"` signiert wird, indem der private Schlüssel des Herausgebers verwendet wird.  
  
    ```  
    makecert -sk SignedByCA -iv TempCA.pvk -n "CN=SignedByCA" -ic TempCA.cer SignedByCA.cer -sr currentuser -ss My  
    ```  
  
## <a name="installing-a-certificate-in-the-trusted-root-certification-authorities-store"></a>Installieren eines Zertifikats im Speicher mit den vertrauenswürdigen Stammzertifizierungsstellen  
 Nachdem ein selbstsigniertes Zertifikat erstellt wurde, können Sie es im Speicher der vertrauenswürdigen Stammzertifizierungsstellen installieren. Alle Zertifikate, die zu diesem Zeitpunkt mit dem Zertifikat signiert sind, werden vom Computer als vertrauenswürdig eingestuft. Aus diesem Grund sollten Sie das Zertifikat aus dem Speicher löschen, sobald Sie es nicht mehr benötigen. Wenn Sie dieses Stammzertifizierungsstellen-Zertifikat löschen, verlieren auch alle anderen Zertifikate, die zusammen damit signiert wurden, ihre Zertifizierung. Bei Stammzertifizierungsstellen-Zertifikaten handelt es sich einfach um einen Mechanismus, bei dem der Gültigkeitsbereich einer Gruppe von Zertifikaten festgelegt werden kann. Bei der Verwendung von Peer-to-Peer-Anwendungen ist eine Stammzertifizierungsstelle zum Beispiel normalerweise nicht erforderlich, weil Sie der Identität einer Person einfach aufgrund ihres bereitgestellten Zertifikats vertrauen.  
  
#### <a name="to-install-a-self-signed-certificate-in-the-trusted-root-certification-authorities"></a>So installieren Sie ein selbstsigniertes Zertifikat im Speicher mit den vertrauenswürdigen Stammzertifizierungsstellen  
  
1.  Öffnen Sie das Zertifikat-Snap-In. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Vorgehensweise: Anzeigen von Zertifikaten mit dem MMC-Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).  
  
2.  Öffnen Sie den Ordner, um das Zertifikat zu speichern, also entweder **Lokaler Computer** oder **Aktueller Benutzer**.  
  
3.  Öffnen Sie den Ordner **Vertrauenswürdige Stammzertifizierungsstellen** .  
  
4.  Klicken Sie mit der rechten Maustaste auf den Ordner **Zertifikate** , und klicken Sie auf **Alle Aufgaben**und anschließend auf **Importieren**.  
  
5.  Folgen Sie den Anweisungen des Assistenten auf dem Bildschirm, um die Datei TempCa.cer in den Speicher zu importieren.  
  
## <a name="using-certificates-with-wcf"></a>Verwenden von Zertifikaten mit WCF  
 Nach dem Einrichten der temporären Zertifikate können diese verwendet werden, um WCF-Lösungen zu entwickeln, mit denen Zertifikate als Clientanmeldeinformationstyp angegeben werden. So gibt beispielsweise die folgende XML-Konfiguration Nachrichtensicherheit und ein Zertifikat als Clientanmeldeinformationstyp an.  
  
#### <a name="to-specify-a-certificate-as-the-client-credential-type"></a>So geben Sie ein Zertifikat als Clientanmeldeinformationstyp an  
  
-   Verwenden Sie in der Konfigurationsdatei für einen Dienst die folgende XML, um den Sicherheitsmodus auf die Nachrichtenebene und den Clientanmeldeinformationstyp auf Zertifikate festzulegen:  
  
    ```xml  
    <bindings>       
      <wsHttpBinding>  
        <binding name="CertificateForClient">  
          <security>  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    ```  
  
 Verwenden Sie die folgende XML in der Konfigurationsdatei für einen Client um anzugeben, dass das Zertifikat im Speicher des Benutzers befindet und durch Durchsuchen des SubjectName-Felds für den Wert "CohoWinery" gefunden werden können  
  
```xml  
<behaviors>  
  <endpointBehaviors>  
    <behavior name="CertForClient">  
      <clientCredentials>  
        <clientCertificate findValue="CohoWinery" x509FindType="FindBySubjectName" />  
       </clientCredentials>  
     </behavior>  
   </endpointBehaviors>  
</behaviors>  
```  
  
 Weitere Informationen zum Verwenden von Zertifikaten in WCF finden Sie unter [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Achten Sie darauf, alle temporären Stammzertifizierungsstellen-Zertifikate aus den Ordnern **Vertrauenswürdige Stammzertifizierungsstellen** und **Persönlich** zu löschen, indem Sie mit der rechten Maustaste auf das Zertifikat klicken und anschließend auf **Löschen**klicken.  
  
## <a name="see-also"></a>Siehe auch  
 [Arbeiten mit Zertifikaten](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [Vorgehensweise: Anzeigen von Zertifikaten mit dem MMC-Snap-In](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)  
 [Sichern von Diensten und Clients](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
