---
title: Auswählen eines Filters
ms.date: 03/30/2017
ms.assetid: 67ab5af9-b9d9-4300-b3b1-41abb5a1fd10
ms.openlocfilehash: f783b6416f2330d272c4c756a3ca0cd332f3c6e7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276099"
---
# <a name="choosing-a-filter"></a><span data-ttu-id="e291d-102">Auswählen eines Filters</span><span class="sxs-lookup"><span data-stu-id="e291d-102">Choosing a Filter</span></span>

<span data-ttu-id="e291d-103">Beim Konfigurieren des Routingdiensts ist es wichtig, richtige Nachrichtenfilter auszuwählen und so zu konfigurieren, dass Sie genaue Übereinstimmungen mit den Nachrichten erzielen können, die Sie empfangen.</span><span class="sxs-lookup"><span data-stu-id="e291d-103">When configuring the Routing Service, it is important to select correct message filters and configure them to allow you to make exact matches against the messages you receive.</span></span> <span data-ttu-id="e291d-104">Falls die ausgewählten Filter in Bezug auf die Übereinstimmungen zu ungenau oder falsch konfiguriert sind, werden die Nachrichten nicht korrekt weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="e291d-104">If the filters you select are overly broad in their matches or are incorrectly configured, messages are routed incorrectly.</span></span> <span data-ttu-id="e291d-105">Wenn die Filter zu restriktiv sind, kann es sein, dass für einige Nachrichten keine gültigen Weiterleitungsrouten verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="e291d-105">If the filters are too restrictive, you may not have any valid routes available for some of your messages.</span></span>

## <a name="filter-types"></a><span data-ttu-id="e291d-106">Filtertypen</span><span class="sxs-lookup"><span data-stu-id="e291d-106">Filter Types</span></span>

<span data-ttu-id="e291d-107">Beim Auswählen der vom Routingdienst verwendeten Filter ist es wichtig, dass Sie verstehen, wie die einzelnen Filter funktionieren. Außerdem sollten Sie wissen, welche Informationen in Verbindung mit den eingehenden Nachrichten verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="e291d-107">When selecting the filters that are used by the Routing Service, it is important that you understand how each filter works as well as what information is available as part of the incoming messages.</span></span> <span data-ttu-id="e291d-108">Falls beispielsweise alle Nachrichten über den gleichen Endpunkt empfangen werden, sind die Adress- und EndpointName-Filter nicht hilfreich, weil alle Nachrichten Übereinstimmungen mit diesen Filtern aufweisen.</span><span class="sxs-lookup"><span data-stu-id="e291d-108">For instance, if all messages are received over the same endpoint, the Address and EndpointName filters are not useful because all messages match these filters.</span></span>

### <a name="action"></a><span data-ttu-id="e291d-109">Action</span><span class="sxs-lookup"><span data-stu-id="e291d-109">Action</span></span>

<span data-ttu-id="e291d-110">Der Action-Filter überprüft die <xref:System.ServiceModel.Channels.MessageHeaders.Action%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e291d-110">The Action filter inspects the <xref:System.ServiceModel.Channels.MessageHeaders.Action%2A> property.</span></span> <span data-ttu-id="e291d-111">Falls der Inhalt des Action-Headers in der Nachricht mit dem Filterdatenwert übereinstimmt, der in der Filterkonfiguration angegeben ist, gibt dieser Filter `true` zurück.</span><span class="sxs-lookup"><span data-stu-id="e291d-111">If the contents of the Action header in the message match the filter data value specified in the filter configuration, then this filter returns `true`.</span></span> <span data-ttu-id="e291d-112">Im folgenden Beispiel wird ein definiert `FilterElement` , das den Aktionsfilter verwendet, um Nachrichten mit einem Aktions Header abzugleichen, der den Wert enthält `http://namespace/contract/operation/` .</span><span class="sxs-lookup"><span data-stu-id="e291d-112">The following example defines a `FilterElement` that uses the Action filter to match messages with an action header that contains a value of `http://namespace/contract/operation/`.</span></span>

```xml
<filter name="action1" filterType="Action" filterData="http://namespace/contract/operation/" />
```

```csharp
ActionMessageFilter action1 = new ActionMessageFilter(new string[] { "http://namespace/contract/operation" });
```

