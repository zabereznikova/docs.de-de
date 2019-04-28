---
title: 4209 - TimeoutOpeningSqlConnection
ms.date: 03/30/2017
ms.assetid: f0e56518-9758-41dc-a760-50d1a10fba6e
ms.openlocfilehash: d61d710959f99dbc8a91441766a690eb7e9a365c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774269"
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
