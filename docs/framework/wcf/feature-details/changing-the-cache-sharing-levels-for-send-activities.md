---
title: "Ändern der Cachefreigabeebenen für Send-Aktivitäten"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03926a64-753d-460e-ac06-2a4ff8e1bbf5
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 59c6ae1ae31a5aa256844e6efca158e4702b6aba
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="changing-the-cache-sharing-levels-for-send-activities"></a><span data-ttu-id="1c219-102">Ändern der Cachefreigabeebenen für Send-Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="1c219-102">Changing the Cache Sharing Levels for Send Activities</span></span>
<span data-ttu-id="1c219-103">Mit der Erweiterung <xref:System.ServiceModel.Activities.SendMessageChannelCache> können Sie die Cachefreigabeebenen, die Einstellungen des Kanalfactorycaches und die Einstellungen des Kanalcaches für Workflows anpassen, die Nachrichten mit <xref:System.ServiceModel.Activities.Send>-Messagingaktivitäten an Dienstendpunkte senden.</span><span class="sxs-lookup"><span data-stu-id="1c219-103">The <xref:System.ServiceModel.Activities.SendMessageChannelCache> extension enables you to customize the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using <xref:System.ServiceModel.Activities.Send> messaging activities.</span></span> <span data-ttu-id="1c219-104">Diese Workflows sind in der Regel Clientworkflows, könnten jedoch auch Workflowdienste sein, die in einem <xref:System.ServiceModel.WorkflowServiceHost> gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="1c219-104">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span> <span data-ttu-id="1c219-105">Der Kanalfactorycache enthält zwischengespeicherte <xref:System.ServiceModel.ChannelFactory%601>-Objekte.</span><span class="sxs-lookup"><span data-stu-id="1c219-105">The channel factory cache contains cached <xref:System.ServiceModel.ChannelFactory%601> objects.</span></span> <span data-ttu-id="1c219-106">Der Kanalcache enthält zwischengespeicherte Kanäle.</span><span class="sxs-lookup"><span data-stu-id="1c219-106">The channel cache contains cached channels.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1c219-107">Workflows können mittels <xref:System.ServiceModel.Activities.Send>-Messagingaktivitäten Nachrichten oder Parameter senden.</span><span class="sxs-lookup"><span data-stu-id="1c219-107">Workflows can use <xref:System.ServiceModel.Activities.Send> messaging activities to send either messages or parameters.</span></span> <span data-ttu-id="1c219-108">Die Workflowlaufzeit fügt dem Cache Kanalfactorys hinzu, die Kanäle vom Typ <xref:System.ServiceModel.Channels.IRequestChannel> erstellen, wenn Sie eine <xref:System.ServiceModel.Activities.ReceiveReply>-Aktivität mit einer <xref:System.ServiceModel.Activities.Send>-Aktivität verwenden, bzw. einen Kanal vom Typ <xref:System.ServiceModel.Channels.IOutputChannel>, wenn Sie nur eine <xref:System.ServiceModel.Activities.Send>-Aktivität (kein <xref:System.ServiceModel.Activities.ReceiveReply>) verwenden.</span><span class="sxs-lookup"><span data-stu-id="1c219-108">The workflow runtime adds channel factories to the cache that create channels of type <xref:System.ServiceModel.Channels.IRequestChannel> when you use a <xref:System.ServiceModel.Activities.ReceiveReply> activity with a <xref:System.ServiceModel.Activities.Send> activity, and an <xref:System.ServiceModel.Channels.IOutputChannel> when just using a <xref:System.ServiceModel.Activities.Send> activity (no <xref:System.ServiceModel.Activities.ReceiveReply>).</span></span>  
  
