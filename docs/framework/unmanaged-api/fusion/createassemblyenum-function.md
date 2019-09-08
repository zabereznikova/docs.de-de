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
ms.openlocfilehash: 1db72c44b53b5abff9aee35094abc1e0e577fad4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795384"
---
# <a name="createassemblyenum-function"></a>CreateAssemblyEnum-Funktion
Ruft einen Zeiger auf eine [IAssemblyEnum](iassemblyenum-interface.md) -Instanz ab, die die Objekte in der Assembly mit dem angegebenen [IAssemblyName](iassemblyname-interface.md)auflisten kann.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
 vorgenommen Ein Zeiger auf einen Speicherort, der den `IAssemblyEnum` angeforderten Zeiger enthält.  
  
 `pUnkReserved`  
 [in] Für zukünftige Erweiterungen reserviert. `pUnkReserved`muss ein NULL-Verweis sein.  
  
 `pName`  
 in Der `IAssemblyName` der angeforderten Assembly. Dieser Name wird verwendet, um die-Enumeration zu filtern. Es kann NULL sein, um alle Assemblys im globalen Assemblycache aufzuzählen.  
  
 `dwFlags`  
 in Flags zum Ändern des Verhaltens des Enumerators. Dieser Parameter enthält genau ein Bit aus der [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) -Enumeration.  
  
 `pvReserved`  
 [in] Für zukünftige Erweiterungen reserviert. `pvReserved`muss ein NULL-Verweis sein.  
  
## <a name="remarks"></a>Hinweise  
 Der `dwFlags` -Parameter enthält genau ein Bit aus `ASM_CACHE_FLAGS` der-Enumeration.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Fusion. h  
  
 **Fern** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IAssemblyEnum-Schnittstelle](iassemblyenum-interface.md)
- [IAssemblyName-Schnittstelle](iassemblyname-interface.md)
- [Fusion: Globale statistische Funktionen](fusion-global-static-functions.md)
