---
title: Instanzen
ms.date: 03/30/2017
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
ms.openlocfilehash: e0be9c93b5efe17235dbccd426cdd73fbb739361
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651835"
---
# <a name="instances"></a>Instanzen
Indikatorname: -Instanzen.  
  
## <a name="description"></a>Beschreibung  
 Anzahl an Instanzkontexten, die der Dienst gerade enthält.  
  
 Meistens ist die Anzahl an Instanzkontexten mit der Anzahl an Instanzen identisch. Die folgenden Szenarien sind jedoch Ausnahmen von dieser Regel.  
  
- Eine Dienstmethode ruft die <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A>-Methode explizit auf.  
  
- Ein <xref:System.ServiceModel.ReleaseInstanceMode> wird auf eine <xref:System.ServiceModel.OperationBehaviorAttribute>-Instanz angewendet.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.OperationBehaviorAttribute>
