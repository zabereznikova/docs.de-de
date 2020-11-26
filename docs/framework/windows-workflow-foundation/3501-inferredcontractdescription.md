---
title: 3501 - InferredContractDescription
ms.date: 03/30/2017
ms.assetid: 21a70849-4fc0-41d2-b9a4-db5aa2acdf1a
ms.openlocfilehash: 88a04c0eb6d12876592702ad4dba3a17aa8da122
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96245288"
---
# <a name="3501---inferredcontractdescription"></a>3501 - InferredContractDescription

## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|id|3501|  
|Keywords|WFServices|  
|Ebene|Information|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>BESCHREIBUNG  

 Gibt an, dass eine ContractDescription von WorkflowService abgeleitet wurde.  
  
## <a name="message"></a>`Message`  

 Die ContractDescription mit Name='%1' und Namespace='%2' wurde aus WorkflowService abgeleitet.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|BESCHREIBUNG|  
|--------------------|--------------------|-----------------|  
|Name|xs:string|Der Name der ContractDescription.|  
|Namespace|xs:string|Der Namespace des ContractDescription.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
