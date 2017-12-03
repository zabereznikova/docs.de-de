---
title: '&lt;comContracts&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 42e74148-223d-4888-a8ed-1d928527eb09
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1be69cea2b6e47ae10652e3d59936836bb6d1653
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltcomcontractsgt"></a>&lt;comContracts&gt;
Der `comContracts`-Konfigurationsabschnitt enthält Elemente, mit denen Sie verschiedene Eigenschaften eines COM+-Integrationsdienstvertrags angeben können.  
  
## <a name="specifying-namespace-and-contract"></a>Angeben von Namespace und Vertrag  
 COM+-integrationsdienstverträge sind aktuell auf den Namespace "http://tempuri.org" beschränkt und Vertragsname wird von der unterstützenden COM-Schnittstelle abgeleitet. Sie können Alternativen aber angeben, indem Sie den Abschnitt `comContracts` in der Konfigurationsdatei verwenden.  
  
 Sie können z.&#160;B. folgende Konfiguration zum Angeben des Namespaces und Namens des Dienstvertrags sowie als Option zum Erzwingen sitzungsbasierter Bindungen verwenden.  
  
```xml  
<comContracts>  
  <comContract  
      contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"  
      namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"  
      name="_Broker"  
      requireSession="true">  
  </comContract>  
</comContracts>  
```  
  
 Wenn der Dienst initialisiert wird, werden die angegebenen Namespaces und Vertragsnamen auf die generierten Dienstbeschreibungen angewendet.  
  
 Wenn dieser Abschnitt leer ist, wendet die Dienstinitialisierung einen standardmäßigen Namespace und Vertragsnamen aus der unterstützenden COM-Schnittstellen-ID an.  
  
 Darüber hinaus können Sie die [ \<ExposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) Element COM+-Methoden angeben, die verfügbar gemacht werden, wenn die Schnittstelle für eine COM+-Komponente als Webdienst verfügbar gemacht wird. Sie können auch die [ \<PersistableTypes >](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md) an dauerhaften Typen, die bei der Integration verwendet. Schließlich können Sie die [ \<UserDefinedType >](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md) Element zum Einschließen von benutzerdefinierten Typen (UDT), die im Dienstvertrag enthalten sein sollen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.ComContractElementCollection>  
 <xref:System.ServiceModel.Configuration.ComContractElement>  
 [\<ExposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md)  
 [\<PersistableTypes >](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)  
 [\<UserDefinedType >](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md)  
 [\<ComContract >](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontract.md)  
 [Integrieren von COM+-Anwendungen](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [Vorgehensweise: Konfigurieren von COM+-Diensteinstellungen](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
