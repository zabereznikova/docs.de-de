---
title: Synchrone und asynchrone Vorgänge
description: Erfahren Sie mehr über das Implementieren und Aufrufen von asynchronen Dienst Vorgängen. WCF-Dienste und-Clients können asynchrone Vorgänge auf zwei Ebenen der Anwendung verwenden.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], synchronous operations
- service contracts [WCF], asynchronous operations
ms.assetid: db8a51cb-67e6-411b-9035-e5821ed350c9
ms.openlocfilehash: f14e206bb99215a7a9b2535f99feb9971274532b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254193"
---
# <a name="synchronous-and-asynchronous-operations"></a><span data-ttu-id="71882-104">Synchrone und asynchrone Vorgänge</span><span class="sxs-lookup"><span data-stu-id="71882-104">Synchronous and Asynchronous Operations</span></span>

<span data-ttu-id="71882-105">In diesem Thema werden das Implementieren und das Aufrufen asynchroner Dienstvorgänge erörtert.</span><span class="sxs-lookup"><span data-stu-id="71882-105">This topic discusses implementing and calling asynchronous service operations.</span></span>  
  
 <span data-ttu-id="71882-106">Viele Anwendungen rufen Methoden asynchron auf, weil dadurch die Anwendung beim Methodenaufruf weiter nützliche Arbeiten ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="71882-106">Many applications call methods asynchronously because it enables the application to continue doing useful work while the method call runs.</span></span> <span data-ttu-id="71882-107">Windows Communication Foundation-Dienste und -Clients (WCF) können an Aufrufen asynchroner Vorgänge auf zwei unterschiedlichen Anwendungsebenen teilnehmen, was WCF-Anwendungen noch mehr Flexibilität bietet, um den Durchsatz unter Abwägung der Interaktivität zu maximieren.</span><span class="sxs-lookup"><span data-stu-id="71882-107">Windows Communication Foundation (WCF) services and clients can participate in asynchronous operation calls at two distinct levels of the application, which provide WCF applications even more flexibility to maximize throughput balanced against interactivity.</span></span>  
  
## <a name="types-of-asynchronous-operations"></a><span data-ttu-id="71882-108">Typen asynchroner Vorgänge</span><span class="sxs-lookup"><span data-stu-id="71882-108">Types of Asynchronous Operations</span></span>  

 <span data-ttu-id="71882-109">Alle Dienstverträge in WCF verwenden unabhängig von den Parametertypen und Rückgabewerten WCF-Attribute zum Angeben eines bestimmten Musters für den Nachrichtenaustausch zwischen Client und Dienst.</span><span class="sxs-lookup"><span data-stu-id="71882-109">All service contracts in WCF, no matter the parameters types and return values, use WCF attributes to specify a particular message exchange pattern between client and service.</span></span> <span data-ttu-id="71882-110">WCF leitet automatisch eingehende und ausgehende Nachrichten an den entsprechenden Dienstvorgang oder ausgeführten Clientcode weiter.</span><span class="sxs-lookup"><span data-stu-id="71882-110">WCF automatically routes inbound and outbound messages to the appropriate service operation or running client code.</span></span>  
  
 <span data-ttu-id="71882-111">Der Client verfügt nur über den Dienstvertrag, der das Nachrichtenaustauschmuster für einen bestimmten Vorgang angibt.</span><span class="sxs-lookup"><span data-stu-id="71882-111">The client possesses only the service contract, which specifies the message exchange pattern for a particular operation.</span></span> <span data-ttu-id="71882-112">Clients können dem Entwickler ein beliebiges Programmiermodell anbieten, solange das zugrunde liegende Nachrichtenaustauschmuster eingehalten wird.</span><span class="sxs-lookup"><span data-stu-id="71882-112">Clients can offer the developer any programming model they choose, so long as the underlying message exchange pattern is observed.</span></span> <span data-ttu-id="71882-113">Ebenso können Dienste Vorgänge auf beliebige Weise implementieren, solange das angegebene Nachrichtenmuster eingehalten wird.</span><span class="sxs-lookup"><span data-stu-id="71882-113">So, too, can services implement operations in any manner, so long as the specified message pattern is observed.</span></span>  
  
 <span data-ttu-id="71882-114">Die Unabhängigkeit des Dienstvertrags von der Dienst- oder Clientimplementierung ermöglicht die folgenden Formen asynchroner Ausführung in WCF-Anwendungen:</span><span class="sxs-lookup"><span data-stu-id="71882-114">The independence of the service contract from either the service or client implementation enables the following forms of asynchronous execution in WCF applications:</span></span>  
  
