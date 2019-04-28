---
title: <commonBehaviors>
ms.date: 03/30/2017
ms.assetid: 5260aeca-388d-4e82-94c0-124fa8054cf5
ms.openlocfilehash: 73bf759fd3dfa87398aa74de93160a4ffce08eba
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704361"
---
# <a name="commonbehaviors"></a><span data-ttu-id="774e6-101">\<commonBehaviors></span><span class="sxs-lookup"><span data-stu-id="774e6-101">\<commonBehaviors></span></span>
<span data-ttu-id="774e6-102">Der `commonBehaviors`-Abschnitt kann nur in der Datei machine.config definiert werden.</span><span class="sxs-lookup"><span data-stu-id="774e6-102">The `commonBehaviors` section can only be defined in the machine.config file.</span></span> <span data-ttu-id="774e6-103">Er definiert zwei untergeordnete Auflistungen mit den Namen `endpointBehaviors` und `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="774e6-103">It defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="774e6-104">Jede Auflistung definiert verhaltenselemente für alle WCF-Endpunkten und-Dienste auf dem Computer bzw.</span><span class="sxs-lookup"><span data-stu-id="774e6-104">Each collection defines behavior elements consumed by all WCF endpoints and services on the machine respectively.</span></span> <span data-ttu-id="774e6-105">Die in `endpointBehaviors` definierten Verhalten beziehen sich nur auf Clients, und die in `serviceBehaviors` definierten Verhalten beziehen sich nur auf Dienste.</span><span class="sxs-lookup"><span data-stu-id="774e6-105">Behaviors defined in `endpointBehaviors` are only applied to clients, and behaviors defined in `serviceBehaviors` are only applied to services.</span></span> <span data-ttu-id="774e6-106">Wenn ein Verhalten im `commonBehaviors`-Abschnitt und im `behaviors`-Abschnitt definiert ist, wird dem Verhalten im `behaviors`-Abschnitt Priorität eingeräumt.</span><span class="sxs-lookup"><span data-stu-id="774e6-106">If a behavior is defined in both `commonBehaviors` and `behaviors` sections, the behavior in the `behaviors` section is given preference.</span></span>
