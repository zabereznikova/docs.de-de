---
title: "Exemplarische Vorgehensweise: Filterung der Ausgaben von &quot;My.Application.Log&quot; (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Filtern der Ausgabe My.Log-Objekt"
  - "Filtern der Ausgabe My.Application.Log-Objekt"
  - "die Anwendungsereignisprotokolle, Ausgabe filtern"
ms.assetid: 2c0a457a-38a4-49e1-934d-a51320b7b4ca
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Exemplarische Vorgehensweise: Filterung der Ausgaben von &quot;My.Application.Log&quot; (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

In dieser exemplarischen Vorgehensweise veranschaulicht, wie das Protokoll für die Filterung ändern die `My.Application.Log` Objekt, um zu steuern, welche Informationen übergeben wird, aus der `Log` Objekt, das die Listener und welche Informationen von den Listenern geschrieben wird. Sie können das Protokollierungsverhalten ändern, auch nach dem Erstellen der Anwendung, da die Konfigurationsinformationen in der Konfigurationsdatei der Anwendung gespeichert ist.  
  
## <a name="getting-started"></a>Erste Schritte  
 Nachrichten, die `My.Application.Log` Schreibvorgänge verfügt über einen zugeordneten Schweregrad, welche Filtermechanismen zu verwenden, um die Protokollausgabe steuern. Diese Anwendung verwendet `My.Application.Log` Methoden zum Schreiben von mehreren Nachrichten mit Schweregrade protokollieren.  
  
#### <a name="to-build-the-sample-application"></a>Zum Erstellen der beispielanwendung  
  
1.  Öffnen Sie eine neue [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] Windows-Anwendungsprojekt.  
  
2.  Hinzufügen einer Schaltfläche mit dem Namen Button1 zu Form1 hinzu.  
  
3.  In der <xref:System.Windows.Forms.Control.Click> -Ereignishandler für Button1, fügen Sie folgenden Code:  
  
     [!code-vb[VbVbcnMyApplicationLogFiltering#1](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/visualbasic/VbVbcnMyApplicationLogFiltering/Form1.vb#1)]  
  
4.  Die Anwendung im Debugger auszuführen.  
  
5.  Drücken Sie **Button1**.  
  
     Die Anwendung schreibt die folgende Informationen in der Datei der Anwendung debuggen und die Protokolldatei.  
  
     `DefaultSource Information: 0 : In Button1_Click`  
  
     `DefaultSource Error: 2 : Error in the application.`  
  
6.  Schließen Sie die Anwendung.  
  
     Informationen zum Anzeigen der Anwendung Debug-Ausgabefenster finden Sie unter [Ausgabefenster](/visual-studio/ide/reference/output-window). Informationen auf den Speicherort der Protokolldatei für die Anwendung finden Sie unter [Exemplarische Vorgehensweise: bestimmen, wohin "My.Application.log" schreibt Informationen](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).  
  
    > [!NOTE]
    >  In der Standardeinstellung leert die Anwendung die Protokolldatei Ausgabe beim Schließen der Anwendung.  
  
     Im obigen Beispiel ist der zweite Aufruf von der <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A> und der Aufruf von der <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A> Methode erzeugt, während die erste und letzte Aufrufe an die `WriteEntry` Methode nicht. Grund hierfür ist, den Schweregrad von `WriteEntry` und `WriteException` sind "Information" und "Fehler", die zulässig sind die `My.Application.Log` des Objekts Standard Protokoll filtern. Allerdings werden Ereignisse mit einem Schweregrad von "Start" und "Beenden" Protokollausgabe verhindert.  
  
## <a name="filtering-for-all-myapplicationlog-listeners"></a>Filterung für alle My.Application.Log-Listener  
 Die `My.Application.Log` -Objekt verwendet eine <xref:System.Diagnostics.SourceSwitch> namens `DefaultSwitch` steuern, welche von übergibt Nachrichten die `WriteEntry` und `WriteException` Methoden, um die Protokolllistener. Sie können konfigurieren, `DefaultSwitch` in der Anwendungskonfigurationsdatei durch Festlegen ihres Werts eines der <xref:System.Diagnostics.SourceLevels> -Enumerationswerte. Standardmäßig ist der Wert "Informationen".  
  
 Diese Tabelle zeigt den Schweregrad für die Anmeldung zum Schreiben einer Meldung an die Listener einer bestimmten erforderlich `DefaultSwitch` festlegen.  
  
|||  
|-|-|  
|DefaultSwitch-Wert|Erforderlich für die Ausgabe den Schweregrad der Meldung|  
|`Critical`|`Critical`|  
|`Error`|`Critical` oder `Error`|  
|`Warning`|`Critical`, `Error` oder `Warning`|  
|`Information`|`Critical`, `Error`, `Warning` oder `Information`|  
|`Verbose`|`Critical`, `Error`, `Warning`, `Information` oder `Verbose`|  
|`ActivityTracing`|`Start`, `Stop`, `Suspend`, `Resume` oder `Transfer`|  
|`All`|Alle Nachrichten sind zulässig.|  
|`Off`|Alle Nachrichten werden blockiert.|  
  
> [!NOTE]
>  Die `WriteEntry` und `WriteException` Methoden geben jeweils eine Überladung, der nicht mit einen Schweregrad haben. Der implizite Schweregrad für die `WriteEntry` Überladung ist "Information", und der implizite Schweregrad für die `WriteException` -Überladung ist "Error".  
  
 Dieser Tabelle werden die im vorherigen Beispiel gezeigte Protokollausgaben erläutert: mit der standardmäßigen `DefaultSwitch` "Information" festlegen, nur für den zweiten Aufruf der `WriteEntry` -Methode und der Aufruf von der `WriteException` -Methode Protokollausgaben.  
  
#### <a name="to-log-only-activity-tracing-events"></a>Ablaufverfolgungsereignisse einzige Aktivität protokollieren  
  
1.  Mit der rechten Maustaste in "App.config" in der **Projektmappen-Explorer** und wählen Sie **Öffnen**.  
  
     - oder -   
  
     Wenn keine app.config-Datei vorhanden ist:  
  
    1.  Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.  
  
    2.  Wählen Sie im Dialogfeld **Neues Element hinzufügen** den Eintrag **Anwendungskonfigurationsdatei**aus.  
  
    3.  Klicken Sie auf **Hinzufügen**.  
  
2.  Suchen Sie die `<switches>` Abschnitt, der in der `<system.diagnostics>` Abschnitt, der in der obersten Ebene wird `<configuration>` Abschnitt.  
  
3.  Suchen Sie das Element, das addiert `DefaultSwitch` auf die Auflistung von Schaltern. Sie sollten dieses Element ähnelt:  
  
     `<add name="DefaultSwitch" value="Information" />`  
  
4.  Ändern Sie den Wert, der die `value` -Attributs in "ActivityTracing".  
  
5.  Der Inhalt der app.config-Datei sollte ähnlich dem folgenden XML-Code sein:  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.diagnostics>  
        <sources>  
          <!-- This section configures My.Application.Log -->  
          <source name="DefaultSource" switchName="DefaultSwitch">  
            <listeners>  
              <add name="FileLog"/>  
            </listeners>  
          </source>  
        </sources>  
        <switches>  
          <add name="DefaultSwitch" value="ActivityTracing" />  
        </switches>  
        <sharedListeners>  
          <add name="FileLog"  
               type="Microsoft.VisualBasic.Logging.FileLogTraceListener,   
                     Microsoft.VisualBasic, Version=8.0.0.0,   
                     Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a,   
                     processorArchitecture=MSIL"   
               initializeData="FileLogWriter"/>  
        </sharedListeners>  
      </system.diagnostics>  
    </configuration>  
    ```  
  
6.  Die Anwendung im Debugger auszuführen.  
  
7.  Drücken Sie **Button1**.  
  
     Die Anwendung schreibt die folgende Informationen in der Datei der Anwendung debuggen und die Protokolldatei:  
  
     `DefaultSource Start: 4 : Entering Button1_Click`  
  
     `DefaultSource Stop: 5 : Leaving Button1_Click`  
  
8.  Schließen Sie die Anwendung.  
  
9. Ändern Sie den Wert, der die `value` -Attributs zurück in "Information".  
  
    > [!NOTE]
    >  Die `DefaultSwitch` Einstellung steuert nur Schalter `My.Application.Log`. Ändert sich nicht wie die [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)] <xref:System.Diagnostics.Trace?displayProperty=fullName> und <xref:System.Diagnostics.Debug?displayProperty=fullName> Klassen Verhalten.  
  
## <a name="individual-filtering-for-myapplicationlog-listeners"></a>Einzelne Filterung für My.Application.Log-Listener  
 Im vorherige Beispiel veranschaulicht das Ändern der Filterung für alle `My.Application.Log` Ausgabe. In diesem Beispiel wird veranschaulicht, wie einen einzelnen Protokolllistener filtern. Standardmäßig verwendet eine Anwendung zwei Listener, die in die Debugausgabe und die Protokolldatei schreiben.  
  
 Die Konfigurationsdatei steuert das Verhalten der Protokolllistener durch Angabe jeweils einen Filter verfügen, vergleichbar mit einem Switch für `My.Application.Log`. Ein Protokolllistener wird eine Meldung ausgegeben, nur, wenn der Schweregrad der Meldung sowohl das Protokoll zulässig ist `DefaultSwitch` und die Protokolllistener filtern.  
  
 In diesem Beispiel wird veranschaulicht, wie das Konfigurieren der Filterung für einen neuen Debuglistener, und fügen sie der `Log` Objekt. Der Standard-Debug-Listener sollte entfernt werden, aus der `Log` Objekt, damit deutlich wird, dass die Debugmeldungen vom neuen Debuglistener stammen.  
  
#### <a name="to-log-only-activity-tracing-events"></a>Nur aktivitätsablaufverfolgung Ereignisse protokollieren  
  
1.  Mit der rechten Maustaste in "App.config" in der **Projektmappen-Explorer** und wählen Sie **Öffnen**.  
  
     - oder -   
  
     Wenn keine app.config-Datei vorhanden ist:  
  
    1.  Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.  
  
    2.  Wählen Sie im Dialogfeld **Neues Element hinzufügen** den Eintrag **Anwendungskonfigurationsdatei**aus.  
  
    3.  Klicken Sie auf **Hinzufügen**.  
  
2.  Mit der rechten Maustaste in app.config **Projektmappen-Explorer**. Wählen Sie **Öffnen**.  
  
3.  Suchen Sie die `<listeners>` im Abschnitt der `<source>` im Abschnitt mit der `name` -Attribut "DefaultSource" befindet sich unter der `<sources>` Abschnitt. Die `<sources>` Abschnitt befindet sich in der `<system.diagnostics>` in der obersten Ebene im Abschnitt `<configuration>` Abschnitt.  
  
4.  Fügen Sie dieses Element in der `<listeners>` Abschnitt:  
  
    ```xml  
    <!-- Remove the default debug listener. -->  
    <remove name="Default"/>  
    <!-- Add a filterable debug listener. -->  
    <add name="NewDefault"/>  
    ```  
  
5.  Suchen Sie den Abschnitt `<sharedListeners>` im `<system.diagnostics>` -Abschnitt im Abschnitt `<configuration>` der obersten Ebene.  
  
6.  Fügen Sie dem `<sharedListeners>` -Abschnitt dieses Element hinzu:  
  
    ```xml  
    <add name="NewDefault"   
         type="System.Diagnostics.DefaultTraceListener,   
               System, Version=2.0.0.0, Culture=neutral,   
               PublicKeyToken=b77a5c561934e089,   
               processorArchitecture=MSIL">  
        <filter type="System.Diagnostics.EventTypeFilter"   
                initializeData="Error" />  
    </add>  
    ```  
  
     Die <xref:System.Diagnostics.EventTypeFilter> Filter akzeptiert einen von der <xref:System.Diagnostics.SourceLevels> -Enumerationswerte als seine `initializeData` Attribut.  
  
7.  Der Inhalt der app.config-Datei sollte ähnlich dem folgenden XML-Code sein:  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.diagnostics>  
        <sources>  
          <!-- This section configures My.Application.Log -->  
          <source name="DefaultSource" switchName="DefaultSwitch">  
            <listeners>  
              <add name="FileLog"/>  
              <!-- Remove the default debug listener. -->  
              <remove name="Default"/>  
              <!-- Add a filterable debug listener. -->  
              <add name="NewDefault"/>  
            </listeners>  
          </source>  
        </sources>  
        <switches>  
          <add name="DefaultSwitch" value="Information" />  
        </switches>  
        <sharedListeners>  
          <add name="FileLog"  
               type="Microsoft.VisualBasic.Logging.FileLogTraceListener,   
                     Microsoft.VisualBasic, Version=8.0.0.0,   
                     Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a,   
                     processorArchitecture=MSIL"   
               initializeData="FileLogWriter"/>  
          <add name="NewDefault"   
               type="System.Diagnostics.DefaultTraceListener,   
                     System, Version=2.0.0.0, Culture=neutral,   
                     PublicKeyToken=b77a5c561934e089,   
                     processorArchitecture=MSIL">  
            <filter type="System.Diagnostics.EventTypeFilter"   
                    initializeData="Error" />  
          </add>  
        </sharedListeners>  
      </system.diagnostics>  
    </configuration>  
    ```  
  
8.  Die Anwendung im Debugger auszuführen.  
  
9. Drücken Sie **Button1**.  
  
     Die Anwendung schreibt die folgende Informationen in der Anwendung-Protokolldatei:  
  
     `Default Information: 0 : In Button1_Click`  
  
     `Default Error: 2 : Error in the application.`  
  
     Die Anwendung schreibt weniger Informationen in die Debugausgabe aufgrund der restriktiveren Filterung.  
  
     `Default Error   2   Error`  
  
10. Schließen Sie die Anwendung.  
  
 Weitere Informationen zum Ändern der Einstellungen für nach der Bereitstellung finden Sie unter [Arbeiten mit Anwendungsprotokollen](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Exemplarische Vorgehensweise: Bestimmen, wohin "My.Application.log" Informationen schreibt](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)   
 [Exemplarische Vorgehensweise: Ändern, wohin "My.Application.log" Informationen schreibt](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)   
 [Exemplarische Vorgehensweise: Erstellen von benutzerdefinierten Protokolllistenern](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-creating-custom-log-listeners.md)   
 [Gewusst wie: Schreiben von Protokollmeldungen](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)   
 [Trace-Schalter](../Topic/Trace%20Switches.md)   
 [Protokollieren von Informationen aus der Anwendung](../../../../visual-basic/developing-apps/programming/log-info/logging-information-from-the-application.md)