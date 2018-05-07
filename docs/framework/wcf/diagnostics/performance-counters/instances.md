---
title: Instanzen
ms.date: 03/30/2017
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
ms.openlocfilehash: a95acf8e775e0802dc0ed781c562fa6373995a70
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="instances"></a>Instanzen
Indikatorname: Instanzen.  
  
## <a name="description"></a>Beschreibung  
 Anzahl an Instanzkontexten, die der Dienst gerade enthält.  
  
 Meistens ist die Anzahl an Instanzkontexten mit der Anzahl an Instanzen identisch. Die folgenden Szenarien sind jedoch Ausnahmen von dieser Regel.  
  
-   Eine Dienstmethode ruft die <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A>-Methode explizit auf.  
  
-   Ein <xref:System.ServiceModel.ReleaseInstanceMode> wird auf eine <xref:System.ServiceModel.OperationBehaviorAttribute>-Instanz angewendet.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.OperationBehaviorAttribute>
