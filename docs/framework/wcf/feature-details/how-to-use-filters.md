---
title: 'Vorgehensweise: Verwenden von Filtern'
ms.date: 03/30/2017
ms.assetid: f2c7255f-c376-460e-aa20-14071f1666e5
ms.openlocfilehash: 34ea961b0ef5db51efcae0b86f2c06171d6d756c
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "81464103"
---
# <a name="how-to-use-filters"></a>Vorgehensweise: Verwenden von Filtern
In diesem Thema werden die grundlegenden Schritte beschrieben, die erforderlich sind, um eine Routingkonfiguration mit mehreren Filtern zu erstellen. In diesem Beispiel werden Nachrichten an zwei Implementierungen eines Rechnerdiensts weitergeleitet: regularCalc und roundingCalc. Beide Implementierungen unterstützen die gleichen Vorgänge. Ein Dienst rundet vor der Rückgabe jedoch alle Berechnungen auf den nächsten ganzzahligen Wert. Eine Clientanwendung muss angeben können, ob die Rundungsversion des Diensts verwendet werden soll. Falls kein bevorzugter Dienst angegeben wird, wird für die Nachricht ein Lastenausgleich zwischen beiden Diensten durchgeführt. Beide Dienste machen die folgenden Vorgänge verfügbar:  
  
- Hinzufügen  
  
- Subtrahieren  
  
- Multiplizieren  
  
- Dividieren  
  
 Da beide Dienste die gleichen Vorgänge implementieren, können Sie den Aktionsfilter nicht verwenden, weil die in der Nachricht angegebene Aktion nicht eindeutig ist. Stattdessen müssen Sie weitere Schritte unternehmen, um sicherzustellen, dass die Nachrichten an die entsprechenden Endpunkte weitergeleitet werden.  
  
### <a name="determine-unique-data"></a>Bestimmen von eindeutigen Daten  
  
1. Da beide Dienstimplementierungen die gleichen Vorgänge behandeln und bis auf die zurückgegebenen Daten im Wesentlichen identisch sind, sind die Basisdaten von Nachrichten, die aus Clientanwendungen gesendet werden, nicht eindeutig genug, um die Weiterleitung der Anforderung einwandfrei bestimmen zu können. Aber wenn die Clientanwendung der Nachricht einen eindeutigen Headerwert hinzufügt, können Sie anhand dieses Werts bestimmen, auf welche Weise die Nachricht weitergeleitet werden soll.  
  
     Für dieses Beispiel gilt, dass mit dem folgenden Code ein benutzerdefinierter Header hinzugefügt wird, wenn die Clientanwendung eine Verarbeitung der Nachricht mit dem Rundungsrechner erfordert:  
  
    ```csharp  
    messageHeadersElement.Add(MessageHeader.CreateHeader("RoundingCalculator",
                                   "http://my.custom.namespace/", "rounding"));  
    ```  
  
     Sie können Nachrichten für diesen Header jetzt mithilfe des XPath-Filters überprüfen und Nachrichten, die den Header enthalten, an den roundCalc-Dienst weiterleiten.  
  
2. Darüber hinaus macht der Routingdienst zwei virtuelle Dienstendpunkte verfügbar, die mit den Filtern EndpointName, EndpointAddress oder PrefixEndpointAddress verwendet werden können. Damit ist das eindeutige Weiterleiten eingehender Nachrichten an eine bestimmte Rechnerimplementierung basierend auf dem Endpunkt erforderlich, an den die Clientanwendung die Anforderung sendet.  
  
### <a name="define-endpoints"></a>Definieren von Endpunkten  
  
