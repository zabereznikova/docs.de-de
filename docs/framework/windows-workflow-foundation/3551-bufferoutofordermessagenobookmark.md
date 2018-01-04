---
title: 3551 - BufferOutOfOrderMessageNoBookmark
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7930d6c4-c843-4a83-933a-cecd71b80d1e
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5e785e40afcb91620940f952022eda4c4b799f4a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="3551---bufferoutofordermessagenobookmark"></a>3551 - BufferOutOfOrderMessageNoBookmark
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|3551|  
|Schlüsselwörter|WFServices|  
|Ebene|Information|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Beschreibung  
 Gibt an, dass eine Lesezeichenwiederaufnahme fehlgeschlagen ist. Der gepufferte Empfangsvorgang wird wiederholt, wenn die Dienstinstanz bereit ist, diesen Vorgang zu verarbeiten.  
  
## <a name="message"></a>Meldung  
 Vorgang '%2' der Dienstinstanz '%1' kann derzeit nicht ausgeführt werden. Es wird ein weiterer Versuch unternommen, wenn die Dienstinstanz bereit ist, diesen Vorgang zu verarbeiten.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|OperationName|xs:string|Der Name des Vorgangs.|  
|ServiceInstanceId|xs:string|Die ID der Dienstinstanz.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
