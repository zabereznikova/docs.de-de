---
title: "Erstellen der Windows Communication Foundation-Beispiele | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2899e7a5-9cb2-4e8d-b8d2-f31391549198
caps.latest.revision: 33
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 33
---
# Erstellen der Windows Communication Foundation-Beispiele
Die [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Beispiele können mit Visual Studio 2010 oder mit dem Befehl **msbuild** in der Befehlszeile erstellt werden.In diesem Thema werden beide Vorgehensweisen beschrieben.  
  
> [!NOTE]
>  Vor dem Erstellen oder Ausführen eines der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Beispiele müssen Sie sicherstellen, dass Sie die [Einmaliges Setupverfahren für Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) ausgeführt haben.  
  
### So erstellen Sie das Beispiel mithilfe einer Eingabeaufforderung  
  
1.  Öffnen Sie die [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]\-Eingabeaufforderung mit Administratorrechten, und navigieren Sie zum sprachspezifischen Unterverzeichnis unterhalb des Verzeichnisses, in dem Sie das Beispiel installiert haben.  
  
2.  Geben Sie in der Befehlszeile `msbuild` ein.Die Clientprogrammdateien werden im Verzeichnis client\\bin erstellt, und die Dienstprogrammdateien werden im Verzeichnis service\\bin erstellt.Wenn der Dienst von Internetinformationsdienste \(IIS\) gehostet wird, werden die Dienstprogrammdateien auch in das Verzeichnis servicemodelsamples und dessen Unterverzeichnis \\bin kopiert.  
  
> [!NOTE]
>  Sie müssen die Zugriffssteuerungslisten \(Access Control List, ACL\) für %systemdrive%\\inetpub\\wwwroot festlegen, um dem Konto, unter dem das Programm ausgeführt wird, Berechtigungen zum Ändern zu erteilen.Andernfalls führen einige Postbuildereignisse zu Fehlern.Sie können aber auch die ACLs unverändert lassen und die SDK\-Eingabeaufforderung als Administrator ausführen.  
  
### So erstellen Sie das Beispiel mithilfe von Visual Studio  
  
1.  Wenn Sie [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[lserver](../../../../includes/lserver-md.md)], Windows 7 oder Windows Server 2008 R2 verwenden und [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] ausführen, müssen Sie [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] mit erweiterten Berechtigungen ausführen.Klicken Sie hierzu mit der rechten Maustaste auf das Symbol im Startmenü, und klicken Sie dann auf **Als Administrator ausführen**.  
  
2.  Klicken Sie in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] im Menü **Datei** auf **Öffnen** und dann auf **Projekt\/Projektmappe**.Wechseln Sie zu dem sprachspezifischen Unterverzeichnis in dem Verzeichnis, in dem Sie das Beispiel installiert haben, und klicken Sie auf das Symbol der SLN\-Datei, um die Projektmappe in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] zu öffnen.  
  
3.  Wählen Sie im Menü **Erstellen** die Option **Projektmappe neu erstellen** aus.Die Clientprogrammdateien werden im Verzeichnis client\\bin erstellt, und die Dienstprogrammdateien werden im Verzeichnis service\\bin erstellt.Wenn der Dienst in IIS gehostet wird, werden die Dienstprogrammdateien auch in das Verzeichnis \\servicemodelsamples und dessen Unterverzeichnis \\bin kopiert.  
  
> [!NOTE]
>  Sie müssen die Zugriffssteuerungslisten \(Access Control List, ACL\) für %systemdrive%\\inetpub\\wwwroot festlegen, um dem Konto, unter dem das Programm ausgeführt wird, Berechtigungen zum Ändern zu erteilen.Andernfalls führen einige Postbuildereignisse zu Fehlern.Sie können die ACLs aber auch unverändert lassen und die SDK\-Eingabeaufforderung oder Visual Studio als Administrator ausführen.Für einige Visual Studio\-Aktionen \(wie das Anfügen eines Debuggers an den ASP.NET\-Arbeitsprozess\) sind ebenfalls Administratorrechte erforderlich.  
  
## Setupbatchdateien und Skripts  
 Die Batchdateien und Skripts Setup.exe und Cleanup.exe müssen an einer Visual Studio\-Eingabeaufforderung ausgeführt werden.Einige Setup\- und Cleanup\-Dateien führen Aufgaben aus, für die Administratorrechte erforderlich sind. Sie müssen daher mit entsprechenden Rechten gestartet werden.  
  