- <span data-ttu-id="71882-115">Clients können Anforderungs-/Antwortvorgänge mit einem synchronen Nachrichtenaustausch asynchron aufrufen.</span><span class="sxs-lookup"><span data-stu-id="71882-115">Clients can invoke request/response operations asynchronously using a synchronous message exchange.</span></span>  
  
- <span data-ttu-id="71882-116">Clients können asynchrone Anforderungs-/Antwortvorgänge mit einem synchronen Nachrichtenaustausch implementieren.</span><span class="sxs-lookup"><span data-stu-id="71882-116">Services can implement a request/response operation asynchronously using a synchronous message exchange.</span></span>  
  
- <span data-ttu-id="71882-117">Ein Nachrichtenaustausch kann unidirektional sein, unabhängig von der Implementierung des Clients oder Dienstes.</span><span class="sxs-lookup"><span data-stu-id="71882-117">Message exchanges can be one-way, regardless of the implementation of the client or service.</span></span>  
  
### <a name="suggested-asynchronous-scenarios"></a><span data-ttu-id="71882-118">Vorgeschlagene asynchrone Szenarien</span><span class="sxs-lookup"><span data-stu-id="71882-118">Suggested Asynchronous Scenarios</span></span>  

 <span data-ttu-id="71882-119">Verwenden Sie den asynchronen Ansatz in der Implementierung eines Dienstvorgangs, wenn dieser Dienstvorgang blockierende Aufrufe, beispielsweise E/A-Vorgänge, vornimmt.</span><span class="sxs-lookup"><span data-stu-id="71882-119">Use an asynchronous approach in a service operation implementation if the operation service implementation makes a blocking call, such as doing I/O work.</span></span> <span data-ttu-id="71882-120">Bei der Implementierung eines asynchronen Vorgangs sollten Sie versuchen, asynchrone Vorgänge und Methoden aufzurufen, um den asynchronen Aufrufpfad so weit wie möglich zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="71882-120">When you are in an asynchronous operation implementation, try to call asynchronous operations and methods to extend the asynchronous call path as far as possible.</span></span> <span data-ttu-id="71882-121">Rufen Sie z.&#160;B. innerhalb von `BeginOperationTwo()``BeginOperationOne()` auf.</span><span class="sxs-lookup"><span data-stu-id="71882-121">For example, call a `BeginOperationTwo()` from within `BeginOperationOne()`.</span></span>  
  
- <span data-ttu-id="71882-122">Verwenden Sie in den folgenden Fällen einen asynchronen Ansatz in einem Client oder in einer aufrufenden Anwendung:</span><span class="sxs-lookup"><span data-stu-id="71882-122">Use an asynchronous approach in a client or calling application in the following cases:</span></span>  
  
- <span data-ttu-id="71882-123">Wenn Sie Vorgänge von einer Anwendung der mittleren Ebene aufrufen.</span><span class="sxs-lookup"><span data-stu-id="71882-123">If you are invoking operations from a middle-tier application.</span></span> <span data-ttu-id="71882-124">(Weitere Informationen zu solchen Szenarien finden Sie unter [Clientanwendungen mittlerer Ebene](./feature-details/middle-tier-client-applications.md).)</span><span class="sxs-lookup"><span data-stu-id="71882-124">(For more information about such scenarios, see [Middle-Tier Client Applications](./feature-details/middle-tier-client-applications.md).)</span></span>  
  
