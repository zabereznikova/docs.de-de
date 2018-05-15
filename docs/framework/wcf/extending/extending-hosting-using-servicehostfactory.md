---
title: Erweitern des Hosting mit ServiceHostFactory
ms.date: 03/30/2017
ms.assetid: bcc5ae1b-21ce-4e0e-a184-17fad74a441e
ms.openlocfilehash: e553fe161ffc5b50850d916cf1cef6b38dd5c1a9
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="extending-hosting-using-servicehostfactory"></a><span data-ttu-id="bffe0-102">Erweitern des Hosting mit ServiceHostFactory</span><span class="sxs-lookup"><span data-stu-id="bffe0-102">Extending Hosting Using ServiceHostFactory</span></span>
<span data-ttu-id="bffe0-103">Der Standard <xref:System.ServiceModel.ServiceHost> API zum Hosten von Diensten in Windows Communication Foundation (WCF) ist ein Erweiterungspunkt. er in der WCF-Architektur.</span><span class="sxs-lookup"><span data-stu-id="bffe0-103">The standard <xref:System.ServiceModel.ServiceHost> API for hosting services in Windows Communication Foundation (WCF) is an extensibility point in the WCF architecture.</span></span> <span data-ttu-id="bffe0-104">Benutzer können ihre eigenen Hostklassen von <xref:System.ServiceModel.ServiceHost> ableiten, üblicherweise um <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening> für die Verwendung von <xref:System.ServiceModel.Description.ServiceDescription> zu überschreiben, um Endpunkte imperativ hinzuzufügen oder das Verhalten vor dem Öffnen des Diensts zu ändern.</span><span class="sxs-lookup"><span data-stu-id="bffe0-104">Users can derive their own host classes from <xref:System.ServiceModel.ServiceHost>, usually to override <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening> to use <xref:System.ServiceModel.Description.ServiceDescription> to add default endpoints imperatively or modify behaviors, prior to opening the service.</span></span>  
  
 <span data-ttu-id="bffe0-105">In der selbst gehosteten Umgebung müssen Sie keine benutzerdefinierte <xref:System.ServiceModel.ServiceHost>-Klasse erstellen, weil Sie den Code schreiben, der den Host instantiiert, und rufen anschließend <xref:System.ServiceModel.ICommunicationObject.Open> für den Host auf.</span><span class="sxs-lookup"><span data-stu-id="bffe0-105">In the self-host environment, you do not have to create a custom <xref:System.ServiceModel.ServiceHost> because you write the code that instantiates the host and then call <xref:System.ServiceModel.ICommunicationObject.Open> on it after you instantiate it.</span></span> <span data-ttu-id="bffe0-106">Zwischen diesen beiden Schritten können Sie beliebige Vorgänge ausführen.</span><span class="sxs-lookup"><span data-stu-id="bffe0-106">Between those two steps you can do whatever you want.</span></span> <span data-ttu-id="bffe0-107">Sie könnten z.&#160;B. ein neues <xref:System.ServiceModel.Description.IServiceBehavior> hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="bffe0-107">You could, for example, add a new <xref:System.ServiceModel.Description.IServiceBehavior>:</span></span>  
  
```  
public static void Main()  
{  
   ServiceHost host = new ServiceHost( typeof( MyService ) );  
   host.Description.Add( new MyServiceBehavior() );  
   host.Open();  
  
   ...  
}  
```  
  
 <span data-ttu-id="bffe0-108">Dieser Ansatz ist nicht wiederverwendbar.</span><span class="sxs-lookup"><span data-stu-id="bffe0-108">This approach is not reusable.</span></span> <span data-ttu-id="bffe0-109">Der Code, der die Beschreibung bearbeitet, wird in das Hostprogramm eingefügt (in diesem Fall in die Main()-Funktion), daher ist es schwierig, diese Logik in anderen Kontexten wiederzuverwenden.</span><span class="sxs-lookup"><span data-stu-id="bffe0-109">The code that manipulates the description is coded into the host program (in this case, the Main() function), so it is difficult to reuse that logic in other contexts.</span></span> <span data-ttu-id="bffe0-110">Es gibt auch andere Wege, ein <xref:System.ServiceModel.Description.IServiceBehavior> hinzuzufügen, die keinen imperativen Code erfordern.</span><span class="sxs-lookup"><span data-stu-id="bffe0-110">There are also other ways of adding an <xref:System.ServiceModel.Description.IServiceBehavior> that do not require imperative code.</span></span> <span data-ttu-id="bffe0-111">Sie können von <xref:System.ServiceModel.ServiceBehaviorAttribute> ein Attribut ableiten und es in Ihren Dienstimplementierungstyp aufnehmen, oder Sie können ein benutzerdefiniertes Verhalten konfigurierbar gestalten und es dynamisch mithilfe einer Konfiguration erstellen.</span><span class="sxs-lookup"><span data-stu-id="bffe0-111">You can derive an attribute from <xref:System.ServiceModel.ServiceBehaviorAttribute> and put that on your service implementation type or you can make a custom behavior configurable and compose it dynamically using configuration.</span></span>  
  
 <span data-ttu-id="bffe0-112">Es kann jedoch auch eine kleine Variante des Beispiels verwendet werden, um dieses Problem zu lösen.</span><span class="sxs-lookup"><span data-stu-id="bffe0-112">However, a slight variation of the example can also be used to solve this problem.</span></span> <span data-ttu-id="bffe0-113">Ein Ansatz besteht darin, den Code, mit dem ServiceBehavior hinzugefügt wird, von `Main()` in die <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A>-Methode einer benutzerdefinierten Ableitung von <xref:System.ServiceModel.ServiceHost> zu verschieben:</span><span class="sxs-lookup"><span data-stu-id="bffe0-113">One approach is to move the code that adds the ServiceBehavior out of `Main()` and into the <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> method of a custom derivative of <xref:System.ServiceModel.ServiceHost>:</span></span>  
  
