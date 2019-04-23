---
title: 'Vorgehensweise: Anzeigen von Zertifikaten mit dem MMC-Snap-in'
ms.date: 02/25/2019
helpviewer_keywords:
- certificates [WCF], viewing with the MMC snap-in
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
ms.openlocfilehash: 69f79b64250ff46524e7b4720d13351774875a3f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59167504"
---
# <a name="how-to-view-certificates-with-the-mmc-snap-in"></a>Vorgehensweise: Anzeigen von Zertifikaten mit dem MMC-Snap-in
Wenn Sie einen sicheren Client oder Dienst erstellen, können Sie eine [Zertifikat](working-with-certificates.md) als die Anmeldeinformationen. Ein allgemeiner Typ der Anmeldeinformationen ist z. B. das x. 509-Zertifikat, das Sie erstellen, mit der <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType> Methode. 

Es gibt drei verschiedene Typen von Zertifikatspeichern, die Sie, mit der Microsoft Management Console (MMC) auf Windows-Systemen untersuchen können:

- Lokaler Computer: Der Speicher ist lokal auf dem Gerät und global für alle Benutzer auf dem Gerät.

- Aktueller Benutzer: Der Speicher ist für das aktuelle Benutzerkonto auf dem Gerät lokal.

- Dienstkonto: Der Speicher ist für einen bestimmten Dienst auf dem Gerät lokal.

## <a name="view-certificates-in-the-mmc-snap-in"></a>Anzeigen von Zertifikaten im MMC-Snap-in 

Das folgende Verfahren veranschaulicht, wie der Speicher auf dem lokalen Gerät finden Sie ein entsprechendes Zertifikat zu überprüfen: 
  
1. Wählen Sie **ausführen** aus der **starten** Menü, und geben Sie dann *Mmc*. 

    Die MMC wird angezeigt. 
  
2. Von der **Datei** , wählen Sie im Menü **Snap-In hinzufügen/entfernen**. 
    
    Die **hinzufügen oder Entfernen von-Snap-ins** Fenster wird angezeigt.
  
3. Von der **Verfügbare Snap-Ins** wählen **Zertifikate**, und wählen Sie dann **hinzufügen**.  

    ![Zertifikat-Snap-in hinzufügen](./media/mmc-add-certificate-snap-in.png)
  
4. In der **Zertifikat-Snap-in** wählen Sie im Fenster **Computerkonto**, und wählen Sie dann **Weiter**. 
  
    Wählen Sie optional **mein Benutzerkonto** für den aktuellen Benutzer oder **-Dienstkonto** für einen bestimmten Dienst. 

    > [!NOTE]
    > Wenn Sie für Ihr Gerät kein Administrator sind, können Sie Zertifikate nur für Ihr Benutzerkonto verwalten.
  
5. In der **Computer auswählen** Fenster verlassen **lokalen Computer** ausgewählt, und wählen Sie dann **Fertig stellen**.  
  
6. In der **hinzufügen oder Entfernen von Snap-Ins** wählen Sie im Fenster **OK**.  
  
    ![Zertifikat-Snap-in hinzufügen](./media/mmc-certificate-snap-in-selected.png)

7. Optional: Von der **Datei** , wählen Sie im Menü **speichern** oder **speichern** zum Speichern der Datei des MMC-Konsole für die spätere Verwendung.  

8. Wählen Sie zum Anzeigen Ihrer Zertifikate im MMC-Snap-in **Konsolenstamm** im linken Bereich, und erweitern Sie dann **Zertifikate (lokaler Computer)**.

    Eine Liste der Verzeichnisse für jeden Typ von Zertifikat wird angezeigt. Jedes Verzeichnis Zertifikat können Sie anzeigen, exportieren, importieren und die Zertifikate zu löschen.

## <a name="view-certificates-with-the-certificate-manager-tool"></a>Anzeigen von Zertifikaten mit dem Zertifikat-Manager-tool

Sie können auch anzeigen, exportieren, importieren und Löschen von Zertifikaten mit dem Zertifikat-Manager-Tool.

### <a name="to-view-certificates-for-the-local-device"></a>Zertifikate für das lokale Gerät angezeigt

1. Wählen Sie **ausführen** aus der **starten** Menü, und geben Sie dann *"certlm.msc"*. 

    Das Zertifikat-Manager-Tool für das lokale Gerät angezeigt wird. 
  
2. Die Zertifikate, unter anzeigen **Zertifikate – lokaler Computer** im linken Bereich, erweitern Sie in das Verzeichnis für den Typ des Zertifikats, die Sie anzeigen möchten.

### <a name="to-view-certificates-for-the-current-user"></a>Zum Anzeigen der Zertifikate für den aktuellen Benutzer

1. Wählen Sie **ausführen** aus der **starten** Menü, und geben Sie dann *"Certmgr.msc"*. 

    Das Zertifikat-Manager-Tool für den aktuellen Benutzer angezeigt wird. 
  
2. Die Zertifikate, unter anzeigen **Zertifikate - Aktueller Benutzer** im linken Bereich, erweitern Sie in das Verzeichnis für den Typ des Zertifikats, die Sie anzeigen möchten.

## <a name="see-also"></a>Siehe auch

- [Arbeiten mit Zertifikaten](working-with-certificates.md)
- [Vorgehensweise: Erstellen von temporären Zertifikaten für die Verwendung während der Entwicklung](how-to-create-temporary-certificates-for-use-during-development.md)
- [Vorgehensweise: Abrufen des Fingerabdrucks eines Zertifikats](how-to-retrieve-the-thumbprint-of-a-certificate.md)