## <a name="the-cache-sharing-levels"></a><span data-ttu-id="1c219-109">Die Cachefreigabeebenen</span><span class="sxs-lookup"><span data-stu-id="1c219-109">The Cache Sharing Levels</span></span>  
 <span data-ttu-id="1c219-110">In einem von einem <xref:System.ServiceModel.WorkflowServiceHost> gehosteten Workflow wird der von <xref:System.ServiceModel.Activities.Send>-Messagingaktivitäten verwendete Cache von allen Workflowinstanzen auf dem <xref:System.ServiceModel.WorkflowServiceHost> gemeinsam genutzt (Zwischenspeicherung auf Hostebene).</span><span class="sxs-lookup"><span data-stu-id="1c219-110">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost> the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="1c219-111">Bei einen Clientworkflow, der nicht von einem <xref:System.ServiceModel.WorkflowServiceHost> gehostet wird, steht der Cache nur der Workflowinstanz zur Verfügung (Zwischenspeichern auf Instanzebene).</span><span class="sxs-lookup"><span data-stu-id="1c219-111">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="1c219-112">Der Cache ist nur verfügbar für <xref:System.ServiceModel.Activities.Send>-Aktivitäten, die keine in der Konfiguration definierten Endpunkte verwenden, es sei denn, die Zwischenspeicherung im unsicheren Modus wurde aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1c219-112">The cache is only available for <xref:System.ServiceModel.Activities.Send> activities that do not use endpoints defined in configuration unless unsafe caching is enabled.</span></span>  
  
 <span data-ttu-id="1c219-113">Im Folgenden sind die unterschiedlichen Cachefreigabeebenen für <xref:System.ServiceModel.Activities.Send>-Aktivitäten in einem Workflow mit Empfehlungen zur Verwendung aufgelistet:</span><span class="sxs-lookup"><span data-stu-id="1c219-113">The following are the different cache sharing levels available for <xref:System.ServiceModel.Activities.Send> activities in a workflow and their recommended use:</span></span>  
  
-   <span data-ttu-id="1c219-114">**Hostebene**: auf dem Host, Freigabestufe, der Cache ist nur für die in dem Workflowdiensthost gehosteten Workflowinstanzen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1c219-114">**Host Level**: In the host sharing level, the cache is available only to the workflow instances hosted in the workflow service host.</span></span> <span data-ttu-id="1c219-115">Ein Cache kann auch prozessweit für mehrere Workflowdiensthosts freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1c219-115">A cache can also be shared between workflow service hosts in a process-wide cache.</span></span>  
  
-   <span data-ttu-id="1c219-116">**-Instanzebene**: In der Instanz, Freigabestufe, der Cache für eine bestimmte Workflowinstanz Dauer ihrer Lebensdauer verfügbar ist, aber der Cache ist nicht für andere Workflowinstanzen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1c219-116">**Instance Level**: In the instance sharing level, the cache is available to a particular workflow instance throughout its lifetime but the cache is not available to other workflow instances.</span></span>  
  
-   <span data-ttu-id="1c219-117">**Kein Cache**: der Cache ist standardmäßig deaktiviert, wenn Sie einen Workflow vorliegen haben, die in der Konfiguration definierte Endpunkte verwendet.</span><span class="sxs-lookup"><span data-stu-id="1c219-117">**No Cache**: The cache is turned off by default if you have a workflow that uses endpoints defined in configuration.</span></span> <span data-ttu-id="1c219-118">Es wird empfohlen, den Cache in diesem Fall nicht zu aktivieren, da dies unsicher sein kann.</span><span class="sxs-lookup"><span data-stu-id="1c219-118">It is also recommended to keep the cache turned off in this case because turning it on could be unsecure.</span></span> <span data-ttu-id="1c219-119">Beispiel: Wenn eine andere Identität (andere Anmeldeinformationen oder Identitätswechsel) für jeden Sendevorgang benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="1c219-119">For example, if a different identity (different credentials or using impersonation) is required for each send.</span></span>  
  
## <a name="changing-the-cache-sharing-level-for-a-client-workflow"></a><span data-ttu-id="1c219-120">Ändern der Cachefreigabeebene für einen Clientworkflow</span><span class="sxs-lookup"><span data-stu-id="1c219-120">Changing the Cache Sharing Level for a Client Workflow</span></span>  
 <span data-ttu-id="1c219-121">Um die Cachefreigabe für einen Clientworkflow festzulegen, fügen Sie dem gewünschten Satz von Workflowinstanzen eine Instanz der <xref:System.ServiceModel.Activities.SendMessageChannelCache>-Klasse als Erweiterung hinzu.</span><span class="sxs-lookup"><span data-stu-id="1c219-121">To set the cache sharing in a client workflow, add an instance of the <xref:System.ServiceModel.Activities.SendMessageChannelCache> class as an extension to the desired set of workflow instances.</span></span> <span data-ttu-id="1c219-122">So wird der Cache für alle Workflowinstanzen freigegeben.</span><span class="sxs-lookup"><span data-stu-id="1c219-122">This results in sharing the cache across all the workflow instances.</span></span> <span data-ttu-id="1c219-123">In den folgenden Codebeispielen wird die Ausführung dieser Schritte veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="1c219-123">The following code examples show how to perform these steps.</span></span>  
  
 <span data-ttu-id="1c219-124">Deklarieren Sie zuerst eine Instanz vom Typ <xref:System.ServiceModel.Activities.SendMessageChannelCache>.</span><span class="sxs-lookup"><span data-stu-id="1c219-124">First, declare an instance of type <xref:System.ServiceModel.Activities.SendMessageChannelCache>.</span></span>  
  
