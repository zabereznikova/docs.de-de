---
title: Konfigurationsbasierte Aktivierung
ms.date: 03/30/2017
ms.assetid: 21bb762e-c43e-4b0c-887b-5e434d665838
ms.openlocfilehash: 3ac4edd2a51e4ed8a5c0b7e73d7d1afa31334c33
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="configuration-based-activation"></a>Konfigurationsbasierte Aktivierung
Dieses Beispiel veranschaulicht die Windows Communication Foundation (WCF)-Dienste zu aktivieren, ohne eine SVC-Datei.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\ConfigBasedActivation`  
  
## <a name="sample-details"></a>Beispieldetails  
 In diesem Beispiel wird der Client den WCF-Testclient und der Dienst in IIS gehostet wird.  
  
> [!NOTE]
>  Die Setup- und Erstellungsanweisungen für dieses Beispiel befinden sich am Ende dieses Abschnitts.  
  
### <a name="activation-of-services-without-requiring-a-svc-file"></a>Aktivierung von Diensten ohne SVC-Datei  
 In [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] war eine SVC-Datei zum Aktivieren eines Diensts erforderlich. Das führte zu zusätzlichem Verwaltungsmehraufwand, da neben der Anwendung eine weitere Datei bereitgestellt und verwaltet werden musste. Seit der Veröffentlichung von [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] können die Aktivierungskomponenten mit der Anwendungskonfigurationsdatei konfiguriert werden.  
  
 In [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)] wird ein neues Konfigurationselement (<xref:System.ServiceModel.Configuration.ServiceActivationElement>), in den <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection> der Anwendungskonfigurationsdatei eingeführt. Die <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>-Auflistung akzeptiert eine Auflistung von Diensten für die Aktivierung, wie im folgenden Codebeispiel gezeigt.  
  
```xml  
<serviceActivations>  
   <add relativeAddress="Calculator.svc" service="Microsoft.ServiceModel.Samples.CalculatorService" />  
  
<serviceActivations>  
```  
  
 Die Konfiguration ähnelt offensichtlich der Konfiguration von SVC-Dateien. Ein zusätzliches Attribut, das eingeführt wird, ist das `relativeAddress`-Attribut, das die Adresse des Diensts bereitstellt. Die relative Adresse ist auch der virtuelle Pfad für den Dienst. Der Host ruft die Datei Web.config aus dem `virtualPath`-Speicherort ab, wenn sie vorhanden ist; andernfalls führt der Host im übergeordneten Ordner eine rekursive Suche durch.  
  
> [!NOTE]
>  Dieses Beispiel muss in IIS gehostet werden, um zu funktionieren.  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie die Datei Service.csproj mit [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
3.  Testen Sie den Dienst, indem Sie WCFTestClient.exe ausführen.  
  
4.  Navigieren Sie im [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] zum Ordner %SystemDrive%\Programme\Microsoft Visual Studio 10.0\Common7\IDE.  
  
5.  Führen Sie WcfTestClient.exe aus.  
  
6.  Legen Sie die MEX-Adresse des Diensts fest.  
  
7.  Drücken Sie STRG+UMSCHALT+A, um die Dienstadresse festzulegen.  
  
8.  Legen Sie die Adresse http://localhost/ServiceModelSamples/Calculator.svc.  
  
9. Führen Sie den `Add`-Vorgang aus. Legen Sie den Wert für den `n1`-Parameter auf 10 und den Wert für den `n2`-Parameter auf 15 fest.  
  
10. Drücken Sie **Aufrufen**.  
  
     Das erwartete Ergebnis lautet 25.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Achten Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3.  Nachdem die Projektmappe erstellt wurde, führen Sie Setup.bat aus, um die ServiceModelSamples-Anwendung in IIS einzurichten. Das Verzeichnis ServiceModelSamples sollte jetzt als IIS-Anwendung angezeigt werden.  
  
4.  Um das Beispiel in einer Einzelcomputer- oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## <a name="see-also"></a>Siehe auch  
 [AppFabric-Hosting und Persistenzbeispiele](http://go.microsoft.com/fwlink/?LinkId=193961)