<span data-ttu-id="e291d-113">Dieser Filter sollte beim Weiterleiten von Nachrichten verwendet werden, die einen eindeutigen Action-Header enthalten.</span><span class="sxs-lookup"><span data-stu-id="e291d-113">This filter should be used when routing messages that contain a unique Action header.</span></span>

### <a name="endpointaddress"></a><span data-ttu-id="e291d-114">EndpointAddress</span><span class="sxs-lookup"><span data-stu-id="e291d-114">EndpointAddress</span></span>

<span data-ttu-id="e291d-115">Der EndpointAddress-Filter überprüft die EndpointAddress, über die die Nachricht empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="e291d-115">The EndpointAddress filter inspects the EndpointAddress that the message was received on.</span></span> <span data-ttu-id="e291d-116">Wenn die Adresse, über die die Nachricht eingeht, genau mit der in der Filterkonfiguration angegebenen Filteradresse übereinstimmt, gibt dieser Filter `true` zurück.</span><span class="sxs-lookup"><span data-stu-id="e291d-116">If the address that the message arrives at exactly matches the filter address specified in the filter configuration, then this filter returns `true`.</span></span> <span data-ttu-id="e291d-117">Im folgenden Beispiel wird ein definiert `FilterElement` , das den Adress Filter verwendet, um Nachrichten abzugleichen, die an "http:///vdir/s.svc/b" adressiert sind \<hostname> .</span><span class="sxs-lookup"><span data-stu-id="e291d-117">The following example defines a `FilterElement` that uses the Address filter to match any messages addressed to "http://\<hostname>/vdir/s.svc/b".</span></span>

```xml
<filter name="address1" filterType="EndpointAddress" filterData="http://host/vdir/s.svc/b" />
```

```csharp
EndpointAddressMessageFilter address1 = new EndpointAddressMessageFilter(new EndpointAddress("http://host/vdir/s.svc/b"), false);
```

> [!NOTE]
> <span data-ttu-id="e291d-118">Beachten Sie dabei, dass sich der Hostnamenteil einer Adresse in Abhängigkeit davon unterscheiden kann, ob der Client den vollqualifizierten Domänennamen, den NetBIOS-Namen, die IP-Adresse oder einen anderen Namen verwendet.</span><span class="sxs-lookup"><span data-stu-id="e291d-118">It is important to note that the host name portion of an address can differ based on whether the client uses the fully qualified domain name, NetBIOS name, IP address, or other name.</span></span> <span data-ttu-id="e291d-119">Da verschiedene Werte auf den gleichen Host verweisen können, besteht das Standardverhalten für diesen Vergleich nicht darin, beim Ermitteln von Übereinstimmungen den Hostnamenteil der Adresse zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e291d-119">Because differing values can refer to the same host, the default behavior for this comparison is to not use the host name portion of the address when performing matches.</span></span>
>
> <span data-ttu-id="e291d-120">Dieses Verhalten kann geändert werden, damit der Vergleich beim programmgesteuerten Konfigurieren des Routingdiensts den Hostnamen auswerten kann.</span><span class="sxs-lookup"><span data-stu-id="e291d-120">This behavior can be modified to allow the comparison to evaluate the host name when configuring the Routing Service programmatically.</span></span>

<span data-ttu-id="e291d-121">Dieser Filter sollte verwendet werden, wenn die eingehenden Nachrichten an eine eindeutige Adresse adressiert sind.</span><span class="sxs-lookup"><span data-stu-id="e291d-121">This filter should be used when the incoming messages are addressed to a unique address.</span></span>

### <a name="endpointaddressprefix"></a><span data-ttu-id="e291d-122">EndpointAddressPrefix</span><span class="sxs-lookup"><span data-stu-id="e291d-122">EndpointAddressPrefix</span></span>

