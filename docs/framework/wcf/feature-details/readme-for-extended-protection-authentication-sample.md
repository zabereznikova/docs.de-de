---
title: "Infodatei für das Beispiel zum erweiterten Schutz für die Authentifizierung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 80bf2e97-398d-4db5-9040-d96478a2ccab
caps.latest.revision: "3"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 78e787c129c0161e8730472124ee4162e2d1ba9d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="readme-for-extended-protection-authentication-sample"></a>Infodatei für das Beispiel zum erweiterten Schutz für die Authentifizierung
Erweiterter Schutz ist eine Sicherheitsinitiative zum Schutz vor Man-in-the-Middle-Angriffen (MITM), in dem ein Angreifer (die "Man-in-the-Middle"), fängt die Anmeldeinformationen des Clients ab, und verwendet sie den Zugriff auf sichere Ressourcen auf dem Client vorgesehenen Server.  
  
 Weitere Informationen finden Sie unter [erweiterter Schutz für die Authentifizierung (Übersicht)](../../../../docs/framework/wcf/feature-details/extended-protection-for-authentication-overview.md).  
  
> [!NOTE]
>  Dieses Beispiel funktioniert nur, wenn es auf IIS gehostet wird. Es funktioniert nicht unter Visual Studio Development Server, da hier keine HTTPS-Unterstützung gegeben ist.  
  
## <a name="to-set-up-build-and-run-the-sample"></a>So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Wählen Sie im Abschnitt zum Hinzufügen bzw. Entfernen von Programmen die Option für die Windows-Funktionen aus, um IIS auf dem Computer zu installieren.  
  
2.  Aktivieren Sie in den Windows-Funktionen die Windows-Authentifizierung: Internetinformationsdienste -> World Wide Web-Dienst -> Sicherheit -> Windows-Authentifizierung.  
  
3.  Aktivieren Sie in den Windows-Funktionen die HTTP-Aktivierung: Microsoft .NET Framework 3.5.1 -> Windows Communication Foundation-Http-Aktivierung.  
  
4.  In diesem Beispiel muss der Client eine Verbindung über einen sicheren Kanal zum Server herstellen. Dazu muss ein Serverzertifikat vorliegen, das im IIS (Internet Information Services)-Manager installiert werden kann.  
  
    1.  Öffnen Sie auf der Registerkarte mit den Funktionen „IIS-Manager“ -> „Serverzertifikate“.  
  
    2.  Für dieses Beispiel können Sie ein selbstsigniertes Zertifikat erstellen. (Wenn Sie von Internet Explorer keine Meldung hinsichtlich der fehlenden Sicherheit des Zertifikats erhalten möchten, können Sie es im entsprechenden Autoritätsspeicher für vertrauenswürdige Zertifikate installieren).  
  
5.  Wechseln Sie zum Aktionsbereich für die Standardwebsite. Klicken Sie auf die Option zum Bearbeiten der Website und anschließend auf "Bindungen". Falls nicht bereits vorhanden, fügen Sie HTTPS als Typ mit der Anschlussnummer 443 hinzu, und weisen Sie das im vorherigen Schritt erstellte SSL-Zertifikat zu.  
  
6.  Erstellen Sie den Dienst. In IIS wird gemäß der in den Projekteigenschaften angegebenen Postbuildaktion ein virtuelles Verzeichnis erstellt, und die für das Webhosting des Diensts erforderlichen DLL-, SVC- und CONFIG-Dateien werden kopiert.  
  
7.  Öffnen Sie den IIS-Manager. Klicken Sie mit der rechten Maustaste auf das virtuelle Verzeichnis (ExtendedProtection), das Sie im vorhergehenden Schritt erstellt haben, und wählen Sie die Option zum Konvertieren in eine Anwendung.  
  
8.  Öffnen Sie das Authentifizierungsmodul für das virtuelle Verzeichnis in IIS Manager, und aktivieren Sie die Windows-Authentifizierung.  
  
9. Öffnen Sie die erweiterten Einstellungen für die Windows-Authentifizierung für dieses virtuelle Verzeichnis, und legen Sie es auf "Erforderlich" fest, da in diesem Beispiel die entsprechende ExtendedProtection-Einstellung auf "Immer" festgelegt ist.  
  
10. Testen Sie den Dienst, indem Sie von einem Browserfenster aus auf die URL zugreifen. Möchten Sie von einem Computer im Netzwerk aus auf die URL zugreifen, konfigurieren Sie die Firewall entsprechend, damit ein- und ausgehende HTTP- und HTTPS-Verbindungen hergestellt werden können.  
  
11. Öffnen Sie die Client-Config-Datei, und geben Sie den vollständigen Computernamen für die \<Client >- \<Endpunkt >--adressenattribut << Full_machine_name >> ersetzen.  
  
12. Führen Sie den Client aus. Der Client kommuniziert mit dem Dienst über einen sicheren Kanal und verwendet verdeckt die erweiterte Sicherheit.
