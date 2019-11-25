---
title: 'Vorgehensweise: Schützen von Nachrichten innerhalb einer zuverlässigen Sitzung'
ms.date: 03/30/2017
ms.assetid: aee33e50-936f-4486-9ca8-c1520c19a62d
ms.openlocfilehash: edff27fe9649387c1922c34e72ef59d615e52b90
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141661"
---
# <a name="how-to-secure-messages-within-reliable-sessions"></a>Vorgehensweise: Schützen von Nachrichten innerhalb einer zuverlässigen Sitzung

Dieses Thema enthält einen Überblick über die Schritte zum Aktivieren der Sicherheit auf Nachrichtenebene für den Nachrichtenaustausch innerhalb einer zuverlässigen Sitzung mithilfe einer der vom System bereitgestellten Bindungen, die eine solche Sitzung zwar unterstützen, standardmäßig aber keine Unterstützung dafür bieten. Aktivieren Sie eine sichere, zuverlässige Sitzung entweder Imperativ durch die Verwendung von Code oder deklarativ in der Konfigurationsdatei. Dieses Verfahren verwendet die Konfigurationsdateien von Client und Dienst, um die sichere, zuverlässige Sitzung zu aktivieren.

Dieses Verfahren besteht aus den folgenden drei Hauptaufgaben:

1. Angeben, dass der Client und der Dienst Nachrichten in einer zuverlässigen Sitzung austauschen.

1. Anfordern der Sicherheit auf Nachrichtenebene innerhalb der zuverlässigen Sitzung.

1. Angeben des Clientanmeldeinformationstyps, den der Client verwenden muss, um sich selbst beim Server authentifizieren zu können.

In der ersten Aufgabe ist es wichtig, dass das Endpunkt Konfigurationselement ein `bindingConfiguration` Attribut enthält, das auf eine Bindungs Konfiguration mit dem Namen (in diesem Beispiel) `MessageSecurity`verweist. Das [ **\<Binding >** ](../../configure-apps/file-schema/wcf/bindings.md) Configuration-Element verweist dann auf diesen Namen, um zuverlässige Sitzungen zu aktivieren, indem das `enabled`-Attribut des [ **\<ReliableSession >** ](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90)) -Elements auf `true`festgelegt wird. Sie können angeben, dass eine Zusicherung der Zustellung in der richtigen Reihenfolge innerhalb einer zuverlässigen Sitzung verfügbar ist, indem Sie das `ordered`-Attribut auf `true` festlegen.

Die Quell Kopie des Beispiels, auf dem diese Konfigurations Prozedur basiert, finden Sie in der [zuverlässigen WS-Sitzung](../../../../docs/framework/wcf/samples/ws-reliable-session.md).

Die wesentlichen Elemente der zweiten Aufgabe werden erreicht, indem das `mode`-Attribut des **\<Security >** -Elements, das im **\<Binding >** Element des Clients und des Diensts enthalten ist, auf `Message`festgelegt wird.

Die wesentlichen Elemente der dritten Aufgabe werden erreicht, indem das `clientCredentialType`-Attribut des **\<Message >** -Elements im **\<Security >** -Element des Clients und des Diensts auf `Certificate`festgelegt wird.

> [!NOTE]
> Wenn Sie Nachrichten Sicherheit mit zuverlässigen Sitzungen verwenden, versucht zuverlässiges Messaging, einen nicht authentifizierten Client zu authentifizieren, bis ein Timeout auftritt, anstatt beim ersten Fehler eine Ausnahme auszulösen.

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a>Konfigurieren Sie den Dienst mit einer wsHttpBinding, um eine zuverlässige Sitzung zu verwenden.

Dieses Verfahren wird unter Vorgehens [Weise: Austauschen von Nachrichten innerhalb einer zuverlässigen Sitzung](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md)beschrieben.

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a>Konfigurieren des Clients mit WSHttpBinding zur Verwendung einer zuverlässigen Sitzung

Dieses Verfahren wird unter Vorgehens [Weise: Austauschen von Nachrichten innerhalb einer zuverlässigen Sitzung](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md)beschrieben.

### <a name="set-the-mode-and-clientcredentialtype-in-configuration"></a>Legen Sie den Modus und clientkredentialtype in der Konfiguration fest.

1. Fügen Sie dem [ **\<-Bindungen >** ](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) Element der Konfigurationsdatei ein entsprechendes Bindungs Element hinzu. Im folgenden Beispiel wird ein [ **\<WSHttpBinding->** ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) Element hinzugefügt.

1. Fügen Sie ein **\<Bindungs >** Element hinzu, und legen Sie dessen `name`-Attribut auf einen geeigneten Wert fest. Im Beispiel wird der Name `MessageSecurity`verwendet.

1. Fügen Sie ein **\<Security >** -Element hinzu, und legen Sie das Attribut `mode` auf `Message`fest.

1. Fügen Sie im **\<Security >** -Element ein **\<Message->** Element hinzu, und legen Sie das `clientCredentialType`-Attribut auf `Certificate`fest.

```xml
<wsHttpBinding>
  <binding name="MessageSecurity">
    <security mode="Message">
      <message clientCredentialType="Certificate" />
    </security>
  </binding>
</wsHttpBinding>
```
