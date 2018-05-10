---
title: Bindungen und Bindungselemente
ms.date: 03/30/2017
helpviewer_keywords:
- binding elements [WCF]
ms.assetid: 765ff77b-7682-4ea3-90eb-e4d751e37379
ms.openlocfilehash: 2a0e797a921ff20b2432e824c92c09fff833bf7d
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="bindings-and-binding-elements"></a>Bindungen und Bindungselemente
Bindungen sind Sammlungen spezieller Konfigurationselemente, die aufgerufen *Bindungselementen*, werden ausgewertet, von der Service-Laufzeit, wenn ein Client oder ein Dienstendpunkt erstellt wird. Der Typ und die Reihenfolge der Bindungselemente in einer Bindung bestimmen die Auswahl und Stapelreihenfolge des Protokolls und der Transportkanäle in einem Endpunkt-Kanalstapel.  
  
 Bindungen, vor allem solche, die vom System bereitgestellt werden, weisen normalerweise auch mehrere Konfigurationseigenschaften auf, die die am häufigsten bearbeiteten Eigenschaften der gekapselten Bindungselemente widerspiegeln.  
  
 Eine Bindung muss genau ein Transportbindungselement enthalten. Jedes Transportbindungselement weist auf ein Standardnachrichten-Codierungsbindungselement hin, das durch das Hinzufügen von maximal einem Nachrichten codierenden Bindungselement zur Bindung überschrieben werden kann. Neben den Transportbindungselementen und Encoderbindungselementen kann die Bindung auch eine beliebige Anzahl an Protokollbindungselementen enthalten, die zusammen die für den Dienst benötigten Funktionen implementieren, und eine SOAP-Nachricht von einem Endpunkt zum nächsten senden. Weitere Informationen finden Sie unter [Bindungen verwenden, und Konfigurieren von Diensten und Clients](../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md).  
  
## <a name="extending-bindings-and-binding-elements"></a>Erweitern von Bindungen und Bindungselementen  
 Windows Communication Foundation (WCF) enthält die vom System bereitgestellte Bindungen, die eine Vielzahl von Szenarien abdecken. (Weitere Informationen finden Sie unter [sicherheitsbindungsarten Bindungen](../../../../docs/framework/wcf/system-provided-bindings.md).) Möglicherweise gibt es Zeiten, aber wenn Sie benötigen zum Erstellen und verwenden eine Bindung, die nicht in WCF enthalten ist. Bei den folgenden Szenarien muss eine neue Bindung erstellt werden:  
  