<span data-ttu-id="e291d-123">Der EndpointAddressPrefix-Filter ähnelt dem EndpointAddress-Filter.</span><span class="sxs-lookup"><span data-stu-id="e291d-123">The EndpointAddressPrefix filter is similar to the EndpointAddress filter.</span></span> <span data-ttu-id="e291d-124">Der EndpointAddressPrefix-Filter überprüft die EndpointAddress, über die die Nachricht empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="e291d-124">The EndpointAddressPrefix filter inspects the EndpointAddress that the message was received on.</span></span> <span data-ttu-id="e291d-125">Der EndpointAddressPrefix-Filter fungiert jedoch als Platzhalter, indem er Übereinstimmungen für Adressen ermittelt, die mit dem in der Filterkonfiguration angegebenen Wert beginnen.</span><span class="sxs-lookup"><span data-stu-id="e291d-125">However the EndpointAddressPrefix filter acts as a wildcard by matching addresses that begin with the value specified in the filter configuration.</span></span> <span data-ttu-id="e291d-126">Im folgenden Beispiel wird ein definiert `FilterElement` , das den endpointadresssspree Fix-Filter verwendet, um Nachrichten abzugleichen, die an adressiert sind `http://<hostname>/vdir*` .</span><span class="sxs-lookup"><span data-stu-id="e291d-126">The following example defines a `FilterElement` that uses the EndpointAddressPrefix filter to match any messages addressed to `http://<hostname>/vdir*`.</span></span>

```xml
<filter name="prefix1" filterType="EndpointAddressPrefix" filterData="http://host/vdir" />
```

```csharp
PrefixEndpointAddressMessageFilter prefix1 = new PrefixEndpointAddressMessageFilter(new EndpointAddress("http://host/vdir/s.svc/b"), false);
```

> [!NOTE]
> <span data-ttu-id="e291d-127">Beachten Sie dabei, dass sich der Hostnamenteil einer Adresse in Abhängigkeit davon unterscheiden kann, ob der Client den vollqualifizierten Domänennamen, den NetBIOS-Namen, die IP-Adresse oder einen anderen Namen verwendet.</span><span class="sxs-lookup"><span data-stu-id="e291d-127">It is important to note that the host name portion of an address can differ based on whether the client uses the fully qualified domain name, NetBIOS name, IP address, or other name.</span></span> <span data-ttu-id="e291d-128">Da verschiedene Werte auf den gleichen Host verweisen können, besteht das Standardverhalten für diesen Vergleich nicht darin, beim Ermitteln von Übereinstimmungen den Hostnamenteil der Adresse zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e291d-128">Because differing values can refer to the same host, the default behavior for this comparison is to not use the host name portion of the address when performing matches.</span></span>

<span data-ttu-id="e291d-129">Dieser Filter sollte verwendet werden, wenn eingehende Nachrichten weitergeleitet werden, die über ein gemeinsames Adresspräfix verfügen.</span><span class="sxs-lookup"><span data-stu-id="e291d-129">This filter should be used when routing incoming messages that share a common address prefix.</span></span>

### <a name="and"></a><span data-ttu-id="e291d-130">AND</span><span class="sxs-lookup"><span data-stu-id="e291d-130">AND</span></span>

<span data-ttu-id="e291d-131">Der AND-Filter filtert nicht direkt nach einem Wert innerhalb einer Nachricht, sondern ermöglicht Ihnen die Kombination von zwei anderen Filtern, um eine `AND`-Bedingung zu erstellen. Dabei müssen beide Filter eine Übereinstimmung mit der Nachricht ergeben, bevor für den AND-Filter `true` ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="e291d-131">The AND filter does not directly filter on a value within a message, but allows you to combine two other filters to create an `AND` condition where both filters must match the message before the AND filter evaluates to `true`.</span></span> <span data-ttu-id="e291d-132">Auf diese Weise können Sie komplexe Filter erstellen, die nur dann Übereinstimmungen ergeben, wenn alle Unterfilter zu Übereinstimmungen führen.</span><span class="sxs-lookup"><span data-stu-id="e291d-132">This allows you to create complex filters that only match if all the sub-filters match.</span></span> <span data-ttu-id="e291d-133">Im folgenden Beispiel werden ein Adressfilter und ein Aktionsfilter definiert. Anschließend wird ein AND-Filter definiert, der eine Nachricht sowohl für den Adressfilter als auch für den Aktionsfilter auswertet.</span><span class="sxs-lookup"><span data-stu-id="e291d-133">The following example defines an address filter and an action filter, and then defines an AND filter that evaluates a message against both the address and action filters.</span></span> <span data-ttu-id="e291d-134">Falls der Adressfilter und der Aktionsfilter zu Übereinstimmungen führen, gibt der AND-Filter `true` zurück.</span><span class="sxs-lookup"><span data-stu-id="e291d-134">If both the address and the action filters match, then the AND filter returns `true`.</span></span>

```xml
<filter name="address1" filterType="AddressPrefix" filterData="http://host/vdir"/>
<filter name="action1" filterType="Action" filterData="http://namespace/contract/operation/"/>
<filter name="and1" filterType="And" filter1="address1" filter2="action1" />
```

