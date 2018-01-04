---
title: 3501 - InferredContractDescription
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 21a70849-4fc0-41d2-b9a4-db5aa2acdf1a
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 32eac2fbfc0175010906d600b2d044868bda38be
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="3501---inferredcontractdescription"></a>3501 - InferredContractDescription
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|3501|  
|Schlüsselwörter|WFServices|  
|Ebene|Information|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Beschreibung  
 Gibt an, dass eine ContractDescription von WorkflowService abgeleitet wurde.  
  
## <a name="message"></a>Meldung  
 Die ContractDescription mit Name='%1' und Namespace='%2' wurde aus WorkflowService abgeleitet.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|Name|xs:string|Der Name der ContractDescription.|  
|Namespace|xs:string|Der Namespace des ContractDescription.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