## Wichtige Sicherheitsinformationen über Metadatenendpunkte  
 Um zu verhindern, dass potenziell vertrauliche Dienstmetadaten versehentlich offengelegt werden, wird in der Standardkonfiguration für [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Dienste das Veröffentlichen von Metadaten deaktiviert.Dieses Verhalten ist in der Standardeinstellung sicher, bedeutet aber auch, dass der zum Aufrufen des Diensts erforderliche Clientcode nicht mithilfe eines Tools zum Importieren von Metadaten \(wie Svcutil.exe\) generiert werden kann. Dies ist nur dann möglich, wenn das Verhalten des Diensts zum Veröffentlichen von Metadaten in der Konfiguration explizit aktiviert ist.Um Ihnen das Experimentieren mit den Beispielen zu vereinfachen, wird in fast allen Beispielen ein ungesicherter Endpunkt zum Veröffentlichen von Metadaten verfügbar gemacht.Solche Endpunkte können für anonyme, nicht authentifizierte Benutzer möglicherweise verfügbar sein. Daher muss beim Bereitstellen solcher Endpunkte sorgfältig darauf geachtet werden, dass das Öffentlichmachen von Metadaten eines Diensts sachgerecht erfolgt.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zum Veröffentlichen von Dienstmetadaten finden Sie im Beispiel [Metadatenveröffentlichungsverhalten](../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md).Ein Beispiel zum Absichern eines Metadatenendpunkts finden Sie im Beispiel unter [Benutzerdefinierter sicherer Metadatenendpunkt](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md).  
  
## Ausnahmebehandlung  
 Im Allgemeinen enthalten diese Beispiele keine Ausnahmebehandlung, damit sich der Code nur auf das Thema des jeweiligen Beispiels konzentriert.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zum Behandeln von Ausnahmen finden Sie im Beispiel [Erwartete Ausnahmen](../../../../docs/framework/wcf/samples/expected-exceptions.md).  
  
## Neugenerieren von Clients und Konfiguration mit "Svcutil"  
 Sie können das [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) verwenden, um Clientcode und Konfiguration für die meisten Beispiele neu zu generieren.Bei einigen Beispielen ist es erforderlich, die Konfiguration manuell zu bearbeiten.Wenn Sie beispielsweise mit Svcutil.exe die Konfiguration für ein Beispiel neu generieren, in dem Clientzertifikat\-Anmeldeinformationen verwendet werden, müssen Sie die vorher konfigurierten Anmeldeinformationen manuell angeben.Einige Beispiele beeinflussen den generierten Code mithilfe bestimmter Optionen für Svcutil.exe. Diese Optionen sind dann in den jeweiligen Beispielthemen angegeben.  
  
#### So generieren Sie den Client und die Konfigurationsdateien neu  
  
1.  Öffnen Sie eine SDK\-Eingabeaufforderung, und navigieren Sie zu dem sprachspezifischen Unterverzeichnis unterhalb des Verzeichnisses, in dem Sie das Beispiel installiert haben.  
  
2.  Wenn der Dienst im Internet gehostet wird, verwenden Sie den folgenden Befehl.  
  
    ```  
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /out:generatedClient.cs  
    ```  
  
     Wenn der Dienst selbst gehostet ist, verwenden Sie den folgenden Befehl.  
  
    ```  
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost:8000/servicemodelsamples/service.svc/mex /out:generatedClient.cs  
    ```  
  
     Ersetzen Sie http:\/\/localhost:8000\/ServiceModelSamples\/service.svc\/mex durch die Adresse des mex\-Endpunkts des selbst gehosteten Diensts.  
  
     Verwenden Sie zum Generieren des Clients in Visual Basic den folgenden Befehl.  
  
    ```  
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /l:vb /out:generatedClient.vb  
  
    ```  
  
     Wenn der Dienst selbst gehostet ist, verwenden Sie den folgenden Befehl.  
  
    ```  
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost:8000/servicemodelsamples/service.svc/mex /l:vb /out:generatedClient.vb  
    ```  
  
    > [!NOTE]
    >  Wenn Sie die Generierung der Clientkonfiguration überspringen möchten, fügen Sie die Option **\/noConfig** hinzu.  
  
## Siehe auch  
 [Durchführen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md)   
 [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)