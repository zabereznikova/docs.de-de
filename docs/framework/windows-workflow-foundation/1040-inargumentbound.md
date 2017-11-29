---
title: 1040 - InArgumentBound
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7dfaad1b-36c0-4575-84c1-31d63b0eaf5d
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b3ce0997dcdad4779f87744edf661316b2efa47c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="1040---inargumentbound"></a>1040 - InArgumentBound
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|1040|  
|Schlüsselwörter|WFActivities|  
|Ebene|Ausführlich|  
|Kanal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Beschreibung  
 Gibt an, das ein In-Argument gebunden wurde.  
  
## <a name="message"></a>Meldung  
 Das Argument '%1' der Aktivität '%2', DisplayName: '%3', InstanceId: '%4' wurde mit Wert %5 gebunden.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|InArgument|xs:string|Der Name des InArgument.|  
|Aktivität|xs:string|Der Typname der Aktivität.|  
|DisplayName|xs:string|Der Anzeigename der Aktivität.|  
|InstanceId|xs:string|Die Instanz-ID der Aktivität.|  
|Wert|xs:string|Der an das InArgument gebundene Wert.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
