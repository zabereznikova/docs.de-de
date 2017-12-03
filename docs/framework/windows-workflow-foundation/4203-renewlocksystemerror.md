---
title: 4203 - RenewLockSystemError
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6ec9ec6f-4ae2-45cf-b99b-02cdb9dc9ec9
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9c2214ec48f0c1cba1e3aacad0eaa5a29625f9c4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="4203---renewlocksystemerror"></a>4203 - RenewLockSystemError
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|4203|  
|Schlüsselwörter|WFInstanceStore|  
|Ebene|Fehler|  
|Kanal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Beschreibung  
 Gibt an, dass der SQL-Anbieter die Sperre nicht verlängern konnte, da die Gültigkeit der Sperre bereits abgelaufen war oder der Sperrenbesitzer gelöscht wurde. Das SqlWorkflowInstanceStore wird abgebrochen.  
  
## <a name="message"></a>Meldung  
 Die Gültigkeit der Sperre konnte nicht verlängert werden. Die Sperre ist abgelaufen, oder der Besitzer wurde gelöscht. SqlWorkflowInstanceStore wird abgebrochen.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
