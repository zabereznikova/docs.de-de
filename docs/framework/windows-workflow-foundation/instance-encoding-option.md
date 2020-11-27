---
title: Instance Encoding Option
ms.date: 03/30/2017
ms.assetid: 89e4b029-4f68-438c-8117-9b21fe094ef4
ms.openlocfilehash: 416394eb346a7c82385da32a89bd54179b255cd4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279895"
---
# <a name="instance-encoding-option"></a><span data-ttu-id="e216e-102">Instance Encoding Option</span><span class="sxs-lookup"><span data-stu-id="e216e-102">Instance Encoding Option</span></span>

<span data-ttu-id="e216e-103">Mit der Eigenschaft **instance Encoding Option** des SQL-workflowinstanzspeichers können Sie angeben, ob der SQL-Persistenzanbieter die Zustandsinformationen der Workflow Instanz mithilfe des gzip-Algorithmus komprimieren soll, bevor die Informationen in der Persistenzdatenbank gespeichert</span><span class="sxs-lookup"><span data-stu-id="e216e-103">The **Instance Encoding Option** property of the SQL Workflow Instance Store lets you specify whether the SQL persistence provider should compress the workflow instance state information using the GZip algorithm before saving the information into the persistence database.</span></span> <span data-ttu-id="e216e-104">Die zulässigen Werte für diese Eigenschaft sind: GZIP und None.</span><span class="sxs-lookup"><span data-stu-id="e216e-104">The allowed values for this property are: GZip and None.</span></span> <span data-ttu-id="e216e-105">Der Standardwert lautet „Keine“.</span><span class="sxs-lookup"><span data-stu-id="e216e-105">The default value is None.</span></span> <span data-ttu-id="e216e-106">In der folgenden Liste werden diese Optionen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e216e-106">The following list describes these options.</span></span>  
  
1. <span data-ttu-id="e216e-107">**Gzip**.</span><span class="sxs-lookup"><span data-stu-id="e216e-107">**GZip**.</span></span> <span data-ttu-id="e216e-108">Der Persistenzanbieter codiert die Zustandsinformationen mithilfe des GZip-Algorithmus, bevor die Zustandsinformationen in der Persistenzdatenbank gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="e216e-108">The persistence provider encodes the state information using the GZip algorithm before persisting the state information in the persistence database.</span></span>  
  
2. <span data-ttu-id="e216e-109">**None** (Keine).</span><span class="sxs-lookup"><span data-stu-id="e216e-109">**None**.</span></span> <span data-ttu-id="e216e-110">Der Persistenzanbieter codiert die Zustandsinformationen nicht, bevor die Informationen in der Persistenzdatenbank gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="e216e-110">The persistence provider does not encode the state information before saving the information into the persistence database.</span></span>  
  
 <span data-ttu-id="e216e-111">Durch die Codierung der Zustandsinformationen der Workflowinstanz mithilfe von GZip wird in der SQL-Datenbank weniger Speicher und Netzwerkkapazität belegt, wenn sich die Datenbank auf einem anderen Computer im Netzwerk befindet als der Host des Workflowdiensts.</span><span class="sxs-lookup"><span data-stu-id="e216e-111">Encoding workflow instance state information using the GZip reduces memory consumption in the SQL database and also reduces network consumption if the database resides on a different computer on the network from the computer on which the workflow service host is running.</span></span> <span data-ttu-id="e216e-112">Eine allgemeine Anleitung besteht darin, die Eigenschaft **instance Encoding Option** auf **None** festzulegen, wenn der Zustand der workflowinstanzinstanz gering ist.</span><span class="sxs-lookup"><span data-stu-id="e216e-112">A general guidance is to set the **Instance Encoding Option** property to **None** if the workflow instance state is small.</span></span>
