---
title: 3551 - BufferOutOfOrderMessageNoBookmark
ms.date: 03/30/2017
ms.assetid: 7930d6c4-c843-4a83-933a-cecd71b80d1e
ms.openlocfilehash: 5e6a5f9d21435fee8309bd222443407e50ec2cee
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263606"
---
# <a name="3551---bufferoutofordermessagenobookmark"></a>3551 - BufferOutOfOrderMessageNoBookmark

## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|id|3551|  
|Keywords|WFServices|  
|Ebene|Information|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>BESCHREIBUNG  

 Gibt an, dass eine Lesezeichenwiederaufnahme fehlgeschlagen ist. Der gepufferte Empfangsvorgang wird wiederholt, wenn die Dienstinstanz bereit ist, diesen Vorgang zu verarbeiten.  
  
## <a name="message"></a>`Message`  

 Vorgang '%2' der Dienstinstanz '%1' kann derzeit nicht ausgeführt werden. Es wird ein weiterer Versuch unternommen, wenn die Dienstinstanz bereit ist, diesen Vorgang zu verarbeiten.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|BESCHREIBUNG|  
|--------------------|--------------------|-----------------|  
|Vorgangsname|xs:string|Der Name des Vorgangs.|  
|ServiceInstanceId|xs:string|Die ID der Dienstinstanz.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
