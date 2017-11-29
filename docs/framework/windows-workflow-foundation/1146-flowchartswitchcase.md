---
title: 1146 - FlowchartSwitchCase
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 274e9209-1720-4512-a615-e742f00895f4
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 68c1c4c881e7b963618679a86622b7f8ab961681
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
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
