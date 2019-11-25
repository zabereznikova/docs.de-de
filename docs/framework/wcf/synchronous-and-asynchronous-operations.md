---
title: Synchrone und asynchrone Vorgänge
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], synchronous operations
- service contracts [WCF], asynchronous operations
ms.assetid: db8a51cb-67e6-411b-9035-e5821ed350c9
ms.openlocfilehash: 39a7db3fb7dc3651f2cf6c850e7ebb5525e24963
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74281633"
---
# <a name="synchronous-and-asynchronous-operations"></a>Synchrone und asynchrone Vorgänge
In diesem Thema werden das Implementieren und das Aufrufen asynchroner Dienstvorgänge erörtert.  
  
 Viele Anwendungen rufen Methoden asynchron auf, weil dadurch die Anwendung beim Methodenaufruf weiter nützliche Arbeiten ausführen kann. Windows Communication Foundation-Dienste und -Clients (WCF) können an Aufrufen asynchroner Vorgänge auf zwei unterschiedlichen Anwendungsebenen teilnehmen, was WCF-Anwendungen noch mehr Flexibilität bietet, um den Durchsatz unter Abwägung der Interaktivität zu maximieren.  
  
## <a name="types-of-asynchronous-operations"></a>Typen asynchroner Vorgänge  
 Alle Dienstverträge in WCF verwenden unabhängig von den Parametertypen und Rückgabewerten WCF-Attribute zum Angeben eines bestimmten Musters für den Nachrichtenaustausch zwischen Client und Dienst. WCF leitet automatisch eingehende und ausgehende Nachrichten an den entsprechenden Dienstvorgang oder ausgeführten Clientcode weiter.  
  
 Der Client verfügt nur über den Dienstvertrag, der das Nachrichtenaustauschmuster für einen bestimmten Vorgang angibt. Clients können dem Entwickler ein beliebiges Programmiermodell anbieten, solange das zugrunde liegende Nachrichtenaustauschmuster eingehalten wird. Ebenso können Dienste Vorgänge auf beliebige Weise implementieren, solange das angegebene Nachrichtenmuster eingehalten wird.  
  
 Die Unabhängigkeit des Dienstvertrags von der Dienst- oder Clientimplementierung ermöglicht die folgenden Formen asynchroner Ausführung in WCF-Anwendungen:  
  
- Clients können Anforderungs-/Antwortvorgänge mit einem synchronen Nachrichtenaustausch asynchron aufrufen.  
  
- Clients können asynchrone Anforderungs-/Antwortvorgänge mit einem synchronen Nachrichtenaustausch implementieren.  
  
- Ein Nachrichtenaustausch kann unidirektional sein, unabhängig von der Implementierung des Clients oder Dienstes.  
  
### <a name="suggested-asynchronous-scenarios"></a>Vorgeschlagene asynchrone Szenarien  
 Verwenden Sie den asynchronen Ansatz in der Implementierung eines Dienstvorgangs, wenn dieser Dienstvorgang blockierende Aufrufe, beispielsweise E/A-Vorgänge, vornimmt. Bei der Implementierung eines asynchronen Vorgangs sollten Sie versuchen, asynchrone Vorgänge und Methoden aufzurufen, um den asynchronen Aufrufpfad so weit wie möglich zu erweitern. Rufen Sie z.&#160;B. innerhalb von `BeginOperationTwo()``BeginOperationOne()` auf.  
  
- Verwenden Sie in den folgenden Fällen einen asynchronen Ansatz in einem Client oder in einer aufrufenden Anwendung:  
  
- Wenn Sie Vorgänge von einer Anwendung der mittleren Ebene aufrufen. (Weitere Informationen zu solchen Szenarien finden Sie unter [Clientanwendungen mittlerer Ebene](./feature-details/middle-tier-client-applications.md).)  
  
- Verwenden Sie asynchrone Seiten, wenn Sie Vorgänge innerhalb einer ASP.NET-Seite aufrufen.  
  
- Wenn Sie Vorgänge von einer Singlethread-Anwendung aufrufen, etwa einer Windows Forms- oder Windows Presentation Foundation-Anwendung (WPF). Bei Verwendung des ereignisgesteuerten asynchronen Aufrufmodells wird das resultierende Ereignis im UI-Thread ausgelöst. Dies erhöht die Ansprechempfindlichkeit der Anwendung gegenüber Benutzeraktivitäten, ohne dass Sie selbst mehrere Threads verwalten müssen.  
  
