---
title: 3502 - InferredOperationDescription
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6aebb614-3c72-4537-ba11-3cc7200ef1f1
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 144ab1a4a2fd313dc7817846e3e0118145cd3f8e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="3502---inferredoperationdescription"></a>3502 - InferredOperationDescription
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|3502|  
|Schlüsselwörter|WFServices|  
|Ebene|Information|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Beschreibung  
 Gibt an, dass eine OperationDescription aus WorkflowService abgeleitet wurde.  
  
## <a name="message"></a>Meldung  
 Die OperationDescription mit Name='%1' in Vertrag '%2' wurde aus WorkflowService abgeleitet. IsOneWay=%3.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|OperationName|xs:string|Der Name des Vorgangs.|  
|ContractName|xs:string|Der Name des Vertrags.|  
|IsOneWay|xs:string|True oder False gibt an, ob der Vertrag unidirektional ist.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
