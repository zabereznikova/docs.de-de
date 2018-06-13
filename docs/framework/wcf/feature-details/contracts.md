---
title: Verträge
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], contracts
- contracts [WCF]
- Windows Communication Foundation [WCF], contracts
ms.assetid: c8364183-4ac1-480b-804a-c5e6c59a5d7d
ms.openlocfilehash: 8522ae89ca69ec594f62e272f8479b607609f064
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33493259"
---
# <a name="contracts"></a>Verträge
In diesem Abschnitt wird gezeigt, wie definieren und Implementieren von Windows Communication Foundation (WCF)-Verträge. Ein Dienstvertrag gibt an, was ein Endpunkt an die Außenwelt kommuniziert. Konkreter gesagt ist er ein Anweisung zu mehreren bestimmten Nachrichten, die in grundlegende Nachrichtenaustauschmuster aufgeteilt sind, wie Anforderung/Antwort, unidirektional und Duplex. Wenn ein Dienstvertrag ein logisch zusammengehöriger Satz von Vorgängen des Nachrichtenaustauschs ist, dann ist ein Dienstvorgang ein einzelner Nachrichtenaustausch. Beispielsweise muss ein `Hello`-Vorgang natürlich eine Nachricht annehmen (damit der Aufrufer den Gruß ankündigen kann) und kann dann eine Nachricht zurückgeben (je nach Verfügung des Vorgangs).  
  
 Weitere Informationen zu Verträgen und andere Kernkonzepte von WCF, finden Sie unter [grundlegenden Windows Communication Foundation-Begriffe](../../../../docs/framework/wcf/fundamental-concepts.md). In diesem Thema werden in erster Linie Kenntnisse über Dienstverträge vermittelt. Weitere Informationen zur Erstellung von Clients, die Dienstverträge, die für die Verbindung mit Diensten verwenden, finden Sie unter [Überblick über WCF-Client](../../../../docs/framework/wcf/wcf-client-overview.md). Weitere Informationen zu Clientkanäle, die Clientarchitektur und andere clientprobleme finden Sie unter [Clients](../../../../docs/framework/wcf/feature-details/clients.md).  
  
## <a name="overview"></a>Übersicht  
 Dieses Thema bietet eine allgemeine Orientierung über das Entwerfen und Implementieren von WCF-Dienste. Untergeordneten Themen bieten ausführlichere Informationen zu den Besonderheiten des Entwerfens und Implementierens. Vor dem Entwerfen und implementieren die WCF-Anwendung, es wird empfohlen, die Sie:  
  
-   Kenntnisse darüber, was ein Dienstvertrag ist, wie er funktioniert und erstellt wird.  
  
-   Kenntnisse darüber, dass Verträge Mindestanforderungen angeben, die Laufzeitkonfiguration oder die Hostumgebung möglicherweise nicht unterstützt.  
  
## <a name="service-contracts"></a>Dienstverträge  
 Ein Dienstvertrag ist eine Anweisung, die Informationen zu folgenden Parametern enthält:  
  
-   Die Gruppierung von Vorgängen in einem Dienst.  
  
-   Die Signatur der Vorgänge in Bezug auf ausgetauschte Nachrichten.  
  
-   Die Datentypen dieser Nachrichten.  
  
-   Der Speicherort der Vorgänge.  
  
-   Die spezifischen Protokolle und Serialisierungsformate, die verwendet werden, um die erfolgreiche Kommunikation mit dem Dienst zu unterstützen.  
  
 Beispielsweise kann ein Vertrag für eine Bestellung einen `CreateOrder`-Vorgang aufweisen, der eine Eingabe von Bestellinformationstypen annimmt und Erfolgs- oder Fehlerinformationen einschließlich einer Bestellnummer zurückgibt. Er kann auch einen `GetOrderStatus`-Vorgang aufweisen, der eine Bestellnummer annimmt und Bestellstatusinformationen zurückgibt. Ein Dienstvertrag dieser Art würde Folgendes angeben:  
  
-   Dass der Vertrag für die Bestellung aus `CreateOrder`- und `GetOrderStatus`-Vorgänge besteht.  
  
-   Dass die Vorgänge Eingabemeldungen und Ausgabemeldungen angegeben haben.  
  
-   Die Daten, die diese Meldungen enthalten können.  
  
