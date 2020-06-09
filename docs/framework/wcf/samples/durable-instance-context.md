---
title: Permanenter Instanzkontext
ms.date: 03/30/2017
ms.assetid: 97bc2994-5a2c-47c7-927a-c4cd273153df
ms.openlocfilehash: 567ca62d48e80993328548b11f8b59c4fcd355fe
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600593"
---
# <a name="durable-instance-context"></a>Permanenter Instanzkontext

In diesem Beispiel wird veranschaulicht, wie die Windows Communication Foundation (WCF)-Laufzeit angepasst wird, um permanente Instanzkontexte zu aktivieren. Dabei wird als Sicherungsspeicher SQL Server 2005 (in diesem Fall SQL Server 2005 Express) verwendet. Aber es bietet auch eine Möglichkeit, auf benutzerdefinierte Speichermechanismen zuzugreifen.

> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.

Dieses Beispiel umfasst die Erweiterung der Kanal Schicht und der Dienstmodell Ebene von WCF. Deshalb ist es notwendig, das zugrunde liegenden Konzept zu verstehen, bevor Sie sich mit den Implementierungsdetails beschäftigen.

Permanente Instanzkontexte sind sehr häufig in realen Szenarios anzutreffen. Eine Einkaufswagen Anwendung hat beispielsweise die Möglichkeit, den Einkauf an einem anderen Tag in der Mitte anzuhalten und fortzufahren. Wenn der Warenkorb am nächsten Tag geöffnet wird, wird der ursprüngliche Kontext wiederhergestellt. Es ist jedoch unbedingt zu beachten, dass die Warenkorb-Anwendung (auf dem Server) nicht die Warenkorb-Instanz beibehält, während die Verbindung zum Server getrennt ist. Sie behält vielmehr ihren Zustand in einem permanenten Speichermedium bei und verwendet diesen Zustand, wenn eine neue Instanz für den wiederhergestellten Kontext erstellt wird. Aus diesem Grund handelt es sich bei der Dienstinstanz, die möglicherweise für denselben Kontext dient, nicht um dieselbe Instanz wie die vorherige Instanz (d. h. sie hat nicht dieselbe Speicheradresse).

Permanenter Instanzkontext wird durch ein kleines Protokoll ermöglicht, das eine Kontext-ID zwischen dem Client und dem Dienst austauscht. Diese Kontext-ID wird auf dem Client erstellt und zum Dienst übertragen. Wenn die Dienstinstanz erstellt wird, versucht die Dienstlaufzeit den beibehaltenen Zustand zu laden, der dieser Kontext-ID aus einer permanenten Speicherung entspricht (standardmäßig ist es eine SQL Server 2005-Datenbank). Wenn kein Status verfügbar ist, hat die neue Instanz ihren Standardzustand. Die Dienstimplementierung verwendet ein benutzerdefiniertes Attribut, um Vorgänge zu kennzeichnen, die den Zustand der Dienstimplementierung ändern. Die Laufzeit kann dadurch die Dienstinstanz speichern, nachdem die Vorgänge aufgerufen wurden.

Anhand der vorangegangenen Beschreibung können leicht zwei Schritte bestimmt werden, um das Ziel zu erreichen:

1. Ändern Sie die Nachricht, mit der die Kontext-ID übertragen wird.

2. Ändern Sie das lokale Verhalten des Diensts, um die benutzerdefinierte Instanziierungslogik zu implementieren.

Da sich der erste in der Liste auf die Nachrichten bei der Übertragung auswirkt, sollte er als benutzerdefinierter Kanal implementiert und mit der Kanal Schicht verknüpft werden. Der zweite Schritt beeinflusst nur das lokale Verhalten des Diensts und kann deshalb durch das Erweitern mehrerer Diensterweiterungspunkte implementiert werden. In den nächsten Abschnitten wird jede dieser Erweiterungen erläutert.

## <a name="durable-instancecontext-channel"></a>Permanenter InstanceContext-Kanal

