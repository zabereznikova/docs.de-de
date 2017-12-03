---
title: Erstellen der Windows Communication Foundation-Beispiele
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2899e7a5-9cb2-4e8d-b8d2-f31391549198
caps.latest.revision: "33"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 26a47e6ea0d93d81275d7b3b87c88d0d3ab595df
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="building-the-windows-communication-foundation-samples"></a>Erstellen der Windows Communication Foundation-Beispiele
Die [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Beispiele erstellt werden können, mithilfe von Visual Studio 2010 oder mit der **Msbuild** Befehl über die Befehlszeile. In diesem Thema werden beide Vorgehensweisen beschrieben.  
  
> [!NOTE]
>  Vor dem Erstellen oder Ausführen eines der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Beispiele, stellen Sie sicher, die von Ihnen ausgeführte der [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
### <a name="to-build-the-sample-using-a-command-prompt"></a>So erstellen Sie das Beispiel mithilfe einer Eingabeaufforderung  
  
1.  Öffnen Sie die [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]-Eingabeaufforderung mit Administratorrechten, und navigieren Sie zum sprachspezifischen Unterverzeichnis unterhalb des Verzeichnisses, in dem Sie das Beispiel installiert haben.  
  
2.  Typ `msbuild` in der Befehlszeile. Die Clientprogrammdateien werden im Verzeichnis client\bin erstellt, und die Dienstprogrammdateien werden im Verzeichnis service\bin erstellt. Wenn der Dienst von Internetinformationsdienste (IIS) gehostet wird, werden die Dienstprogrammdateien auch in das Verzeichnis servicemodelsamples und dessen Unterverzeichnis \bin kopiert.  
  
> [!NOTE]
>  Sie müssen die Zugriffssteuerungslisten (Access Control List, ACL) für %systemdrive%\inetpub\wwwroot festlegen, um dem Konto, unter dem das Programm ausgeführt wird, Berechtigungen zum Ändern zu erteilen. Andernfalls führen einige Postbuildereignisse zu Fehlern. Sie können aber auch die ACLs unverändert lassen und die SDK-Eingabeaufforderung als Administrator ausführen.  
  
### <a name="to-build-the-sample-using-visual-studio"></a>So erstellen Sie das Beispiel mithilfe von Visual Studio  
  
1.  Wenn Sie [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[lserver](../../../../includes/lserver-md.md)], Windows 7 oder Windows Server 2008 R2 verwenden und [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] ausführen, müssen Sie [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] mit erweiterten Berechtigungen ausführen. Klicken Sie hierzu mit der rechten Maustaste auf das Startmenü auf des Symbol, und klicken Sie dann auf **als Administrator ausführen**.  
  
2.  Aus der **Datei** im Menü [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], klicken Sie auf **öffnen**, klicken Sie dann auf **Projekt/Projektmappe**. Wechseln Sie zu dem sprachspezifischen Unterverzeichnis in dem Verzeichnis, in dem Sie das Beispiel installiert haben, und klicken Sie auf das Symbol der SLN-Datei, um die Projektmappe in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] zu öffnen.  
  
3.  In der **erstellen** klicken Sie im Menü **Projektmappe neu erstellen**. Die Clientprogrammdateien werden im Verzeichnis client\bin erstellt, und die Dienstprogrammdateien werden im Verzeichnis service\bin erstellt. Wenn der Dienst in IIS gehostet wird, werden die Dienstprogrammdateien auch in das Verzeichnis \servicemodelsamples und dessen Unterverzeichnis \bin kopiert.  
  
> [!NOTE]
>  Sie müssen die Zugriffssteuerungslisten (Access Control List, ACL) für %systemdrive%\inetpub\wwwroot festlegen, um dem Konto, unter dem das Programm ausgeführt wird, Berechtigungen zum Ändern zu erteilen. Andernfalls führen einige Postbuildereignisse zu Fehlern. Sie können die ACLs aber auch unverändert lassen und die SDK-Eingabeaufforderung oder Visual Studio als Administrator ausführen. Für einige Visual Studio-Aktionen (wie das Anfügen eines Debuggers an den ASP.NET-Arbeitsprozess) sind ebenfalls Administratorrechte erforderlich.  
  
## <a name="setup-batch-files-and-scripts"></a>Setupbatchdateien und Skripts  
 Die Batchdateien und Skripts Setup.exe und Cleanup.exe müssen an einer Visual Studio-Eingabeaufforderung ausgeführt werden. Einige Setup- und Cleanup-Dateien führen Aufgaben aus, für die Administratorrechte erforderlich sind. Sie müssen daher mit entsprechenden Rechten gestartet werden.  
  
## <a name="important-security-information-about-metadata-endpoints"></a>Wichtige Sicherheitsinformationen über Metadatenendpunkte  
 Um ein unbeabsichtigtes Veröffentlichen von möglicherweise vertraulichen Dienstmetadaten zu vermeiden, wird mit der Standardkonfiguration für [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Dienste die Metadatenveröffentlichung deaktiviert. Dieses Verhalten ist in der Standardeinstellung sicher, bedeutet aber auch, dass man den zum Aufrufen des Diensts erforderlichen Clientcode nicht mithilfe eines Tools zum Importieren von Metadaten (wie Svcutil.exe) generieren kann. Dies ist nur dann möglich, wenn das Verhalten des Diensts zum Veröffentlichen von Metadaten in der Konfiguration explizit aktiviert ist. Um Ihnen das Experimentieren mit den Beispielen zu vereinfachen, wird in fast allen Beispielen ein ungesicherter Endpunkt zum Veröffentlichen von Metadaten verfügbar gemacht. Solche Endpunkte können für anonyme, nicht authentifizierte Benutzer möglicherweise verfügbar sein. Daher muss beim Bereitstellen solcher Endpunkte sorgfältig darauf geachtet werden, dass das Öffentlichmachen von Metadaten eines Diensts sachgerecht erfolgt. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Veröffentlichen von Dienstmetadaten, finden Sie unter der [Metadatenveröffentlichungsverhalten](../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md) Beispiel. Finden Sie unter der [benutzerdefinierter sicherer Metadatenendpunkt](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) Sample ist ein Beispiel ein metadatenendpunkts zu sichern.  
  
## <a name="exception-handling"></a>Ausnahmebehandlung  
 Im Allgemeinen enthalten diese Beispiele keine Ausnahmebehandlung, damit der Code auf das Thema des jeweiligen Beispiels beschränkt werden kann. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Ausnahmebehandlung, finden Sie unter der [Ausnahmen erwartet](../../../../docs/framework/wcf/samples/expected-exceptions.md) Beispiel.  
  
## <a name="regenerating-clients-and-configuration-with-svcutil"></a>Neugenerieren von Clients und Konfiguration mit "Svcutil"  
 Sie können die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) zum Generieren von Clientcode und-Konfiguration für die meisten der Beispiele. Bei einigen Beispielen ist es erforderlich, die Konfiguration manuell zu bearbeiten. Wenn Sie beispielsweise mit Svcutil.exe die Konfiguration für ein Beispiel neu generieren, in dem Clientzertifikat-Anmeldeinformationen verwendet werden, müssen Sie die vorher konfigurierten Anmeldeinformationen manuell angeben. Einige Beispiele beeinflussen den generierten Code mithilfe bestimmter Optionen für Svcutil.exe. Diese Optionen sind dann in den jeweiligen Beispielthemen angegeben.  
  
#### <a name="to-regenerate-the-client-and-configuration-files"></a>So generieren Sie den Client und die Konfigurationsdateien neu  
  
1.  Öffnen Sie eine SDK-Eingabeaufforderung, und navigieren Sie zu dem sprachspezifischen Unterverzeichnis unterhalb des Verzeichnisses, in dem Sie das Beispiel installiert haben.  
  
2.  Wenn der Dienst im Internet gehostet wird, verwenden Sie den folgenden Befehl.  
  
    ```  
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /out:generatedClient.cs  
    ```  
  
     Wenn der Dienst selbst gehostet ist, verwenden Sie den folgenden Befehl.  
  
    ```  
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost:8000/servicemodelsamples/service.svc/mex /out:generatedClient.cs  
    ```  
  
     Ersetzen Sie http://localhost:8000/ServiceModelSamples/service.svc/mex durch die Adresse des mex-Endpunkts des selbst gehosteten Diensts.  
  
     Verwenden Sie zum Generieren des Clients in Visual Basic den folgenden Befehl.  
  
    ```  
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /l:vb /out:generatedClient.vb  
    ```  
  
     Wenn der Dienst selbst gehostet ist, verwenden Sie den folgenden Befehl.  
  
    ```  
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost:8000/servicemodelsamples/service.svc/mex /l:vb /out:generatedClient.vb  
    ```  
  
    > [!NOTE]
    >  Hinzufügen der Generierung der Clientkonfiguration Überspringen der **/noconfig** Option.  
  
## <a name="see-also"></a>Siehe auch  
 [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md)  
 [ServiceModel Metadata Utility-Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