1. Beim Definieren der vom Routingdienst verwendeten Endpunkte sollten Sie zuerst die Form des Kanals bestimmen, der von den Clients und Diensten verwendet wird. In diesem Szenario verwenden beide Zieldienste ein Anforderung-Antwort-Muster. Es wird also <xref:System.ServiceModel.Routing.IRequestReplyRouter> verwendet. Im folgenden Beispiel werden die vom Routingdienst verfügbar gemachten Dienstendpunkte definiert.  
  
    ```xml  
    <services>  
          <service behaviorConfiguration="routingConfiguration"  
                   name="System.ServiceModel.Routing.RoutingService">  
            <host>  
              <baseAddresses>  
                <add baseAddress="http://localhost/routingservice/router" />  
              </baseAddresses>  
            </host>  
            <!--Set up the inbound endpoints for the Routing Service-->  
            <!--first create the general router endpoint-->  
            <endpoint address="general"  
                      binding="wsHttpBinding"  
                      name="routerEndpoint"  
                      contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
            <!--create a virtual endpoint for the regular calculator service-->  
            <endpoint address="regular/calculator"  
                      binding="wsHttpBinding"  
                      name="calculatorEndpoint"  
                      contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
            <!--now create a virtual endpoint for the rounding calculator-->  
            <endpoint address="rounding/calculator"  
                      binding="wsHttpBinding"  
                      name="roundingEndpoint"  
                      contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
  
          </service>  
    </services>  
    ```  
  
     Mit dieser Konfiguration macht der Routingdienst drei separate Endpunkte verfügbar. Je nach den ausgewählten Optionen für die Laufzeit sendet die Clientanwendung Nachrichten an eine dieser Adressen. Nachrichten, die an einem der "virtuellen" Serviceendpunkte ("Rundung/Rechner" oder "Regular/Rechner") eingehen, werden an die entsprechende Rechnerimplementierung weitergeleitet. Falls die Clientanwendung die Anforderung nicht an einen bestimmten Endpunkt sendet, wird die Nachricht an den allgemeinen Endpunkt adressiert. Unabhängig vom ausgewählten Endpunkt kann sich die Clientanwendung auch für die Einbeziehung des benutzerdefinierten Headers entscheiden, um anzugeben, dass die Nachricht an die Implementierung des Rundungsrechners weitergeleitet werden soll.  
  
2. Im folgenden Beispiel werden die Endpunkte des Clients (Zielendpunkte) definiert, an die der Routingdienst Nachrichten weiterleitet.  
  
    ```xml  
    <client>  
          <endpoint name="regularCalcEndpoint"  
                    address="net.tcp://localhost:9090/servicemodelsamples/service/"  
                    binding="netTcpBinding"  
                    contract="*" />  
  
          <endpoint name="roundingCalcEndpoint"  
                    address="net.tcp://localhost:8080/servicemodelsamples/service/"  
                    binding="netTcpBinding"  
                    contract="*" />  
    </client>  
    ```  
  
     Mit diesen Endpunkten wird in der Filtertabelle der Zielendpunkt angegeben, an den die Nachricht gesendet wird, wenn sich dafür eine Übereinstimmung mit einem bestimmten Filter ergibt.  
  
### <a name="define-filters"></a>Filter definieren  
  
1. Um Nachrichten basierend auf dem benutzerdefinierten Header "RoundingCalculator" weiterzuleiten, den die Clientanwendung der Nachricht hinzufügt, definieren Sie einen Filter, der eine XPath-Abfrage verwendet, um das Vorhandensein dieses Headers zu überprüfen. Da dieser Header mithilfe eines benutzerdefinierten Namespace definiert wird, fügen Sie auch einen Namespaceeintrag hinzu, der ein benutzerdefiniertes Namespacepräfix von "custom" definiert, das in der XPath-Abfrage verwendet wird. Im folgenden Beispiel werden der erforderliche Routingabschnitt, die Namespacetabelle und der XPath-Filter definiert.  
  
    ```xml  
    <routing>  
          <!-- use the namespace table element to define a prefix for our custom namespace-->  
          <namespaceTable>  
            <add prefix="custom" namespace="http://my.custom.namespace/"/>  
          </namespaceTable>  
          <filters>  
            <!--define the different message filters-->  
            <!--define an xpath message filter to look for the custom header coming from the client-->  
            <filter name="XPathFilter" filterType="XPath"
                    filterData="/s12:Envelope/s12:Header/custom:RoundingCalculator = 'rounding'"/>  
          </filters>  
    </routing>  
    ```  
  
     Dieser **MessageFilter** sucht in der Nachricht nach einem RoundingCalculator-Header, der den Wert "Rundung" enthält. Dieser Header wird vom Client festgelegt, um anzugeben, dass die Nachricht an den roundingCalc-Dienst weitergeleitet werden soll.  
  
    > [!NOTE]
    > Das Namespacepräfix s12 ist standardmäßig in der Namespacetabelle `http://www.w3.org/2003/05/soap-envelope`definiert und stellt den Namespace dar.
  
