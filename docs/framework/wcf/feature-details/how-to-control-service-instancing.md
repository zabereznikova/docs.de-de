---
title: "Gewusst wie: Steuern der Dienstinstanzierung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: e0b12b34-8004-443a-a46d-83a5c00f2601
caps.latest.revision: 19
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 19
---
# Gewusst wie: Steuern der Dienstinstanzierung
Durch das Festlegen des Instanzmodus eines Dienstes können Sie angeben, wann ein <xref:System.ServiceModel.InstanceContext?displayProperty=fullName> \(und das zugeordnete benutzerdefinierte Dienstobjekt\) erstellt wird.  Mögliche Modi finden Sie in der <xref:System.ServiceModel.InstanceContextMode>\-Enumeration.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu Verhaltensweisen finden Sie unter [Konfigurieren und Erweitern der Laufzeit mit Verhalten](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).  Arbeitsbeispiele finden Sie unter [Verhalten](../../../../docs/framework/wcf/samples/behaviors.md).  
  
### So steuern Sie die Lebensdauer der Dienstinstanz mit Code  
  
1.  Fügen Sie das <xref:System.ServiceModel.ServiceBehaviorAttribute> der Dienstklasse hinzu.  
  
2.  Legen Sie die <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>\-Eigenschaft auf einen der folgenden Werte fest: <xref:System.ServiceModel.InstanceContextMode>, <xref:System.ServiceModel.InstanceContextMode> oder <xref:System.ServiceModel.InstanceContextMode>.  
  
     [!code-csharp[C_ControlServiceInstancing#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#1)]
     [!code-vb[C_ControlServiceInstancing#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#1)]  
  
## Beispiel  
 Im folgenden Codebeispiel wird die <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>\-Eigenschaft des <xref:System.ServiceModel.ServiceBehaviorAttribute>\-Attributs auf <xref:System.ServiceModel.InstanceContextMode> festgelegt.  
  
 [!code-csharp[c_ControlServiceInstancing#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#2)]
 [!code-vb[c_ControlServiceInstancing#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#2)]  
  
## Siehe auch  
 <xref:System.ServiceModel.ServiceBehaviorAttribute>   
 <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>   
 <xref:System.ServiceModel.InstanceContextMode>   
 [Service: Behaviors Samples](http://msdn.microsoft.com/de-de/4e3c6513-a7ff-4b35-8dcf-b5506c6f39a7)