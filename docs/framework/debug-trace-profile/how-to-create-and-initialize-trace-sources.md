---
title: 'Vorgehensweise: Erstellen und Initialisieren von Ablaufverfolgungsquellen'
description: Erstellen und Initialisieren von Ablauf Verfolgungs Quellen mithilfe der TraceSource-Klasse in .net. Diese Klasse stellt Methoden zum Nachverfolgen von Ereignissen und Daten und zum Ausgeben von Informations Ablauf Verfolgungen bereit.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- trace sources
- initializing trace sources
- configuration files [.NET Framework], trace sources
ms.assetid: f88dda6f-5fda-45be-9b3c-745a9b708c4d
ms.openlocfilehash: 3c3624dce9e860a46a9c8c9e9075a03a7c47cb8d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244131"
---
# <a name="how-to-create-and-initialize-trace-sources"></a><span data-ttu-id="f6f15-104">Vorgehensweise: Erstellen und Initialisieren von Ablaufverfolgungsquellen</span><span class="sxs-lookup"><span data-stu-id="f6f15-104">How to: Create and Initialize Trace Sources</span></span>

<span data-ttu-id="f6f15-105">Die <xref:System.Diagnostics.TraceSource>-Klasse wird von Anwendungen verwendet, um Ablaufverfolgungen zu erzeugen, die der Anwendung zugeordnet werden können.</span><span class="sxs-lookup"><span data-stu-id="f6f15-105">The <xref:System.Diagnostics.TraceSource> class is used by applications to produce traces that can be associated with the application.</span></span> <span data-ttu-id="f6f15-106"><xref:System.Diagnostics.TraceSource> stellt Ablaufverfolgungsmethoden bereit, mit denen Sie Ereignisse und Daten einfach verfolgen und Ablaufverfolgungen zu Informationszwecken ausgeben können.</span><span class="sxs-lookup"><span data-stu-id="f6f15-106"><xref:System.Diagnostics.TraceSource> provides tracing methods that allow you to easily trace events, trace data, and issue informational traces.</span></span> <span data-ttu-id="f6f15-107">Die Ablaufverfolgungsausgabe von <xref:System.Diagnostics.TraceSource> kann mit oder ohne Konfigurationsdateien erstellt und initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="f6f15-107">Trace output from <xref:System.Diagnostics.TraceSource> can be created and initialized with or without the use of configuration files.</span></span> <span data-ttu-id="f6f15-108">Dieses Thema enthält Anweisungen für beide Varianten.</span><span class="sxs-lookup"><span data-stu-id="f6f15-108">This topic provides instructions for both options.</span></span> <span data-ttu-id="f6f15-109">Es wird jedoch empfohlen, Konfigurationsdateien zu verwenden, um die Neukonfiguration der durch die Ablaufverfolgungsquellen erzeugten Ablaufverfolgungen zur Laufzeit zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="f6f15-109">However, we recommend that you use configuration files to facilitate the reconfiguration of the traces produced by trace sources at run time.</span></span>  
  
### <a name="to-create-and-initialize-a-trace-source-using-a-configuration-file"></a><span data-ttu-id="f6f15-110">So erstellen und initialisieren Sie eine Ablaufverfolgungsquelle mit einer Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="f6f15-110">To create and initialize a trace source using a configuration file</span></span>  
  
