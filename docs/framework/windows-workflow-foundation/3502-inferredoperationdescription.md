---
title: 3502 - InferredOperationDescription
ms.date: 03/30/2017
ms.assetid: 6aebb614-3c72-4537-ba11-3cc7200ef1f1
ms.openlocfilehash: 05278067e3f86612ee4aafbe7d5eb66dc934cb85
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242109"
---
# <a name="3502---inferredoperationdescription"></a>3502 - InferredOperationDescription

## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|id|3502|  
|Keywords|WFServices|  
|Ebene|Information|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>BESCHREIBUNG  

 Gibt an, dass eine OperationDescription aus WorkflowService abgeleitet wurde.  
  
## <a name="message"></a>`Message`  

 Die OperationDescription mit Name='%1' in Vertrag '%2' wurde aus WorkflowService abgeleitet. IsOneWay=%3.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|BESCHREIBUNG|  
|--------------------|--------------------|-----------------|  
|Vorgangsname|xs:string|Der Name des Vorgangs.|  
|ContractName|xs:string|Der Name des Vertrags.|  
|IsOneWay|xs:string|True oder False gibt an, ob der Vertrag unidirektional ist.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
