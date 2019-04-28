---
title: Installationsanleitung für IIS-Serverzertifikate (Internetinformationsdienste)
ms.date: 03/30/2017
ms.assetid: 11281490-d2ac-4324-8f33-e7714611a34b
ms.openlocfilehash: 8d0b80930424f0d8529f2b035a8e1167f361f99a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61752490"
---
# <a name="internet-information-services-iis-server-certificate-installation-instructions"></a>Installationsanleitung für IIS-Serverzertifikate (Internetinformationsdienste)
Zum Ausführen der Beispiele, die über eine sichere Kommunikation mit Internetinformationsdiensten (IIS) verbunden sind, müssen Sie ein Serverzertifikat erstellen und installieren.  
  
## <a name="step-1-creating-certificates"></a>Schritt 1. Erstellen von Zertifikaten  
 Um ein Zertifikat für den Computer zu erstellen, öffnen Sie eine Developer-Eingabeaufforderung für Visual Studio mit Administratorrechten, und führen Sie die Datei Setup.bat aus, die in den einzelnen Beispielen enthalten ist, die sicheren Kommunikation mit IIS zu verwenden. Stellen Sie vor dem Ausführen dieser Batchdatei sicher, dass der Pfad den Ordner einschließt, in dem sich die Datei Makecert.exe befindet. Der folgende Befehl wird zum Erstellen des Zertifikats in Setup.bat verwendet.  
  
```  
makecert -sr LocalMachine -ss My -n CN=ServiceModelSamples-HTTPS-Server -sky exchange -sk ServiceModelSamples-HTTPS-Key  
```  
  
## <a name="step-2-installing-certificates"></a>Schritt 2 Installieren von Zertifikaten  
 Welche Schritte Sie zum Installieren der erstellten Zertifikate ausführen müssen, hängt von der verwendeten IIS-Version ab.  
  
#### <a name="to-install-iis-on-iis-51-windows-xp-and-iis-60-windows-server-2003"></a>Installation mit IIS 5.1 (Windows XP) und IIS 6.0 (Windows Server 2003)  
  
1. Öffnen Sie das MMC-Snap-In Internetinformationsdienste-Manager.  
  
2. Mit der rechten Maustaste die Standardwebsite, und wählen Sie **Eigenschaften**.  
  
3. Wählen Sie die **Verzeichnissicherheit** Registerkarte.  
  
4. Klicken Sie auf die **Serverzertifikat** Schaltfläche. Der Assistent für Webserverzertifikate wird gestartet.  
  
5. Durchlaufen Sie den Assistenten. Wählen Sie die Option zum Zuweisen eines Zertifikats aus. Wählen Sie aus der angezeigten Liste mit Zertifikaten das Zertifikat ServiceModelSamples-HTTPS-Server aus.  
  
     ![IIS-Zertifikat-Assistent](../../../../docs/framework/wcf/samples/media/iiscertificate-wizard.GIF "IISCertificate_Wizard")  
  
6. Testen Sie den Zugriff auf den Dienst unter Verwendung der HTTPS-Adresse in einem Browser `https://localhost/servicemodelsamples/service.svc`.  
  
#### <a name="if-ssl-was-previously-configured-by-using-httpcfgexe"></a>Wenn zuvor SSL mit Httpcfg.exe konfiguriert wurde  
  
1. Verwenden Sie zum Erstellen des Serverzertifikats Makecert.exe (oder führen Sie Setup.bat aus).  
  
2. Führen Sie den IIS-Manager aus, und installieren Sie das Zertifikat wie oben beschrieben.  
  
3. Fügen Sie dem Clientprogramm folgenden Code hinzu.  
  
> [!IMPORTANT]
>  Dieser Code ist nur für Testzertifikate erforderlich, die z. B. mit Makecert.exe erstellt wurden. Er wird nicht für Produktionsumgebungen empfohlen.  
  
```  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```  
  
#### <a name="to-install-iis-on-iis-70-windows-vista-and-windows-server-2008"></a>Installation mit IIS&amp;#160;7.0 (Windows&amp;#160;Vista und Windows Server&amp;#160;2008)  
  
1. Von der **starten** Menü klicken Sie auf **ausführen**, geben Sie dann **Inetmgr** auf das Internet Information Services (IIS)-MMC-Snap-in zu öffnen.  
  
2. Mit der rechten Maustaste die **Default Web Site** , und wählen Sie **Bindungen bearbeiten...**  
  
3. Klicken Sie auf die **hinzufügen** -Schaltfläche der **Sitebindungen** Dialogfeld.  
  
4. Wählen Sie **HTTPS** aus der **Typ** Dropdown-Liste.  
  
5. Wählen Sie die **ServiceModelSamples-HTTPS-Server** aus der **SSL-Zertifikat** Dropdown-Liste und klicken Sie auf **OK**.  
  
6. Testen Sie den Zugriff auf den Dienst unter Verwendung der HTTPS-Adresse in einem Browser `https://localhost/servicemodelsamples/service.svc`.  
  
> [!NOTE]
>  Da es sich bei dem gerade installierten Testzertifikat nicht um ein vertrauenswürdiges Zertifikat handelt, werden im Internet Explorer möglicherweise zusätzliche Sicherheitswarnungen angezeigt, wenn Sie zu lokalen Webseiten navigieren, die dieses Zertifikat verwenden.  
  
## <a name="removing-certificates"></a>Entfernen von Zertifikaten  
  
- Führen Sie im Internetinformationsdienste-Manager die zuvor beschriebenen Schritte aus. Entfernen Sie jedoch das Zertifikat bzw. die Bindung, anstatt sie hinzuzufügen.  
  
- Entfernen Sie das Computerzertifikat mit dem folgenden Befehl.  
  
    ```  
    httpcfg delete ssl -i 0.0.0.0:443  
    ```
