---
title: 202 - ClientMessageInspectorBeforeSendInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b02ca82-8a55-45e3-b2e2-ddfe28a7269c
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f6d737a7334098961cccb73a114be9be5bb71727
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="202---clientmessageinspectorbeforesendinvoked"></a>202 - ClientMessageInspectorBeforeSendInvoked
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|Id|202|  
|Stichwörter|Troubleshooting, ServiceModel|  
|Ebene|Information|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Beschreibung  
 Dieses Ereignis wird ausgegeben, nachdem das Dienstmodell die `BeforeSendRequest`-Methode auf einem Clientmeldungsinspektor aufgerufen hat.  
  
## <a name="message"></a>Meldung  
 Der Verteiler hat 'BeforeSendRequest' auf einem ClientMessageInspector des Typs '%1' aufgerufen.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|TypeName|`xs:string`|Der CLR-FullName für den Typ des aufgerufenen Inspektors.|  
|HostReference|`xs:string`|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig. Das Format ist definiert als "Website Namen virtueller Anwendungspfad &#124; Virtueller Dienstpfad &#124; ServiceName ". Beispiel: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.|  
|AppDomain|`xs:string`|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
