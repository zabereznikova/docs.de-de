---
title: "Überwachen mit einer Textdatei"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56a82682-73c2-4b91-a206-4d8bb12c561b
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f1d4b3f319d86dd463dabc8b71be7c76c7fef41f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="tracking-using-a-text-file"></a>Überwachen mit einer Textdatei
In diesem Beispiel wird veranschaulicht, wie die Nachverfolgung von [!INCLUDE[wf](../../../../includes/wf-md.md)] erweitert wird, indem ein benutzerdefinierter Nachverfolgungsteilnehmer erstellt wird. Nachverfolgungsteilnehmer sind .NET Framework-Klassen, die Nachverfolgungsdatensätze von der Laufzeit empfangen, wenn sie ausgegeben werden. Sie können einen Nachverfolgungsteilnehmer erstellen, um die Nachverfolgungsereignisse zu dem Ziel zu transportieren, das für das Szenario erforderlich ist. Ein ETW-Nachverfolgungsteilnehmer (Event Tracing for Windows, Ereignisablaufverfolgung für Windows) wird z. B. als Bestandteil von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] bereitgestellt. Der Nachverfolgungsteilnehmer in diesem Beispiel schreibt die Datensätze in eine Textdatei im XML-Format.  
  
## <a name="sample-details"></a>Beispieldetails  
 Um die Nützlichkeit und die Stabilität des Nachverfolgungsteilnehmers zu optimieren, müssen einige zusätzliche Schritte ausgeführt werden, damit der Nachverfolgungsteilnehmer ordnungsgemäß mit der Laufzeit verbunden wird. In der folgenden Tabelle werden die in diesem Beispiel verwendeten Klassen beschrieben, mit denen ein Nachverfolgungsteilnehmer erstellt wird, der bewährte Methoden einhält.  
  
|Klasse|Beschreibung|  
|-----------|-----------------|  
|`TextFileTrackingExtensionElement`|Ein <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> wird verwendet, um den Konfigurationsabschnitt zu definieren, der verwendet wird, um den Textdatei-Nachverfolgungsteilnehmer zu konfigurieren. Dies ermöglicht es Benutzern, das Ziel der Protokolldatei mit standardmäßigen .NET Framework-Konfigurationsdateien anzugeben.|  
|`TextFileTrackingBehavior`|Das Verhalten in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ermöglicht es Benutzern, Erweiterungen in die Laufzeit einzufügen. Dieses Verhalten fügt dem Dienst den Nachverfolgungsteilnehmer hinzu, wenn der Dienst gestartet wird.|  
|`TextFileTrackingParticipant`|Der Nachverfolgungsteilnehmer, der zur Laufzeit Nachverfolgungsteilnehmer empfängt und sie in einer Protokolldatei als XML speichert.|  
  
## <a name="behavior-extension-elements-configuration"></a>Konfiguration von Verhaltenserweiterungselementen  
 Ein weiterer Schritt ist erforderlich, um das Verhaltenserweiterungselement zu nutzen, das zuvor mit .NET Framework-Konfigurationsdateien beschrieben wurde. Die folgende Konfiguration muss in Konfigurationsdateien eingefügt werden, in denen die Erweiterung verwendet werden soll.  
  
```xml  
<system.serviceModel>  
    <extensions>  
      <behaviorExtensions>  
        <add name="textFileTracking" type="Microsoft.Samples.TextFileTracking.TextFileTrackingExtensionElement, WFStockPriceApplication, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
      </behaviorExtensions>  
    </extensions>  
…  
  </system.serviceModel>  
```  
  
> [!NOTE]
>  Eine vollständige Beispielverwendung der Konfiguration von Verhaltenserweiterungselementen finden Sie in der Datei "Web.config" im Beispiel.  
  
## <a name="custom-tracking-records"></a>Benutzerdefinierte Überwachungsdatensätze  
 Die Datei "GetStockPrices.cs" veranschaulicht, wie benutzerdefinierte Nachverfolgungsdatensätze in <xref:System.Activities.CodeActivity> erstellt werden. Suchen Sie nach diesem Datensatz, wenn Sie das Beispiel ausführen.  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie mit [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "WFStockPriceApplication.sln".  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie STRG+F5, um die Projektmappe auszuführen.  
  
     Das Browserfenster wird geöffnet und zeigt die Verzeichnisliste für die Anwendung an.  
  
4.  Klicken Sie im Browser auf "StockPriceService.xamlx".  
  
5.  Der Browser zeigt die **StockPriceService** Seite, die die Wsdl-Adresse des lokalen Diensts enthält. Kopieren Sie diese Adresse.  
  
     Ein Beispiel für die WSDL-Adresse des lokalen Diensts ist "http://localhost:65193/StockPriceService.xamlx?wsdl".  
  
6.  Wechseln Sie im [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] zum [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]-Ordner (der Standardinstallationsordner ist "%SystemDrive%\Programme\Microsoft Visual Studio 10.0"). Suchen Sie dann den Unterordner "Common7\IDE\".  
  
7.  Doppelklicken Sie auf die Datei "WcfTestClient.exe", um den WCF-Testclient zu starten.  
  
8.  Wählen Sie in der WCF-Testclient **Dienst hinzufügen...** aus der **Datei** Menü.  
  
9. Fügen Sie die URL ein, die Sie gerade in das Textfeld kopiert haben.  
  
10. Klicken Sie auf **OK** um das Dialogfeld zu schließen.  
  
11. Testen Sie den Dienst mit dem WCF-Testclient.  
  
    1.  Doppelklicken Sie im WCF-Testclient auf **GetStockPrice()** unter der **IStockPriceService** Knoten.  
  
         Die **GetStockPrice()** -Methode wird im rechten Bereich mit einem Parameter angezeigt.  
  
    2.  Geben Sie "Contoso" als Wert für den Parameter ein.  
  
    3.  Klicken Sie auf **Aufrufen**.  
  
12. Sehen Sie sich die nachverfolgten Ereignisse in der Protokolldatei an, die sich im Anwendungsdatenverzeichnis unter "%APPDATA%\trackingRecords.log" befindet.  
  
    > [!NOTE]
    >  %Appdata% ist eine Umgebungsvariable, die zu %SystemDrive%\Users aufgelöst\\< Benutzername\>\AppData\Roaming in [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[lserver](../../../../includes/lserver-md.md)], oder Windows Server 2008.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\TextFileTracking`  
  
## <a name="see-also"></a>Siehe auch  
 [Überwachen der AppFabric-Beispiele](http://go.microsoft.com/fwlink/?LinkId=193959)
