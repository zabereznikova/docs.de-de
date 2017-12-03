---
title: Instanzen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 87423c3de551cb9fbf8c5a7756e2f0f999129a3b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
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
