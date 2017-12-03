---
title: 4209 - TimeoutOpeningSqlConnection
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f0e56518-9758-41dc-a760-50d1a10fba6e
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 86d971a2e5f1257281c453e7eb0c2dc1755098d8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="4209---timeoutopeningsqlconnection"></a>4209 - TimeoutOpeningSqlConnection
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|4209|  
|Schlüsselwörter|WFInstanceStore|  
|Ebene|Fehler|  
|Kanal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Beschreibung  
 Gibt an, dass ein Timeout aufgetreten ist bei dem Versuch, eine SQL-Verbindung zu öffnen.  
  
## <a name="message"></a>Meldung  
 Timeout beim Versuch, eine SQL-Verbindung zu öffnen. Der Vorgang wurde nicht innerhalb des zugewiesenen Timeouts von %1 abgeschlossen. Die für diesen Vorgang zugewiesene Zeit war möglicherweise ein Teil eines längeren Timeouts.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|Timeout|xs:string|Der Timeoutwert zum Öffnen der SQL-Verbindung.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
