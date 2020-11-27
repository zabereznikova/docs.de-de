---
title: Nachrichtenfilter
ms.date: 03/30/2017
helpviewer_keywords:
- routing [WCF], message filters
ms.assetid: cb33ba49-8b1f-4099-8acb-240404a46d9a
ms.openlocfilehash: a0cc4663b9a3044d0ab80f03479a024acba50a3f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279778"
---
# <a name="message-filters"></a>Nachrichtenfilter

Um das inhaltsbasierte Routing zu implementieren, verwendet der Routingdienst <xref:System.ServiceModel.Dispatcher.MessageFilter>-Implementierungen, die bestimmte Abschnitte einer Nachricht überprüfen, z. B. Adresse, Endpunktname oder eine bestimmte XPath-Anweisung. Wenn keiner der von [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] bereitgestellten Nachrichtenfilter Ihren Anforderungen entspricht, können Sie einen benutzerdefinierten Filter erstellen, indem Sie eine neue Implementierung der <xref:System.ServiceModel.Dispatcher.MessageFilter>-Basisklasse erstellen.  
  
 Beim Konfigurieren des Routing Dienstanbieter müssen Sie Filterelemente ( <xref:System.ServiceModel.Routing.Configuration.FilterElement> -Objekte) definieren, die den Typ von **MessageFilter** und alle unterstützenden Daten beschreiben, die zum Erstellen des Filters erforderlich sind, z. b. bestimmte Zeichen folgen Werte, die in der Nachricht gesucht werden sollen. Beachten Sie, dass beim Erstellen der Filterelemente nur die einzelnen Nachrichtenfilter definiert werden. Um die Filter zum Auswerten und Weiterleiten von Nachrichten zu verwenden, müssen Sie zusätzlich eine Filtertabelle definieren (<xref:System.ServiceModel.Routing.Configuration.FilterTableEntryCollection>).  
  
 Jeder Eintrag in der Filtertabelle verweist auf ein Filterelement und gibt den Clientendpunkt an, an den eine Nachricht weitergeleitet wird, wenn sich für die Nachricht eine Übereinstimmung mit dem Filter ergibt. Die Filtertabelleneinträge ermöglichen Ihnen auch das Angeben einer Auflistung von Sicherungsendpunkten (<xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection>). Damit wird eine Liste von Endpunkten definiert, an die die Nachricht im Falle eines Übertragungsfehlers gesendet wird, sofern das Senden an den primären Endpunkt erfolgt. Diese Endpunkte werden in der angegebenen Reihefolge abgearbeitet, bis ein Sendevorgang erfolgreich ist.  
  
## <a name="message-filters"></a>Nachrichtenfilter  

 Die vom Routingdienst verwendeten Nachrichtenfilter stellen allgemeine Funktionen zur Auswahl von Nachrichten bereit. Beispiele hierfür sind das Auswerten des Namens eines Endpunkts, an den eine Nachricht gesendet wurde, die SOAP-Aktion oder die Adresse bzw. das Adresspräfix, an die bzw. das die Nachricht gesendet wurde. Filter können auch mit einer `AND`-Bedingung verknüpft werden, sodass Nachrichten nur dann an einen Endpunkt weitergeleitet werden, wenn die Nachricht mit beiden Filtern zu Übereinstimmungen führt. Sie können benutzerdefinierte Filter auch erstellen, indem Sie eine eigene Implementierung von <xref:System.ServiceModel.Dispatcher.MessageFilter> erstellen.  
  
 In der folgenden Tabelle sind der jeweils vom Routingdienst verwendete <xref:System.ServiceModel.Routing.Configuration.FilterType> und die Klasse aufgeführt, die den spezifischen Nachrichtenfilter implementiert. Außerdem ist der erforderliche <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>-Parameter angegeben.  
  
