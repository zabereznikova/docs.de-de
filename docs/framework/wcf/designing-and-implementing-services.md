---
title: Entwerfen und Implementieren von Diensten
ms.date: 03/30/2017
helpviewer_keywords:
- defining service contracts [WCF]
ms.assetid: 036fae20-7c55-4002-b71d-ac4466e167a3
ms.openlocfilehash: ea32855a3a512b8e96b8d6d72f101523b5d16107
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96248772"
---
# <a name="designing-and-implementing-services"></a>Entwerfen und Implementieren von Diensten

In diesem Abschnitt wird gezeigt, wie WCF-Verträge definiert und implementiert werden. Ein Dienstvertrag gibt an, was ein Endpunkt an die Außenwelt kommuniziert. Konkreter gesagt ist er ein Anweisung zu mehreren bestimmten Nachrichten, die in grundlegende Nachrichtenaustauschmuster aufgeteilt sind, wie Anforderung/Antwort, unidirektional und Duplex. Wenn ein Dienstvertrag ein logisch zusammengehöriger Satz von Vorgängen des Nachrichtenaustauschs ist, dann ist ein Dienstvorgang ein einzelner Nachrichtenaustausch. Beispielsweise muss ein `Hello`-Vorgang natürlich eine Nachricht annehmen (damit der Aufrufer den Gruß ankündigen kann) und kann dann eine Nachricht zurückgeben (je nach Verfügung des Vorgangs).  
  
 Weitere Informationen zu Verträgen und anderen Kern Windows Communication Foundation (WCF)-Konzepten finden Sie unter [grundlegende Windows Communication Foundation Konzepte](fundamental-concepts.md). In diesem Thema werden in erster Linie Kenntnisse über Dienstverträge vermittelt. Weitere Informationen zum Erstellen von Clients, die Dienstverträge zum Herstellen einer Verbindung mit Diensten verwenden, finden Sie unter Übersicht über den [WCF-Client](wcf-client-overview.md).  
  
## <a name="overview"></a>Übersicht  

 Dieses Thema bietet eine allgemeine konzeptionelle Ausrichtung beim Entwerfen und Implementieren von WCF-Diensten. Untergeordnete Themen bieten ausführlichere Informationen zu den Besonderheiten des Entwerfens und Implementierens. Vor dem Entwerfen und Implementieren der WCF-Anwendung empfiehlt es sich, Folgendes zu tun:  
  
- Kenntnisse darüber, was ein Dienstvertrag ist, wie er funktioniert und erstellt wird.  
  
- Kenntnisse darüber, dass Verträge Mindestanforderungen angeben, die die Laufzeitkonfiguration oder die Hostumgebung möglicherweise nicht unterstützen.  
  
## <a name="service-contracts"></a>Dienstverträge  

 Ein Dienstvertrag gibt Folgendes an:  
  
- Die Vorgänge, die ein Vertrag verfügbar macht.  
  
- Die Signatur der Vorgänge in Bezug auf ausgetauschte Nachrichten.  
  
- Die Datentypen dieser Nachrichten.  
  
- Der Speicherort der Vorgänge.  
  
- Die spezifischen Protokolle und Serialisierungsformate, die verwendet werden, um die erfolgreiche Kommunikation mit dem Dienst zu unterstützen.  
  
 Beispielsweise kann ein Vertrag für eine Bestellung einen `CreateOrder`-Vorgang aufweisen, der eine Eingabe von Bestellinformationstypen annimmt und Erfolgs- oder Fehlerinformationen einschließlich einer Bestellnummer zurückgibt. Er kann auch einen `GetOrderStatus`-Vorgang aufweisen, der eine Bestellnummer annimmt und Bestellstatusinformationen zurückgibt. Ein Dienstvertrag dieser Art würde Folgendes angeben:  
  
1. Dass der Vertrag für die Bestellung aus `CreateOrder`- und `GetOrderStatus`-Vorgänge besteht.  
  
2. Dass die Vorgänge Eingabemeldungen und Ausgabemeldungen angegeben haben.  
  
3. Die Daten, die diese Meldungen enthalten können.  
  
