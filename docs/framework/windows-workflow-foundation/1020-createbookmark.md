---
title: 1020 - CreateBookmark
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4bee948d-816f-4803-85cc-3883b5e23d10
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7c47a5464222d12c1dba717e24606e5614e392f1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="1020---createbookmark"></a>1020 - CreateBookmark
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|1020|  
|Schlüsselwörter|WFRuntime|  
|Ebene|Ausführlich|  
|Kanal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Beschreibung  
 Gibt an, dass für eine Aktivität ein Lesezeichen erstellt wurde.  
  
## <a name="message"></a>Meldung  
 Ein Lesezeichen erstellt wurde, für die Aktivität '%1', DisplayName: '%2', InstanceId: "%3".  BookmarkName: %4, BookmarkScope: %5.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|Aktivität|xs:string|Der Typname der Aktivität.|  
|DisplayName|xs:string|Der Anzeigename der Aktivität.|  
|InstanceId|xs:string|Die Instanz-ID der Aktivität.|  
|BookmarkName|xs:string|Der Name des Lesezeichens.|  
|BookmarkScope|xs:string|Der Bereich des Lesezeichens.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
