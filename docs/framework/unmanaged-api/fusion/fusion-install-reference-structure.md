---
title: FUSION_INSTALL_REFERENCE-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FUSION_INSTALL_REFERENCE
api_location: fusion.dll
api_type: COM
f1_keywords: FUSION_INSTALL_REFERENCE
helpviewer_keywords: FUSION_INSTALL_REFERENCE structure [.NET Framework fusion]
ms.assetid: ae181ec8-36bf-4ed1-9a02-ca27d417c80b
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 36321606fe208233fb6114fe9568b655f0e1b400
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="fusioninstallreference-structure"></a>FUSION_INSTALL_REFERENCE-Struktur
Stellt einen Verweis, den eine Anwendung eine Assembly ändert, der die Anwendung im globalen Assemblycache installiert wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
|`dwFlags`|Für zukünftige Erweiterungen reserviert. Dieser Wert muss 0 (null) sein.|  
|`guidScheme`|Die Entität, die den Verweis hinzufügt. Dieses Feld kann einen der folgenden Werte aufweisen:<br /><br /> -FUSION_REFCOUNT_MSI_GUID: Auf die Assembly wird von einer Anwendung verwiesen, die mit Microsoft Windows Installer installiert wurde. Die `szIdentifier` Feld `MSI`, und die `szNonCanonicalData` Feld `Windows Installer`. Dieses Schema wird für Windows-Seite-an-Seite-Assemblys verwendet.<br />-FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: Die Assembly von einer Anwendung, die in angezeigt verweist die **Programme hinzufügen/entfernen** Schnittstelle. Die `szIdentifier` Feld gibt das Token, das die Anwendung mit registriert die **Programme hinzufügen/entfernen** Schnittstelle.<br />-FUSION_REFCOUNT_FILEPATH_GUID: Auf die Assembly wird von einer Anwendung verwiesen, die durch eine Datei im Dateisystem dargestellt wird. Die `szIdentifier` Feld gibt den Pfad zu dieser Datei.<br />-FUSION_REFCOUNT_OPAQUE_STRING_GUID: Auf die Assembly wird von einer Anwendung verwiesen, die nur durch eine nicht transparente Zeichenfolge dargestellt wird. Die `szIdentifier` Feld bietet diese nicht transparente Zeichenfolge. Im globalen Assemblycache überprüft nicht das Vorhandensein von nicht transparenten verweisen, wenn Sie diesen Wert entfernen.<br />-FUSION_REFCOUNT_OSINSTALL_GUID: Dieser Wert ist reserviert.|  
|`szIdentifier`|Eine eindeutige Zeichenfolge, die die Anwendung identifiziert, die die Assembly im globalen Assemblycache installiert. Der Wert hängt vom Wert von der `guidScheme` Feld.|  
|`szNonCanonicalData`|Eine Zeichenfolge, die nur von der Entität verstanden wird, die den Verweis hinzufügt. Der globale Assemblycache speichert diese Zeichenfolge, aber nicht verwendet.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Fusion.h  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Fusion-Strukturen](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)  
 [Globaler Assemblycache](../../../../docs/framework/app-domains/gac.md)