- <span data-ttu-id="71882-125">Verwenden Sie asynchrone Seiten, wenn Sie Vorgänge innerhalb einer ASP.NET-Seite aufrufen.</span><span class="sxs-lookup"><span data-stu-id="71882-125">If you are invoking operations within an ASP.NET page, use asynchronous pages.</span></span>  
  
- <span data-ttu-id="71882-126">Wenn Sie Vorgänge von einer Singlethread-Anwendung aufrufen, etwa einer Windows Forms- oder Windows Presentation Foundation-Anwendung (WPF).</span><span class="sxs-lookup"><span data-stu-id="71882-126">If you are invoking operations from any application that is single threaded, such as Windows Forms or Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="71882-127">Bei Verwendung des ereignisgesteuerten asynchronen Aufrufmodells wird das resultierende Ereignis im UI-Thread ausgelöst. Dies erhöht die Ansprechempfindlichkeit der Anwendung gegenüber Benutzeraktivitäten, ohne dass Sie selbst mehrere Threads verwalten müssen.</span><span class="sxs-lookup"><span data-stu-id="71882-127">When using the event-based asynchronous calling model, the result event is raised on the UI thread, adding responsiveness to the application without requiring you to handle multiple threads yourself.</span></span>  
  
- <span data-ttu-id="71882-128">Im Allgemeinen gilt: Haben Sie die Wahl zwischen einem synchronen oder einem asynchronen Aufruf, dann wählen Sie den asynchronen Aufruf.</span><span class="sxs-lookup"><span data-stu-id="71882-128">In general, if you have a choice between a synchronous and asynchronous call, choose the asynchronous call.</span></span>  
  
### <a name="implementing-an-asynchronous-service-operation"></a><span data-ttu-id="71882-129">Implementieren eines asynchronen Dienstvorgangs</span><span class="sxs-lookup"><span data-stu-id="71882-129">Implementing an Asynchronous Service Operation</span></span>  

 <span data-ttu-id="71882-130">Asynchrone Vorgänge können auf eine der drei folgenden Arten implementiert werden:</span><span class="sxs-lookup"><span data-stu-id="71882-130">Asynchronous operations can be implemented by using one of the three following methods:</span></span>  
  
1. <span data-ttu-id="71882-131">Das aufgabenbasierte asynchrone Muster</span><span class="sxs-lookup"><span data-stu-id="71882-131">The task-based asynchronous pattern</span></span>  
  
2. <span data-ttu-id="71882-132">Das ereignisbasierte asynchrone Muster</span><span class="sxs-lookup"><span data-stu-id="71882-132">The event-based asynchronous pattern</span></span>  
  
3. <span data-ttu-id="71882-133">Das asynchrone IAsyncResult-Muster</span><span class="sxs-lookup"><span data-stu-id="71882-133">The IAsyncResult asynchronous pattern</span></span>  
  
