---
title: "Fehler beim &#220;berwachen von Dienstvorg&#228;ngen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 59472ba3-8ebf-4479-bd7b-f440d5e636cb
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Fehler beim &#220;berwachen von Dienstvorg&#228;ngen
Wenn die analytische Ablaufverfolgung für eine Anwendung aktiviert ist, können Dienstfehler in der Ereignisanzeige auf einfache Weise überwacht werden.In diesem Thema wird erläutert, wie festgestellt wird, wenn ein Dienstvorgang fehlschlägt, und wie die Fehlerursache bestimmt wird.  
  
### Bestimmen der Fehlerinformationen des Dienstvorgangs  
  
1.  Öffnen Sie die Ereignisanzeige, indem Sie auf **Start** und **Ausführen** klicken und dann `eventvwr.exe` eingeben.  
  
2.  Wenn Sie die analytische Ablaufverfolgung nicht aktiviert haben, erweitern Sie **Anwendungs\- und Dienstprotokolle**, **Microsoft**, **Windows** und **Anwendungsserver \- Anwendungen**.Wählen Sie **Ansicht** und **Analytische und Debugprotokolle einblenden** aus.Klicken Sie mit der rechten Maustaste auf **Analytisch**, und wählen Sie **Protokoll aktivieren** aus.Lassen Sie die Ereignisanzeige geöffnet, damit Ablaufverfolgungen angezeigt werden können, nachdem der Dienstvorgang fehlgeschlagen ist.  
  
3.  Öffnen Sie als Nächstes das Beispiel, das Sie im [Lernprogramm 'Erste Schritte'](../../../../../docs/framework/wcf/getting-started-tutorial.md) in [!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)] erstellt haben. Beachten Sie, dass Sie [!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)] als Administrator ausführen müssen, damit der Dienst erstellt werden kann.Wenn Sie die [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]\-Beispiele installiert haben, können Sie das [Erste Schritte](../../../../../docs/framework/wcf/samples/getting-started-sample.md) öffnen, das das im Lernprogramm erstellte vollständige Projekt enthält.  
  
4.  Fügen Sie im Serverprojekt in der Datei Program.cs die folgende Codezeile am Anfang der `Divide`\-Methode in der `CalculatorService`\-Klasse hinzu:  
  
    ```  
    if (n2 == 0) throw new DivideByZeroException();  
  
    ```  
  
5.  Ändern Sie in der Datei Program.cs im Clientprojekt den Wert, der Wert2 zugewiesen ist, in 0 \(null\):  
  
    ```  
    //Call the Divide service operation  
    value1 = 22.00D;  
    value2 = 0.00D;  
    result = client.Divide(value1, value2);  
    Console.WriteLine("Divide({0}, {1}) = {2}", value1, value2, result);  
  
    ```  
  
6.  Führen Sie die Serveranwendung ohne Debuggen aus, indem Sie **STRG\+F5** drücken.  
  
7.  Öffnen Sie eine Visual Studio\-Eingabeaufforderung.Navigieren Sie zum Clientverzeichnis, und führen Sie den Client über die Befehlszeile aus.  
  
8.  Deaktivieren und aktualisieren Sie das analytische Protokoll in der Ereignisanzeige, und sortieren Sie die Ereignisse nach Ereignis\-ID.Suchen Sie nach einem Ereignis mit der Ereignis\-ID [219 \- ServiceException](../../../../../docs/framework/wcf/diagnostics/etw/219-serviceexception.md), die den Dienstfehler beschreibt.  
  
    ```Output  
    Während der Nachrichtenverarbeitung ist ein Ausnahmefehler vom Typ 'System.DivideByZeroException' aufgetreten.Vollständige Ausnahme ToString: System.DivideByZeroException: Es wurde versucht, durch 0 (null) zu teilen.  
    ```  
  
    > [!NOTE]
    >  Ereignisse werden gepuffert, wenn sie an die Ereignisanzeige gesendet werden; das Fehlerereignis wird möglicherweise nicht sofort angezeigt.