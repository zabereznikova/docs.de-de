---
title: "Fehler beim Überwachen von Dienstvorgängen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59472ba3-8ebf-4479-bd7b-f440d5e636cb
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ce62eb348cb57ce6137c58fbc50a32e829980c0c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="monitoring-service-operation-failures"></a>Fehler beim Überwachen von Dienstvorgängen
Wenn die analytische Ablaufverfolgung für eine Anwendung aktiviert ist, können Dienstfehler in der Ereignisanzeige auf einfache Weise überwacht werden.  In diesem Thema wird erläutert, wie festgestellt wird, wenn ein Dienstvorgang fehlschlägt, und wie die Fehlerursache bestimmt wird.  
  
### <a name="determining-service-operation-failure-information"></a>Bestimmen der Fehlerinformationen des Dienstvorgangs  
  
1.  Ereignisanzeige öffnen, indem Sie auf **starten**, **ausführen**, und geben Sie `eventvwr.exe`.  
  
2.  Wenn Sie analytische Ablaufverfolgung nicht aktiviert haben, erweitern Sie **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**, **Anwendungsserver-Anwendungen** . Wählen Sie **Ansicht**, **analytische und Debugprotokolle einblenden**. Mit der rechten Maustaste **analytisch** , und wählen Sie **Protokoll aktivieren**. Lassen Sie die Ereignisanzeige geöffnet, damit Ablaufverfolgungen angezeigt werden können, nachdem der Dienstvorgang fehlgeschlagen ist.  
  
3.  Als Nächstes öffnen Sie das Beispiel erstellt, der [Lernprogramm für erste Schritte](../../../../../docs/framework/wcf/getting-started-tutorial.md) in [!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)] Hinweis an, die Sie ausführen müssen [!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)] als Administrator, damit der Dienst erstellt werden kann. Haben die [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] Beispiele, die installiert werden, öffnen Sie die [Einstieg](../../../../../docs/framework/wcf/samples/getting-started-sample.md), enthält das abgeschlossene Projekt, das im Lernprogramm erstellt.  
  
4.  Fügen Sie im Serverprojekt in der Datei Program.cs die folgende Codezeile am Anfang der `Divide`-Methode in der `CalculatorService`-Klasse hinzu:  
  
    ```  
    if (n2 == 0) throw new DivideByZeroException();  
    ```  
  
5.  Ändern Sie in der Datei Program.cs im Clientprojekt den Wert, der Wert2 zugewiesen ist, in 0 (null):  
  
    ```  
    //Call the Divide service operation  
    value1 = 22.00D;  
    value2 = 0.00D;  
    result = client.Divide(value1, value2);  
    Console.WriteLine("Divide({0}, {1}) = {2}", value1, value2, result);  
    ```  
  
6.  Führen Sie die Serveranwendung ohne Debuggen durch Drücken von **STRG + F5**.  
  
7.  Öffnen Sie eine Visual Studio-Eingabeaufforderung.  Navigieren Sie zum Clientverzeichnis, und führen Sie den Client über die Befehlszeile aus.  
  
8.  Deaktivieren und aktualisieren Sie das analytische Protokoll in der Ereignisanzeige, und sortieren Sie die Ereignisse nach Ereignis-ID.  Suchen Sie nach einem Ereignis mit der Ereignis-ID [219 - ServiceException](../../../../../docs/framework/wcf/diagnostics/etw/219-serviceexception.md), das den Dienstfehler beschreibt.  
  
    ```Output  
    There was an unhandled exception of type 'System.DivideByZeroException' during message processing.  Full Exception ToString: System.DivideByZeroException: Attempted to divide by zero.  
    ```  
  
    > [!NOTE]
    >  Ereignisse werden gepuffert, wenn sie an die Ereignisanzeige gesendet werden; das Fehlerereignis wird möglicherweise nicht sofort angezeigt.
