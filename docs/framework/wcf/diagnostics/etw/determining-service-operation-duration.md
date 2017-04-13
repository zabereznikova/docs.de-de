---
title: "Ermitteln der Dienstvorgangsdauer | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e8a93a2c-2c20-48b3-8986-57e90e9aa908
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Ermitteln der Dienstvorgangsdauer
Wenn die analytische Ablaufverfolgung in einer [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]\-Anwendung aktiviert wird, kann die Dauer der Ausführung eines Dienstvorgangs problemlos bestimmt werden, indem das Ereignisprotokoll untersucht wird.  Dieses Thema veranschaulicht, wie die Zeitdauer bestimmt wird, die ein Dienstvorgang bis zu seinem Abschluss benötigt.  
  
### Bestimmen der Ausführungsdauer eines Dienstvorgangs  
  
1.  Öffnen Sie die Ereignisanzeige, indem Sie auf **Start** und **Ausführen** klicken und dann `eventvwr.exe` eingeben.  
  
2.  Wenn Sie die analytische Ablaufverfolgung nicht aktiviert haben, erweitern Sie **Anwendungs\- und Dienstprotokolle**, **Microsoft**, **Windows** und **Anwendungsserver \- Anwendungen**.  Wählen Sie **Ansicht** und **Analytische und Debugprotokolle einblenden** aus.  Klicken Sie mit der rechten Maustaste auf **Analytisch**, und wählen Sie **Protokoll aktivieren** aus.  Lassen Sie die Ereignisanzeige geöffnet, damit Ablaufverfolgungen angezeigt werden können, nachdem der Dienstvorgang ausgeführt wird.  
  
3.  Öffnen Sie danach eine [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]\-Anwendung, das ein Dienstprojekt und ein Clientprojekt, das mit dem Dienst interagiert, enthält.  Sie können eine Anwendung dieser Art erstellen, indem Sie die Anweisungen im [Lernprogramm 'Erste Schritte'](../../../../../docs/framework/wcf/getting-started-tutorial.md) befolgen.  Wenn Sie die [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]\-Beispiele installiert haben, können Sie das [Erste Schritte](../../../../../docs/framework/wcf/samples/getting-started-sample.md) öffnen, das das vollständige im Lernprogramm erstellte Projekt enthält.  
  
4.  Führen Sie die Serveranwendung aus, indem Sie **F5** drücken.  Führen Sie die Clientanwendung aus, indem Sie mit der rechten Maustaste auf das Clientprojekt klicken und **Debuggen**, **Neue Instanz starten** auswählen.  
  
5.  Aktualisieren Sie das analytische Protokoll in der Ereignisanzeige, und sortieren Sie die Ereignisse nach Ereignis\-ID.  Suchen Sie nach Ereignissen mit der Ereignis ID [214 \- OperationCompleted](../../../../../docs/framework/wcf/diagnostics/etw/214-operationcompleted.md).  Anhand dieser Ereignisse können Sie sehen, welche Vorgänge abgeschlossen wurden und wie lange die Vorgänge dauerten.  Das folgende Ereignis zeigt die Dauer eines Add\-Vorgangs an.  
  
    ```Output  
  
    Ein OperationInvoker hat den Aufruf der 'Add'-Methode abgeschlossen.  Die Methodenaufrufdauer betrug '3' ms.    
    ```