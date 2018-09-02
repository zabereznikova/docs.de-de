---
title: Benutzerdefinierte Lebensdauer
ms.date: 08/20/2018
ms.assetid: 52806c07-b91c-48fe-b992-88a41924f51f
ms.openlocfilehash: 1946608c69401fb08f6eb458a8adabea24563963
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2018
ms.locfileid: "43467745"
---
# <a name="custom-lifetime"></a>Benutzerdefinierte Lebensdauer

In diesem Beispiel wird veranschaulicht, wie schreiben Sie eine Windows Communication Foundation (WCF)-Erweiterung, um die benutzerdefinierte Lebensdauerdienste für freigegebene Instanzen von WCF-Dienst bereitstellen werden.

> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Artikels.

## <a name="shared-instancing"></a>Freigegebene Instanziierung

WCF bietet mehrere instanziierungsmodi für Ihre Dienstinstanzen. Der freigegebene Instanziierungsmodus, die in diesem Artikel behandelten bietet eine Möglichkeit, eine Dienstinstanz zwischen mehreren Kanälen freizugeben. Clients können wenden Sie sich an eine Factorymethode im Dienst und erstellen einen neuen Kanal aus, um Kommunikation zu starten. Der folgende Codeausschnitt zeigt, wie eine Clientanwendung einen neuen Kanal zu einer vorhandenen Dienstinstanz erstellt:

```csharp
// Create a header for the shared instance id
MessageHeader shareableInstanceContextHeader = MessageHeader.CreateHeader(
        CustomHeader.HeaderName,
        CustomHeader.HeaderNamespace,
        Guid.NewGuid().ToString());

// Create the channel factory
ChannelFactory<IEchoService> channelFactory =
    new ChannelFactory<IEchoService>("echoservice");

// Create the first channel
IEchoService proxy = channelFactory.CreateChannel();

// Call an operation to create shared service instance
using (new OperationContextScope((IClientChannel)proxy))
{
    OperationContext.Current.OutgoingMessageHeaders.Add(shareableInstanceContextHeader);
    Console.WriteLine("Service returned: " + proxy.Echo("Apple"));
}

((IChannel)proxy).Close();

// Create the second channel
IEchoService proxy2 = channelFactory.CreateChannel();

// Call an operation using the same header that will reuse the shared service instance
using (new OperationContextScope((IClientChannel)proxy2))
{
    OperationContext.Current.OutgoingMessageHeaders.Add(shareableInstanceContextHeader);
    Console.WriteLine("Service returned: " + proxy2.Echo("Apple"));
}
```

Der freigegebene Instanziierungsmodus unterscheidet sich von anderen Instanziierungsmodi in seiner einzigartigen Methode zum Freigeben von Dienstinstanzen. Standardmäßig für alle Kanäle geschlossen werden ein <xref:System.ServiceModel.InstanceContext>, die WCF-Dienst-Laufzeit überprüft, ob der Dienst <xref:System.ServiceModel.InstanceContextMode> konfiguriert ist <xref:System.ServiceModel.InstanceContextMode.PerCall> oder <xref:System.ServiceModel.InstanceContextMode.PerSession>, und wenn also die Instanz frei, und die Ressourcen von Ansprüchen. Wenn eine benutzerdefinierte <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> ist WCF verwendet wird, aufgerufen werden. die <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> -Methode der Implementierung des Anbieters, bevor die Instanz freigegeben. Wenn <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> gibt `true` die Instanz freigegeben wird, andernfalls die <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> Implementierung ist zuständig für die Benachrichtigung der `Dispatcher` von dem Leerlaufzustand durch Verwendung einer Rückrufmethode. Dies erfolgt durch Aufrufen der <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> -Methode des Anbieters.

In diesem Beispiel wird veranschaulicht, wie Sie verzögern freigeben, können die <xref:System.ServiceModel.InstanceContext> mit einem Leerlauftimeout von 20 Sekunden.

## <a name="extending-the-instancecontext"></a>Erweitern von InstanceContext

In WCF <xref:System.ServiceModel.InstanceContext> ist der Link zwischen der Dienstinstanz und `Dispatcher`. WCF lässt sich durch Hinzufügen von neuen Zustand oder ein Verhalten mithilfe des erweiterbaren Objektmusters diese Laufzeitkomponente zu erweitern. Das erweiterbare Objektmuster wird in WCF verwendet, um entweder vorhandene Laufzeitklassen neue Funktionen zu erweitern oder zu einem Objekt neue Zustandsfunktionen hinzuzufügen. Es gibt drei Schnittstellen im erweiterbaren Objektmuster: <xref:System.ServiceModel.IExtensibleObject%601>, <xref:System.ServiceModel.IExtension%601> und <xref:System.ServiceModel.IExtensionCollection%601>.

Die <xref:System.ServiceModel.IExtensibleObject%601> Schnittstelle wird implementiert von Objekten um Erweiterungen zuzulassen, die ihre Funktionalität anpassen.

Die <xref:System.ServiceModel.IExtension%601>-Schnittstelle wird von Objekten implementiert, die Erweiterungen von Klassen des Typs `T` sein können.

