---
title: Benutzerdefinierte Filter
ms.date: 03/30/2017
ms.assetid: 97cf247d-be0a-4057-bba9-3be5c45029d5
ms.openlocfilehash: ae020173544372c3ce097c8ac57e53f3fde37514
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185212"
---
# <a name="custom-filters"></a><span data-ttu-id="13c2e-102">Benutzerdefinierte Filter</span><span class="sxs-lookup"><span data-stu-id="13c2e-102">Custom Filters</span></span>
<span data-ttu-id="13c2e-103">Mit benutzerdefinierten Filtern können Sie eine Übereinstimmungslogik definieren, was mit den vom System bereitgestellten Nachrichtenfiltern nicht möglich ist.</span><span class="sxs-lookup"><span data-stu-id="13c2e-103">Custom filters allow you to define matching logic that cannot be accomplished using the system-provided message filters.</span></span> <span data-ttu-id="13c2e-104">Sie können z. B. einen benutzerdefinierten Filter erstellen, der einen Hashwert für ein bestimmtes Nachrichtenelement erstellt und dann untersucht, um zu ermitteln, ob der Filter "true" oder "false" zurückgeben soll.</span><span class="sxs-lookup"><span data-stu-id="13c2e-104">For example, you might create a custom filter that hashes a particular message element and then examines the value to determine whether the filter should return true or false.</span></span>  
  
## <a name="implementation"></a><span data-ttu-id="13c2e-105">Implementierung</span><span class="sxs-lookup"><span data-stu-id="13c2e-105">Implementation</span></span>  
 <span data-ttu-id="13c2e-106">Ein benutzerdefinierter Filter ist eine Implementierung der abstrakten <xref:System.ServiceModel.Dispatcher.MessageFilter>-Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="13c2e-106">A custom filter is an implementation of the <xref:System.ServiceModel.Dispatcher.MessageFilter> abstract base class.</span></span> <span data-ttu-id="13c2e-107">Beim Implementieren des benutzerdefinierten Filters kann der Konstruktor optional einen einzelnen Zeichenfolgenparameter akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="13c2e-107">When implementing your custom filter, the constructor can optionally accept a single string parameter.</span></span> <span data-ttu-id="13c2e-108">Dieser Parameter enthält die Konfigurationsinformationen, die an den MessageFilter-Konstruktor übergeben werden, um alle Werte bzw. die Konfiguration bereitzustellen, die der Filter zur Laufzeit zur Ermittlung von Übereinstimmungen benötigt.</span><span class="sxs-lookup"><span data-stu-id="13c2e-108">This parameter contains the configuration information that is passed to the MessageFilter constructor in order to provide any values or configuration that the filter needs at runtime in order to perform matches.</span></span> <span data-ttu-id="13c2e-109">Dies kann z. B. verwendet werden, um einen Wert bereitzustellen, nach dem der Filter innerhalb der ausgewerteten Nachricht sucht.</span><span class="sxs-lookup"><span data-stu-id="13c2e-109">For example, this might be used to provide a value that the filter looks for within the message being evaluated.</span></span> <span data-ttu-id="13c2e-110">Das folgende Beispiel veranschaulicht eine grundlegende Implementierung eines benutzerdefinierten Nachrichtenfilters, der einen Zeichenfolgenparameter akzeptiert:</span><span class="sxs-lookup"><span data-stu-id="13c2e-110">The following example demonstrates a basic implementation of a custom message filter that accepts a string parameter:</span></span>  
  
```csharp  
public class MyMessageFilter: MessageFilter  
{  
    string filterData;  
    public MyMessageFilter(string filterData)  
    {  
        if(string.IsNullOrEmpty(filterData)  
            throw new ArgumentNullException("filterData");  
        this.filterData=filterData;  
    }  
    public override bool Match(System.ServiceModel.Channels.Message message)  
    {  
        ...  
        return retValue;  
    }  
    public override bool Match(System.ServiceModel.Channels.MessageBuffer buffer)  
    {  
        ...  
        return retValue;  
    }  
}  
```  
  
> [!NOTE]
> <span data-ttu-id="13c2e-111">In einer tatsächlichen Implementierung enthält die Match-Methode(n) Logik, die die Nachricht untersucht, um zu bestimmen, ob dieser Nachrichtenfilter **true** oder **false**zurückgeben soll.</span><span class="sxs-lookup"><span data-stu-id="13c2e-111">In an actual implementation, the Match method(s) contains logic that will examine the message to determine if this message filter should return **true** or **false**.</span></span>  
  
