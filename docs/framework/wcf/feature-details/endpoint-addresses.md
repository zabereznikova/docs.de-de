---
title: Endpunktadressen
ms.date: 03/30/2017
helpviewer_keywords:
- addresses [WCF]
- Windows Communication Foundation [WCF], addresses
- WCF [WCF], addresses
ms.assetid: 13f269e3-ebb1-433c-86cf-54fbd866a627
ms.openlocfilehash: cbae03c52f3cc39f7afd422a34b16e99a60d9f3a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283219"
---
# <a name="endpoint-addresses"></a>Endpunktadressen
Jedem Endpunkt ist eine Adresse zugeordnet, um den Endpunkt suchen und identifizieren zu können. Diese Adresse besteht hauptsächlich aus einem Uniform Resource Identifier (URI), der den Speicherort des Endpunkts angibt. Die Endpunkt Adresse wird im WCF-Programmiermodell (Windows Communication Foundation) durch die <xref:System.ServiceModel.EndpointAddress>-Klasse dargestellt, die eine optionale <xref:System.ServiceModel.EndpointAddress.Identity%2A>-Eigenschaft enthält, die die Authentifizierung des Endpunkts durch andere Endpunkte ermöglicht, die Nachrichten mit ihm austauschen, sowie einen Satz optionaler <xref:System.ServiceModel.EndpointAddress.Headers%2A> Eigenschaften, die alle anderen SOAP-Header definieren, die für den Dienst erforderlich sind. Die optionalen Header stellen zusätzliche und ausführlichere Adressinformationen bereit, um den Dienstendpunkt zu identifizieren oder mit ihm zu interagieren. Die Adresse eines Endpunkts wird während der Übertragung als WS-Adressierungsendpunktverweis (Endpoint Reference, EPR) dargestellt.  
  
## <a name="uri-structure-of-an-address"></a>URI-Struktur einer Adresse  
 Der Adress-URI besteht für die meisten Transporte aus vier Teilen. Beispielsweise können die vier Teile des URI-`http://www.fabrikam.com:322/mathservice.svc/secureEndpoint` wie folgt aufgelistet werden:  
  
- Schema: `http:`
  
- Computer: `www.fabrikam.com`  
  
- (optional) Port: 322  
  
- Pfad: /mathservice.svc/secureEndpoint  
  
## <a name="defining-an-address-for-a-service"></a>Definieren einer Adresse für einen Dienst  
 Die Endpunktadresse für einen Dienst kann entweder imperativ über Code oder deklarativ über die Konfiguration angegeben werden. Die Definition von Endpunkten im Code ist normalerweise nicht geeignet, da die Bindungen und Adressen für einen bereitgestellten Dienst sich in der Regel von denen unterscheiden, die während der Entwicklung des Diensts verwendet werden. Im Allgemeinen ist es praktischer, Dienstendpunkte nicht mit Code, sondern mit Konfiguration zu definieren. Werden die Bindung und die Adressinformationen nicht in den Code integriert, ist eine Änderung ohne Neukompilierung oder eine erneute Bereitstellung der Anwendung möglich.  
  
### <a name="defining-an-address-in-configuration"></a>Definieren einer Adresse in der Konfiguration  
 Um einen Endpunkt in einer Konfigurationsdatei zu definieren, verwenden Sie den [\<Endpunkt >](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) -Elements. Weitere Informationen und ein Beispiel finden Sie unter [Angeben einer Endpunkt Adresse](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).  
  
### <a name="defining-an-address-in-code"></a>Definieren einer Adresse im Code  
 Eine Endpunktadresse kann mit der <xref:System.ServiceModel.EndpointAddress>-Klasse im Code erstellt werden. Weitere Informationen und ein Beispiel finden Sie unter [Angeben einer Endpunkt Adresse](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).  
  
### <a name="endpoints-in-wsdl"></a>Endpunkt in WSDL  
 Eine Endpunktadresse kann auch in WSDL (Web Services Description Language) als ein WS-Addressierungs-EPR-Element innerhalb des `wsdl:port`-Elements des entsprechenden Endpunkts dargestellt werden. Der EPR enthält die Endpunktadresse sowie eventuelle Adresseigenschaften. Weitere Informationen und ein Beispiel finden Sie unter [Angeben einer Endpunkt Adresse](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).  
  
## <a name="multiple-iis-binding-support-in-net-framework-35"></a>Unterstützung mehrerer IIS-Bindungen in .NET Framework 3,5  
 Internetdienstanbieter hosten oftmals viele Anwendungen auf demselben Server und derselben Website, um die Websitedichte zu erhöhen und die Gesamtkosten (TCO) zu senken. Diese Anwendungen werden i.&#160;d.&#160;R. an unterschiedliche Basisadressen gebunden. Eine Internetinformationsdienste(IIS)-Website kann mehrere Anwendungen enthalten. Auf die Anwendungen auf einer Website kann über eine oder mehrere IIS-Bindungen zugegriffen werden.  
  
 IIS-Bindungen stellen zwei Angaben bereit: ein Bindungsprotokoll und Bindungsinformationen. Das Bindungsprotokoll definiert das Schema, das für die Kommunikation verwendet wird, und die Bindungsinformationen dienen dem Zugriff auf die Website.  
  
 Das folgende Beispiel zeigt die Komponenten, die in einer IIS-Bindung enthalten sein können:  
  
