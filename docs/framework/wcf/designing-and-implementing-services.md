---
title: Entwerfen und Implementieren von Diensten
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- defining service contracts [WCF]
ms.assetid: 036fae20-7c55-4002-b71d-ac4466e167a3
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b6d5a2dfb4db1d57f60e4c7f8cf3300b766402e1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="designing-and-implementing-services"></a>Entwerfen und Implementieren von Diensten
In diesem Abschnitt wird veranschaulicht, wie definieren und implementieren [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Verträge. Ein Dienstvertrag gibt an, was ein Endpunkt an die Außenwelt kommuniziert. Konkreter gesagt ist er ein Anweisung zu mehreren bestimmten Nachrichten, die in grundlegende Nachrichtenaustauschmuster aufgeteilt sind, wie Anforderung/Antwort, unidirektional und Duplex. Wenn ein Dienstvertrag ein logisch zusammengehöriger Satz von Vorgängen des Nachrichtenaustauschs ist, dann ist ein Dienstvorgang ein einzelner Nachrichtenaustausch. Beispielsweise muss ein `Hello`-Vorgang natürlich eine Nachricht annehmen (damit der Aufrufer den Gruß ankündigen kann) und kann dann eine Nachricht zurückgeben (je nach Verfügung des Vorgangs).  
  
 Weitere Informationen zu Verträgen und andere grundlegende [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] Konzepte, finden Sie unter [grundlegenden Windows Communication Foundation-Begriffe](../../../docs/framework/wcf/fundamental-concepts.md). In diesem Thema werden in erster Linie Kenntnisse über Dienstverträge vermittelt. Weitere Informationen zur Erstellung von Clients, die Dienstverträge, die für die Verbindung mit Diensten verwenden, finden Sie unter [Überblick über WCF-Client](../../../docs/framework/wcf/wcf-client-overview.md).  
  
## <a name="overview"></a>Übersicht  
 Dieses Thema bietet eine allgemeine Orientierung über das Entwerfen und Implementieren von [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Diensten. Untergeordnete Themen bieten ausführlichere Informationen zu den Besonderheiten des Entwerfens und Implementierens. Vor dem Entwerfen und Implementieren der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Anwendung werden die folgenden Voraussetzungen empfohlen:  
  
-   Kenntnisse darüber, was ein Dienstvertrag ist, wie er funktioniert und erstellt wird.  
  
-   Kenntnisse darüber, dass Verträge Mindestanforderungen angeben, die die Laufzeitkonfiguration oder die Hostumgebung möglicherweise nicht unterstützen.  
  
## <a name="service-contracts"></a>Dienstverträge  
 Ein Dienstvertrag gibt Folgendes an:  
  
-   Die Vorgänge, die ein Vertrag verfügbar macht.  
  
-   Die Signatur der Vorgänge in Bezug auf ausgetauschte Nachrichten.  
  
-   Die Datentypen dieser Nachrichten.  
  
-   Der Speicherort der Vorgänge.  
  
-   Die spezifischen Protokolle und Serialisierungsformate, die verwendet werden, um die erfolgreiche Kommunikation mit dem Dienst zu unterstützen.  
  
 Beispielsweise kann ein Vertrag für eine Bestellung einen `CreateOrder`-Vorgang aufweisen, der eine Eingabe von Bestellinformationstypen annimmt und Erfolgs- oder Fehlerinformationen einschließlich einer Bestellnummer zurückgibt. Er kann auch einen `GetOrderStatus`-Vorgang aufweisen, der eine Bestellnummer annimmt und Bestellstatusinformationen zurückgibt. Ein Dienstvertrag dieser Art würde Folgendes angeben:  
  
1.  Dass der Vertrag für die Bestellung aus `CreateOrder`- und `GetOrderStatus`-Vorgänge besteht.  
  
2.  Dass die Vorgänge Eingabemeldungen und Ausgabemeldungen angegeben haben.  
  
3.  Die Daten, die diese Meldungen enthalten können.  
  
4.  Nach Kategorien geordnete Anweisungen zur für die erfolgreiche Verarbeitung der Meldungen erforderlichen Kommunikationsinfrastruktur. Beispielsweise schließen diese Details ein, ob und welche Formen von Sicherheit erforderlich sind, um eine erfolgreiche Kommunikation herzustellen.  
  
 Um diese Art von Informationen für andere Anwendungen auf vielen Plattformen (einschließlich nicht-Microsoft-Plattformen) zu vermitteln, XML-Dienstverträge öffentlich in ausgedrückt werden standard-XML-Formaten, z. B. [Web Services Description Language](http://go.microsoft.com/fwlink/?LinkId=94952) () WSDL) und [XML-Schema](http://go.microsoft.com/fwlink/?LinkId=94953) (XSD), o. ä. Entwickler für viele Plattformen können mithilfe dieser öffentlichen Vertragsinformationen Anwendungen erstellen, die mit dem Dienst kommunizieren können, da sie die Sprache der Spezifikation verstehen und diese Sprachen für das Ermöglichen der Interoperation konzipiert sind, indem sie die öffentlichen Formulare, Formate und Protokolle beschreiben, die der Dienst unterstützt. Weitere Informationen dazu, wie [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Handles, die dieser Art von Informationen finden Sie unter [Metadaten](../../../docs/framework/wcf/feature-details/metadata.md).  
  
 Verträge können auf verschiedene Weise ausgedrückt werden; WSDL und XSD sind zwar ausgezeichnete Sprachen zum Beschreiben von Diensten beim Zugriff, jedoch schwierige Sprachen bei der direkten Verwendung. Sie sind lediglich Beschreibungen eines Diensts und keine Dienstvertragsimplementierungen. Daher verwenden [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Anwendungen verwaltete Attribute, Schnittstellen und Klassen zum Definieren der Struktur eines Diensts und zum Implementieren dieses Diensts.  
  
 Der resultierende in verwalteten Typen definierte Vertrag kann *exportiert* als Metadaten – WSDL und XSD – Wenn von Clients oder anderen dienstimplementierern benötigt wird. Das Ergebnis ist ein einfaches Programmiermodell, das (mit öffentlichen Metadaten) für jede Clientanwendung beschrieben werden kann. Die Details der zugrunde liegenden SOAP-Nachrichten, wie die Informationen zu Transport und Sicherheit, können [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] überlassen werden, das die erforderlichen Konvertierungen zum und vom Dienstvertragstypsystem zum XML-Typsystem automatisch ausführt.  
  
 Weitere Informationen zum Entwerfen von Verträgen finden Sie unter [Entwerfen von Dienstverträgen](../../../docs/framework/wcf/designing-service-contracts.md). Weitere Informationen zum Implementieren von Verträgen finden Sie unter [implementieren Dienstverträge](../../../docs/framework/wcf/implementing-service-contracts.md).  
  
### <a name="messages-up-front-and-center"></a>Nachrichten im Mittelpunkt  
 Die Verwendung verwalteter Schnittstellen, Klassen und Methoden zur Modellierung von Dienstvorgängen ist unkompliziert, wenn Sie mit Methodensignaturen im RPC-Stil (Remote Procedure Call) vertraut sind. Bei dieser Methode stellt die Übergabe von Parametern an eine Methode und der Empfang der Rückgabewerte die normale Form dar, Funktionen von einem Objekt oder einem anderen Codetyp anzufordern. Programmierer, die beispielsweise verwaltete Sprachen wie [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] und C++ COM verwenden, wenden ihre Kenntnisse des RPC-ähnlichen Ansatzes (egal ob sie Objekte oder Schnittstellen verwenden) auf die Erstellung von [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienstverträgen an, ohne auf die Probleme zu stoßen, die in verteilten RPC-Objektsystemen bekannt sind. Die Dienstausrichtung bietet den Vorteil lose gekoppelter, nachrichtenorientierter Programmierung, während gleichzeitig die Leichtigkeit und Vertrautheit der RPC-Programmiererfahrung erhalten bleibt.  
  
 Viele Programmierer fühlen sich mit nachrichtenorientierten Anwendungsprogrammierschnittstellen, beispielsweise mit Nachrichtenwarteschlangen wie Microsoft MSMQ, den <xref:System.Messaging>-Namespaces im .NET Framework oder dem Senden unstrukturierter XML in HTTP-Anforderungen wohler. Weitere Informationen zur Programmierung auf Nachrichtenebene finden Sie unter [Verwendung von Nachrichtenverträgen](../../../docs/framework/wcf/feature-details/using-message-contracts.md), [Programmierung auf Kanalebene Dienst](../../../docs/framework/wcf/extending/service-channel-level-programming.md), und [Interoperabilität mit POX-Anwendungen](../../../docs/framework/wcf/feature-details/interoperability-with-pox-applications.md).  
  
### <a name="understanding-the-hierarchy-of-requirements"></a>Grundlagen der Anforderungshierarchie  
 Ein Dienstvertrag gruppiert die Vorgänge, gibt das Nachrichtenaustauschmuster, die Nachrichtentypen und Datentypen an, die diese Nachrichten enthalten, und zeigt Kategorien von Laufzeitverhalten an, die eine Implementierung aufweisen muss, um den Vertrag zu unterstützen (z. B. dass Nachrichten verschlüsselt und signiert sein müssen). Der Dienstvertrag selbst gibt nicht genau an, wie diese Anforderungen erfüllt werden, sondern lediglich, dass sie erfüllt werden müssen. Welcher Verschlüsselungstyp verwendet wird oder wie eine Nachricht signiert wird, hängt von der Implementierung und Konfiguration eines kompatiblen Diensts ab.  
  
 Beachten Sie, dass der Vertrag bestimmte Anforderungen an die Dienstvertragsimplementierung und die Laufzeitkonfiguration stellt, um ein Verhalten hinzuzufügen. Die Anforderungen, um einen Dienst für die Verwendung verfügbar zu machen, bauen auf den vorherigen Anforderungen auf. Wenn ein Vertrag Anforderungen an die Implementierung stellt, kann eine Implementierung noch weitere Anforderungen an die Konfiguration und die Bindungen stellen, die die Ausführung des Dienstes ermöglichen. Außerdem muss die Hostanwendung auch alle Anforderungen unterstützen, die die Dienstkonfiguration und die Bindungen hinzufügen.  
  
 Beachten Sie unbedingt diesen zusätzlichen Anforderungsprozess beim Entwerfen, Implementieren, Konfigurieren und Hosten einer [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]-Dienstanwendung. Beispielsweise kann der Vertrag angeben, dass er eine Sitzung unterstützen muss. In diesem Fall müssen Sie die Bindung so konfigurieren, dass sie diese Vertragsanforderung unterstützt, oder die Dienstimplementierung funktioniert nicht. Wenn der Dienst integrierte Windows-Authentifizierung erfordert und in Internetinformationsdiensten gehostet wird, muss für die Webanwendung, in der sich der Dienst befindet, die integrierte Windows-Authentifizierung aktiviert und der anonyme Support deaktiviert sein. Weitere Informationen zu den Funktionen und die Auswirkungen von den anderen Dienst Anwendung Hosttypen finden Sie unter [Hostingdienste](../../../docs/framework/wcf/hosting-services.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Entwerfen von Dienstverträgen](../../../docs/framework/wcf/designing-service-contracts.md)  
 [Implementieren von Dienstverträgen](../../../docs/framework/wcf/implementing-service-contracts.md)
