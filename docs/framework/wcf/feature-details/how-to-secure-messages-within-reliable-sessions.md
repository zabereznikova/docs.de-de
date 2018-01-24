---
title: "Vorgehensweise: Schützen von Nachrichten innerhalb einer zuverlässigen Sitzung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aee33e50-936f-4486-9ca8-c1520c19a62d
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 2604b9dacf11b9971b10d23d9a807092ddf07830
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-secure-messages-within-reliable-sessions"></a>Vorgehensweise: Schützen von Nachrichten innerhalb einer zuverlässigen Sitzung

Dieses Thema enthält einen Überblick über die Schritte zum Aktivieren der Sicherheit auf Nachrichtenebene für den Nachrichtenaustausch innerhalb einer zuverlässigen Sitzung mithilfe einer der vom System bereitgestellten Bindungen, die eine solche Sitzung zwar unterstützen, standardmäßig aber keine Unterstützung dafür bieten. Aktivieren Sie eine sichere, zuverlässige Sitzung entweder verbindlich durch Verwenden von Code oder deklarativ in der Konfigurationsdatei. Dieses Verfahren verwendet die Konfigurationsdateien von Client und Dienst, um die sichere, zuverlässige Sitzung zu aktivieren.

Dieses Verfahren besteht aus den folgenden drei Hauptaufgaben:

1. Angeben, dass der Client und der Dienst Nachrichten in einer zuverlässigen Sitzung austauschen.

1. Anfordern der Sicherheit auf Nachrichtenebene innerhalb der zuverlässigen Sitzung.

1. Angeben des Clientanmeldeinformationstyps, den der Client verwenden muss, um sich selbst beim Server authentifizieren zu können.

Es ist wichtig, in der ersten Aufgabe, die der Endpunkt-Konfigurationselement enthalten eine `bindingConfiguration` -Attribut, das auf die Bindungskonfiguration Namens (in diesem Beispiel) `MessageSecurity`. Die [  **\<Bindung >** ](../../../../docs/framework/misc/binding.md) Konfigurationselement verweist dann diesen Namen, um zuverlässige Sitzungen zu aktivieren, durch Festlegen der `enabled` Attribut des der [  **\<ReliableSession >** ](http://msdn.microsoft.com/library/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b) Element `true`. Sie können angeben, dass eine Zusicherung der Zustellung in der richtigen Reihenfolge innerhalb einer zuverlässigen Sitzung verfügbar ist, indem Sie das `ordered`-Attribut auf `true` festlegen.

Eine Kopie der Quelle des Beispiels auf dem diese Vorgehensweise basiert, finden Sie unter der [zuverlässige WS-Sitzung](../../../../docs/framework/wcf/samples/ws-reliable-session.md).

Die wesentlichen Elemente der zweiten Aufgabe werden erreicht, indem die `mode` Attribut von der  **\<Sicherheit >** in enthaltenen Elementen der  **\<Bindung >** Element des dem Client und Dienst `Message`.

Die wesentlichen Elemente der dritten Aufgabe werden erreicht, indem die `clientCredentialType` Attribut von der  **\<Nachricht >** in enthaltenen Elementen der  **\<Sicherheit >** Element des dem Client und Dienst `Certificate`.

> [!NOTE]
> Wenn Sie nachrichtensicherheit mit zuverlässigen Sitzungen verwenden, versucht das zuverlässiges Messaging, einen nicht authentifizierten Client zu authentifizieren, bis ein Timeout auftritt, statt einer Ausnahme nach dem ersten Fehlschlag.

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a>Konfigurieren Sie den Dienst mit WSHttpBinding zur Verwendung einer zuverlässigen Sitzung

Hierin wird beschrieben, [Vorgehensweise: Exchange Nachrichten innerhalb einer zuverlässigen Sitzung](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a>Konfigurieren Sie den Client mit WSHttpBinding zur Verwendung einer zuverlässigen Sitzung

Hierin wird beschrieben, [Vorgehensweise: Exchange Nachrichten innerhalb einer zuverlässigen Sitzung](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).

### <a name="set-the-mode-and-clientcredentialtype-in-configuration"></a>Festlegen Sie der Modus und den ClientCredentialType in der Konfiguration.

1. Fügen Sie eine entsprechende Bindungselement auf dem [  **\<Bindungen >** ](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) Element der Konfigurationsdatei. Im folgenden Beispiel wird eine [  **\<WsHttpBinding >** ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) Element.

1. Hinzufügen einer  **\<Bindung >** Element, und legen seine `name` -Attribut auf einen geeigneten Wert. Im Beispiel wird der Name `MessageSecurity`.

1. Hinzufügen einer  **\<Sicherheit >** Element, und legen die `mode` -Attribut `Message`.

1. Innerhalb der  **\<Sicherheit >** Element, Hinzufügen einer  **\<Nachricht >** Element, und legen die `clientCredentialType` -Attribut `Certificate`.

```xml
<wsHttpBinding>
  <binding name="MessageSecurity">
    <security mode="Message">
      <message clientCredentialType="Certificate" />
    </security>
  </binding>
</wsHttpBinding>
```
