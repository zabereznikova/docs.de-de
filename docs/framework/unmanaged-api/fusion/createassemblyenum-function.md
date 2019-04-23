---
title: CreateAssemblyEnum-Funktion
ms.date: 03/30/2017
api_name:
- CreateAssemblyEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyEnum
helpviewer_keywords:
- CreateAssemblyEnum function [.NET Framework fusion]
ms.assetid: 3506df38-6cea-42f6-946e-4287863bcfb3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c0c5dabd4145098941e9e8a7e36fa3215c26713d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59084902"
---
# <a name="createassemblyenum-function"></a>CreateAssemblyEnum-Funktion
Ruft einen Zeiger auf ein [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) -Instanz, die die Objekte in der Assembly mit dem angegebenen auflisten kann [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CreateAssemblyEnum (  
    [out] IAssemblyEnum  **pEnum,  
    [in]  IUnknown       *pUnkReserved,  
    [in]  IAssemblyName  *pName,  
    [in]  DWORD          dwFlags,  
    [in]  LPVOID         pvReserved  
 );  
```  
  
## <a name="parameters"></a>Parameter  
 `pEnum`  
 [out] Zeiger auf einen Speicherbereich, der den angeforderten enthält `IAssemblyEnum` Zeiger.  
  
 `pUnkReserved`  
 [in] Für zukünftige Erweiterungen reserviert. `pUnkReserved` ein null-Verweis muss sein.  
  
 `pName`  
 [in] Die `IAssemblyName` der angeforderten Assembly. Dieser Name wird verwendet, um die Enumeration zu filtern. Es kann null, um alle Assemblys im globalen Assemblycache aufgelistet sein.  
  
 `dwFlags`  
 [in] Flags für das Verhalten des Enumerators geändert. Dieser Parameter enthält genau ein Bit aus dem [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) Enumeration.  
  
 `pvReserved`  
 [in] Für zukünftige Erweiterungen reserviert. `pvReserved` ein null-Verweis muss sein.  
  
## <a name="remarks"></a>Hinweise  
 Die `dwFlags` Parameter enthält genau ein Bit aus dem `ASM_CACHE_FLAGS` Enumeration.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Fusion.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IAssemblyEnum-Schnittstelle](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
- [IAssemblyName-Schnittstelle](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [Fusion: Globale statistische Funktionen](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