- Im Allgemeinen gilt: Haben Sie die Wahl zwischen einem synchronen oder einem asynchronen Aufruf, dann wählen Sie den asynchronen Aufruf.  
  
### <a name="implementing-an-asynchronous-service-operation"></a>Implementieren eines asynchronen Dienstvorgangs  
 Asynchrone Vorgänge können auf eine der drei folgenden Arten implementiert werden:  
  
1. Das aufgabenbasierte asynchrone Muster  
  
2. Das ereignisbasierte asynchrone Muster  
  
3. Das asynchrone IAsyncResult-Muster  
  
#### <a name="task-based-asynchronous-pattern"></a>Taskbasiertes asynchrones Muster  
 Das aufgabenbasierte asynchrone Muster ist die bevorzugte Methode zum Implementieren asynchroner Vorgänge, weil es einfach und verständlich ist. Um diese Methode zu verwenden, implementieren Sie einfach den Dienstvorgang, und geben Sie den Rückgabetyp Task\<T> an, wobei T der Typ ist, der von der logischen Operation zurückgegeben wird. Zum Beispiel:  
  
```csharp  
public class SampleService:ISampleService   
{   
   // ...  
   public async Task<string> SampleMethodTaskAsync(string msg)   
   {   
      return Task<string>.Factory.StartNew(() =>   
      {   
         return msg;   
      });   
   }  
   // ...  
}  
```  
  
 Der SampleMethodTaskAsync-Vorgang gibt Task\<string> zurück, da die logische Operation eine Zeichenfolge zurückgibt. Weitere Informationen über das taskbasierte asynchrone Muster finden Sie unter [Taskbasiertes asynchrones Muster](https://go.microsoft.com/fwlink/?LinkId=232504).  
  
> [!WARNING]
> Bei Verwendung des taskbasierten asynchronen Musters kann bei einer Ausnahme eine {1}T:System.AggregateException{2} ausgelöst werden, während auf den Abschluss des Vorgangs gewartet wird. Diese Ausnahme kann für Clients oder Dienste auftreten.  
  
#### <a name="event-based-asynchronous-pattern"></a>Ereignisbasiertes asynchrones Muster  
 Ein Dienst, der das ereignisbasierte asynchrone Muster unterstützt, verfügt über einen oder mehrere Vorgänge mit dem Namen {1}MethodNameAsync{2}. Diese Methoden spiegeln möglicherweise synchrone Versionen wider, die denselben Vorgang im aktuellen Thread durchführen. Die Klasse kann darüber hinaus auch über ein MethodNameCompleted-Ereignis und eine MethodNameAsyncCancel-Methode (kurz {1}CancelAsync{2}) verfügen. Ein Client, der den Vorgang aufrufen möchte, definiert einen Ereignishandler, der bei Abschluss des Vorgangs aufgerufen wird.  
  
 Der folgende Codeausschnitt veranschaulicht, wie asynchrone Vorgänge unter Verwendung des ereignisbasierten asynchronen Musters deklariert werden.  
  
```csharp  
public class AsyncExample  
{  
    // Synchronous methods.  
    public int Method1(string param);  
    public void Method2(double param);  
  
    // Asynchronous methods.  
    public void Method1Async(string param);  
    public void Method1Async(string param, object userState);  
    public event Method1CompletedEventHandler Method1Completed;  
  
    public void Method2Async(double param);  
    public void Method2Async(double param, object userState);  
    public event Method2CompletedEventHandler Method2Completed;  
  
    public void CancelAsync(object userState);  
  
    public bool IsBusy { get; }  
  
    // Class implementation not shown.  
}  
```  
  
 Weitere Informationen über das ereignisbasierte asynchrone Muster finden Sie unter [Übersicht über ereignisbasierte asynchrone Muster](https://go.microsoft.com/fwlink/?LinkId=232515).  
  
#### <a name="iasyncresult-asynchronous-pattern"></a>Das asynchrone IAsyncResult-Muster  
 Ein Dienst Vorgang kann asynchron implementiert werden, indem das .NET Framework asynchrone Programmier Muster verwendet und die `<Begin>`-Methode mit der Eigenschaft <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A> auf `true`festgelegt wird. In diesem Fall wird der asynchrone Vorgang in Metadaten in der gleichen Form wie ein synchroner Vorgang verfügbar gemacht: Er wird als einzelner Vorgang mit einer Anforderungsnachricht und einer korrelierten Antwortnachricht verfügbar gemacht. Clientprogrammierungsmodelle haben dann eine Wahl. Sie können dieses Muster als synchronen oder als asynchronen Vorgang darstellen, solange beim Aufrufen des Diensts ein Anforderung-Antwort-Nachrichtenaustausch stattfindet.  
  
 Aufgrund der asynchronen Natur der Systeme sollte i. A. eine Abhängigkeit von den Threads vermieden werden.  Die verlässlichste Möglichkeit, Daten an verschiedene Stufen der Vorgangsverteilungsverarbeitung zu übergeben, ist die Verwendung von Erweiterungen.  
  
 Ein Beispiel finden Sie unter [Vorgehensweise: Implementieren eines asynchronen Dienstvorgangs](how-to-implement-an-asynchronous-service-operation.md).  
  
 So definieren Sie ein Vertragsvorgang `X`, der unabhängig von der Art des Aufrufs in der Clientanwendung asynchron ausgeführt wird:  
  
- Definieren Sie zwei Methoden mit dem Muster `BeginOperation` und `EndOperation`.  
  
- Die `BeginOperation`-Methode enthält den `in`-Parameter und den `ref`-Parameter für den Vorgang und gibt einen <xref:System.IAsyncResult>-Typ zurück.  
  
- Die `EndOperation`-Methode enthält ebenfalls einen <xref:System.IAsyncResult>-Parameter sowie den `out`-Parameter und den `ref`-Parameter und gibt den Rückgabewert des Vorgangs zurück.  
  
 Betrachten Sie beispielsweise die folgende Methode:  
  
```csharp  
int DoWork(string data, ref string inout, out string outonly)  
```  
  
```vb  
Function DoWork(ByVal data As String, ByRef inout As String, _out outonly As out) As Integer  
```  
  
 Die beiden Methoden zum Erstellen eines asynchronen Vorgangs sind:  
  
```csharp  
[OperationContract(AsyncPattern=true)]
IAsyncResult BeginDoWork(string data,
                         ref string inout,
                         AsyncCallback callback,
                         object state);
int EndDoWork(ref string inout, out string outonly, IAsyncResult result);  
```  
  
```vb  
<OperationContract(AsyncPattern := True)>
Function BeginDoWork(ByVal data As String, _
                     ByRef inout As String, _
                     ByVal callback As AsyncCallback, _
                     ByVal state As Object) As IAsyncResult
Function EndDoWork(ByRef inout As String, ByRef outonly As String, ByVal result As IAsyncResult) As Integer  
```  
  
> [!NOTE]
> Das <xref:System.ServiceModel.OperationContractAttribute>-Attribut wird nur auf die `BeginDoWork`-Methode angewendet. Der resultierende Vertrag verfügt über einen WSDL-Vorgang mit der Bezeichnung `DoWork`.  
  
### <a name="client-side-asynchronous-invocations"></a>Clientseitige asynchrone Aufrufe  
 Eine WCF-Clientanwendung kann eine der drei asynchronen, oben beschriebenen Aufrufmodelle verwenden  
  
 Wenn Sie das taskbasierte Modell verwenden, rufen Sie einfach den Vorgang mithilfe des await-Schlüsselworts wie im folgenden Codeausschnitt dargestellt auf.  
  
```csharp  
await simpleServiceClient.SampleMethodTaskAsync("hello, world");  
```  
  
 Das ereignisbasierte asynchrone Muster erfordert lediglich, dass ein Ereignishandler hinzugefügt wird, der eine Benachrichtigung über die Antwort empfängt – und das Ereignis wird automatisch im Benutzeroberflächenthread ausgelöst. Geben Sie zum Verwenden dieses Ansatzes die **/async**- und die **/tcv:Version35**-Befehlsoption für das [Service Model Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) an, wie in folgendem Beispiel dargestellt.  
  
```console  
svcutil http://localhost:8000/servicemodelsamples/service/mex /async /tcv:Version35  
```  
  
 Dadurch generiert „Svcutil.exe“ eine WCF-Clientklasse mit der Ereignisinfrastruktur, die es der aufrufenden Anwendung ermöglicht, einen Ereignishandler zu implementieren und zuzuweisen, der die Antwort empfängt und die entsprechende Aktion einleitet. Ein vollständiges Beispiel finden Sie unter [Vorgehensweise: Asynchrones Aufrufen von Dienstvorgängen](./feature-details/how-to-call-wcf-service-operations-asynchronously.md).  
  
 Das ereignisbasierte asynchrone Modell ist jedoch nur in .NET Framework 3,5 verfügbar. Außerdem wird Sie auch in .NET Framework 3,5 nicht unterstützt, wenn ein WCF-Client Kanal mithilfe einer <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>erstellt wird. Bei WCF-Clientkanalobjekten müssen Sie <xref:System.IAsyncResult?displayProperty=nameWithType>-Objekte verwenden, um die Vorgänge asynchron aufzurufen. Geben Sie zum Verwenden dieses Ansatzes die **/async**-Befehlsoption für das [Service Model Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) an, wie in folgendem Beispiel dargestellt.  
  
```console  
svcutil http://localhost:8000/servicemodelsamples/service/mex /async   
```  
  
 Dadurch wird ein Dienstvertrag generiert, in dem jeder Vorgang als eine `<Begin>`-Methode mit der auf <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A> festgelegten `true`-Eigenschaft und einer entsprechenden `<End>`-Methode modelliert wird. Ein vollständiges Beispiel unter Verwendung einer <xref:System.ServiceModel.ChannelFactory%601> finden Sie unter [Vorgehensweise: Asynchrones Aufrufen von Vorgängen mit einer Kanalfactory](./feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md).  
  
 In jedem Fall können Anwendungen einen Vorgang asynchron aufrufen, auch wenn der Dienst synchron implementiert wurde, ebenso wie eine Anwendung mit dem gleichen Muster eine lokale synchrone Methode asynchron aufrufen kann. Wie der Vorgang implementiert wird, ist für den Client nicht von Bedeutung. Wenn die Antwortnachricht eintrifft, wird Ihr Inhalt an die asynchrone < des Clients gesendet,`End`>-Methode, und der Client ruft die Informationen ab.  
  
### <a name="one-way-message-exchange-patterns"></a>Unidirektionale Nachrichtenaustauschmuster  
 Sie können auch ein asynchrones Nachrichtenaustauschmuster erstellen, in dem unidirektionale Vorgänge (Vorgänge, bei denen das <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A?displayProperty=nameWithType>`true` ist, verfügen über keine korrelierte Antwort) vom Client oder vom Dienst unabhängig von der anderen Seite in beide Richtungen gesendet werden können. (Hierbei wird das Duplex Nachrichtenaustausch Muster mit unidirektionalen Nachrichten verwendet.) In diesem Fall gibt der Dienstvertrag einen unidirektionalen Nachrichtenaustausch an, der von beiden Seiten als asynchrone Aufrufe oder Implementierungen implementiert werden kann, oder nicht, je nach Bedarf. Wenn der Vertrag ein Austausch von unidirektionalen Nachrichten ist, können die Implementierungen im Allgemeinen hauptsächlich asynchron sein, da die Anwendung nach dem Senden der Nachricht nicht auf eine Antwort wartet und andere Aktivitäten weiter ausführen kann.  
  
### <a name="event-based-asynchronous-clients-and-message-contracts"></a>Ereignisbasierte asynchrone Clients und Nachrichtenverträge  
 Die Entwurfsrichtlinien für das ereignisbasierte asynchrone Modell besagen, dass in den Fällen, in denen mehr als ein Wert zurückgegeben wird, ein Wert in der `Result`-Eigenschaft und die übrigen Werte in Eigenschaften des <xref:System.EventArgs>-Objekts zurückgegeben werden sollen. Wenn ein Client Metadaten mithilfe der ereignisbasierten asynchronen Befehlsoptionen importiert, und der Vorgang mehr als einen Wert zurückgibt, dann gibt das <xref:System.EventArgs>-Standardobjekt infolgedessen einen Wert in der `Result`-Eigenschaft zurück, während die übrigen Werte in Eigenschaften des <xref:System.EventArgs>-Objekts zurückgegeben werden.  
  
 Wenn das Nachrichtenobjekt in der `Result`-Eigenschaft und die Rückgabewerte als Eigenschaften dieses Objekts übermittelt werden sollen, verwenden Sie die **/messageContract**-Befehlsoption. Damit wird eine Signatur generiert, bei der die Antwortnachricht in der `Result`-Eigenschaft des <xref:System.EventArgs>-Objekts zurückgegeben wird. Alle internen Rückgabewerte sind dann Eigenschaften des Antwortnachrichtenobjekts.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A>
- <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A>