```  
public class DerivedHost : ServiceHost  
{  
   public DerivedHost( Type t, params Uri baseAddresses ) :  
      base( t, baseAddresses ) {}  
  
   public override void OnOpening()  
   {  
  this.Description.Add( new MyServiceBehavior() );  
   }  
}  
```  
  
 <span data-ttu-id="bffe0-114">Dann können Sie innerhalb von `Main()` Folgendes verwenden.</span><span class="sxs-lookup"><span data-stu-id="bffe0-114">Then, inside of `Main()` you can use:</span></span>  
  
```  
public static void Main()  
{  
   ServiceHost host = new DerivedHost( typeof( MyService ) );  
   host.Open();  
  
   ...  
}  
```  
  
 <span data-ttu-id="bffe0-115">Sie haben jetzt die benutzerdefinierte Logik in einer abstrakten Form gekapselt, die so in verschiedenen Hostimplementierungen wiederverwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="bffe0-115">Now you have encapsulated the custom logic into a clean abstraction that can be easily reused across many different host executables.</span></span>  
  
 <span data-ttu-id="bffe0-116">Es ist nicht unmittelbar einsichtig, wie diese benutzerdefinierte <xref:System.ServiceModel.ServiceHost>-Klasse innerhalb von IIS (Internetinformationsdiensten) oder WAS (Windows Process Activation Service) verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="bffe0-116">It is not immediately obvious how to use this custom <xref:System.ServiceModel.ServiceHost> from inside of Internet Information Services (IIS) or Windows Process Activation Service (WAS).</span></span> <span data-ttu-id="bffe0-117">Diese Umgebungen unterscheiden sich von einer selbst gehosteten Umgebung, weil die Hostumgebung im Namen der Anwendung <xref:System.ServiceModel.ServiceHost> instantiiert.</span><span class="sxs-lookup"><span data-stu-id="bffe0-117">Those environments are different than the self-host environment, because the hosting environment is the one instantiating the <xref:System.ServiceModel.ServiceHost> on behalf of the application.</span></span> <span data-ttu-id="bffe0-118">Die Hostumgebungen IIS und WAS wissen jedoch nichts von Ihrer benutzerdefinierten <xref:System.ServiceModel.ServiceHost>-Ableitung.</span><span class="sxs-lookup"><span data-stu-id="bffe0-118">The IIS and WAS hosting infrastructure does not know anything about your custom <xref:System.ServiceModel.ServiceHost> derivative.</span></span>  
  
 <span data-ttu-id="bffe0-119"><xref:System.ServiceModel.Activation.ServiceHostFactory> wurde dafür konzipiert, dieses Problem des Zugriffs auf Ihre benutzerdefinierte <xref:System.ServiceModel.ServiceHost>-Klasse durch IIS oder WAS zu lösen.</span><span class="sxs-lookup"><span data-stu-id="bffe0-119">The <xref:System.ServiceModel.Activation.ServiceHostFactory> was designed to solve this problem of accessing your custom <xref:System.ServiceModel.ServiceHost> from within IIS or WAS.</span></span> <span data-ttu-id="bffe0-120">Da ein benutzerdefinierter, von <xref:System.ServiceModel.ServiceHost> abgeleiteter Host dynamisch konfiguriert und von potentiell unterschiedlichem Typ ist, wird er von der Hostumgebung niemals direkt instantiiert.</span><span class="sxs-lookup"><span data-stu-id="bffe0-120">Because a custom host that is derived from <xref:System.ServiceModel.ServiceHost> is dynamically configured and potentially of various types, the hosting environment never instantiates it directly.</span></span> <span data-ttu-id="bffe0-121">Stattdessen verwendet WCF ein Factorymuster, um eine Dereferenzierungsschicht zwischen der hostumgebung und dem konkreten Typ des Diensts bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="bffe0-121">Instead, WCF uses a factory pattern to provide a layer of indirection between the hosting environment and the concrete type of the service.</span></span> <span data-ttu-id="bffe0-122">Sofern Sie nichts anderes angeben, wird dazu eine Standardimplementierung von <xref:System.ServiceModel.Activation.ServiceHostFactory> verwendet, die eine Instanz von <xref:System.ServiceModel.ServiceHost> zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="bffe0-122">Unless you tell it otherwise, it uses a default implementation of <xref:System.ServiceModel.Activation.ServiceHostFactory> that returns an instance of <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="bffe0-123">Aber Sie können auch angeben, eine eigene Factory, die den abgeleiteten Host zurückgibt, durch Angeben der CLR-Typnamen Ihrer Factory-Implementierung in der @ServiceHost Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="bffe0-123">But you can also provide your own factory that returns your derived host by specifying the CLR type name of your factory implementation in the @ServiceHost directive.</span></span>  
  
 <span data-ttu-id="bffe0-124">Ziel ist, dass in den grundlegenden Fällen die Implementierung einer eigenen Factory eine einfache Angelegenheit sein sollte.</span><span class="sxs-lookup"><span data-stu-id="bffe0-124">The intent is that for basic cases, implementing your own factory should be a straight forward exercise.</span></span> <span data-ttu-id="bffe0-125">Als Beispiel folgt hier eine benutzerdefinierte <xref:System.ServiceModel.Activation.ServiceHostFactory>, die eine abgeleitete <xref:System.ServiceModel.ServiceHost>-Klasse zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="bffe0-125">For example, here is a custom <xref:System.ServiceModel.Activation.ServiceHostFactory> that returns a derived <xref:System.ServiceModel.ServiceHost>:</span></span>  
  
