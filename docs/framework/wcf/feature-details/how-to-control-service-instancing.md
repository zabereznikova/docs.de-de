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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3c77cae35abacb780aec86750c37c6ecd91ff370
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-control-service-instancing"></a><span data-ttu-id="683fd-102">Gewusst wie: Steuern der Dienstinstanzierung</span><span class="sxs-lookup"><span data-stu-id="683fd-102">How to: Control Service Instancing</span></span>
<span data-ttu-id="683fd-103">Durch das Festlegen des Instanzmodus eines Dienstes können Sie angeben, wann ein <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> (und das zugeordnete benutzerdefinierte Dienstobjekt) erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="683fd-103">Setting the instance mode of a service enables you to specify when a <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> (and its associated user-defined service object) is created.</span></span> <span data-ttu-id="683fd-104">Mögliche Modi finden Sie in der <xref:System.ServiceModel.InstanceContextMode>-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="683fd-104">See the <xref:System.ServiceModel.InstanceContextMode> enumeration for the possible modes.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="683fd-105">Verhalten, finden Sie unter [konfigurieren und Erweitern der Laufzeit mit Verhalten](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="683fd-105"> behaviors, see [Configuring and Extending the Runtime with Behaviors](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).</span></span> <span data-ttu-id="683fd-106">Funktionierende Beispiele finden Sie in [Verhalten](../../../../docs/framework/wcf/samples/behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="683fd-106">For working examples, see [Behaviors](../../../../docs/framework/wcf/samples/behaviors.md).</span></span>  
  
### <a name="to-control-the-service-instance-lifetime-using-code"></a><span data-ttu-id="683fd-107">So steuern Sie die Lebensdauer der Dienstinstanz mit Code</span><span class="sxs-lookup"><span data-stu-id="683fd-107">To control the service instance lifetime using code</span></span>  
  
1.  <span data-ttu-id="683fd-108">Fügen Sie das <xref:System.ServiceModel.ServiceBehaviorAttribute> der Dienstklasse hinzu.</span><span class="sxs-lookup"><span data-stu-id="683fd-108">Apply the <xref:System.ServiceModel.ServiceBehaviorAttribute> to the service class.</span></span>  
  
2.  <span data-ttu-id="683fd-109">Legen Sie die <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>-Eigenschaft auf einen der folgenden Werte fest: <xref:System.ServiceModel.InstanceContextMode.PerCall>, <xref:System.ServiceModel.InstanceContextMode.PerSession> oder <xref:System.ServiceModel.InstanceContextMode.Single>.</span><span class="sxs-lookup"><span data-stu-id="683fd-109">Set the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property to one of the following values: <xref:System.ServiceModel.InstanceContextMode.PerCall>, <xref:System.ServiceModel.InstanceContextMode.PerSession>, or <xref:System.ServiceModel.InstanceContextMode.Single>.</span></span>  
  
     [!code-csharp[C_ControlServiceInstancing#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#1)]
     [!code-vb[C_ControlServiceInstancing#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="683fd-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="683fd-110">Example</span></span>  
 <span data-ttu-id="683fd-111">Im folgenden Codebeispiel wird die <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>-Eigenschaft des <xref:System.ServiceModel.ServiceBehaviorAttribute>-Attributs auf <xref:System.ServiceModel.InstanceContextMode.PerCall> festgelegt.</span><span class="sxs-lookup"><span data-stu-id="683fd-111">The following code example sets the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property of the <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute to <xref:System.ServiceModel.InstanceContextMode.PerCall>.</span></span>  
  
 [!code-csharp[c_ControlServiceInstancing#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#2)]
 [!code-vb[c_ControlServiceInstancing#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="683fd-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="683fd-112">See Also</span></span>  
 <xref:System.ServiceModel.ServiceBehaviorAttribute>  
 <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>  
 <xref:System.ServiceModel.InstanceContextMode>  
 [<span data-ttu-id="683fd-113">Dienst: Verhalten-Beispiele</span><span class="sxs-lookup"><span data-stu-id="683fd-113">Service: Behaviors Samples</span></span>](http://msdn.microsoft.com/library/4e3c6513-a7ff-4b35-8dcf-b5506c6f39a7)
