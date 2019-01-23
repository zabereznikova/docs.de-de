---
title: Instanzen
ms.date: 03/30/2017
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
ms.openlocfilehash: 1b2801b5df3a5d2ca6d7fd03299ecdf4b7df426a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54520266"
---
# <a name="instances"></a>Instanzen
Indikatorname: -Instanzen.  
  
## <a name="description"></a>Beschreibung  
 Anzahl an Instanzkontexten, die der Dienst gerade enthält.  
  
 Meistens ist die Anzahl an Instanzkontexten mit der Anzahl an Instanzen identisch. Die folgenden Szenarien sind jedoch Ausnahmen von dieser Regel.  
  
-   Eine Dienstmethode ruft die <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A>-Methode explizit auf.  
  
-   Ein <xref:System.ServiceModel.ReleaseInstanceMode> wird auf eine <xref:System.ServiceModel.OperationBehaviorAttribute>-Instanz angewendet.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.ServiceModel.OperationBehaviorAttribute>
