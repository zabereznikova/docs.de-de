---
title: "How to: Use TraceSource and Filters with Trace Listeners | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "initializing trace listeners"
  - "configuration files [.NET Framework], trace listeners"
  - "app.config files, trace listeners"
  - "levels of writing trace messages"
  - "trace listeners, TraceSource class"
  - "application configuration files, trace listeners"
  - "filters, trace listeners"
  - "TraceSource class, trace listeners"
  - "trace listeners, creating"
  - "trace listeners, filters"
  - "trace listeners, initializing"
ms.assetid: 21dc2169-947d-453a-b0e2-3dac3ba0cc9f
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# How to: Use TraceSource and Filters with Trace Listeners
Eines der neuen Features in .NET Framework, Version 2.0, ist ein verbessertes System zur Ablaufverfolgung.  Die Grundlage bleibt unverändert: Ablaufverfolgungsmeldungen werden mithilfe von Schaltern an Listener gesendet, die die Daten an das jeweilige zugeordnete Ausgabemedium weiterleiten.  Ein wichtiger Unterschied in Version 2.0 ist, dass die Ablaufverfolgung mithilfe von Instanzen der <xref:System.Diagnostics.TraceSource>\-Klasse eingeleitet werden kann.  <xref:System.Diagnostics.TraceSource> ist als verbessertes System zur Ablaufverfolgung vorgesehen; die Klasse kann statt den statischen Methoden der älteren <xref:System.Diagnostics.Trace>\-Klasse und der <xref:System.Diagnostics.Debug>\-Klasse verwendet werden.  Die vertraute <xref:System.Diagnostics.Trace>\-Klasse und die <xref:System.Diagnostics.Debug>\-Klasse sind immer noch vorhanden, es wird jetzt jedoch empfohlen, die <xref:System.Diagnostics.TraceSource>\-Klasse für die Ablaufverfolgung zu verwenden.  
  
 In diesem Thema wird die Verwendung von <xref:System.Diagnostics.TraceSource> zusammen mit einer Anwendungskonfigurationsdatei erläutert.  Es möglich, die Ablaufverfolgung unter Verwendung von <xref:System.Diagnostics.TraceSource> ohne Konfigurationsdatei durchzuführen. Dies wird jedoch nicht empfohlen.  Weitere Informationen über die Ablaufverfolgung ohne Konfigurationsdatei finden Sie unter [Gewusst wie: Erstellen und Initialisieren von Ablaufverfolgungsquellen](../../../docs/framework/debug-trace-profile/how-to-create-and-initialize-trace-sources.md).  
  
### So erstellen und initialisieren Sie eine Ablaufverfolgungsquelle  
  