#### <a name="task-based-asynchronous-pattern"></a><span data-ttu-id="71882-134">Taskbasiertes asynchrones Muster</span><span class="sxs-lookup"><span data-stu-id="71882-134">Task-Based Asynchronous Pattern</span></span>  

 <span data-ttu-id="71882-135">Das aufgabenbasierte asynchrone Muster ist die bevorzugte Methode zum Implementieren asynchroner Vorgänge, weil es einfach und verständlich ist.</span><span class="sxs-lookup"><span data-stu-id="71882-135">The task-based asynchronous pattern is the preferred way to implement asynchronous operations because it is the easiest and most straight forward.</span></span> <span data-ttu-id="71882-136">Um diese Methode zu verwenden, implementieren Sie einfach den Dienst Vorgang und geben den Rückgabetyp Task an \<T> , wobei T der Typ ist, der von der logischen Operation zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="71882-136">To use this method simply implement your service operation and specify a return type of Task\<T>, where T is the type returned by the logical operation.</span></span> <span data-ttu-id="71882-137">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="71882-137">For example:</span></span>  
  
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
  
 <span data-ttu-id="71882-138">Der samplemethodtaskasync-Vorgang gibt die Aufgabe zurück, \<string> da die logische Operation eine Zeichenfolge zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="71882-138">The SampleMethodTaskAsync operation returns Task\<string> because the logical operation returns a string.</span></span> <span data-ttu-id="71882-139">Weitere Informationen über das taskbasierte asynchrone Muster finden Sie unter [Taskbasiertes asynchrones Muster](https://go.microsoft.com/fwlink/?LinkId=232504).</span><span class="sxs-lookup"><span data-stu-id="71882-139">For more information about the task-based asynchronous pattern, see [The Task-Based Asynchronous Pattern](https://go.microsoft.com/fwlink/?LinkId=232504).</span></span>  
  
> [!WARNING]
> <span data-ttu-id="71882-140">Bei Verwendung des taskbasierten asynchronen Musters kann bei einer Ausnahme eine T:System.AggregateException ausgelöst werden, während auf den Abschluss des Vorgangs gewartet wird.</span><span class="sxs-lookup"><span data-stu-id="71882-140">When using the task-based asynchronous pattern, a T:System.AggregateException may be thrown if an exception occurs while waiting on the completion of the operation.</span></span> <span data-ttu-id="71882-141">Diese Ausnahme kann für Clients oder Dienste auftreten.</span><span class="sxs-lookup"><span data-stu-id="71882-141">This exception may occur on the client or services</span></span>  
  
#### <a name="event-based-asynchronous-pattern"></a><span data-ttu-id="71882-142">Ereignisbasiertes asynchrones Muster</span><span class="sxs-lookup"><span data-stu-id="71882-142">Event-Based Asynchronous Pattern</span></span>  

 <span data-ttu-id="71882-143">Ein Dienst, der das ereignisbasierte asynchrone Muster unterstützt, verfügt über einen oder mehrere Vorgänge mit dem Namen MethodNameAsync.</span><span class="sxs-lookup"><span data-stu-id="71882-143">A service that supports the Event-based Asynchronous Pattern will have one or more operations named MethodNameAsync.</span></span> <span data-ttu-id="71882-144">Diese Methoden spiegeln möglicherweise synchrone Versionen wider, die denselben Vorgang im aktuellen Thread durchführen.</span><span class="sxs-lookup"><span data-stu-id="71882-144">These methods may mirror synchronous versions, which perform the same operation on the current thread.</span></span> <span data-ttu-id="71882-145">Die Klasse kann darüber hinaus auch über ein MethodNameCompleted-Ereignis und eine MethodNameAsyncCancel-Methode (kurz CancelAsync) verfügen.</span><span class="sxs-lookup"><span data-stu-id="71882-145">The class may also have a MethodNameCompleted event and it may have a MethodNameAsyncCancel (or simply CancelAsync) method.</span></span> <span data-ttu-id="71882-146">Ein Client, der den Vorgang aufrufen möchte, definiert einen Ereignishandler, der bei Abschluss des Vorgangs aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="71882-146">A client wishing to call the operation will define an event handler to be called when the operation completes,</span></span>  
  
 <span data-ttu-id="71882-147">Der folgende Codeausschnitt veranschaulicht, wie asynchrone Vorgänge unter Verwendung des ereignisbasierten asynchronen Musters deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="71882-147">The following code snippet illustrates how to declare asynchronous operations using the event-based asynchronous pattern.</span></span>  
  
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
  
 <span data-ttu-id="71882-148">Weitere Informationen über das ereignisbasierte asynchrone Muster finden Sie unter [Übersicht über ereignisbasierte asynchrone Muster](../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).</span><span class="sxs-lookup"><span data-stu-id="71882-148">For more information about the Event-based Asynchronous Pattern, see [The Event-Based Asynchronous Pattern](../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).</span></span>  
  
#### <a name="iasyncresult-asynchronous-pattern"></a><span data-ttu-id="71882-149">Das asynchrone IAsyncResult-Muster</span><span class="sxs-lookup"><span data-stu-id="71882-149">IAsyncResult Asynchronous Pattern</span></span>  

 <span data-ttu-id="71882-150">Ein Dienst Vorgang kann asynchron implementiert werden, indem das .NET Framework asynchrone Programmier Muster verwendet wird, und die- `<Begin>` Methode wird mit der- <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A> Eigenschaft markiert, die auf festgelegt ist `true` .</span><span class="sxs-lookup"><span data-stu-id="71882-150">A service operation can be implemented in an asynchronous fashion using the .NET Framework asynchronous programming pattern and marking the `<Begin>` method with the <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A> property set to `true`.</span></span> <span data-ttu-id="71882-151">In diesem Fall wird der asynchrone Vorgang in Metadaten in der gleichen Form wie ein synchroner Vorgang verfügbar gemacht: Er wird als einzelner Vorgang mit einer Anforderungsnachricht und einer korrelierten Antwortnachricht verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="71882-151">In this case, the asynchronous operation is exposed in metadata in the same form as a synchronous operation: It is exposed as a single operation with a request message and a correlated response message.</span></span> <span data-ttu-id="71882-152">Clientprogrammierungsmodelle haben dann eine Wahl.</span><span class="sxs-lookup"><span data-stu-id="71882-152">Client programming models then have a choice.</span></span> <span data-ttu-id="71882-153">Sie können dieses Muster als synchronen oder als asynchronen Vorgang darstellen, solange beim Aufrufen des Diensts ein Anforderung-Antwort-Nachrichtenaustausch stattfindet.</span><span class="sxs-lookup"><span data-stu-id="71882-153">They can represent this pattern as a synchronous operation or as an asynchronous one, so long as when the service is invoked a request-response message exchange takes place.</span></span>  
  
 <span data-ttu-id="71882-154">Aufgrund der asynchronen Natur der Systeme sollte i. A. eine Abhängigkeit von den Threads vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="71882-154">In general, with the asynchronous nature of the systems, you should not take a dependency on the threads.</span></span>  <span data-ttu-id="71882-155">Die verlässlichste Möglichkeit, Daten an verschiedene Stufen der Vorgangsverteilungsverarbeitung zu übergeben, ist die Verwendung von Erweiterungen.</span><span class="sxs-lookup"><span data-stu-id="71882-155">The most reliable way of passing data to various stages of operation dispatch processing is to use extensions.</span></span>  
  
 <span data-ttu-id="71882-156">Ein Beispiel finden Sie unter [Vorgehensweise: Implementieren eines asynchronen Dienstvorgangs](how-to-implement-an-asynchronous-service-operation.md).</span><span class="sxs-lookup"><span data-stu-id="71882-156">For an example, see [How to: Implement an Asynchronous Service Operation](how-to-implement-an-asynchronous-service-operation.md).</span></span>  
  
 <span data-ttu-id="71882-157">So definieren Sie ein Vertragsvorgang `X`, der unabhängig von der Art des Aufrufs in der Clientanwendung asynchron ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="71882-157">To define a contract operation `X` that is executed asynchronously regardless of how it is called in the client application:</span></span>  
  
- <span data-ttu-id="71882-158">Definieren Sie zwei Methoden mit dem Muster `BeginOperation` und `EndOperation`.</span><span class="sxs-lookup"><span data-stu-id="71882-158">Define two methods using the pattern `BeginOperation` and `EndOperation`.</span></span>  
  
- <span data-ttu-id="71882-159">Die `BeginOperation`-Methode enthält den `in`-Parameter und den `ref`-Parameter für den Vorgang und gibt einen <xref:System.IAsyncResult>-Typ zurück.</span><span class="sxs-lookup"><span data-stu-id="71882-159">The `BeginOperation` method includes `in` and `ref` parameters for the operation and returns an <xref:System.IAsyncResult> type.</span></span>  
  
- <span data-ttu-id="71882-160">Die `EndOperation`-Methode enthält ebenfalls einen <xref:System.IAsyncResult>-Parameter sowie den `out`-Parameter und den `ref`-Parameter und gibt den Rückgabewert des Vorgangs zurück.</span><span class="sxs-lookup"><span data-stu-id="71882-160">The `EndOperation` method includes an <xref:System.IAsyncResult> parameter as well as the `out` and `ref` parameters and returns the operations return type.</span></span>  
  
 <span data-ttu-id="71882-161">Betrachten Sie beispielsweise die folgende Methode:</span><span class="sxs-lookup"><span data-stu-id="71882-161">For example, see the following method.</span></span>  
  
```csharp  
int DoWork(string data, ref string inout, out string outonly)  
```  
  
```vb  
Function DoWork(ByVal data As String, ByRef inout As String, _out outonly As out) As Integer  
```  
  
 <span data-ttu-id="71882-162">Die beiden Methoden zum Erstellen eines asynchronen Vorgangs sind:</span><span class="sxs-lookup"><span data-stu-id="71882-162">To create an asynchronous operation, the two methods would be:</span></span>  
  
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
> <span data-ttu-id="71882-163">Das <xref:System.ServiceModel.OperationContractAttribute>-Attribut wird nur auf die `BeginDoWork`-Methode angewendet.</span><span class="sxs-lookup"><span data-stu-id="71882-163">The <xref:System.ServiceModel.OperationContractAttribute> attribute is applied only to the `BeginDoWork` method.</span></span> <span data-ttu-id="71882-164">Der resultierende Vertrag verfügt über einen WSDL-Vorgang mit der Bezeichnung `DoWork`.</span><span class="sxs-lookup"><span data-stu-id="71882-164">The resulting contract has one WSDL operation named `DoWork`.</span></span>  
  
### <a name="client-side-asynchronous-invocations"></a><span data-ttu-id="71882-165">Clientseitige asynchrone Aufrufe</span><span class="sxs-lookup"><span data-stu-id="71882-165">Client-Side Asynchronous Invocations</span></span>  

 <span data-ttu-id="71882-166">Eine WCF-Clientanwendung kann eine der drei asynchronen, oben beschriebenen Aufrufmodelle verwenden</span><span class="sxs-lookup"><span data-stu-id="71882-166">A WCF client application can use any of three asynchronous calling models described previously</span></span>  
  
 <span data-ttu-id="71882-167">Wenn Sie das taskbasierte Modell verwenden, rufen Sie einfach den Vorgang mithilfe des await-Schlüsselworts wie im folgenden Codeausschnitt dargestellt auf.</span><span class="sxs-lookup"><span data-stu-id="71882-167">When using the task-based model, simply call the operation using the await keyword as shown in the following code snippet.</span></span>  
  
```csharp  
await simpleServiceClient.SampleMethodTaskAsync("hello, world");  
```  
  
 <span data-ttu-id="71882-168">Das ereignisbasierte asynchrone Muster erfordert lediglich, dass ein Ereignishandler hinzugefügt wird, der eine Benachrichtigung über die Antwort empfängt – und das Ereignis wird automatisch im Benutzeroberflächenthread ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="71882-168">Using the event-based asynchronous pattern only requires adding an event handler to receive a notification of the response -- and the resulting event is raised on the user interface thread automatically.</span></span> <span data-ttu-id="71882-169">Geben Sie zum Verwenden dieses Ansatzes die **/async**- und die **/tcv:Version35**-Befehlsoption für das [Service Model Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) an, wie in folgendem Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="71882-169">To use this approach, specify both the **/async** and **/tcv:Version35** command options with the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md), as in the following example.</span></span>  
  
