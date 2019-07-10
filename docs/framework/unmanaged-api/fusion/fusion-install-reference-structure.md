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
ms.openlocfilehash: ec18d5d5a6574cb0e08a6c4d6eaedcbcbf6886cd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759359"
---
# <a name="fusioninstallreference-structure"></a>FUSION_INSTALL_REFERENCE-Struktur
Stellt einen Verweis, den eine Anwendung in einer Assembly zu können, die die Anwendung im globalen Assemblycache installiert ist.  
  
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
|`guidScheme`|Die Entität, die den Verweis hinzugefügt. Dieses Feld kann einen der folgenden Werte aufweisen:<br /><br /> -   FUSION_REFCOUNT_MSI_GUID: Die Assembly wird von einer Anwendung auf die verwiesen wird, die mit dem Microsoft Windows Installer installiert wurde. Die `szIdentifier` Feld nastaven NA hodnotu `MSI`, und die `szNonCanonicalData` Feld nastaven NA hodnotu `Windows Installer`. Dieses Schema wird für Windows-Seite-an-Seite-Assemblys verwendet.<br />-   FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: Die Assembly verwiesen wird, von einer Anwendung, die in angezeigt wird. die **Programme hinzufügen/entfernen** Schnittstelle. Die `szIdentifier` Feld enthält das Token, das die Anwendung mit registriert die **Programme hinzufügen/entfernen** Schnittstelle.<br />-   FUSION_REFCOUNT_FILEPATH_GUID: Die Assembly wird von einer Anwendung auf die verwiesen wird, die von einer Datei im Dateisystem dargestellt wird. Die `szIdentifier` Feld enthält den Pfad zu dieser Datei.<br />-   FUSION_REFCOUNT_OPAQUE_STRING_GUID: Die Assembly wird von einer Anwendung auf die verwiesen wird, die nur durch eine nicht transparente Zeichenfolge dargestellt wird. Die `szIdentifier` Feld enthält, diese nicht transparente Zeichenfolge. Im globalen Assemblycache überprüft nicht das Vorhandensein von nicht transparenten verweisen, wenn Sie diesen Wert entfernen.<br />-   FUSION_REFCOUNT_OSINSTALL_GUID: Dieser Wert ist reserviert.|  
|`szIdentifier`|Eine eindeutige Zeichenfolge, die die Anwendung identifiziert, die die Assembly im globalen Assemblycache installiert. Der Wert hängt von den Wert des der `guidScheme` Feld.|  
|`szNonCanonicalData`|Eine Zeichenfolge, die nur von der Entität verstanden wird, die den Verweis hinzugefügt. Im globalen Assemblycache speichert diese Zeichenfolge ist, aber nicht verwendet.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Fusion.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Fusion-Strukturen](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
- [Globaler Assemblycache](../../../../docs/framework/app-domains/gac.md)
