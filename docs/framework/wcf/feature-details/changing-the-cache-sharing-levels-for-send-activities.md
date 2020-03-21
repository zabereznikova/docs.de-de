---
title: Ändern der Cachefreigabeebenen für Send-Aktivitäten
ms.date: 03/30/2017
ms.assetid: 03926a64-753d-460e-ac06-2a4ff8e1bbf5
ms.openlocfilehash: 101aab98a7d34ad45ad29efbe252cff0814ca290
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185398"
---
# <a name="changing-the-cache-sharing-levels-for-send-activities"></a>Ändern der Cachefreigabeebenen für Send-Aktivitäten
Mit der Erweiterung <xref:System.ServiceModel.Activities.SendMessageChannelCache> können Sie die Cachefreigabeebenen, die Einstellungen des Kanalfactorycaches und die Einstellungen des Kanalcaches für Workflows anpassen, die Nachrichten mit <xref:System.ServiceModel.Activities.Send>-Messagingaktivitäten an Dienstendpunkte senden. Diese Workflows sind in der Regel Clientworkflows, könnten jedoch auch Workflowdienste sein, die in einem <xref:System.ServiceModel.WorkflowServiceHost> gehostet werden. Der Kanalfactorycache enthält zwischengespeicherte <xref:System.ServiceModel.ChannelFactory%601>-Objekte. Der Kanalcache enthält zwischengespeicherte Kanäle.  
  
> [!NOTE]
> Workflows können mittels <xref:System.ServiceModel.Activities.Send>-Messagingaktivitäten Nachrichten oder Parameter senden. Die Workflowlaufzeit fügt dem Cache Kanalfactorys hinzu, die Kanäle vom Typ <xref:System.ServiceModel.Channels.IRequestChannel> erstellen, wenn Sie eine <xref:System.ServiceModel.Activities.ReceiveReply>-Aktivität mit einer <xref:System.ServiceModel.Activities.Send>-Aktivität verwenden, bzw. einen Kanal vom Typ <xref:System.ServiceModel.Channels.IOutputChannel>, wenn Sie nur eine <xref:System.ServiceModel.Activities.Send>-Aktivität (kein <xref:System.ServiceModel.Activities.ReceiveReply>) verwenden.  
  
## <a name="the-cache-sharing-levels"></a>Die Cachefreigabeebenen  
 In einem von einem <xref:System.ServiceModel.WorkflowServiceHost> gehosteten Workflow wird der von <xref:System.ServiceModel.Activities.Send>-Messagingaktivitäten verwendete Cache von allen Workflowinstanzen auf dem <xref:System.ServiceModel.WorkflowServiceHost> gemeinsam genutzt (Zwischenspeicherung auf Hostebene). Bei einen Clientworkflow, der nicht von einem <xref:System.ServiceModel.WorkflowServiceHost> gehostet wird, steht der Cache nur der Workflowinstanz zur Verfügung (Zwischenspeichern auf Instanzebene). Der Cache ist nur verfügbar für <xref:System.ServiceModel.Activities.Send>-Aktivitäten, die keine in der Konfiguration definierten Endpunkte verwenden, es sei denn, die Zwischenspeicherung im unsicheren Modus wurde aktiviert.  
  
 Im Folgenden sind die unterschiedlichen Cachefreigabeebenen für <xref:System.ServiceModel.Activities.Send>-Aktivitäten in einem Workflow mit Empfehlungen zur Verwendung aufgelistet:  
  
- **Hostebene:** Auf der Hostfreigabeebene ist der Cache nur für die Workflowinstanzen verfügbar, die auf dem Workflowdiensthost gehostet werden. Ein Cache kann auch prozessweit für mehrere Workflowdiensthosts freigegeben werden.  
  
- **Instanzebene**: Auf der Ebenenfreigabeebene ist der Cache während seiner gesamten Lebensdauer für eine bestimmte Workflowinstanz verfügbar, für andere Workflowinstanzen jedoch nicht verfügbar.  
  
