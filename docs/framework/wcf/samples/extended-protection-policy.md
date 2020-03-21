---
title: Erweiterte Schutzrichtlinie
ms.date: 03/30/2017
ms.assetid: e2616a10-317e-4c34-8023-0c015a80a82f
ms.openlocfilehash: 3a5b1c7f296c68d407f0217963dec56f53e9a08a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144721"
---
# <a name="extended-protection-policy"></a>Erweiterte Schutzrichtlinie
Der erweiterte Schutz ist eine Sicherheitsinitiative zum Schutz vor Man-In-The-Middle-Angriffen (MITM-Angriff, Janusangriff). Ein MITM-Angriff ist eine Sicherheitsbedrohung, bei der ein MITM die Anmeldeinformationen eines Clients an einen Server weiterleitet.  
  
## <a name="demonstrates"></a>Zeigt  
 Erweiterter Schutz  
  
## <a name="discussion"></a>Diskussion  
 Wenn sich Anwendungen über Kerberos, Digest oder NTLM mit HTTPS authentifizieren, wird zunächst ein Transport Level Security (TLS)-Kanal eingerichtet. Die Authentifizierung erfolgt dann über den sicheren Kanal. Zwischen dem von SSL und dem bei der Authentifizierung erstellten Sitzungsschlüssel besteht jedoch keine Bindung. Jeder MITM kann sich zwischen den Client und den Server schalten und anfangen, die Anforderungen vom Client weiterzuleiten, auch wenn der Transportkanal selbst sicher ist. Der Server selbst kann nicht feststellen, ob der sichere Kanal vom Client oder von einem MITM eingerichtet wurde. Die Lösung bei einem Szenario dieser Art besteht darin, den äußeren TLS-Kanal mit dem inneren Authentifizierungskanal auf eine Weise zu binden, die es dem Server ermöglicht, festzustellen, ob es einen MITM gibt.  
  
> [!NOTE]
> Dieses Beispiel funktioniert nur, wenn es unter IIS gehostet wird und nicht unter Cassini – Visual Studio Development Server, da hier keine HTTPS-Unterstützung gegeben ist.  
  
> [!NOTE]
> Diese Funktion ist aktuell nur unter Windows 7 verfügbar. Die folgenden Schritte gelten für Windows 7.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Installieren Sie Internetinformationsdienste aus der **Systemsteuerung**, **Hinzufügen/Entfernen von Programmen**, **Windows-Features**.  
  
2. Installieren Sie die **Windows-Authentifizierung** in **Windows Features**, **InternetInformation Services**, World Wide Web **Services**, **Security**und **Windows Authentication**.  
  
3. Installieren Sie **die HTTP-Aktivierung von Windows Communication Foundation** in Windows **Features**, **Microsoft .NET Framework 3.5.1**und **Windows Communication Foundation HTTP Activation**.  
  
4. In diesem Beispiel muss der Client eine Verbindung über einen sicheren Kanal zum Server herstellen. Dazu muss ein Serverzertifikat vorliegen, das im IIS (Internet Information Services)-Manager installiert werden kann.  
  
    1. Öffnen Sie IIS-Manager. Öffnen Sie **Serverzertifikate**, die auf der Registerkarte **Feature-Ansicht** angezeigt werden, wenn der Stammknoten (Computername) ausgewählt ist.  
  
    2. Erstellen Sie zum Testen dieses Beispiels ein selbstsigniertes Zertifikat. Wenn Sie von Internet Explorer keine Meldung hinsichtlich der fehlenden Sicherheit des Zertifikats erhalten möchten, installieren Sie das Zertifikat im entsprechenden Autoritätsspeicher für vertrauenswürdige Zertifikate.  
  
5. Öffnen Sie den Bereich **Aktionen** für die Standardwebsite. Klicken Sie auf **Site bearbeiten**, **Bindungen**. Fügen Sie HTTPS als Typ hinzu, wenn nicht bereits vorhanden ist, und geben Sie die Portnummer 443 an. Weisen Sie das im vorangehenden Schritt erstellte SSL-Zertifikat zu.  
  
6. Erstellen Sie den Dienst. Hierdurch wird ein virtuelles Verzeichnis in IIS erstellt. Die DLL-, SVC- und CONFIG-Dateien, die dafür erforderlich sind, dass der Dienst über das Web gehostet wird, werden kopiert.  
  
7. Öffnen Sie IIS-Manager. Klicken Sie mit der rechten Maustaste auf das virtuelle Verzeichnis (**ExtendedProtection**), das im vorherigen Schritt erstellt wurde. Wählen Sie **Konvertieren in Anwendung**.  
  
8. Öffnen Sie das **Authentifizierungsmodul** in IIS Manager für dieses virtuelle Verzeichnis, und aktivieren Sie die **Windows-Authentifizierung**.  
  
9. Öffnen Sie **erweiterte Einstellungen** unter **Windows-Authentifizierung** für dieses virtuelle Verzeichnis, und legen Sie es auf **Erforderlich**fest.  
  
10. Sie können den Dienst testen, indem Sie die HTTPS-URL in einem Browserfenster öffnen. (Geben Sie einen vollqualifizierten Domänennamen an.) Möchten Sie von einem Remotecomputer aus auf die URL zugreifen, konfigurieren Sie die Firewall entsprechend, damit ein- und ausgehende HTTP- und HTTPS-Verbindungen hergestellt werden können.  
  
11. Öffnen Sie die Clientkonfigurationsdatei, und geben Sie einen vollqualifizierten Domänennamen für das Client- oder Endpunktadressattribut das, mit dem der `<<full_machine_name>>` ersetzt wird.  
  
12. Führen Sie den Client aus. Der Client kommuniziert mit dem Dienst, der einen sicheren Kanal einrichtet und den erweiterten Schutz verwendet.  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Security\ExtendedProtection`
