---
title: 1035 - RuntimeTransactionSet
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03b37de9-778c-4beb-b0e3-de73ece6088e
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0fcd6662c0f8899b6830dc8e06cee4f56b5ff906
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
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
