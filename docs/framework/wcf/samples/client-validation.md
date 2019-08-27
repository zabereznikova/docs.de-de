---
title: Clientvalidierung
ms.date: 03/30/2017
ms.assetid: f0c1f805-1a81-4d0d-a112-bf5e2e87a631
ms.openlocfilehash: 641d5e84c09575574ff6b06888d156c4b4aa0a38
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "70040112"
---
# <a name="client-validation"></a>Clientvalidierung
Dienste veröffentlichen häufig Metadaten, um die automatische Generierung und Konfiguration von Clientproxytypen zu aktivieren. Wenn der Dienst nicht vertrauenswürdig ist, sollten Clientanwendungen überprüfen, dass die Metadaten den Richtlinien der Clientanwendung in Bezug auf Sicherheit, Transaktionen, Typ des Servicevertrags usw. entsprechen. Das folgende Beispiel veranschaulicht das Schreiben eines Clientendpunktverhaltens, das den Dienstendpunkt überprüft, um zu gewährleisten, dass der Dienstendpunkt sicher verwendet werden kann.  
  
 Der Dienst macht vier Dienstendpunkte verfügbar. Der erste Endpunkt verwendet die WSDualHttpBinding, der zweite Endpunkt verwendet die NTLM-Authentifizierung, der dritte Endpunkt aktiviert den Transaktionsfluss, und der vierte Endpunkt verwendet die zertifikatbasierte Authentifizierung.  
  
 Der Client verwendet die <xref:System.ServiceModel.Description.MetadataResolver>-Klasse, um die Metadaten für den Dienst abzurufen. Der Client erzwingt eine Richtlinie zur Verhinderung von Duplexbindungen, NTLM-Authentifizierungen und des Transaktionsflusses unter Verwendung von Validierungsverhalten. Für jede <xref:System.ServiceModel.Description.ServiceEndpoint> Instanz, die aus den Metadaten des dienstanders importiert wurde, fügt die Client `InternetClientValidatorBehavior` Anwendung der <xref:System.ServiceModel.Description.ServiceEndpoint> eine Instanz des Endpunkt Verhaltens hinzu, bevor versucht wird, einen Windows Communication Foundation (WCF)-Client zum Herstellen einer Verbindung mit zu verwenden. der Endpunkt. Die `Validate`-Methode des Verhaltens wird ausgeführt, bevor andere Operationen für den Dienst aufgerufen werden, und sie erzwingt die Clientrichtlinie durch Auslösen der `InvalidOperationExceptions`.  
  
### <a name="to-build-the-sample"></a>So erstellen Sie das Beispiel  
  
1. Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md), um die Lösung zu erstellen.  
  
### <a name="to-run-the-sample-on-the-same-computer"></a>So führen Sie das Beispiel auf demselben Computer aus  
  
1. Öffnen Sie eine Developer-Eingabeaufforderung für Visual Studio mit Administratorrechten, und führen Sie Setup. bat aus dem Beispiel Installationsordner aus. Hiermit werden alle Zertifikate installiert, die zum Ausführen des Beispiels erforderlich sind.  
  
2. Führen Sie die Dienstanwendung in "\service\bin\Debug" aus.  
  
3. Führen Sie die Clientanwendung in "\client\bin\Debug" aus. In der Clientkonsolenanwendung wird Clientaktivität angezeigt.  
  
4. Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.  
  
5. Wenn Sie mit dem Beispiel fertig sind, führen Sie die Datei Cleanup.bat aus, um die Zertifikate zu entfernen. In anderen Sicherheitsbeispielen werden die gleichen Zertifikate verwendet.  
  
### <a name="to-run-the-sample-across-computers"></a>So führen Sie das Beispiel computerübergreifend aus  
  
1. Geben `setup.bat service`Sie auf dem-Server in einem Developer-Eingabeaufforderung für Visual Studio mit Administratorrechten ausführen ein. Wenn `setup.bat` Sie mit `service` dem-Argument ausführen, wird ein Dienst Zertifikat mit dem voll qualifizierten Domänen Namen des Computers erstellt und in die Datei Service. CER exportiert.  
  
2. Bearbeiten Sie auf dem Server "App.config", damit es dem neuen Zertifikatsnamen entspricht, Das heißt, ändern Sie `findValue` das-Attribut [ \<im serviceCertificate->](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) -Element in den voll qualifizierten Domänen Namen des Computers.  
  
3. Kopieren Sie die Datei Service.cer aus dem Dienstverzeichnis in das Clientverzeichnis auf dem Clientcomputer.  
  
4. Öffnen Sie auf dem Client eine Developer-Eingabeaufforderung für Visual Studio mit Administratorrechten, und geben `setup.bat client`Sie ein. Wenn `setup.bat` Sie mit `client` dem-Argument ausführen, wird ein Client Zertifikat mit dem Namen Client.com erstellt und das Client Zertifikat in eine Datei mit dem Namen Client. CER exportiert.  
  
5. Ändern Sie in der Datei "client.cs" den Adresswert des MEX-Endpunkts und den `findValue`, um das Standardserverzertifikat so festzulegen, das es der neuen Adresse des Diensts entspricht. Ersetzen Sie dazu localhost durch den vollqualifizierten Domänennamen des Servers. Erstellen Sie sie neu.  
  
6. Kopieren Sie die Datei Client.cer aus dem Clientverzeichnis in das Dienstverzeichnis auf dem Server.  
  
7. Führen Sie auf dem Client ImportServiceCert. bat in einem Developer-Eingabeaufforderung für Visual Studio aus, das mit Administratorrechten geöffnet wurde. Dadurch wird das Dienstzertifikat aus der Datei Service.cer in den Speicher CurrentUser – TrustedPeople importiert.  
  
8. Führen Sie ImportClientCert. bat auf dem-Server in einem Developer-Eingabeaufforderung für Visual Studio aus, das mit Administratorrechten geöffnet wurde. Dadurch wird das Clientzertifikat aus der Datei Client.cer in den Speicher LocalMachine – TrustedPeople importiert.  
  
9. Erstellen Sie auf dem Dienstcomputer das Dienstprojekt in Visual Studio, und führen Sie service.exe aus.  
  
10. Führen Sie auf dem Clientcomputer client.exe aus.  
  
    1. Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.  
  
### <a name="to-clean-up-after-the-sample"></a>So stellen Sie den Zustand vor Ausführung des Beispiels wieder her  
  
- Führen Sie Cleanup.bat im Beispielordner aus, nachdem Sie das Beispiel fertig ausgeführt haben.  
  
    > [!NOTE]
    > Wenn dieses Beispiel computerübergreifend ausgeführt wird, entfernt dieses Skript keine Dienstzertifikate auf einem Client. Wenn Sie WCF-Beispiele ausgeführt haben, die Zertifikate Computer übergreifend verwenden, stellen Sie sicher, dass Sie die Dienst Zertifikate löschen, die im Speicher CurrentUser-treudpeople installiert wurden. Führen Sie dazu folgenden Befehl aus: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>. For example: certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`  
  
## <a name="see-also"></a>Siehe auch

- [Verwenden von Metadaten](../../../../docs/framework/wcf/feature-details/using-metadata.md)
