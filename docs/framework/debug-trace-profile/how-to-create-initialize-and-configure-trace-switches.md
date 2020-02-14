---
title: 'Gewusst wie: Erstellen, Initialisieren und Konfigurieren von Ablaufverfolgungsschaltern'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- trace switches, configuring
- tracing [.NET Framework], trace switches
- switches, trace
- tracing [.NET Framework], enabling or disabling
- Web.config configuration file, trace switches
ms.assetid: 5a0e41bf-f99c-4692-8799-f89617f5bcf9
ms.openlocfilehash: 358e34b2ce5d896ba02b343ce060604f2d42eeeb
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216474"
---
# <a name="how-to-create-initialize-and-configure-trace-switches"></a>Gewusst wie: Erstellen, Initialisieren und Konfigurieren von Ablaufverfolgungsschaltern
Mit Ablaufverfolgungsschaltern können Sie die Ablaufverfolgungsausgabe aktivieren, deaktivieren und filtern.  
  
<a name="create"></a>   
## <a name="creating-and-initializing-a-trace-switch"></a>Erstellen und Initialisieren eines Ablaufverfolgungsschalters  
 Damit Sie Ablaufverfolgungsschalter verwenden können, müssen Sie diese zunächst erstellen und in Ihrem Code platzieren. Es gibt zwei vordefinierte Klassen, aus denen Sie Schalterobjekte erstellen können: die <xref:System.Diagnostics.BooleanSwitch?displayProperty=nameWithType>-Klasse und die <xref:System.Diagnostics.TraceSwitch?displayProperty=nameWithType>-Klasse. Sie verwenden die <xref:System.Diagnostics.BooleanSwitch>-Klasse, wenn Sie nur wissen möchten, ob eine Ablaufverfolgungsmeldung angezeigt oder wird oder nicht. <xref:System.Diagnostics.TraceSwitch> verwenden Sie, wenn Sie zwischen Ebenen für die Ablaufverfolgung unterscheiden möchten. Wenn Sie eine <xref:System.Diagnostics.TraceSwitch>-Instanz verwenden, können Sie eigene Debugmeldungen definieren und diese verschiedenen Ablaufverfolgungsebenen zuordnen. Sie können beide Typen von Schaltern mit Ablaufverfolgung oder Debuggen verwenden. In der Standardeinstellung ist ein <xref:System.Diagnostics.BooleanSwitch> deaktiviert und ein <xref:System.Diagnostics.TraceSwitch> auf die Ebene <xref:System.Diagnostics.TraceLevel.Off?displayProperty=nameWithType> festgelegt. Ablaufverfolgungsschalter können in jedem beliebigen Teil Ihres Codes erstellt und platziert werden, in dem sie möglicherweise verwendet werden.  
  
 Obwohl Sie Ablaufverfolgungsebenen und weitere Konfigurationsoptionen in Code festlegen können, empfiehlt es sich, dass Sie die Konfigurationsdatei verwenden, um den Zustand Ihrer Schalter zu verwalten. Grund hierfür ist, dass Sie flexibler sind, wenn Sie die Konfiguration Ihrer Schalter im Konfigurationssystem verwalten, denn Sie können verschiedene Schalter und Änderungsebenen ein-und ausschalten, ohne Ihre Anwendung erneut zu kompilieren.  
  
#### <a name="to-create-and-initialize-a-trace-switch"></a>So erstellen und initialisieren Sie einen Ablaufverfolgungsschalter  
  
1. Definieren Sie einen Schalter entweder mit dem Typ <xref:System.Diagnostics.BooleanSwitch?displayProperty=nameWithType> oder mit dem Typ <xref:System.Diagnostics.TraceSwitch?displayProperty=nameWithType>, und legen Sie den Namen und die Beschreibung des Schalters fest.  
  
