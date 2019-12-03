---
title: Initialisierung der Instanziierung
ms.date: 03/30/2017
ms.assetid: 154d049f-2140-4696-b494-c7e53f6775ef
ms.openlocfilehash: ee7d470cb80e913707ae6e92039061efde8fcb7f
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715800"
---
# <a name="instancing-initialization"></a>Initialisierung der Instanziierung
In diesem Beispiel wird das [Pooling](../../../../docs/framework/wcf/samples/pooling.md) -Beispiel erweitert, indem eine Schnittstelle definiert wird, `IObjectControl`, mit der die Initialisierung eines Objekts durch Aktivieren und deaktivieren angepasst wird. Der Client ruft Methoden auf, die das Objekt an den Pool zurückgeben und das Objekt nicht an den Pool zurückgeben.  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
## <a name="extensibility-points"></a>Erweiterungspunkte  
 Der erste Schritt beim Erstellen einer Windows Communication Foundation (WCF)-Erweiterung besteht darin, den zu verwendenden Erweiterbarkeits Punkt zu entscheiden. In WCF bezieht sich der Begriff *EndpointDispatcher* auf eine Laufzeitkomponente, die für die Umstellung eingehender Nachrichten in Methodenaufrufe für den Dienst des Benutzers und zum Umstellen von Rückgabe Werten aus dieser Methode in eine ausgehende Nachricht zuständig ist. Ein WCF-Dienst erstellt einen EndpointDispatcher für jeden Endpunkt.  
  
 Der EndpointDispatcher stellt mithilfe der <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>-Klasse die Erweiterung des Endpunktbereichs bereit (für alle vom Dienst empfangenen oder gesendeten Nachrichten). Mit dieser Klasse können Sie verschiedene Eigenschaften anpassen, die das Verhalten von EndpointDispatcher steuern. In diesem Beispiel wird in erster Linie die <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A>-Eigenschaft behandelt, die auf das Objekt zeigt, das die Instanzen der Dienstklasse bereitstellt.  
  
## <a name="iinstanceprovider"></a>IInstanceProvider  
 In WCF erstellt der EndpointDispatcher Instanzen einer Dienstklasse mithilfe eines Instanzanbieters, der die <xref:System.ServiceModel.Dispatcher.IInstanceProvider>-Schnittstelle implementiert. Diese Schnittstelle verfügt über nur zwei Methoden:  
  
- <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A>: Wenn eine Nachricht eingeht, ruft der Verteiler die <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A>-Methode auf, um eine Instanz der Dienstklasse zum Verarbeiten der Nachricht zu erstellen. Die Häufigkeit der Aufrufe dieser Methode wird von der <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>-Eigenschaft bestimmt. Wenn die <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>-Eigenschaft beispielsweise auf <xref:System.ServiceModel.InstanceContextMode.PerCall?displayProperty=nameWithType> festgelegt ist, wird eine neue Instanz der Dienstklasse erstellt, um alle eingehenden Nachrichten zu verarbeiten. Daher wird <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A> immer dann aufgerufen, wenn eine Nachricht eingeht.  
  
- <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A>: Wenn die Dienstinstanz das Verarbeiten der Nachricht abgeschlossen hat, ruft EndpointDispatcher die <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A>-Methode auf. Wie bei der <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A>-Methode wird die Häufigkeit der Aufrufe dieser Methode von der <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>-Eigenschaft bestimmt.  
  
## <a name="the-object-pool"></a>Der Objektpool  
 Die `ObjectPoolInstanceProvider`-Klasse enthält die Implementierung des Objektpools. Diese Klasse implementiert die <xref:System.ServiceModel.Dispatcher.IInstanceProvider>-Schnittstelle für die Interaktion mit der Dienstmodellebene. Wenn EndpointDispatcher die <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A>-Methode aufruft, erstellt die benutzerdefinierte Implementierung keine neue Instanz, sondern sucht ein vorhandenes Objekt in einem Pool im Speicher. Wenn eines verfügbar ist, wird es zurückgegeben. Andernfalls überprüft `ObjectPoolInstanceProvider`, ob die `ActiveObjectsCount`-Eigenschaft (Anzahl der aus dem Pool zurückgegebenen Objekte) die maximale Poolgröße erreicht hat. Wenn dies nicht der Fall ist, wird eine neue Instanz erstellt und an den Aufrufer zurückgegeben, und anschließend wird `ActiveObjectsCount` inkrementiert. Andernfalls wird eine Objekterstellungsanforderung für einen konfigurierten Zeitraum in die Warteschlange gestellt. Die Implementierung für `GetObjectFromThePool` wird im folgenden Beispielcode dargestellt.  
  
