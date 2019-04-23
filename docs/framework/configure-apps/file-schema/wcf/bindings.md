---
title: <bindings>
ms.date: 01/22/2018
ms.assetid: b62cd369-5409-4030-8490-9759a462dd3a
ms.openlocfilehash: 479941593b1abefe637525703140b02917c6692b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59316790"
---
# <a name="bindings"></a>\<bindings>

Sie können die `bindings` Element, um eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen für Windows Communication Foundation (WCF) zu konfigurieren. Jeder Eintrag ist ein `binding`-Element, das anhand seines eindeutigen `name` identifiziert werden kann. Dienste verwenden Bindungen, indem sie sie mithilfe des `name` verknüpfen. Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen. Weitere Informationen zu Standardkonfiguration und zu namenlosen Bindungen und Verhaltensweisen finden Sie unter [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) und [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
## <a name="system-provided-bindings"></a>Vom System bereitgestellte Bindungen
 
 Vom System bereitgestellte Bindungen verbergen die Komplexität der WCF-Messagingstapel. Anwendungen, die vom System bereitgestellte Bindungen einsetzen, erfordern keine volle Kontrolle über den Stapel. Diese Attribute, die für jede vom System bereitgestellte Bindung verfügbar gemacht werden, eignen sich am besten für das Verwendungsszenario der Bindungsadressen.  
  
 Der Konfigurationsabschnitt für jede vom System bereitgestellte Bindung kann verschiedene Konfigurationen definieren, mit denen die Bindung konfiguriert wird. Jede Konfiguration wird durch einen eindeutigen Namen identifiziert.  
  
 Es ist nicht möglich, eine vom System bereitgestellte Bindung Elemente oder Attribute hinzuzufügen. Zu diesem Zweck sollten Sie eine benutzerdefinierte Bindung implementieren, wie beschrieben in der [benutzerdefinierte Bindungen](#custom-bindings) Abschnitt. Es ist möglich, eine benutzerdefinierte Bindung zu definieren, die imitiert eine vom System bereitgestellte Bindung auf perfekte und fügt einige Einstellungen, denen der Benutzer die Anwendung über die Kontrolle haben möchte.  
  
 Eine Liste der vom System bereitgestellten Bindungen, finden Sie unter [System-provided Bindings](../../../../../docs/framework/wcf/system-provided-bindings.md).  
  
## <a name="custom-bindings"></a>Benutzerdefinierte Bindungen

 Benutzerdefinierte Bindungen stellen Vollzugriff auf den WCF-Messagingstapel bereit. Eine individuelle Bindung definiert den Nachrichtenstapel durch Angeben der Konfigurationselemente für Stapelelemente in der Reihenfolge des Stapels. Jedes Element definiert und konfiguriert ein Element des Stapels. Es muss genau ein `transport`-Element in jeder benutzerdefinierten Bindung geben. Ohne dieses Element ist der Messagingstapel unvollständig.  
  
 Die Reihenfolge der Elemente im Stapel ist von Belang, da sie der Reihenfolge entspricht, in der Vorgänge auf die Meldung angewendet werden. Die erforderliche Reihenfolge von Stapelelementen ist folgende:  
  
1. Transaktionen (optional)  
  
2. Zuverlässiges messaging (optional)  
  
3. Sicherheit (Security, optional)  
  
4. Encoder  
  
5. Transport  
  
 Benutzerdefinierte Bindungen werden durch ihr `name`-Attribut identifiziert. Weitere Informationen zu benutzerdefinierten Bindungen finden Sie unter [benutzerdefinierte Bindungen](../../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Configuration.BindingsSection?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.Binding?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType>  
- [Bindungen](../../../../../docs/framework/wcf/bindings.md)  
- [Benutzerdefinierte Bindungen](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
- [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
- [\<binding>](../../../../../docs/framework/misc/binding.md)