Als erstes wird eine Kanalschichterweiterung betrachtet. Der erste Schritt beim Schreiben eines benutzerdefinierten Kanals besteht darin, die Kommunikationsstruktur des Kanals festzulegen. Wenn ein neues Wire-Protokoll eingeführt wird, sollte der Kanal mit fast allen anderen Kanälen im Kanal Stapel funktionieren. Deshalb sollte es alle Nachrichtenaustauschmuster unterstützen. Die Kernfunktionalität des Kanals ändert sich jedoch nicht, unabhängig von seiner Kommunikationsstruktur. Genauer gesagt sollte der Kanal vom Client die Kontext-ID in die Nachrichten schreiben und vom Dienst sollte er diese Kontext-ID aus den Nachrichten lesen und an die höheren Ebenen weiterleiten. Aus diesem Grund wird eine `DurableInstanceContextChannelBase`-Klasse erstellt, die als die abstrakte Basisklasse für alle Implementierungen von permanenten Instanzkontext-Kanälen handelt. Diese Klasse enthält die allgemeinen Computerverwaltungsfunktionen und zwei geschützte Member, um die Kontextinformationen auf Nachrichten anzuwenden und von ihnen zu lesen.

```csharp
class DurableInstanceContextChannelBase
{
  //…
  protected void ApplyContext(Message message)
  {
    //…
  }
  protected string ReadContextId(Message message)
  {
    //…
  }
}
```

Diese beiden Methoden nutzen `IContextManager`-Implementierungen, um die Kontext-ID auf Nachrichten zu schreiben und von ihnen zu lesen. ( `IContextManager` eine benutzerdefinierte Schnittstelle, die verwendet wird, um den Vertrag für alle Kontext-Manager zu definieren.) Der Kanal kann entweder die Kontext-ID in einem benutzerdefinierten SOAP-Header oder in einem HTTP-Cookie-Header enthalten. Jede Kontextmanagerimplementierung erbt von der `ContextManagerBase`-Klasse, die die allgemeine Funktionalität für alle Kontextmanager enthält. Die `GetContextId`-Methode in dieser Klasse wird verwendet, um die Kontext-ID vom Client zu erzeugen. Wenn eine Kontext-ID ist zum ersten Mal erzeugt wird, wird sie mithilfe dieser Methode in einer Textdatei gespeichert, deren Name von der Remote-Endpunktadresse erstellt wird (in den typischen URI werden ungültige Zeichen im Dateinamen durch @-Zeichen ersetzt).

Wird die Kontext-ID später für denselben Remote-Endpunkt benötigt, überprüft diese Methode, ob eine entsprechende Datei vorhanden ist. Wenn dies der Fall ist, liest sie die Kontext-ID und gibt sie zurück. Andernfalls gibt sie eine neu generierte Kontext-ID zurück und speichert sie in einer Datei. Mit der Standardkonfiguration werden diese Dateien in einem Verzeichnis namens "contextstore" abgelegt, das sich im temporären Verzeichnis des aktuellen Benutzers befindet. Dieser Speicherort ist jedoch mit dem Bindungselement konfigurierbar.

Der für den Transport der Kontext-ID verwendete Mechanismus kann konfiguriert werden. Er kann entweder in den HTTP-Cookieheader oder einen benutzerdefinierten SOAP-Header geschrieben werden. Wenn Sie sich für den benutzerdefinierten SOAP-Header entscheiden, kann dieses Protokoll mit anderen als HTTP-Protokollen (z. B. TCP oder Benannte Pipes) verwendet werden. Es gibt zwei Klassen, nämlich `MessageHeaderContextManager` und `HttpCookieContextManager`, die diese beiden Optionen implementieren.

Beide Klassen schreiben die Kontext-ID richtig in die Nachricht. Die `MessageHeaderContextManager`-Klasse schreibt sie beispielsweise in einen SOAP-Header in der `WriteContext`-Methode.

