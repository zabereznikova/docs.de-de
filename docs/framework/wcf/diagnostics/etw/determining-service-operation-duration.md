---
title: Ermitteln der Dienstvorgangsdauer
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8a93a2c-2c20-48b3-8986-57e90e9aa908
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 24f1bc22e088c0198ec8a8f8183611d2b43941b5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="determining-service-operation-duration"></a>Ermitteln der Dienstvorgangsdauer
Wenn die analytische Ablaufverfolgung in einer [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Anwendung aktiviert wird, kann die Dauer der Ausführung eines Dienstvorgangs problemlos bestimmt werden, indem das Ereignisprotokoll untersucht wird.  Dieses Thema veranschaulicht, wie die Zeitdauer bestimmt wird, die ein Dienstvorgang bis zu seinem Abschluss benötigt.  
  
### <a name="determining-service-operation-execution-duration"></a>Bestimmen der Ausführungsdauer eines Dienstvorgangs  
  
1.  Ereignisanzeige öffnen, indem Sie auf **starten**, **ausführen**, und geben Sie `eventvwr.exe`.  
  
2.  Wenn Sie analytische Ablaufverfolgung nicht aktiviert haben, erweitern Sie **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**, **Anwendungsserver-Anwendungen** . Wählen Sie **Ansicht**, **analytische und Debugprotokolle einblenden**. Mit der rechten Maustaste **analytisch** , und wählen Sie **Protokoll aktivieren**. Lassen Sie die Ereignisanzeige geöffnet, damit Ablaufverfolgungen angezeigt werden können, nachdem der Dienstvorgang ausgeführt wird.  
  
3.  Öffnen Sie danach eine [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]-Anwendung, das ein Dienstprojekt und ein Clientprojekt, das mit dem Dienst interagiert, enthält.  Sie können eine solchen Anwendung erstellen, indem Sie die folgenden der [Lernprogramm für erste Schritte](../../../../../docs/framework/wcf/getting-started-tutorial.md).  Haben die [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] Beispiele, die installiert werden, öffnen Sie die [Einstieg](../../../../../docs/framework/wcf/samples/getting-started-sample.md), enthält das abgeschlossene Projekt, das im Lernprogramm erstellt.  
  
4.  Führen Sie die Serveranwendung durch Drücken von **F5**. Führen Sie die Client-Anwendung, indem Sie mit der rechten Maustaste auf die **Client** Projekt klicken und auswählen **Debuggen**, **neue Instanz starten**.  
  
5.  Aktualisieren Sie das analytische Protokoll in der Ereignisanzeige, und sortieren Sie die Ereignisse nach Ereignis-ID.  Suchen Sie nach Ereignissen mit der Ereignis-ID [214 - OperationCompleted](../../../../../docs/framework/wcf/diagnostics/etw/214-operationcompleted.md).  Anhand dieser Ereignisse können Sie sehen, welche Vorgänge abgeschlossen wurden und wie lange die Vorgänge dauerten.  Das folgende Ereignis zeigt die Dauer eines Add-Vorgangs an.  
  
    ```Output  
    An OperationInvoker completed the call to the 'Add' method.  The method call duration was '3' ms.  
    ```