- **Kein Cache**: Der Cache ist standardmäßig deaktiviert, wenn Sie über einen Workflow verfügen, der Endpunkte verwendet, die in der Konfiguration definiert sind. Es wird empfohlen, den Cache in diesem Fall nicht zu aktivieren, da dies unsicher sein kann. Beispiel: Wenn eine andere Identität (andere Anmeldeinformationen oder Identitätswechsel) für jeden Sendevorgang benötigt wird.  
  
## <a name="changing-the-cache-sharing-level-for-a-client-workflow"></a>Ändern der Cachefreigabeebene für einen Clientworkflow  
 Um die Cachefreigabe für einen Clientworkflow festzulegen, fügen Sie dem gewünschten Satz von Workflowinstanzen eine Instanz der <xref:System.ServiceModel.Activities.SendMessageChannelCache>-Klasse als Erweiterung hinzu. So wird der Cache für alle Workflowinstanzen freigegeben. In den folgenden Codebeispielen wird die Ausführung dieser Schritte veranschaulicht.  
  
 Deklarieren Sie zuerst eine Instanz vom Typ <xref:System.ServiceModel.Activities.SendMessageChannelCache>.  
  
```csharp  
// Create an instance of SendMessageChannelCache with default cache settings.  
static SendMessageChannelCache sharedChannelCacheExtension =  
    new SendMessageChannelCache();  
```  
  
 Fügen Sie dann jeder einzelnen Clientworkflowinstanz die Cacheerweiterung hinzu.  
  
```csharp
WorkflowApplication clientInstance1 = new WorkflowApplication(new clientWorkflow1());  
WorkflowApplication clientInstance2 = new WorkflowApplication(new clientWorkflow2());  
  
// Share the cache extension object
  
clientInstance1.Extensions.Add(sharedChannelCacheExtension);  
clientInstance2.Extensions.Add(sharedChannelCacheExtension);  
```  
  
## <a name="changing-the-cache-sharing-level-for-a-hosted-workflow-service"></a>Ändern der Cachefreigabeebene für einen gehosteten Workflowdienst  
 Um die Cachefreigabe für einen gehosteten Workflowdienst festzulegen, fügen Sie allen Workflowdiensthosts eine Instanz der <xref:System.ServiceModel.Activities.SendMessageChannelCache>-Klasse als Erweiterung hinzu. So wird der Cache für alle Workflowdiensthosts freigegeben. In den folgenden Codebeispielen wird die Ausführung dieser Schritte veranschaulicht.  
  
 Deklarieren Sie zuerst eine Instanz vom Typ <xref:System.ServiceModel.Activities.SendMessageChannelCache> auf Klassenebene.  
  
```csharp  
// Create static instance of SendMessageChannelCache with default cache settings.  
static SendMessageChannelCache sharedChannelCacheExtension = new  
    SendMessageChannelCache();  
```  
  
 Fügen Sie dann jedem einzelnen Workflowdiensthost die statische Cacheerweiterung hinzu.  
  
```csharp  
WorkflowServiceHost host1 = new WorkflowServiceHost(new serviceWorkflow1(), new Uri(baseAddress1));  
WorkflowServiceHost host2 = new WorkflowServiceHost(new serviceWorkflow2(), new Uri(baseAddress2));  
  
// Share the static cache to get an AppDomain level cache.  
host1.WorkflowExtensions.Add(sharedChannelCacheExtension);  
host2.WorkflowExtensions.Add(sharedChannelCacheExtension);  
```  
  
 Um die Cachefreigabe für einen gehosteten Workflowdienst auf Instanzebene festzulegen, fügen Sie dem Workflowdiensthost einen `Func<SendMessageChannelCache>`-Delegaten als Erweiterung hinzu, und weisen Sie diesen Delegaten dem Code hinzu, der eine neue Instanz der <xref:System.ServiceModel.Activities.SendMessageChannelCache>-Klasse instanziiert. Auf diese Weise wird für jede einzelne Workflowinstanz ein anderer Cache verwendet. Im folgenden Codebeispiel wird gezeigt, wie Sie dieses Ergebnis mit einem Lambdaausdruck erzielen, um die <xref:System.ServiceModel.Activities.SendMessageChannelCache>-Erweiterung, auf die der Delegat zeigt, direkt zu definieren.  
  
