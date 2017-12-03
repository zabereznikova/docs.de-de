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
ms.openlocfilehash: 1a0837caa668d6395bf1551c319781934bcfecc1
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
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