```csharp
public override void WriteContext(Message message)
{
  string contextId = this.GetContextId();

  MessageHeader contextHeader =
    MessageHeader.CreateHeader(DurableInstanceContextUtility.HeaderName,
      DurableInstanceContextUtility.HeaderNamespace,
      contextId,
      true);

  message.Headers.Add(contextHeader);
}
```

Sowohl die `ApplyContext`-Methode als auch die `ReadContextId`-Methode in der `DurableInstanceContextChannelBase`-Klasse rufen `IContextManager.ReadContext` bzw. `IContextManager.WriteContext` auf. Diese Kontext-Manager werden jedoch nicht direkt von der `DurableInstanceContextChannelBase`-Klasse erstellt. Diese Aufgabe wird von der `ContextManagerFactory`-Klasse ausgeführt.

```csharp
IContextManager contextManager =
                ContextManagerFactory.CreateContextManager(contextType,
                this.contextStoreLocation,
                this.endpointAddress);
```

Die `ApplyContext`-Methode wird von den Sendekanälen aufgerufen. Sie fügt die Kontext-ID in die ausgehenden Nachrichten ein. Die `ReadContextId`-Methode wird von den Empfangskanälen aufgerufen. Diese Methode stellt sicher, dass die Kontext-ID in den eingehenden Nachrichten verfügbar ist und fügt sie zur `Properties`-Auflistung der `Message`-Klasse hinzu. Wenn ein Fehler beim Lesen der Kontext-ID auftritt und der Kanal abgebrochen wird, löst diese Methode eine `CommunicationException` aus.

```csharp
message.Properties.Add(DurableInstanceContextUtility.ContextIdProperty, contextId);
```

Bevor Sie fortfahren, ist es wichtig, die Verwendung der `Properties`-Auflistung in der `Message`-Klasse zu verstehen. In der Regel wird diese `Properties`-Auflistung verwendet, wenn Daten von unteren an die obere Ebenen der Kanalschicht weitergegeben werden. So können die gewünschten Daten den oberen Ebenen konsistent und unabhängig von den Protokolldetails zur Verfügung gestellt werden. Das heißt, die Kanal Ebene kann die Kontext-ID senden und als SOAP-Header oder HTTP-Cookie-Header empfangen. Die oberen Ebenen müssen diese Details jedoch nicht kennen, da die Kanalschicht diese Informationen in der `Properties`-Auflistung verfügbar macht.

Wenn die `DurableInstanceContextChannelBase`-Klasse vorhanden ist, müssen alle zehn erforderlichen Schnittstellen (IOutputChannel, IInputChannel, IOutputSessionChannel, IInputSessionChannel, IRequestChannel, IReplyChannel, IRequestSessionChannel, IReplySessionChannel, IDuplexChannel, IDuplexSessionChannel) implementiert werden. Sie ähneln jedem verfügbaren Nachrichtenaustausch Muster (Datagram, Simplex, Duplex und ihren Sitzungs basierten Varianten). Jede dieser Implementierungen erbt die zuvor beschriebene Basisklasse und ruft `ApplyContext` und `ReadContextId` entsprechend auf. So ruft beispielsweise `DurableInstanceContextOutputChannel` – die die IOutputChannel-Schnittstelle implementiert – die `ApplyContext`-Methode von jeder Methode auf, die Nachrichten sendet.

```csharp
public void Send(Message message, TimeSpan timeout)
{
    // Apply the context information before sending the message.
    this.ApplyContext(message);
    //…
}
```

Auf der anderen Seite, `DurableInstanceContextInputChannel` die die- `IInputChannel` Schnittstelle implementiert, ruft die- `ReadContextId` Methode in jeder Methode auf, die die Nachrichten empfängt.

```csharp
public Message Receive(TimeSpan timeout)
{
    //…
      ReadContextId(message);
      return message;
}
```

