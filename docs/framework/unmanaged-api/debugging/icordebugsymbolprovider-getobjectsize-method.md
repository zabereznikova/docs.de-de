---
title: ICorDebugSymbolProvider::GetObjectSize-Methode
ms.date: 03/30/2017
ms.assetid: 3c564396-ac64-4ef3-b4f6-df96f1d46fc7
ms.openlocfilehash: 4937ff1be7736f98be9efb9b01bdb322bf33e037
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730807"
---
# <a name="icordebugsymbolprovidergetobjectsize-method"></a>ICorDebugSymbolProvider::GetObjectSize-Methode

Gibt die Objektgröße eines Objekts basierend auf seiner TypeSpec-Signatur zurück.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetObjectSize(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [out] ULONG32 *pObjectSize  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `cbSignature`  
 [in] Die Anzahl der Bytes in der TypeSpec-Signatur.  
  
 typeSig  
 [in] Die TypeSpec-Signatur.  
  
 `pObjectSize`  
 [out] Ein Zeiger auf die Größe des Objekts.  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Methode ist nur mit .NET Native verfügbar.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugSymbolProvider-Schnittstelle](icordebugsymbolprovider-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