```csharp
EndpointAddressMessageFilter address1 = new EndpointAddressMessageFilter(new EndpointAddress("http://host/vdir/s.svc/b"), false);
ActionMessageFilter action1 = new ActionMessageFilter(new string[] { "http://namespace/contract/operation" });
StrictAndMessageFilter and1=new StrictAndMessageFilter(address1, action1);
```

<span data-ttu-id="e291d-135">Dieser Filter sollte verwendet werden, wenn Sie die Logik mehrerer Filter kombinieren müssen, um festzulegen, wann eine Übereinstimmung erzielt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e291d-135">This filter should be used when you must combine the logic from multiple filters to determine when a match should be made.</span></span> <span data-ttu-id="e291d-136">Wenn Sie z. B. über mehrere Ziele verfügen, die nur bestimmte Kombinationen von Aktionen und Nachrichten unter bestimmten Adressen empfangen dürfen, können Sie die erforderlichen Aktions- und Adressfilter mithilfe eines AND-Filters kombinieren.</span><span class="sxs-lookup"><span data-stu-id="e291d-136">For example, if you have multiple destinations that must receive only certain combinations of actions and messages to particular addresses, you can use an AND filter to combine the necessary Action and Address filters.</span></span>

### <a name="custom"></a><span data-ttu-id="e291d-137">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="e291d-137">Custom</span></span>

<span data-ttu-id="e291d-138">Wenn Sie den benutzerdefinierten Filtertyp auswählen, müssen Sie einen CustomType-Wert angeben, der den Typ der Assembly enthält, die die **MessageFilter** -Implementierung enthält, die für diesen Filter verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e291d-138">When selecting the Custom filter type, you must provide a customType value that contains the type of the assembly that contains the **MessageFilter** implementation to be used for this filter.</span></span> <span data-ttu-id="e291d-139">Außerdem muss "filterData" alle Werte enthalten, die der benutzerdefinierte Filter beim Auswerten der Nachrichten ggf. erfordert.</span><span class="sxs-lookup"><span data-stu-id="e291d-139">Additionally, filterData must contain any values that the custom filter may require in its evaluation of messages.</span></span> <span data-ttu-id="e291d-140">Im folgenden Beispiel wird ein `FilterElement` definiert, dass die `CustomAssembly.MyCustomMsgFilter`-MessageFilter-Implementierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="e291d-140">The following example defines a `FilterElement` that uses the `CustomAssembly.MyCustomMsgFilter` MessageFilter implementation.</span></span>

```xml
<filter name="custom1" filterType="Custom" customType="CustomAssembly.MyCustomMsgFilter, CustomAssembly" filterData="Custom Data" />
```

```csharp
MyCustomMsgFilter custom1=new MyCustomMsgFilter("Custom Data");
```

<span data-ttu-id="e291d-141">Wenn Sie eine benutzerdefinierte abgleichslogik für eine Nachricht ausführen müssen, die nicht von den in bereitgestellten Filtern abgedeckt ist [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] , müssen Sie einen benutzerdefinierten Filter erstellen, bei dem es sich um eine Implementierung der **MessageFilter** -Klasse handelt.</span><span class="sxs-lookup"><span data-stu-id="e291d-141">If you need to perform custom matching logic against a message that is not covered by the filters provided with [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)], you must create a custom filter that is an implementation of the **MessageFilter** class.</span></span> <span data-ttu-id="e291d-142">Sie können z. B. einen benutzerdefinierten Filter erstellen, der ein Feld in der eingehenden Nachricht mit einer Liste bekannter Werte vergleicht, die dem Filter als Konfiguration vorliegen. Oder Sie können einen Filter erstellen, der den Hashwert für ein bestimmtes Nachrichtenelement generiert und diesen Wert dann untersucht und angibt, ob der Filter `true` oder `false` zurückgeben soll.</span><span class="sxs-lookup"><span data-stu-id="e291d-142">For example, you might create a custom filter that compares a field in the incoming message against a list of known values given to the filter as configuration, or that hashes a particular message element and then examines that value to determine whether the filter should return `true` or `false`.</span></span>

### <a name="endpointname"></a><span data-ttu-id="e291d-143">EndpointName</span><span class="sxs-lookup"><span data-stu-id="e291d-143">EndpointName</span></span>

