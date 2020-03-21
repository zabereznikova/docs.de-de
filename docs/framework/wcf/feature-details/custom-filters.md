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
# <a name="custom-filters"></a>Benutzerdefinierte Filter
Mit benutzerdefinierten Filtern können Sie eine Übereinstimmungslogik definieren, was mit den vom System bereitgestellten Nachrichtenfiltern nicht möglich ist. Sie können z. B. einen benutzerdefinierten Filter erstellen, der einen Hashwert für ein bestimmtes Nachrichtenelement erstellt und dann untersucht, um zu ermitteln, ob der Filter "true" oder "false" zurückgeben soll.  
  
## <a name="implementation"></a>Implementierung  
 Ein benutzerdefinierter Filter ist eine Implementierung der abstrakten <xref:System.ServiceModel.Dispatcher.MessageFilter>-Basisklasse. Beim Implementieren des benutzerdefinierten Filters kann der Konstruktor optional einen einzelnen Zeichenfolgenparameter akzeptieren. Dieser Parameter enthält die Konfigurationsinformationen, die an den MessageFilter-Konstruktor übergeben werden, um alle Werte bzw. die Konfiguration bereitzustellen, die der Filter zur Laufzeit zur Ermittlung von Übereinstimmungen benötigt. Dies kann z. B. verwendet werden, um einen Wert bereitzustellen, nach dem der Filter innerhalb der ausgewerteten Nachricht sucht. Das folgende Beispiel veranschaulicht eine grundlegende Implementierung eines benutzerdefinierten Nachrichtenfilters, der einen Zeichenfolgenparameter akzeptiert:  
  
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
> In einer tatsächlichen Implementierung enthält die Match-Methode(n) Logik, die die Nachricht untersucht, um zu bestimmen, ob dieser Nachrichtenfilter **true** oder **false**zurückgeben soll.  
  
### <a name="performance"></a>Leistung  
 Wenn ein benutzerdefinierter Filter implementiert wird, ist es wichtig, die maximale Zeitspanne zu berücksichtigen, die für den Abschluss der Auswertung einer Meldung durch den Filter erforderlich ist. Da eine Meldung möglicherweise mit mehreren Filtern ausgewertet wird, bevor eine Übereinstimmung gefunden wird, ist es wichtig sicherzustellen, dass die Clientanforderung kein Timeout zurückgibt, bevor alle Filter ausgewertet werden können. Daher sollte ein benutzerdefinierter Filter nur den erforderlichen Code für die Auswertung des Inhalts oder die Attribute einer Meldung enthalten, damit bestimmt werden kann, ob es eine Entsprechung für die Filterkriterien findet.  
  
 Im Allgemeinen sollten Sie bei der Implementierung eines benutzerdefinierten Filters Folgendes vermeiden:  
  
- E/A, z. B. Speichern von Daten auf einem Datenträger oder in einer Datenbank.  
  
- Unnötige Verarbeitungsvorgänge, z. B. Ausführung von Schleifen für mehrere Datensätze in einem Dokument.  
  
- Blockieren von Vorgängen, z. B. Aufrufe, die das Abrufen einer Sperre für freigegebene Ressourcen oder das Ausführen von Suchabfragen für eine Datenbank enthalten.  
  
 Vor der Verwendung eines benutzerdefinierten Filters in einer Produktionsumgebung sollten Sie Leistungstests ausführen, um die durchschnittliche erforderliche Zeit zur Auswertung einer Meldung zu bestimmen. In Kombination mit der durchschnittlichen Verarbeitungszeit der anderen in der Filtertabelle verwendeten Filter können Sie so genau den maximalen Timeoutwert bestimmen, der von der Clientanwendung angegeben werden sollte.  
  
## <a name="usage"></a>Verwendung  
 Um Ihren benutzerdefinierten Filter mit dem Routingdienst verwenden zu können, müssen Sie ihn der Filtertabelle hinzufügen, indem Sie einen neuen Filtereintrag vom Typ "Benutzerdefiniert", den vollqualifizierten Typnamen des Nachrichtenfilters und den Namen der Assembly angeben.  Wie bei anderen MessageFilters auch, können Sie unter "filterData" eine Zeichenfolge angeben, die an den Konstruktor des benutzerdefinierten Filters übergeben wird.  
  
 In den folgenden Beispielen wird veranschaulicht, wie Sie einen benutzerdefinierten Filter mit dem Routingdienst verwenden:  
  
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