Außerdem delegieren diese Kanalimplementierungen die Methodenaufrufe an den nächst unteren Kanal im Kanalstapel. Sitzungsbasierte Varianten verfügen jedoch über eine Grundlogik, um sicherzustellen, dass die Kontext-ID gesendet und nur für die erste Nachricht gelesen wird, aufgrund derer die Sitzung erstellt wurde.

```csharp
if (isFirstMessage)
{
//…
    this.ApplyContext(message);
    isFirstMessage = false;
}
```

Diese Channelimplementierungen werden dann der WCF-Channel-Laufzeit von der `DurableInstanceContextBindingElement` -Klasse und der- `DurableInstanceContextBindingElementSection` Klasse entsprechend hinzugefügt. Weitere Informationen zu Bindungs Elementen und Bindungs Element Abschnitten finden Sie in der Beispiel Dokumentation zum [HttpCookieSession](httpcookiesession.md) -Channel.

## <a name="service-model-layer-extensions"></a>Erweiterungen der Dienstmodellebene

Nachdem nun die Kontext-ID die Kanalschicht durchlaufen hat, kann das Dienstverhalten implementiert werden, um die Instanziierung benutzerspezifisch anzupassen. In diesem Beispiel wird ein Speicher-Manager verwendet, um den Zustand aus dem permanenten Speicher zu laden und in ihm zu speichern. Wie bereits erläutert arbeitet dieses Beispiel mit einem Speicher-Manager, der SQL Server 2005 als Sicherungsspeicher verwendet. Es ist aber auch möglich, benutzerdefinierte Speichermechanismen zu dieser Erweiterung hinzuzufügen. Dazu wird eine öffentliche Schnittstelle deklariert, die von allen Speicher-Managern implementiert werden muss.

```csharp
public interface IStorageManager
{
    object GetInstance(string contextId, Type type);
    void SaveInstance(string contextId, object state);
}
```

Die `SqlServerStorageManager`-Klasse enthält die `IStorageManager`-Standardimplementierung. In der `SaveInstance` -Methode wird das angegebene Objekt mit dem XmlSerializer serialisiert und in der SQL Server-Datenbank gespeichert.

```csharp
XmlSerializer serializer = new XmlSerializer(state.GetType());
string data;

using (StringWriter writer = new StringWriter(CultureInfo.InvariantCulture))
{
    serializer.Serialize(writer, state);
    data = writer.ToString();
}

using (SqlConnection connection = new SqlConnection(GetConnectionString()))
{
    connection.Open();

    string update = @"UPDATE Instances SET Instance = @instance WHERE ContextId = @contextId";

    using (SqlCommand command = new SqlCommand(update, connection))
    {
        command.Parameters.Add("@instance", SqlDbType.VarChar, 2147483647).Value = data;
        command.Parameters.Add("@contextId", SqlDbType.VarChar, 256).Value = contextId;

        int rows = command.ExecuteNonQuery();

        if (rows == 0)
        {
            string insert = @"INSERT INTO Instances(ContextId, Instance) VALUES(@contextId, @instance)";
            command.CommandText = insert;
            command.ExecuteNonQuery();
        }
    }
}
```

In der- `GetInstance` Methode werden die serialisierten Daten für eine angegebene Kontext-ID gelesen, und das Objekt, das daraus erstellt wird, wird an den Aufrufer zurückgegeben.

```csharp
object data;
using (SqlConnection connection = new SqlConnection(GetConnectionString()))
{
    connection.Open();

    string select = "SELECT Instance FROM Instances WHERE ContextId = @contextId";
    using (SqlCommand command = new SqlCommand(select, connection))
    {
        command.Parameters.Add("@contextId", SqlDbType.VarChar, 256).Value = contextId;
        data = command.ExecuteScalar();
    }
}

if (data != null)
{
    XmlSerializer serializer = new XmlSerializer(type);
    using (StringReader reader = new StringReader((string)data))
    {
        object instance = serializer.Deserialize(reader);
        return instance;
    }
}
```

