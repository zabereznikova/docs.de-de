---
title: Instanzen
ms.date: 03/30/2017
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
ms.openlocfilehash: 668cfb3026b9ab7259665f5e53873a512b1e2238
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59118988"
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