```  
// Create an instance of SendMessageChannelCache with default cache settings.  
static SendMessageChannelCache sharedChannelCacheExtension =  
    new SendMessageChannelCache();  
```  
  
 <span data-ttu-id="1c219-125">Fügen Sie dann jeder einzelnen Clientworkflowinstanz die Cacheerweiterung hinzu.</span><span class="sxs-lookup"><span data-stu-id="1c219-125">Next, add the cache extension to each client workflow instance.</span></span>  
  
```  
WorkflowApplication clientInstance1 = new WorkflowApplication(new clientWorkflow1());  
WorkflowApplication clientInstance2 = new WorkflowApplication(new clientWorkflow2());  
  
// Share the cache extension object   
  
clientInstance1.Extensions.Add(sharedChannelCacheExtension);  
clientInstance2.Extensions.Add(sharedChannelCacheExtension);  
```  
  
## <a name="changing-the-cache-sharing-level-for-a-hosted-workflow-service"></a><span data-ttu-id="1c219-126">Ändern der Cachefreigabeebene für einen gehosteten Workflowdienst</span><span class="sxs-lookup"><span data-stu-id="1c219-126">Changing the Cache Sharing Level for a Hosted Workflow Service</span></span>  
 <span data-ttu-id="1c219-127">Um die Cachefreigabe für einen gehosteten Workflowdienst festzulegen, fügen Sie allen Workflowdiensthosts eine Instanz der <xref:System.ServiceModel.Activities.SendMessageChannelCache>-Klasse als Erweiterung hinzu.</span><span class="sxs-lookup"><span data-stu-id="1c219-127">To set the cache sharing in a hosted workflow service, add an instance of the <xref:System.ServiceModel.Activities.SendMessageChannelCache> class as an extension to all the workflow service hosts.</span></span> <span data-ttu-id="1c219-128">So wird der Cache für alle Workflowdiensthosts freigegeben.</span><span class="sxs-lookup"><span data-stu-id="1c219-128">This results in sharing the cache across all the workflow service hosts.</span></span> <span data-ttu-id="1c219-129">In den folgenden Codebeispielen wird die Ausführung dieser Schritte veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="1c219-129">The following code examples show to perform these steps.</span></span>  
  
 <span data-ttu-id="1c219-130">Deklarieren Sie zuerst eine Instanz vom Typ <xref:System.ServiceModel.Activities.SendMessageChannelCache> auf Klassenebene.</span><span class="sxs-lookup"><span data-stu-id="1c219-130">First, declare an instance  of type <xref:System.ServiceModel.Activities.SendMessageChannelCache> at the class level.</span></span>  
  
```  
// Create static instance of SendMessageChannelCache with default cache settings.  
static SendMessageChannelCache sharedChannelCacheExtension = new  
    SendMessageChannelCache();  
```  
  
 <span data-ttu-id="1c219-131">Fügen Sie dann jedem einzelnen Workflowdiensthost die statische Cacheerweiterung hinzu.</span><span class="sxs-lookup"><span data-stu-id="1c219-131">Next, add the static cache extension to each workflow service host.</span></span>  
  
