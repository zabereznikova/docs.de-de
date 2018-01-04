---
title: Sicherheit
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 737ec121-bfc5-4b75-a504-2d53c2c8af39
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 461bc36fd85a158e67c29c3f4ad001997218c824
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="security"></a><span data-ttu-id="a88dd-102">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="a88dd-102">Security</span></span>
<span data-ttu-id="a88dd-103">Der SQL-Workflowinstanzspeicher verwendet die folgenden Datenbanksicherheitsrollen, um den Zugriff auf Instanzstatusinformationen in der Persistenzdatenbank zu sichern.</span><span class="sxs-lookup"><span data-stu-id="a88dd-103">The SQL Workflow Instance Store uses the following database security roles to secure access to instance state information in the persistence database.</span></span>  
  
-   <span data-ttu-id="a88dd-104">**System.Activities.DurableInstancing.InstanceStoreUsers**.</span><span class="sxs-lookup"><span data-stu-id="a88dd-104">**System.Activities.DurableInstancing.InstanceStoreUsers**.</span></span> <span data-ttu-id="a88dd-105">Diese Rolle verfügt über Lese- und Schreibzugriff auf öffentliche Ansichten und Ausführungsrechte auf gespeicherte Prozeduren, die zum Erstellen, Laden und Speichern von Instanzen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a88dd-105">This role has read and write access to public views and execution rights to stored procedures that are involved in creating, loading and saving instances.</span></span>  
  
-   <span data-ttu-id="a88dd-106">**System.Activities.DurableInstancing.InstanceStoreObservers**.</span><span class="sxs-lookup"><span data-stu-id="a88dd-106">**System.Activities.DurableInstancing.InstanceStoreObservers**.</span></span> <span data-ttu-id="a88dd-107">Diese Rolle verfügt über schreibgeschützten Zugriff auf öffentliche Ansichten.</span><span class="sxs-lookup"><span data-stu-id="a88dd-107">This role has read-only access to public views.</span></span>  
  
-   <span data-ttu-id="a88dd-108">**System.Activities.DurableInstancing.WorkflowActivationUsers**.</span><span class="sxs-lookup"><span data-stu-id="a88dd-108">**System.Activities.DurableInstancing.WorkflowActivationUsers**.</span></span> <span data-ttu-id="a88dd-109">Diese Rolle verfügt über die Berechtigung, gespeicherte Prozeduren auszuführen, die am Instanzaktivierungsvorgang beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="a88dd-109">This role has execution rights to stored procedures that are involved in the instance activation process.</span></span> <span data-ttu-id="a88dd-110">Weitere Informationen zur instanzaktivierung finden Sie unter [Instanzaktivierung](../../../docs/framework/windows-workflow-foundation/instance-activation.md).</span><span class="sxs-lookup"><span data-stu-id="a88dd-110">For more information about instance activation, see [Instance Activation](../../../docs/framework/windows-workflow-foundation/instance-activation.md).</span></span> <span data-ttu-id="a88dd-111">Das Benutzerkonto, unter dem ein generischer Host ausgeführt wird (z. B. der Workflowverwaltungsdienst von [!INCLUDE[dublin](../../../includes/dublin-md.md)]), sollte dieser Datenbankrolle hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="a88dd-111">The user account under which a generic host (such as the Workflow Management Service of [!INCLUDE[dublin](../../../includes/dublin-md.md)]) runs should be added to this database role.</span></span>  
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="a88dd-112">Sicherheit für Persistenzspeicher mit Windows Server AppFabric finden Sie unter [Sicherheitskonfiguration für Persistenzspeicher in AppFabric](http://go.microsoft.com/fwlink/?LinkId=201208)</span><span class="sxs-lookup"><span data-stu-id="a88dd-112"> security for persistence stores with Windows Server App Fabric, see [Security Configuration for Persistence Stores in App Fabric](http://go.microsoft.com/fwlink/?LinkId=201208)</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="a88dd-113">Ein Client, der Zugriff auf seine eigenen Instanzdaten im Instanzspeicher hat, kann auch auf alle anderen Instanzen im selben Instanzspeicher zugreifen.</span><span class="sxs-lookup"><span data-stu-id="a88dd-113">A client that has access to its own instance data in the instance store has access to all other instances in the same instance store.</span></span> <span data-ttu-id="a88dd-114">Der Instanzspeicher unterstützt die Angabe von Sicherheitsberechtigungen auf Instanzebene nicht.</span><span class="sxs-lookup"><span data-stu-id="a88dd-114">The instance store does not support specifying security permissions at the instance level.</span></span> <span data-ttu-id="a88dd-115">Sie sollten separate Instanzspeicher erstellen und verschiedene Gruppen/Benutzer zuordnen, um auf andere Speicher zugreifen zu können.</span><span class="sxs-lookup"><span data-stu-id="a88dd-115">You should create separate instance stores and map different groups/users to have access to different stores.</span></span>