-   Um ein neues Bindungselement zu verwenden (z. B. ein neues Transport-, Codierungs- oder Protokollbindungselement), müssen Sie eine neue Bindung erstellen, die dieses Bindungselemente enthält. Wenn Sie beispielsweise ein benutzerdefiniertes `UdpTransportBindingElement` für den UDP-Transport hinzufügen, müssen Sie eine neue Bindung erstellen, damit Sie das Element verwenden können. Weitere Informationen zum Ausführen dieses Verhalten mithilfe der <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> finden Sie unter [benutzerdefinierte Bindungen](../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
-   Zum Konfigurieren vorhandener Bindungselemente, sodass die vom System bereitgestellten Bindungen nicht auf öffentlichen Eigenschaften verfügbar gemacht werden. Sie müssen beispielsweise eine neue Bindung erstellen, um die Reihenfolge zu ändern, in der Signatur- und Verschlüsselungsvorgänge durchgeführt werden. Informationen zum Ausführen dieses Verhaltens finden Sie unter [wie: Anpassen einer sicherheitsbindungsarten Bindung](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md).  
  
-   Zum Einrichten von unternehmensweiten Standardbindungen, die nur bestimmte Konfigurationsoptionen verfügbar machen. Wenn Sie beispielsweise für Ihr Unternehmen eine Variante der <xref:System.ServiceModel.WSHttpBinding> erstellen, in der Sicherheit nicht deaktiviert werden kann, erstellen Sie eine neue Bindung, die das gleiche Verhalten hat wie die <xref:System.ServiceModel.WSHttpBinding>, allerdings ist die Sicherheit immer aktiviert. Weitere Informationen finden Sie unter [Erstellen benutzerdefinierter Bindungen](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md).  
  
-   Zum Durchführen von Metadatenanpassungen, normalerweise zum Konfigurieren oder Verwenden von benutzerdefinierten Bindungselementen. Weitere Informationen zum Bereitstellen von metadatenunterstützung für Bindungen und Bindungselemente finden Sie unter [Konfigurations- und Metadatenunterstützung](../../../../docs/framework/wcf/extending/configuration-and-metadata-support.md).  
  
-  
  
## <a name="channels-bindings-and-binding-elements"></a>Kanäle, Bindungen und Bindungselemente  
 Bindungen und Bindungselemente sind das Bindeglied zwischen dem Anwendungsprogrammiermodell, das die Attribute und Verhalten enthält, und dem Kanalmodell, das Factorys und Listeners, Nachrichtenencoder sowie Transport- und Protokollimplementierungen enthält. Normalerweise werden Bindungselemente und Bindungen implementiert, um Kanäle zu aktivieren, damit sie von der Anwendungsschicht verwendet werden.  
  
 Die Kanalschicht sendet oder empfängt Nachrichten von und an die Dienstschicht und transportiert diese Nachrichten zwischen den Endpunkten. Auf einem Client besteht die Kanalschicht aus einem Stapel an Kanalfactorys, die Kanäle zu einem Netzwerkendpunkt erstellen. Auf einem Dienst besteht die Kanalschicht aus einem Stapel an Kanallisteners, die die an einem Netzwerkendpunkt eingehenden Kanäle akzeptieren.  
  
 Es gibt zwei allgemeine Arten von Kanälen: Protokollkanäle und Transportkanäle. Transportkanäle sind verantwortlich für die eigentliche Übertragung einer Nachricht von einem Netzwerkendpunkt zum nächsten. Transportkanäle benötigen einen Standardnachrichtenencoder und sollten auch den durch das Nachrichtenencoder-Bindungselement bereitgestellten alternativen Nachrichtenencoder verwenden können. Mit einen Nachrichtenencoder verwandeln Sie eine <xref:System.ServiceModel.Channels.Message?displayProperty=nameWithType> in eine Übertragungsdarstellung und umgekehrt. Mit Protokollkanälen werden Protokolle auf SOAP-Ebene (z. B. WS-Sicherheit oder WS-ReliableMessaging) implementiert.  
  
 Die grundlegende Anforderung an Transportkanäle und Protokollkanäle besteht darin, die erforderlichen Kanalschnittstellen zu implementieren. Um eine funktionsfähige Kanalschicht zu erstellen, müssen ihnen Factorys und Listeners usw. zugewiesen sein. Um die kanalimplementierungen von WCF verwenden, es ein zugewiesenes Bindungselement sein muss, abgeleitet <xref:System.ServiceModel.Channels.BindingElement> für jeden Kanal und sollte ein verwandte bindungserweiterungselement für die Einbeziehung in die Konfigurationsdateien, die von abgeleitet<xref:System.ServiceModel.Configuration.BindingElementExtensionElement>.  
  
 Wie zuvor erwähnt können Bindungselemente für Nachrichtenencoder, Protokollkanalimplementierungen und Transportkanalimplementierungen zu einem Kanalstapel zusammengefasst werden. Zum Aufreihen in einem geordneten Satz wird die Bindung verwendet. Bindungen und Bindungselemente verbinden das Anwendungsprogrammiermodell mit dem Kanalmodell. Sie können die Kanalimplementierungen direkt aus dem Code verwenden, aber erst nachdem Encoder, Transporte und Protokolle als Bindungselemente implementiert wurden, können sie aus dem Dienstschichtprogrammiermodell heraus verwendet werden.  
  
 Ausführliche Informationen zum Entwickeln von Kanälen und ihre Bindungselemente finden Sie unter [Erweitern der Kanalschicht](../../../../docs/framework/wcf/extending/extending-the-channel-layer.md).