Und schließlich die <xref:System.ServiceModel.IExtensionCollection%601> Schnittstelle ist eine Sammlung von <xref:System.ServiceModel.IExtension%601> Implementierungen, die es ermöglicht eine Implementierung der abrufen <xref:System.ServiceModel.IExtension%601> anhand ihres Typs.

Aus diesem Grund zum Erweitern der <xref:System.ServiceModel.InstanceContext>, müssen Sie implementieren die <xref:System.ServiceModel.IExtension%601> Schnittstelle. In diesem Beispielprojekt das `CustomLeaseExtension` -Klasse enthält diese Implementierung.

```csharp
class CustomLeaseExtension : IExtension<InstanceContext>
{
}
```

Die <xref:System.ServiceModel.IExtension%601>-Schnittstelle verfügt über zwei Methoden: <xref:System.ServiceModel.IExtension%601.Attach%2A> und <xref:System.ServiceModel.IExtension%601.Detach%2A>. Wie ihre Namen vermuten lassen, werden diese beiden Methoden aufgerufen, wenn die Laufzeit die Erweiterung an eine Instanz der <xref:System.ServiceModel.InstanceContext>-Klasse anfügt oder von der Instanz löst. In diesem Beispiel wird die `Attach`-Methode für die Nachverfolgung des <xref:System.ServiceModel.InstanceContext>-Objekts verwendet, das zur aktuellen Instanz der Erweiterung gehört.

```csharp
InstanceContext owner;

public void Attach(InstanceContext owner)
{
    this.owner = owner;
}
```

Darüber hinaus müssen Sie zur Bereitstellung der erweiterten Lebensdauerunterstützung die erforderliche Implementierung zur Erweiterung hinzufügen. Aus diesem Grund die `ICustomLease` Schnittstelle wird mit den gewünschten Methoden deklariert und implementiert wird, der `CustomLeaseExtension` Klasse.

```csharp
interface ICustomLease
{
    bool IsIdle { get; }
    InstanceContextIdleCallback Callback { get; set; }
}

class CustomLeaseExtension : IExtension<InstanceContext>, ICustomLease
{
}
```

Wenn WCF aufruft der <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> -Methode in der die <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> Implementierung dieser Aufruf wird an weitergeleitet der <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> Methode der `CustomLeaseExtension`. Anschließend wird die `CustomLeaseExtension` überprüft den privaten Zustand, um festzustellen, ob die <xref:System.ServiceModel.InstanceContext> im Leerlauf befindet. Wenn er im Leerlauf ist, gibt es `true`. Andernfalls wird ein Zeitgeber für eine bestimmte erweiterte Lebensdauerperiode gestartet.

```csharp
public bool IsIdle
{
  get
  {
    lock (thisLock)
    {
      if (isIdle)
      {
        return true;
      }
      else
      {
        StartTimer();
        return false;
      }
    }
  }
}
```

In des Timers `Elapsed` Ereignis die Rückruffunktion im Verteiler wird aufgerufen, um eine andere Bereinigungszyklus zu starten.

```csharp
void idleTimer_Elapsed(object sender, ElapsedEventArgs args)
{
    lock (thisLock)
    {
        StopTimer();
        isIdle = true;
        Utility.WriteMessageToConsole(
            ResourceHelper.GetString("MsgLeaseExpired"));
        callback(owner);
    }
}
```

Es gibt keine Möglichkeit, den ausgeführten Timer zu erneuern, wenn eine neue Nachricht eingeht, für die Instanz, die in den Leerlaufzustand verschoben wird.

Im Beispiel wird <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementiert, um die Aufrufe der <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>-Methode abzufangen und diese zur `CustomLeaseExtension` weiterzuleiten. Die <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider>-Implementierung ist in der `CustomLifetimeLease`-Klasse enthalten. Die <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> Methode wird aufgerufen, wenn WCF Begriff ist, die Dienstinstanz freizugeben. Es gibt jedoch nur eine Instanz einer bestimmten `ISharedSessionInstance`-Implementierung in der <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider>-Auflistung von ServiceBehavior. Dies bedeutet, dass es keine Möglichkeit wissen darüber zurück, wenn die <xref:System.ServiceModel.InstanceContext> wird geschlossen, die zum Zeitpunkt der WCF überprüft die <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> Methode. Dieses Beispiel verwendet aus diesem Grund Thread sperren, um Anforderungen zum Serialisieren der <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> Methode.

> [!IMPORTANT]
> Die Verwendung der Threadsperre wird nicht empfohlen, da die Leistung der Anwendung durch die Serialisierung deutlich beeinträchtigt werden kann.

Ein privates Memberfeld werden in der `CustomLifetimeLease` Klasse zum Nachverfolgen von des Leerlaufzustand und wird zurückgegeben, indem die <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> Methode. Jedes Mal die <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> -Methode aufgerufen wird, die `isIdle` Feld zurückgegeben wird, und zum Zurücksetzen `false`.  Dieser Wert muss auf `false` festgelegt werden, um sicherzustellen, dass der Verteiler die <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A>-Methode aufruft.

