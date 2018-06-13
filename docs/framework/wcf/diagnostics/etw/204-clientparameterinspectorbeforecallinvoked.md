---
title: 204 - ClientParameterInspectorBeforeCallInvoked
ms.date: 03/30/2017
ms.assetid: 8253555a-9002-4565-8ede-33d7a33a895f
ms.openlocfilehash: eb060cfa79b75452deae67705126a24b7ca9ffef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458584"
---
# <a name="204---clientparameterinspectorbeforecallinvoked"></a>204 - ClientParameterInspectorBeforeCallInvoked
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|Id|204|  
|Stichwörter|Troubleshooting, ServiceModel|  
|Ebene|Information|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Beschreibung  
 Dieses Ereignis wird ausgegeben, nachdem das Dienstmodell die `BeforeCall`-Methode auf einem Clientparameterinspektor aufgerufen hat.  
  
## <a name="message"></a>Meldung  
 Der Verteiler hat 'BeforeCall' auf einem ClientParameterInspector vom Typ '%1' aufgerufen.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|TypeName|`xs:string`|Der CLR-FullName für den Typ des aufgerufenen Inspektors.|  
|HostReference|`xs:string`|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig. Das Format ist definiert als "Website Namen virtueller Anwendungspfad&#124;virtueller Dienstpfad&#124;ServiceName". Beispiel: "Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