Benutzer dieser Speicher-Manager sollten sie nicht direkt instanziieren. Sie verwenden die `StorageManagerFactory`-Klasse, die von den Speichermanagererstellungsdetails abstrahiert wird. Diese Klasse verfügt über einen statischen Member, `GetStorageManager`, der eine Instanz eines gegebenen Speichermanagertyps erstellt. Wenn der Typparameter `null` lautet, erstellt diese Methode eine Instanz der `SqlServerStorageManager`-Standardklasse und gibt diese zurück. Sie überprüft auch den gegebenen Typ, um sicherzustellen, dass er die `IStorageManager`-Schnittstelle implementiert.

```csharp
public static IStorageManager GetStorageManager(Type storageManagerType)
{
IStorageManager storageManager = null;

if (storageManagerType == null)
{
    return new SqlServerStorageManager();
}
else
{
    object obj = Activator.CreateInstance(storageManagerType);

    // Throw if the specified storage manager type does not
    // implement IStorageManager.
    if (obj is IStorageManager)
    {
        storageManager = (IStorageManager)obj;
    }
    else
    {
        throw new InvalidOperationException(
                  ResourceHelper.GetString("ExInvalidStorageManager"));
    }

    return storageManager;
}
}
```

Die notwendige Infrastruktur zum Lesen und Schreiben von Instanzen aus dem permanenten Speicher wurde implementiert. Jetzt müssen die notwendigen Schritte zum Ändern des Dienstverhaltens durchgeführt werden.

Zuerst muss die Kontext-ID gespeichert werden, die über die Kanalschicht zur aktuellen InstanceContext übertragen wurde. InstanceContext ist eine Laufzeitkomponente, die als Link zwischen dem WCF-Verteiler und der Dienst Instanz fungiert. Sie kann verwendet werden, um der Dienstinstanz einen zusätzlichen Zustand und zusätzliches Verhalten bereitzustellen. Dies ist notwendig, da die Kontext-ID in einer sitzungsbasierten Kommunikation nur mit der ersten Nachricht gesendet wird.

WCF ermöglicht die Erweiterung der InstanceContext-Laufzeitkomponente durch Hinzufügen eines neuen Zustands und Verhaltens mithilfe des erweiterbaren Objekt Musters. Das Extensible Object-Muster wird in WCF verwendet, um vorhandene Lauf Zeit Klassen um neue Funktionen zu erweitern oder um neue Zustands Funktionen zu einem Objekt hinzuzufügen. Es gibt drei Schnittstellen im Extensible Object Pattern-IExtensibleObject \<T> , IExtension \<T> und IExtensionCollection \<T> :

- Die IExtensibleObject- \<T> Schnittstelle wird von Objekten implementiert, die Erweiterungen zulassen, die ihre Funktionalität anpassen.

- Die IExtension- \<T> Schnittstelle wird von Objekten implementiert, die Erweiterungen von Klassen des Typs T sind.

- Die IExtensionCollection- \<T> Schnittstelle ist eine Auflistung von iextensions, die das Abrufen von iextensions nach ihrem Typ ermöglicht.

Es sollte deshalb eine InstanceContextExtension-Klasse erstellt werden, die die IExtension-Schnittstelle implementiert und den erforderlichen Zustand zum Speichern der Kontext-ID definiert. Diese Klasse bietet auch den Zustand, um den verwendeten Speicher-Manager aufzunehmen. Sobald der neue Zustand gespeichert ist, sollte es nicht mehr möglich sein, ihn zu ändern. Deshalb wird der Zustand zum Erstellungszeitpunkt bereitgestellt und in der Instanz gespeichert. Anschließend kann nur über schreibgeschützte Eigenschaften darauf zugegriffen werden.