```csharp
public bool IsIdle(InstanceContext instanceContext)
{
    get
    {
        lock (thisLock)
        {
            //...
            bool idleCopy = isIdle;
            isIdle = false;
            return idleCopy;
        }
    }
}
```

Wenn die <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType> Methodenrückgabe `false`, registriert der Verteiler eine Rückruffunktion mit der <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> Methode. Diese Methode empfängt einen Verweis darauf, dass <xref:System.ServiceModel.InstanceContext> freigegeben wird. Aus diesem Grund kann der Beispielcode Abfragen die `ICustomLease` "Erweiterung", und überprüfen Sie die `ICustomLease.IsIdle` Eigenschaft im erweiterten Zustand.

```csharp
public void NotifyIdle(InstanceContextIdleCallback callback,
            InstanceContext instanceContext)
{
    lock (thisLock)
    {
       ICustomLease customLease =
           instanceContext.Extensions.Find<ICustomLease>();
       customLease.Callback = callback;
       isIdle = customLease.IsIdle;
       if (isIdle)
       {
             callback(instanceContext);
       }
    }
}
```

Bevor Sie die `ICustomLease.IsIdle` Eigenschaft aktiviert ist, wird die Callback-Eigenschaft muss festgelegt werden, da dies entscheidend für `CustomLeaseExtension` den Verteiler benachrichtigen, wenn es in den Leerlauf wechselt. Wenn `ICustomLease.IsIdle` `true` zurückgibt, wird der private `isIdle`-Member einfach in `CustomLifetimeLease` auf `true` festgelegt, und die Rückrufmethode wird vom Member aufgerufen. Da der Code eine Sperre enthalten ist, können nicht andere Threads den Wert dieses privaten Members nicht ändern. Das nächste Mal mit dem Verteiler ruft der <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType>, gibt `true` und der Verteiler, die die Instanz freigeben kann.

Jetzt da die Vorarbeit für die benutzerdefinierte Erweiterung abgeschlossen ist, muss sie in das Dienstmodell eingebunden werden. Zum Einbinden der `CustomLeaseExtension` Implementierung, die die <xref:System.ServiceModel.InstanceContext>, WCF bietet der <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> Schnittstelle, führen Sie das bootstrapping von <xref:System.ServiceModel.InstanceContext>. In diesem Beispiel implementiert die `CustomLeaseInitializer`-Klasse diese Schnittstelle und fügt eine `CustomLeaseExtension`-Instanz zur <xref:System.ServiceModel.InstanceContext.Extensions%2A>-Auflistung aus der einzigen Methodeninitialisierung hinzu. Diese Methode wird vom Verteiler aufgerufen, während <xref:System.ServiceModel.InstanceContext> initialisiert wird.

```csharp
public void InitializeInstanceContext(InstanceContext instanceContext,
    System.ServiceModel.Channels.Message message, IContextChannel channel)

    //...

    IExtension<InstanceContext> customLeaseExtension =
        new CustomLeaseExtension(timeout, headerId);
    instanceContext.Extensions.Add(customLeaseExtension);
}
```

 Zum Schluss die <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> Implementierung ist eingebunden in das Dienstmodell mithilfe der <xref:System.ServiceModel.Description.IServiceBehavior> Implementierung. Diese Implementierung wird in der `CustomLeaseTimeAttribute`-Klasse eingefügt, und sie wird außerdem von der `Attribute`-Basisklasse abgeleitet, um dieses Verhalten als Attribut verfügbar zu machen.

```csharp
public void ApplyDispatchBehavior(ServiceDescription description,
           ServiceHostBase serviceHostBase)
{
    CustomLifetimeLease customLease = new CustomLifetimeLease(timeout);

    foreach (ChannelDispatcherBase cdb in serviceHostBase.ChannelDispatchers)
    {
        ChannelDispatcher cd = cdb as ChannelDispatcher;

        if (cd != null)
        {
            foreach (EndpointDispatcher ed in cd.Endpoints)
            {
                ed.DispatchRuntime.InstanceContextProvider = customLease;
            }
        }
    }
}
```

Dieses Verhalten kann einer Beispieldienstklasse hinzugefügt werden, indem es mit dem `CustomLeaseTime`-Attribut kommentiert wird.

```csharp
[CustomLeaseTime(Timeout = 20000)]
public class EchoService : IEchoService
{
  //…
}
```

Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Dienst- und Clientkonsolenfenster angezeigt. Drücken Sie die EINGABETASTE in den einzelnen Konsolenfenstern, um den Dienst und den Client zu schließen.

### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen

1. Stellen Sie sicher, dass Sie durchgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](one-time-setup-procedure-for-the-wcf-samples.md).

2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe erstellen, folgen Sie den Anweisungen im [Erstellen der Windows Communication Foundation-Beispiele](building-the-samples.md).

3. Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen im [Ausführen der Windows Communication Foundation-Beispiele](running-the-samples.md).

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Lifetime`