```  
public class DerivedFactory : ServiceHostFactory  
{  
   public override ServiceHost CreateServiceHost( Type t, Uri[] baseAddresses )  
   {  
      return new DerivedHost( t, baseAddresses )  
   }  
}  
```  
  
 <span data-ttu-id="bffe0-126">Um diese Factory statt der standardfactory verwenden möchten, geben Sie den Typnamen in der @ServiceHost Richtlinie wie folgt:</span><span class="sxs-lookup"><span data-stu-id="bffe0-126">To use this factory instead of the default factory, provide the type name in the @ServiceHost directive as follows:</span></span>  
  
```  
<% @ServiceHost Factory="DerivedFactory" Service="MyService" %>  
```  
  
 <span data-ttu-id="bffe0-127">Zwar gibt es keine technische Grenze für das, was Sie mit einer von <xref:System.ServiceModel.ServiceHost> zurückgegebenen <xref:System.ServiceModel.Activation.ServiceHostFactory.CreateServiceHost%2A>-Klasse tun können, jedoch wird empfohlen, die Implementierung der Factory so einfach wie möglich zu halten.</span><span class="sxs-lookup"><span data-stu-id="bffe0-127">While there is no technical limit on doing what you want to the <xref:System.ServiceModel.ServiceHost> you return from <xref:System.ServiceModel.Activation.ServiceHostFactory.CreateServiceHost%2A>, we suggest that you keep your factory implementations as simple as possible.</span></span> <span data-ttu-id="bffe0-128">Falls Sie benutzerdefinierte Logik großen Umfangs definieren müssen, platzieren Sie sie statt in die Factory besser in den Host, damit der Code einfacher wiederverwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="bffe0-128">If you have lots of custom logic, it is better to put that logic inside of you host instead of inside the factory so that it can be reusable.</span></span>  
  
 <span data-ttu-id="bffe0-129">Es gibt noch eine weitere Ebene der Host-API, die hier erwähnt werden muss.</span><span class="sxs-lookup"><span data-stu-id="bffe0-129">There is one more layer to the hosting API that should be mentioned here.</span></span> <span data-ttu-id="bffe0-130">WCF verfügt auch über <xref:System.ServiceModel.ServiceHostBase> und <xref:System.ServiceModel.Activation.ServiceHostFactoryBase>, von dem <xref:System.ServiceModel.ServiceHost> und <xref:System.ServiceModel.Activation.ServiceHostFactory> abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="bffe0-130">WCF also has <xref:System.ServiceModel.ServiceHostBase> and <xref:System.ServiceModel.Activation.ServiceHostFactoryBase>, from which <xref:System.ServiceModel.ServiceHost> and <xref:System.ServiceModel.Activation.ServiceHostFactory> respectively derive.</span></span> <span data-ttu-id="bffe0-131">Diese sind für erweiterte Szenarien vorgesehen, in denen Sie große Teile des Metadatensystems mit Ihren benutzerdefinierten Klassen auslagern müssen.</span><span class="sxs-lookup"><span data-stu-id="bffe0-131">Those exist for more advanced scenarios where you must swap out large parts of the metadata system with your own customized creations.</span></span>
