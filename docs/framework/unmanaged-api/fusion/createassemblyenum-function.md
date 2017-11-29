---
title: CreateAssemblyEnum-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateAssemblyEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type: DLLExport
f1_keywords: CreateAssemblyEnum
helpviewer_keywords: CreateAssemblyEnum function [.NET Framework fusion]
ms.assetid: 3506df38-6cea-42f6-946e-4287863bcfb3
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c229496a79b146b5dcac3d06fa3efd9237e39d3a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="createassemblyenum-function"></a>CreateAssemblyEnum-Funktion
Ruft einen Zeiger auf eine [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) -Instanz, die die Objekte in der Assembly mit dem angegebenen auflisten kann [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md).  
  
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
  
#### <a name="parameters"></a>Parameter  
 `pEnum`  
 [out] Zeiger auf eine Speicheradresse, die die angeforderte enthält `IAssemblyEnum` Zeiger.  
  
 `pUnkReserved`  
 [in] Für zukünftige Erweiterungen reserviert. `pUnkReserved`ein null-Verweis muss sein.  
  
 `pName`  
 [in] Die `IAssemblyName` der angeforderten Assembly. Dieser Name wird verwendet, um die Enumeration zu filtern. Sie können alle Assemblys im globalen Assemblycache auflisten null sein.  
  
 `dwFlags`  
 [in] Flags für das Verhalten des Enumerators ändern. Dieser Parameter enthält genau ein Bit aus der [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) Enumeration.  
  
 `pvReserved`  
 [in] Für zukünftige Erweiterungen reserviert. `pvReserved`ein null-Verweis muss sein.  
  
## <a name="remarks"></a>Hinweise  
 Die `dwFlags` Parameter enthält genau ein Bit aus der `ASM_CACHE_FLAGS` Enumeration.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Fusion.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IAssemblyEnum-Schnittstelle](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)  
 [IAssemblyName-Schnittstelle](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [Globale statische Fusionsfunktionen](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