```  
WorkflowServiceHost host1 = new WorkflowServiceHost(new serviceWorkflow1(), new Uri(baseAddress1));  
WorkflowServiceHost host2 = new WorkflowServiceHost(new serviceWorkflow2(), new Uri(baseAddress2));  
  
// Share the static cache to get an AppDomain level cache.  
host1.WorkflowExtensions.Add(sharedChannelCacheExtension);  
host2.WorkflowExtensions.Add(sharedChannelCacheExtension);  
```  
  
 <span data-ttu-id="1c219-132">Um die Cachefreigabe für einen gehosteten Workflowdienst auf Instanzebene festzulegen, fügen Sie dem Workflowdiensthost einen `Func<SendMessageChannelCache>`-Delegaten als Erweiterung hinzu, und weisen Sie diesen Delegaten dem Code hinzu, der eine neue Instanz der <xref:System.ServiceModel.Activities.SendMessageChannelCache>-Klasse instanziiert.</span><span class="sxs-lookup"><span data-stu-id="1c219-132">To set the cache sharing in a hosted workflow service to the instance level, add a `Func<SendMessageChannelCache>` delegate as an extension to the workflow service host and assign this delegate to the code that instantiates a new instance of the <xref:System.ServiceModel.Activities.SendMessageChannelCache> class.</span></span> <span data-ttu-id="1c219-133">Auf diese Weise wird für jede einzelne Workflowinstanz ein anderer Cache verwendet.</span><span class="sxs-lookup"><span data-stu-id="1c219-133">This results in a different cache for each individual workflow instance, instead of a single cache shared by all workflow instances in the workflow service host.</span></span> <span data-ttu-id="1c219-134">Im folgenden Codebeispiel wird gezeigt, wie Sie dieses Ergebnis mit einem Lambda-Ausdruck erzielen, um die <xref:System.ServiceModel.Activities.SendMessageChannelCache>-Erweiterung, auf die der Delegat zeigt, direkt zu definieren.</span><span class="sxs-lookup"><span data-stu-id="1c219-134">The following code example shows how to achieve this by using a lambda expression to directly define the <xref:System.ServiceModel.Activities.SendMessageChannelCache> extension that the delegate points to.</span></span>  
  
