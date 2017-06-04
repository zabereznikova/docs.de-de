---
title: "Clientvalidierung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f0c1f805-1a81-4d0d-a112-bf5e2e87a631
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Clientvalidierung
Dienste veröffentlichen häufig Metadaten, um die automatische Generierung und Konfiguration von Clientproxytypen zu aktivieren.  Wenn der Dienst nicht vertrauenswürdig ist, sollten Clientanwendungen überprüfen, dass die Metadaten den Richtlinien der Clientanwendung in Bezug auf Sicherheit, Transaktionen, Typ des Servicevertrags usw. entsprechen.  Das folgende Beispiel veranschaulicht das Schreiben eines Clientendpunktverhaltens, das den Dienstendpunkt überprüft, um zu gewährleisten, dass der Dienstendpunkt sicher verwendet werden kann.  
  
 Der Dienst macht vier Dienstendpunkte verfügbar.  Der erste Endpunkt verwendet die WSDualHttpBinding, der zweite Endpunkt verwendet die NTLM\-Authentifizierung, der dritte Endpunkt aktiviert den Transaktionsfluss, und der vierte Endpunkt verwendet die zertifikatbasierte Authentifizierung.  
  
 Der Client verwendet die <xref:System.ServiceModel.Description.MetadataResolver>\-Klasse, um die Metadaten für den Dienst abzurufen.  Der Client erzwingt eine Richtlinie zur Verhinderung von Duplexbindungen, NTLM\-Authentifizierungen und des Transaktionsflusses unter Verwendung von Validierungsverhalten.  Für jede <xref:System.ServiceModel.Description.ServiceEndpoint>\-Instanz, die aus den Metadaten des Diensts importiert wurde, fügt die Clientanwendung eine Instanz des `InternetClientValidatorBehavior`\-Endpunktverhaltens zu dem <xref:System.ServiceModel.Description.ServiceEndpoint> hinzu, bevor versucht wird, einen [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Client für die Verbindung mit dem Endpunkt zu verwenden.  Die `Validate`\-Methode des Verhaltens wird ausgeführt, bevor andere Operationen für den Dienst aufgerufen werden, und sie erzwingt die Clientrichtlinie durch Auslösen der `InvalidOperationExceptions`.  
  
### So erstellen Sie das Beispiel  
  
1.  Befolgen Sie die Anweisungen unter [Erstellen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md), um die Projektmappe zu erstellen.  
  
### So führen Sie das Beispiel auf demselben Computer aus  
  
1.  Öffnen Sie eine Visual Studio\-Eingabeaufforderung mit Administratorrechten, und führen Sie die Datei Setup.bat aus dem Beispielinstallationsordner aus.  Hiermit werden alle Zertifikate installiert, die zum Ausführen des Beispiels erforderlich sind.  
  
2.  Führen Sie die Dienstanwendung in "\\service\\bin\\Debug" aus.  
  
3.  Führen Sie die Clientanwendung in "\\client\\bin\\Debug" aus.  In der Clientkonsolenanwendung wird Clientaktivität angezeigt.  
  
4.  Wenn der Client und der Dienst nicht miteinander kommunizieren können, finden Sie weitere Informationen unter [Troubleshooting Tips](http://msdn.microsoft.com/de-de/8787c877-5e96-42da-8214-fa737a38f10b).  
  
5.  Wenn Sie mit dem Beispiel fertig sind, führen Sie die Datei Cleanup.bat aus, um die Zertifikate zu entfernen.  In anderen Sicherheitsbeispielen werden die gleichen Zertifikate verwendet.  
  
### So führen Sie das Beispiel computerübergreifend aus  
  
1.  Öffnen Sie auf dem Server eine Visual Studio\-Eingabeaufforderung mit Administratorrechten, und geben Sie `setup.bat service` ein.  Durch Ausführen von `setup.bat` `` mit dem Argument `service` wird ein Dienstzertifikat mit dem vollqualifizierten Domänennamen des Computers erstellt und in die Datei Service.cer exportiert.  
  
2.  Bearbeiten Sie auf dem Server "App.config", damit es dem neuen Zertifikatsnamen entspricht,  Ändern Sie dazu das `findValue`\-Attribut im [\<serviceCertificate\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)\-Element so, dass es dem vollqualifizierten Domänennamen des Computers entspricht.  
  
3.  Kopieren Sie die Datei Service.cer aus dem Dienstverzeichnis in das Clientverzeichnis auf dem Clientcomputer.  
  
4.  Öffnen Sie auf dem Client eine Visual Studio\-Eingabeaufforderung mit Administratorrechten, und geben Sie `setup.bat client` ein.  Durch Ausführen von `setup.bat` `` mit dem Argument `client` wird ein Clientzertifikat mit dem Namen client.com erstellt und in die Datei Client.cer exportiert.  
  
5.  Ändern Sie in der Datei "client.cs" den Adresswert des MEX\-Endpunkts und den `findValue`, um das Standardserverzertifikat so festzulegen, das es der neuen Adresse des Diensts entspricht.  Ersetzen Sie dazu localhost durch den vollqualifizierten Domänennamen des Servers.  Erstellen Sie sie neu.  
  
6.  Kopieren Sie die Datei Client.cer aus dem Clientverzeichnis in das Dienstverzeichnis auf dem Server.  
  
7.  Führen Sie auf dem Client ImportServiceCert.bat an einer Visual Studio\-Eingabeaufforderung mit Administratorrechten aus.  Dadurch wird das Dienstzertifikat aus der Datei Service.cer in den Speicher CurrentUser – TrustedPeople importiert.  
  
8.  Führen Sie auf dem Server ImportClientCert.bat an einer Visual Studio\-Eingabeaufforderung mit Administratorrechten aus.  Dadurch wird das Clientzertifikat aus der Datei Client.cer in den Speicher LocalMachine – TrustedPeople importiert.  
  
9. Erstellen Sie auf dem Dienstcomputer das Dienstprojekt in Visual Studio, und führen Sie service.exe aus.  
  
10. Führen Sie auf dem Clientcomputer client.exe aus.  
  
    1.  Wenn der Client und der Dienst nicht miteinander kommunizieren können, finden Sie weitere Informationen unter [Troubleshooting Tips](http://msdn.microsoft.com/de-de/8787c877-5e96-42da-8214-fa737a38f10b).  
  
### So stellen Sie den Zustand vor Ausführung des Beispiels wieder her  
  
-   Führen Sie Cleanup.bat im Beispielordner aus, nachdem Sie das Beispiel fertig ausgeführt haben.  
  
    > [!NOTE]
    >  Wenn dieses Beispiel computerübergreifend ausgeführt wird, entfernt dieses Skript keine Dienstzertifikate auf einem Client.  Wenn Sie [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Beispiele ausgeführt haben, die Zertifikate computerübergreifend verwenden, müssen Sie die Dienstzertifikate entfernen, die im Speicher CurrentUser – TrustedPeople installiert wurden.  Führen Sie dazu folgenden Befehl aus: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Name des vollqualifizierten Servercomputers>. Beispielsweise: certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.  
  
## Siehe auch  
 [Verwenden von Metadaten](../../../../docs/framework/wcf/feature-details/using-metadata.md)