2. Sie müssen auch Filter definieren, die nach Nachrichten suchen, die an den beiden virtuellen Endpunkten empfangen werden. Der erste virtuelle Endpunkt ist der "regular/calculator"-Endpunkt. Der Client kann Anforderungen an diesen Endpunkt senden, um anzugeben, dass die Nachricht an den regularCalc-Dienst weitergeleitet werden soll. In der folgenden Konfiguration wird ein Filter definiert, der anhand von <xref:System.ServiceModel.Dispatcher.EndpointNameMessageFilter> bestimmt, ob die Nachricht an einem Endpunkt empfangen wurde, dessen Name unter filterData angegeben ist.  
  
    ```xml  
    <!--define an endpoint name filter looking for messages that show up on the virtual regular calculator endpoint-->  
    <filter name="EndpointNameFilter" filterType="EndpointName" filterData="calculatorEndpoint"/>  
    ```  
  
     Wenn eine Nachricht vom Dienstendpunkt mit dem Namen "calculatorEndpoint" empfangen wird, wird dieser Filter zu `true`ausgewertet.  
  
3. Definieren Sie als Nächstes einen Filter, der nach Nachrichten sucht, die an die Adresse von roundingEndpoint gesendet werden. Der Client kann Anforderungen an diesen Endpunkt senden, um anzugeben, dass die Nachricht an den roundingCalc-Dienst weitergeleitet werden soll. Die folgende Konfiguration definiert einen <xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter> Filter, der die verwendet, um zu bestimmen, ob die Nachricht am Endpunkt "Rundung/Rechner" angekommen ist.  
  
    ```xml  
    <!--define a filter looking for messages that show up with the address prefix.  The corresponds to the rounding calc virtual endpoint-->  
    <filter name="PrefixAddressFilter" filterType="PrefixEndpointAddress"  
            filterData="http://localhost/routingservice/router/rounding/"/>  
    ```  
  
     Wenn eine Nachricht an eine Adresse `http://localhost/routingservice/router/rounding/` empfangen wird, die mit der Adresse beginnt, wird dieser Filter als **true**ausgewertet. Da die von dieser Konfiguration `http://localhost/routingservice/router` verwendete Basisadresse lautet und die für den RoundingEndpoint angegebene Adresse "Rundung/Rechner" ist, lautet `http://localhost/routingservice/router/rounding/calculator`die vollständige Adresse, die für die Kommunikation mit diesem Endpunkt verwendet wird, , die diesem Filter entspricht.  
  
    > [!NOTE]
    > Bei der Ermittlung einer Übereinstimmung wertet der PrefixEndpointAddress-Filter den Hostnamen nicht aus, weil auf einen einzelnen Host mit einer Vielzahl von Hostnamen verwiesen werden kann, die alle zulässige Möglichkeiten zum Verweisen auf den Host aus der Clientanwendung darstellen können. Es kann z. B. sein, dass alle unten aufgeführten Adressen auf den gleichen Host verweisen:  
    >
    > - localhost  
    > - 127.0.0.1  
    > - `www.contoso.com`  
    > - ContosoWeb01  
  
