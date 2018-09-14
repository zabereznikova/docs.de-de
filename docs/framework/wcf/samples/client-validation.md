---
title: Clientvalidierung
ms.date: 03/30/2017
ms.assetid: f0c1f805-1a81-4d0d-a112-bf5e2e87a631
ms.openlocfilehash: 3f8b5ec3f8652ef50bbda3456669f2abf456472b
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2018
ms.locfileid: "45569959"
---
# <a name="client-validation"></a>Clientvalidierung
Dienste veröffentlichen häufig Metadaten, um die automatische Generierung und Konfiguration von Clientproxytypen zu aktivieren. Wenn der Dienst nicht vertrauenswürdig ist, sollten Clientanwendungen überprüfen, dass die Metadaten den Richtlinien der Clientanwendung in Bezug auf Sicherheit, Transaktionen, Typ des Servicevertrags usw. entsprechen. Das folgende Beispiel veranschaulicht das Schreiben eines Clientendpunktverhaltens, das den Dienstendpunkt überprüft, um zu gewährleisten, dass der Dienstendpunkt sicher verwendet werden kann.  
  
 Der Dienst macht vier Dienstendpunkte verfügbar. Der erste Endpunkt verwendet die WSDualHttpBinding, der zweite Endpunkt verwendet die NTLM-Authentifizierung, der dritte Endpunkt aktiviert den Transaktionsfluss, und der vierte Endpunkt verwendet die zertifikatbasierte Authentifizierung.  
  
 Der Client verwendet die <xref:System.ServiceModel.Description.MetadataResolver>-Klasse, um die Metadaten für den Dienst abzurufen. Der Client erzwingt eine Richtlinie zur Verhinderung von Duplexbindungen, NTLM-Authentifizierungen und des Transaktionsflusses unter Verwendung von Validierungsverhalten. Für jede <xref:System.ServiceModel.Description.ServiceEndpoint> Instanz importiert aus den Metadaten des Diensts, die Clientanwendung Fügt eine Instanz von der `InternetClientValidatorBehavior` Endpunktverhalten auf der <xref:System.ServiceModel.Description.ServiceEndpoint> vor dem Versuch, einen Windows Communication Foundation (WCF)-Client verwenden, um das Herstellen einer Verbindung mit der Endpunkt. Die `Validate`-Methode des Verhaltens wird ausgeführt, bevor andere Operationen für den Dienst aufgerufen werden, und sie erzwingt die Clientrichtlinie durch Auslösen der `InvalidOperationExceptions`.  
  
### <a name="to-build-the-sample"></a>So erstellen Sie das Beispiel  
  
1.  Um die Projektmappe zu erstellen, folgen Sie den Anweisungen im [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
### <a name="to-run-the-sample-on-the-same-computer"></a>So führen Sie das Beispiel auf demselben Computer aus  
  
1.  Öffnen Sie eine Visual Studio-Eingabeaufforderung mit Administratorrechten, und führen Sie die Datei Setup.bat aus dem Beispielinstallationsordner aus. Hiermit werden alle Zertifikate installiert, die zum Ausführen des Beispiels erforderlich sind.  
  
2.  Führen Sie die Dienstanwendung in "\service\bin\Debug" aus.  
  
3.  Führen Sie die Clientanwendung in "\client\bin\Debug" aus. In der Clientkonsolenanwendung wird Clientaktivität angezeigt.  
  
4.  Wenn der Client und Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung](https://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).  
  
5.  Wenn Sie mit dem Beispiel fertig sind, führen Sie die Datei Cleanup.bat aus, um die Zertifikate zu entfernen. In anderen Sicherheitsbeispielen werden die gleichen Zertifikate verwendet.  
  
### <a name="to-run-the-sample-across-computers"></a>So führen Sie das Beispiel computerübergreifend aus  
  
1.  Geben Sie auf dem Server in einer Visual Studio-Eingabeaufforderung mit Administratorrechten, `setup.bat service`. Ausführung `setup.bat` mit der `service` Argument wird ein Dienstzertifikat mit dem vollqualifizierten Domänennamen des Computers erstellt und das Dienstzertifikat in die Datei Service.cer exportiert.  
  
2.  Bearbeiten Sie auf dem Server "App.config", damit es dem neuen Zertifikatsnamen entspricht, Ändern der `findValue` -Attribut in der [ \<ServiceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) Element, den vollständig qualifizierten Domänennamen des Computers.  
  
3.  Kopieren Sie die Datei Service.cer aus dem Dienstverzeichnis in das Clientverzeichnis auf dem Clientcomputer.  
  
4.  Öffnen Sie auf dem Client eine Visual Studio-Eingabeaufforderung mit Administratorrechten, und geben `setup.bat client`. Ausführung `setup.bat` mit der `client` Argument wird ein Clientzertifikat mit dem Namen Client.com erstellt und das Clientzertifikat in der Datei Client.cer exportiert.  
  
5.  Ändern Sie in der Datei "client.cs" den Adresswert des MEX-Endpunkts und den `findValue`, um das Standardserverzertifikat so festzulegen, das es der neuen Adresse des Diensts entspricht. Ersetzen Sie dazu localhost durch den vollqualifizierten Domänennamen des Servers. Erstellen Sie sie neu.  
  
6.  Kopieren Sie die Datei Client.cer aus dem Clientverzeichnis in das Dienstverzeichnis auf dem Server.  
  
7.  Führen Sie auf dem Client ImportServiceCert.bat an einer Visual Studio-Eingabeaufforderung mit Administratorrechten aus. Dadurch wird das Dienstzertifikat aus der Datei Service.cer in den Speicher CurrentUser – TrustedPeople importiert.  
  
8.  Führen Sie auf dem Server ImportClientCert.bat an einer Visual Studio-Eingabeaufforderung mit Administratorrechten aus. Dadurch wird das Clientzertifikat aus der Datei Client.cer in den Speicher LocalMachine – TrustedPeople importiert.  
  
9. Erstellen Sie auf dem Dienstcomputer das Dienstprojekt in Visual Studio, und führen Sie service.exe aus.  
  
10. Führen Sie auf dem Clientcomputer client.exe aus.  
  
    1.  Wenn der Client und Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung](https://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).  
  
### <a name="to-clean-up-after-the-sample"></a>So stellen Sie den Zustand vor Ausführung des Beispiels wieder her  
  
-   Führen Sie Cleanup.bat im Beispielordner aus, nachdem Sie das Beispiel fertig ausgeführt haben.  
  
    > [!NOTE]
    >  Wenn dieses Beispiel computerübergreifend ausgeführt wird, entfernt dieses Skript keine Dienstzertifikate auf einem Client. Wenn Sie über WCF-Beispiele, die Zertifikate computerübergreifend verwenden, achten Sie darauf, dass Sie die Dienstzertifikate entfernen, die in den Speicher CurrentUser – installiert wurden ausgeführt haben, TrustedPeople speichern. Führen Sie dazu folgenden Befehl aus: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>. For example: certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Metadaten](../../../../docs/framework/wcf/feature-details/using-metadata.md)
