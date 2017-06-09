---
title: "Vergleichen von Transaktionen in COM+ und ServiceModel | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e493bcdd-b91a-4486-853f-83dbcd1931b7
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Vergleichen von Transaktionen in COM+ und ServiceModel
In diesem Thema wird das Simulieren des Verhaltens eines COM\+\-Transaktionsdienstes mithilfe der [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Attribute, die der <xref:System.ServiceModel>\-Namespace bereitstellt, beschrieben.  
  
## Emulieren von COM\+ mit ServiceModel\-Attributen  
 In der folgenden Tabelle wird die <xref:System.EnterpriseServices.TransactionOption>\-Enumeration, die zum Erstellen einer `EnterpriseServices`\-Transaktion verwendet wird, und die Beziehung zu den [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Attributen, die der <xref:System.ServiceModel>\-Namespace bereitstellt, verglichen.  
  
|COM\+\-Attribut|[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Attribute|  
|---------------------|------------------------------------------------------------------------|  
|RequiresNew|Für <xref:System.ServiceModel.TransactionFlowAttribute> ist <xref:System.ServiceModel.TransactionFlowOption> festgelegt.<br /><br /> <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> ist `true`.<br /><br /> Das `TransactionFlow`\-Attribut im Bindungselement ist `false`.|  
|Erforderlich|Für <xref:System.ServiceModel.TransactionFlowAttribute> ist <xref:System.ServiceModel.TransactionFlowOption> festgelegt.<br /><br /> <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> ist `true`.<br /><br /> Das `TransactionFlow`\-Attribut im Bindungselement ist `true`.|  
|Unterstützt|Es gibt keine direkte Entsprechung.  Übernehmen Sie stattdessen im Allgemeinen das für `Required` angegebene Verhalten.|  
|NotSupported|<xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> ist `false`.<br /><br /> Das `TransactionFlow`\-Attribut im Bindungselement ist `false`.|  
|Deaktiviert|Es gibt keine direkte Entsprechung.  Übernehmen Sie stattdessen im Allgemeinen das für `NotSupported` angegebene Verhalten.|