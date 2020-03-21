---
title: Kontextaustauschprotokoll
ms.date: 03/30/2017
ms.assetid: 3dfd38e0-ae52-491c-94f4-7a862b9843d4
ms.openlocfilehash: 00adb68d96f77ce0953811d13b5377ec4ed1e0ea
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185265"
---
# <a name="context-exchange-protocol"></a>Kontextaustauschprotokoll
In diesem Abschnitt wird das Kontextaustauschprotokoll beschrieben, das in Der Version .NET Framework Version 3.5 (Windows Communication Foundation) vorgestellt wurde. Mithilfe dieses Protokolls kann vom Clientkanal ein vom Dienst bereitgestellter Kontext akzeptiert und für alle nachfolgenden Anforderungen übernommen werden, die über dieselbe Clientkanalinstanz an den Dienst gesendet werden. Zur Implementierung des Kontextaustauschprotokolls kann einer der beiden folgenden Mechanismen verwendet werden, um den Kontext zwischen dem Server und dem Client zu propagieren: HTTP-Cookies oder ein SOAP-Header.  
  
 Das Kontextaustauschprotokoll wird in einer benutzerdefinierten Kanalebene implementiert. Der Kontext wird mithilfe der <xref:System.ServiceModel.Channels.ContextMessageProperty>-Eigenschaft von der Kanalebene an die Anwendungsebene (und umgekehrt) übermittelt. Zur Übertragung zwischen Endpunkten wird der Wert des Kontexts entweder auf der Kanalebene in einen SOAP-Header serialisiert oder in die bzw. aus den Nachrichteneigenschaften konvertiert, die eine HTTP-Anforderung bzw. eine HTTP-Antwort darstellen. Im zweiten Fall wird erwartet, das eine der zugrunde liegenden Kanalebenen die Eigenschaften der HTTP-Anforderungs- bzw. HTTP-Antwortnachrichten in bzw. aus HTTP-Cookies umwandelt. Der für den Kontextaustausch zu verwendende Mechanismus wird mithilfe der <xref:System.ServiceModel.Channels.ContextExchangeMechanism>-Eigenschaft für das <xref:System.ServiceModel.Channels.ContextBindingElement> ausgewählt Gültige Werte sind `HttpCookie` und `SoapHeader`.  
  
 Auf dem Client kann eine Kanalinstanz abhängig von der Einstellung der Kanaleigenschaft <xref:System.ServiceModel.Channels.IContextManager.Enabled%2A> in zwei Modi arbeiten.  
  
## <a name="mode-1-channel-context-management"></a>Modus 1: Kanalkontextverwaltung  
 Dies ist der Standardmodus, wobei <xref:System.ServiceModel.Channels.IContextManager.Enabled%2A> auf `true` festgelegt wird. In diesem Modus verwaltet der Kontextkanal den Kontext und speichert den Kontext während seiner Lebensdauer zwischen. Der Kontext kann über die Kanaleigenschaft `IContextManager` durch einen Aufruf der `GetContext`-Methode vom Kanal abgerufen werden. Der Kanal kann auch vor dem Öffnen vorab mit einem bestimmten Kontext initialisiert werden, indem die `SetContext`-Methode für die Kanaleigenschaft aufgerufen wird. Sobald der Kanal mit einem Kontext initialisiert wurde, kann er nicht mehr zurückgesetzt werden.  
  
 Im Folgenden finden Sie eine Liste der Dinge, die in diesem Modus nicht verändert werden können:  
  
- Jeder Versuch, den Kontext mit `SetContext` zurückzusetzen, nachdem der Kanal geöffnet wurde, löst eine <xref:System.InvalidOperationException> aus.  
  
- Jeder Versuch, Kontext mithilfe der <xref:System.ServiceModel.Channels.ContextMessageProperty> in einer ausgehenden Nachricht zu senden, löst eine <xref:System.InvalidOperationException> aus.  
  
- Wenn eine Nachricht mit einem bestimmten Kontext vom Server empfangen wird, dann wird eine <xref:System.ServiceModel.ProtocolException> ausgelöst, wenn der Kanal bereits mit einem bestimmten Kontext initialisiert wurde.  
  
    > [!NOTE]
    > Der Empfang eines Anfangskontexts vom Server ist nur dann angemessen, wenn der Kanal geöffnet wird, ohne dass explizit ein Kontext festgelegt wird.  
  
- Bei eingehenden Nachrichten hat <xref:System.ServiceModel.Channels.ContextMessageProperty> stets den Wert NULL.  
  