```console  
svcutil http://localhost:8000/servicemodelsamples/service/mex /async /tcv:Version35  
```  
  
 <span data-ttu-id="71882-170">Dadurch generiert „Svcutil.exe“ eine WCF-Clientklasse mit der Ereignisinfrastruktur, die es der aufrufenden Anwendung ermöglicht, einen Ereignishandler zu implementieren und zuzuweisen, der die Antwort empfängt und die entsprechende Aktion einleitet.</span><span class="sxs-lookup"><span data-stu-id="71882-170">When this is done, Svcutil.exe generates a WCF client class with the event infrastructure that enables the calling application to implement and assign an event handler to receive the response and take the appropriate action.</span></span> <span data-ttu-id="71882-171">Ein vollständiges Beispiel finden Sie unter [Vorgehensweise: Asynchrones Aufrufen von Dienstvorgängen](./feature-details/how-to-call-wcf-service-operations-asynchronously.md).</span><span class="sxs-lookup"><span data-stu-id="71882-171">For a complete example, see [How to: Call Service Operations Asynchronously](./feature-details/how-to-call-wcf-service-operations-asynchronously.md).</span></span>  
  
 <span data-ttu-id="71882-172">Das ereignisbasierte asynchrone Modell ist jedoch nur in .NET Framework 3,5 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="71882-172">The event-based asynchronous model, however, is only available in .NET Framework 3.5.</span></span> <span data-ttu-id="71882-173">Außerdem wird Sie auch in .NET Framework 3,5 nicht unterstützt, wenn ein WCF-Client Kanal mithilfe von erstellt wird <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="71882-173">In addition, it is not supported even in .NET Framework 3.5 when a WCF client channel is created by using a <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="71882-174">Bei WCF-Clientkanalobjekten müssen Sie <xref:System.IAsyncResult?displayProperty=nameWithType>-Objekte verwenden, um die Vorgänge asynchron aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="71882-174">With WCF client channel objects, you must use <xref:System.IAsyncResult?displayProperty=nameWithType> objects to invoke your operations asynchronously.</span></span> <span data-ttu-id="71882-175">Geben Sie zum Verwenden dieses Ansatzes die **/async**-Befehlsoption für das [Service Model Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) an, wie in folgendem Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="71882-175">To use this approach, specify the **/async** command option with the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md), as in the following example.</span></span>  
  
