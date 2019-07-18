---
title: 3501 - InferredContractDescription
ms.date: 03/30/2017
ms.assetid: 21a70849-4fc0-41d2-b9a4-db5aa2acdf1a
ms.openlocfilehash: 47a5d98f4510e8c6092e8533a98366141d4b24db
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755895"
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