```csharp
private object GetObjectFromThePool()  
{  
    bool didNotTimeout =   
       availableCount.WaitOne(creationTimeout, true);  
    if(didNotTimeout)  
    {  
         object obj = null;  
         lock (poolLock)  
        {  
             if (pool.Count != 0)  
             {  
                   obj = pool.Pop();  
                   activeObjectsCount++;  
             }  
             else if (pool.Count == 0)  
             {  
                   if (activeObjectsCount < maxPoolSize)  
                   {  
                        obj = CreateNewPoolObject();  
                        activeObjectsCount++;  
  
                        #if (DEBUG)  
                        WritePoolMessage(  
                             ResourceHelper.GetString("MsgNewObject"));  
                       #endif  
                   }                          
            }  
           idleTimer.Stop();  
      }  
     // Call the Activate method if possible.  
    if (obj is IObjectControl)  
   {  
         ((IObjectControl)obj).Activate();  
   }  
   return obj;  
}  
throw new TimeoutException(  
ResourceHelper.GetString("ExObjectCreationTimeout"));  
}  
```  
  
 Die benutzerdefinierte `ReleaseInstance`-Implementierung fügt die freigegebene Instanz dem Pool erneut hinzu und dekrementiert den `ActiveObjectsCount`-Wert. EndpointDispatcher kann diese Methoden von unterschiedlichen Threads aus aufrufen. Daher ist ein synchronisierter Zugriff auf die Member der Klassenebene in der `ObjectPoolInstanceProvider`-Klasse erforderlich.  
  
```csharp
public void ReleaseInstance(InstanceContext instanceContext, object instance)  
{  
    lock (poolLock)  
    {  
        // Check whether the object can be pooled.   
        // Call the Deactivate method if possible.  
        if (instance is IObjectControl)  
        {  
            IObjectControl objectControl = (IObjectControl)instance;  
            objectControl.Deactivate();  
  
            if (objectControl.CanBePooled)  
            {  
                pool.Push(instance);  
  
                #if(DEBUG)  
                WritePoolMessage(  
                    ResourceHelper.GetString("MsgObjectPooled"));  
                #endif                          
            }  
            else  
            {  
                #if(DEBUG)  
                WritePoolMessage(  
                    ResourceHelper.GetString("MsgObjectWasNotPooled"));  
                #endif  
            }  
        }  
        else  
        {  
            pool.Push(instance);  
  
            #if(DEBUG)  
            WritePoolMessage(  
                ResourceHelper.GetString("MsgObjectPooled"));  
            #endif   
        }  
  
        activeObjectsCount--;  
  
        if (activeObjectsCount == 0)  
        {  
            idleTimer.Start();                       
        }  
    }  
  
    availableCount.Release(1);  
}  
```  
  
 Die `ReleaseInstance`-Methode bietet eine Bereinigungs Funktion für die *Initialisierung* . Normalerweise wird im Pool eine Mindestanzahl von Objekten für die Lebensdauer des Pools beibehalten. Es kann jedoch Zeiten mit übermäßiger Auslastung geben, für die im Pool zusätzliche Objekte erstellt werden müssen, um die in der Konfiguration festgelegte Höchstgrenze zu erreichen. Wenn der Pool weniger aktiv ist, stellen diese überzähligen Objekte einen zusätzlichen Aufwand dar. Wenn `activeObjectsCount` daher 0 (null) erreicht, wird ein Leerlaufzeitgeber gestartet, der einen Bereinigungszyklus auslöst und ausführt.  
  
```csharp  
if (activeObjectsCount == 0)  
{  
    idleTimer.Start();   
}  
```  
  
 ServiceModel-Ebenenerweiterungen werden mithilfe der folgenden Verhalten verknüpft:  
  
- Dienstverhalten: Diese ermöglichen die Anpassung der ganzen Dienstlaufzeit.  
  
- Endpunktverhalten: Diese ermöglichen das Anpassen eines bestimmten Dienstendpunkts, einschließlich EndpointDispatcher.  
  
- Vertragsverhalten: Diese ermöglichen das Anpassen von <xref:System.ServiceModel.Dispatcher.ClientRuntime>-Klassen oder <xref:System.ServiceModel.Dispatcher.DispatchRuntime>-Klassen auf dem Client bzw. Server.  
  
