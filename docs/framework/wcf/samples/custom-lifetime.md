---
title: Benutzerdefinierte Lebensdauer
ms.date: 08/20/2018
ms.assetid: 52806c07-b91c-48fe-b992-88a41924f51f
ms.openlocfilehash: 8625877d9b4d05d5cf06af2c9f8ef10f701e98db
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715468"
---
# <a name="custom-lifetime"></a>Benutzerdefinierte Lebensdauer

Dieses Beispiel zeigt, wie Sie eine Windows Communication Foundation (WCF)-Erweiterung schreiben, um benutzerdefinierte Lebensdauer Dienste für freigegebene WCF-Dienst Instanzen bereitzustellen.

> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Artikels.

## <a name="shared-instancing"></a>Freigegebene Instanziierung

WCF bietet mehrere Instanziierungsmodi für Ihre Dienst Instanzen. Der freigegebene Instanziierungsmodus, der in diesem Artikel behandelt wird, bietet eine Möglichkeit, eine Dienst Instanz zwischen mehreren Kanälen freizugeben. Clients können eine Factorymethode im Dienst kontaktieren und einen neuen Kanal zum Starten der Kommunikation erstellen. Der folgende Code Ausschnitt zeigt, wie eine Client Anwendung einen neuen Kanal für eine vorhandene Dienst Instanz erstellt:

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

Der freigegebene Instanziierungsmodus unterscheidet sich von anderen Instanziierungsmodi in seiner einzigartigen Methode zum Freigeben von Dienstinstanzen. Wenn alle Kanäle für eine <xref:System.ServiceModel.InstanceContext>geschlossen sind, prüft die WCF-Dienst Laufzeit standardmäßig, ob der Dienst <xref:System.ServiceModel.InstanceContextMode> für <xref:System.ServiceModel.InstanceContextMode.PerCall> oder <xref:System.ServiceModel.InstanceContextMode.PerSession>konfiguriert ist, und wenn dies der Fall ist, wird die Instanz freigegeben, und die Ressourcen werden beansprucht. Wenn ein benutzerdefiniertes <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> verwendet wird, ruft WCF vor der Freigabe der Instanz die <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>-Methode der Anbieter Implementierung auf. Wenn <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> zurückgibt, `true` die Instanz freigegeben wird, ist die Implementierung der <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> für die Benachrichtigung des `Dispatcher` des Leerlauf Zustands mithilfe einer Rückruf Methode verantwortlich. Dies erfolgt durch Aufrufen der <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A>-Methode des Anbieters.

In diesem Beispiel wird veranschaulicht, wie Sie das Freigeben des <xref:System.ServiceModel.InstanceContext> mit einem Leerlauf Timeout von 20 Sekunden verzögern können.

## <a name="extending-the-instancecontext"></a>Erweitern von InstanceContext

In WCF ist <xref:System.ServiceModel.InstanceContext> der Link zwischen der Dienst Instanz und der `Dispatcher`. WCF ermöglicht es Ihnen, diese Laufzeitkomponente zu erweitern, indem Sie mithilfe des erweiterbaren Objekt Musters einen neuen Zustand oder ein neues Verhalten hinzufügen. Das Extensible Object-Muster wird in WCF verwendet, um vorhandene Lauf Zeit Klassen um neue Funktionen zu erweitern oder um neue Zustands Funktionen zu einem Objekt hinzuzufügen. Es gibt drei Schnittstellen im erweiterbaren Objektmuster: <xref:System.ServiceModel.IExtensibleObject%601>, <xref:System.ServiceModel.IExtension%601> und <xref:System.ServiceModel.IExtensionCollection%601>.

Die <xref:System.ServiceModel.IExtensibleObject%601>-Schnittstelle wird von Objekten implementiert, um Erweiterungen zuzulassen, die ihre Funktionalität anpassen.

Die <xref:System.ServiceModel.IExtension%601>-Schnittstelle wird von Objekten implementiert, die Erweiterungen von Klassen des Typs `T` sein können.

Und schließlich handelt es sich bei der <xref:System.ServiceModel.IExtensionCollection%601>-Schnittstelle um eine Auflistung von <xref:System.ServiceModel.IExtension%601>-Implementierungen, die das Abrufen einer Implementierung von <xref:System.ServiceModel.IExtension%601> durch ihren Typ ermöglicht.

Um die <xref:System.ServiceModel.InstanceContext>zu erweitern, müssen Sie daher die <xref:System.ServiceModel.IExtension%601>-Schnittstelle implementieren. In diesem Beispiel Projekt enthält die `CustomLeaseExtension`-Klasse diese Implementierung.

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

Darüber hinaus müssen Sie zur Bereitstellung der erweiterten Lebensdauerunterstützung die erforderliche Implementierung zur Erweiterung hinzufügen. Daher wird die `ICustomLease`-Schnittstelle mit den gewünschten Methoden deklariert und in der `CustomLeaseExtension`-Klasse implementiert.

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

