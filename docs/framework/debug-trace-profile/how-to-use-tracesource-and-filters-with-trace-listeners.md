---
title: 'Gewusst wie: Verwenden von TraceSource und Filtern für Ablaufverfolgungslistener'
ms.date: 03/30/2017
helpviewer_keywords:
- initializing trace listeners
- configuration files [.NET Framework], trace listeners
- app.config files, trace listeners
- levels of writing trace messages
- trace listeners, TraceSource class
- application configuration files, trace listeners
- filters, trace listeners
- TraceSource class, trace listeners
- trace listeners, creating
- trace listeners, filters
- trace listeners, initializing
ms.assetid: 21dc2169-947d-453a-b0e2-3dac3ba0cc9f
ms.openlocfilehash: 53cdce767d437c47aab94e883381954f8cf70653
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215922"
---
# <a name="how-to-use-tracesource-and-filters-with-trace-listeners"></a><span data-ttu-id="afa78-102">Gewusst wie: Verwenden von TraceSource und Filtern für Ablaufverfolgungslistener</span><span class="sxs-lookup"><span data-stu-id="afa78-102">How to: Use TraceSource and Filters with Trace Listeners</span></span>
<span data-ttu-id="afa78-103">Eine der neuen Funktionen in .NET Framework, Version 2.0, ist ein verbessertes Ablaufverfolgungssystem.</span><span class="sxs-lookup"><span data-stu-id="afa78-103">One of the new features in the .NET Framework version 2.0 is an enhanced tracing system.</span></span> <span data-ttu-id="afa78-104">Die Grundlage bleibt unverändert: Ablaufverfolgungsmeldungen werden mithilfe von Schaltern an Listener gesendet, die die Daten an das jeweilige zugeordnete Ausgabemedium weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="afa78-104">The basic premise is unchanged: tracing messages are sent through switches to listeners, which report the data to an associated output medium.</span></span> <span data-ttu-id="afa78-105">Ein wichtiger Unterschied in Version 2.0 ist, dass die Ablaufverfolgung mithilfe von Instanzen der <xref:System.Diagnostics.TraceSource>-Klasse eingeleitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="afa78-105">A primary difference for version 2.0 is that traces can be initiated through instances of the <xref:System.Diagnostics.TraceSource> class.</span></span> <span data-ttu-id="afa78-106"><xref:System.Diagnostics.TraceSource> ist als verbessertes System zur Ablaufverfolgung vorgesehen; die Klasse kann statt den statischen Methoden der älteren <xref:System.Diagnostics.Trace>-Klasse und der <xref:System.Diagnostics.Debug>-Klasse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="afa78-106"><xref:System.Diagnostics.TraceSource> is intended to function as an enhanced tracing system and can be used in place of the static methods of the older <xref:System.Diagnostics.Trace> and <xref:System.Diagnostics.Debug> tracing classes.</span></span> <span data-ttu-id="afa78-107">Die vertrauten <xref:System.Diagnostics.Trace>- und <xref:System.Diagnostics.Debug>-Klassen sind immer noch vorhanden, es wird jetzt jedoch empfohlen, die <xref:System.Diagnostics.TraceSource>-Klasse für die Ablaufverfolgung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="afa78-107">The familiar <xref:System.Diagnostics.Trace> and <xref:System.Diagnostics.Debug> classes still exist, but the recommended practice is to use the <xref:System.Diagnostics.TraceSource> class for tracing.</span></span>  
  
 <span data-ttu-id="afa78-108">In diesem Thema wird die Verwendung von <xref:System.Diagnostics.TraceSource> zusammen mit einer Anwendungskonfigurationsdatei erläutert.</span><span class="sxs-lookup"><span data-stu-id="afa78-108">This topic describes the use of a <xref:System.Diagnostics.TraceSource> coupled with an application configuration file.</span></span>  <span data-ttu-id="afa78-109">Es ist möglich, die Ablaufverfolgung unter Verwendung von <xref:System.Diagnostics.TraceSource> ohne Konfigurationsdatei durchzuführen. Dies wird jedoch nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="afa78-109">It is possible, although not recommended, to trace using a <xref:System.Diagnostics.TraceSource> without the use of a configuration file.</span></span> <span data-ttu-id="afa78-110">Weitere Informationen über die Ablaufverfolgung ohne Konfigurationsdatei finden Sie unter [How to: Create and Initialize Trace Sources (Vorgehensweise: Erstellen und Initialisieren von Ablaufverfolgungsquellen)](how-to-create-and-initialize-trace-sources.md).</span><span class="sxs-lookup"><span data-stu-id="afa78-110">For information on tracing without a configuration file, see [How to: Create and Initialize Trace Sources](how-to-create-and-initialize-trace-sources.md).</span></span>  
  
