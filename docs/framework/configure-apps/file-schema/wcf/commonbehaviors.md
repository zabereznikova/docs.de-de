---
title: '&lt;commonBehaviors&gt;'
ms.date: 03/30/2017
ms.assetid: 5260aeca-388d-4e82-94c0-124fa8054cf5
ms.openlocfilehash: 0a9fab68ce240fc37d27c42d9feff969b97f93a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33350321"
---
# <a name="ltcommonbehaviorsgt"></a><span data-ttu-id="15083-102">&lt;commonBehaviors&gt;</span><span class="sxs-lookup"><span data-stu-id="15083-102">&lt;commonBehaviors&gt;</span></span>
<span data-ttu-id="15083-103">Der `commonBehaviors`-Abschnitt kann nur in der Datei machine.config definiert werden.</span><span class="sxs-lookup"><span data-stu-id="15083-103">The `commonBehaviors` section can only be defined in the machine.config file.</span></span> <span data-ttu-id="15083-104">Er definiert zwei untergeordnete Auflistungen mit den Namen `endpointBehaviors` und `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="15083-104">It defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="15083-105">Jede Auflistung definiert verhaltenselemente durch alle WCF-Endpunkten und Diensten auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="15083-105">Each collection defines behavior elements consumed by all WCF endpoints and services on the machine respectively.</span></span> <span data-ttu-id="15083-106">Die in `endpointBehaviors` definierten Verhalten beziehen sich nur auf Clients, und die in `serviceBehaviors` definierten Verhalten beziehen sich nur auf Dienste.</span><span class="sxs-lookup"><span data-stu-id="15083-106">Behaviors defined in `endpointBehaviors` are only applied to clients, and behaviors defined in `serviceBehaviors` are only applied to services.</span></span> <span data-ttu-id="15083-107">Wenn ein Verhalten im `commonBehaviors`-Abschnitt und im `behaviors`-Abschnitt definiert ist, wird dem Verhalten im `behaviors`-Abschnitt Priorität eingeräumt.</span><span class="sxs-lookup"><span data-stu-id="15083-107">If a behavior is defined in both `commonBehaviors` and `behaviors` sections, the behavior in the `behaviors` section is given preference.</span></span>