- Bindungsprotokoll: HTTP  
  
- Bindungsinformationen: IP-Adresse, Anschluss, Hostheader  
  
 IIS kann mehrere Bindungen für jede Site angeben, was zu mehreren Basisadressen für jedes Schema führt. Vor .NET Framework 3,5 wurde von WCF nicht mehrere Adressen für ein Schema unterstützt. Wenn Sie angegeben wurden, wurde während der Aktivierung ein <xref:System.ArgumentException> ausgelöst.  
  
 Der .NET Framework 3,5 ermöglicht es Internet Dienstanbietern, mehrere Anwendungen mit unterschiedlichen Basisadressen für dasselbe Schema auf derselben Website zu hosten.  
  
 Eine Website kann beispielsweise die folgenden Basisadressen enthalten:  
  
- `http://payroll.myorg.com/Service.svc`
  
- `http://shipping.myorg.com/Service.svc`
  
 Bei .NET Framework 3,5 geben Sie einen Präfix Filter auf der AppDomain-Ebene in der Konfigurationsdatei an. Dies geschieht mit dem [\<baseadresssspree fixfilters >](../../../../docs/framework/configure-apps/file-schema/wcf/baseaddressprefixfilters.md) -Element, das eine Liste von Präfixen enthält. Die eingehenden, von IIS angegebenen Basisadressen werden anhand der optionalen Präfixliste gefiltert. Standardmäßig werden alle Adressen übergeben, wenn ein Präfix nicht angegeben ist. Wenn die Präfixergebnisse angegeben werden, wird nur die Basisadresse übergeben, die dem Schema entspricht.  
  
 Es folgt ein Beispiel für Konfigurationscode, der die Präfixfilter verwendet.  
  
```xml  
<system.serviceModel>  
  <serviceHostingEnvironment>  
     <baseAddressPrefixFilters>  
        <add prefix="net.tcp://payroll.myorg.com:8000"/>  
        <add prefix="http://shipping.myorg.com:8000"/>  
    </baseAddressPrefixFilters>  
  </serviceHostingEnvironment>  
</system.serviceModel>  
```  
  
 Im vorherigen Beispiel sind `net.tcp://payroll.myorg.com:8000` und `http://shipping.myorg.com:8000` die einzigen Basisadressen für die jeweiligen Schemas, die durchlaufen werden.  
  
 Der `baseAddressPrefixFilter` unterstützt keine Platzhalter.  
  
 Die von IIS angegebenen Basisadressen verfügen möglicherweise über Adressen, die an andere, nicht in der `baseAddressPrefixFilters`-Liste vorhandene Schemas gebunden sind. Diese Adressen werden nicht herausgefiltert.  
  
## <a name="multiple-iis-binding-support-in-net-framework-4-and-later"></a>Unterstützung für mehrere IIS-Bindungen in .NET Framework 4 und höher  
 Ab .NET 4 können Sie die Unterstützung für mehrere Bindungen in IIS aktivieren, ohne eine Basisadresse auswählen zu müssen. Legen Sie dazu die Einstellung <xref:System.ServiceModel.ServiceHostingEnvironment> von <xref:System.ServiceModel.ServiceHostingEnvironment.MultipleSiteBindingsEnabled%2A> auf TRUE fest. Die Unterstützung ist auf HTTP-Protokollschemas begrenzt.  
  
 Im folgenden finden Sie ein Beispiel für Konfigurations Code, der multiplesitebindingsenabled auf [\<servicehoststingenvironment->](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)verwendet.  
  
```xml  
<system.serviceModel>  
  <serviceHostingEnvironment multipleSiteBindingsEnabled="true" >  
  </serviceHostingEnvironment>  
</system.serviceModel>  
```  
  
 Wenn mehrere Websitebindungen mit dieser Einstellung aktiviert wurden, werden alle Einstellungen von baseAddressPrefixFilters sowohl für HTTP-Protokolle als auch für andere Protokolle ignoriert.  
  
 Weitere Informationen und Beispiele finden Sie [unter unterstützen mehrerer IIS-Site Bindungen](../../../../docs/framework/wcf/feature-details/supporting-multiple-iis-site-bindings.md) und <xref:System.ServiceModel.ServiceHostingEnvironment.MultipleSiteBindingsEnabled%2A>.  
  
## <a name="extending-addressing-in-wcf-services"></a>Erweitern der Adressierung in WCF-Diensten  
 Das Standard Adressierungs Modell der WCF-Dienste verwendet den Endpunkt Adress-URI für die folgenden Zwecke:  
  
- Um die Abhöradresse des Diensts anzugeben, d.&#160;h. den Speicherort, den der Endpunkt auf Nachrichten abhört  
  
