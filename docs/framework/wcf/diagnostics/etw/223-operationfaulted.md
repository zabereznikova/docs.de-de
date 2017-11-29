---
title: 223 - OperationFaulted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2f7d89d7-3a6a-40fe-9610-5424eb6bbf61
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a04ed11db97d02a90e016ee1825b303375a23412
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="223---operationfaulted"></a>223 - OperationFaulted
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|223|  
|Stichwörter|EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel|  
|Ebene|Warnung|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Beschreibung  
 Dieses Ereignis wird ausgegeben, wenn beim Aufrufen der Methode der standardmäßige `OperationInvoker` des Dienstmodells auf eine Ausnahme gestoßen ist, die von `FaultException` abgeleitet ist.  
  
## <a name="message"></a>Meldung  
 Die '%1'-Methode hat beim Aufrufen von OperationInvoker eine FaultException ausgelöst. Die Methodenaufrufdauer betrug '%2' ms.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|MethodName|`xs:string`|Der CLR-Name der Methode, die vom `OperationInvoker` aufgerufen wurde.|  
|Dauer|`xs:long`|Die Zeit, in Millisekunden, die der `OperationInvoker` zum Aufrufen der Methode benötigt hat.|  
|HostReference|`xs:string`|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig. Das Format ist definiert als "Website Namen virtueller Anwendungspfad &#124; Virtueller Dienstpfad &#124; ServiceName ". Beispiel: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.|  
|AppDomain|`xs:string`|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