2. Konfigurieren Sie Ihren Ablaufverfolgungsschalter. Weitere Informationen finden Sie unter [Konfigurieren von Ablaufverfolgungsschaltern](#configure).  
  
     Im folgenden Code werden zwei Schalter erstellt, jeweils ein Schalter jedes Typs:  
  
    ```vb  
    Dim dataSwitch As New BooleanSwitch("Data", "DataAccess module")  
    Dim generalSwitch As New TraceSwitch("General", "Entire application")  
    ```  
  
    ```csharp  
    System.Diagnostics.BooleanSwitch dataSwitch =   
       new System.Diagnostics.BooleanSwitch("Data", "DataAccess module");  
    System.Diagnostics.TraceSwitch generalSwitch =   
       new System.Diagnostics.TraceSwitch("General",   
       "Entire application");  
    ```  
  
<a name="configure"></a>   
## <a name="configuring-trace-switches"></a>Konfigurieren von Ablaufverfolgungsschaltern  
 Nachdem Ihre Anwendung bereitgestellt wurde, können weiterhin Ablaufverfolgungsausgabe aktivieren oder deaktivieren, indem Sie die Ablaufverfolgungsschalter in der Anwendung konfigurieren. Konfigurieren eines Schalters bedeutet, dass sein Wert aus einer externen Quelle geändert wird, nachdem er initialisiert wurde. Sie können die Werte der Schalterobjekte mithilfe der Konfigurationsdatei ändern. Sie konfigurieren einen Ablaufverfolgungsschalter so, dass er aktiviert oder deaktiviert oder dass seine Ebene festgelegt wird. Dabei bestimmen Sie den Umfang und die Art der Meldungen, die der Schalter an Listener weiterleitet.  
  
 Ihre Schalter werden über die .config-Datei konfiguriert. Für eine Webanwendung ist dies die "Web.config"-Datei, die dem Projekt zugeordnet ist. In einer Windows-Anwendung heißt diese Datei (Anwendungsname). exe. config. In einer bereitgestellten Anwendung muss sich diese Datei im selben Ordner befinden wie die ausführbare Datei.  
  
 Wenn die Anwendung den Code, der eine Instanz eines Schalters erstellt, zum ersten Mal ausführt, prüft sie die Konfigurationsdatei auf Ablaufverfolgungsebenen-Informationen zu dem angegebenen Schalter. Das Ablaufverfolgungssystem durchsucht die Konfigurationsdatei für jeden Schalter nur ein Mal – wenn die Anwendung den Schalter erstmalig erstellt.  
  
 In einer bereitgestellten Anwendung aktivieren Sie Ablaufverfolgungscode, indem Sie Schalterobjekte neu konfigurieren, wenn die Anwendung nicht ausgeführt wird. Üblicherweise gehört hierzu Aktivieren oder Deaktivieren der Schalterobjekte oder Ändern der Ablaufverfolgungsebenen und dann Neustarten Ihrer Anwendung.  
  
 Wenn Sie eine Instanz eines Schalters erstellen, initialisieren Sie diesen auch, indem Sie zwei Argumente angeben: ein *displayName*-Argument und ein *description*-Argument. Das *displayName*-Argument des Konstruktors legt die <xref:System.Diagnostics.Switch.DisplayName%2A?displayProperty=nameWithType>-Eigenschaft der <xref:System.Diagnostics.Switch>-Klasseninstanz fest. Der *displayName* ist der Name, der verwendet wird, um den Schalter in der CONFIG-Datei zu konfigurieren, und das *description*-Argument sollte eine kurze Beschreibung des Schalters sowie die Information zurückgeben, welche Meldungen er steuert.  
  
 Zusätzlich zum Angeben des Namens eines Schalters, der konfiguriert werden soll, müssen Sie auch einen Wert für den Schalter angeben. Dieser Wert ist eine ganze Zahl. Für <xref:System.Diagnostics.BooleanSwitch> entspricht der Wert 0 **Deaktiviert**, und ein Wert ungleich 0 entspricht **Aktiviert**. Für <xref:System.Diagnostics.TraceSwitch> entsprechen 0,1,2,3 bzw. 4 **Deaktiviert**, **Fehler**, **Warnung**, **Info** bzw. **Ausführlich**. Jede Zahl, die größer als 4 ist, wird als **Ausführlich**, und jede Anzahl, die kleiner als 0 ist, wird als **Deaktiviert** angesehen.  
  
> [!NOTE]
> In .NET Framework 2.0 können Sie Text verwenden, um den Wert eines Schalters anzugeben. Beispielsweise `true` für einen <xref:System.Diagnostics.BooleanSwitch> oder den Text, der einem Enumerationswert entspricht, etwa `Error`, für einen <xref:System.Diagnostics.TraceSwitch>. Die Zeile `<add name="myTraceSwitch" value="Error" />` ist gleichbedeutend mit `<add name="myTraceSwitch" value="1" />`.  
  
 Damit Endbenutzer die Möglichkeit haben, die Ablaufverfolgungsschalter einer Anwendung konfigurieren zu können, müssen Sie eine detaillierte Dokumentation zu den Schaltern in Ihrer Anwendung bereitstellen. Sie sollten ausführlich beschreiben, welche Schalter welche Vorgänge steuern und wie die Schalter aktiviert und deaktiviert werden. Außerdem sollten Sie Ihren Endbenutzern eine .config-Datei bereitstellen, die entsprechende Hilfen in den Kommentaren enthält.  
  
#### <a name="to-configure-trace-switches"></a>So konfigurieren Sie Ablaufverfolgungsschalter  
  
1. Um Ablaufverfolgungsschalter zu verwenden, müssen Sie diese zuerst erstellen und sie, wie im Abschnitt [Erstellen und Initialisieren eines Ablaufverfolgungsschalters](#create) beschrieben, in Ihrem Code platzieren.  
  
2. Enthält Ihr Projekt keine Konfigurationsdatei („app.config“ oder „Web.config“), dann wählen Sie im Menü **Projekt** den Befehl **Neues Element hinzufügen** aus.  
  
    - **Visual Basic:** Klicken Sie im Dialogfeld **Neues Element hinzufügen** auf **Anwendungskonfigurationsdatei**.  
  
         Die Anwendungskonfigurationsdatei wird erstellt und geöffnet. Diese Datei ist ein XML-Dokument mit dem Stammelement `<configuration>.`  
  
    - **Visual C#:** Klicken Sie im Dialogfeld **Neues Element hinzufügen** auf **XML-Datei**. Nennen Sie diese Datei **app. config**. Fügen Sie im XML-Editor nach der XML-Deklaration den folgenden XML-Code hinzu:  
  
        ```xml  
        <configuration>  
        </configuration>  
        ```  
  
         Nachdem das Projekt kompiliert ist, wird die Datei „app.config“ in den Projektausgabeordner kopiert und in „*Anwendungsname*.exe.config“ umbenannt.  
  
3. Fügen Sie nach dem `<configuration>`-Tag, aber vor dem `</configuration>`-Tag, die entsprechende XML ein, um die Schalter zu konfigurieren. In den folgenden Beispielen werden ein **BooleanSwitch** mit einer **DisplayName**-Eigenschaft von `DataMessageSwitch` und ein **TraceSwitch** mit einer **DisplayName**-Eigenschaft von `TraceLevelSwitch` veranschaulicht.  
  
    ```xml  
    <system.diagnostics>  
       <switches>  
          <add name="DataMessagesSwitch" value="0" />  
          <add name="TraceLevelSwitch" value="0" />  
       </switches>  
    </system.diagnostics>  
    ```  
  
     In dieser Konfiguration sind beide Schalter deaktiviert.  
  
4. Wenn Sie einen **BooleanSwitch**, wie `DataMessagesSwitch` im vorhergehenden Beispiel, aktivieren möchten, ändern Sie den **Wert** in eine beliebige ganze Zahl ungleich 0.  
  
5. Wenn Sie einen **TraceSwitch**, wie `TraceLevelSwitch` im vorhergehenden Beispiel, aktivieren möchten, ändern Sie den **Wert** in die entsprechende Ebeneneinstellung (1 bis 4).  
  
6. Fügen Sie der .config-Datei Kommentare hinzu , damit der Benutzer genau weiß, welche Werte geändert werden müssen, damit die Schalter geeignet konfiguriert sind.  
  
     Im folgenden Beispiel wird gezeigt, wie der endgültige Code einschließlich der Kommentare aussehen könnte:  
  
    ```xml  
    <system.diagnostics>  
       <switches>  
          <!-- This switch controls data messages. In order to receive data   
             trace messages, change value="0" to value="1" -->  
          <add name="DataMessagesSwitch" value="0" />  
          <!-- This switch controls general messages. In order to   
             receive general trace messages change the value to the   
             appropriate level. "1" gives error messages, "2" gives errors   
             and warnings, "3" gives more detailed error information, and   
             "4" gives verbose trace information -->  
          <add name="TraceLevelSwitch" value="0" />  
       </switches>  
    </system.diagnostics>  
    ```  
  
## <a name="see-also"></a>Weitere Informationen

- [Ablaufverfolgung und Instrumentieren von Anwendungen](tracing-and-instrumenting-applications.md)
- [Vorgehensweise: Hinzufügen von Ablaufverfolgungsanweisungen zu Anwendungscode](how-to-add-trace-statements-to-application-code.md)
- [Ablaufverfolgungsschalter](trace-switches.md)
- [Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)](../configure-apps/file-schema/trace-debug/index.md)
