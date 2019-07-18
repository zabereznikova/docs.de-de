---
title: 206 - ErrorHandlerInvoked
ms.date: 03/30/2017
ms.assetid: 97340f4d-4e09-4e42-a17a-982b3868dbcf
ms.openlocfilehash: 40a92d77c57728249569a854eab8767ff371bca2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781926"
---
# <a name="206---errorhandlerinvoked"></a>206 - ErrorHandlerInvoked
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|206|  
|Schlüsselwörter|Troubleshooting, ServiceModel|  
|Ebene|Information|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Beschreibung  
 Dieses Ereignis wird ausgegeben, nachdem ein `ErrorHandler` die Gelegenheit hatte, eine Ausnahme zu behandeln, die während eines Dienstvorgangs aufgetreten ist.  
  
## <a name="message"></a>Meldung  
 Der Verteiler hat einen ErrorHandler vom Typ "%1" mit einer Ausnahme vom Typ "%3" aufgerufen. ErrorHandled == '%2'.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|TypeName|`xs:string`|Der CLR-FullName des aufgerufenen `ErrorHandler`-Typs.|  
|Handled|`xs:unsignedByte`|`true`, wenn der Fehlerhandler den Fehler behandelt hat, andernfalls `false`.|  
|ExceptionTypeName|`xs:string`|Der CLR-FullName der Ausnahme, die behandelt wurde.|  
|HostReference|`xs:string`|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig. Das Format ist definiert als "Website Namen virtueller Anwendungspfad&#124;virtueller Dienstpfad&#124;ServiceName". Beispiel: "Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
