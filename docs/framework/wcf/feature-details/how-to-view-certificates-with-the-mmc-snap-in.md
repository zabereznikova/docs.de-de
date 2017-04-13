---
title: "Vorgehensweise: Anzeigen von Zertifikaten mit dem MMC-Snap-In | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Zertifikate [WCF], Anzeigen mit dem MMC-Snap-In"
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Vorgehensweise: Anzeigen von Zertifikaten mit dem MMC-Snap-In
Ein allgemeiner Typ der Anmeldeinformationen ist das X.509\-Zertifikat.Bei der Erstellung sicherer Dienste oder Clients können Sie ein Zertifikat angeben, das als Anmeldeinformation für Client oder Dienst über die Methoden wie beispielsweise <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> verwendet wird.Die Methode erfordert diverse Parameter; beispielsweise den Speicherplatz des Zertifikats und eines Werts, der für die Suche eines Zertifikats verwendet wird.Die folgende Prozedur veranschaulicht, wie die Speicherplätze auf einem Computer untersucht werden, um ein entsprechendes Zertifikat zu suchen.Ein Beispiel für das Suchen eines Zertifikat\-Fingerabdrucks finden Sie unter [Vorgehensweise: Abrufen des Fingerabdrucks eines Zertifikats](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).  
  
### So zeigen Sie Zertifikate im MMC\-Snap\-In an  
  
1.  Öffnen Sie ein Eingabeaufforderungsfenster.  
  
2.  Geben Sie `mmc` ein, und drücken Sie die Eingabetaste.Beachten Sie, dass Sie in der Administratorrolle sein müssen, um Zertifikate im lokalen Computerspeicher anzuzeigen.  
  
3.  Klicken Sie im Menü **Datei** auf **Snap\-In hinzufügen\/entfernen**.  
  
4.  Klicken Sie auf **Hinzufügen**.  
  
5.  Wählen Sie im Dialogfeld **Eigenständiges Snap\-In hinzufügen** **Zertifikate**.  
  
6.  Klicken Sie auf **Hinzufügen**.  
  
7.  Wählen Sie im Dialogfeld **Zertifikate** des Snap\-Ins **Computerkonto** aus, und klicken Sie auf **Weiter**.Optional können Sie **Eigenes Benutzerkonto** oder **Dienstkonto** auswählen.Sind Sie kein Verwalter des Computers, können Sie Zertifikate nur für Ihr Benutzerkonto verwalten.  
  
8.  Klicken Sie im Dialogfeld **Computer auswählen** auf **Fertig stellen**.  
  
9. Wählen Sie im Dialogfeld **Eigenständiges Snap\-In hinzufügen** **Schließen** aus.  
  
10. Klicken Sie im Dialogfeld **Snap\-In hinzufügen\/entfernen** auf **OK**.  
  
11. Klicken Sie im Fenster **Konsolenstamm** auf **Zertifikate \(Lokaler Computer\)**, um die Zertifikatspeicher für den Computer anzuzeigen.  
  
12. Optional.Wiederholen Sie die Schritte 3 bis 6, um Zertifikate für Ihr Konto anzuzeigen.Wählen Sie in Schritt 7 anstelle von **Computerkonto** die Option **Eigenes Benutzerkonto** aus, und wiederholen Sie die Schritte 8 bis 10.  
  
13. Optional.Klicken Sie im Menü **Datei** auf **Speichern** oder **Speichern unter**.Speichern Sie die Konsolendatei zur späteren Wiederverwendung.  
  
## Anzeigen von Zertifikaten mit Internet Explorer  
 Darüber hinaus können Sie Zertifikate mit dem Internet Explorer ansehen, exportieren, importieren und löschen.  
  
#### So zeigen Sie Zertifikate mit dem Internet Explorer an  
  
1.  Klicken Sie im Internet Explorer auf **Extras** und dann auf **Internetoptionen**, um das Dialogfeld **Internetoptionen** zu öffnen.  
  
2.  Klicken Sie auf die Registerkarte **Inhalte**.  
  
3.  Klicken Sie unter **Zertifikate** auf **Zertifikate**.  
  
4.  Um Details eines Zertifikats anzuzeigen, wählen Sie das Zertifikat aus, und klicken Sie auf **Anzeigen**.  
  
## Siehe auch  
 [Verwenden von Zertifikaten](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)   
 [Gewusst wie: Erstellen von temporären Zertifikaten für die Verwendung während der Entwicklung](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)   
 [Vorgehensweise: Abrufen des Fingerabdrucks eines Zertifikats](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)