4. Der abschließende Filter muss das Routing von Nachrichten unterstützen, die ohne den benutzerdefinierten Header am allgemeinen Endpunkt ankommen. Für dieses Szenario sollten die Nachrichten zwischen dem regularCalc-Dienst und dem roundingCalc-Dienste wechseln. Um das "Round Robin"-Routing dieser Nachrichten zu unterstützen, verwenden Sie einen benutzerdefinierten Filter, der es einer Filterinstanz ermöglicht, für jede verarbeitete Nachricht zu entsprechen.  Im folgenden Code werden zwei Instanzen von RoundRobinMessageFilter definiert, die gruppiert werden und auf diese Weise angeben, dass dazwischen gewechselt werden soll.  
  
    ```xml  
    <!-- Set up the custom message filters.  In this example,   
         we'll use the example round robin message filter,   
         which alternates between the references-->  
    <filter name="RoundRobinFilter1" filterType="Custom"  
                    customType="CustomFilterAssembly.RoundRobinMessageFilter, CustomFilterAssembly"  
                    filterData="group1"/>  
    <filter name="RoundRobinFilter2" filterType="Custom"  
                    customType="CustomFilterAssembly.RoundRobinMessageFilter, CustomFilterAssembly"  
                    filterData="group1"/>  
    ```  
  
     Während der Laufzeit wechselt der Filtertyp zwischen allen definierten Filterinstanzen dieses Typs, die als Gruppe in einer Auflistung konfiguriert sind. Dies bewirkt, dass Nachrichten, `true` die `RoundRobinFilter1` `RoundRobinFilter2`von diesem benutzerdefinierten Filter verarbeitet werden, zwischen der Rückgabe für und wechseln.  
  
### <a name="define-filter-tables"></a>Definieren von Filtertabellen  
  
1. Um die Filter bestimmten Clientendpunkten zuzuordnen, müssen Sie diese in eine Filtertabelle einfügen. In diesem Beispielszenario werden außerdem Filterprioritätseinstellungen verwendet. Dies ist eine optionale Einstellung, mit der Sie die Reihenfolge angeben können, in der Filter verarbeitet werden. Falls keine Filterpriorität angegeben wird, werden alle Filter gleichzeitig ausgewertet.  
  
    > [!NOTE]
    > Mit der Angabe einer Filterpriorität können Sie zwar die Reihenfolge steuern, in der Filter verarbeitet werden, aber dies kann sich auch negativ auf die Leistung des Routingdiensts auswirken. Erstellen Sie die Filterlogik nach Möglichkeit so, dass die Verwendung von Filterprioritäten nicht erforderlich ist.  
  
     Im Folgenden wird die Filtertabelle definiert und der zuvor definierte "XPathFilter" zur Tabelle mit der Priorität 2 hinzugefügt. Dieser Eintrag gibt auch `XPathFilter` an, dass die Nachricht an die `roundingCalcEndpoint`weitergeleitet wird, wenn die der Nachricht entspricht.  
  
    ```xml  
    <routing>  
    ...      <filters>  
    ...      </filters>  
          <filterTables>  
            <table name="filterTable1">  
              <entries>  
                <!--add the filters to the message filter table-->  
                <!--first look for the custom header, and if we find it,  
                    send the message to the rounding calc endpoint-->  
                <add filterName="XPathFilter" endpointName="roundingCalcEndpoint" priority="2"/>  
              </entries>  
            </table>  
          </filterTables>  
    </routing>  
    ```  
  
     Beim Angeben einer Filterpriorität werden die Filter mit der höchsten Priorität zuerst ausgewertet. Wenn sich für einen oder mehrere Filter mit einer bestimmten Prioritätsstufen ein Übereinstimmung ergibt, werden keine Filter mit niedrigeren Prioritätsstufen ausgewertet. Bei diesem Szenario ist 2 die höchste angegebene Priorität, und dies ist der einzige Filtereintrag auf dieser Stufe.  
  
