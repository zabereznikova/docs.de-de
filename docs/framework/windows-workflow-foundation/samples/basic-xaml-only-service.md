---
title: "Einfacher nur XAML-f&#228;higer Dienst | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c106feb0-0245-43b5-aefe-93ce0e4d38eb
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Einfacher nur XAML-f&#228;higer Dienst
In diesem Beispiel wird veranschaulicht, wie ein nur XAML\-fähiger Dienst erstellt wird.Das Szenario ist ein Diagnosedienst für Probleme bei Fahrzeugen.Der Dienst wird als Workflow implementiert, der dem Client eine Reihe von Fragen stellt, um das Problem zu diagnostizieren.Es gibt zwei Arten von Problemen, die der Dienst diagnostizieren kann \(Auto startet nicht oder Klimaanlage funktioniert nicht\).Der Workflow macht mithilfe der Anforderungs\-\/Antwortvorlage aus dem Designer drei einfache Dienstvorgänge verfügbar.Der Dienst wird in IIS gehostet, indem ein virtuelles Verzeichnis in IIS erstellt und die Dateien service1.xamlx und Web.config in das virtuelle Verzeichnis kopiert werden. Es ist kein kompilierter Code erforderlich.Die benötigten Dateien werden von diesem Beispiel automatisch in das erstellte virtuelle Verzeichnis kopiert, wenn Sie die Setupanweisungen für das WCF\- und WF\-Beispiel [Einmaliges Setupverfahren für Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) bei der Erstellung in Visual Studio 2010 befolgen.  
  
#### So verwenden Sie dieses Beispiel  
  
1.  Laden Sie die Projektmappe in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], und erstellen Sie das Projekt.  
  
2.  Führen Sie die unter "\[Projektmappenbasisverzeichnis\] \\Client\\bin\\debug" generierte Clientanwendung aus.  
  
3.  Die Anwendung druckt Optionen aus und aktiviert eine Option.Die Anwendung stellt dann einige Fragen; beantworten Sie diese \(mithilfe der J\/N\-Tasten\) mit Ja oder Nein.Wenn der Dienst mit der Diagnose der Probleme fertig ist, druckt die Anwendung eine Diagnose aus.  
  
4.  Die Anwendung wechselt zu den Optionen zurück.Sie können ein anderes Problem diagnostizieren oder die Anwendung beenden.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\XAMLService`  
  
## Siehe auch