```csharp
// Constructor
public DurableInstanceContextExtension(string contextId,
            IStorageManager storageManager)
{
    this.contextId = contextId;
    this.storageManager = storageManager;
}

// Read only properties
public string ContextId
{
    get { return this.contextId; }
}

public IStorageManager StorageManager
{
    get { return this.storageManager; }
}
```

Die InstanceContextInitializer-Klasse implementiert die IInstanceContextInitializer-Schnittstelle und fügt die Instanzkontexterweiterung zur Erweiterungsauflistung der erstellten Komponente InstanceContext hinzu.

```csharp
public void Initialize(InstanceContext instanceContext, Message message)
{
    string contextId =
  (string)message.Properties[DurableInstanceContextUtility.ContextIdProperty];

    DurableInstanceContextExtension extension =
                new DurableInstanceContextExtension(contextId,
                     storageManager);
    instanceContext.Extensions.Add(extension);
}
```

Wie bereits beschrieben wird die Kontext-ID von der `Properties`-Auflistung der `Message`-Klasse gelesen und an den Konstruktor der Erweiterungsklasse weitergegeben. Dadurch wird veranschaulicht, wie Informationen zwischen den Schichten konsistent ausgetauscht werden können.

Im nächsten wichtigen Schritt wird der Vorgang zum Erstellen der Dienstinstanz überschrieben. WCF ermöglicht die Implementierung von benutzerdefinierten Instanziierungsverhaltensweisen und das Einbinden dieser Verhaltensweisen in die Laufzeit mithilfe der IInstanceProvider-Schnittstelle. Die neue `InstanceProvider`-Klasse wird implementiert, um diese Aufgabe auszuführen. Der vom Instanzanbieter erwartete Diensttyp wird im Konstruktor akzeptiert. Später wird dies verwendet, um neue Instanzen zu erstellen. In der- `GetInstance` Implementierung wird eine Instanz eines Speicher-Managers erstellt, die nach einer permanenten Instanz sucht. Wenn zurück `null` gegeben wird, wird eine neue Instanz des Dienst Typs instanziiert und an den Aufrufer zurückgegeben.

```csharp
public object GetInstance(InstanceContext instanceContext, Message message)
{
    object instance = null;

    DurableInstanceContextExtension extension =
    instanceContext.Extensions.Find<DurableInstanceContextExtension>();

    string contextId = extension.ContextId;
    IStorageManager storageManager = extension.StorageManager;

    instance = storageManager.GetInstance(contextId, serviceType);

    instance ??= Activator.CreateInstance(serviceType);
    return instance;
}
```

Der nächste wichtige Schritt besteht darin, die `InstanceContextExtension` `InstanceContextInitializer` -,-und- `InstanceProvider` Klassen in der Dienstmodell Laufzeit zu installieren. Es kann ein benutzerdefiniertes Attribut verwendet werden, um die Dienstimplementierungsklassen für die Installation des Verhaltens zu kennzeichnen. `DurableInstanceContextAttribute` enthält die Implementierung für dieses Attribut und implementiert die `IServiceBehavior`-Schnittstelle, um die gesamte Dienstlaufzeit zu erweitern.

Diese Klasse verfügt über eine Eigenschaft, die den Typ des zu verwendenden Speicher-Managers akzeptiert. Auf diese Weise ermöglicht die-Implementierung den Benutzern, ihre eigene `IStorageManager` Implementierung als Parameter dieses Attributs anzugeben.

In der- `ApplyDispatchBehavior` Implementierung `InstanceContextMode` wird der des aktuellen `ServiceBehavior` Attributs überprüft. Wenn diese Eigenschaft auf "Singleton" festgelegt ist, kann keine permanente Instanziierung aktualisiert werden und `InvalidOperationException` wird ausgelöst, um den Host zu benachrichtigen.

```csharp
ServiceBehaviorAttribute serviceBehavior =
    serviceDescription.Behaviors.Find<ServiceBehaviorAttribute>();

if (serviceBehavior != null &&
     serviceBehavior.InstanceContextMode == InstanceContextMode.Single)
{
    throw new InvalidOperationException(
       ResourceHelper.GetString("ExSingletonInstancingNotSupported"));
}
```

