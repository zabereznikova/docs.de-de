---
title: 1020 - CreateBookmark
ms.date: 03/30/2017
ms.assetid: 4bee948d-816f-4803-85cc-3883b5e23d10
ms.openlocfilehash: 8c9c20fd4fb74f80779c1d2ef8f29ac3d44050d9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275374"
---
# <a name="1020---createbookmark"></a>1020 - CreateBookmark

## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|id|1020|  
|Keywords|WFRuntime|  
|Ebene|Ausführlich|  
|Kanal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>BESCHREIBUNG  

 Gibt an, dass für eine Aktivität ein Lesezeichen erstellt wurde.  
  
## <a name="message"></a>`Message`  

 Für die Aktivität ' %1 ', Display Name: ' %2 ', InstanceId: ' %3 ' wurde ein Lesezeichen erstellt.  BookmarkName: %4, BookmarkScope: %5.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|BESCHREIBUNG|  
|--------------------|--------------------|-----------------|  
|Aktivität|xs:string|Der Typname der Aktivität.|  
|DisplayName|xs:string|Der Anzeigename der Aktivität.|  
|InstanceId|xs:string|Die Instanz-ID der Aktivität.|  
|BookmarkName|xs:string|Der Name des Lesezeichens.|  
|BookmarkScope|xs:string|Der Bereich des Lesezeichens.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