```csharp
serviceHost.WorkflowExtensions.Add(() => new SendMessageChannelCache  
{  
    // Use FactorySettings property to add custom factory cache settings.  
    FactorySettings = new ChannelCacheSettings
    { MaxItemsInCache = 5, },  
    // Use ChannelSettings property to add custom channel cache settings.  
    ChannelSettings = new ChannelCacheSettings
    { MaxItemsInCache = 10 },  
});  
```  
  
## <a name="customizing-cache-settings"></a>Anpassen von Cacheeinstellungen  
 Sie können die Cacheeinstellungen für den Kanalfactorycache und den Kanalcache anpassen. Die Cacheeinstellungen werden in der <xref:System.ServiceModel.Activities.ChannelCacheSettings>-Klasse definiert. Die <xref:System.ServiceModel.Activities.SendMessageChannelCache> Klasse definiert in ihrem parameterlosen Konstruktor Standardcacheeinstellungen für den Channel Factory Cache und den Kanalcache. In der folgenden Tabelle sind die Standardwerte für diese Cacheeinstellungen für die beiden Cachetypen aufgeführt.  
  
|Einstellungen|LeaseTimeout (min)|IdleTimeout (min)|MaxItemsInCache|  
|-|-|-|-|  
|Standardwert Factorycache|TimeSpan.MaxValue|2|16|  
|Standardwert Kanalcache|5|2|16|  
  
 Zum Anpassen der Einstellungen für den Factorycache und den Kanalcache instanziieren Sie die <xref:System.ServiceModel.Activities.SendMessageChannelCache>-Klasse mit dem parametrisierten Konstruktor <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A>, und übergeben Sie eine neue Instanz des <xref:System.ServiceModel.Activities.ChannelCacheSettings>-Elements mit benutzerdefinierten Werten an jeden `factorySettings`-Parameter und `channelSettings`-Parameter. Fügen Sie danach die neue Instanz dieser Klasse als Erweiterung einem Workflowdiensthost oder einer Workflowinstanz hinzu. Im folgenden Codebeispiel wird gezeigt, wie diese Schritte für eine Workflowinstanz ausgeführt werden.  
  
```csharp  
ChannelCacheSettings factorySettings = new ChannelCacheSettings{  
                        MaxItemsInCache = 5,
                        IdleTimeout = TimeSpan.FromMinutes(5),
                        LeaseTimeout = TimeSpan.FromMinutes(20)};  
  
ChannelCacheSettings channelSettings = new ChannelCacheSettings{  
                        MaxItemsInCache = 5,
                        IdleTimeout = TimeSpan.FromMinutes(2),  
                        LeaseTimeout = TimeSpan.FromMinutes(10) };  
  
SendMessageChannelCache customChannelCacheExtension =
    new SendMessageChannelCache(factorySettings, channelSettings);  
  
clientInstance.Extensions.Add(customChannelCacheExtension);  
```  
  
 Wenn Ihr Workflowdienst in der Konfiguration definierte Endpunkte verwendet, müssen Sie zum Aktivieren des Cache die <xref:System.ServiceModel.Activities.SendMessageChannelCache>-Klasse instanziieren, wobei Sie den parametrisierten Konstruktor <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> verwenden und der `allowUnsafeCaching`-Parameter auf `true` festgelegt sein muss. Fügen Sie danach die neue Instanz dieser Klasse als Erweiterung einem Workflowdiensthost oder einer Workflowinstanz hinzu. Im folgenden Codebeispiel wird gezeigt, wie der Cache für eine Workflowinstanz aktiviert wird.  
  