Anschließend werden die Instanzen des Speicher-Managers, des Instanzkontextinitialisierers und des Instanzenanbieters erstellt und in der für jeden Endpunkt erstellten `DispatchRuntime` installiert.

```csharp
IStorageManager storageManager =
    StorageManagerFactory.GetStorageManager(storageManagerType);

InstanceContextInitializer contextInitializer =
    new InstanceContextInitializer(storageManager);

InstanceProvider instanceProvider =
    new InstanceProvider(description.ServiceType);

foreach (ChannelDispatcherBase cdb in serviceHostBase.ChannelDispatchers)
{
    ChannelDispatcher cd = cdb as ChannelDispatcher;

    if (cd != null)
    {
        foreach (EndpointDispatcher ed in cd.Endpoints)
        {
            ed.DispatchRuntime.InstanceContextInitializers.Add(contextInitializer);
            ed.DispatchRuntime.InstanceProvider = instanceProvider;
        }
    }
}
```

Bisher resultiert aus diesem Beispiel ein Kanal, der das benutzerdefinierte Versandprotokoll für den Austausch der benutzerdefinierten Kontext-ID aktiviert hat. Außerdem überschreibt es das Standardinstanziierungsverhalten, die Instanzen aus dem permanenten Speicher zu laden.

Nun muss nur noch die Dienstinstanz im permanenten Speicher gespeichert werden. Wie zuvor erläutert gibt es bereits die erforderliche Funktionalität, den Zustand in einer `IStorageManager`-Implementierung zu speichern. Wir müssen dies jetzt in die WCF-Laufzeit integrieren. Es ist ein weiteres Attribut erforderlich, dass auf die Methoden in der Dienstimplementierungsklasse angewendet werden kann. Dieses Attribut soll auf die Methoden angewendet werden, die den Zustand der Dienstinstanz ändern.

Die `SaveStateAttribute`-Klasse implementiert diese Funktionalität. Außerdem implementiert es `IOperationBehavior` die-Klasse, um die WCF-Laufzeit für jeden Vorgang zu ändern. Wenn eine Methode mit diesem Attribut markiert ist, ruft die WCF-Laufzeit die-Methode auf, `ApplyBehavior` während die entsprechende `DispatchOperation` erstellt wird. Diese Methoden Implementierung enthält eine einzelne Codezeile:

```csharp
dispatch.Invoker = new OperationInvoker(dispatch.Invoker);
```

Die Anweisung erstellt eine Instanz des `OperationInvoker`-Typs und weist sie zur `Invoker`-Eigenschaft des erstellten `DispatchOperation` zu. Die `OperationInvoker`-Klasse ist ein Wrapper des Standardvorgangaufrufers, der für `DispatchOperation` erstellt wurde. Diese Klasse implementiert die `IOperationInvoker`-Schnittstelle. In der `Invoke` Methoden Implementierung wird der tatsächliche Methodenaufruf an den inneren Vorgangs Aufruf delegiert. Bevor die Ergebnisse jedoch zurückgegeben werden, wird mit dem Speicher-Manager in `InstanceContext` die Dienstinstanz gespeichert.

```csharp
object result = innerOperationInvoker.Invoke(instance,
    inputs, out outputs);

// Save the instance using the storage manager saved in the
// current InstanceContext.
InstanceContextExtension extension =
    OperationContext.Current.InstanceContext.Extensions.Find<InstanceContextExtension>();

extension.StorageManager.SaveInstance(extension.ContextId, instance);
return result;
```

## <a name="using-the-extension"></a>Verwenden der Erweiterung

Die Erweiterungen der channelschicht und der Dienstmodell Ebene sind abgeschlossen und können nun in WCF-Anwendungen verwendet werden. Dienste müssen den Kanal mithilfe einer benutzerdefinierten Bindung zum Kanal Stapel hinzufügen und dann die Dienst Implementierungsklassen mit den entsprechenden Attributen markieren.

