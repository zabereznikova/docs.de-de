---
title: 'Icordebugsymbolprovider:: getinstancefieldsymbols-Methode'
ms.date: 03/30/2017
ms.assetid: a29b9233-ee67-4b53-b8bc-c00b281e7edb
ms.openlocfilehash: 0ad8ddd78d963681c0b2f69bf0f211ad464dc7b7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138879"
---
# <a name="icordebugsymbolprovidergetinstancefieldsymbols-method"></a>Icordebugsymbolprovider:: getinstancefieldsymbols-Methode
Ruft die Instanzenfeldsymbole ab, die einer TypeSpec-Signatur entsprechen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetInstanceFieldSymbols(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugInstanceFieldSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `cbSignature`  
 [in] Die Anzahl der Bytes im `typeSig`-Array.  
  
 `typeSig`  
 [in] Ein Bytearray, das die `typespec`-Signatur enthält.  
  
 `cRequestedSymbols`  
 [in] Die Anzahl der angeforderten Symbole.  
  
 `pcFetchedSymbols`  
 [out] Ein Zeiger auf die Anzahl der von der Methode abgerufenen Symbole.  
  
 `pSymbols`  
 vorgenommen Ein Zeiger auf ein [icordebugstaticfieldsymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md) -Array, das die angeforderten instanzfeldsymbole enthält.  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Methode ist nur mit .NET Native verfügbar.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [GetStaticFieldSymbols-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getstaticfieldsymbols-method.md)
- [ICorDebugSymbolProvider-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