### <a name="to-create-and-initialize-your-trace-source"></a><span data-ttu-id="afa78-111">Erstellen und Initialisieren von Ablaufverfolgungsquellen</span><span class="sxs-lookup"><span data-stu-id="afa78-111">To create and initialize your trace source</span></span>  
  
1. <span data-ttu-id="afa78-112">Der erste Schritt beim Instrumentieren einer Anwendung mit der Ablaufverfolgung ist das Erstellen einer Ablaufverfolgungsquelle.</span><span class="sxs-lookup"><span data-stu-id="afa78-112">The first step to instrumenting an application with tracing is to create a trace source.</span></span> <span data-ttu-id="afa78-113">In umfangreichen Projekten mit verschiedenen Komponenten können Sie für jede Komponente eine separate Ablaufverfolgungsquelle erstellen.</span><span class="sxs-lookup"><span data-stu-id="afa78-113">In large projects with various components, you can create a separate trace source for each component.</span></span> <span data-ttu-id="afa78-114">Es empfiehlt sich, den Anwendungsnamen als Namen der Ablaufverfolgungsquelle zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="afa78-114">The recommended practice is to use the application name for the trace source name.</span></span> <span data-ttu-id="afa78-115">Dies erleichtert es, die unterschiedlichen Ablaufverfolgungen auseinander zu halten.</span><span class="sxs-lookup"><span data-stu-id="afa78-115">This will make it easier to keep the different traces separate.</span></span> <span data-ttu-id="afa78-116">Im folgenden Codebeispiel wird eine neue Ablaufverfolgungsquelle (`mySource)`) erstellt und eine Methode (`Activity1`) aufgerufen, die Ereignisse aufzeichnet.</span><span class="sxs-lookup"><span data-stu-id="afa78-116">The following code creates a new trace source (`mySource)` and calls a method (`Activity1`) that traces events.</span></span>  <span data-ttu-id="afa78-117">Die Ablaufverfolgungsmeldungen werden vom standardmäßigen Ablaufverfolgungslistener geschrieben.</span><span class="sxs-lookup"><span data-stu-id="afa78-117">The trace messages are written by the default trace listener.</span></span>  
  
    ```csharp
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
  
### <a name="to-create-and-initialize-trace-listeners-and-filters"></a><span data-ttu-id="afa78-118">Erstellen und Initialisieren von Ablaufverfolgungslistenern und Filtern</span><span class="sxs-lookup"><span data-stu-id="afa78-118">To create and initialize trace listeners and filters</span></span>  
  
1. <span data-ttu-id="afa78-119">Im Code in der ersten Prozedur werden weder Ablaufverfolgungslistener noch Filter angegeben.</span><span class="sxs-lookup"><span data-stu-id="afa78-119">The code in the first procedure does not programmatically identify any trace listeners or filters.</span></span> <span data-ttu-id="afa78-120">Die Ablaufverfolgungsmeldungen werden allein durch den Code in den standardmäßigen Ablaufverfolgungslistener geschrieben.</span><span class="sxs-lookup"><span data-stu-id="afa78-120">The code alone results in the trace messages being written to the default trace listener.</span></span> <span data-ttu-id="afa78-121">Um bestimmte Ablaufverfolgungslistener und zugeordnete Filter anzugeben, bearbeiten Sie die Konfigurationsdatei, die dem Namen der Anwendung entspricht.</span><span class="sxs-lookup"><span data-stu-id="afa78-121">To configure specific trace listeners and their associated filters, edit the configuration file that corresponds to the name of your application.</span></span> <span data-ttu-id="afa78-122">In dieser Datei können Sie Listener hinzufügen und entfernen sowie die Eigenschaften und Filter für einen Listener festlegen.</span><span class="sxs-lookup"><span data-stu-id="afa78-122">In this file, you can add or remove a listener, set the properties and filter for a listener, or remove listeners.</span></span> <span data-ttu-id="afa78-123">In der folgenden Beispielkonfigurationsdatei wird veranschaulicht, wie ein Konsolen- und ein Textwriter-Ablaufverfolgungslistener für die Ablaufverfolgungsquelle initialisiert werden, die in der vorausgegangenen Prozedur erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="afa78-123">The following configuration file example shows how to initialize a console trace listener and a text writer trace listener for the trace source that is created in the preceding procedure.</span></span> <span data-ttu-id="afa78-124">Neben der Konfiguration für die Ablaufverfolgungslistener werden in der Konfigurationsdatei Filter für beide Listener sowie ein Quellenschalter für die Ablaufverfolgungsquelle erstellt.</span><span class="sxs-lookup"><span data-stu-id="afa78-124">In addition to configuring the trace listeners, the configuration file creates filters for both of the listeners and creates a source switch for the trace source.</span></span> <span data-ttu-id="afa78-125">Es werden zwei Verfahren zum Hinzufügen der Ablaufverfolgungslistener gezeigt: das direkte Hinzufügen des listeners zur Ablaufverfolgungsquelle sowie das Hinzufügen eines Listeners zur gemeinsam genutzten Auflistung der Listener und das anschließende Hinzufügen zur Ablaufverfolgungsquelle nach Namen.</span><span class="sxs-lookup"><span data-stu-id="afa78-125">Two techniques are shown for adding trace listeners: adding the listener directly to the trace source and adding a listener to the shared listeners collection and then adding it by name to the trace source.</span></span> <span data-ttu-id="afa78-126">Die für die beiden Listener angegebenen Filter werden mit unterschiedlichen Stufen für die Quelle initialisiert.</span><span class="sxs-lookup"><span data-stu-id="afa78-126">The filters identified for the two listeners are initialized with different source levels.</span></span> <span data-ttu-id="afa78-127">Dies führt dazu, dass einige Meldungen nur von einem der beiden Listener geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="afa78-127">This results in some messages being written by only one of the two listeners.</span></span>  
  
    ```xml  
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
  
### <a name="to-change-the-level-at-which-a-listener-writes-a-trace-message"></a><span data-ttu-id="afa78-128">Ändern der Ebene, bei der ein Listener eine Ablaufverfolgungsmeldung schreibt</span><span class="sxs-lookup"><span data-stu-id="afa78-128">To change the level at which a listener writes a trace message</span></span>  
  
1. <span data-ttu-id="afa78-129">Die Konfigurationsdatei initialisiert die Einstellungen für die Ablaufverfolgungsquelle, wenn die Anwendung initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="afa78-129">The configuration file initializes the settings for the trace source at the time the application is initialized.</span></span> <span data-ttu-id="afa78-130">Um diese Einstellungen zu ändern, müssen Sie entweder die Konfigurationsdatei ändern und die Anwendung neu starten oder die Anwendung programmgesteuert aktualisieren, indem Sie die <xref:System.Diagnostics.Trace.Refresh%2A?displayProperty=nameWithType>-Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="afa78-130">To change those settings you must change the configuration file and restart the application or programmatically refresh the application using the <xref:System.Diagnostics.Trace.Refresh%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="afa78-131">Die Anwendung kann die durch die Konfigurationsdatei festgelegten Eigenschaften dynamisch ändern, um die vom Benutzer angegebenen Einstellungen zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="afa78-131">The application can dynamically change the properties set by the configuration file to override any settings specified by the user.</span></span>  <span data-ttu-id="afa78-132">So können Sie beispielsweise sicherstellen, dass Meldungen für kritische Fehler unabhängig von den aktuellen Konfigurationseinstellungen immer in eine Textdatei geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="afa78-132">For example, you might want to assure that critical messages are always sent to a text file, regardless of the current configuration settings.</span></span>  
  
    ```csharp
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
  
## <a name="see-also"></a><span data-ttu-id="afa78-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="afa78-133">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.EventTypeFilter>
- [<span data-ttu-id="afa78-134">Vorgehensweise: Erstellen und Initialisieren von Ablaufverfolgungsquellen</span><span class="sxs-lookup"><span data-stu-id="afa78-134">How to: Create and Initialize Trace Sources</span></span>](how-to-create-and-initialize-trace-sources.md)
- [<span data-ttu-id="afa78-135">Ablaufverfolgungslistener</span><span class="sxs-lookup"><span data-stu-id="afa78-135">Trace Listeners</span></span>](trace-listeners.md)
