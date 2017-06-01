---
title: "Verwenden der InvokePowerShell-Aktivit&#228;t | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 956251a0-31ca-4183-bf76-d277c08585df
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Verwenden der InvokePowerShell-Aktivit&#228;t
Im InvokePowerShell\-Beispiel wird veranschaulicht, wie Windows PowerShell\-Befehle mit der `InvokePowerShell`\-Aktivität aufgerufen werden.  
  
## Veranschaulicht  
  
-   Einfache Innovation von Windows PowerShell\-Befehlen.  
  
-   Rufen Sie Werte aus der Windows PowerShell\-Ausgabepipeline ab, und speichern Sie diese in Workflowvariablen.  
  
-   Übergeben Sie Daten an Windows PowerShell als Eingabepipeline für einen Ausführungsbefehl.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Überprüfen Sie das folgende \(standardmäßige\) Verzeichnis, bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\PowerShell`  
  
## Diskussion  
 Dieses Beispiel enthält die folgenden drei Projekte.  
  
|Projektname|Beschreibung|Hauptdateien|  
|-----------------|------------------|------------------|  
|CodedClient|Eine Beispielclientanwendung, die die PowerShell\-Aktivität verwendet.|-   **Program.cs**: Erstellt programmgesteuert einen sequenzbasierten Workflow, der die InvokePowerShell\-Aktivität aufruft.|  
|DesignerClient|Ein Satz benutzerdefinierter Aktivitäten, die die benutzerdefinierte Aktivität `InvokePowerShell` und weitere benutzerdefinierte Aktivitäten sowie einen Workflow, der sie verwendet, enthalten.|<ul><li>Aktivitäten:<br /><br /> <ul><li>**PrintCollection.cs**: Eine Hilfsaktivität, die alle Elemente in einer Auflistung zur Konsole druckt.</li><li>**ReadLine.cs**: Eine Hilfsaktivität zum Lesen von Eingaben über die Konsole.</li></ul></li><li>Dateisystem:<br /><br /> <ul><li>**Copy.xaml**: Eine Aktivität, die eine Datei kopiert.</li><li>**CreateFile.xaml**: Eine Aktivität, die eine Datei erstellt.</li><li>**DeleteFile.xaml**: Eine Aktivität, die eine Datei löscht.</li><li>**MakeDir.xaml**: Eine Aktivität, die ein Verzeichnis erstellt.</li><li>**Move.xaml**: Eine Aktivität, die eine Datei verschiebt.</li><li>**ReadFile.xaml**: Eine Aktivität, die eine Datei liest und ihren Inhalt zurückgibt.</li><li>**TestPath.xaml**: Eine Aktivität, die das Vorhandensein eines Pfads überprüft.</li></ul></li><li>Prozess:<br /><br /> <ul><li>**GetProcess.xaml**: Eine Aktivität, die eine Liste von laufenden Prozessen abruft.</li><li>**StopProcess.xaml**: Eine Aktivität, die einen bestimmten Prozess beendet.</li></ul></li><li>**Program.cs**: Ruft den Sequence1\-Workflow auf.</li><li>**Sequence1.xaml**: Ein sequenzbasierter Workflow.</li></ul>|  
|PowerShell|Die `InvokePowerShell`\-Aktivität und ihre zugeordneten Designer.|Aktivitätsdateien<br /><br /> -   **ExecutePowerShell.cs**: Die Hauptausführungslogik der Aktivität.<br />-   **InvokePowerShell.cs**: Der Wrapper um die Hauptausführungslogik, die eine generische Version \(Rückgabewert\) und eine nicht generische Version \(nicht\-Rückgabewert\) enthält.Dies ist die öffentliche Schnittstelle für die Aktivität.<br />-   **NoPersistZone.cs**: Diese Aktivität verhindert, dass alle untergeordneten Aktivitäten erhalten bleiben.Diese Klasse wird in der Implementierung der `InvokePowerShell`\-Aktivität verwendet, um zu verhindern, dass die Aktivität mitten in der Ausführung beibehalten wird.<br /><br /> Designerdateien:<br /><br /> 1.  **ArgumentDictionaryEditor.cs**: Ein Windows\-Dialogfeld, das dem Benutzer ermöglicht, die Argumente der `InvokePowerShell`\-Aktivität zu bearbeiten.<br />2.  **GenericInvokePowerShellDesigner.xaml** und **GenericInvokePowerShellDesigner.xaml.cs**: Definiert die Darstellung der generischen `InvokePowerShell`\-Aktivität in [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].<br />3.  **InvokePowerShellDesigner.xaml** und **InvokePowerShellDesigner.cs**: Definiert die Darstellung der nicht generischen `InvokePowerShell`\-Aktivität in [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].|  
  
 Die Clientprojekte werden zuerst erläutert, da es einfacher ist, die interne Funktionalität der PowerShell\-Aktivität zu verstehen, nachdem ihre Verwendung verstanden wurde.  
  
## Verwenden dieses Beispiels  
 In den folgenden Abschnitten wird beschrieben, wie die drei Projekte im Beispiel verwendet werden.  
  
### Verwenden des codierten Clientprojekts  
 Der Beispielclient erstellt programmgesteuert eine Sequenzaktivität, die Beispiele für mehrere verschiedene Methoden für die Verwendung der `InvokePowerShell`\-Aktivität enthält.Mit dem ersten Aufruf wird der Editor gestartet.  
  
```  
new InvokePowerShell()  
{  
    CommandText = "notepad"  
},  
  
