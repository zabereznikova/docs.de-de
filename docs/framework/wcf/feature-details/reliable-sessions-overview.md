---
title: "&#220;bersicht &#252;ber zuverl&#228;ssige Sitzungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: a7fc4146-ee2c-444c-82d4-ef6faffccc2d
caps.latest.revision: 30
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 30
---
# &#220;bersicht &#252;ber zuverl&#228;ssige Sitzungen
Zuverlässiges [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] SOAP\-Messaging stellt eine zuverlässige End\-to\-End\-Übertragung zwischen SOAP\-Endpunkten bereit.Dies erfolgt in nicht zuverlässigen Netzwerken, indem Transportfehler und SOAP\-Fehler auf Nachrichtenebene behoben werden.Insbesondere wird sitzungsbasierte, einzelne und \(optional\) geordnete Zustellung für Nachrichten bereitgestellt, die über SOAP\- oder Transportvermittler übertragen werden.Die sitzungsbasierte Zustellung gruppiert Nachrichten in einer Sitzung und ordnet optional die Nachrichten.  
  
 Die folgenden Erläuterungen beschreiben, was eine zuverlässige Sitzung ist, wie und wann sie verwendet wird, und wie sie geschützt wird.  
  
## Zuverlässige WCF\-Sitzungen  
 In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sind zuverlässige Sitzungen eine Implementierung von zuverlässigem SOAP\-Messaging, wie im WS\-ReliableMessaging\-Protokoll definiert.  
  
 Zuverlässiges [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] SOAP\-Messaging bietet eine zuverlässige End\-to\-End\-Übertragung zwischen zwei Endpunkten, unabhängig von der Anzahl oder dem Typ der Vermittler, durch die die Messagingendpunkte getrennt werden.Dies umfasst alle Transportvermittler, die kein SOAP \(z. B. HTTP\-Proxys\) verwenden, oder Vermittler, die SOAP \(z. B. SOAP\-basierte Router oder Brücken\) verwenden, und die für die Übertragung von Nachrichten zwischen den Endpunkten erforderlich sind.Ein zuverlässiger Sitzungskanal unterstützt "interaktive" Kommunikation, sodass die über einen solchen Kanal verbundenen Dienste gleichzeitig ausgeführt werden können und mit geringer Latenz, also in relativ geringen Zeitintervallen, Nachrichten austauschen und verarbeiten können.Diese Kopplung bedeutet, dass diese Komponenten zusammen weiterarbeiten oder zusammen fehlschlagen; sie sind also nicht voneinander isoliert.  
  
 Eine zuverlässige Sitzung maskiert zwei Arten von Fehlern:  
  
-   SOAP\-Fehler auf Nachrichtenebene, zu denen verloren gegangene oder doppelte Nachrichten gehören sowie Nachrichten, die in einer anderen Reihenfolge eintreffen als der, in der sie gesendet wurden.  
  
-   Transportfehler.  
  
 Eine zuverlässige Sitzung implementiert das WS\-ReliableMessaging\-Protokoll und ein Übertragungsfenster im Arbeitsspeicher, um SOAP\-Fehler auf Nachrichtenebene zu maskieren und Verbindungen im Falle von Transportfehlern neu herzustellen.  
  
 Eine zuverlässige Sitzung stellt für SOAP\-Nachrichten das bereit, was TCP für IP\-Pakete bereitstellt.Eine TCP\-Socketverbindung stellt eine einzelne, geordnete Übertragung von IP\-Paketen zwischen Knoten bereit.Der zuverlässige Kanal stellt denselben Typ zuverlässiger Übertragung bereit, die sich aber von der TCP\-Socket\-Zuverlässigkeit in folgenden Punkten unterscheidet:  
  
-   Die Zuverlässigkeit gilt für die SOAP\-Nachrichten\-Ebene, nicht für ein Byte\-Paket zufälliger Größe.  
  
-   Die Zuverlässigkeit ist transportneutral und gilt nicht nur für die Übertragung über TCP.  
  
-   Die Zuverlässigkeit ist nicht an eine bestimmte Transportsitzung gebunden \(beispielsweise an die Sitzung, die eine TCP\-Verbindung bereitstellt\) und kann während der Lebensdauer einer zuverlässigen Sitzung mehrere Transportsitzungen gleichzeitig oder nacheinander verwenden.  
  
-   Die zuverlässige Sitzung besteht zwischen den sendenden und den empfangenden SOAP\-Endpunkten, unabhängig von der Anzahl der Transportverbindungen, die für die Konnektivität zwischen ihnen erforderlich ist.Kurz gesagt, TCP\-Zuverlässigkeit endet, wo die Transportverbindung endet, wohingegen eine zuverlässige Sitzung End\-to\-End\-Zuverlässigkeit bereitstellt.  
  
