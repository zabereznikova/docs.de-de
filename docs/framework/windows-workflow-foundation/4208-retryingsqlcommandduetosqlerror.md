---
title: 4208 - RetryingSqlCommandDueToSqlError
ms.date: 03/30/2017
ms.assetid: a8e6483a-a6e4-4bbf-82ec-cd8b6e711aad
ms.openlocfilehash: a97336f12ccfe041b79328bcb48f4e7214a05b63
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774295"
---
# <a name="4208---retryingsqlcommandduetosqlerror"></a>4208 - RetryingSqlCommandDueToSqlError
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|4208|  
|Schlüsselwörter|WFInstanceStore|  
|Ebene|Information|  
|Kanal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Beschreibung  
 Gibt an, dass der SQL-Anbieter einen SQL-Befehl aufgrund eines SQL-Fehlers wiederholt.  
  
## <a name="message"></a>Meldung  
 Wiederholungsversuch für einen SQL-Befehl aufgrund von SQL-Fehlernummer %1.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|ErrorNumber|xs:string|Die SQL-Fehlernummer.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
