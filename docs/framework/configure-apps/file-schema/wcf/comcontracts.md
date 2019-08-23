---
title: <comContracts>
ms.date: 03/30/2017
ms.assetid: 42e74148-223d-4888-a8ed-1d928527eb09
ms.openlocfilehash: d061d48374a8745dc61e1ca156e4fcbbccee5ef7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919472"
---
# <a name="comcontracts"></a>\<comContracts>
Der `comContracts`-Konfigurationsabschnitt enthält Elemente, mit denen Sie verschiedene Eigenschaften eines COM+-Integrationsdienstvertrags angeben können.  
  
## <a name="specifying-namespace-and-contract"></a>Angeben von Namespace und Vertrag  
 Com+-Integrations Dienstverträge sind zurzeit auf `http://tempuri.org` den Namespace beschränkt, und der Vertrags Name wird von der unterstützenden com-Schnittstelle abgeleitet. Sie können Alternativen aber angeben, indem Sie den Abschnitt `comContracts` in der Konfigurationsdatei verwenden.  
  
 Sie können z.&#160;B. folgende Konfiguration zum Angeben des Namespaces und Namens des Dienstvertrags sowie als Option zum Erzwingen sitzungsbasierter Bindungen verwenden.  
  
```xml  
<comContracts>
  <comContract contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"
               namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"
               name="_Broker"
               requireSession="true">
  </comContract>
</comContracts>
```  
  
 Wenn der Dienst initialisiert wird, werden die angegebenen Namespaces und Vertragsnamen auf die generierten Dienstbeschreibungen angewendet.  
  
 Wenn dieser Abschnitt leer ist, wendet die Dienstinitialisierung einen standardmäßigen Namespace und Vertragsnamen aus der unterstützenden COM-Schnittstellen-ID an.  
  
 Darüber hinaus können Sie das [ \<exposedMethod](exposedmethod.md) -Element >-Element verwenden, um com+-Methoden anzugeben, die verfügbar gemacht werden, wenn die Schnittstelle für eine COM+-Komponente als Webdienst verfügbar gemacht wird. Sie können auch die [ \<persistabletypes->](persistabletypes.md) verwenden, um dauerhafte Typen anzugeben, die bei der Integration verwendet werden. Schließlich können Sie das [ \<UserDefinedType](userdefinedtype.md) -Element >-Element verwenden, um benutzerdefinierte Typen (User Defined Types, UDT) einzuschließen, die in den Dienstvertrag eingeschlossen werden sollen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [\<exposedMethod>](exposedmethod.md)
- [\<persistableTypes>](persistabletypes.md)
- [\<userDefinedType>](userdefinedtype.md)
- [\<comContract>](comcontract.md)
- [Integrieren von COM+-Anwendungen](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [Vorgehensweise: Konfigurieren der com+-Dienst Einstellungen](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