```  
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
  
## <a name="customizing-cache-settings"></a><span data-ttu-id="1c219-135">Anpassen von Cacheeinstellungen</span><span class="sxs-lookup"><span data-stu-id="1c219-135">Customizing Cache Settings</span></span>  
 <span data-ttu-id="1c219-136">Sie können die Cacheeinstellungen für den Kanalfactorycache und den Kanalcache anpassen.</span><span class="sxs-lookup"><span data-stu-id="1c219-136">You can customize the cache settings for the channel factory cache and the channel cache.</span></span> <span data-ttu-id="1c219-137">Die Cacheeinstellungen werden in der <xref:System.ServiceModel.Activities.ChannelCacheSettings>-Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="1c219-137">The cache settings are defined in the <xref:System.ServiceModel.Activities.ChannelCacheSettings> class.</span></span> <span data-ttu-id="1c219-138">Die <xref:System.ServiceModel.Activities.SendMessageChannelCache>-Klasse enthält Standardcacheeinstellungen für den Kanalfactorycache und den Kanalcache in ihrem Standardkonstruktor.</span><span class="sxs-lookup"><span data-stu-id="1c219-138">The <xref:System.ServiceModel.Activities.SendMessageChannelCache> class defines default cache settings for the channel factory cache and the channel cache in its default constructor.</span></span> <span data-ttu-id="1c219-139">In der folgenden Tabelle sind die Standardwerte für diese Cacheeinstellungen für die beiden Cachetypen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="1c219-139">The following table lists the default values of these cache settings for each type of cache.</span></span>  
  
|<span data-ttu-id="1c219-140">Einstellungen</span><span class="sxs-lookup"><span data-stu-id="1c219-140">Settings</span></span>|<span data-ttu-id="1c219-141">LeaseTimeout (min)</span><span class="sxs-lookup"><span data-stu-id="1c219-141">LeaseTimeout (min)</span></span>|<span data-ttu-id="1c219-142">IdleTimeout (min)</span><span class="sxs-lookup"><span data-stu-id="1c219-142">IdleTimeout (min)</span></span>|<span data-ttu-id="1c219-143">MaxItemsInCache</span><span class="sxs-lookup"><span data-stu-id="1c219-143">MaxItemsInCache</span></span>|  
|-|-|-|-|  
|<span data-ttu-id="1c219-144">Standardwert Factorycache</span><span class="sxs-lookup"><span data-stu-id="1c219-144">Factory Cache Default</span></span>|<span data-ttu-id="1c219-145">TimeSpan.MaxValue</span><span class="sxs-lookup"><span data-stu-id="1c219-145">TimeSpan.MaxValue</span></span>|<span data-ttu-id="1c219-146">2</span><span class="sxs-lookup"><span data-stu-id="1c219-146">2</span></span>|<span data-ttu-id="1c219-147">16</span><span class="sxs-lookup"><span data-stu-id="1c219-147">16</span></span>|  
|<span data-ttu-id="1c219-148">Standardwert Kanalcache</span><span class="sxs-lookup"><span data-stu-id="1c219-148">Channel Cache Default</span></span>|<span data-ttu-id="1c219-149">5</span><span class="sxs-lookup"><span data-stu-id="1c219-149">5</span></span>|<span data-ttu-id="1c219-150">2</span><span class="sxs-lookup"><span data-stu-id="1c219-150">2</span></span>|<span data-ttu-id="1c219-151">16</span><span class="sxs-lookup"><span data-stu-id="1c219-151">16</span></span>|  
  
 <span data-ttu-id="1c219-152">Zum Anpassen der Einstellungen für den Factorycache und den Kanalcache instanziieren Sie die <xref:System.ServiceModel.Activities.SendMessageChannelCache>-Klasse mit dem parametrisierten Konstruktor <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A>, und übergeben Sie eine neue Instanz des <xref:System.ServiceModel.Activities.ChannelCacheSettings>-Elements mit benutzerdefinierten Werten an jeden `factorySettings`-Parameter und `channelSettings`-Parameter.</span><span class="sxs-lookup"><span data-stu-id="1c219-152">To customize the factory cache and channel cache settings, instantiate the <xref:System.ServiceModel.Activities.SendMessageChannelCache> class using the parameterized constructor <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> and pass a new instance of the <xref:System.ServiceModel.Activities.ChannelCacheSettings> with custom values to each of the `factorySettings` and `channelSettings` parameters.</span></span> <span data-ttu-id="1c219-153">Fügen Sie danach die neue Instanz dieser Klasse als Erweiterung einem Workflowdiensthost oder einer Workflowinstanz hinzu.</span><span class="sxs-lookup"><span data-stu-id="1c219-153">Next, add the new instance of this class as an extension to a workflow service host or a workflow instance.</span></span> <span data-ttu-id="1c219-154">Im folgenden Codebeispiel wird gezeigt, wie diese Schritte für eine Workflowinstanz ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1c219-154">The following code example shows how to perform these steps for a workflow instance.</span></span>  
  
```  
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
  
 <span data-ttu-id="1c219-155">Wenn Ihr Workflowdienst in der Konfiguration definierte Endpunkte verwendet, müssen Sie zum Aktivieren des Cache die <xref:System.ServiceModel.Activities.SendMessageChannelCache>-Klasse instanziieren, wobei Sie den parametrisierten Konstruktor <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> verwenden und der `allowUnsafeCaching`-Parameter auf `true` festgelegt sein muss.</span><span class="sxs-lookup"><span data-stu-id="1c219-155">To enable caching when your workflow service has endpoints defined in configuration, instantiate the <xref:System.ServiceModel.Activities.SendMessageChannelCache> class using the parameterized constructor <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> with the `allowUnsafeCaching` parameter set to `true`.</span></span> <span data-ttu-id="1c219-156">Fügen Sie danach die neue Instanz dieser Klasse als Erweiterung einem Workflowdiensthost oder einer Workflowinstanz hinzu.</span><span class="sxs-lookup"><span data-stu-id="1c219-156">Next, add the new instance of this class as an extension to a workflow service host or a workflow instance.</span></span> <span data-ttu-id="1c219-157">Im folgenden Codebeispiel wird gezeigt, wie der Cache für eine Workflowinstanz aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="1c219-157">The following code example shows how to enable caching for a workflow instance.</span></span>  
  
