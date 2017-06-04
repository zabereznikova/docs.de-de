---
title: "Vorgehensweise: Angeben der Zertifizierungsstellenzertifikatskette, die verwendet wird, um Signaturen (WCF) zu &#252;berpr&#252;fen | Microsoft Docs"
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
  - "Zertifikate [WCF], Angeben der Zertifizierungsstellenzertifikatskette."
  - "Zertifikate [WCF], Verifizieren von Signaturen"
ms.assetid: 7c719355-aa41-4567-80d0-5115a8cf73fd
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Vorgehensweise: Angeben der Zertifizierungsstellenzertifikatskette, die verwendet wird, um Signaturen (WCF) zu &#252;berpr&#252;fen
Wenn [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] eine mit einem X.509\-Zertifikat signierte SOAP\-Nachricht empfängt, wird standardmäßig überprüft, ob das X.509\-Zertifikat von einer vertrauenswürdigen Zertifizierungsstelle ausgestellt wurde.Dies erfolgt durch Prüfen eines Zertifikatsspeichers und Feststellen, ob das Zertifikat für diese Zertifizierungsstelle als vertrauenswürdig bestimmt worden ist.Damit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] diese Feststellung machen kann, muss die Zertifizierungsstellenzertifikatskette im richtigen Zertifikatsspeicher installiert werden.  
  
### So installieren Sie eine Zertifizierungsstellenzertifikatskette  
  
-   Installieren Sie für jede Zertifizierungsstelle, für die ein SOAP\-Nachrichtenempfänger die von ihr ausgegebenen X.509\-Zertifikate als vertrauenswürdig behandeln möchte, die Zertifizierungsstellenzertifikatskette in dem Zertifikatsspeicher, von dem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] aufgrund der Konfiguration X.509\-Zertifikate abrufen kann.  
  
     Wenn z. B. ein SOAP\-Nachrichtenempfänger von Microsoft ausgegebene X.509\-Zertifikate als vertrauenswürdig behandeln möchte, muss die Zertifizierungsstellenzertifikatskette für Microsoft in dem Zertifikatsspeicher installiert werden, in dem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] aufgrund der Einrichtung nach X.509\-Zertifikaten sucht.Der Zertifikatspeicher, in dem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] nach X.509\-Zertifikaten sucht, kann im Code oder in der Konfiguration festgelegt werden.Dies kann z. B. im Code mithilfe der <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A>\-Methode oder in der Konfiguration auf verschiedene Arten erfolgen, einschließlich mithilfe von [\<serviceCertificate\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md).  
  
     Da Windows mit einem Satz an Standardzertifikatsketten für vertrauenswürdige Zertifizierungsstellen geliefert wird, ist es u. U. nicht erforderlich, die Zertifikatskette für alle Zertifizierungsstellen zu installieren.  
  
    1.  Exportieren Sie die Zertifizierungsstellenzertifikatskette.  
  
         Wie dies genau erfolgt, hängt von der Zertifizierungsstelle ab.Wenn bei der Zertifizierungsstelle Microsoft\-Zertifikatsdienste ausgeführt werden, wählen Sie **Download eines Zertifizierungsstellenzertifikats, einer Zertifikatskette oder einer Sperrliste** aus, und wählen Sie dann **Download des Zertifizierungsstellenzertifikats**.  
  
    2.  Importieren Sie die Zertifizierungsstellenzertifikatskette.  
  
         Öffnen Sie das Zertifikats\-Snap\-in in der Microsoft Management Console \(MMC\).Wählen Sie für den Zertifikatsspeicher, von dem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] aufgrund der Konfiguration X.509\-Zertifikate abruft, den Ordner **Vertrauenswürdige Stamm** **zertifizierungsstellen**.Klicken Sie mit der rechten Maustaste unter dem Ordner **Vertrauenswürdige Stammzertifzierungsstellen** auf den Ordner **Zertifikate**, zeigen Sie auf **Alle Aufgaben**, und klicken Sie anschließend auf **Importieren**.Geben Sie die in Schritt a exportierte Datei an.  
  
         [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zum Verwenden des Zertifikats\-Snap\-in mit MMC finden Sie unter [Vorgehensweise: Anzeigen von Zertifikaten mit dem MMC\-Snap\-In](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).  
  
## Siehe auch  
 [Verwenden von Zertifikaten](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)