2. Filtereinträge wurden definiert, um eine Nachricht darauf zu überprüfen, ob diese an einem bestimmten Endpunkt empfangen wird, indem der Endpunktname oder das Adresspräfix untersucht wird. Die folgenden Einträge fügen diese beiden Filtereinträge der Filtertabelle hinzu und ordnen sie den Zielendpunkten zu, an die die Nachricht weitergeleitet wird. Für diese Filter ist eine Priorität von 1 festgelegt, um anzugeben, dass sie nur ausgeführt werden sollen, wenn sich für den vorherigen XPath-Filter keine Übereinstimmung mit der Nachricht ergeben hat.  
  
    ```xml  
    <!--if the header wasn't there, send the message based on which virtual endpoint it arrived at-->  
    <!--we determine this through the endpoint name, or through the address prefix-->  
    <add filterName="EndpointNameFilter" endpointName="regularCalcEndpoint" priority="1"/>  
    <add filterName="PrefixAddressFilter" endpointName="roundingCalcEndpoint" priority="1"/>  
    ```  
  
     Da diese Filter eine Filterpriorität von 1 aufweisen, werden diese nur ausgewertet, wenn sich für den Filter auf der Prioritätsstufe 2 keine Übereinstimmung mit der Nachricht ergeben hat. Da beide Filter außerdem die gleiche Prioritätsstufe aufweisen, werden sie gleichzeitig ausgewertet. Weil sich beide Filter gegenseitig ausschließen, kann sich nur für einen von beiden eine Übereinstimmung mit der Nachricht ergeben.  
  
3. Falls sich für eine Nachricht keine Übereinstimmung mit den vorherigen Filtern ergibt, wurde die Nachricht über den generischen Dienstendpunkt empfangen und hat keine Headerinformationen enthalten, die das Ziel für die Weiterleitung angeben. Diese Nachrichten werden vom benutzerdefinierten Filter behandelt, der dafür einen Lastausgleich zwischen den beiden Rechnerdiensten vornimmt. Im folgenden Beispiel wird veranschaulicht, wie Sie der Filtertabelle die Filtereinträge hinzufügen. Jedem Filter wird einer der beiden Zielendpunkte zugeordnet.  
  
    ```xml  
    <!--if none of the other filters have matched,   
        this message showed up on the default router endpoint,   
        with no custom header-->  
    <!--round robin these requests between the two services-->  
    <add filterName="RoundRobinFilter1" endpointName="regularCalcEndpoint" priority="0"/>  
    <add filterName="RoundRobinFilter2" endpointName="roundingCalcEndpoint" priority="0"/>  
    ```  
  
     Da diese Einträge eine Priorität von 0 angeben, werden sie nur ausgewertet, sofern sich für keinen Filter mit einer höheren Priorität eine Übereinstimmung ergibt. Da beide außerdem die gleiche Priorität aufweisen, werden sie gleichzeitig ausgewertet.  
  
     Wie bereits erwähnt, wertet der von diesen Filterdefinitionen verwendete benutzerdefinierte Filter für die empfangenen Nachrichten jeweils nur einen Eintrag als `true` aus. Da mit diesem Filter nur zwei Filter mit der gleichen angegebenen Gruppeneinstellung definiert werden, führt dies dazu, dass der Routingdienst zwischen dem Senden an regularCalcEndpoint und RoundingCalcEndpoint wechselt.  
  
