---
title: 'Vorgehensweise: Anzeigen von Zertifikaten mit dem MMC-Snap-in'
description: Ein sicherer WCF-Client oder-Dienst kann ein Zertifikat als Anmelde Informationen verwenden. Erfahren Sie mehr über die Typen von Zertifikat speichern, die Sie mithilfe des MMC-Plug-ins untersuchen können.
ms.date: 02/25/2019
helpviewer_keywords:
- certificates [WCF], viewing with the MMC snap-in
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
ms.openlocfilehash: 1f20384f16b3b5b898f926258d76a6a2773eaaa1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280623"
---
# <a name="how-to-view-certificates-with-the-mmc-snap-in"></a>Vorgehensweise: Anzeigen von Zertifikaten mit dem MMC-Snap-in

Wenn Sie einen sicheren Client oder Dienst erstellen, können Sie ein [Zertifikat](working-with-certificates.md) als Anmelde Informationen verwenden. Beispielsweise handelt es sich bei einem allgemeinen Anmelde Informationstyp um das X. 509-Zertifikat, das Sie mit der- <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType> Methode erstellen.

Es gibt drei verschiedene Typen von Zertifikat speichern, die Sie mit der Microsoft Management Console (MMC) auf Windows-Systemen untersuchen können:

- Lokaler Computer: der Speicher ist für das Gerät lokal und für alle Benutzer auf dem Gerät Global.

- Aktueller Benutzer: der Speicher ist für das aktuelle Benutzerkonto auf dem Gerät lokal.

- Dienst Konto: der Speicher ist für einen bestimmten Dienst auf dem Gerät lokal.

## <a name="view-certificates-in-the-mmc-snap-in"></a>Anzeigen von Zertifikaten im MMC-Snap-in

Im folgenden Verfahren wird veranschaulicht, wie Sie die Speicher auf Ihrem lokalen Gerät untersuchen, um ein entsprechendes Zertifikat zu finden:
  
1. Wählen Sie im **Startmenü** die Option **Ausführen** aus, und geben Sie dann *MMC* ein.

    Die MMC wird angezeigt.
  
2. Wählen Sie im Menü **Datei** die Option **Snap-in hinzufügen/entfernen** aus.

    Das Fenster **Snap-Ins hinzufügen bzw. entfernen** wird angezeigt.
  
3. Wählen Sie in der Liste **Verfügbare Snap-Ins** die Option **Zertifikate** und dann **Hinzufügen** aus.  

    ![Zertifikat-Snap-in hinzufügen](./media/mmc-add-certificate-snap-in.png)
  
4. Wählen Sie im Fenster **Zertifikate-Snap-in** die Option **Computer Konto** aus, und klicken Sie dann auf **weiter**.
  
    Optional können Sie das **Benutzerkonto** für das aktuelle Benutzer-oder **Dienst Konto** für einen bestimmten Dienst auswählen.

    > [!NOTE]
    > Wenn Sie kein Administrator für Ihr Gerät sind, können Sie Zertifikate nur für Ihr Benutzerkonto verwalten.
  
5. Lassen Sie im Fenster **Computer auswählen** die Option **lokaler Computer** ausgewählt, und klicken Sie dann auf **Fertig** stellen.  
  
6. Wählen Sie im Fenster **Snap-in hinzufügen/entfernen** die Option **OK** aus.  
  
    ![Zertifikat-Snap-in hinzufügen](./media/mmc-certificate-snap-in-selected.png)

7. Optional: Wählen Sie im Menü **Datei** die Option **Speichern** oder **Speichern** unter, um die MMC-Konsolen Datei zur späteren Verwendung zu speichern.  

8. Um Ihre Zertifikate im MMC-Snap-in anzuzeigen, klicken Sie im linken Bereich auf **Konsolen** Stamm und dann auf **Zertifikate (lokaler Computer)**.

    Eine Liste der Verzeichnisse für jeden Zertifikattyp wird angezeigt. Aus jedem Zertifikat Verzeichnis können Sie die Zertifikate anzeigen, exportieren, importieren und löschen.

## <a name="view-certificates-with-the-certificate-manager-tool"></a>Anzeigen von Zertifikaten mit dem Zertifikat-Manager-Tool

Mit dem Zertifikat-Manager-Tool können Sie Zertifikate auch anzeigen, exportieren, importieren und löschen.

### <a name="to-view-certificates-for-the-local-device"></a>So zeigen Sie Zertifikate für das lokale Gerät an

1. Wählen Sie im **Startmenü** die Option **Ausführen** aus, und geben Sie dann *certlm. msc* ein.

    Das Certificate Manager-Tool für das lokale Gerät wird angezeigt.
  
2. Um Ihre Zertifikate anzuzeigen, erweitern Sie im linken Bereich unter **Zertifikate-lokaler Computer** das Verzeichnis für den Typ des Zertifikats, das Sie anzeigen möchten.

### <a name="to-view-certificates-for-the-current-user"></a>So zeigen Sie Zertifikate für den aktuellen Benutzer an

1. Wählen Sie im Menü **Start** den Befehl **Ausführen** aus, und geben Sie *certmgr.msc* ein.

    Das Tool „Zertifikat-Manager“ für den aktuellen Benutzer wird angezeigt.
  
2. Um Ihre Zertifikate anzuzeigen, erweitern Sie im linken Bereich unter **Zertifikate-Aktueller Benutzer** das Verzeichnis für den Typ des Zertifikats, das Sie anzeigen möchten.

## <a name="see-also"></a>Weitere Informationen

- [Arbeiten mit Zertifikaten](working-with-certificates.md)
- [Vorgehensweise: Erstellen von temporären Zertifikaten für die Verwendung während der Entwicklung](how-to-create-temporary-certificates-for-use-during-development.md)
- [Vorgehensweise: Abrufen des Fingerabdrucks eines Zertifikats](how-to-retrieve-the-thumbprint-of-a-certificate.md)