```console  
svcutil http://localhost:8000/servicemodelsamples/service/mex /async
```  
  
 <span data-ttu-id="71882-176">Dadurch wird ein Dienstvertrag generiert, in dem jeder Vorgang als eine `<Begin>`-Methode mit der auf <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A> festgelegten `true`-Eigenschaft und einer entsprechenden `<End>`-Methode modelliert wird.</span><span class="sxs-lookup"><span data-stu-id="71882-176">This generates a service contract in which each operation is modeled as a `<Begin>` method with the <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A> property set to `true` and a corresponding `<End>` method.</span></span> <span data-ttu-id="71882-177">Ein vollständiges Beispiel unter Verwendung einer <xref:System.ServiceModel.ChannelFactory%601> finden Sie unter [Vorgehensweise: Asynchrones Aufrufen von Vorgängen mit einer Kanalfactory](./feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md).</span><span class="sxs-lookup"><span data-stu-id="71882-177">For a complete example using a <xref:System.ServiceModel.ChannelFactory%601>, see [How to: Call Operations Asynchronously Using a Channel Factory](./feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md).</span></span>  
  
 <span data-ttu-id="71882-178">In jedem Fall können Anwendungen einen Vorgang asynchron aufrufen, auch wenn der Dienst synchron implementiert wurde, ebenso wie eine Anwendung mit dem gleichen Muster eine lokale synchrone Methode asynchron aufrufen kann.</span><span class="sxs-lookup"><span data-stu-id="71882-178">In either case, applications can invoke an operation asynchronously even if the service is implemented synchronously, in the same way that an application can use the same pattern to invoke asynchronously a local synchronous method.</span></span> <span data-ttu-id="71882-179">Wie der Vorgang implementiert wird, ist für den Client nicht von Bedeutung. Wenn die Antwortnachricht eintrifft, wird Ihr Inhalt an die asynchrone <> Methode des Clients gesendet, `End` und der Client ruft die Informationen ab.</span><span class="sxs-lookup"><span data-stu-id="71882-179">How the operation is implemented is not significant to the client; when the response message arrives, its content is dispatched to the client's asynchronous <`End`> method and the client retrieves the information.</span></span>  
  
