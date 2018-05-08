---
title: 1035 - RuntimeTransactionSet
ms.date: 03/30/2017
ms.assetid: 03b37de9-778c-4beb-b0e3-de73ece6088e
ms.openlocfilehash: 198e11dd94b0ad5cdc1e01c3611280754ca081d3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="1035---runtimetransactionset"></a>1035 - RuntimeTransactionSet
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|1035|  
|Schlüsselwörter|WFRuntime|  
|Ebene|Ausführlich|  
|Kanal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Beschreibung  
 Gibt an, dass eine Aktivität die Laufzeittransaktion festgelegt hat.  
  
## <a name="message"></a>Meldung  
 Die laufzeittransaktion festgelegt wurde, von der Aktivität '%1', DisplayName: '%2', InstanceId: "%3".  Ausführung isoliert Aktivität '%4', DisplayName: '%5', InstanceId: '%6'.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|Aktivität|xs:string|Der Typname der Aktivität.|  
|DisplayName|xs:string|Der Anzeigename der Aktivität.|  
|InstanceId|xs:string|Die Instanz-ID der Aktivität.|  
|IsolatedActivity|xs:string|Der Typname der Aktivität, für die die Transaktion isoliert ist.|  
|IsolatedActivityDisplayName|xs:string|Der Anzeigename der Aktivität, für die die Transaktion isoliert ist.|  
|IsolatedActivityInstanceId|xs:string|Die Instanz-ID der Aktivität, für die die Transaktion isoliert ist.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
