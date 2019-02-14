---
title: 'Vorgehensweise: Steuern der Dienstinstanzierung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e0b12b34-8004-443a-a46d-83a5c00f2601
ms.openlocfilehash: 06324b30d2fbd68a12619375024b9f86019adbb1
ms.sourcegitcommit: af0a22a4eb11bbcd33baec49150d551955b50a16
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2019
ms.locfileid: "56260963"
---
# <a name="how-to-control-service-instancing"></a><span data-ttu-id="e5651-102">Vorgehensweise: Steuern der Dienstinstanzierung</span><span class="sxs-lookup"><span data-stu-id="e5651-102">How to: Control Service Instancing</span></span>
<span data-ttu-id="e5651-103">Durch das Festlegen des Instanzmodus eines Dienstes können Sie angeben, wann ein <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> (und das zugeordnete benutzerdefinierte Dienstobjekt) erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="e5651-103">Setting the instance mode of a service enables you to specify when a <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> (and its associated user-defined service object) is created.</span></span> <span data-ttu-id="e5651-104">Mögliche Modi finden Sie in der <xref:System.ServiceModel.InstanceContextMode>-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="e5651-104">See the <xref:System.ServiceModel.InstanceContextMode> enumeration for the possible modes.</span></span> <span data-ttu-id="e5651-105">Weitere Informationen zu Verhalten finden Sie unter [konfigurieren und Erweitern der Laufzeit mit Verhalten](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="e5651-105">For more information about behaviors, see [Configuring and Extending the Runtime with Behaviors](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).</span></span> <span data-ttu-id="e5651-106">Arbeitsbeispiele finden Sie unter [Verhaltensweisen](../../../../docs/framework/wcf/samples/behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="e5651-106">For working examples, see [Behaviors](../../../../docs/framework/wcf/samples/behaviors.md).</span></span>  
  
### <a name="to-control-the-service-instance-lifetime-using-code"></a><span data-ttu-id="e5651-107">So steuern Sie die Lebensdauer der Dienstinstanz mit Code</span><span class="sxs-lookup"><span data-stu-id="e5651-107">To control the service instance lifetime using code</span></span>  
  
1.  <span data-ttu-id="e5651-108">Fügen Sie das <xref:System.ServiceModel.ServiceBehaviorAttribute> der Dienstklasse hinzu.</span><span class="sxs-lookup"><span data-stu-id="e5651-108">Apply the <xref:System.ServiceModel.ServiceBehaviorAttribute> to the service class.</span></span>  
  
2.  <span data-ttu-id="e5651-109">Legen Sie die <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>-Eigenschaft auf einen der folgenden Werte fest: <xref:System.ServiceModel.InstanceContextMode.PerCall>, <xref:System.ServiceModel.InstanceContextMode.PerSession> oder <xref:System.ServiceModel.InstanceContextMode.Single>.</span><span class="sxs-lookup"><span data-stu-id="e5651-109">Set the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property to one of the following values: <xref:System.ServiceModel.InstanceContextMode.PerCall>, <xref:System.ServiceModel.InstanceContextMode.PerSession>, or <xref:System.ServiceModel.InstanceContextMode.Single>.</span></span>  
  
     [!code-csharp[C_ControlServiceInstancing#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#1)]
     [!code-vb[C_ControlServiceInstancing#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="e5651-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e5651-110">Example</span></span>  
 <span data-ttu-id="e5651-111">Im folgenden Codebeispiel wird die <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>-Eigenschaft des <xref:System.ServiceModel.ServiceBehaviorAttribute>-Attributs auf <xref:System.ServiceModel.InstanceContextMode.PerCall> festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e5651-111">The following code example sets the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property of the <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute to <xref:System.ServiceModel.InstanceContextMode.PerCall>.</span></span>  
  
 [!code-csharp[c_ControlServiceInstancing#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#2)]
 [!code-vb[c_ControlServiceInstancing#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="e5651-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e5651-112">See also</span></span>
- <xref:System.ServiceModel.ServiceBehaviorAttribute>
- <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>
- <xref:System.ServiceModel.InstanceContextMode>
- [<span data-ttu-id="e5651-113">Dienst: Verhaltensbeispiele</span><span class="sxs-lookup"><span data-stu-id="e5651-113">Service: Behaviors Samples</span></span>](../samples/behaviors.md)
