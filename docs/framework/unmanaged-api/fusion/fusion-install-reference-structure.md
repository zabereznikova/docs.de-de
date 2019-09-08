---
title: FUSION_INSTALL_REFERENCE-Struktur
ms.date: 03/30/2017
api_name:
- FUSION_INSTALL_REFERENCE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- FUSION_INSTALL_REFERENCE
helpviewer_keywords:
- FUSION_INSTALL_REFERENCE structure [.NET Framework fusion]
ms.assetid: ae181ec8-36bf-4ed1-9a02-ca27d417c80b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9e81fb7c99b9fd03a69456a84f2191770f40121d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795348"
---
# <a name="fusion_install_reference-structure"></a>FUSION_INSTALL_REFERENCE-Struktur
Stellt einen Verweis auf eine Assembly dar, die von der Anwendung im globalen Assemblycache installiert wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef struct _FUSION_INSTALL_REFERENCE_ {  
    DWORD    cbSize,  
    DWORD    dwFlags,  
    GUID     guidScheme,  
    LPCWSTR  szIdentifier,  
    LPCWSTR  szNonCanonicalData  
} FUSION_INSTALL_REFERENCE, *LPFUSION_INSTALL_REFERENCE;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`cbSize`|Die Größe der Struktur in Bytes.|  
|`dwFlags`|Reserviert für zukünftige Erweiterbarkeit. Dieser Wert muss 0 (null) sein.|  
|`guidScheme`|Die Entität, die den Verweis hinzufügt. Dieses Feld kann einen der folgenden Werte aufweisen:<br /><br /> - FUSION_REFCOUNT_MSI_GUID: Auf die Assembly wird von einer Anwendung verwiesen, die mithilfe des-Microsoft Windows Installer installiert wurde. Das `szIdentifier` Feld wird auf `MSI`festgelegt, und `szNonCanonicalData` das Feld wird auf `Windows Installer`festgelegt. Dieses Schema wird für parallele Assemblys von Windows verwendet.<br />- FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: Auf die Assembly wird von einer Anwendung verwiesen, die in der Schnittstelle " **Programme hinzufügen/entfernen** " angezeigt wird. Das `szIdentifier` -Feld stellt das Token bereit, das die Anwendung bei der Schnittstelle zum **Hinzufügen/Entfernen von Programmen** registriert.<br />- FUSION_REFCOUNT_FILEPATH_GUID: Auf die Assembly wird von einer Anwendung verwiesen, die durch eine Datei im Dateisystem dargestellt wird. Das `szIdentifier` Feld enthält den Pfad zu dieser Datei.<br />- FUSION_REFCOUNT_OPAQUE_STRING_GUID: Auf die Assembly wird von einer Anwendung verwiesen, die nur durch eine nicht transparente Zeichenfolge dargestellt wird. Das `szIdentifier` -Feld stellt diese nicht transparente Zeichenfolge bereit. Der globale Assemblycache prüft nicht, ob nicht transparente Verweise vorhanden sind, wenn Sie diesen Wert entfernen.<br />- FUSION_REFCOUNT_OSINSTALL_GUID: Dieser Wert ist reserviert.|  
|`szIdentifier`|Eine eindeutige Zeichenfolge, die die Anwendung identifiziert, die die Assembly im globalen Assemblycache installiert hat. Der Wert hängt vom Wert des `guidScheme` Felds ab.|  
|`szNonCanonicalData`|Eine Zeichenfolge, die nur von der Entität verstanden wird, die den Verweis hinzufügt. Der globale Assemblycache speichert diese Zeichenfolge, verwendet Sie jedoch nicht.|  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Fusion. h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Fusion-Strukturen](fusion-structures.md)
- [Globaler Assemblycache](../../app-domains/gac.md)
