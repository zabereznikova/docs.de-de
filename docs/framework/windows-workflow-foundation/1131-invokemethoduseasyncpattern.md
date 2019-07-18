---
title: 1131 - InvokeMethodUseAsyncPattern
ms.date: 03/30/2017
ms.assetid: eca50fa7-5276-4759-ad1c-e490b9bd1f82
ms.openlocfilehash: 150973935d12455aa671043a619fbd6fd7e77425
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62009954"
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