```csharp
[DurableInstanceContext]
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]
public class ShoppingCart : IShoppingCart
{
//…
     [SaveState]
     public int AddItem(string item)
     {
         //…
     }
//…
 }
```

Clientanwendungen müssen den DurableInstanceContextChannel mit einer benutzerdefinierten Bindung zum Kanalstapel hinzufügen. Um den Kanal deklarativ in der Konfigurationsdatei zu konfigurieren, muss der Bindungselementbereich zur Auflistung der Bindungselementerweiterungen hinzugefügt werden.

```xml
<system.serviceModel>
 <extensions>
   <bindingElementExtensions>
     <add name="durableInstanceContext"
type="Microsoft.ServiceModel.Samples.DurableInstanceContextBindingElementSection, DurableInstanceContextExtension, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null"/>
   </bindingElementExtensions>
 </extensions>
</system.serviceModel>
```

Jetzt kann das Bindungselement wie andere Standardbindungselemente mit einer benutzerdefinierten Bindung verwendet werden:

```xml
<bindings>
 <customBinding>
   <binding name="TextOverHttp">
     <durableInstanceContext contextType="HttpCookie"/>
     <reliableSession />
     <textMessageEncoding />
     <httpTransport />
   </binding>
 </customBinding>
</bindings>
```

## <a name="conclusion"></a>Zusammenfassung

In diesem Beispiel wurde gezeigt, wie ein benutzerdefinierter Protokollkanal erstellt wird und wie das Dienstverhalten angepasst werden muss, um diesen Protokollkanal zu aktivieren.

Die Erweiterung kann weiter verbessert werden, wenn Benutzer die `IStorageManager`-Implementierung mit einem Konfigurationsabschnitt angeben können. Dadurch kann der Sicherungsspeicher geändert werden, ohne den Dienstcode neu zu kompilieren.

Außerdem können Sie versuchen, eine Klasse zu implementieren (z. B. `StateBag`), die den Zustand der Instanz kapselt. Diese Klasse ist für das Beibehalten des Zustands verantwortlich, wenn er sich ändert. Sie können so die Verwendung des `SaveState`-Attributs vermeiden und die bestehenden Aufgaben genauer ausführen (Sie können z. B. den Zustand beibehalten, wenn der Zustand geändert wird, anstatt ihn jedes Mal zu speichern, wenn eine Methode mit dem `SaveState`-Attribut aufgerufen wird).

Wenn Sie das Beispiel ausführen, wird die folgende Ausgabe angezeigt: Der Client fügt zwei Elemente zum Warenkorb hinzu und erhält dann vom Dienst die Liste der Elemente im Warenkorb. Drücken Sie die EINGABETASTE in den einzelnen Konsolenfenstern, um den Dienst und den Client zu schließen.

```console
Enter the name of the product: apples
Enter the name of the product: bananas

Shopping cart currently contains the following items.
apples
bananas
Press ENTER to shut down client
```

> [!NOTE]
> Durch erneutes Erstellen des Diensts wird die Datenbankdatei überschrieben. Wenn Sie den Zustand überwachen möchten, der während mehrerer Durchläufe des Beispiels beibehalten wurde, erstellen Sie das Beispiel zwischen den einzelnen Durchläufen nicht neu.

#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen

1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.

2. Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](building-the-samples.md), um die Lösung zu erstellen.

3. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).

> [!NOTE]
> Um dieses Beispiel auszuführen, muss SQL Server 2005 oder SQL Express 2005 ausgeführt werden. Wenn Sie SQL Server 2005 ausführen, müssen Sie die Konfiguration der Verbindungszeichenfolge des Diensts ändern. Wenn Sie das Beispiel computerübergreifend ausführen, ist SQL Server nur auf dem Servercomputer erforderlich.

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Durable`