### <a name="one-way-message-exchange-patterns"></a><span data-ttu-id="71882-180">Unidirektionale Nachrichtenaustauschmuster</span><span class="sxs-lookup"><span data-stu-id="71882-180">One-Way Message Exchange Patterns</span></span>  

 <span data-ttu-id="71882-181">Sie können auch ein asynchrones Nachrichtenaustauschmuster erstellen, in dem unidirektionale Vorgänge (Vorgänge, bei denen das <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A?displayProperty=nameWithType>`true` ist, verfügen über keine korrelierte Antwort) vom Client oder vom Dienst unabhängig von der anderen Seite in beide Richtungen gesendet werden können.</span><span class="sxs-lookup"><span data-stu-id="71882-181">You can also create an asynchronous message exchange pattern in which one-way operations (operations for which the <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A?displayProperty=nameWithType> is `true` have no correlated response) can be sent in either direction by the client or service independently of the other side.</span></span> <span data-ttu-id="71882-182">(Hierbei wird das Duplex Nachrichtenaustausch Muster mit unidirektionalen Nachrichten verwendet.) In diesem Fall gibt der Dienstvertrag einen unidirektionalen Nachrichtenaustausch an, der von beiden Seiten als asynchrone Aufrufe oder Implementierungen implementiert werden kann, oder nicht, je nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="71882-182">(This uses the duplex message exchange pattern with one-way messages.) In this case, the service contract specifies a one-way message exchange that either side can implement as asynchronous calls or implementations, or not, as appropriate.</span></span> <span data-ttu-id="71882-183">Wenn der Vertrag ein Austausch von unidirektionalen Nachrichten ist, können die Implementierungen im Allgemeinen hauptsächlich asynchron sein, da die Anwendung nach dem Senden der Nachricht nicht auf eine Antwort wartet und andere Aktivitäten weiter ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="71882-183">Generally, when the contract is an exchange of one-way messages, the implementations can largely be asynchronous because once a message is sent the application does not wait for a reply and can continue doing other work.</span></span>  
  
