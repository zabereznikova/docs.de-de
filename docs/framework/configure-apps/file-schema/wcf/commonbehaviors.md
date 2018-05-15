---
title: '&lt;commonBehaviors&gt;'
ms.date: 03/30/2017
ms.assetid: 5260aeca-388d-4e82-94c0-124fa8054cf5
ms.openlocfilehash: aaf89f73b6de250aaa572b8fef31e5a1ebd5482b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltcommonbehaviorsgt"></a><span data-ttu-id="20498-102">&lt;commonBehaviors&gt;</span><span class="sxs-lookup"><span data-stu-id="20498-102">&lt;commonBehaviors&gt;</span></span>
<span data-ttu-id="20498-103">Der `commonBehaviors`-Abschnitt kann nur in der Datei machine.config definiert werden.</span><span class="sxs-lookup"><span data-stu-id="20498-103">The `commonBehaviors` section can only be defined in the machine.config file.</span></span> <span data-ttu-id="20498-104">Er definiert zwei untergeordnete Auflistungen mit den Namen `endpointBehaviors` und `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="20498-104">It defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="20498-105">Jede Auflistung definiert Verhaltenselemente, die von allen [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]-Endpunkten und -Diensten auf dem Computer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="20498-105">Each collection defines behavior elements consumed by all [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] endpoints and services on the machine respectively.</span></span> <span data-ttu-id="20498-106">Die in `endpointBehaviors` definierten Verhalten beziehen sich nur auf Clients, und die in `serviceBehaviors` definierten Verhalten beziehen sich nur auf Dienste.</span><span class="sxs-lookup"><span data-stu-id="20498-106">Behaviors defined in `endpointBehaviors` are only applied to clients, and behaviors defined in `serviceBehaviors` are only applied to services.</span></span> <span data-ttu-id="20498-107">Wenn ein Verhalten im `commonBehaviors`-Abschnitt und im `behaviors`-Abschnitt definiert ist, wird dem Verhalten im `behaviors`-Abschnitt Priorität eingeräumt.</span><span class="sxs-lookup"><span data-stu-id="20498-107">If a behavior is defined in both `commonBehaviors` and `behaviors` sections, the behavior in the `behaviors` section is given preference.</span></span>
