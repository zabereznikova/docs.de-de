---
title: Ermitteln der Dienstvorgangsdauer
ms.date: 03/30/2017
ms.assetid: e8a93a2c-2c20-48b3-8986-57e90e9aa908
ms.openlocfilehash: fd7dec5784f50a0613b574822a31202a859b34c6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61999452"
---
# <a name="determining-service-operation-duration"></a>Ermitteln der Dienstvorgangsdauer
Wenn die analytische Ablaufverfolgung in einer Windows Communication Foundation (WCF)-Anwendung aktiviert ist, kann die Dauer der Ausführung für einen Dienstvorgang ganz einfach ermittelt werden im Ereignisprotokoll.  Dieses Thema veranschaulicht, wie die Zeitdauer bestimmt wird, die ein Dienstvorgang bis zu seinem Abschluss benötigt.  
  
### <a name="determining-service-operation-execution-duration"></a>Bestimmen der Ausführungsdauer eines Dienstvorgangs  
  
1. Ereignisanzeige öffnen, indem Sie auf **starten**, **ausführen**, und geben Sie `eventvwr.exe`.  
  
2. Wenn Sie analytische Ablaufverfolgung nicht aktiviert haben, erweitern Sie **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**, **Anwendungsserver-Anwendungen** . Wählen Sie **Ansicht**, **analytische und Debugprotokolle einblenden**. Mit der rechten Maustaste **analytisch** , und wählen Sie **Protokoll aktivieren**. Lassen Sie die Ereignisanzeige geöffnet, damit Ablaufverfolgungen angezeigt werden können, nachdem der Dienstvorgang ausgeführt wird.  
  
3. Öffnen Sie als Nächstes eine WCF-Anwendung, das ein Dienstprojekt und ein Clientprojekt, das mit dem Dienst interagiert.  Sie können eine solche Anwendung erstellen, indem Sie die folgenden der [Getting Started Tutorial](../../../../../docs/framework/wcf/getting-started-tutorial.md).  Wenn Sie die WCF-Beispiele installiert haben, können Sie öffnen die [Einstieg](../../../../../docs/framework/wcf/samples/getting-started-sample.md), enthält das abgeschlossene Projekt, das in diesem Tutorial erstellt haben.  
  
4. Führen Sie die Serveranwendung durch Drücken von **F5**. Führen Sie die Client-Anwendung, indem Sie mit der rechten Maustaste auf die **Client** Projekt- und Auswählen von **Debuggen**, **neue Instanz starten**.  
  
5. Aktualisieren Sie das analytische Protokoll in der Ereignisanzeige, und sortieren Sie die Ereignisse nach Ereignis-ID.  Suchen Sie nach Ereignissen mit Ereignis-ID [214 - OperationCompleted](../../../../../docs/framework/wcf/diagnostics/etw/214-operationcompleted.md).  Anhand dieser Ereignisse können Sie sehen, welche Vorgänge abgeschlossen wurden und wie lange die Vorgänge dauerten.  Das folgende Ereignis zeigt die Dauer eines Add-Vorgangs an.  
  
    ```Output  
    An OperationInvoker completed the call to the 'Add' method.  The method call duration was '3' ms.  
    ```
