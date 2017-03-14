---
title: "Debugging Your Visual Basic Application | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "debugging [Visual Basic], common tasks"
ms.assetid: 904760b8-9fe9-42a7-9d65-d93774253219
caps.latest.revision: 28
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 28
---
# Debugging Your Visual Basic Application
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Diese Seite enthält Links auf Dokumentation für die in [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] enthaltenen Debuggingfunktionen.  Sie können zum Beispiel Semantikfehler in der Anwendung feststellen, indem Sie ihr Laufzeitverhalten im Debugger beobachten.  
  
 Mithilfe eines Debuggers können Sie den Inhalt von Anwendungsvariablen untersuchen, ohne dass zusätzliche Aufrufe für die Ausgabe der Werte hinzugefügt werden müssen.  Auf ähnliche Weise können Sie einen Haltepunkt im Code einfügen, um die Programmausführung am angegebenen Punkt anzuhalten.  
  
## Steuern der Programmausführung  
 In der folgenden Tabelle werden Debuggingaufgaben im Zusammenhang mit der Steuerung der Programmausführung aufgeführt. Außerdem sind die Links zu den entsprechenden Hilfeseiten aufgeführt.  
  
|||  
|-|-|  
|To|Siehe|  
|Beginnen, ein Visual Studio\-Projekt zu debuggen, Anfügen an einen Prozess, Unterbrechen im Code, Code durcharbeiten, Ausführen bis zum Cursor, Ausführen bis zu einer Funktion in der Aufrufliste, Nächste Anweisung festlegen, Nur\-Mein\-Code durcharbeiten, Debuggen beenden, Debuggen neu starten oder Von einem debuggten Prozess trennen.|[Navigieren im Code mit dem Debugger](/visual-studio/debugger/navigating-through-code-with-the-debugger)|  
|Geben Sie die Konfigurationen für die Debug\- und Freigabeversionen eines Programms an.|[Debug and Release Project Configurations](http://msdn.microsoft.com/de-de/0440b300-0614-4511-901a-105b771b236e)|  
|Festlegen von Startoptionen \(Befehlszeilenargumente, Arbeitsverzeichnis, Remotecomputer\)|[NIB: How to: Set Start Options for Application Debugging](http://msdn.microsoft.com/de-de/ce792058-7bac-4dd6-858b-466e872687b8)|  
|Debuggen zur Entwurfszeit|[Exemplarische Vorgehensweise: Debuggen zur Entwurfszeit](../Topic/Walkthrough:%20Debugging%20at%20Design%20Time.md)|  
|Just\-in\-Time\-Debuggen aktivieren. Hierbei wird der Visual Studio\-Debugger automatisch gestartet, wenn in einem Programm, das außerhalb von Visual Studio ausgeführt wird, ein schwerwiegender Fehler auftritt.|[Just\-In\-Time\-Debuggen](/visual-studio/debugger/just-in-time-debugging-in-visual-studio)|  
|Legen Sie Haltepunkte für Quellzeilen, Assemblyanweisungen und die Aufruflistenfunktion fest.  Geben Sie Bedingungen, Trefferzähler und Ausführungsspeicherort an.|[Verwenden von Haltepunkten](/visual-studio/debugger/using-breakpoints)|  
  
## Behandeln von Ausnahmen  
 In der folgenden Tabelle werden Debuggingaufgaben im Zusammenhang mit der Behandlung von Ausnahmen und die zugehörigen Hilfeseiten aufgeführt.  
  
|||  
|-|-|  
|Zweck|Siehe|  
|Programmunterbrechung bei nicht behandelten Ausnahmen|[Gewusst wie: Unterbrechen bei Ausnahmen, die nicht vom Benutzercode behandelt werden](../Topic/How%20to:%20Break%20on%20User-Unhandled%20Exceptions.md)|  
|Programmunterbrechung beim Auslösen einer Ausnahme|[Gewusst wie: Unterbrechen bei ausgelöster Ausnahme](../Topic/How%20to:%20Break%20When%20an%20Exception%20is%20Thrown.md)|  
|Programmunterbrechung bei Ausnahmen \(erste Chance\)|[Gewusst wie: Unterbrechen bei ausgelöster Ausnahme](../Topic/How%20to:%20Break%20When%20an%20Exception%20is%20Thrown.md)|  
|Verwenden des Ausnahmen\-Assistenten|[How to: Correct Run\-Time Errors with the Exception Assistant](../Topic/How%20to:%20Correct%20Run-Time%20Errors%20with%20the%20Exception%20Assistant.md)|  
|Hinzufügen einer neuen Ausnahme|[Gewusst wie: Hinzufügen von neuen Ausnahmen](../Topic/How%20to:%20Add%20New%20Exceptions.md)|  
|Fortsetzen der Ausführung nach dem Auslösen einer Ausnahme|[Fortfahren mit der Ausführung nach einer Ausnahme](/visual-studio/debugger/continuing-execution-after-an-exception)|  
  
## "Bearbeiten und Fortfahren"  
 In der folgenden Tabelle werden Debuggingaufgaben im Zusammenhang mit Bearbeiten und Fortfahren und die zugehörigen Hilfeseiten aufgeführt.  
  
|||  
|-|-|  
|Zweck|Siehe|  
|Bearbeiten und Fortfahren aktivieren und deaktivieren|[Gewusst wie: Aktivieren und Deaktivieren von "Bearbeiten und Fortfahren"](../Topic/How%20to:%20Enable%20and%20Disable%20Edit%20and%20Continue.md)|  
|Übernehmen von Codeänderungen aus Bearbeiten und Fortfahren beenden|[Gewusst wie: Anhalten von Codeänderungen](../Topic/How%20to:%20Stop%20Code%20Changes.md)|  
|Anwenden von Bearbeitungen im Unterbrechungsmodus|[Gewusst wie: Anwenden von Bearbeitungen im Unterbrechungsmodus mithilfe von "Bearbeiten und Fortfahren"](../Topic/How%20to:%20Apply%20Edits%20in%20Break%20Mode%20with%20Edit%20and%20Continue.md)|  
  
## Untersuchen von Debuggingdaten  
 In der folgenden Tabelle werden Debuggingaufgaben im Zusammenhang mit der Anzeige von Debuggingdaten und die zugehörigen Hilfeseiten aufgeführt.  
  
|||  
|-|-|  
|Zweck|Siehe|  
|Verwenden des Fensters **Register** zum Anzeigen von Registerinhalten|[Gewusst wie: Verwenden des Fensters "Register"](../Topic/How%20to:%20Use%20the%20Registers%20Window.md)|  
|Verwenden des Fensters **Aufrufliste** zum Anzeigen von Funktions\- und Prozeduraufrufen, die sich derzeit im Stapel befinden|[Gewusst wie: Verwenden des Fensters Aufrufliste](../Topic/How%20to:%20Use%20the%20Call%20Stack%20Window.md)|  
|Verwenden des Fensters **Disassembly** zum Anzeigen von Assemblycode, der den vom Compiler erstellten Anweisungen entspricht|[Gewusst wie: Verwenden des Fensters Disassembly](../Topic/How%20to:%20Use%20the%20Disassembly%20Window.md)|  
|Verwenden des Fensters **Module**, um die vom Programm verwendeten Module mit einer Beschreibung aufzulisten|[Gewusst wie: Verwenden des Fensters Module](../Topic/How%20to:%20Use%20the%20Modules%20Window.md)|  
|Verwenden des Fensters **Skript\-Explorer** zum Auflisten von Skriptdateien, die gegenwärtig im Programm geladen sind|[Gewusst wie: Anzeigen von Skriptdokumenten](../Topic/How%20to:%20View%20Script%20Documents.md)|  
|Verwenden des Fensters **Threads** zum Überprüfen und Steuern von Threads im Programm|[Gewusst wie: Verwenden des Fensters Threads](../Topic/How%20to:%20Use%20the%20Threads%20Window.md)|  
  
## Siehe auch  
 [Exemplarische Vorgehensweise: Debuggen eines Windows Forms](../Topic/Walkthrough:%20Debugging%20a%20Windows%20Form.md)   
 [Debuggen von verwaltetem Code](/visual-studio/debugger/debugging-managed-code)   
 [Debuggen von systemeigenem Code](/visual-studio/debugger/debugging-native-code)   
 [Debuggen von Webanwendungen und Skripts](/visual-studio/debugger/debugging-web-applications-and-script)   
 [Referenz zur Debugger\-Benutzeroberfläche](/visual-studio/debugger/debugging-user-interface-reference)   
 [Einstellungen und Vorbereitung für das Debuggen](/visual-studio/debugger/debugger-settings-and-preparation)   
 [Debugger – Grundlagen](/visual-studio/debugger/debugger-basics)   
 [Navigieren im Code mit dem Debugger](/visual-studio/debugger/navigating-through-code-with-the-debugger)   
 [Verwenden von IntelliTrace](/visual-studio/debugger/intellitrace)   
 [C\#\-, F\#\- und Visual Basic\-Projekttypen](../Topic/Debugging%20Preparation:%20C%23,%20F%23,%20and%20Visual%20Basic%20Project%20Types.md)   
 [Gewusst wie: Anwenden von Bearbeitungen im Unterbrechungsmodus mithilfe von "Bearbeiten und Fortfahren"](../Topic/How%20to:%20Apply%20Edits%20in%20Break%20Mode%20with%20Edit%20and%20Continue.md)