- Um den SOAP-Adressfilter anzugeben, d.&#160;h. die Adresse, die ein Endpunkt als SOAP-Header erwartet  
  
 Die Werte für beide Situationen können separat angegeben werden. Dadurch werden mehrere Adressierungserweiterungen für nützliche Szenarien möglich:  
  
- SOAP-Vermittler: Eine von einem Client gesendete Nachricht durchläuft einen oder mehrere zusätzliche Dienste, die die Nachricht verarbeiten, bevor sie ihr endgültiges Ziel erreicht. SOAP-Vermittler können verschiedene Aufgaben ausführen, z.&#160;B. Caching, Routing, Lastenausgleich oder Schemavalidierung für Nachrichten. Dieses Szenario wird durch das Senden von Nachrichten an eine separate physische Adresse erreicht (`via`), die auf den Vermittler verweist, anstatt nur an eine logische Adresse (`wsa:To`), die auf das endgültige Ziel verweist.  
  
- Die Abhöradresse des Endpunkts ist ein privater URI und wird auf einen anderen Wert als seine `listenURI`-Eigenschaft festgelegt.  
  
 Nachrichten sollten zunächst an die Transportadresse gesendet werden, die von `via` angegeben wird, bevor sie an eine andere Remoteadresse gesendet werden, die vom `to`-Parameter angegeben wird und an der sich der Dienst befindet. In den meisten Internetszenarien sind der `via`-URI der <xref:System.ServiceModel.EndpointAddress.Uri%2A>-Eigenschaft und die endgültige `to`-Adresse des Diensts identisch. Eine Unterscheidung zwischen den beiden Adressen ist nur beim manuellen Routing erforderlich.  
  
### <a name="addressing-headers"></a>Adressierungsheader  
 Ein Endpunkt kann neben seinem Basis-URI von einem oder mehreren SOAP-Headern adressiert werden. Dies ist beispielsweise in SOAP-Vermittlerszenarien nützlich, in denen ein Endpunkt es erfordert, dass seine Clients SOAP-Header einfügen, die sich an Vermittler richten.  
  
 Sie können benutzerdefinierte Adressheader auf zweierlei Weise definieren &#8211; entweder mit Code oder einer Konfiguration:  
  
- Im Code werden benutzerdefinierte Adressheader mithilfe der <xref:System.ServiceModel.Channels.AddressHeader>-Klasse erstellt und dann bei der Erstellung einer <xref:System.ServiceModel.EndpointAddress> verwendet.  
  
- In der Konfiguration werden benutzerdefinierte [\<Header >](../../configure-apps/file-schema/wcf/headers.md) als untergeordnete Elemente des [\<Endpunkt >](../../configure-apps/file-schema/wcf/endpoint-of-client.md) Elements angegeben.  
  
 Die Konfiguration ist im Allgemeinen dem Code vorzuziehen, da sie es Ihnen ermöglicht, die Header nach der Bereitstellung zu ändern.  
  
### <a name="custom-listening-addresses"></a>Benutzerdefinierte Abhöradressen  
 Sie können die Abhöradresse auf einen anderen Wert als den URI des Endpunkts festlegen. Das ist in Vermittlerszenarios nützlich, in denen die SOAP-Adresse, die verfügbar gemacht werden soll, die eines öffentlichen SOAP-Vermittlers ist, während die Adresse, an der der Endpunkt lauscht, eine private Netzwerkadresse ist.  
  
 Sie können eine benutzerdefinierte Abhöradresse angeben, indem Sie entweder Code oder eine Konfiguration verwenden:  
  
- Im Code geben Sie eine benutzerdefinierte Abhöradresse durch Hinzufügen einer <xref:System.ServiceModel.Description.ClientViaBehavior>-Klasse zur Verhaltensauflistung des Endpunkts an.  
  
- Geben Sie unter Konfiguration eine benutzerdefinierte Abhör Adresse mit dem `ListenUri`-Attribut des Dienst [\<Endpunkt >](../../configure-apps/file-schema/wcf/endpoint-element.md) Elements an.  
  
### <a name="custom-soap-address-filter"></a>Benutzerdefinierter SOAP-Adressenfilter  
 Der <xref:System.ServiceModel.EndpointAddress.Uri%2A> wird in Verbindung mit einer beliebigen <xref:System.ServiceModel.EndpointAddress.Headers%2A>-Eigenschaft zur Definition des SOAP-Adressfilters eines Endpunkts verwendet (<xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A>). Standardmäßig prüft dieser Filter, ob eine eingehende Nachricht über einen `To`-Nachrichtenheader verfügt, der mit dem URI des Endpunkts übereinstimmt, und ob alle erforderlichen Endpunktheader in der Nachricht vorhanden sind.  
  
 In einigen Szenarien empfängt ein Endpunkt alle Nachrichten, die mit dem zugrunde liegenden Transport ankommen, und nicht nur die mit dem entsprechenden `To`-Header. Um dies zu aktivieren, kann der Benutzer die <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter>-Klasse verwenden.  
  
## <a name="see-also"></a>Siehe auch

- [Angeben einer Endpunktadresse](../../../../docs/framework/wcf/specifying-an-endpoint-address.md)
- [Dienstidentität und Authentifizierung](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