```  
  
 Der zweite Aufruf ruft eine Liste der Prozesse ab, die auf dem lokalen Computer ausgeführt werden.  
  
```  
new InvokePowerShell<Process>()  
{  
    CommandText = "Get-Process",  
    Output = processes1,  
},  
  
```  
  
 `Output` ist die Variable, die zum Speichern der Ausgabe des Befehls verwendet wird.  
  
 Der nächste Aufruf veranschaulicht, wie ein Nachverarbeitungsschritt für jede einzelne Ausgabe des PowerShell\-Aufrufs ausgeführt wird.Für `InitializationAction` wird die Funktion festgelegt, die eine Zeichenfolgendarstellung für die einzelnen Prozesse ausgibt.Die Auflistung dieser Zeichenfolgen wird in der `Output`\-Variablen von der `InvokePowerShell<string>`\-Aktivität zurückgegeben.  
  
 Die erfolgreichen `InvokePowerShell`\-Aufrufe veranschaulichen das Übergeben von Daten an die Aktivität und Abrufen von Ausgaben und Fehlern.  
  
### Verwenden des Designerclientprojekts  
 Das DesignerClient\-Projekt besteht aus einem Satz benutzerdefinierter Aktivitäten, die fast alle die `InvokePowerShell`\-Aktivität enthalten.Die meisten der Aktivitäten rufen die nicht generische Version der `InvokePowerShell`\-Aktivität auf und erwarten keinen Rückgabewert.Andere Aktivitäten verwenden die generische Version der `InvokePowerShell`\-Aktivität und verwenden das `InitializationAction`\-Argument für die Nachverarbeitung der Ergebnisse.  
  
## Verwenden des PowerShell\-Projekts  
 Die Hauptaktion der Aktivität findet in der `ExecutePowerShell`\-Klasse statt.Da die Ausführung von PowerShell\-Befehlen den Hauptworkflowthread nicht blockieren sollte, wird die Aktivität als asynchrone Aktivität erstellt, indem sie von der <xref:System.Activities.AsyncCodeActivity>\-Klasse erbt.  
  
 Die <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A>\-Methode wird von der Workflowlaufzeit aufgerufen, um mit der Ausführung der Aktivität zu beginnen.Sie beginnt mit dem Aufruf von PowerShell\-APIs zum Erstellen einer PowerShell\-Pipeline.  
  
```  
runspace = RunspaceFactory.CreateRunspace();  
runspace.Open();  
pipeline = runspace.CreatePipeline();  
  
```  
  
 Anschließend erstellt sie einen PowerShell\-Befehl und füllt ihn mit Parametern und Variablen.  
  
```  
Command cmd = new Command(this.CommandText, this.IsScript);   
// loop over parameters and run: cmd.Parameters.Add(...)  
// loop over variables and run: runspace.SessionStateProxy.SetVariable(...)  
pipeline.Commands.Add(cmd);  
  
