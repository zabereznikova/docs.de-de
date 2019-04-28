---
title: Vergleichen von Transaktionen in COM+ und ServiceModel
ms.date: 03/30/2017
ms.assetid: e493bcdd-b91a-4486-853f-83dbcd1931b7
ms.openlocfilehash: 4a47fe1686dff2e705b06b001d7d5e4ea6e8c5f2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61857869"
---
# <a name="comparing-transactions-in-com-and-servicemodel"></a>Vergleichen von Transaktionen in COM+ und ServiceModel
In diesem Thema wird erläutert, wie zum Simulieren des Verhaltens eines COM+-transaktionsdiensts mithilfe der Windows Communication Foundation (WCF)-Attribute der <xref:System.ServiceModel> Namespace bietet.  
  
## <a name="emulating-com-using-servicemodel-attributes"></a>Emulieren von COM+ mit ServiceModel-Attributen  
 Die folgende Tabelle enthält eine Gegenüberstellung der <xref:System.EnterpriseServices.TransactionOption> Enumeration, die zum Erstellen einer `EnterpriseServices` Transaktion und die die WCF-Attribute Beziehung der <xref:System.ServiceModel> Namespace bietet.  
  
|COM+-Attribut|WCF-Attribute|  
|---------------------|------------------------------------------------------------------------|  
|RequiresNew|Für <xref:System.ServiceModel.TransactionFlowAttribute> ist <xref:System.ServiceModel.TransactionFlowOption.NotAllowed> festgelegt.<br /><br /> <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> ist `true`.<br /><br /> Das `TransactionFlow`-Attribut im Bindungselement ist `false`.|  
|Erforderlich|Für <xref:System.ServiceModel.TransactionFlowAttribute> ist <xref:System.ServiceModel.TransactionFlowOption.Allowed> festgelegt.<br /><br /> <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> ist `true`.<br /><br /> Das `TransactionFlow`-Attribut im Bindungselement ist `true`.|  
|Unterstützt|Es gibt keine direkte Entsprechung. Übernehmen Sie stattdessen im Allgemeinen das für `Required` angegebene Verhalten.|  
|NotSupported|<xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> ist `false`.<br /><br /> Das `TransactionFlow`-Attribut im Bindungselement ist `false`.|  
|Deaktiviert|Es gibt keine direkte Entsprechung. Übernehmen Sie stattdessen im Allgemeinen das für `NotSupported` angegebene Verhalten.|