```  
SendMessageChannelCache customChannelCacheExtension =   
    new SendMessageChannelCache{ AllowUnsafeCaching = true };  
  
clientInstance.Extensions.Add(customChannelCacheExtension);  
```  
  
 <span data-ttu-id="1c219-158">Wenn Sie den Cache für die Kanalfactorys und die Kanäle komplett deaktivieren möchten, deaktivieren Sie den Kanalfactorycache.</span><span class="sxs-lookup"><span data-stu-id="1c219-158">To disable the cache completely for the channel factories and the channels, disable the channel factory cache.</span></span> <span data-ttu-id="1c219-159">Hierdurch wird automatisch auch der Kanalcache deaktiviert, da die Kanäle den jeweiligen Kanalfactorys untergeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="1c219-159">Doing so also turns off the channel cache as the channels are owned by their corresponding channel factories.</span></span> <span data-ttu-id="1c219-160">Um den Kanalfactorycache zu deaktivieren, übergeben Sie den `factorySettings`-Parameter an den <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A>-Konstruktor, initialisiert auf eine <xref:System.ServiceModel.Activities.ChannelCacheSettings>-Instanz mit dem <xref:System.ServiceModel.Activities.ChannelCacheSettings.MaxItemsInCache%2A>-Wert auf 0 (null).</span><span class="sxs-lookup"><span data-stu-id="1c219-160">To disable the channel factory cache, pass the `factorySettings` parameter to the <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> constructor initialized to a <xref:System.ServiceModel.Activities.ChannelCacheSettings> instance with a <xref:System.ServiceModel.Activities.ChannelCacheSettings.MaxItemsInCache%2A> value of 0.</span></span> <span data-ttu-id="1c219-161">Dies wird im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1c219-161">The following code example shows this.</span></span>  
  
```  
// Disable the factory cache. This results in the channel cache to be turned off as well.  
ChannelCacheSettings factorySettings = new ChannelCacheSettings  
    { MaxItemsInCache = 0 };  
  
ChannelCacheSettings channelSettings = new ChannelCacheSettings();  
  
SendMessageChannelCache customChannelCacheExtension =   
    new SendMessageChannelCache(factorySettings, channelSettings);   
  
clientInstance.Extensions.Add(customChannelCacheExtension);  
```  
  
 <span data-ttu-id="1c219-162">Sie können auch den Kanalfactorycache verwenden und nur den Kanalcache deaktivieren, indem Sie den `channelSettings`-Parameter an den <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A>-Konstruktor übergeben, initialisiert auf eine <xref:System.ServiceModel.Activities.ChannelCacheSettings>-Instanz mit dem <xref:System.ServiceModel.Activities.ChannelCacheSettings.MaxItemsInCache%2A>-Wert auf 0 (null).</span><span class="sxs-lookup"><span data-stu-id="1c219-162">You can choose to use only the channel factory cache and disable the channel cache by passing the `channelSettings` parameter to the <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> constructor initialized to a <xref:System.ServiceModel.Activities.ChannelCacheSettings> instance with a <xref:System.ServiceModel.Activities.ChannelCacheSettings.MaxItemsInCache%2A> value of 0.</span></span> <span data-ttu-id="1c219-163">Dies wird im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1c219-163">The following code example shows this.</span></span>  
  
```  
ChannelCacheSettings factorySettings = new ChannelCacheSettings();  
// Disable only the channel cache.  
ChannelCacheSettings channelSettings = new ChannelCacheSettings  
    { MaxItemsInCache = 0};  
  
SendMessageChannelCache customChannelCacheExtension =   
    new SendMessageChannelCache(factorySettings, channelSettings);   
  
clientInstance.Extensions.Add(customChannelCacheExtension);  
```  
  
 <span data-ttu-id="1c219-164">In einem gehosteten Workflowdienst können Sie die Einstellungen für den Factorycache und den Channelcache in der Anwendungskonfigurationsdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="1c219-164">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="1c219-165">Fügen Sie dafür ein Dienstverhalten hinzu, das die Cacheeinstellungen für die Factory und den Channelcache enthält, und fügen Sie dieses Dienstverhalten dem Dienst hinzu.</span><span class="sxs-lookup"><span data-stu-id="1c219-165">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="1c219-166">Das folgende Beispiel zeigt den Inhalt einer Konfigurationsdatei, die enthält die `MyChannelCacheBehavior` -Dienstverhalten mit cacheeinstellungen für die benutzerdefinierte Factory und den channelcache.</span><span class="sxs-lookup"><span data-stu-id="1c219-166">The following example shows the contents of a configuration file that contains the `MyChannelCacheBehavior` service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="1c219-167">Dieses Dienstverhalten wird hinzugefügt, um den Dienst über die `behaviorConfiguarion` Attribut.</span><span class="sxs-lookup"><span data-stu-id="1c219-167">This service behavior is added to the service through the `behaviorConfiguarion` attribute.</span></span>  
  
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