```  
  
 Die über die Pipeline übergebenen Eingaben werden an diesem Punkt ebenfalls an die Pipeline gesendet.Zum Schluss wird die Pipeline mit einem `PipelineInvokerAsyncResult`\-Objekt als Wrapper versehen und zurückgegeben.Das `PipelineInvokerAsyncResult`\-Objekt registriert einen Listener und ruft die Pipeline auf.  
  
```  
pipeline.InvokeAsync();  
  
```  
  
 Nach dem Beenden der Ausführung werden die Ausgabe und Fehler in demselben `PipelineInvokerAsyncResult`\-Objekt gespeichert. Die Workflowlaufzeit erlangt wieder die Steuerung, indem die ursprünglich an <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> übergebene Rückrufmethode aufgerufen wird.  
  
 Bei Ende der Methodenausführung ruft die Workflowlaufzeit die <xref:System.Activities.AsyncCodeActivity.EndExecute%2A>\-Methode der Aktivität auf.  
  
 Die `InvokePowerShell`\-Klasse fungiert als Wrapper der `ExecutePowerShellCommand`\-Klasse und erstellt zwei Versionen der Aktivität, eine generische Version und eine nicht generische Version.Die nicht generische Version gibt die Ausgabe der PowerShell\-Ausführung direkt zurück, wohingegen die generische Version die einzelnen Ergebnisse in den generischen Typ transformiert.  
  
 Die generische Version der Aktivität wird als sequenzieller Workflow implementiert, der `ExecutePowerShellCommand` aufruft und die Ergebnisse nachverarbeitet.Für jedes Element in der Ergebnisauflistung ruft der Nachverarbeitungsschritt `InitializationAction` auf, wenn dies festgelegt ist.Andernfalls wird eine einfache Umwandlung ausgeführt.  
  
```  
new ForEach<PSObject>  
{  
    Values = psObjects,  
    Body = new ActivityAction<PSObject>  
    {  
        Argument = psObject,  
        Handler = new Sequence  
        {  
            Activities =  
            {  
                new If  
                {  
                    Condition = // Is InitializationAction set?  
                    Then = new InvokeFunc<PSObject, TResult>  
                    {  
                        Argument = psObject,  
                        Result = outputObject,  
                        Func = this.InitializationAction  
                    },  
                    Else = new Assign<TResult>  
                    {  
                        To = outputObject,  
                        Value = new InArgument<TResult>(ctx => (TResult) psObject.Get(ctx).BaseObject),  
                    }  
                },  
                new AddToCollection<TResult>  
                {  
                    Collection = outputObjects,  
                    Item = outputObject  
                },  
            }  
        }  
    }  
},  
  
```  
  
 Für jede der beiden `InvokePowerShell`\-Aktivitäten \(generisch und nicht generisch\) wurde ein Designer erstellt.InvokePowerShellDesigner.xaml und die entsprechende CS\-Datei definieren die Darstellung in [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)] für die nicht generische Version der `InvokePowerShell`\-Aktivität.In InvokePowerShellDesigner.xaml wird ein <xref:System.Windows.Controls.DockPanel> verwendet, um die grafische Schnittstelle darzustellen.  
  
```  
<DockPanel x:Uid="DockPanel_1" LastChildFill="True">  
        <TextBlock x:Uid="TextBlock_1" Text="CommandText" />  
        <TextBox x:Uid="TextBox_1" Text="{Binding Path=ModelItem.CommandText, Mode=TwoWay}"  
                 TextWrapping="WrapWithOverflow"  AcceptsReturn="True" MinLines="4" MaxLines="4"  
                 Background="{x:Null}" Margin="3" />  
    </DockPanel>  
  
