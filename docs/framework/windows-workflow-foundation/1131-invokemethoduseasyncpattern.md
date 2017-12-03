---
title: 1131 - InvokeMethodUseAsyncPattern
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eca50fa7-5276-4759-ad1c-e490b9bd1f82
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: db529ed413d70165c7813e23ce8f164262c8e16b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="1131---invokemethoduseasyncpattern"></a>1131 - InvokeMethodUseAsyncPattern
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|1131|  
|Schlüsselwörter|WFRuntime|  
|Ebene|Information|  
|Kanal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Beschreibung  
 Während des CacheMetadata-Schritts gibt die InvokeMethod-Aktivität an, dass sie das asynchrone Muster für den Methodenaufruf verwendet.  
  
## <a name="message"></a>Meldung  
 InvokeMethod '%1' - Methode verwendet das asynchrone Muster von '%2' und '%3'.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|InvokeMethod|xs:string|Der Anzeigename der InvokeMethod-Aktivität.|  
|BeginMethod|xs:string|Der Name der Anfangsmethode.|  
|EndMethod|xs:string|Der Name der Endmethode.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