1. <span data-ttu-id="f6f15-111">Erstellen Sie ein Visual Studio-Konsolen Anwendungsprojekt (.NET Framework), und ersetzen Sie den bereitgestellten Code durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="f6f15-111">Create a Visual Studio console application project (.NET Framework) and replace the supplied code with the following code.</span></span> <span data-ttu-id="f6f15-112">Dieser Code protokolliert Fehler und Warnungen und gibt einige davon in der Konsole aus und einige davon in der myListener-Datei, die von den Einträgen in der Konfigurationsdatei erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="f6f15-112">This code logs errors and warnings and outputs some of them to the console, and some of them to the myListener file that is created by the entries in the configuration file.</span></span>  
  
     [!code-csharp[TraceSourceExample1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/tracesourceexample1/cs/program.cs#1)]
     [!code-vb[TraceSourceExample1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/tracesourceexample1/vb/program.vb#1)]  
  
2. <span data-ttu-id="f6f15-113">Fügen Sie dem Projekt eine Anwendungskonfigurationsdatei hinzu, falls keine vorhanden ist, um die Ablaufverfolgungsquelle mit dem Namen `TraceSourceApp` aus Schritt 1 des Codebeispiels zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="f6f15-113">Add an application configuration file, if one is not present, to the project to initialize the trace source named `TraceSourceApp` in the code example in step 1.</span></span>  
  
3. <span data-ttu-id="f6f15-114">Ersetzen Sie den Standardinhalt der Konfigurationsdatei durch die folgenden Einstellungen, um einen Konsolen-Ablaufverfolgungslistener und einen Textwriter-Ablaufverfolgungslistener für die Ablaufverfolgungsquelle zu initialisieren, die in Schritt 1 erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="f6f15-114">Replace the default configuration file content with the following settings to initialize a console trace listener and a text writer trace listener for the trace source that was created in step 1.</span></span>  
  
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
                  initializeData="Error"/>  
              </add>  
              <add name="myListener"/>  
              <remove name="Default"/>  
            </listeners>  
          </source>  
        </sources>  
        <switches>  
          <add name="sourceSwitch" value="Error"/>  
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
  
     <span data-ttu-id="f6f15-115">Neben der Konfiguration für die Ablaufverfolgungslistener werden in der Konfigurationsdatei Filter für beide Listener sowie ein Quellschalter für die Ablaufverfolgungsquelle erstellt.</span><span class="sxs-lookup"><span data-stu-id="f6f15-115">In addition to configuring the trace listeners, the configuration file creates filters for both listeners and creates a source switch for the trace source.</span></span> <span data-ttu-id="f6f15-116">Es werden zwei Verfahren zum Hinzufügen der Ablaufverfolgungslistener gezeigt: das direkte Hinzufügen des listeners zur Ablaufverfolgungsquelle sowie das Hinzufügen eines Listeners zur gemeinsam genutzten Auflistung der Listener und das anschließende Hinzufügen zur Ablaufverfolgungsquelle nach Namen.</span><span class="sxs-lookup"><span data-stu-id="f6f15-116">Two techniques are shown for adding trace listeners: adding the listener directly to the trace source and adding a listener to the shared listeners collection and then adding it by name to the trace source.</span></span> <span data-ttu-id="f6f15-117">Die für die beiden Listener angegebenen Filter werden mit unterschiedlichen Stufen für die Quelle initialisiert.</span><span class="sxs-lookup"><span data-stu-id="f6f15-117">The filters identified for the two listeners are initialized with different source levels.</span></span> <span data-ttu-id="f6f15-118">Dies führt dazu, dass einige Meldungen nur von einem der beiden Listener geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="f6f15-118">This results in some messages being written by only one of the two listeners.</span></span>  
  
     <span data-ttu-id="f6f15-119">Die Konfigurationsdatei initialisiert die Einstellungen für die Ablaufverfolgungsquelle, wenn die Anwendung initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="f6f15-119">The configuration file initializes the settings for the trace source at the time the application is initialized.</span></span> <span data-ttu-id="f6f15-120">Die Anwendung kann die durch die Konfigurationsdatei festgelegten Eigenschaften dynamisch ändern, um die vom Benutzer angegebenen Einstellungen zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="f6f15-120">The application can dynamically change the properties set by the configuration file to override any settings specified by the user.</span></span> <span data-ttu-id="f6f15-121">So können Sie beispielsweise sicherstellen, dass Meldungen für kritische Fehler unabhängig von den aktuellen Konfigurationseinstellungen immer in eine Textdatei geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="f6f15-121">For example, you might want to ensure that critical messages are always sent to a text file, regardless of the current configuration settings.</span></span> <span data-ttu-id="f6f15-122">Im Beispielcode wird veranschaulicht, wie Einstellungen in der Konfigurationsdatei überschrieben werden können, um sicherzustellen, dass Meldungen für schwerwiegende Fehler an die Ablaufverfolgungslistener ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f6f15-122">The example code demonstrates how to override configuration file settings to ensure that critical messages are output to the trace listeners.</span></span>  
  
     <span data-ttu-id="f6f15-123">Wenn Sie die Einstellungen aus der Konfigurationsdatei ändern, während die Anwendung ausgeführt wird, werden die ursprünglichen Einstellungen nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="f6f15-123">Changing the configuration file settings while the application is executing does not change the initial settings.</span></span> <span data-ttu-id="f6f15-124">Um die Einstellungen zu ändern, müssen Sie entweder die Anwendung neu starten oder die Anwendung programmgesteuert aktualisieren, indem Sie die <xref:System.Diagnostics.Trace.Refresh%2A?displayProperty=nameWithType>-Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="f6f15-124">To change the settings, you must either restart the application or programmatically refresh the application by using the <xref:System.Diagnostics.Trace.Refresh%2A?displayProperty=nameWithType> method.</span></span>  
  
### <a name="to-initialize-trace-sources-listeners-and-filters-without-a-configuration-file"></a><span data-ttu-id="f6f15-125">So initialisieren Sie Ablaufverfolgungsquellen, Listener und Filter ohne eine Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="f6f15-125">To initialize trace sources, listeners, and filters without a configuration file</span></span>  
  
- <span data-ttu-id="f6f15-126">Verwenden Sie den folgenden Beispielcode, um die Ablaufverfolgung mit einer Ablaufverfolgungsquelle zu aktivieren, ohne eine Konfigurationsdatei zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f6f15-126">Use the following example code to enable tracing through a trace source without using a configuration file.</span></span> <span data-ttu-id="f6f15-127">Dieses Verfahren wird nicht empfohlen. Möglicherweise gibt es jedoch Situationen, in denen Sie sich nicht auf Konfigurationsdateien verlassen möchten, um die Ablaufverfolgung sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="f6f15-127">This is not a recommended practice, but there may be circumstances in which you do not want to depend on configuration files to ensure tracing.</span></span>  
  
     [!code-csharp[TraceSourceExample2#1](../../../samples/snippets/csharp/VS_Snippets_CLR/tracesourceexample2/cs/program.cs#1)]
     [!code-vb[TraceSourceExample2#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/tracesourceexample2/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="f6f15-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f6f15-128">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.EventTypeFilter>
- [<span data-ttu-id="f6f15-129">Ablaufverfolgung und Instrumentieren von Anwendungen</span><span class="sxs-lookup"><span data-stu-id="f6f15-129">Tracing and Instrumenting Applications</span></span>](tracing-and-instrumenting-applications.md)
