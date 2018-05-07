---
title: Ermitteln der Dienstvorgangsdauer
ms.date: 03/30/2017
ms.assetid: e8a93a2c-2c20-48b3-8986-57e90e9aa908
ms.openlocfilehash: a7615a4574210ad6e9b5eee2e5d5855365768854
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="determining-service-operation-duration"></a>Ermitteln der Dienstvorgangsdauer
Wenn die analytische Ablaufverfolgung in einer Windows Communication Foundation (WCF)-Anwendung aktiviert ist, kann die Dauer der Ausführung für einen Dienstvorgang problemlos ermittelt werden im Ereignisprotokoll.  Dieses Thema veranschaulicht, wie die Zeitdauer bestimmt wird, die ein Dienstvorgang bis zu seinem Abschluss benötigt.  
  
### <a name="determining-service-operation-execution-duration"></a>Bestimmen der Ausführungsdauer eines Dienstvorgangs  
  
1.  Ereignisanzeige öffnen, indem Sie auf **starten**, **ausführen**, und geben Sie `eventvwr.exe`.  
  
2.  Wenn Sie analytische Ablaufverfolgung nicht aktiviert haben, erweitern Sie **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**, **Anwendungsserver-Anwendungen** . Wählen Sie **Ansicht**, **analytische und Debugprotokolle einblenden**. Mit der rechten Maustaste **analytisch** , und wählen Sie **Protokoll aktivieren**. Lassen Sie die Ereignisanzeige geöffnet, damit Ablaufverfolgungen angezeigt werden können, nachdem der Dienstvorgang ausgeführt wird.  
  
3.  Öffnen Sie danach eine [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]-Anwendung, das ein Dienstprojekt und ein Clientprojekt, das mit dem Dienst interagiert, enthält.  Sie können eine solchen Anwendung erstellen, indem Sie die folgenden der [Lernprogramm für erste Schritte](../../../../../docs/framework/wcf/getting-started-tutorial.md).  Haben die [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] Beispiele, die installiert werden, öffnen Sie die [Einstieg](../../../../../docs/framework/wcf/samples/getting-started-sample.md), enthält das abgeschlossene Projekt, das im Lernprogramm erstellt.  
  
4.  Führen Sie die Serveranwendung durch Drücken von **F5**. Führen Sie die Client-Anwendung, indem Sie mit der rechten Maustaste auf die **Client** Projekt klicken und auswählen **Debuggen**, **neue Instanz starten**.  
  
5.  Aktualisieren Sie das analytische Protokoll in der Ereignisanzeige, und sortieren Sie die Ereignisse nach Ereignis-ID.  Suchen Sie nach Ereignissen mit der Ereignis-ID [214 - OperationCompleted](../../../../../docs/framework/wcf/diagnostics/etw/214-operationcompleted.md).  Anhand dieser Ereignisse können Sie sehen, welche Vorgänge abgeschlossen wurden und wie lange die Vorgänge dauerten.  Das folgende Ereignis zeigt die Dauer eines Add-Vorgangs an.  
  
    ```Output  
    An OperationInvoker completed the call to the 'Add' method.  The method call duration was '3' ms.  
    ```
