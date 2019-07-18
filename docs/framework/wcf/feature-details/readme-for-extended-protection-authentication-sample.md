---
title: Infodatei für das Beispiel zum erweiterten Schutz für die Authentifizierung
ms.date: 03/30/2017
ms.assetid: 80bf2e97-398d-4db5-9040-d96478a2ccab
ms.openlocfilehash: cc60ee32efcbe1e6ac1ce620fa1c17504db5197f
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2019
ms.locfileid: "66690577"
---
# <a name="readme-for-extended-protection-authentication-sample"></a>Infodatei für das Beispiel zum erweiterten Schutz für die Authentifizierung

Erweiterter Schutz ist eine Sicherheitsinitiative zum Schutz vor Man-in-the-Middle (MITM)-Angriffen, in dem ein Angreifer (der "Man-in-the-Middle"), fängt die Anmeldeinformationen eines Clients, und verwendet, um den Zugriff auf sichere Ressourcen auf dem Client vorgesehenen Server.

Weitere Informationen finden Sie unter [erweiterter Schutz für die Authentifizierung (Übersicht)](../../../../docs/framework/wcf/feature-details/extended-protection-for-authentication-overview.md).

> [!NOTE]
> Dieses Beispiel funktioniert nur, wenn es auf IIS gehostet wird. Es funktioniert nicht unter Visual Studio Development Server, da hier keine HTTPS-Unterstützung gegeben ist.

## <a name="to-set-up-build-and-run-the-sample"></a>So richten Sie das Beispiel ein, erstellen es und führen es aus

1. Installieren von IIS auf dem Computer von Software -> Windows-Features.

2. Aktivieren Sie auf der Windows-Authentifizierung in Windows-Features: Internetinformationsdienste -> World Wide Web Services -> Sicherheit -> Windows-Authentifizierung.

3. HTTP-Aktivierung in Windows-Features aktivieren: Microsoft .NET Framework 3.5.1 -> Windows Communication Foundation HTTP Activation.

4. In diesem Beispiel muss der Client eine Verbindung über einen sicheren Kanal zum Server herstellen. Dazu muss ein Serverzertifikat vorliegen, das im IIS (Internet Information Services)-Manager installiert werden kann.

    1. Öffnen Sie der IIS-Manager -> Serverzertifikate (auf der Registerkarte des Feature-Ansicht).

    2. Für dieses Beispiel können Sie ein selbstsigniertes Zertifikat erstellen. (Wenn Sie von Internet Explorer keine Meldung hinsichtlich der fehlenden Sicherheit des Zertifikats erhalten möchten, können Sie es im entsprechenden Autoritätsspeicher für vertrauenswürdige Zertifikate installieren).

5. Wechseln Sie zum Aktionsbereich für die Standardwebsite. Klicken Sie auf Bearbeiten Bindungen-Website >. Falls nicht bereits vorhanden, fügen Sie HTTPS als Typ mit der Anschlussnummer 443 hinzu, und weisen Sie das im vorherigen Schritt erstellte SSL-Zertifikat zu.

6. Erstellen Sie den Dienst. In IIS wird gemäß der in den Projekteigenschaften angegebenen Postbuildaktion ein virtuelles Verzeichnis erstellt, und die für das Webhosting des Diensts erforderlichen DLL-, SVC- und CONFIG-Dateien werden kopiert.

7. Öffnen Sie den IIS-Manager. Klicken Sie mit der rechten Maustaste auf das virtuelle Verzeichnis (ExtendedProtection), das Sie im vorhergehenden Schritt erstellt haben, und wählen Sie die Option zum Konvertieren in eine Anwendung.

8. Öffnen Sie das Authentifizierungsmodul für das virtuelle Verzeichnis in IIS Manager, und aktivieren Sie die Windows-Authentifizierung.

9. Öffnen Sie die erweiterten Einstellungen für die Windows-Authentifizierung für dieses virtuelle Verzeichnis, und legen Sie es auf "Erforderlich" fest, da in diesem Beispiel die entsprechende ExtendedProtection-Einstellung auf "Immer" festgelegt ist.

10. Testen Sie den Dienst, indem Sie von einem Browserfenster aus auf die URL zugreifen. Möchten Sie von einem Computer im Netzwerk aus auf die URL zugreifen, konfigurieren Sie die Firewall entsprechend, damit ein- und ausgehende HTTP- und HTTPS-Verbindungen hergestellt werden können.

11. Öffnen Sie die Client-Config-Datei, und geben Sie den vollständigen Computernamen für die \<Client >- \<Endpunkt >-Adressattribut aus, und Ersetzen Sie dabei \<Full_machine_name >.

12. Führen Sie den Client aus. Der Client kommuniziert mit dem Dienst über einen sicheren Kanal und verwendet verdeckt die erweiterte Sicherheit.