4. Um Nachrichten mithilfe von Filtern auswerten zu können, muss die Filtertabelle den Dienstendpunkten zugeordnet sein, die zum Empfangen von Nachrichten verwendet werden.  Im folgenden Beispiel wird veranschaulicht, wie Sie die Routingtabelle mithilfe des Routingverhaltens den Dienstendpunkten zuordnen:  
  
    ```xml  
    <behaviors>  
      <!--default routing service behavior definition-->  
      <serviceBehaviors>  
        <behavior name="routingConfiguration">  
          <routing filterTableName="filterTable1" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
## <a name="example"></a>Beispiel  
 Es folgt eine vollständige Auflistung der Konfigurationsdatei.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- Copyright (c) Microsoft Corporation. All rights reserved -->  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service behaviorConfiguration="routingConfiguration"  
               name="System.ServiceModel.Routing.RoutingService">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost/routingservice/router" />  
          </baseAddresses>  
        </host>  
        <!--Set up the inbound endpoints for the Routing Service-->  
        <!--first create the general router endpoint-->  
        <endpoint address="general"  
                  binding="wsHttpBinding"  
                  name="routerEndpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
        <!--create a virtual endpoint for the regular calculator service-->  
        <endpoint address="regular/calculator"  
                  binding="wsHttpBinding"  
                  name="calculatorEndpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
        <!--now create a virtual endpoint for the rounding calculator-->  
        <endpoint address="rounding/calculator"  
                  binding="wsHttpBinding"  
                  name="roundingEndpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
  
      </service>  
    </services>  
    <behaviors>  
      <!--default routing service behavior definition-->  
      <serviceBehaviors>  
        <behavior name="routingConfiguration">  
          <routing filterTableName="filterTable1" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
    <client>  
<!--set up the destination endpoints-->  
      <endpoint name="regularCalcEndpoint"  
                address="net.tcp://localhost:9090/servicemodelsamples/service/"  
                binding="netTcpBinding"  
                contract="*" />  
  
      <endpoint name="roundingCalcEndpoint"  
                address="net.tcp://localhost:8080/servicemodelsamples/service/"  
                binding="netTcpBinding"  
                contract="*" />  
    </client>  
    <routing>  
      <!-- use the namespace table element to define a prefix for our custom namespace-->  
      <namespaceTable>  
        <add prefix="custom" namespace="http://my.custom.namespace/"/>  
      </namespaceTable>  
      <filters>  
        <!--define the different message filters-->  
        <!--define an xpath message filter to look for the custom header coming from the client-->  
        <filter name="XPathFilter" filterType="XPath" filterData="/s12:Envelope/s12:Header/custom:RoundingCalculator = 'rounding'"/>  
  
        <!--define an endpoint name filter looking for messages that show up on the virtual regular calculator endpoint-->  
        <filter name="EndpointNameFilter" filterType="EndpointName" filterData="calculatorEndpoint"/>  
  
        <!--define a filter looking for messages that show up with the address prefix.  The corresponds to the rounding calc virtual endpoint-->  
        <filter name="PrefixAddressFilter" filterType="PrefixEndpointAddress" filterData="http://localhost/routingservice/router/rounding/"/>  
  
        <!--Set up the custom message filters.  In this example, we'll use the example round robin message filter, which alternates between the references-->  
        <filter name="RoundRobinFilter1" filterType="Custom" customType="CustomFilterAssembly.RoundRobinMessageFilter, CustomFilterAssembly" filterData="group1"/>  
        <filter name="RoundRobinFilter2" filterType="Custom" customType="CustomFilterAssembly.RoundRobinMessageFilter, CustomFilterAssembly" filterData="group1"/>  
      </filters>  
      <filterTables>  
        <table name="filterTable1">  
          <entries>  
            <!--add the filters to the message filter table-->  
            <!--first look for the custom header, and if we find it, send the message to the rounding calc endpoint-->  
            <add filterName="XPathFilter" endpointName="roundingCalcEndpoint" priority="2"/>  
  
            <!--if the header wasn't there, send the message based on which virtual endpoint it arrived at-->  
            <!--we determine this through the endpoint name, or through the address prefix-->  
            <add filterName="EndpointNameFilter" endpointName="regularCalcEndpoint" priority="1"/>  
            <add filterName="PrefixAddressFilter" endpointName="roundingCalcEndpoint" priority="1"/>  
  
            <!--if none of the other filters have matched, this message showed up on the default router endpoint, with no custom header-->  
            <!--round robin these requests between the two services-->  
            <add filterName="RoundRobinFilter1" endpointName="regularCalcEndpoint" priority="0"/>  
            <add filterName="RoundRobinFilter2" endpointName="roundingCalcEndpoint" priority="0"/>  
          </entries>  
        </table>  
      </filterTables>  
    </routing>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Routingdienste](../../../../docs/framework/wcf/samples/routing-services.md)