- Vorgangsverhalten: Diese ermöglichen das Anpassen von <xref:System.ServiceModel.Dispatcher.ClientOperation>-Klassen oder <xref:System.ServiceModel.Dispatcher.DispatchOperation>-Klassen auf dem Client bzw. Server.  
  
 Für den Zweck einer Objektpoolingerweiterung kann ein Endpunktverhalten oder ein Dienstverhalten erstellt werden. In diesem Beispiel wird ein Dienstverhalten verwendet, das die Objektpoolingfähigkeit auf alle Endpunkte des Diensts anwendet. Dienstverhaltensweisen werden durch Implementieren der <xref:System.ServiceModel.Description.IServiceBehavior>-Schnittstelle erstellt. Es gibt mehrere Möglichkeiten, ServiceModel auf die benutzerdefinierten Verhaltensweisen hinzuweisen:  
  
- Verwenden eines benutzerdefinierten Attributs.  
  
- Imperatives Hinzufügen zur Verhaltensauflistung der Dienstbeschreibung.  
  
- Erweitern der Konfigurationsdatei.  
  
 In diesem Beispiel wird ein benutzerdefiniertes Attribut verwendet. Beim Erstellen von <xref:System.ServiceModel.ServiceHost> werden die in der Typdefinition des Diensts verwendeten Attribute untersucht, und die verfügbaren Verhalten werden der Verhaltensauflistung der Dienstbeschreibung hinzugefügt.  
  
 Die <xref:System.ServiceModel.Description.IServiceBehavior>-Schnittstelle verfügt über drei Methoden: <xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A>`,` <xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A>`,` und <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A>. Diese Methoden werden von WCF aufgerufen, wenn die <xref:System.ServiceModel.ServiceHost> initialisiert wird. <xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A?displayProperty=nameWithType> wird zuerst aufgerufen. So kann der Dienst auf Inkonsistenzen untersucht werden. <xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A?displayProperty=nameWithType> wird danach aufgerufen. Diese Methode ist nur in sehr komplexen Szenarios erforderlich. <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A?displayProperty=nameWithType> wird zuletzt aufgerufen und ist für das Konfigurieren der Laufzeit zuständig. Die folgenden Parameter werden in <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A?displayProperty=nameWithType> übergeben:  
  
- `Description`: Dieser Parameter stellt die Dienstbeschreibung für den gesamten Dienst bereit. Dies kann verwendet werden, um Beschreibungsdaten über die Endpunkte, Verträge, Bindungen und andere Daten zu dem Dienst zu überprüfen.  
  
- `ServiceHostBase`: Dieser Parameter stellt die <xref:System.ServiceModel.ServiceHostBase> bereit, die gerade initialisiert wird.  
  
 In der benutzerdefinierten <xref:System.ServiceModel.Description.IServiceBehavior>-Implementierung wird eine neue Instanz von `ObjectPoolInstanceProvider` instanziiert und der <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A>-Eigenschaft in jedem <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> zugewiesen, der <xref:System.ServiceModel.ServiceHostBase> angefügt ist.  
  
```csharp
public void ApplyDispatchBehavior(ServiceDescription description, ServiceHostBase serviceHostBase)  
{  
    if (enabled)  
    {  
        // Create an instance of the ObjectPoolInstanceProvider.  
        instanceProvider = new ObjectPoolInstanceProvider(description.ServiceType,  
        maxPoolSize, minPoolSize, creationTimeout);  
  
        // Assign our instance provider to Dispatch behavior in each   
        // endpoint.  
        foreach (ChannelDispatcherBase cdb in serviceHostBase.ChannelDispatchers)  
        {  
             ChannelDispatcher cd = cdb as ChannelDispatcher;  
             if (cd != null)  
             {  
                 foreach (EndpointDispatcher ed in cd.Endpoints)  
                 {  
                        ed.DispatchRuntime.InstanceProvider = instanceProvider;  
                 }  
             }  
         }  
     }  
}   
```  
  
 Neben einer <xref:System.ServiceModel.Description.IServiceBehavior>-Implementierung verfügt die `ObjectPoolingAttribute`-Klasse über mehrere Member zum Anpassen des Objektpools mithilfe der Attributargumente. Diese Member umfassen `MaxSize`, `MinSize`, `Enabled` und `CreationTimeout` für die Übereinstimmung mit dem von .NET Enterprise Services bereitgestellten Objektpooling-Funktionssatz.  
  
 Das Objektpoolingverhalten kann nun einem WCF-Dienst hinzugefügt werden, indem die Dienst Implementierung mit dem neu erstellten benutzerdefinierten `ObjectPooling`-Attribut kommentiert wird.  
  