|Filtertyp|BESCHREIBUNG|Bedeutung der Filterdaten|Beispielfilter|  
|------------------|-----------------|-------------------------|--------------------|  
|Aktion|Verwendet die <xref:System.ServiceModel.Dispatcher.ActionMessageFilter>-Klasse, um eine Übereinstimmung für Nachrichten zu erzielen, die eine bestimmte Aktion enthalten.|Die Aktion, nach der gefiltert werden soll.|\<filter name="action1" filterType="Action" filterData="http://namespace/contract/operation" />|  
|EndpointAddress|Verwendet die- <xref:System.ServiceModel.Dispatcher.EndpointAddressMessageFilter> Klasse mit, <xref:System.ServiceModel.Dispatcher.EndpointAddressMessageFilter.IncludeHostNameInComparison%2A>  ==  `true` um Nachrichten abzugleichen, die eine bestimmte Adresse enthalten.|Die Adresse, nach der gefiltert werden soll (im To-Header).|\<filter name="address1" filterType="EndpointAddress" filterData="http://host/vdir/s.svc/b"  />|  
|EndpointAddressPrefix|Verwendet die- <xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter> Klasse mit, <xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter.IncludeHostNameInComparison%2A>  ==  `true` um Nachrichten abzugleichen, die ein bestimmtes Adress Präfix enthalten.|Die Adresse, nach der unter Verwendung der längsten Präfixübereinstimmung gefiltert werden soll.|\<filter name="prefix1" filterType="EndpointAddressPrefix" filterData="http://host/" />|  
|Und|Verwendet die <xref:System.ServiceModel.Dispatcher.StrictAndMessageFilter>-Klasse, die vor der Rückgabe immer beide Bedingungen auswertet.|"FilterData" wird nicht verwendet. Stattdessen verfügen filter1 und filter2 über die Namen der entsprechenden Nachrichtenfilter (auch in der Tabelle), die zusammengeführt **werden sollen**.|\<filter name="and1" filterType="And" filter1="address1" filter2="action1" />|  
|Benutzerdefiniert|Ein benutzerdefinierter Typ, der die <xref:System.ServiceModel.Dispatcher.MessageFilter>-Klasse erweitert und über einen Konstruktor verfügt, der eine Zeichenfolge verwendet.|Das customType-Attribut ist der vollqualifizierte Typname der zu erstellenden Klasse. "filterData" ist die Zeichenfolge, die beim Erstellen des Filters an den Konstruktor übergeben werden soll.|\<filter name="custom1" filterType="Custom" customType="CustomAssembly.CustomMsgFilter, CustomAssembly" filterData="Custom Data" />|  
|EndpointName|Verwendet die <xref:System.ServiceModel.Dispatcher.EndpointNameMessageFilter>-Klasse, um für Nachrichten basierend auf dem Namen des Dienstendpunkts, an dem diese empfangen wurden, eine Übereinstimmung zu erzielen.|Der Name des Dienst Endpunkts, z. b.: "serviceEndpoint1".  Hierbei sollte es sich um einen der Endpunkte handeln, die vom Routingdienst verfügbar gemacht werden.|\<filter name="stock1" filterType="Endpoint" filterData="SvcEndpoint" />|  
|MatchAll|Verwendet die <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter>-Klasse. Dieser Filter führt für alle eingehenden Nachrichten zu Übereinstimmungen.|"filterData" wird nicht verwendet. Dieser Filter führt immer zu Übereinstimmungen mit allen Nachrichten.|\<filter name="matchAll1" filterType="MatchAll" />|  
|XPath|Verwendet die <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>-Klasse, um für bestimmte XPath-Abfragen in der Nachricht Übereinstimmungen zu ermitteln.|Die XPath-Abfrage, die beim Ermitteln von Übereinstimmungen für Nachrichten verwendet wird.|\<filter name="XPath1" filterType="XPath" filterData="//ns:element" />|  
  
 Im folgenden Beispiel werden Filtereinträge definiert, die die Nachrichtenfilter „XPath“, „EndpointName“ und „PrefixEndpointAddress“ verwenden. Dieses Beispiel veranschaulicht außerdem die Verwendung eines benutzerdefinierten Filters für die Einträge RoundRobinFilter1 und RoundRobinFilter2.  
  
```xml  
<filters>  
     <filter name="XPathFilter" filterType="XPath"
             filterData="/s12:Envelope/s12:Header/custom:RoundingCalculator = 1"/>  
     <filter name="EndpointNameFilter" filterType="EndpointName"
             filterData="calculatorEndpoint"/>  
     <filter name="PrefixAddressFilter" filterType="PrefixEndpointAddress"
             filterData="http://localhost/routingservice/router/rounding/"/>  
     <filter name="RoundRobinFilter1" filterType="Custom"
             customType="RoutingServiceFilters.RoundRobinMessageFilter,
             RoutingService" filterData="group1"/>  
     <filter name="RoundRobinFilter2" filterType="Custom"
             customType="RoutingServiceFilters.RoundRobinMessageFilter,
             RoutingService" filterData="group1"/>  
</filters>  
```  
  
