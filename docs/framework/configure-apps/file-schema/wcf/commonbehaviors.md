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
# <a name="commonbehaviors"></a>\<commonBehaviors>
Der `commonBehaviors`-Abschnitt kann nur in der Datei machine.config definiert werden. Er definiert zwei untergeordnete Auflistungen mit den Namen `endpointBehaviors` und `serviceBehaviors`.  Jede Auflistung definiert verhaltenselemente für alle WCF-Endpunkten und-Dienste auf dem Computer bzw. Die in `endpointBehaviors` definierten Verhalten beziehen sich nur auf Clients, und die in `serviceBehaviors` definierten Verhalten beziehen sich nur auf Dienste. Wenn ein Verhalten im `commonBehaviors`-Abschnitt und im `behaviors`-Abschnitt definiert ist, wird dem Verhalten im `behaviors`-Abschnitt Priorität eingeräumt.
