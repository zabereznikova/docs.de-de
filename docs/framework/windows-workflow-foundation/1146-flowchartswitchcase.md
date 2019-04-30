---
title: 1146 - FlowchartSwitchCase
ms.date: 03/30/2017
ms.assetid: 274e9209-1720-4512-a615-e742f00895f4
ms.openlocfilehash: 9f4e3af664ed30634e4b56f16cd6caf2366c3674
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61923902"
---
# <a name="1146---flowchartswitchcase"></a>1146 - FlowchartSwitchCase
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|1146|  
|Schlüsselwörter|WFActivities|  
|Ebene|Information|  
|Kanal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Beschreibung  
 Gibt an, welcher Fall in einem Flussdiagrammschalter ausgewählt wurde.  
  
## <a name="message"></a>Meldung  
 Flussdiagramm '%1'/FlowSwitch - Fall '%2' wurde ausgewählt.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|FlowChart|xs:string|Der Anzeigename des FlowChart.|  
|Case|xs:string|Der Schalterfall, der ausgewählt wurde.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