> [!NOTE]
> Wenn Sie einfach nur einen Filter definieren, führt dies noch nicht dazu, dass Nachrichten mit diesem Filter ausgewertet werden. Sie müssen den Filter einer Filtertabelle hinzufügen, die dann dem Dienstendpunkt zugeordnet wird, der vom Routingdienst verfügbar gemacht wird.  
  
### <a name="namespace-table"></a>Namespacetabelle  

 Bei einem XPath-Filter können die Filterdaten, die die XPath-Abfrage enthalten, aufgrund der Verwendung von Namespaces sehr umfangreich werden. Um dieses Problem zu umgehen, ermöglicht der Routingdienst das Definieren Ihrer eigenen Namespacepräfixe mithilfe der Namespacetabelle.  
  
 Die Namespacetabelle ist eine Auflistung von <xref:System.ServiceModel.Routing.Configuration.NamespaceElement>-Objekten, in der die Namespacepräfixe für allgemeine Namespaces definiert sind, die in einem XPath verwendet werden können. Unten sind die standardmäßigen Namespaces und Namespacepräfixe aufgeführt, die in der Namespacetabelle enthalten sind.  
  
|Präfix|Namespace|  
|------------|---------------|  
|s11|`http://schemas.xmlsoap.org/soap/envelope`|  
|s12|`http://www.w3.org/2003/05/soap-envelope`|  
|wsaAugust2004|`http://schemas.xmlsoap.org/ws/2004/08/addressing`|  
|wsa10|`http://www.w3.org/2005/08/addressing`|  
|sm|`http://schemas.microsoft.com/serviceModel/2004/05/xpathfunctions`|  
|tempuri|`http://tempuri.org`|  
|ser|`http://schemas.microsoft.com/2003/10/Serialization`|  
  
 Wenn Sie wissen, dass Sie in den XPath-Abfragen einen bestimmten Namespace verwenden, können Sie diesen der Namespacetabelle zusammen mit einem eindeutigen Namespacepräfix hinzufügen und das Präfix statt des vollständigen Namespaces in XPath-Abfragen verwenden. Im folgenden Beispiel wird das Präfix "Custom" für den-Namespace definiert `"http://my.custom.namespace"` , der dann in der XPath-Abfrage verwendet wird, die in "FilterData" enthalten ist.  
  
```xml  
<namespaceTable>  
     <add prefix="custom" namespace="http://my.custom.namespace/"/>  
</namespaceTable>  
<filters>  
     <filter name="XPathFilter" filterType="XPath" filterData="/s12:Envelope/s12:Header/custom:RoundingCalculator = 1"/>  
</filters>  
```  
  
## <a name="filter-tables"></a>Filtertabellen  

 Während jedes Filterelement einen logischen Vergleich definiert, der auf eine Nachricht angewendet werden kann, stellt die Filtertabelle die Zuordnung zwischen dem Filterelement und dem Zielclientendpunkt bereit. Bei einer Filtertabelle handelt es sich um eine benannte Auflistung von <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement>-Objekten, die die Zuordnung zwischen einem Filter, einem primären Zielendpunkt und einer Liste alternativer Sicherungsendpunkte definieren. Die Filtertabelleneinträge ermöglichen es Ihnen auch, eine optionale Priorität für jede Filterbedingung anzugeben. Im folgenden Beispiel werden zwei Filter definiert. Anschließend wird eine Filtertabelle definiert, in der jedem Filter ein Zielendpunkt zugeordnet wird.  
  
```xml  
<routing>  
     <filters>  
       <filter name="AddAction" filterType="Action" filterData="Add" />  
       <filter name="SubtractAction" filterType="Action" filterData="Subtract" />  
     </filters>  
     <filterTables>  
       <table name="routingTable1">  
         <filters>  
           <add filterName="AddAction" endpointName="Addition" />  
           <add filterName="SubtractAction" endpointName="Subtraction" />  
         </filters>  
       </table>  
     </filterTables>
</routing>  
```  
  