## Zuverlässige Sitzungen und Bindungen  
 Wie schon erwähnt, ist eine zuverlässige Sitzung transportneutral und kann daher über viele Transporte implementiert werden.Eine zuverlässige Sitzung kann auch über viele Nachrichtenaustauschmuster eingerichtet werden, z. B. über Anforderung\-Antwort\- oder Duplex\-Muster.Die zuverlässige Sitzung wird daher in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] als Eigenschaft eines Satzes von Bindungen verfügbar gemacht.  
  
 Sie können eine zuverlässige Sitzung auf Endpunkten einsetzen, die folgende Bindungen verwenden:  
  
-   HTTP\-basierte Transport\-Standardbindungen:  
  
    -   `WsHttpBinding` und verfügbar gemachte Anforderung\-Antwort\- oder unidirektionale Verträge.  
  
    -   Kann verwendet werden, wenn zuverlässige Sitzung über einen Anforderung\-Antwort\- oder einen einfachen unidirektionalen Dienstvertrag verwendet wird.  
  
    -   `WsDualHttpBinding` und verfügbar gemachte Duplex\-, Anforderung\-Antwort\- oder unidirektionale Verträge.  
  
    -   `WsFederationHttpBinding` und verfügbar gemachte Anforderung\-Antwort\- oder unidirektionale Verträge.  
  
-   TCP\-basierte Transport\-Standardbindungen:  
  
    -   `NetTcpBinding` und verfügbar gemachte Duplex\-, Anforderung\-Antwort\- oder unidirektionale Verträge.  
  
 Sie können eine zuverlässige Sitzung für jede andere Bindung verwenden, indem Sie eine benutzerdefinierte Bindung, etwa HTTPS \(weitere Informationen zu möglichen Problemen finden Sie im Abschnitt "Zuverlässige Sitzungen und Sicherheit" weiter unten in diesem Thema\), oder eine benannte Pipebindung erstellen.  
  
 Eine zuverlässige Sitzung kann auf verschiedene zugrunde liegende Kanaltypen gestapelt werden, und die Form des sich ergebenden zuverlässigen Sitzungskanals variiert.Sowohl beim Client als auch beim Server hängt der Typ des unterstützten zuverlässigen Sitzungskanals vom Typ des zugrunde liegenden Kanals ab, der verwendet wird.In der folgenden Tabelle werden die Typen von Sitzungskanälen aufgeführt, die vom Client auf der Basis des zugrunde liegenden Kanaltyps unterstützt werden.  
  
|Unterstützte zuverlässige Sitzungskanaltypen \(unterstützte Werte von `TChannel` für einen gegebenen, zugrunde liegenden Kanaltyp\)|`IRequestChannel`|`IRequestSessionChanne`l|`IDuplexChannel`|`IDuplexSessionChannel`|  
|-----------------------------------------------------------------------------------------------------------------------------------------|-----------------------|------------------------------|----------------------|-----------------------------|  
|`IOutputSessionChannel`|Ja|Ja|Ja|Ja|  
|`IRequestSessionChannel`|Yes|Ja|Nein|Nein|  
|`IDuplexSessionChannel`|Nein|Nein|Ja|Ja|  
  
 Die unterstützen Kanaltypen sind die für den generischen `TChannel`\-Parameterwert verfügbaren Werte. Dieser Parameter wird in die <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.BuildChannelFactory%60%601%28System.ServiceModel.Channels.BindingContext%29>\-Methode übergeben.  
  
 In der folgenden Tabelle werden die Typen von Sitzungskanälen aufgeführt, die vom Server auf der Basis des zugrunde liegenden Kanaltyps unterstützt werden.  
  
|Unterstützte zuverlässige Sitzungskanaltypen \(unterstützte Werte von `TChannel` für einen gegebenen, zugrunde liegenden Kanaltyp\)|`IReplyChannel`|`IReplySessionChannel`|`IDuplexChannel`|`IDuplexSessionChannel`|  
|-----------------------------------------------------------------------------------------------------------------------------------------|---------------------|----------------------------|----------------------|-----------------------------|  
|`IInputSessionChannel`|Ja|Ja|Ja|Ja|  
|`IReplySessionChannel`|Yes|Ja|Nein|Nein|  
|`IDuplexSessionChannel`|Nein|Nein|Ja|Ja|  
  
 Die unterstützen Kanaltypen sind die für den generischen `TChannel`\-Parameterwert verfügbaren Werte. Dieser Parameter wird in die <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.BuildChannelListener%60%601%28System.ServiceModel.Channels.BindingContext%29>\-Methode übergeben.  
  
