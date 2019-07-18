---
title: 3551 - BufferOutOfOrderMessageNoBookmark
ms.date: 03/30/2017
ms.assetid: 7930d6c4-c843-4a83-933a-cecd71b80d1e
ms.openlocfilehash: 89643edde5856688c762b0cf0d188bd4e7ba8a24
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755531"
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
