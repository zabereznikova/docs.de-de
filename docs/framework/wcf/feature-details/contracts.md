---
title: "Vertr&#228;ge | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Verträge [WCF]"
  - "WCF [WCF], Verträge"
  - "Windows Communication Foundation [WCF], Verträge"
ms.assetid: c8364183-4ac1-480b-804a-c5e6c59a5d7d
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Vertr&#228;ge
In diesem Abschnitt wird dargestellt, wie [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Verträge definiert und implementiert werden.  Ein Dienstvertrag gibt an, was ein Endpunkt an die Außenwelt kommuniziert.  Konkreter gesagt ist er ein Anweisung zu mehreren bestimmten Nachrichten, die in grundlegende Nachrichtenaustauschmuster aufgeteilt sind, wie Anforderung\/Antwort, unidirektional und Duplex.  Wenn ein Dienstvertrag ein logisch zusammengehöriger Satz von Vorgängen des Nachrichtenaustauschs ist, dann ist ein Dienstvorgang ein einzelner Nachrichtenaustausch.  Beispielsweise muss ein `Hello`\-Vorgang natürlich eine Nachricht annehmen \(damit der Aufrufer den Gruß ankündigen kann\) und kann dann eine Nachricht zurückgeben \(je nach Verfügung des Vorgangs\).  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu Verträgen und anderen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Kernbegriffen finden Sie unter [Wesentliche Windows Communication Foundation\-Begriffe](../../../../docs/framework/wcf/fundamental-concepts.md).  In diesem Thema werden in erster Linie Kenntnisse über Dienstverträge vermittelt.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zum Erstellen von Clients, die zum Herstellen der Verbindung mit Diensten Dienstverträge verwenden, finden Sie unter [Übersicht über den WCF\-Client](../../../../docs/framework/wcf/wcf-client-overview.md).  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu Clientkanälen, Clientarchitektur und anderen Fragen zu Clients finden Sie unter [Clients](../../../../docs/framework/wcf/feature-details/clients.md).  
  
## Übersicht  
 Dieses Thema bietet eine allgemeine Orientierung über das Entwerfen und Implementieren von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Diensten.  Untergeordneten Themen bieten ausführlichere Informationen zu den Besonderheiten des Entwerfens und Implementierens.  Vor dem Entwerfen und Implementieren der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Anwendung werden die folgenden Voraussetzungen empfohlen:  
  
-   Kenntnisse darüber, was ein Dienstvertrag ist, wie er funktioniert und erstellt wird.  
  
-   Kenntnisse darüber, dass Verträge Mindestanforderungen angeben, die Laufzeitkonfiguration oder die Hostumgebung möglicherweise nicht unterstützt.  
  
## Dienstverträge  
 Ein Dienstvertrag ist eine Anweisung, die Informationen zu folgenden Parametern enthält:  
  
-   Die Gruppierung von Vorgängen in einem Dienst.  
  
-   Die Signatur der Vorgänge in Bezug auf ausgetauschte Nachrichten.  
  
-   Die Datentypen dieser Nachrichten.  
  
-   Der Speicherort der Vorgänge.  
  
-   Die spezifischen Protokolle und Serialisierungsformate, die verwendet werden, um die erfolgreiche Kommunikation mit dem Dienst zu unterstützen.  
  
 Beispielsweise kann ein Vertrag für eine Bestellung einen `CreateOrder`\-Vorgang aufweisen, der eine Eingabe von Bestellinformationstypen annimmt und Erfolgs\- oder Fehlerinformationen einschließlich einer Bestellnummer zurückgibt.  Er kann auch einen `GetOrderStatus`\-Vorgang aufweisen, der eine Bestellnummer annimmt und Bestellstatusinformationen zurückgibt.  Ein Dienstvertrag dieser Art würde Folgendes angeben:  
  
-   Dass der Vertrag für die Bestellung aus `CreateOrder`\- und `GetOrderStatus`\-Vorgänge besteht.  
  
-   Dass die Vorgänge Eingabemeldungen und Ausgabemeldungen angegeben haben.  
  
-   Die Daten, die diese Meldungen enthalten können.  
  
-   Nach Kategorien geordnete Anweisungen zur für die erfolgreiche Verarbeitung der Meldungen erforderlichen Kommunikationsinfrastruktur.  Beispielsweise schließen diese Details ein, ob und welche Formen von Sicherheit erforderlich sind, um eine erfolgreiche Kommunikation herzustellen.  
  
 Um diese Informationen an Anwendungen auf anderen Plattformen \(einschließlich Nicht\-Microsoft\-Plattformen\) zu vermitteln, werden XML\-Dienstverträge öffentlich in XML\-Standardformaten ausgedrückt, unter anderem in [Web Services Description Language \(WSDL\)](http://go.microsoft.com/fwlink/?LinkId=87004) und als [XML\-Schema \(XSD\)](http://go.microsoft.com/fwlink/?LinkId=87005).  Entwickler für viele Plattformen können mithilfe dieser öffentlichen Vertragsinformationen Anwendungen erstellen, die mit dem Dienst kommunizieren können, da sie die Sprache der Spezifikation verstehen und diese Sprachen für das Ermöglichen der Interoperation konzipiert sind, indem sie die öffentlichen Formulare, Formate und Protokolle beschreiben, die der Dienst unterstützt.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] darüber, wie [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] diese Informationen verarbeitet, finden Sie unter [Metadaten](../../../../docs/framework/wcf/feature-details/metadata.md).  
  
 Verträge können allerdings auf verschiedene Weise ausgedrückt werden; WSDL und XSD sind zwar ausgezeichnete Sprachen zum Beschreiben von Diensten beim Zugriff, jedoch schwierige Sprachen bei der direkten Verwendung. Sie sind lediglich Beschreibungen eines Dienstes und keine Dienstvertragsimplementierungen.  Daher verwenden [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Anwendungen verwaltete Attribute, Schnittstellen und Klassen zum Definieren der Struktur und zum Implementieren eines Dienstes.  
  
 Der resultierende, in verwalteten Typen definierte Vertrag kann als Metadaten \(WSDL und XSD\) konvertiert \(bzw. *exportiert*\) werden, wenn er von Clients oder anderen Dienstimplementierern benötigt wird, insbesondere auf anderen Plattformen.  Das Ergebnis ist ein einfaches Programmiermodell, das mit öffentlichen Metadaten für jede Clientanwendung beschrieben werden kann.  Die Details der zugrunde liegenden SOAP\-Nachrichten, wie die Informationen zu Transport und Sicherheit, können [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] überlassen werden, wo die erforderlichen Konvertierungen zum und vom Dienstvertragstypsystem zum XML\-Typsystem automatisch ausgeführt werden.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zum Entwerfen von Verträgen finden Sie unter [Entwerfen von Dienstverträgen](../../../../docs/framework/wcf/designing-service-contracts.md).  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zum Implementieren von Verträgen finden Sie unter [Implementieren von Dienstverträgen](../../../../docs/framework/wcf/implementing-service-contracts.md).  
  
 Außerdem bietet [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] die Möglichkeit, Dienstverträge vollständig auf Nachrichtenebene zu entwickeln.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zum Entwickeln von Dienstverträgen auf Nachrichtenebene finden Sie unter [Verwendung von Nachrichtenverträgen](../../../../docs/framework/wcf/feature-details/using-message-contracts.md).  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zum Entwickeln von Diensten in Nicht\-SOAP\-XML finden Sie unter [Interoperabilität mit POX\-Anwendungen](../../../../docs/framework/wcf/feature-details/interoperability-with-pox-applications.md).  
  
### Grundlagen der Anforderungshierarchie  
 Ein Dienstvertrag gruppiert die Vorgänge, gibt das Nachrichtenaustauschmuster, die Nachrichtentypen und Datentypen an, die diese Nachrichten enthalten, und zeigt Kategorien von Laufzeitverhalten an, die eine Implementierung aufweisen muss, um den Vertrag zu unterstützen \(z. B. dass Nachrichten verschlüsselt und signiert sein müssen\).  Der Dienstvertrag selbst gibt nicht genau an, wie diese Anforderungen erfüllt werden, sondern lediglich, dass sie erfüllt werden müssen.  Welcher Verschlüsselungstyp verwendet wird oder wie eine Nachricht signiert wird, hängt von der Implementierung und Konfiguration eines kompatiblen Dienstes ab.  
  
 Beachten Sie, dass der Vertrag bestimmte Anforderungen an die Dienstvertragsimplementierung und die Laufzeitkonfiguration stellt, um ein Verhalten hinzuzufügen.  Die Anforderungen, um einen Dienst für die Verwendung verfügbar zu machen, bauen auf den vorherigen Anforderungen auf.  Wenn ein Vertrag Anforderungen an die Implementierung stellt, kann eine Implementierung noch weitere Anforderungen an die Konfiguration und die Bindungen stellen, die die Ausführung des Dienstes ermöglichen.  Außerdem muss die Hostanwendung auch alle Anforderungen unterstützen, die die Dienstkonfiguration und die Bindungen hinzufügen.  
  
 Beachten Sie unbedingt diesen zusätzlichen Anforderungsvorgang beim Entwerfen, Implementieren, Konfigurieren und Hosten der [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Dienstanwendung.  Beispielsweise kann der Vertrag angeben, dass er eine Sitzung unterstützen muss.  In diesem Fall müssen Sie die Bindung so konfigurieren, dass sie diese Vertragsanforderung unterstützt, oder die Dienstimplementierung funktioniert nicht.  Wenn der Dienst integrierte Windows\-Authentifizierung erfordert und in Internetinformationsdienste \(IIS\) gehostet wird, muss für die Webanwendung, in der sich der Dienst befindet, die integrierte Windows\-Authentifizierung aktiviert und der anonyme Support deaktiviert sein.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu den Funktionen und den Auswirkungen der verschiedenen Diensthost\-Anwendungstypen finden Sie unter [Hosting](../../../../docs/framework/wcf/feature-details/hosting.md).  
  
## Siehe auch  
 [Endpunkte: Adressen, Bindungen und Verträge](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)   
 [Entwerfen von Dienstverträgen](../../../../docs/framework/wcf/designing-service-contracts.md)   
 [Implementieren von Dienstverträgen](../../../../docs/framework/wcf/implementing-service-contracts.md)