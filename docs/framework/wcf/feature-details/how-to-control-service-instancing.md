---
title: 'Gewusst wie: Steuern der Dienstinstanzierung'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: e0b12b34-8004-443a-a46d-83a5c00f2601
caps.latest.revision: "19"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 58393f6ed3f14e65b1732c8ec8f90c109be0894a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-control-service-instancing"></a>Gewusst wie: Steuern der Dienstinstanzierung
Durch das Festlegen des Instanzmodus eines Dienstes können Sie angeben, wann ein <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> (und das zugeordnete benutzerdefinierte Dienstobjekt) erstellt wird. Mögliche Modi finden Sie in der <xref:System.ServiceModel.InstanceContextMode>-Enumeration. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Verhalten, finden Sie unter [konfigurieren und Erweitern der Laufzeit mit Verhalten](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md). Funktionierende Beispiele finden Sie in [Verhalten](../../../../docs/framework/wcf/samples/behaviors.md).  
  
### <a name="to-control-the-service-instance-lifetime-using-code"></a>So steuern Sie die Lebensdauer der Dienstinstanz mit Code  
  
1.  Fügen Sie das <xref:System.ServiceModel.ServiceBehaviorAttribute> der Dienstklasse hinzu.  
  
2.  Legen Sie die <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>-Eigenschaft auf einen der folgenden Werte fest: <xref:System.ServiceModel.InstanceContextMode.PerCall>, <xref:System.ServiceModel.InstanceContextMode.PerSession> oder <xref:System.ServiceModel.InstanceContextMode.Single>.  
  
     [!code-csharp[C_ControlServiceInstancing#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#1)]
     [!code-vb[C_ControlServiceInstancing#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#1)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird die <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>-Eigenschaft des <xref:System.ServiceModel.ServiceBehaviorAttribute>-Attributs auf <xref:System.ServiceModel.InstanceContextMode.PerCall> festgelegt.  
  
 [!code-csharp[c_ControlServiceInstancing#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#2)]
 [!code-vb[c_ControlServiceInstancing#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#2)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.ServiceBehaviorAttribute>  
 <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>  
 <xref:System.ServiceModel.InstanceContextMode>  
 [Dienst: Verhalten-Beispiele](http://msdn.microsoft.com/en-us/4e3c6513-a7ff-4b35-8dcf-b5506c6f39a7)
