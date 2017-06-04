---
title: "Verwenden von Leistungsindikatoren | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 00a787af-1876-473c-a48d-f52b51e28a3f
caps.latest.revision: 31
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 31
---
# Verwenden von Leistungsindikatoren
In diesem Beispiel wird veranschaulicht, wie auf [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Leistungsindikatoren zugegriffen wird und wie benutzerdefinierte Leistungsindikatoren erstellt werden.Dieses Beispiel basiert auf dem [Erste Schritte](../../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 In diesem Beispiel ruft der Client die vier Methoden des `ICalculator`\-Diensts auf.Der Client setzt dies fort, bis er vom Benutzer unterbrochen wird.Der Dienst bleibt unverändert.  
  
 Die Leistungsindikatoren sind im Diagnoseabschnitt der Datei "Web.config" für diesen Dienst aktiviert, wie in der folgenden Beispielkonfiguration dargestellt.  
  
```  
<configuration>  
  <system.serviceModel>  
    <diagnostics performanceCounters="All" />   
  </system.serviceModel>  
</configuration>  
```  
  
 Diese Aufgabe kann auch mit [Configuration Editor\-Tool \(SvcConfigEditor.exe\)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) ausgeführt werden.  
  
 Wenn Leistungsindikatoren aktiviert sind, wird die ganze Suite von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Leistungsindikatoren für den Dienst aktiviert..NET Framework behält Leistungsdaten automatisch auf drei Ebenen bei: `ServiceModelService`, `ServiceModelEndpoint` und `ServiceModelOperation`.Jede dieser Ebenen verfügt über Leistungsindikatoren wie "Calls", "Calls per Second" und "Security Calls Not Authorized".  
  
### So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Stellen Sie sicher, dass Sie die [Einmaliges Setupverfahren für Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) ausgeführt haben.  
  
2.  Folgen Sie zum Erstellen der C\#\- bzw. Visual Basic .NET\-Version der Projektmappe den Anweisungen unter [Erstellen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Um das Beispiel in einer Konfiguration mit einem Computer oder computerübergreifend auszuführen, folgen Sie den Anweisungen unter [Durchführen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
### So zeigen Sie Leistungsdaten an  
  
1.  Starten Sie das Leistungsmonitor\-Tool, indem Sie auf **Start**, **Ausführen…** klicken, `perfmon` eingeben und dann auf **OK** klicken. Sie können auch in der Systemsteuerung **Verwaltung** auswählen und auf **Leistung** doppelklicken.  
  
    > [!NOTE]
    >  Sie können erst Indikatoren hinzufügen, wenn der Beispielcode ausgeführt wird.  
  
2.  Entfernen Sie die aufgeführten Leistungsindikatoren, indem Sie sie auswählen und dann die ENTF\-TASTE drücken.  
  
3.  Fügen Sie [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Indikatoren hinzu, indem Sie mit der rechten Maustaste in den Diagrammbereich klicken und **Leistungsindikatoren hinzufügen** auswählen.Wählen Sie im Dialogfeld **Leistungsindikatoren hinzufügen** im Dropdownlistenfeld **Leistungsobjekt** die Option ServiceModelOperation 3.0.0.0, ServiceModelEndpoint 3.0.0.0 oder ServiceModelService 3.0.0.0 aus.Wählen Sie die anzuzeigenden Indikatoren in der Liste aus.  
  
    > [!NOTE]
    >  Es werden keine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Leistungsindikatoren für einen Dienst angezeigt, wenn keine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienste auf dem Computer ausgeführt werden.  
  
### So aktivieren Sie Indikatoren mit dem Konfigurations\-Editor  
  
1.  Öffnen Sie eine Instanz von SvcConfigEditor.exe.  
  
2.  Klicken Sie im Menü **Datei** auf **Öffnen** und dann auf Konfigurationsdatei....  
  
3.  Navigieren Sie zum Dienstordner der Beispielanwendung, und öffnen Sie die Datei "Web.config".  
  
4.  Klicken Sie in der Konfigurationsstruktur auf **Diagnose**.  
  
5.  Schalten Sie im Fenster **Diagnose** die Option **Leistungsindikator** um, um "Alle" anzuzeigen.  
  
6.  Speichern Sie die Konfigurationsdatei, und beenden Sie den Editor.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\PerfCounters`  
  
## Siehe auch  
 [AppFabric\-Überwachungsbeispiele](http://go.microsoft.com/fwlink/?LinkId=193959)