Wenn WCF die <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>-Methode in der <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider>-Implementierung aufruft, wird dieser Aufruf an die <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>-Methode der `CustomLeaseExtension`weitergeleitet. Anschließend prüft der `CustomLeaseExtension` seinen privaten Status, um festzustellen, ob sich die <xref:System.ServiceModel.InstanceContext> im Leerlauf befindet. Wenn Sie sich im Leerlauf befindet, wird `true`zurückgegeben. Andernfalls wird ein Zeitgeber für eine bestimmte erweiterte Lebensdauerperiode gestartet.

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

Im `Elapsed`-Ereignis des Timers wird die Rückruffunktion im Verteiler aufgerufen, um einen weiteren Bereinigungs Prozess zu starten.

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

Es gibt keine Möglichkeit, den ausgelaufenden Timer zu erneuern, wenn eine neue Nachricht für die Instanz eingeht, die in den Leerlauf wechselt.

Im Beispiel wird <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementiert, um die Aufrufe der <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>-Methode abzufangen und diese zur `CustomLeaseExtension` weiterzuleiten. Die <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider>-Implementierung ist in der `CustomLifetimeLease`-Klasse enthalten. Die <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>-Methode wird aufgerufen, wenn WCF die Dienst Instanz freigibt. Es gibt jedoch nur eine Instanz einer bestimmten `ISharedSessionInstance`-Implementierung in der <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider>-Auflistung von ServiceBehavior. Dies bedeutet, dass es nicht möglich ist, zu wissen, ob das <xref:System.ServiceModel.InstanceContext> zu dem Zeitpunkt geschlossen wird, zu dem WCF die <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>-Methode überprüft. Daher wird in diesem Beispiel die Thread Sperre verwendet, um Anforderungen an die <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>-Methode zu serialisieren.

> [!IMPORTANT]
> Die Verwendung der Threadsperre wird nicht empfohlen, da die Leistung der Anwendung durch die Serialisierung deutlich beeinträchtigt werden kann.

Ein privates Member-Feld wird in der `CustomLifetimeLease`-Klasse verwendet, um den Leerlaufzustand zu verfolgen, und wird von der <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>-Methode zurückgegeben. Jedes Mal, wenn die <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>-Methode aufgerufen wird, wird das `isIdle` Feld zurückgegeben und auf `false`zurückgesetzt.  Dieser Wert muss auf `false` festgelegt werden, um sicherzustellen, dass der Verteiler die <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A>-Methode aufruft.

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

Wenn die <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType>-Methode `false`zurückgibt, registriert der Verteiler mithilfe der <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A>-Methode eine Rückruffunktion. Diese Methode empfängt einen Verweis darauf, dass <xref:System.ServiceModel.InstanceContext> freigegeben wird. Aus diesem Grund kann der Beispielcode die `ICustomLease` Typerweiterung Abfragen und die `ICustomLease.IsIdle`-Eigenschaft im erweiterten Zustand überprüfen.

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

Bevor die `ICustomLease.IsIdle`-Eigenschaft aktiviert ist, muss die Callback-Eigenschaft festgelegt werden, da dies für `CustomLeaseExtension` erforderlich ist, damit der Verteiler benachrichtigt wird, wenn er sich im Leerlauf befindet. Wenn `ICustomLease.IsIdle``true` zurückgibt, wird der private `isIdle`-Member einfach in `CustomLifetimeLease` auf `true` festgelegt, und die Rückrufmethode wird vom Member aufgerufen. Da der Code eine Sperre besitzt, können andere Threads den Wert dieses privaten Members nicht ändern. Beim nächsten Aufruf des <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType>wird `true` zurückgegeben, und die Instanz wird von Dispatcher freigegeben.

Jetzt da die Vorarbeit für die benutzerdefinierte Erweiterung abgeschlossen ist, muss sie in das Dienstmodell eingebunden werden. Um die `CustomLeaseExtension`-Implementierung mit dem <xref:System.ServiceModel.InstanceContext>zu verbinden, stellt WCF die <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer>-Schnittstelle bereit, um das Bootstrapping <xref:System.ServiceModel.InstanceContext>auszuführen. In diesem Beispiel implementiert die `CustomLeaseInitializer`-Klasse diese Schnittstelle und fügt eine `CustomLeaseExtension`-Instanz zur <xref:System.ServiceModel.InstanceContext.Extensions%2A>-Auflistung aus der einzigen Methodeninitialisierung hinzu. Diese Methode wird vom Verteiler aufgerufen, während <xref:System.ServiceModel.InstanceContext> initialisiert wird.

```csharp
public void InitializeInstanceContext(InstanceContext instanceContext,
    System.ServiceModel.Channels.Message message, IContextChannel channel)

    //...

    IExtension<InstanceContext> customLeaseExtension =
        new CustomLeaseExtension(timeout, headerId);
    instanceContext.Extensions.Add(customLeaseExtension);
}
```

 Schließlich wird die <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> Implementierung mit dem Dienstmodell verknüpft, indem die <xref:System.ServiceModel.Description.IServiceBehavior>-Implementierung verwendet wird. Diese Implementierung wird in der `CustomLeaseTimeAttribute`-Klasse eingefügt, und sie wird außerdem von der <xref:System.Attribute>-Basisklasse abgeleitet, um dieses Verhalten als Attribut verfügbar zu machen.

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

1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.

2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.

3. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Lifetime`
