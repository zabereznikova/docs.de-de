---
title: CorDeclSecurity-Enumeration
ms.date: 03/30/2017
api_name:
- CorDeclSecurity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorDeclSecurity
helpviewer_keywords:
- CorDeclSecurity enumeration [.NET Framework metadata]
ms.assetid: 864f1267-d267-4696-8df7-1f83f8444d6f
topic_type:
- apiref
ms.openlocfilehash: dd599ce8c63fa94e1a18b4e2d18fa334238728bd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718877"
---
# <a name="cordeclsecurity-enumeration"></a>CorDeclSecurity-Enumeration

Gibt die Sicherheitsaktionen an, die mit deklarativer Sicherheit ausgeführt werden können.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum CorDeclSecurity {  
  
    dclActionMask               =   0x001f,  
    dclActionNil                =   0x0000,  
    dclRequest                  =   0x0001,  
    dclDemand                   =   0x0002,  
    dclAssert                   =   0x0003,  
    dclDeny                     =   0x0004,  
    dclPermitOnly               =   0x0005,  
    dclLinktimeCheck            =   0x0006,  
    dclInheritanceCheck         =   0x0007,  
    dclRequestMinimum           =   0x0008,  
    dclRequestOptional          =   0x0009,  
    dclRequestRefuse            =   0x000a,  
    dclPrejitGrant              =   0x000b,  
    dclPrejitDenied             =   0x000c,  
    dclNonCasDemand             =   0x000d,  
    dclNonCasLinkDemand         =   0x000e,  
    dclNonCasInheritance        =   0x000f,  
    dclLinkDemandChoice         =   0x0010,  
    dclInheritanceDemandChoice  =   0x0011,  
    dclDemandChoice             =   0x0012,  
    dclMaximumValue             =   0x0012  
  
} CorDeclSecurity;  
```  
  
## <a name="members"></a>Member  
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`dclActionMask`|Reserviert.|  
|`dclActionNil`|Reserviert.|  
|`dclRequest`|Reserviert.|  
|`dclDemand`|Allen Aufrufern einer höheren Ebene in der Aufrufliste muss die vom aktuellen Berechtigungsobjekt angegebene Berechtigung erteilt worden sein.|  
|`dclAssert`|Der Aufruf Code kann auf die durch das aktuelle Berechtigungs Objekt identifizierte Ressource zugreifen, selbst wenn Aufrufern einer höheren Ebene im Stapel keine Berechtigung für den Zugriff auf die Ressource erteilt wurde.|  
|`dclDeny`|Die Möglichkeit, auf die durch das aktuelle Berechtigungs Objekt angegebene Ressource zuzugreifen, wird Aufrufern auch dann verweigert, wenn Ihnen die Berechtigung für den Zugriff auf die Ressource erteilt wurde.|  
|`dclPermitOnly`|Nur auf die durch dieses Berechtigungsobjekt angegebenen Ressourcen kann zugegriffen werden, selbst wenn dem Code die Berechtigung für den Zugriff auf andere Ressourcen gewährt wurde.|  
|`dclLinktimeCheck`|Dem unmittelbaren Aufrufer muss die angegebene Berechtigung für einen bestimmten Zeitraum erteilt worden sein.|  
|`dclInheritanceCheck`|Der abgeleiteten Klasse, die eine andere Klasse erbt oder eine Methode überschreibt, muss die angegebene Berechtigung erteilt worden sein.|  
|`dclRequestMinimum`|Der Aufrufer kann die minimalen Berechtigungen anfordern, die zum Ausführen von Code erforderlich sind. Diese Aktion kann nur innerhalb des Gültigkeitsbereichs der Assembly verwendet werden.|  
|`dclRequestOptional`|Der Aufrufer kann zusätzliche Berechtigungen anfordern, die optional sind (zum Ausführen nicht erforderlich). Diese Anforderung lehnt implizit alle anderen nicht speziell angeforderten Berechtigungen ab. Diese Aktion kann nur innerhalb des Gültigkeitsbereichs der Assembly verwendet werden.|  
|`dclRequestRefuse`|Die Anforderung des Aufrufers für Berechtigungen, die möglicherweise missbraucht werden, wird nicht erteilt. Diese Aktion kann nur innerhalb des Gültigkeitsbereichs der Assembly verwendet werden.|  
|`dclPrejitGrant`|Reserviert.|  
|`dclPrejitDenied`|Reserviert.|  
|`dclNonCasDemand`|Reserviert.|  
|`dclNonCasLinkDemand`|Dem unmittelbaren Aufrufer muss die angegebene Berechtigung erteilt worden sein.|  
|`dclNonCasInheritance`|Reserviert.|  
|`dclLinkDemandChoice`|Reserviert.|  
|`dclInheritanceDemandChoice`|Reserviert.|  
|`dclDemandChoice`|Reserviert.|  
|`dclMaximumValue`|Reserviert.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Corhdr. h  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Metadatenenumerationen](metadata-enumerations.md)
