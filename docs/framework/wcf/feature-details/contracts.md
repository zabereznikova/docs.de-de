---
title: Verträge
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], contracts
- contracts [WCF]
- Windows Communication Foundation [WCF], contracts
ms.assetid: c8364183-4ac1-480b-804a-c5e6c59a5d7d
ms.openlocfilehash: 1cd7e54d50e7116c71c040df1965674a4fdaff13
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595595"
---
# <a name="contracts"></a>Verträge
In diesem Abschnitt wird gezeigt, wie Windows Communication Foundation (WCF)-Verträge definiert und implementiert werden. Ein Dienstvertrag gibt an, was ein Endpunkt an die Außenwelt kommuniziert. Konkreter gesagt ist er ein Anweisung zu mehreren bestimmten Nachrichten, die in grundlegende Nachrichtenaustauschmuster aufgeteilt sind, wie Anforderung/Antwort, unidirektional und Duplex. Wenn ein Dienstvertrag ein logisch zusammengehöriger Satz von Vorgängen des Nachrichtenaustauschs ist, dann ist ein Dienstvorgang ein einzelner Nachrichtenaustausch. Beispielsweise muss ein `Hello`-Vorgang natürlich eine Nachricht annehmen (damit der Aufrufer den Gruß ankündigen kann) und kann dann eine Nachricht zurückgeben (je nach Verfügung des Vorgangs).  
  
 Weitere Informationen zu Verträgen und anderen Kernkonzepten von WCF finden Sie unter [grundlegende Windows Communication Foundation Konzepte](../fundamental-concepts.md). In diesem Thema werden in erster Linie Kenntnisse über Dienstverträge vermittelt. Weitere Informationen zum Erstellen von Clients, die Dienstverträge zum Herstellen einer Verbindung mit Diensten verwenden, finden Sie unter Übersicht über den [WCF-Client](../wcf-client-overview.md). Weitere Informationen zu Client Kanälen, der Client Architektur und anderen Client Problemen finden Sie unter [Clients](clients.md).  
  
## <a name="overview"></a>Übersicht  
 Dieses Thema bietet eine allgemeine Konzept Orientierung zum Entwerfen und Implementieren von WCF-Diensten. Untergeordneten Themen bieten ausführlichere Informationen zu den Besonderheiten des Entwerfens und Implementierens. Vor dem Entwerfen und Implementieren der WCF-Anwendung empfiehlt es sich, Folgendes zu tun:  
  
- Kenntnisse darüber, was ein Dienstvertrag ist, wie er funktioniert und erstellt wird.  
  
- Kenntnisse darüber, dass Verträge Mindestanforderungen angeben, die Laufzeitkonfiguration oder die Hostumgebung möglicherweise nicht unterstützt.  
  
## <a name="service-contracts"></a>Dienstverträge  
 Ein Dienstvertrag ist eine Anweisung, die Informationen zu folgenden Parametern enthält:  
  
- Die Gruppierung von Vorgängen in einem Dienst.  
  
- Die Signatur der Vorgänge in Bezug auf ausgetauschte Nachrichten.  
  
- Die Datentypen dieser Nachrichten.  
  
- Der Speicherort der Vorgänge.  
  
- Die spezifischen Protokolle und Serialisierungsformate, die verwendet werden, um die erfolgreiche Kommunikation mit dem Dienst zu unterstützen.  
  
 Beispielsweise kann ein Vertrag für eine Bestellung einen `CreateOrder`-Vorgang aufweisen, der eine Eingabe von Bestellinformationstypen annimmt und Erfolgs- oder Fehlerinformationen einschließlich einer Bestellnummer zurückgibt. Er kann auch einen `GetOrderStatus`-Vorgang aufweisen, der eine Bestellnummer annimmt und Bestellstatusinformationen zurückgibt. Ein Dienstvertrag dieser Art würde Folgendes angeben:  
  
- Dass der Vertrag für die Bestellung aus `CreateOrder`- und `GetOrderStatus`-Vorgänge besteht.  
  
- Dass die Vorgänge Eingabemeldungen und Ausgabemeldungen angegeben haben.  
  
- Die Daten, die diese Meldungen enthalten können.  
  