### <a name="event-based-asynchronous-clients-and-message-contracts"></a><span data-ttu-id="71882-184">Ereignisbasierte asynchrone Clients und Nachrichtenverträge</span><span class="sxs-lookup"><span data-stu-id="71882-184">Event-based Asynchronous Clients and Message Contracts</span></span>  

 <span data-ttu-id="71882-185">Die Entwurfsrichtlinien für das ereignisbasierte asynchrone Modell besagen, dass in den Fällen, in denen mehr als ein Wert zurückgegeben wird, ein Wert in der `Result`-Eigenschaft und die übrigen Werte in Eigenschaften des <xref:System.EventArgs>-Objekts zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="71882-185">The design guidelines for the event-based asynchronous model state that if more than one value is returned, one value is returned as the `Result` property and the others are returned as properties on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="71882-186">Wenn ein Client Metadaten mithilfe der ereignisbasierten asynchronen Befehlsoptionen importiert, und der Vorgang mehr als einen Wert zurückgibt, dann gibt das <xref:System.EventArgs>-Standardobjekt infolgedessen einen Wert in der `Result`-Eigenschaft zurück, während die übrigen Werte in Eigenschaften des <xref:System.EventArgs>-Objekts zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="71882-186">One result of this is that if a client imports metadata using the event-based asynchronous command options and the operation returns more than one value, the default <xref:System.EventArgs> object returns one value as the `Result` property and the remainder are properties of the <xref:System.EventArgs> object.</span></span>  
  
 <span data-ttu-id="71882-187">Wenn das Nachrichtenobjekt in der `Result`-Eigenschaft und die Rückgabewerte als Eigenschaften dieses Objekts übermittelt werden sollen, verwenden Sie die **/messageContract**-Befehlsoption.</span><span class="sxs-lookup"><span data-stu-id="71882-187">If you want to receive the message object as the `Result` property and have the returned values as properties on that object, use the **/messageContract** command option.</span></span> <span data-ttu-id="71882-188">Damit wird eine Signatur generiert, bei der die Antwortnachricht in der `Result`-Eigenschaft des <xref:System.EventArgs>-Objekts zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="71882-188">This generates a signature that returns the response message as the `Result` property on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="71882-189">Alle internen Rückgabewerte sind dann Eigenschaften des Antwortnachrichtenobjekts.</span><span class="sxs-lookup"><span data-stu-id="71882-189">All internal return values are then properties of the response message object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71882-190">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="71882-190">See also</span></span>

- <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A>
- <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A>