### <a name="filter-evaluation-priority"></a>Priorität bei der Filterauswertung  

 Standardmäßig werden alle Einträge in der Filtertabelle gleichzeitig ausgewertet, und die jeweils ausgewertete Nachricht wird an die Endpunkte weitergeleitet, die den einzelnen übereinstimmenden Filtereinträgen zugeordnet sind. Wenn sich für die Auswertung mehrerer Filter `true` ergibt und die Nachricht den Typ unidirektional oder duplex aufweist, wird die Nachricht per Multicast an die Endpunkte für alle übereinstimmenden Filter übermittelt. Anforderung-Antwort-Nachrichten können nicht per Multicast gesendet werden, weil nur eine Antwort an den Client zurückgegeben werden kann.  
  
 Sie können eine komplexere Routinglogik implementieren, indem Sie für jeden Filter Prioritätsstufen angeben. Der Routingdienst wertet zuerst alle Filter auf höchster Prioritätsstufe aus. Wenn eine Nachricht auf dieser Stufe eine Übereinstimmung mit einem Filter ergibt, werden keine Filter mit einer niedrigeren Priorität verarbeitet. Zum Beispiel wird eine eingehende unidirektionale Nachricht zuerst für alle Filter mit der Priorität 2 ausgewertet. Die Nachricht ergibt auf dieser Prioritätsstufe keine Übereinstimmung. Als Nächstes wird die Nachricht also mit Filtern mit der Priorität 1 verglichen. Für zwei Filter mit der Priorität 1 ergibt sich für die Nachricht eine Übereinstimmung, und da es sich um eine unidirektionale Nachricht handelt, wird diese an beide Zielendpunkte weitergeleitet.  Da für die Filter der Priorität 1 eine Übereinstimmung ermittelt wurde, werden keine Filter der Priorität 0 ausgewertet.  
  
> [!NOTE]
> Wenn keine Priorität angegeben wird, wird die Standardpriorität 0 verwendet.  
  
 Im folgenden Beispiel wird eine Filtertabelle definiert, in der für die Filter, auf die in der Tabelle verwiesen wird, die Prioritäten von 2, 1 und 0 angegeben werden.  
  
```xml  
<filterTables>  
     <filterTable name="filterTable1">  
          <add filterName="XPathFilter" endpointName="roundingCalcEndpoint"
               priority="2"/>  
          <add filterName="EndpointNameFilter" endpointName="regularCalcEndpoint"
               priority="1"/>  
          <add filterName="PrefixAddressFilter" endpointName="roundingCalcEndpoint"
               priority="1"/>  
          <add filterName="MatchAllMessageFilter" endpointName="defaultCalcEndpoint"
               priority="0"/>  
     </filterTable>  
</filterTables>  
```  
  
 Falls sich im vorangehenden Beispiel für eine Nachricht eine Übereinstimmung mit dem XPathFilter ergibt, wird diese an den roundingCalcEndpoint weitergeleitet. Es werden dann keine weiteren Filter der Tabelle ausgewertet, weil alle anderen Filter über eine niedrigere Priorität verfügen. Falls die Nachricht jedoch nicht zu einer Übereinstimmung mit XPathFilter führt, wird sie mit allen Filtern der nächstniedrigeren Priorität ausgewertet, also EndpointNameFilter und PrefixAddressFilter.  
  
> [!NOTE]
> Nach Möglichkeit sollten Sie anstelle einer Priorität exklusive Filter verwenden, weil die Prioritätsauswertung die Leistung beeinträchtigen kann.  
  
### <a name="backup-lists"></a>Sicherungslisten  

 Für jeden Filter in der Filtertabelle kann optional eine Sicherungsliste angegeben werden, bei der es sich um eine benannte Auflistung von Endpunkten handelt (<xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection>). Diese Auflistung enthält eine sortierte Liste von Endpunkten, an die die Nachricht bei Auftreten einer <xref:System.ServiceModel.CommunicationException> gesendet wird, sofern das Senden an unter <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement.EndpointName%2A> angegebenen primären Endpunkt erfolgt. Im folgenden Beispiel wird eine Sicherungsliste mit dem Namen "backupserviceendpoints" definiert, die zwei Endpunkte enthält.  
  
```xml  
<filterTables>  
     <filterTable name="filterTable1">  
          <add filterName="MatchAllFilter1" endpointName="Destination" backupList="backupEndpointList"/>  
     </filterTable>  
</filterTables>  
<backupLists>  
     <backupList name="backupEndpointList">  
          <add endpointName="backupServiceQueue" />  
          <add endpointName="alternateServiceQueue" />  
     </backupList>  
</backupLists>  
```  
  
 Wenn im vorherigen Beispiel ein Fehler bei einem Sendevorgang an den primären Endpunkt "Destination" auftritt, versucht der Routing Dienst, an jeden Endpunkt in der Reihenfolge zu senden, in der Sie aufgelistet sind, wobei zuerst an backupservicequeue gesendet und anschließend an "Alternative Service Queue" gesendet wird, wenn der Sendevorgang an Backup Service Queue fehlschlägt. Falls für alle Sicherungsendpunkte ein Fehler auftritt, wird ein Fehler zurückgegeben.