-   Nach Kategorien geordnete Anweisungen zur für die erfolgreiche Verarbeitung der Meldungen erforderlichen Kommunikationsinfrastruktur. Beispielsweise schließen diese Details ein, ob und welche Formen von Sicherheit erforderlich sind, um eine erfolgreiche Kommunikation herzustellen.  
  
 Um diese Art von Informationen zu Anwendungen auf anderen Plattformen (einschließlich nicht-Microsoft-Plattformen) zu vermitteln, XML-Dienstverträge öffentlich in ausgedrückt werden standard-XML-Formaten, z. B. [Web Services Description Language (WSDL)](http://go.microsoft.com/fwlink/?LinkId=87004) und [XML-Schema (XSD)](http://go.microsoft.com/fwlink/?LinkId=87005), o. ä. Entwickler für viele Plattformen können mithilfe dieser öffentlichen Vertragsinformationen Anwendungen erstellen, die mit dem Dienst kommunizieren können, da sie die Sprache der Spezifikation verstehen und diese Sprachen für das Ermöglichen der Interoperation konzipiert sind, indem sie die öffentlichen Formulare, Formate und Protokolle beschreiben, die der Dienst unterstützt. Weitere Informationen zur Behandlung dieser Art von Informationen von WCF finden Sie unter [Metadaten](../../../../docs/framework/wcf/feature-details/metadata.md).  
  
 Verträge können allerdings auf verschiedene Weise ausgedrückt werden; WSDL und XSD sind zwar ausgezeichnete Sprachen zum Beschreiben von Diensten beim Zugriff, jedoch schwierige Sprachen bei der direkten Verwendung. Sie sind lediglich Beschreibungen eines Dienstes und keine Dienstvertragsimplementierungen. WCF-Anwendungen verwenden daher verwaltete Attribute, Schnittstellen und Klassen zum Definieren der Struktur und zum Implementieren eines Diensts.  
  
 Der resultierende in verwalteten Typen definierte Vertrag konvertiert werden kann (so genannte *exportiert*) als Metadaten – WSDL und XSD – nach Bedarf durch Clients oder andere Dienstimplementierer, insbesondere auf anderen Plattformen. Das Ergebnis ist ein einfaches Programmiermodell, das mit öffentlichen Metadaten für jede Clientanwendung beschrieben werden kann. Die Details der zugrunde liegenden SOAP-Nachrichten, wie der Transport und sicherheitsbezogene Informationen können WCF, bleiben, die die erforderlichen Konvertierungen zum und aus dem Dienst Vertrag-Typsystem, das XML-Typsystem automatisch ausführt.  
  
 Weitere Informationen zum Entwerfen von Verträgen finden Sie unter [Entwerfen von Dienstverträgen](../../../../docs/framework/wcf/designing-service-contracts.md). Weitere Informationen zum Implementieren von Verträgen finden Sie unter [implementieren Dienstverträge](../../../../docs/framework/wcf/implementing-service-contracts.md).  
  
 WCF bietet darüber hinaus auch die Möglichkeit, Dienstverträge vollständig auf Nachrichtenebene zu entwickeln. Weitere Informationen zum Entwickeln von Dienstverträgen auf Nachrichtenebene finden Sie unter [Verwendung von Nachrichtenverträgen](../../../../docs/framework/wcf/feature-details/using-message-contracts.md). Weitere Informationen zum Entwickeln von Diensten in SOAP-XML finden Sie unter [Interoperabilität mit POX-Anwendungen](../../../../docs/framework/wcf/feature-details/interoperability-with-pox-applications.md).  
  
### <a name="understanding-the-hierarchy-of-requirements"></a>Grundlagen der Anforderungshierarchie  
 Ein Dienstvertrag gruppiert die Vorgänge, gibt das Nachrichtenaustauschmuster, die Nachrichtentypen und Datentypen an, die diese Nachrichten enthalten, und zeigt Kategorien von Laufzeitverhalten an, die eine Implementierung aufweisen muss, um den Vertrag zu unterstützen (z. B. dass Nachrichten verschlüsselt und signiert sein müssen). Der Dienstvertrag selbst gibt nicht genau an, wie diese Anforderungen erfüllt werden, sondern lediglich, dass sie erfüllt werden müssen. Welcher Verschlüsselungstyp verwendet wird oder wie eine Nachricht signiert wird, hängt von der Implementierung und Konfiguration eines kompatiblen Dienstes ab.  
  
 Beachten Sie, dass der Vertrag bestimmte Anforderungen an die Dienstvertragsimplementierung und die Laufzeitkonfiguration stellt, um ein Verhalten hinzuzufügen. Die Anforderungen, um einen Dienst für die Verwendung verfügbar zu machen, bauen auf den vorherigen Anforderungen auf. Wenn ein Vertrag Anforderungen an die Implementierung stellt, kann eine Implementierung noch weitere Anforderungen an die Konfiguration und die Bindungen stellen, die die Ausführung des Dienstes ermöglichen. Außerdem muss die Hostanwendung auch alle Anforderungen unterstützen, die die Dienstkonfiguration und die Bindungen hinzufügen.  
  
 Dieser Anforderungsvorgang ist wichtig zu bedenken, beim Entwerfen, implementieren, konfigurieren und Hosten der Windows Communication Foundation (WCF) dienstanwendung. Beispielsweise kann der Vertrag angeben, dass er eine Sitzung unterstützen muss. In diesem Fall müssen Sie die Bindung so konfigurieren, dass sie diese Vertragsanforderung unterstützt, oder die Dienstimplementierung funktioniert nicht. Wenn der Dienst integrierte Windows-Authentifizierung erfordert und in Internetinformationsdienste (IIS) gehostet wird, muss für die Webanwendung, in der sich der Dienst befindet, die integrierte Windows-Authentifizierung aktiviert und der anonyme Support deaktiviert sein. Weitere Informationen zu den Funktionen und die Auswirkungen von den anderen Dienst Anwendung Hosttypen finden Sie unter [Hosting](../../../../docs/framework/wcf/feature-details/hosting.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Endpunkte: Adressen, Bindungen und Verträge](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)  
 [Entwerfen von Dienstverträgen](../../../../docs/framework/wcf/designing-service-contracts.md)  
 [Implementieren von Dienstverträgen](../../../../docs/framework/wcf/implementing-service-contracts.md)
