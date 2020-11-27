---
title: Bindungen und Bindungselemente
ms.date: 03/30/2017
helpviewer_keywords:
- binding elements [WCF]
ms.assetid: 765ff77b-7682-4ea3-90eb-e4d751e37379
ms.openlocfilehash: 16e1b7840be6a3ec247033fa3a2eada9e5799bdb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262137"
---
# <a name="bindings-and-binding-elements"></a>Bindungen und Bindungselemente

Bindungen sind Auflistungen von speziellen Konfigurationselementen, die als *Bindungs Elemente* bezeichnet werden. Diese werden von der Dienst Laufzeit ausgewertet, wenn ein Client oder ein Dienst Endpunkt erstellt wird. Der Typ und die Reihenfolge der Bindungselemente in einer Bindung bestimmen die Auswahl und Stapelreihenfolge des Protokolls und der Transportkanäle in einem Endpunkt-Kanalstapel.  
  
 Bindungen, vor allem solche, die vom System bereitgestellt werden, weisen normalerweise auch mehrere Konfigurationseigenschaften auf, die die am häufigsten bearbeiteten Eigenschaften der gekapselten Bindungselemente widerspiegeln.  
  
 Eine Bindung muss genau ein Transportbindungselement enthalten. Jedes Transportbindungselement weist auf ein Standardnachrichten-Codierungsbindungselement hin, das durch das Hinzufügen von maximal einem Nachrichten codierenden Bindungselement zur Bindung überschrieben werden kann. Neben den Transportbindungselementen und Encoderbindungselementen kann die Bindung auch eine beliebige Anzahl an Protokollbindungselementen enthalten, die zusammen die für den Dienst benötigten Funktionen implementieren, und eine SOAP-Nachricht von einem Endpunkt zum nächsten senden. Weitere Informationen finden [Sie unter Verwenden von Bindungen zum Konfigurieren von Diensten und Clients](../using-bindings-to-configure-services-and-clients.md).  
  
## <a name="extending-bindings-and-binding-elements"></a>Erweitern von Bindungen und Bindungselementen  

 Windows Communication Foundation (WCF) umfasst vom System bereitgestellte Bindungen, die eine Vielzahl von Szenarios abdecken. (Weitere Informationen finden Sie unter vom [System bereitgestellte Bindungen](../system-provided-bindings.md).) Es kann jedoch vorkommen, dass Sie eine Bindung erstellen und verwenden müssen, die nicht in WCF enthalten ist. Bei den folgenden Szenarien muss eine neue Bindung erstellt werden:  
  
- Um ein neues Bindungselement zu verwenden (z. B. ein neues Transport-, Codierungs- oder Protokollbindungselement), müssen Sie eine neue Bindung erstellen, die dieses Bindungselemente enthält. Wenn Sie beispielsweise ein benutzerdefiniertes `UdpTransportBindingElement` für den UDP-Transport hinzufügen, müssen Sie eine neue Bindung erstellen, damit Sie das Element verwenden können. Weitere Informationen zum Durchführen dieses Verhaltens mithilfe des- <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> Typs finden Sie unter [benutzerdefinierte Bindungen](custom-bindings.md).  
  
- Zum Konfigurieren vorhandener Bindungselemente, sodass die vom System bereitgestellten Bindungen nicht auf öffentlichen Eigenschaften verfügbar gemacht werden. Sie müssen beispielsweise eine neue Bindung erstellen, um die Reihenfolge zu ändern, in der Signatur- und Verschlüsselungsvorgänge durchgeführt werden. Weitere Informationen zum Durchführen dieses Verhaltens finden [Sie unter Gewusst wie: Anpassen einer System-Provided Bindung](how-to-customize-a-system-provided-binding.md).  
  
- Zum Einrichten von unternehmensweiten Standardbindungen, die nur bestimmte Konfigurationsoptionen verfügbar machen. Wenn Sie beispielsweise für Ihr Unternehmen eine Variante der <xref:System.ServiceModel.WSHttpBinding> erstellen, in der Sicherheit nicht deaktiviert werden kann, erstellen Sie eine neue Bindung, die das gleiche Verhalten hat wie die <xref:System.ServiceModel.WSHttpBinding>, allerdings ist die Sicherheit immer aktiviert. Weitere Informationen finden Sie unter [Erstellen von User-Defined Bindungen](creating-user-defined-bindings.md).  
  