```csharp  
[ObjectPooling(MaxSize=1024, MinSize=10, CreationTimeout=30000]      
public class PoolService : IPoolService  
{  
  // …  
}  
```  
  
## <a name="hooking-activation-and-deactivation"></a>Aktivieren und Deaktivieren von Verknüpfungen  
 Das primäre Ziel des Objektpoolings ist das Optimieren von Objekten mit kurzer Lebensdauer und relativ aufwändiger Erstellung und Initialisierung. Bei der richtigen Verwendung kann daher eine erhebliche Leistungssteigerung erreicht werden. Da das Objekt aus dem Pool zurückgegeben wird, wird der Konstruktor nur einmal aufgerufen. Bei einigen Anwendungen ist jedoch eine gewisse Kontrolle erforderlich, damit sie die in einem einzigen Kontext verwendeten Ressourcen initialisieren und bereinigen können. Ein Objekt, das beispielsweise für eine Gruppe von Berechnungen verwendet wird, kann die privaten Felder zurücksetzen, bevor die nächste Berechnung verarbeitet wird. In Enterprise Services wurde diese Art der kontextspezifischen Initialisierung ermöglicht, indem der Objektentwickler die `Activate`-Methode und die `Deactivate`-Methode in der <xref:System.EnterpriseServices.ServicedComponent>-Basisklasse überschreiben konnte.  
  
 Der Objektpool ruft die `Activate`-Methode unmittelbar vor dem Zurückgeben des Objekts aus dem Pool auf. `Deactivate` wird aufgerufen, wenn das Objekt an den Pool zurückgegeben wird. Die <xref:System.EnterpriseServices.ServicedComponent>-Basisklasse verfügt außerdem über die `boolean`-Eigenschaft mit der Bezeichnung `CanBePooled`, mit der der Pool darüber benachrichtigt werden kann, ob das Objekt weiter gepoolt werden kann.  
  
 Im Beispiel wird eine öffentliche Schnittstelle (`IObjectControl`) deklariert, die über die oben genannten Member verfügt, um diese Funktionalität zu imitieren. Diese Schnittstelle wird dann von Dienstklassen implementiert, die die kontextspezifische Initialisierung bereitstellen sollen. Die <xref:System.ServiceModel.Dispatcher.IInstanceProvider>-Implementierung muss geändert werden, um diese Anforderungen zu erfüllen. Wenn Sie jetzt ein Objekt abrufen, indem Sie die `GetInstance`-Methode aufrufen, müssen Sie überprüfen, ob das Objekt implementiert `IObjectControl.` wenn dies der Fall ist. Sie müssen die `Activate`-Methode entsprechend aufrufen.  
  
```csharp  
if (obj is IObjectControl)  
{  
    ((IObjectControl)obj).Activate();  
}  
```  
  
 Beim Zurückgeben eines Objekts an den Pool ist eine Überprüfung für die `CanBePooled`-Eigenschaft erforderlich, bevor das Objekt erneut dem Pool hinzugefügt wird.  
  
```csharp  
if (instance is IObjectControl)  
{  
    IObjectControl objectControl = (IObjectControl)instance;  
    objectControl.Deactivate();  
    if (objectControl.CanBePooled)  
    {  
       pool.Push(instance);  
    }  
}  
```  
  
 Da der Dienstentwickler entscheiden kann, ob ein Objekt gepoolt werden kann, kann die Objektanzahl im Pool zu einem bestimmten Zeitpunkt unter dem Mindestwert liegen. Sie müssen daher überprüfen, ob die Objektanzahl unter dem Mindestwert liegt, und die erforderliche Initialisierung in der Bereinigungsprozedur ausführen.  
  
```csharp  
// Remove the surplus objects.  
if (pool.Count > minPoolSize)  
{  
  // Clean the surplus objects.  
}                      
else if (pool.Count < minPoolSize)  
{  
  // Reinitialize the missing objects.  
  while(pool.Count != minPoolSize)  
  {  
    pool.Push(CreateNewPoolObject());  
  }  
}  
```  
  
 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Dienst- und Clientkonsolenfenster angezeigt. Drücken Sie die EINGABETASTE in den einzelnen Konsolenfenstern, um den Dienst und den Client zu schließen.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
2. Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md), um die Lösung zu erstellen.  
  
3. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Initialization`  
