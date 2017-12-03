---
title: Instance Encoding Option
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 89e4b029-4f68-438c-8117-9b21fe094ef4
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a874f88b787a99af0461ff47c3ae246442af2f19
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="instance-encoding-option"></a><span data-ttu-id="e67f3-102">Instance Encoding Option</span><span class="sxs-lookup"><span data-stu-id="e67f3-102">Instance Encoding Option</span></span>
<span data-ttu-id="e67f3-103">Die **Instance Encoding Option** -Eigenschaft des SQL-Workflowinstanzspeichers können Sie angeben, ob die SQL-Persistenzanbieter die Zustandsinformationen zur Workflowinstanz mithilfe des GZip-Algorithmus vor dem Speichern komprimieren soll die die Informationen in die Persistenzdatenbank.</span><span class="sxs-lookup"><span data-stu-id="e67f3-103">The **Instance Encoding Option** property of the SQL Workflow Instance Store lets you specify whether the SQL persistence provider should compress the workflow instance state information using the GZip algorithm before saving the information into the persistence database.</span></span> <span data-ttu-id="e67f3-104">Die zulässigen Werte für diese Eigenschaft sind: GZIP und None.</span><span class="sxs-lookup"><span data-stu-id="e67f3-104">The allowed values for this property are: GZip and None.</span></span> <span data-ttu-id="e67f3-105">Der Standardwert ist None.</span><span class="sxs-lookup"><span data-stu-id="e67f3-105">The default value is None.</span></span> <span data-ttu-id="e67f3-106">In der folgenden Liste werden diese Optionen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e67f3-106">The following list describes these options.</span></span>  
  
1.  <span data-ttu-id="e67f3-107">**GZip**.</span><span class="sxs-lookup"><span data-stu-id="e67f3-107">**GZip**.</span></span> <span data-ttu-id="e67f3-108">Der Persistenzanbieter codiert die Zustandsinformationen mithilfe des GZip-Algorithmus, bevor die Zustandsinformationen in der Persistenzdatenbank gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="e67f3-108">The persistence provider encodes the state information using the GZip algorithm before persisting the state information in the persistence database.</span></span>  
  
2.  <span data-ttu-id="e67f3-109">**Keine**.</span><span class="sxs-lookup"><span data-stu-id="e67f3-109">**None**.</span></span> <span data-ttu-id="e67f3-110">Der Persistenzanbieter codiert die Zustandsinformationen nicht, bevor die Informationen in der Persistenzdatenbank gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="e67f3-110">The persistence provider does not encode the state information before saving the information into the persistence database.</span></span>  
  
 <span data-ttu-id="e67f3-111">Durch die Codierung der Zustandsinformationen der Workflowinstanz mithilfe von GZip wird in der SQL-Datenbank weniger Speicher und Netzwerkkapazität belegt, wenn sich die Datenbank auf einem anderen Computer im Netzwerk befindet als der Host des Workflowdiensts.</span><span class="sxs-lookup"><span data-stu-id="e67f3-111">Encoding workflow instance state information using the GZip reduces memory consumption in the SQL database and also reduces network consumption if the database resides on a different computer on the network from the computer on which the workflow service host is running.</span></span> <span data-ttu-id="e67f3-112">Allgemein empfiehlt es sich zum Festlegen der **Instance Encoding Option** Eigenschaft, um **keine** Wenn der workflowinstanzzustand klein ist.</span><span class="sxs-lookup"><span data-stu-id="e67f3-112">A general guidance is to set the **Instance Encoding Option** property to **None** if the workflow instance state is small.</span></span>
