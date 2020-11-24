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
ms.openlocfilehash: b7e3696121475885f5061bd96eb6905d7ccae734
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683172"
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
 vorgenommen Ein Zeiger auf einen Speicherort, der den angeforderten `IAssemblyEnum` Zeiger enthält.  
  
 `pUnkReserved`  
 [in] Für zukünftige Erweiterungen reserviert. `pUnkReserved` muss ein NULL-Verweis sein.  
  
 `pName`  
 in Der der `IAssemblyName` angeforderten Assembly. Dieser Name wird verwendet, um die-Enumeration zu filtern. Es kann NULL sein, um alle Assemblys im globalen Assemblycache aufzuzählen.  
  
 `dwFlags`  
 in Flags zum Ändern des Verhaltens des Enumerators. Dieser Parameter enthält genau ein Bit aus der [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) Enumeration.  
  
 `pvReserved`  
 [in] Für zukünftige Erweiterungen reserviert. `pvReserved` muss ein NULL-Verweis sein.  
  
## <a name="remarks"></a>Hinweise  

 Der- `dwFlags` Parameter enthält genau ein Bit aus der- `ASM_CACHE_FLAGS` Enumeration.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Fusion. h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IAssemblyEnum-Schnittstelle](iassemblyenum-interface.md)
- [IAssemblyName-Schnittstelle](iassemblyname-interface.md)
- [Fusion – Globale statistische Funktionen](fusion-global-static-functions.md)