### <a name="performance"></a><span data-ttu-id="13c2e-112">Leistung</span><span class="sxs-lookup"><span data-stu-id="13c2e-112">Performance</span></span>  
 <span data-ttu-id="13c2e-113">Wenn ein benutzerdefinierter Filter implementiert wird, ist es wichtig, die maximale Zeitspanne zu berücksichtigen, die für den Abschluss der Auswertung einer Meldung durch den Filter erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="13c2e-113">When implementing a custom filter, it is important to take into consideration the maximum length of time required for the filter to complete the evaluation of a message.</span></span> <span data-ttu-id="13c2e-114">Da eine Meldung möglicherweise mit mehreren Filtern ausgewertet wird, bevor eine Übereinstimmung gefunden wird, ist es wichtig sicherzustellen, dass die Clientanforderung kein Timeout zurückgibt, bevor alle Filter ausgewertet werden können.</span><span class="sxs-lookup"><span data-stu-id="13c2e-114">Since a message may be evaluated against multiple filters before a match is found, it is important to ensure that the client request does not time out before all filters can be evaluated.</span></span> <span data-ttu-id="13c2e-115">Daher sollte ein benutzerdefinierter Filter nur den erforderlichen Code für die Auswertung des Inhalts oder die Attribute einer Meldung enthalten, damit bestimmt werden kann, ob es eine Entsprechung für die Filterkriterien findet.</span><span class="sxs-lookup"><span data-stu-id="13c2e-115">Therefore a custom filter should contain only the code necessary to evaluate the contents or attributes of a message in order to determine if it matches the filter criteria.</span></span>  
  
 <span data-ttu-id="13c2e-116">Im Allgemeinen sollten Sie bei der Implementierung eines benutzerdefinierten Filters Folgendes vermeiden:</span><span class="sxs-lookup"><span data-stu-id="13c2e-116">In general, you should avoid the following when implementing a custom filter:</span></span>  
  
- <span data-ttu-id="13c2e-117">E/A, z. B. Speichern von Daten auf einem Datenträger oder in einer Datenbank.</span><span class="sxs-lookup"><span data-stu-id="13c2e-117">IO, such as saving data to disk or to a database.</span></span>  
  
- <span data-ttu-id="13c2e-118">Unnötige Verarbeitungsvorgänge, z. B. Ausführung von Schleifen für mehrere Datensätze in einem Dokument.</span><span class="sxs-lookup"><span data-stu-id="13c2e-118">Unnecessary processing, such as looping over multiple records in a document.</span></span>  
  
- <span data-ttu-id="13c2e-119">Blockieren von Vorgängen, z. B. Aufrufe, die das Abrufen einer Sperre für freigegebene Ressourcen oder das Ausführen von Suchabfragen für eine Datenbank enthalten.</span><span class="sxs-lookup"><span data-stu-id="13c2e-119">Blocking operations, such as calls that involve obtaining a lock on shared resources or performing lookups against a database.</span></span>  
  
 <span data-ttu-id="13c2e-120">Vor der Verwendung eines benutzerdefinierten Filters in einer Produktionsumgebung sollten Sie Leistungstests ausführen, um die durchschnittliche erforderliche Zeit zur Auswertung einer Meldung zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="13c2e-120">Before using a custom filter in a production environment, you should run performance tests to determine the average length of time that the filter takes to evaluate a message.</span></span> <span data-ttu-id="13c2e-121">In Kombination mit der durchschnittlichen Verarbeitungszeit der anderen in der Filtertabelle verwendeten Filter können Sie so genau den maximalen Timeoutwert bestimmen, der von der Clientanwendung angegeben werden sollte.</span><span class="sxs-lookup"><span data-stu-id="13c2e-121">When combined with the average processing time of the other filters used in the filter table, this will allow you to accurately determine the maximum timeout value that should be specified by the client application.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="13c2e-122">Verwendung</span><span class="sxs-lookup"><span data-stu-id="13c2e-122">Usage</span></span>  
 <span data-ttu-id="13c2e-123">Um Ihren benutzerdefinierten Filter mit dem Routingdienst verwenden zu können, müssen Sie ihn der Filtertabelle hinzufügen, indem Sie einen neuen Filtereintrag vom Typ "Benutzerdefiniert", den vollqualifizierten Typnamen des Nachrichtenfilters und den Namen der Assembly angeben.</span><span class="sxs-lookup"><span data-stu-id="13c2e-123">In order to use your custom filter with the Routing Service, you must add it to the filter table by specifying a new filter entry of type "Custom," the fully qualified type name of the message filter, and the name of your assembly.</span></span>  <span data-ttu-id="13c2e-124">Wie bei anderen MessageFilters auch, können Sie unter "filterData" eine Zeichenfolge angeben, die an den Konstruktor des benutzerdefinierten Filters übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="13c2e-124">As with other MessageFilters, you can specify the string filterData that will be passed to your custom filter’s constructor.</span></span>  
  
 <span data-ttu-id="13c2e-125">In den folgenden Beispielen wird veranschaulicht, wie Sie einen benutzerdefinierten Filter mit dem Routingdienst verwenden:</span><span class="sxs-lookup"><span data-stu-id="13c2e-125">The following examples demonstrate using a custom filter with the Routing Service:</span></span>  
  
```xml  
<!--ROUTING SECTION -->  
<routing>  
  <filters>  
    <filter name="CustomFilter1" filterType="Custom"
            customType="CustomAssembly.MyMessageFilter,
            CustomAssembly" filterData="custom data" />  
  </filters>  
  <filterTables>  
    <table name="routingTable1">  
      <filters>  
        <add filterName="CustomFilter1" endpointName="CalculatorService" />  
      </filters>  
    </table>  
  </filterTables>  
</routing>  
```  
  
```csharp  
RoutingConfiguration rc = new RoutingConfiguration();  
List<ServiceEndpoint> endpointList = new List<ServiceEndpoint>();  
endpointList.Add(client);  
rc.FilterTable.Add(new MyMessageFilter("CustomData"), endpointList);  
```