- Zum Durchführen von Metadatenanpassungen, normalerweise zum Konfigurieren oder Verwenden von benutzerdefinierten Bindungselementen. Weitere Informationen zum Bereitstellen von Metadatenunterstützung für Bindungen und Bindungs Elemente finden Sie [unter Unterstützung von Konfigurationen und Metadaten](configuration-and-metadata-support.md).  

## <a name="channels-bindings-and-binding-elements"></a>Kanäle, Bindungen und Bindungselemente  

 Bindungen und Bindungselemente sind das Bindeglied zwischen dem Anwendungsprogrammiermodell, das die Attribute und Verhalten enthält, und dem Kanalmodell, das Factorys und Listeners, Nachrichtenencoder sowie Transport- und Protokollimplementierungen enthält. Normalerweise werden Bindungselemente und Bindungen implementiert, um Kanäle zu aktivieren, damit sie von der Anwendungsschicht verwendet werden.  
  
 Die Kanalschicht sendet oder empfängt Nachrichten von und an die Dienstschicht und transportiert diese Nachrichten zwischen den Endpunkten. Auf einem Client besteht die Kanalschicht aus einem Stapel an Kanalfactorys, die Kanäle zu einem Netzwerkendpunkt erstellen. Auf einem Dienst besteht die Kanalschicht aus einem Stapel an Kanallisteners, die die an einem Netzwerkendpunkt eingehenden Kanäle akzeptieren.  
  
 Es gibt zwei allgemeine Arten von Kanälen: Protokollkanäle und Transportkanäle. Transportkanäle sind verantwortlich für die eigentliche Übertragung einer Nachricht von einem Netzwerkendpunkt zum nächsten. Transportkanäle benötigen einen Standardnachrichtenencoder und sollten auch den durch das Nachrichtenencoder-Bindungselement bereitgestellten alternativen Nachrichtenencoder verwenden können. Mit einen Nachrichtenencoder verwandeln Sie eine <xref:System.ServiceModel.Channels.Message?displayProperty=nameWithType> in eine Übertragungsdarstellung und umgekehrt. Mit Protokollkanälen werden Protokolle auf SOAP-Ebene (z. B. WS-Sicherheit oder WS-ReliableMessaging) implementiert.  
  
 Die grundlegende Aufgabe von Transportkanälen und Protokollkanälen besteht darin, die erforderlichen Kanalschnittstellen zu implementieren. Um eine funktionsfähige Kanalschicht zu erstellen, müssen ihnen Factorys und Listeners usw. zugewiesen sein. Um die Kanal Implementierungen von WCF verwenden zu können, muss ein zugeordnetes Bindungs <xref:System.ServiceModel.Channels.BindingElement> Element für jeden Kanal von abgeleitet sein, und es sollte ein verwandtes Bindungs Erweiterungs Element vorhanden sein, das in Konfigurationsdateien eingeschlossen werden soll, die von abgeleitet sind <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> .  
  
 Wie zuvor erwähnt können Bindungselemente für Nachrichtenencoder, Protokollkanalimplementierungen und Transportkanalimplementierungen zu einem Kanalstapel zusammengefasst werden. Zum Aufreihen in einem geordneten Satz wird die Bindung verwendet. Bindungen und Bindungselemente verbinden das Anwendungsprogrammiermodell mit dem Kanalmodell. Sie können die Kanalimplementierungen direkt aus dem Code verwenden, aber erst nachdem Encoder, Transporte und Protokolle als Bindungselemente implementiert wurden, können sie aus dem Dienstschichtprogrammiermodell heraus verwendet werden.  
  
 Ausführliche Informationen zum Entwickeln von Kanälen und deren Bindungs Elementen finden Sie unter [Erweitern der Kanal Ebene](extending-the-channel-layer.md).
