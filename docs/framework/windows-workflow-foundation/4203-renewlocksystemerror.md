---
title: 4203 - RenewLockSystemError
ms.date: 03/30/2017
ms.assetid: 6ec9ec6f-4ae2-45cf-b99b-02cdb9dc9ec9
ms.openlocfilehash: 984f7ddae8797cba17753a618d0820d21bde5eef
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774347"
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