- Nach Kategorien geordnete Anweisungen zur für die erfolgreiche Verarbeitung der Meldungen erforderlichen Kommunikationsinfrastruktur. Beispielsweise schließen diese Details ein, ob und welche Formen von Sicherheit erforderlich sind, um eine erfolgreiche Kommunikation herzustellen.  
  
 Um diese Art von Informationen an Anwendungen auf anderen Plattformen (einschließlich nicht-Microsoft-Plattformen) zu vermitteln, werden XML-Dienstverträge in Standard-XML-Formaten, z. b. [Web Services Description Language (WSDL)](https://www.w3.org/TR/2001/NOTE-wsdl-20010315) und [XML-Schema (XSD)](https://www.w3.org/XML/Schema), öffentlich ausgedrückt. Entwickler für viele Plattformen können mithilfe dieser öffentlichen Vertragsinformationen Anwendungen erstellen, die mit dem Dienst kommunizieren können, da sie die Sprache der Spezifikation verstehen und diese Sprachen für das Ermöglichen der Interoperation konzipiert sind, indem sie die öffentlichen Formulare, Formate und Protokolle beschreiben, die der Dienst unterstützt. Weitere Informationen dazu, wie WCF diese Art von Informationen verarbeitet, finden Sie unter [Metadaten](metadata.md).  
  
 Verträge können allerdings auf verschiedene Weise ausgedrückt werden; WSDL und XSD sind zwar ausgezeichnete Sprachen zum Beschreiben von Diensten beim Zugriff, jedoch schwierige Sprachen bei der direkten Verwendung. Sie sind lediglich Beschreibungen eines Dienstes und keine Dienstvertragsimplementierungen. Daher verwenden WCF-Anwendungen verwaltete Attribute, Schnittstellen und Klassen, um die Struktur von und zu definieren, um einen Dienst zu implementieren.  
  
 Der sich ergebende Vertrag, der in verwalteten Typen definiert ist, *exported*kann als Metadaten – WSDL und XSD – konvertiert werden, wenn Sie von Clients oder anderen Dienstimplementierern benötigt werden, insbesondere auf anderen Plattformen. Das Ergebnis ist ein einfaches Programmiermodell, das mit öffentlichen Metadaten für jede Clientanwendung beschrieben werden kann. Die Details der zugrunde liegenden SOAP-Nachrichten, wie z. b. Transport-und sicherheitsbezogene Informationen, können für WCF belassen werden, das automatisch die erforderlichen Konvertierungen zum und vom Dienst Vertragstyp System in das XML-Typsystem ausführt.  
  
 Weitere Informationen zum Entwerfen von Verträgen finden Sie unter [Entwerfen von Dienstverträgen](../designing-service-contracts.md). Weitere Informationen zum Implementieren von Verträgen finden Sie unter [Implementieren von Dienstverträgen](../implementing-service-contracts.md).  
  
 Außerdem bietet WCF die Möglichkeit, Dienstverträge vollständig auf Nachrichten Ebene zu entwickeln. Weitere Informationen zum Entwickeln von Dienstverträgen auf Nachrichten Ebene finden Sie unter [Verwenden von Nachrichten Verträgen](using-message-contracts.md). Weitere Informationen zum Entwickeln von Diensten in nicht-SOAP-XML finden Sie unter [Interoperabilität mit POX-Anwendungen](interoperability-with-pox-applications.md).  
  
### <a name="understanding-the-hierarchy-of-requirements"></a>Grundlagen der Anforderungshierarchie  
 Ein Dienstvertrag gruppiert die Vorgänge, gibt das Nachrichtenaustauschmuster, die Nachrichtentypen und Datentypen an, die diese Nachrichten enthalten, und zeigt Kategorien von Laufzeitverhalten an, die eine Implementierung aufweisen muss, um den Vertrag zu unterstützen (z. B. dass Nachrichten verschlüsselt und signiert sein müssen). Der Dienstvertrag selbst gibt nicht genau an, wie diese Anforderungen erfüllt werden, sondern lediglich, dass sie erfüllt werden müssen. Welcher Verschlüsselungstyp verwendet wird oder wie eine Nachricht signiert wird, hängt von der Implementierung und Konfiguration eines kompatiblen Dienstes ab.  
  
 Beachten Sie, dass der Vertrag bestimmte Anforderungen an die Dienstvertragsimplementierung und die Laufzeitkonfiguration stellt, um ein Verhalten hinzuzufügen. Die Anforderungen, um einen Dienst für die Verwendung verfügbar zu machen, bauen auf den vorherigen Anforderungen auf. Wenn ein Vertrag Anforderungen an die Implementierung stellt, kann eine Implementierung noch weitere Anforderungen an die Konfiguration und die Bindungen stellen, die die Ausführung des Dienstes ermöglichen. Außerdem muss die Hostanwendung auch alle Anforderungen unterstützen, die die Dienstkonfiguration und die Bindungen hinzufügen.  
  
 Dieser Additive Anforderungs Prozess ist wichtig, um beim Entwerfen, implementieren, konfigurieren und Hosting Ihrer Windows Communication Foundation (WCF)-Dienst Anwendung zu berücksichtigen. Beispielsweise kann der Vertrag angeben, dass er eine Sitzung unterstützen muss. In diesem Fall müssen Sie die Bindung so konfigurieren, dass sie diese Vertragsanforderung unterstützt, oder die Dienstimplementierung funktioniert nicht. Wenn der Dienst integrierte Windows-Authentifizierung erfordert und in Internetinformationsdienste (IIS) gehostet wird, muss für die Webanwendung, in der sich der Dienst befindet, die integrierte Windows-Authentifizierung aktiviert und der anonyme Support deaktiviert sein. Weitere Informationen zu den Features und Auswirkungen der verschiedenen Dienst Host-Anwendungs Typen finden Sie unter [Hosting](hosting.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Endpunkte: Adressen, Bindungen und Verträge](endpoints-addresses-bindings-and-contracts.md)
- [Entwerfen von Dienstverträgen](../designing-service-contracts.md)
- [Implementieren von Dienstverträgen](../implementing-service-contracts.md)