1.  Der erste Schritt beim Instrumentieren einer Anwendung mit der Ablaufverfolgung ist das Erstellen einer Ablaufverfolgungsquelle.  In umfangreichen Projekten mit verschiedenen Komponenten können Sie für jede Komponente eine separate Ablaufverfolgungsquelle erstellen.  Es empfiehlt sich, den Anwendungsnamen als Namen der Ablaufverfolgungsquelle zu verwenden.  Dies erleichtert es, die unterschiedlichen Ablaufverfolgungen auseinander zu halten.  Im folgenden Codebeispiel wird eine neue Ablaufverfolgungsquelle \(`mySource)` erstellt und eine Methode \(`Activity1`\) aufgerufen, die Ereignisse aufzeichnet.  Die Ablaufverfolgungsmeldungen werden vom Standard\-Ablaufverfolgungslistener geschrieben.  
  
    ```  
    using System;  
    using System.Diagnostics;  
    using System.Threading;  
  
    namespace TraceSourceApp  
    {  
        class Program  
        {  
            private static TraceSource mySource =   
                new TraceSource("TraceSourceApp");  
            static void Main(string[] args)  
            {  
                Activity1();  
                mySource.Close();  
                return;  
            }  
            static void Activity1()  
            {  
                mySource.TraceEvent(TraceEventType.Error, 1,   
                    "Error message.");  
                mySource.TraceEvent(TraceEventType.Warning, 2,   
                    "Warning message.");  
            }  
        }  
    }  
    ```  
  
### So erstellen und initialisieren Sie Ablaufverfolgungslistener und Filter  
  
1.  Im Code in der ersten Prozedur werden weder Ablaufverfolgungslistener noch Filter angegeben.  Die Ablaufverfolgungsmeldungen werden allein durch den Code in den Standard\-Ablaufverfolgungslistener geschrieben.  Um bestimmte Ablaufverfolgungslistener und zugeordnete Filter anzugeben, bearbeiten Sie die Konfigurationsdatei, die dem Namen der Anwendung entspricht.  In dieser Datei können Sie Listener hinzufügen und entfernen sowie die Eigenschaften und Filter für einen Listener festlegen.  In der folgenden Beispielkonfigurationsdatei wird veranschaulicht, wie ein Konsolen\- und ein Textwriter\-Ablaufverfolgungslistener für die Ablaufverfolgungsquelle initialisiert werden, die in der vorausgegangenen Prozedur erstellt wird.  Neben der Konfiguration für die Ablaufverfolgungslistener werden in der Konfigurationsdatei Filter für beide Listener sowie ein Quellenschalter für die Ablaufverfolgungsquelle erstellt.  Es werden zwei Verfahren zum Hinzufügen der Ablaufverfolgungslistener gezeigt: das direkte Hinzufügen des listeners zur Ablaufverfolgungsquelle sowie das Hinzufügen eines Listeners zur gemeinsam genutzten Auflistung der Listener und das anschließende Hinzufügen zur Ablaufverfolgungsquelle nach Namen.  Die für die beiden Listener angegebenen Filter werden mit unterschiedlichen Stufen für die Quelle initialisiert.  Dies führt dazu, dass einige Meldungen nur von einem der beiden Listener geschrieben werden.  
  
    ```  
    <configuration>  
      <system.diagnostics>  
        <sources>  
          <source name="TraceSourceApp"   
            switchName="sourceSwitch"   
            switchType="System.Diagnostics.SourceSwitch">  
            <listeners>  
              <add name="console"   
                type="System.Diagnostics.ConsoleTraceListener">  
                <filter type="System.Diagnostics.EventTypeFilter"   
                  initializeData="Warning"/>  
              </add>  
              <add name="myListener"/>  
              <remove name="Default"/>  
            </listeners>  
          </source>  
        </sources>  
        <switches>  
          <add name="sourceSwitch" value="Warning"/>  
        </switches>  
        <sharedListeners>  
          <add name="myListener"   
            type="System.Diagnostics.TextWriterTraceListener"   
            initializeData="myListener.log">  
            <filter type="System.Diagnostics.EventTypeFilter"   
              initializeData="Error"/>  
          </add>  
        </sharedListeners>  
      </system.diagnostics>  
    </configuration>  
    ```  
  
### So ändern Sie die Stufe, bei der ein Listener eine Ablaufverfolgungsmeldung schreibt  
  
1.  Die Konfigurationsdatei initialisiert die Einstellungen für die Ablaufverfolgungsquelle, wenn die Anwendung initialisiert wird.  Um diese Einstellungen zu ändern, müssen Sie die Konfigurationsdatei ändern und die Anwendung neu starten oder die Anwendung programmgesteuert mithilfe der <xref:System.Diagnostics.Trace.Refresh%2A?displayProperty=fullName>\-Methode aktualisieren.  Die Anwendung kann die durch die Konfigurationsdatei festgelegten Eigenschaften dynamisch ändern, um die vom Benutzer angegebenen Einstellungen zu überschreiben.  So können Sie beispielsweise sicherstellen, dass Meldungen für kritische Fehler unabhängig von den aktuellen Konfigurationseinstellungen immer in eine Textdatei geschrieben werden.  
  
    ```  
    using System;  
    using System.Diagnostics;  
    using System.Threading;  
  
    namespace TraceSourceApp  
    {  
        class Program  
        {  
            private static TraceSource mySource =   
                new TraceSource("TraceSourceApp");  
            static void Main(string[] args)  
            {  
                Activity1();  
  
                // Change the event type for which tracing occurs.  
                // The console trace listener must be specified   
                // in the configuration file. First, save the original  
                // settings from the configuration file.  
                EventTypeFilter configFilter =   
                    (EventTypeFilter)mySource.Listeners["console"].Filter;  
  
                // Then create a new event type filter that ensures   
                // critical messages will be written.  
                mySource.Listeners["console"].Filter =  
                    new EventTypeFilter(SourceLevels.Critical);  
                Activity2();  
  
                // Allow the trace source to send messages to listeners   
                // for all event types. This statement will override   
                // any settings in the configuration file.  
                mySource.Switch.Level = SourceLevels.All;  
  
                // Restore the original filter settings.  
                mySource.Listeners["console"].Filter = configFilter;  
                Activity3();  
                mySource.Close();  
                return;  
            }  
            static void Activity1()  
            {  
                mySource.TraceEvent(TraceEventType.Error, 1,   
                    "Error message.");  
                mySource.TraceEvent(TraceEventType.Warning, 2,   
                    "Warning message.");  
            }  
            static void Activity2()  
            {  
                mySource.TraceEvent(TraceEventType.Critical, 3,   
                    "Critical message.");  
                mySource.TraceInformation("Informational message.");  
            }  
            static void Activity3()  
            {  
                mySource.TraceEvent(TraceEventType.Error, 4,   
                    "Error message.");  
                mySource.TraceInformation("Informational message.");  
            }  
        }  
    }  
    ```  
  
## Siehe auch  
 <xref:System.Diagnostics.TraceSource>   
 <xref:System.Diagnostics.TextWriterTraceListener>   
 <xref:System.Diagnostics.ConsoleTraceListener>   
 <xref:System.Diagnostics.EventTypeFilter>   
 [Gewusst wie: Erstellen und Initialisieren von Ablaufverfolgungsquellen](../../../docs/framework/debug-trace-profile/how-to-create-and-initialize-trace-sources.md)   
 [Trace Listeners](../../../docs/framework/debug-trace-profile/trace-listeners.md)