```csharp  
SendMessageChannelCache customChannelCacheExtension =
    new SendMessageChannelCache{ AllowUnsafeCaching = true };  
  
clientInstance.Extensions.Add(customChannelCacheExtension);  
```  
  
 Wenn Sie den Cache für die Kanalfactorys und die Kanäle komplett deaktivieren möchten, deaktivieren Sie den Kanalfactorycache. Hierdurch wird automatisch auch der Kanalcache deaktiviert, da die Kanäle den jeweiligen Kanalfactorys untergeordnet sind. Um den Kanalfactorycache zu deaktivieren, übergeben Sie den `factorySettings`-Parameter an den <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A>-Konstruktor, initialisiert auf eine <xref:System.ServiceModel.Activities.ChannelCacheSettings>-Instanz mit dem <xref:System.ServiceModel.Activities.ChannelCacheSettings.MaxItemsInCache%2A>-Wert auf 0 (null). Dies wird im folgenden Codebeispiel gezeigt.  
  
```csharp  
// Disable the factory cache. This results in the channel cache to be turned off as well.  
ChannelCacheSettings factorySettings = new ChannelCacheSettings  
    { MaxItemsInCache = 0 };  
  
ChannelCacheSettings channelSettings = new ChannelCacheSettings();  
  
SendMessageChannelCache customChannelCacheExtension =
    new SendMessageChannelCache(factorySettings, channelSettings);
  
clientInstance.Extensions.Add(customChannelCacheExtension);  
```  
  
 Sie können auch den Kanalfactorycache verwenden und nur den Kanalcache deaktivieren, indem Sie den `channelSettings`-Parameter an den <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A>-Konstruktor übergeben, initialisiert auf eine <xref:System.ServiceModel.Activities.ChannelCacheSettings>-Instanz mit dem <xref:System.ServiceModel.Activities.ChannelCacheSettings.MaxItemsInCache%2A>-Wert auf 0 (null). Dies wird im folgenden Codebeispiel gezeigt.  
  
```csharp  
ChannelCacheSettings factorySettings = new ChannelCacheSettings();  
// Disable only the channel cache.  
ChannelCacheSettings channelSettings = new ChannelCacheSettings  
    { MaxItemsInCache = 0};  
  
SendMessageChannelCache customChannelCacheExtension =
    new SendMessageChannelCache(factorySettings, channelSettings);
  
clientInstance.Extensions.Add(customChannelCacheExtension);  
```  
  
 In einem gehosteten Workflowdienst können Sie die Einstellungen für den Factorycache und den Channelcache in der Anwendungskonfigurationsdatei angeben. Fügen Sie dafür ein Dienstverhalten hinzu, das die Cacheeinstellungen für die Factory und den Channelcache enthält, und fügen Sie dieses Dienstverhalten dem Dienst hinzu. Das folgende Beispiel zeigt den Inhalt einer `MyChannelCacheBehavior` Konfigurationsdatei, die das Dienstverhalten mit den benutzerdefinierten Factorycache- und Kanalcacheeinstellungen enthält. Dieses Dienstverhalten wird dem Dienst `behaviorConfiguration` über das Attribut hinzugefügt.  
  
```xml  
<configuration>
  <system.serviceModel>  
    <!-- List of other config sections here -->
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="MyChannelCacheBehavior">  
          <sendMessageChannelCache allowUnsafeCaching ="false" >  
            <!-- Control only the host level settings -->
            <factorySettings maxItemsInCache = "8" idleTimeout = "00:05:00" leaseTimeout="10:00:00" />  
            <channelSettings maxItemsInCache = "32" idleTimeout = "00:05:00" leaseTimeout="00:06:00" />  
          </sendMessageChannelCache>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service name="MyService" behaviorConfiguration="MyChannelCacheBehavior" />  
    </services>  
  </system.serviceModel>  
</configuration>  
```