<span data-ttu-id="e291d-144">Der EndpointName-Filter überprüft den Namen des Endpunkts, der die Nachricht empfangen hat.</span><span class="sxs-lookup"><span data-stu-id="e291d-144">The EndpointName filter inspects the name of the endpoint that received the message.</span></span> <span data-ttu-id="e291d-145">Im folgenden Beispiel wird ein definiert `FilterElement` , das den EndpointName-Filter verwendet, um Nachrichten weiterzuleiten, die auf "SvcEndpoint" empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="e291d-145">The following example defines a `FilterElement` that uses the EndpointName filter to route messages received on the "SvcEndpoint".</span></span>

```xml
<filter name="name1" filterType="Endpoint" filterData="SvcEndpoint" />
```

```csharp
EndpointNameMessageFilter name1 = new EndpointNameMessageFilter("SvcEndpoint");
```

<span data-ttu-id="e291d-146">Dieser Filter ist nützlich, wenn der Routingdienst mehr als einen benannten Dienstendpunkt verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="e291d-146">This filter is useful when the Routing Service exposes more than one named service endpoint.</span></span> <span data-ttu-id="e291d-147">Sie können z. B. zwei Endpunkte verfügbar machen, die der Routingdienst zum Empfangen von Nachrichten verwendet. Einer wird von Prioritätskunden verwendet, die eine Echtzeitverarbeitung ihrer Nachrichten benötigen, während der andere Endpunkt Nachrichten empfängt, die nicht eilig sind.</span><span class="sxs-lookup"><span data-stu-id="e291d-147">For example, you might expose two endpoints that the Routing Service uses to receive messages; one is used by priority customers who require real-time processing of their messages, while the other endpoint receives messages that are not time sensitive.</span></span>

<span data-ttu-id="e291d-148">Sie können zwar häufig die Übereinstimmungsprüfung für vollständige Adressen verwenden, um zu ermitteln, über welchen Endpunkt eine Nachricht empfangen wurde, aber die Verwendung des definierten Endpunktnamens stellt eine einfache Alternative dar, die oft weniger fehleranfällig ist. Dies gilt besonders beim Konfigurieren eines Routingdiensts mithilfe einer Konfigurationsdatei (bei denen Endpunktnamen ein erforderliches Attribut darstellen).</span><span class="sxs-lookup"><span data-stu-id="e291d-148">While you can often use full address matching to determine which endpoint a message was received on, using the defined endpoint name instead is a convenient shortcut that is often less error prone, especially when configuring a Routing Service using a configuration file (where endpoint names are a required attribute).</span></span>

### <a name="matchall"></a><span data-ttu-id="e291d-149">MatchAll</span><span class="sxs-lookup"><span data-stu-id="e291d-149">MatchAll</span></span>

<span data-ttu-id="e291d-150">Der MatchAll-Filter ergibt für alle empfangenen Nachrichten Übereinstimmungen.</span><span class="sxs-lookup"><span data-stu-id="e291d-150">The MatchAll filter matches any received message.</span></span> <span data-ttu-id="e291d-151">Dies ist nützlich, wenn Sie alle empfangenen Nachrichten immer an einen bestimmten Endpunkt weiterleiten müssen, z. B. bei einem Protokollierungsdienst, der eine Kopie jeder empfangenen Nachricht speichert.</span><span class="sxs-lookup"><span data-stu-id="e291d-151">It is useful if you must always route all received messages to a specific endpoint, such as a logging service that stores a copy of all received messages.</span></span> <span data-ttu-id="e291d-152">Im folgenden Beispiel wird ein `FilterElement` definiert, das den MatchAll-Filter verwendet.</span><span class="sxs-lookup"><span data-stu-id="e291d-152">The following example defines a `FilterElement` that uses the MatchAll filter.</span></span>

```xml
<filter name="matchAll1" filterType="MatchAll" />
```

```csharp
MatchAllMessageFilter matchAll1 = new MatchAllMessageFilter();
```

### <a name="xpath"></a><span data-ttu-id="e291d-153">XPath</span><span class="sxs-lookup"><span data-stu-id="e291d-153">XPath</span></span>

