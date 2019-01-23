---
title: '&lt;binding&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 666183d6-4d1f-45c7-ac64-bdf93ee8f36f
ms.openlocfilehash: fb4fafda31205e2ce5efd01ab265fcacfa70bdf6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54539193"
---
# <a name="ltbindinggt"></a>&lt;binding&gt;
Sie können das `binding`-Element zum Konfigurieren verschiedener Typen von vordefinierten Bindungen verwenden, die von Windows Communication Foundation (WCF) bereitgestellt werden.  
  
## <a name="system-provided-binding"></a>Vom System bereitgestellte Bindung  
 Vom System bereitgestellte Bindungen verbergen die Komplexität der WCF-Messagingstapel. Anwendungen, die vom System bereitgestellte Bindungen einsetzen, erfordern keine volle Kontrolle über den Stapel. Diese Attribute, die für jede vom System bereitgestellte Bindung verfügbar gemacht werden, eignen sich am besten für das Verwendungsszenario der Bindungsadressen.  
  
 Der Konfigurationsabschnitt für jede vom System bereitgestellte Bindung kann verschiedene Konfigurationen definieren, mit denen die Bindung konfiguriert wird. Jede Konfiguration wird durch einen eindeutigen Namen identifiziert.  
  
 Es ist nicht möglich, Elemente oder Attribute einer vom System bereitgestellten Bindung hinzuzufügen. Um dies durchzuführen, müssen Sie eine benutzerdefinierte Bindung definieren, wie im Abschnitt "Benutzerdefinierte Bindung" dieses Themas beschrieben. Es ist möglich, eine benutzerdefinierte Bindung zu definieren, die eine vom System bereitgestellte Bindung auf perfekte Weise imitiert und einige Einstellungen hinzufügt, über die die Benutzeranwendung die Kontrolle haben möchte.  
  
## <a name="custom-binding"></a>Benutzerdefinierte Bindung  
 Benutzerdefinierte Bindungen stellen Vollzugriff auf den WCF-Messagingstapel bereit. Eine individuelle Bindung definiert den Nachrichtenstapel durch Angeben der Konfigurationselemente für Stapelelemente in der Reihenfolge des Stapels. Jedes Element definiert und konfiguriert das eine Element des Stapels. Es muss genau ein `transport`-Element in jeder benutzerdefinierten Bindung geben. Ohne dieses Element ist der Messagingstapel unvollständig.  
  
 Die Reihenfolge der Elemente im Stapel ist von Belang, da sie der Reihenfolge entspricht, in der Vorgänge auf die Meldung angewendet werden. Die empfohlene Reihenfolge von Stapelelementen ist folgende:  
  
1.  Transaktionen (optional)  
  
2.  Zuverlässiges Messaging (optional)  
  
3.  Sicherheit (Security, optional)  
  
4.  Encoder  
  
5.  Transport  
  
 Benutzerdefinierte Bindungen werden durch ihr `name`-Attribut identifiziert.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.ServiceModel.Configuration.BindingsSection>
- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- [Bindungen](../../../docs/framework/wcf/bindings.md)
- [Benutzerdefinierte Bindungen](../../../docs/framework/wcf/extending/custom-bindings.md)
- [\<customBinding>](../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
