---
title: Clientvalidierung
ms.date: 03/30/2017
ms.assetid: f0c1f805-1a81-4d0d-a112-bf5e2e87a631
ms.openlocfilehash: dee57e039d4510673b7205fd44fa300b24ac1df5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96243312"
---
# <a name="client-validation"></a>Clientvalidierung

Dienste veröffentlichen häufig Metadaten, um die automatische Generierung und Konfiguration von Clientproxytypen zu aktivieren. Wenn der Dienst nicht vertrauenswürdig ist, sollten Clientanwendungen überprüfen, dass die Metadaten den Richtlinien der Clientanwendung in Bezug auf Sicherheit, Transaktionen, Typ des Servicevertrags usw. entsprechen. Das folgende Beispiel veranschaulicht das Schreiben eines Clientendpunktverhaltens, das den Dienstendpunkt überprüft, um zu gewährleisten, dass der Dienstendpunkt sicher verwendet werden kann.  
  
 Der Dienst macht vier Dienstendpunkte verfügbar. Der erste Endpunkt verwendet die WSDualHttpBinding, der zweite Endpunkt verwendet die NTLM-Authentifizierung, der dritte Endpunkt aktiviert den Transaktionsfluss, und der vierte Endpunkt verwendet die zertifikatbasierte Authentifizierung.  
  
 Der Client verwendet die <xref:System.ServiceModel.Description.MetadataResolver>-Klasse, um die Metadaten für den Dienst abzurufen. Der Client erzwingt eine Richtlinie zur Verhinderung von Duplexbindungen, NTLM-Authentifizierungen und des Transaktionsflusses unter Verwendung von Validierungsverhalten. Für jede <xref:System.ServiceModel.Description.ServiceEndpoint> Instanz, die aus den Metadaten des dienstanders importiert wurde, fügt die Client Anwendung der eine Instanz des `InternetClientValidatorBehavior` Endpunkt Verhaltens hinzu, <xref:System.ServiceModel.Description.ServiceEndpoint> bevor versucht wird, einen Windows Communication Foundation (WCF)-Client zum Herstellen einer Verbindung mit dem Endpunkt zu verwenden. Die `Validate`-Methode des Verhaltens wird ausgeführt, bevor andere Operationen für den Dienst aufgerufen werden, und sie erzwingt die Clientrichtlinie durch Auslösen der `InvalidOperationExceptions`.  
  
### <a name="to-build-the-sample"></a>So erstellen Sie das Beispiel  
  
1. Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](building-the-samples.md), um die Lösung zu erstellen.  
  
### <a name="to-run-the-sample-on-the-same-computer"></a>So führen Sie das Beispiel auf demselben Computer aus  
  
1. Öffnen Sie eine Developer-Eingabeaufforderung für Visual Studio mit Administratorrechten, und führen Sie Setup.bat aus dem Beispiel Installationsordner aus. Hiermit werden alle Zertifikate installiert, die zum Ausführen des Beispiels erforderlich sind.  
  
2. Führen Sie die Dienstanwendung in "\service\bin\Debug" aus.  
  
3. Führen Sie die Clientanwendung in "\client\bin\Debug" aus. In der Clientkonsolenanwendung wird Clientaktivität angezeigt.  
  
4. Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.  
  
5. Wenn Sie mit dem Beispiel fertig sind, führen Sie die Datei Cleanup.bat aus, um die Zertifikate zu entfernen. In anderen Sicherheitsbeispielen werden die gleichen Zertifikate verwendet.  
  
### <a name="to-run-the-sample-across-computers"></a>So führen Sie das Beispiel computerübergreifend aus  
  
1. Geben Sie auf dem-Server in einem Developer-Eingabeaufforderung für Visual Studio mit Administratorrechten ausführen ein `setup.bat service` . Wenn `setup.bat` Sie mit dem- `service` Argument ausführen, wird ein Dienst Zertifikat mit dem voll qualifizierten Domänen Namen des Computers erstellt und in die Datei Service. CER exportiert.  
  
2. Bearbeiten Sie auf dem Server "App.config", damit es dem neuen Zertifikatsnamen entspricht, Das heißt, ändern Sie das- `findValue` Attribut im- [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) Element in den voll qualifizierten Domänen Namen des Computers.  
  
3. Kopieren Sie die Datei Service.cer aus dem Dienstverzeichnis in das Clientverzeichnis auf dem Clientcomputer.  
  
4. Öffnen Sie auf dem Client eine Developer-Eingabeaufforderung für Visual Studio mit Administratorrechten, und geben Sie ein `setup.bat client` . Wenn `setup.bat` Sie mit dem- `client` Argument ausführen, wird ein Client Zertifikat mit dem Namen Client.com erstellt und das Client Zertifikat in eine Datei mit dem Namen Client. CER exportiert.  
  
5. Ändern Sie in der Datei "client.cs" den Adresswert des MEX-Endpunkts und den `findValue`, um das Standardserverzertifikat so festzulegen, das es der neuen Adresse des Diensts entspricht. Ersetzen Sie dazu localhost durch den vollqualifizierten Domänennamen des Servers. Neuerstellung.  
  
6. Kopieren Sie die Datei Client.cer aus dem Clientverzeichnis in das Dienstverzeichnis auf dem Server.  
  
7. Führen Sie auf dem Client ImportServiceCert.bat in einem Developer-Eingabeaufforderung für Visual Studio aus, das mit Administratorrechten geöffnet wurde. Dadurch wird das Dienstzertifikat aus der Datei Service.cer in den Speicher CurrentUser – TrustedPeople importiert.  
  
8. Führen Sie auf dem-Server ImportClientCert.bat in einem Developer-Eingabeaufforderung für Visual Studio aus, das mit Administratorrechten geöffnet wurde. Dadurch wird das Clientzertifikat aus der Datei Client.cer in den Speicher LocalMachine – TrustedPeople importiert.  
  
9. Erstellen Sie auf dem Dienstcomputer das Dienstprojekt in Visual Studio, und führen Sie service.exe aus.  
  
10. Führen Sie auf dem Clientcomputer client.exe aus.  
  
    1. Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.  
  
### <a name="to-clean-up-after-the-sample"></a>So stellen Sie den Zustand vor Ausführung des Beispiels wieder her  
  
- Führen Sie Cleanup.bat im Beispielordner aus, nachdem Sie das Beispiel fertig ausgeführt haben.  
  
    > [!NOTE]
    > Wenn dieses Beispiel computerübergreifend ausgeführt wird, entfernt dieses Skript keine Dienstzertifikate auf einem Client. Wenn Sie WCF-Beispiele ausgeführt haben, die Zertifikate Computer übergreifend verwenden, stellen Sie sicher, dass Sie die Dienst Zertifikate löschen, die im Speicher CurrentUser-treudpeople installiert wurden. Führen Sie dazu folgenden Befehl aus: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>. For example: certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`  
  
## <a name="see-also"></a>Weitere Informationen

- [Verwenden von Metadaten](../feature-details/using-metadata.md)