<span data-ttu-id="e291d-154">Mit dem XPath-Filter können Sie eine XPath-Abfrage angeben, die verwendet wird, um ein bestimmtes Element innerhalb der Nachricht zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="e291d-154">The XPath filter allows you to specify an XPath query that is used to inspect a specific element within the message.</span></span> <span data-ttu-id="e291d-155">Die XPath-Filterung ist eine leistungsstarke Filteroption, mit der Sie jeden per XML-Adressierung erreichbaren Eintrag in der Nachricht direkt untersuchen können. Dafür ist es jedoch erforderlich, dass Sie über genaue Kenntnisse der Struktur der Nachrichten verfügen, die Sie empfangen.</span><span class="sxs-lookup"><span data-stu-id="e291d-155">XPath filtering is a powerful filtering option that allows you to directly inspect any XML addressable entry within the message; however it requires that you have specific knowledge of the structure of the messages that you are receiving.</span></span> <span data-ttu-id="e291d-156">Im folgenden Beispiel wird ein definiert `FilterElement` , das den XPath-Filter verwendet, um die Nachricht für ein Element mit dem Namen "Element" innerhalb des Namespace zu überprüfen, auf den das Namespace Präfix "NS" verweist.</span><span class="sxs-lookup"><span data-stu-id="e291d-156">The following example defines a `FilterElement` that uses the XPath filter to inspect the message for an element named "element" within the namespace referenced by the "ns" namespace prefix.</span></span>

```xml
<filter name="xpath1" filterType="XPath" filterData="//ns:element" />
```

```csharp
XPathMessageFilter xpath1=new XPathMessageFilter("//ns:element");
```

<span data-ttu-id="e291d-157">Dieser Filter ist nützlich, wenn Sie wissen, dass die empfangenen Nachrichten einen bestimmten Wert enthalten.</span><span class="sxs-lookup"><span data-stu-id="e291d-157">This filter is useful if you know that the messages you are receiving contain a specific value.</span></span> <span data-ttu-id="e291d-158">Wenn Sie beispielsweise zwei Versionen des gleichen Diensts hosten und wissen, dass an die neuere Version des Diensts adressierte Nachrichten in einem benutzerdefinierten Header einen eindeutigen Wert enthalten, können Sie einen speziellen Filter erstellen. Der Filter verwendet XPath zum Navigieren zu diesem Header und vergleicht den im Header enthaltenen Wert mit einem anderen Wert in der Filterkonfiguration, um zu bestimmen, ob der Filter eine Übereinstimmung ergibt.</span><span class="sxs-lookup"><span data-stu-id="e291d-158">For example, if you are hosting two versions of the same service and you know that messages addressed to the newer version of the service contain a unique value in a custom header, you can create a filter that uses XPath to navigate to this header and compares the value present in the header to another given in the filter configuration to determine if the filter matches.</span></span>

<span data-ttu-id="e291d-159">Da XPath-Abfragen häufig eindeutige Namespaces enthalten, bei denen es sich oft um lange oder komplexe Zeichenfolgenwerte handelt, können Sie mit dem XPath-Filter die Namespacetabelle zum Definieren eindeutiger Präfixe für die Namespaces verwenden.</span><span class="sxs-lookup"><span data-stu-id="e291d-159">Because XPath queries often contain unique namespaces, which are often lengthy or complex string values, the XPath filter allows you to use the namespace table to define unique prefixes for your namespaces.</span></span> <span data-ttu-id="e291d-160">Weitere Informationen zur Namespace Tabelle finden Sie unter [Nachrichtenfilter](message-filters.md).</span><span class="sxs-lookup"><span data-stu-id="e291d-160">For more information about the namespace table, see [Message Filters](message-filters.md).</span></span>

<span data-ttu-id="e291d-161">Weitere Informationen zum Entwerfen von XPath-Abfragen finden Sie unter [XPath-Syntax](/previous-versions/dotnet/netframework-4.0/ms256471(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="e291d-161">For more information about designing XPath queries, see [XPath Syntax](/previous-versions/dotnet/netframework-4.0/ms256471(v=vs.100)).</span></span>

## <a name="see-also"></a><span data-ttu-id="e291d-162">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e291d-162">See also</span></span>

- [<span data-ttu-id="e291d-163">Nachrichtenfilter</span><span class="sxs-lookup"><span data-stu-id="e291d-163">Message Filters</span></span>](message-filters.md)
- [<span data-ttu-id="e291d-164">Vorgehensweise: Verwenden von Filtern</span><span class="sxs-lookup"><span data-stu-id="e291d-164">How To: Use Filters</span></span>](how-to-use-filters.md)
