---
title: '&lt;behaviorExtensions&gt;'
ms.date: 03/30/2017
ms.assetid: 59f2791a-c78f-40d7-aa80-0d9cd10135d9
ms.openlocfilehash: 6698da198c4e1798af4a63e72e1d7ef9e09a5d92
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54599022"
---
# <a name="ltbehaviorextensionsgt"></a><span data-ttu-id="efc36-102">&lt;behaviorExtensions&gt;</span><span class="sxs-lookup"><span data-stu-id="efc36-102">&lt;behaviorExtensions&gt;</span></span>
<span data-ttu-id="efc36-103">Verhaltenserweiterungen ermöglichen es dem Benutzer, benutzerdefinierte Verhaltenselemente zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="efc36-103">Behavior extensions enable the user to create user-defined behavior elements.</span></span> <span data-ttu-id="efc36-104">Diese Elemente können neben den standardmäßigen Windows Communication Foundation (WCF)-Verhaltenselementen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="efc36-104">These elements can be used alongside the standard Windows Communication Foundation (WCF) behavior elements.</span></span> <span data-ttu-id="efc36-105">Im `behaviorExtensions`-Abschnitt wird das Element so definiert, dass es in der Konfiguration verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="efc36-105">The `behaviorExtensions` section defines the element such that it can be used in configuration.</span></span> <span data-ttu-id="efc36-106">Im Folgenden finden Sie ein Beispiel für eine typische Verhaltenserweiterung.</span><span class="sxs-lookup"><span data-stu-id="efc36-106">Here is an example of a typical behavior extension.</span></span>  
  
```xml  
<system.serviceModel>
  <extensions>
    <behaviorExtensions>
      <add name="myBehavior"
           type="Microsoft.ServiceModel.Samples.MyBehaviorSection, MyBehavior,
                 Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />
    </behaviorExtensions>
  </extensions>
</system.serviceModel>
```  
  
 <span data-ttu-id="efc36-107">Um dem Element Konfigurationsfunktionen hinzuzufügen, müssen Sie ein Konfigurationselement schreiben und registrieren.</span><span class="sxs-lookup"><span data-stu-id="efc36-107">To add configuration abilities to the element, you need to write and register a configuration element.</span></span> <span data-ttu-id="efc36-108">Weitere Informationen dazu finden Sie in der <xref:System.Configuration>-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="efc36-108">For more information on this, see the <xref:System.Configuration> documentation.</span></span>  
  
 <span data-ttu-id="efc36-109">Nachdem das Element und sein Konfigurationstyp definiert wurden, kann die Erweiterung wie im folgenden Beispiel verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="efc36-109">After the element and its configuration type are defined, the extension can be used, as shown in the following example.</span></span>  
  
```xml  
<behaviors>
  <behavior configurationName="testChannelBehavior">
    <myBehavior />
    <channelSecurity cacheCookies="false"
                     detectReplays="false"
                     maxCachedNonces="9"
                     maxClockSkew="00:00:03"
                     maxCookieCachingTime="00:07:24"
                     replayWindow="00:07:22.2190000" />
  </behavior>
</behaviors>
```  
  
## <a name="security"></a><span data-ttu-id="efc36-110">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="efc36-110">Security</span></span>  
 <span data-ttu-id="efc36-111">Es wird dringend empfohlen, voll qualifizierte Assemblynamen beim Registrieren von Typen in der `machine.config`-Datei und der `app.config`-Datei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="efc36-111">It is strongly recommended that you use fully qualified assembly names when registering types in the `machine.config` and `app.config` files.</span></span> <span data-ttu-id="efc36-112">Wenn der Typ nicht eindeutig definiert wurde, sucht der Lader vom Typ CLR an folgenden Speicherorten und in folgender Reihenfolge danach:</span><span class="sxs-lookup"><span data-stu-id="efc36-112">If the type is not uniquely defined, the CLR type loader searches for it in the following locations in the specified order:</span></span>  
  
 <span data-ttu-id="efc36-113">Wenn die Assembly des Typs bekannt ist, durchsucht der Lader den Umleitungsspeicherort der Konfigurationsdatei, den GAC, die aktuelle Assembly mit den Konfigurationsinformationen und das Anwendungsbasisverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="efc36-113">If the assembly of the type is known, the loader searches the configuration file's redirect locations, GAC, the current assembly using configuration information, and the application base directory.</span></span> <span data-ttu-id="efc36-114">Wenn die Assembly nicht bekannt ist, durchsucht der Lader die aktuelle Assembly, mscorlib und den vom `TypeResolve`-Ereignishandler zurückgegebenen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="efc36-114">If the assembly is unknown, the loader searches the current assembly, mscorlib, and the location returned by the `TypeResolve` event handler.</span></span> <span data-ttu-id="efc36-115">Diese CLR-Suchreihenfolge kann mit Hooks, wie dem Typweiterleitungsmechanismus und dem AppDomain.TypeResolve-Ereignis, geändert werden.</span><span class="sxs-lookup"><span data-stu-id="efc36-115">This CLR search order can be modified with hooks such as the Type Forwarding mechanism and the AppDomain.TypeResolve event.</span></span>  
  
 <span data-ttu-id="efc36-116">Ein Angreifer kann die CLR-Suchreihenfolge ausnutzen und nicht autorisierten Code ausführen.</span><span class="sxs-lookup"><span data-stu-id="efc36-116">An attacker can exploit the CLR search order and execute unauthorized code.</span></span> <span data-ttu-id="efc36-117">Durch die Verwendung vollqualifizierter (starker) Namen wird ein Typ eindeutig identifiziert und die Sicherheit Ihres Systems verbessert.</span><span class="sxs-lookup"><span data-stu-id="efc36-117">Using fully qualified (strong) names uniquely identifies a type and further increases security of your system.</span></span>  
  
 <span data-ttu-id="efc36-118">Weitere Informationen finden Sie unter [How the Runtime Locates Assemblies](https://go.microsoft.com/fwlink/?LinkId=95336) und <xref:System.AppDomain.TypeResolve>.</span><span class="sxs-lookup"><span data-stu-id="efc36-118">For more information, see [How the Runtime Locates Assemblies](https://go.microsoft.com/fwlink/?LinkId=95336) and <xref:System.AppDomain.TypeResolve>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efc36-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="efc36-119">See also</span></span>
- <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>
- [<span data-ttu-id="efc36-120">Konfigurieren und Erweitern der Laufzeit mit Verhalten</span><span class="sxs-lookup"><span data-stu-id="efc36-120">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
