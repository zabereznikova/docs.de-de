---
title: Vergleichen von Transaktionen in COM+ und ServiceModel
ms.date: 03/30/2017
ms.assetid: e493bcdd-b91a-4486-853f-83dbcd1931b7
ms.openlocfilehash: 30ecbd374e909141dbc944740f90c1b41ac44ed2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96264907"
---
# <a name="comparing-transactions-in-com-and-servicemodel"></a>Vergleichen von Transaktionen in COM+ und ServiceModel

In diesem Thema wird erläutert, wie das Verhalten eines transaktionalen com+-diensdienstanbieter mithilfe der vom Namespace bereitgestellten Windows Communication Foundation (WCF)-Attribute simuliert wird <xref:System.ServiceModel> .  
  
## <a name="emulating-com-using-servicemodel-attributes"></a>Emulieren von COM+ mit ServiceModel-Attributen  

 In der folgenden Tabelle <xref:System.EnterpriseServices.TransactionOption> wird die-Enumeration, die zum Erstellen einer Transaktion verwendet wird, `EnterpriseServices` und ihre Korrelation mit den WCF-Attributen, die der <xref:System.ServiceModel> Namespace bereitstellt, verglichen  
  
|COM+-Attribut|WCF-Attribute|  
|---------------------|------------------------------------------------------------------------|  
|RequiresNew|Für <xref:System.ServiceModel.TransactionFlowAttribute> ist <xref:System.ServiceModel.TransactionFlowOption.NotAllowed> festgelegt.<br /><br /> <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> ist `true`.<br /><br /> Das `TransactionFlow`-Attribut im Bindungselement ist `false`.|  
|Erforderlich|Für <xref:System.ServiceModel.TransactionFlowAttribute> ist <xref:System.ServiceModel.TransactionFlowOption.Allowed> festgelegt.<br /><br /> <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> ist `true`.<br /><br /> Das `TransactionFlow`-Attribut im Bindungselement ist `true`.|  
|Unterstützt|Es gibt keine direkte Entsprechung. Übernehmen Sie stattdessen im Allgemeinen das für `Required` angegebene Verhalten.|  
|NotSupported|<xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> ist `false`<br /><br /> Das `TransactionFlow`-Attribut im Bindungselement ist `false`.|  
|Disabled|Es gibt keine direkte Entsprechung. Übernehmen Sie stattdessen im Allgemeinen das für `NotSupported` angegebene Verhalten.|
