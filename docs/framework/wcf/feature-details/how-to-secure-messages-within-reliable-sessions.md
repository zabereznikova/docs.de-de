---
title: 'Vorgehensweise: Schützen von Nachrichten innerhalb einer zuverlässigen Sitzung'
ms.date: 03/30/2017
ms.assetid: aee33e50-936f-4486-9ca8-c1520c19a62d
ms.openlocfilehash: ee35f2a36ca08814423b5a3d0b1432bacd28c2e5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61973003"
---
# <a name="how-to-secure-messages-within-reliable-sessions"></a>Vorgehensweise: Schützen von Nachrichten innerhalb einer zuverlässigen Sitzung

Dieses Thema enthält einen Überblick über die Schritte zum Aktivieren der Sicherheit auf Nachrichtenebene für den Nachrichtenaustausch innerhalb einer zuverlässigen Sitzung mithilfe einer der vom System bereitgestellten Bindungen, die eine solche Sitzung zwar unterstützen, standardmäßig aber keine Unterstützung dafür bieten. Aktivieren Sie eine sichere, zuverlässige Sitzung, entweder verbindlich durch Verwenden von Code oder deklarativ in der Konfigurationsdatei. Dieses Verfahren verwendet die Konfigurationsdateien von Client und Dienst, um die sichere, zuverlässige Sitzung zu aktivieren.

Dieses Verfahren besteht aus den folgenden drei Hauptaufgaben:

1. Angeben, dass der Client und der Dienst Nachrichten in einer zuverlässigen Sitzung austauschen.

1. Anfordern der Sicherheit auf Nachrichtenebene innerhalb der zuverlässigen Sitzung.

1. Angeben des Clientanmeldeinformationstyps, den der Client verwenden muss, um sich selbst beim Server authentifizieren zu können.

Es ist wichtig, in der ersten Aufgabe, die die Endpunkt-Konfigurationselement enthalten eine `bindingConfiguration` -Attribut, das auf die Bindungskonfiguration Namens (in diesem Beispiel) `MessageSecurity`. Die [  **\<Bindung >** ](../../../../docs/framework/misc/binding.md) Konfigurationselement verweist dann auf diesen Namen, um zuverlässige Sitzungen zu aktivieren, indem Sie die Einstellung der `enabled` Attribut der [  **\<ReliableSession >** ](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90)) Element `true`. Sie können angeben, dass eine Zusicherung der Zustellung in der richtigen Reihenfolge innerhalb einer zuverlässigen Sitzung verfügbar ist, indem Sie das `ordered`-Attribut auf `true` festlegen.

Die Quellkopie des Beispiels auf dem dieses Konfigurationsverfahren basiert, finden Sie unter den [zuverlässige WS-Sitzung](../../../../docs/framework/wcf/samples/ws-reliable-session.md).

Die wesentlichen Punkte der zweiten Aufgabe werden erreicht, indem Sie die Einstellung der `mode` Attribut der  **\<Sicherheit >** in enthaltenen Elementen der  **\<Bindung >** Element des dem Client und Dienst `Message`.

Die wesentlichen Punkte der dritten Aufgabe werden erreicht, indem Sie die Einstellung der `clientCredentialType` Attribut der  **\<Nachricht >** in enthaltenen Elementen der  **\<Sicherheit >** Element des dem Client und Dienst `Certificate`.

> [!NOTE]
> Wenn Sie nachrichtensicherheit mit zuverlässigen Sitzungen verwenden, versucht das zuverlässiges Messaging einen nicht authentifizierten Client zu authentifizieren, bis ein Timeout auftritt, statt einer Ausnahme nach dem ersten Fehlschlag.

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a>Konfigurieren Sie den Dienst mit WSHttpBinding zur Verwendung einer zuverlässigen Sitzung

Dieses Verfahren wird beschrieben, [Vorgehensweise: Austauschen von Nachrichten innerhalb einer zuverlässigen Sitzung](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a>Konfigurieren Sie den Client mit WSHttpBinding zur Verwendung einer zuverlässigen Sitzung

Dieses Verfahren wird beschrieben, [Vorgehensweise: Austauschen von Nachrichten innerhalb einer zuverlässigen Sitzung](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).

### <a name="set-the-mode-and-clientcredentialtype-in-configuration"></a>Festlegen Sie der Modus und den ClientCredentialType in der Konfiguration.

1. Fügen Sie ein entsprechendes Bindungselement, das [  **\<Bindungen >** ](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) Element der Konfigurationsdatei. Im folgenden Beispiel wird eine [  **\<WsHttpBinding >** ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) Element.

1. Hinzufügen einer  **\<Bindung >** Element, und legen dessen `name` -Attribut auf einen geeigneten Wert. Im Beispiel wird der Name `MessageSecurity`.

1. Hinzufügen einer  **\<Sicherheit >** Element, und legen die `mode` Attribut `Message`.

1. Innerhalb der  **\<Sicherheit >** -Element, Hinzufügen einer  **\<Nachricht >** Element, und legen die `clientCredentialType` Attribut `Certificate`.

```xml
<wsHttpBinding>
  <binding name="MessageSecurity">
    <security mode="Message">
      <message clientCredentialType="Certificate" />
    </security>
  </binding>
</wsHttpBinding>
```
