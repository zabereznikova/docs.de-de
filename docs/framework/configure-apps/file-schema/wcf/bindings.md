---
title: <bindings>
ms.date: 01/22/2018
ms.assetid: b62cd369-5409-4030-8490-9759a462dd3a
ms.openlocfilehash: fe8f620668e35183890b8bba1f254a74c962f8d3
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2019
ms.locfileid: "74139661"
---
# <a name="bindings"></a>\<Bindungen >

Sie können das `bindings`-Element verwenden, um eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen für Windows Communication Foundation (WCF) zu konfigurieren. Jeder Eintrag ist ein `binding`-Element, das anhand seines eindeutigen `name` identifiziert werden kann. Dienste verwenden Bindungen, indem sie sie mithilfe des `name` verknüpfen. Ab .NET Framework 4 müssen Bindungen und Verhaltensweisen keinen Namen haben. Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).

## <a name="system-provided-bindings"></a>Vom System bereitgestellte Bindungen

Vom System bereitgestellte Bindungen verbergen die Komplexität der WCF-Messagingstapel. Anwendungen, die vom System bereitgestellte Bindungen einsetzen, erfordern keine volle Kontrolle über den Stapel. Diese Attribute, die für jede vom System bereitgestellte Bindung verfügbar gemacht werden, eignen sich am besten für das Verwendungsszenario der Bindungsadressen.

Der Konfigurationsabschnitt für jede vom System bereitgestellte Bindung kann verschiedene Konfigurationen definieren, mit denen die Bindung konfiguriert wird. Jede Konfiguration wird durch einen eindeutigen Namen identifiziert.

Es ist nicht möglich, einer vom System bereitgestellten Bindung Elemente oder Attribute hinzuzufügen. Zu diesem Zweck sollten Sie eine benutzerdefinierte Bindung implementieren, wie im Abschnitt [benutzerdefinierte Bindungen](#custom-bindings) beschrieben. Es ist möglich, eine benutzerdefinierte Bindung zu definieren, die eine vom System bereitgestellte Bindung perfekt imitiert und einige Einstellungen hinzufügt, die von der Benutzeranwendung gesteuert werden sollen.  

Eine Liste der vom System bereitgestellten Bindungen finden Sie unter vom [System bereitgestellte Bindungen](../../../wcf/system-provided-bindings.md).

## <a name="custom-bindings"></a>Benutzerdefinierte Bindungen

Benutzerdefinierte Bindungen stellen Vollzugriff auf den WCF-Messagingstapel bereit. Eine individuelle Bindung definiert den Nachrichtenstapel durch Angeben der Konfigurationselemente für Stapelelemente in der Reihenfolge des Stapels. Jedes Element definiert und konfiguriert ein Element des Stapels. Es muss genau ein `transport`-Element in jeder benutzerdefinierten Bindung geben. Ohne dieses Element ist der Messagingstapel unvollständig.

Die Reihenfolge der Elemente im Stapel ist von Belang, da sie der Reihenfolge entspricht, in der Vorgänge auf die Meldung angewendet werden. Die erforderliche Reihenfolge von Stapelelementen ist folgende:  

1. Transaktionen (optional)  

2. Zuverlässiges Messaging (optional)  

3. Sicherheit (Security, optional)  

4. Encoder  

5. Transport  

 Benutzerdefinierte Bindungen werden durch ihr `name`-Attribut identifiziert. Weitere Informationen zu benutzerdefinierten Bindungen finden Sie unter [benutzerdefinierte Bindungen](../../../wcf/extending/custom-bindings.md).

## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Configuration.BindingsSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.Binding?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType>
- [Bindungen](../../../wcf/bindings.md)
- [Benutzerdefinierte Bindungen](../../../wcf/extending/custom-bindings.md)
- [\<CustomBinding >](custombinding.md)
