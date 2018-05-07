---
title: '&lt;commonBehaviors&gt;'
ms.date: 03/30/2017
ms.assetid: 5260aeca-388d-4e82-94c0-124fa8054cf5
ms.openlocfilehash: 0a9fab68ce240fc37d27c42d9feff969b97f93a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="ltcommonbehaviorsgt"></a>&lt;commonBehaviors&gt;
Der `commonBehaviors`-Abschnitt kann nur in der Datei machine.config definiert werden. Er definiert zwei untergeordnete Auflistungen mit den Namen `endpointBehaviors` und `serviceBehaviors`.  Jede Auflistung definiert verhaltenselemente durch alle WCF-Endpunkten und Diensten auf dem Computer. Die in `endpointBehaviors` definierten Verhalten beziehen sich nur auf Clients, und die in `serviceBehaviors` definierten Verhalten beziehen sich nur auf Dienste. Wenn ein Verhalten im `commonBehaviors`-Abschnitt und im `behaviors`-Abschnitt definiert ist, wird dem Verhalten im `behaviors`-Abschnitt Priorität eingeräumt.