## Zuverlässige Sitzungen und Sicherheit  
 Der Schutz einer zuverlässigen Sitzung ist wichtig, um sicherstellen zu können, dass die Kommunikationspartner \(Dienst und Client\) authentifiziert und die in der Sitzung ausgetauschten Nachrichten nicht verfälscht werden.Weiterhin ist es wichtig, die Integrität jeder einzelnen zuverlässigen Sitzung sicherzustellen.Eine zuverlässige Sitzung wird geschützt, indem sie an einen sicheren Kontext gebunden wird, der vom Sicherheitskanal der Sitzung dargestellt und verwaltet wird.Der Sicherheitskanal stellt eine Sicherheitssitzung bereit.Die Sicherheitstoken, die während der Einrichtung der Sitzung ausgetauscht werden, werden anschließend verwendet, um die Nachrichten in der zuverlässigen Sitzung zu schützen.  
  
 Findet die zuverlässige Sitzung über TCP\-S statt, ist die TCP\-Sitzung an die zuverlässige Sitzung gebunden, und daher gewährleistet die Transportsicherheit, dass die Sicherheit ebenfalls an die zuverlässige Sitzung gebunden ist.In diesem Fall ist die erneute Einrichtung einer Verbindung abgeschaltet.  
  
 Die einzige Ausnahme besteht bei der Verwendung von HTTPS.Die Secure Sockets Layer \(SSL\)\-Sitzung ist nicht an die zuverlässige Sitzung gebunden.Dies stellt ein Risiko dar, weil Sitzungen, die einen Sicherheitskontext gemeinsam verwenden \(die SSL\-Sitzung\), nicht voreinander geschützt sind. Dies kann, abhängig von der Anwendung, ein echtes Risiko darstellen oder auch nicht.  
  
## Verwenden von zuverlässigen Sitzungen  
 Um zuverlässige [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Sitzungen zu verwenden, erstellen Sie einen Endpunkt mit einer Bindung, die eine zuverlässige Sitzung unterstützt.Verwenden Sie eine der von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bereitgestellten Bindungen mit aktivierter zuverlässiger Sitzung, oder erstellen Sie eine eigene benutzerdefinierte Bindung, die dies tut.Die systemdefinierten Bindungen, die standardmäßig eine zuverlässige Sitzung unterstützen und aktivieren, sind:  
  
-   <xref:System.ServiceModel.WSDualHttpBinding>  
  
 Die systemdefinierten Bindungen, die optional eine zuverlässige Sitzung unterstützen, sie jedoch nicht standardmäßig aktivieren, sind:  
  
-   <xref:System.ServiceModel.WSHttpBinding>  
  
-   <xref:System.ServiceModel.WSFederationHttpBinding>  
  
-   <xref:System.ServiceModel.NetTcpBinding>  
  
 Ein Beispiel dafür, wie eine benutzerdefinierte Bindung erstellt wird, finden Sie unter [Vorgehensweise: Erstellen einer benutzerdefinierten zuverlässigen Sitzungsbindung mit HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md).  
  
 Eine Erläuterung der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Bindungen, die zuverlässige Sitzungen unterstützen, finden Sie unter [Vom System bereitgestellte Bindungen](../../../../docs/framework/wcf/system-provided-bindings.md).  
  
## Wann zuverlässige Sitzungen verwendet werden  
 Es ist wichtig zu wissen, wann Sie in Ihrer Anwendung zuverlässige Sitzungen verwenden sollten.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterstützt zuverlässige Sitzungen zwischen Endpunkten, die gleichzeitig aktiv und am Leben sind.Wenn es für Ihre Anwendung erforderlich ist, dass einer der Endpunkte für einen bestimmten Zeitraum nicht verfügbar ist, können Sie die Zuverlässigkeit mithilfe von Warteschlangen erreichen.  
  
 Erfordert das Szenario, dass zwei Endpunkte über TCP miteinander verbunden sind, dann kann TCP ausreichen, um den zuverlässigen Austausch der Nachrichten bereitzustellen, auch wenn es nicht notwendig ist, eine zuverlässige Sitzung zu verwenden. TCP stellt sicher, dass die Pakete in der richtigen Reihenfolge und nur einmal eintreffen.  
  
 Weist Ihr Szenario eines der folgenden Merkmale auf, müssen Sie ernsthaft erwägen, eine zuverlässige Sitzung zu verwenden:  
  
-   SOAP\-Vermittler, z. B. SOAP\-Router  
  
-   Proxyvermittler oder Transportbrücken  
  
-   Periodische Konnektivität  
  
-   Sitzungen über HTTP  
  
## Siehe auch  
 [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)   
 [Zuverlässige WS\-Sitzung](../../../../docs/framework/wcf/samples/ws-reliable-session.md)