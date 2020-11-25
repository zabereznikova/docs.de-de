---
title: ICorDebugSymbolProvider::GetInstanceFieldSymbols-Methode
ms.date: 03/30/2017
ms.assetid: a29b9233-ee67-4b53-b8bc-c00b281e7edb
ms.openlocfilehash: 1a74b355b695f65166d0fe63bbdd41d789db5cfe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730863"
---
# <a name="icordebugsymbolprovidergetinstancefieldsymbols-method"></a>ICorDebugSymbolProvider::GetInstanceFieldSymbols-Methode

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
 vorgenommen Ein Zeiger auf ein [icordebugstaticfieldsymbol](icordebugstaticfieldsymbol-interface.md) -Array, das die angeforderten instanzfeldsymbole enthält.  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Methode ist nur mit .NET Native verfügbar.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [GetStaticFieldSymbols-Methode](icordebugsymbolprovider-getstaticfieldsymbols-method.md)
- [ICorDebugSymbolProvider-Schnittstelle](icordebugsymbolprovider-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