4. Nach Kategorien geordnete Anweisungen zur für die erfolgreiche Verarbeitung der Meldungen erforderlichen Kommunikationsinfrastruktur. Beispielsweise schließen diese Details ein, ob und welche Formen von Sicherheit erforderlich sind, um eine erfolgreiche Kommunikation herzustellen.  
  
 Um diese Art von Informationen an andere Anwendungen auf vielen Plattformen (einschließlich nicht-Microsoft-Plattformen) zu vermitteln, werden XML-Dienstverträge in Standard-XML-Formaten, z. b. [Web Services Description Language](https://www.w3.org/TR/2001/NOTE-wsdl-20010315) (WSDL) und [XML-Schema](https://www.w3.org/XML/Schema) (XSD), öffentlich ausgedrückt. Entwickler für viele Plattformen können mithilfe dieser öffentlichen Vertragsinformationen Anwendungen erstellen, die mit dem Dienst kommunizieren können, da sie die Sprache der Spezifikation verstehen und diese Sprachen für das Ermöglichen der Interoperation konzipiert sind, indem sie die öffentlichen Formulare, Formate und Protokolle beschreiben, die der Dienst unterstützt. Weitere Informationen dazu, wie WCF diese Art von Informationen verarbeitet, finden Sie unter [Metadaten](./feature-details/metadata.md).  
  
 Verträge können auf verschiedene Weise ausgedrückt werden; WSDL und XSD sind zwar ausgezeichnete Sprachen zum Beschreiben von Diensten beim Zugriff, jedoch schwierige Sprachen bei der direkten Verwendung. Sie sind lediglich Beschreibungen eines Diensts und keine Dienstvertragsimplementierungen. Daher verwenden WCF-Anwendungen verwaltete Attribute, Schnittstellen und Klassen, um die Struktur eines Dienstanbieter zu definieren und zu implementieren.  
  
 Der resultierende Vertrag, der in verwalteten Typen definiert ist, kann als Metadaten – WSDL und XSD – *exportiert* werden, wenn Sie von Clients oder anderen Dienstimplementierern benötigt werden. Das Ergebnis ist ein einfaches Programmiermodell, das (mit öffentlichen Metadaten) für jede Clientanwendung beschrieben werden kann. Die Details der zugrunde liegenden SOAP-Nachrichten, der Transport-und sicherheitsbezogenen Informationen usw. können für WCF verbleiben, das die erforderlichen Konvertierungen zum und vom Dienst Vertragstyp System zum XML-Typsystem automatisch ausführt.  
  
 Weitere Informationen zum Entwerfen von Verträgen finden Sie unter [Entwerfen von Dienstverträgen](designing-service-contracts.md). Weitere Informationen zum Implementieren von Verträgen finden Sie unter [Implementieren von Dienstverträgen](implementing-service-contracts.md).  
  
### <a name="messages-up-front-and-center"></a>Nachrichten im Mittelpunkt  

 Die Verwendung verwalteter Schnittstellen, Klassen und Methoden zur Modellierung von Dienstvorgängen ist unkompliziert, wenn Sie mit Methodensignaturen im RPC-Stil (Remote Procedure Call) vertraut sind. Bei dieser Methode stellt die Übergabe von Parametern an eine Methode und der Empfang der Rückgabewerte die normale Form dar, Funktionen von einem Objekt oder einem anderen Codetyp anzufordern. Beispielsweise können Programmierer, die verwaltete Sprachen wie Visual Basic und C++ com verwenden, Ihr Wissen über den RPC-Stil (unabhängig davon, ob Objekte oder Schnittstellen verwendet werden) für die Erstellung von WCF-Dienstverträgen anwenden, ohne die Probleme zu beheben, die im RPC-Stil verteilter Objekt Systeme auftreten. Die Dienstausrichtung bietet den Vorteil lose gekoppelter, nachrichtenorientierter Programmierung, während gleichzeitig die Leichtigkeit und Vertrautheit der RPC-Programmiererfahrung erhalten bleibt.  
  
 Viele Programmierer fühlen sich mit nachrichtenorientierten Anwendungsprogrammierschnittstellen, beispielsweise mit Nachrichtenwarteschlangen wie Microsoft MSMQ, den <xref:System.Messaging>-Namespaces im .NET Framework oder dem Senden unstrukturierter XML in HTTP-Anforderungen wohler. Weitere Informationen zum Programmieren auf Nachrichten Ebene finden Sie unter [Verwenden von Nachrichten Verträgen](./feature-details/using-message-contracts.md), [Service Channel-Level-Programmierung](./extending/service-channel-level-programming.md)und [Interoperabilität mit POX-Anwendungen](./feature-details/interoperability-with-pox-applications.md).  
  
### <a name="understanding-the-hierarchy-of-requirements"></a>Grundlagen der Anforderungshierarchie  

 Ein Dienstvertrag gruppiert die Vorgänge, gibt das Nachrichtenaustauschmuster, die Nachrichtentypen und Datentypen an, die diese Nachrichten enthalten, und zeigt Kategorien von Laufzeitverhalten an, die eine Implementierung aufweisen muss, um den Vertrag zu unterstützen (z. B. dass Nachrichten verschlüsselt und signiert sein müssen). Der Dienstvertrag selbst gibt nicht genau an, wie diese Anforderungen erfüllt werden, sondern lediglich, dass sie erfüllt werden müssen. Welcher Verschlüsselungstyp verwendet wird oder wie eine Nachricht signiert wird, hängt von der Implementierung und Konfiguration eines kompatiblen Diensts ab.  
  
 Beachten Sie, dass der Vertrag bestimmte Anforderungen an die Dienstvertragsimplementierung und die Laufzeitkonfiguration stellt, um ein Verhalten hinzuzufügen. Die Anforderungen, um einen Dienst für die Verwendung verfügbar zu machen, bauen auf den vorherigen Anforderungen auf. Wenn ein Vertrag Anforderungen an die Implementierung stellt, kann eine Implementierung noch weitere Anforderungen an die Konfiguration und die Bindungen stellen, die die Ausführung des Dienstes ermöglichen. Außerdem muss die Hostanwendung auch alle Anforderungen unterstützen, die die Dienstkonfiguration und die Bindungen hinzufügen.  
  
 Dieser Additive Anforderungs Prozess ist wichtig, um beim Entwerfen, implementieren, konfigurieren und Hosting einer Windows Communication Foundation (WCF)-Dienst Anwendung zu berücksichtigen. Beispielsweise kann der Vertrag angeben, dass er eine Sitzung unterstützen muss. In diesem Fall müssen Sie die Bindung so konfigurieren, dass sie diese Vertragsanforderung unterstützt, oder die Dienstimplementierung funktioniert nicht. Wenn der Dienst integrierte Windows-Authentifizierung erfordert und in Internetinformationsdiensten gehostet wird, muss für die Webanwendung, in der sich der Dienst befindet, die integrierte Windows-Authentifizierung aktiviert und der anonyme Support deaktiviert sein. Weitere Informationen zu den Features und Auswirkungen der verschiedenen Dienst Host-Anwendungs Typen finden Sie unter [Hostingdienste](hosting-services.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Entwerfen von Dienstverträgen](designing-service-contracts.md)
- [Implementieren von Dienstverträgen](implementing-service-contracts.md)
