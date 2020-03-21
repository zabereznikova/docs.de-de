---
title: 'Gewusst wie: Anzeigen von Zertifikaten mit dem MMC-Snap-In'
ms.date: 02/25/2019
helpviewer_keywords:
- certificates [WCF], viewing with the MMC snap-in
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
ms.openlocfilehash: 35048c24e838c513909fae8bedcba287001f5cef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184783"
---
# <a name="how-to-view-certificates-with-the-mmc-snap-in"></a>Gewusst wie: Anzeigen von Zertifikaten mit dem MMC-Snap-In
Wenn Sie einen sicheren Client oder Dienst erstellen, können Sie ein [Zertifikat](working-with-certificates.md) als Anmeldeinformationen verwenden. Ein üblicher Anmeldeinformationstyp ist z. B. das X.509-Zertifikat, das Sie mit der <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType> Methode erstellen.

Es gibt drei verschiedene Arten von Zertifikatspeichern, die Sie mit der Microsoft Management Console (MMC) auf Windows-Systemen untersuchen können:

- Lokaler Computer: Der Speicher ist lokal auf dem Gerät und global für alle Benutzer auf dem Gerät.

- Aktueller Benutzer: Der Speicher ist lokal für das aktuelle Benutzerkonto auf dem Gerät.

- Dienstkonto: Der Speicher ist für einen bestimmten Dienst auf dem Gerät lokal.

## <a name="view-certificates-in-the-mmc-snap-in"></a>Anzeigen von Zertifikaten im MMC-Snap-In

Das folgende Verfahren veranschaulicht, wie Sie die Speicher auf Ihrem lokalen Gerät überprüfen, um ein geeignetes Zertifikat zu finden:
  
1. Wählen Sie **Ausführen** aus dem **Startmenü** aus, und geben Sie dann *mmc*ein.

    Die MMC wird angezeigt.
  
2. Wählen Sie im Menü **Datei** die Option **Snap In hinzufügen/entfernen**aus.

    Das Fenster **Snap-Ins hinzufügen oder entfernen** wird angezeigt.
  
3. Wählen Sie in der Liste **Verfügbare Snap-Ins** **Zertifikate**aus, und wählen Sie dann **Hinzufügen**aus.  

    ![Hinzufügen eines Zertifikat-Snap-Ins](./media/mmc-add-certificate-snap-in.png)
  
4. Wählen Sie im **Snap-In-Fenster Zertifikate** die Option **Computerkonto**aus, und wählen Sie dann **Weiter**aus.
  
    Optional können Sie **Mein Benutzerkonto** für den aktuellen Benutzer oder **Dienstkonto** für einen bestimmten Dienst auswählen.

    > [!NOTE]
    > Wenn Sie kein Administrator für Ihr Gerät sind, können Sie Zertifikate nur für Ihr Benutzerkonto verwalten.
  
5. Lassen Sie im Fenster **Computer auswählen** den **lokalen Computer** aus, und wählen Sie dann Fertig **stellen**aus.  
  
6. Wählen Sie im Fenster **Snap-in hinzufügen oder entfernen** **OK**aus.  
  
    ![Hinzufügen eines Zertifikat-Snap-Ins](./media/mmc-certificate-snap-in-selected.png)

7. Optional: Wählen Sie im Menü **Datei** **speichern** oder **Speichern** unter aus, um die MMC-Konsolendatei für die spätere Verwendung zu speichern.  

8. Um Ihre Zertifikate im MMC-Snap-In anzuzeigen, wählen Sie **Konsolenstamm** im linken Bereich aus, und erweitern Sie dann **Zertifikate (Lokaler Computer)**.

    Eine Liste der Verzeichnisse für jeden Zertifikatstyp wird angezeigt. In jedem Zertifikatverzeichnis können Sie seine Zertifikate anzeigen, exportieren, importieren und löschen.

## <a name="view-certificates-with-the-certificate-manager-tool"></a>Anzeigen von Zertifikaten mit dem Zertifikats-Manager-Tool

Sie können Zertifikate auch anzeigen, exportieren, importieren und löschen, indem Sie das Zertifikats-Manager-Tool verwenden.

### <a name="to-view-certificates-for-the-local-device"></a>So zeigen Sie Zertifikate für das lokale Gerät an

1. Wählen Sie **Ausführen** aus dem **Startmenü** aus, und geben Sie dann *certlm.msc ein.*

    Das Zertifikats-Manager-Tool für das lokale Gerät wird angezeigt.
  
2. Um Ihre Zertifikate anzuzeigen, erweitern Sie unter **Zertifikate - Lokaler Computer** im linken Bereich das Verzeichnis für den Zertifikatstyp, den Sie anzeigen möchten.

### <a name="to-view-certificates-for-the-current-user"></a>So zeigen Sie Zertifikate für den aktuellen Benutzer an

1. Wählen Sie **Ausführen** aus dem **Startmenü** aus, und geben Sie dann *certmgr.msc ein.*

    Das Zertifikats-Manager-Tool für den aktuellen Benutzer wird angezeigt.
  
2. Um Ihre Zertifikate anzuzeigen, erweitern Sie unter **Zertifikate - Aktueller Benutzer** im linken Bereich das Verzeichnis für den Zertifikatstyp, den Sie anzeigen möchten.

## <a name="see-also"></a>Weitere Informationen

- [Arbeiten mit Zertifikaten](working-with-certificates.md)
- [Gewusst wie: Erstellen temporärer Zertifikate für die Verwendung während der Entwicklung](how-to-create-temporary-certificates-for-use-during-development.md)
- [Gewusst wie: Abrufen des Fingerabdrucks eines Zertifikats](how-to-retrieve-the-thumbprint-of-a-certificate.md)