## <a name="mode-2-application-context-management"></a>Modus 2: Anwendungskontextverwaltung  
 Dieser Modus wird verwendet, wenn <xref:System.ServiceModel.Channels.IContextManager.Enabled%2A> auf `false` festgelegt wurde. In diesem Modus verwaltet der Kontextkanal keinen Kontext. Es liegt in der Verantwortung der Anwendung, den Kontext mithilfe von <xref:System.ServiceModel.Channels.ContextMessageProperty> abzurufen, zu verwalten und zu übernehmen. Jeder Versuch, `GetContext` oder `SetContext` aufzurufen, führt zu einer <xref:System.InvalidOperationException>.  
  
 Unabhängig vom ausgewählten Modus unterstützt die Clientkanalfactory die Nachrichtenaustauschmuster <xref:System.ServiceModel.Channels.IRequestChannel>, <xref:System.ServiceModel.Channels.IRequestSessionChannel> und <xref:System.ServiceModel.Channels.IDuplexSessionChannel>.  
  
 Auf der Dienstseite ist eine Instanz des Kanals für die Konvertierung des vom Client in eingehenden Nachrichten bereitgestellten Kontexts in eine <xref:System.ServiceModel.Channels.ContextMessageProperty>-Eigenschaft verantwortlich. Die Anwendungsebene oder andere Kanäle weiter oben im Aufrufstapel können dann auf diese Nachrichteneigenschaft zugreifen. Die Dienstkanäle erlauben es der Anwendungsebene auch, einen neuen Kontextwert anzugeben, der zurück zum Client übermittelt werden soll, indem der Antwortnachricht eine <xref:System.ServiceModel.Channels.ContextMessageProperty> angehängt wird. Diese Eigenschaft wird in einen SOAP-Header oder ein HTTP-Cookie umgewandelt, der bzw. das den Kontext enthält, der von der Konfiguration der Bindung abhängt. Der Dienstkanallistener unterstützt die Nachrichtenaustauschmuster <xref:System.ServiceModel.Channels.IReplyChannel>, <xref:System.ServiceModel.Channels.IReplySessionChannel> und <xref:System.ServiceModel.Channels.IReplySessionChannel>.  
  
 Das Kontextaustauschprotokoll führt den neuen SOAP-Header `wsc:Context` ein, der zur Darstellung der Kontextinformationen dient, wenn der Kontext nicht mithilfe von HTTP-Cookies übermittelt wird. Das Kontextheaderschema lässt eine beliebige Anzahl untergeordneter Elemente zu, die jeweils einen Zeichenfolgenschlüssel und Zeichenfolgeninhalt enthalten. Es folgt ein Beispiel für einen Kontextheader.  
  
 `<Context xmlns="http://schemas.microsoft.com/ws/2006/05/context">`  
  
 `<property name="myContext">context-2</property>`  
  
 `</Context>`  
  
 Im `HttpCookie`-Modus werden Cookies mit dem `SetCookie`-Header festgelegt. Der Cookiename lautet `WscContext`. Der Wert des Cookies entspricht der Base64-Codierung des `wsc:Context`-Headers. Dieser Wert wird in Anführungszeichen eingeschlossen.  
  
 Der Wert des Kontexts muss während der Übermittlung aus den gleichen Gründen vor Veränderungen geschützt werden, aus denen WS-Adressierungsheader geschützt werden: Anhand des Headers wird ermittelt, an welchen Endpunkt im Dienst die Anforderung weitergeleitet werden soll. Deshalb muss der `wsc:Context`-Header entweder auf SOAP- oder auf Transportebene digital signiert und verschlüsselt werden, wenn für die Bindung ein Nachrichtenschutz verfügbar ist. Werden zum Weitergeben von Kontext HTTP-Cookies verwendet, sollten diese mithilfe der Transportsicherheit geschützt werden.  
  
 Für Dienstendpunkte, bei denen die Unterstützung des Kontextaustauschprotokolls erforderlich ist, kann diese Anforderung in der veröffentlichten Richtlinie als explizite Anforderung festgelegt werden. Es wurden zwei neue Richtlinienassertionen eingeführt, die die Anforderung des Clients zur Unterstützung des Kontextaustauschprotokolls auf SOAP-Ebene oder das Aktivieren der Unterstützung von HTTP-Cookies darstellen. Die Generierung dieser Assertionen in der Richtlinie auf Dienstseite wird vom Wert der <xref:System.ServiceModel.Channels.ContextBindingElement.ContextExchangeMechanism%2A>-Eigenschaft folgendermaßen gesteuert:  
  
- Für <xref:System.ServiceModel.Channels.ContextExchangeMechanism.ContextSoapHeader> wird die folgende Assertion generiert:  
  
    ```xml  
    <IncludeContext
    xmlns="http://schemas.microsoft.com/ws/2006/05/context"  
    protectionLevel="Sign" />  
    ```  
  
- Für <xref:System.ServiceModel.Channels.ContextExchangeMechanism.HttpCookie> wird die folgende Assertion generiert:  
  
    ```xml  
    <HttpUseCookie xmlns="http://schemas.xmlsoap.org/soap/http"/>  
    ```  
  
## <a name="see-also"></a>Weitere Informationen

- [Leitfaden für die Interoperabilität von Webdienstprotokollen](../../../../docs/framework/wcf/feature-details/web-services-protocols-interoperability-guide.md)
