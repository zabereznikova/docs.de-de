---
title: Ermitteln der Dienstvorgangsdauer
ms.date: 03/30/2017
ms.assetid: e8a93a2c-2c20-48b3-8986-57e90e9aa908
ms.openlocfilehash: 9bc38f40b22eca8278905440ee69af9f38b81a0d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798115"
---
# <a name="determining-service-operation-duration"></a>Ermitteln der Dienstvorgangsdauer
Wenn die analytische Ablauf Verfolgung in einer Windows Communication Foundation (WCF)-Anwendung aktiviert ist, kann die Ausführungsdauer für einen Dienst Vorgang durch Untersuchen des Ereignis Protokolls leicht ermittelt werden.  Dieses Thema veranschaulicht, wie die Zeitdauer bestimmt wird, die ein Dienstvorgang bis zu seinem Abschluss benötigt.  
  
### <a name="determining-service-operation-execution-duration"></a>Bestimmen der Ausführungsdauer eines Dienstvorgangs  
  
1. Öffnen Sie Ereignisanzeige, indem Sie auf **Start**und **Ausführen**klicken und dann eingeben `eventvwr.exe`.  
  
2. Wenn Sie die analytische Ablauf Verfolgung nicht aktiviert haben, erweitern Sie **Anwendungs-und Dienst Protokolle**, **Microsoft**, **Windows**, **Anwendungs Server-Anwendungen**. Wählen Sie **Ansicht**, **analytische und Debugprotokolle anzeigen**aus. Klicken Sie mit der rechten Maustaste auf **Analyse** , und wählen Sie **Protokoll aktivieren** Lassen Sie die Ereignisanzeige geöffnet, damit Ablaufverfolgungen angezeigt werden können, nachdem der Dienstvorgang ausgeführt wird.  
  
3. Öffnen Sie als nächstes eine WCF-Anwendung, die ein Dienstprojekt und ein Client Projekt enthält, das mit diesem Dienst interagiert.  Sie können eine solche Anwendung erstellen, indem Sie das [Tutorial "Getting Started](../../getting-started-tutorial.md)" befolgen.  Wenn Sie die WCF-Beispiele installiert [haben, können Sie die ersten](../../samples/getting-started-sample.md)Schritte öffnen, die das abgeschlossene Projekt enthalten, das Sie im Tutorial erstellt haben.  
  
4. Führen Sie die Serveranwendung aus, indem Sie **F5**drücken. Führen Sie die Client Anwendung aus, indem Sie mit der rechten Maustaste auf das **Client** Projekt klicken und **Debuggen**, **neue Instanz starten**auswählen.  
  
5. Aktualisieren Sie das analytische Protokoll in der Ereignisanzeige, und sortieren Sie die Ereignisse nach Ereignis-ID.  Suchen Sie nach Ereignissen mit der Ereignis [-ID 214-operationabgeschlossene](214-operationcompleted.md).  Anhand dieser Ereignisse können Sie sehen, welche Vorgänge abgeschlossen wurden und wie lange die Vorgänge dauerten.  Das folgende Ereignis zeigt die Dauer eines Add-Vorgangs an.  
  
    ```Output  
    An OperationInvoker completed the call to the 'Add' method.  The method call duration was '3' ms.  
    ```
