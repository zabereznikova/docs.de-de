---
title: Infodatei für das Beispiel zum erweiterten Schutz für die Authentifizierung
ms.date: 03/30/2017
ms.assetid: 80bf2e97-398d-4db5-9040-d96478a2ccab
ms.openlocfilehash: 9b0a3535282a1fcc1103651f5601459e80d3d8d4
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601100"
---
# <a name="readme-for-extended-protection-authentication-sample"></a>Infodatei für das Beispiel zum erweiterten Schutz für die Authentifizierung

Der erweiterte Schutz ist eine Sicherheitsinitiative zum Schutz vor man-in-the-Middle-Angriffen (MITM), bei denen ein Angreifer ("man-in-the-Middle") die Anmelde Informationen eines Clients abfängt und Sie für den Zugriff auf sichere Ressourcen auf dem vorgesehenen Server des Clients verwendet.

Weitere Informationen finden Sie unter [Erweiterter Schutz für die Authentifizierung Übersicht](extended-protection-for-authentication-overview.md).

> [!NOTE]
> Dieses Beispiel funktioniert nur, wenn es auf IIS gehostet wird. Es funktioniert nicht unter Visual Studio Development Server, da hier keine HTTPS-Unterstützung gegeben ist.

## <a name="to-set-up-build-and-run-the-sample"></a>So richten Sie das Beispiel ein, erstellen es und führen es aus

1. Installieren Sie IIS auf dem Computer unter "Software-> Windows-Features".

2. Aktivieren Sie die Windows-Authentifizierung in Windows-Features: Internetinformationsdienste-> World Wide Web Services-> Sicherheit-> Windows-Authentifizierung.

3. Aktivieren Sie die HTTP-Aktivierung in Windows-Features: Microsoft .NET Framework 3.5.1-> Windows Communication Foundation http-Aktivierung.

4. In diesem Beispiel muss der Client eine Verbindung über einen sicheren Kanal zum Server herstellen. Dazu muss ein Serverzertifikat vorliegen, das im IIS (Internet Information Services)-Manager installiert werden kann.

    1. Öffnen Sie die IIS-Manager-> Server Zertifikate (auf der Registerkarte Funktions Ansicht).

    2. Für dieses Beispiel können Sie ein selbstsigniertes Zertifikat erstellen. (Wenn Sie von Internet Explorer keine Meldung hinsichtlich der fehlenden Sicherheit des Zertifikats erhalten möchten, können Sie es im entsprechenden Autoritätsspeicher für vertrauenswürdige Zertifikate installieren).

5. Wechseln Sie zum Aktionsbereich für die Standardwebsite. Klicken Sie auf Website > Bindungen bearbeiten. Falls nicht bereits vorhanden, fügen Sie HTTPS als Typ mit der Anschlussnummer 443 hinzu, und weisen Sie das im vorherigen Schritt erstellte SSL-Zertifikat zu.

6. Erstellen Sie den Dienst. In IIS wird gemäß der in den Projekteigenschaften angegebenen Postbuildaktion ein virtuelles Verzeichnis erstellt, und die für das Webhosting des Diensts erforderlichen DLL-, SVC- und CONFIG-Dateien werden kopiert.

7. Öffnen Sie den IIS-Manager. Klicken Sie mit der rechten Maustaste auf das virtuelle Verzeichnis (ExtendedProtection), das Sie im vorhergehenden Schritt erstellt haben, und wählen Sie die Option zum Konvertieren in eine Anwendung.

8. Öffnen Sie das Authentifizierungsmodul für das virtuelle Verzeichnis in IIS Manager, und aktivieren Sie die Windows-Authentifizierung.

9. Öffnen Sie die erweiterten Einstellungen für die Windows-Authentifizierung für dieses virtuelle Verzeichnis, und legen Sie es auf "Erforderlich" fest, da in diesem Beispiel die entsprechende ExtendedProtection-Einstellung auf "Immer" festgelegt ist.

10. Testen Sie den Dienst, indem Sie von einem Browserfenster aus auf die URL zugreifen. Möchten Sie von einem Computer im Netzwerk aus auf die URL zugreifen, konfigurieren Sie die Firewall entsprechend, damit ein- und ausgehende HTTP- und HTTPS-Verbindungen hergestellt werden können.

11. Öffnen Sie die Client Konfigurationsdatei, und geben Sie einen vollständigen Computernamen für das \<client>  -  \<endpoint> -address-Attribut an \<full_machine_name> .

12. Führen Sie den Client aus. Der Client kommuniziert mit dem Dienst über einen sicheren Kanal und verwendet verdeckt die erweiterte Sicherheit.