```  
  
 Beachten Sie, dass die `Text`\-Eigenschaft des Textfelds eine bidirektionale Bindung ist, die sicherstellt, dass der Wert der `CommandText`\-Eigenschaft der Aktivität dem im Designer eingegebenen Wert entspricht.  
  
 GenericInvokePowerShellDesigner.xaml und die entsprechende CS\-Datei definieren die grafische Schnittstelle für die generische `InvokePowerShell`\-Aktivität.Der Designer ist etwas komplizierter, da er Benutzern ermöglicht, eine `InitializationAction` festzulegen.Das Schlüsselelement ist die Verwendung von <xref:System.Activities.Presentation.WorkflowItemPresenter>, wodurch das Ziehen und Ablegen untergeordneter Aktivitäten in die `InvokePowerShell`\-Designer Oberfläche ermöglicht wird.  
  
```  
<sap:WorkflowItemPresenter x:Uid="sap:WorkflowItemPresenter_1" Margin="0,10,0,10"  
    HintText="Drop Activities Here"  
    AllowedItemType="{x:Type sa:Activity}"  
    Item="{Binding Path=ModelItem.InitializationAction.Handler, Mode=TwoWay}"  
    Grid.Row="1" Grid.Column="1" />  
  
```  
  
 Die Designeranpassung hört nicht mit den XAML\-Dateien auf, die die Darstellung der Aktivität im Zeichenbereich definieren.Die Dialogfelder, die zum Anzeigen der Parameter der Aktivität verwendet werden, können ebenfalls angepasst werden.Diese Parameter und PowerShell\-Variablen wirken sich auf das Verhalten von PowerShell\-Befehlen aus.Die Aktivität macht sie als <xref:System.Collections.Generic.Dictionary%601>\-Typen verfügbar.Mit ArgumentDictionaryEditor.cs, PropertyEditorResources.xaml und PropertyEditorResources.cs wird das Dialogfeld definiert, das Ihnen ermöglicht, diese Typen zu bearbeiten.  
  
## So richten Sie das Beispiel ein, erstellen es und führen es aus  
 Sie müssen Windows PowerShell installieren, um dieses Beispiel ausführen zu können.Windows PowerShell kann von diesem Speicherort aus installiert werden: [Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=150383).  
  
#### So führen Sie den kodierten Client aus  
  
1.  Öffnen Sie PowerShell.sln mit [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Klicken Sie mit der rechten Maustaste auf die Projektmappe, und erstellen Sie sie.  
  
3.  Klicken Sie mit der rechten Maustaste auf das **CodedClient**\-Projekt, und wählen Sie **Als Startprojekt festlegen** aus.  
  
4.  Drücken Sie STRG\+F5, um die Anwendung auszuführen.  
  
#### So führen Sie den Designerclient aus  
  
1.  Öffnen Sie PowerShell.sln mit [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Klicken Sie mit der rechten Maustaste auf die Projektmappe, und erstellen Sie sie.  
  
3.  Klicken Sie mit der rechten Maustaste auf das **DesignerClient**\-Projekt, und wählen Sie **Als Startprojekt festlegen** aus.  
  
4.  Drücken Sie STRG\+F5, um die Anwendung auszuführen.  
  
## Bekannte Probleme  
  
1.  Wenn das Verweisen auf die `InvokePowerShell`\-Aktivitätsassembly oder das Projekt von einem anderen Projekt zu einem Buildfehler führt, müssen Sie das `<SpecificVersion>True</SpecificVersion>`\-Element möglicherweise manuell der CSPROJ\-Datei des neuen Projekts unter der Zeile, die auf `InvokePowerShell` verweist, hinzufügen.  
  
2.  Wenn Windows PowerShell nicht installiert ist, wird die folgende Fehlermeldung in Visual Studio angezeigt, sobald Sie einem Workflow eine `InvokePowerShell`\-Aktivität hinzufügen: `In Workflow Designer wurden Probleme mit dem Dokument erkannt. Die Datei oder Assembly 'System.Management.Automation' oder eine ihrer Abhängigkeit konnte nicht geladen werden. Das System konnte die angegebene Datei nicht finden.`  
  
3.  In Windows PowerShell 2.0 schlägt das programmgesteuerte Aufrufen von `$input.MoveNext()` fehl, und Skripte, die `$input.MoveNext()` verwenden, führen zu unbeabsichtigten Fehlern und Ergebnissen.Um dieses Problem zu vermeiden, ziehen Sie die Verwendung des PowerShell\-Verbs `foreach` in Betracht, anstatt bei der Wiederholung eines Arrays `MoveNext()` aufzurufen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Überprüfen Sie das folgende \(standardmäßige\) Verzeichnis, bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\PowerShell`  
  
## Siehe auch