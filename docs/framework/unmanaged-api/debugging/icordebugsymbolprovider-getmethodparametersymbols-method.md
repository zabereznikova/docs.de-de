---
title: ICorDebugSymbolProvider::GetMethodParameterSymbols-Methode
ms.date: 03/30/2017
ms.assetid: 58b7c0b9-f6ad-4b49-b92d-0e421cfd0ec6
ms.openlocfilehash: 95b7b61087f3d3fddab36b7835a633534c223b72
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730837"
---
# <a name="icordebugsymbolprovidergetmethodparametersymbols-method"></a>ICorDebugSymbolProvider::GetMethodParameterSymbols-Methode

Ruft die Parametersymbole einer Methode ab, wenn die relative virtuelle Adresse (RVA) der Methode angegeben ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetMethodParameterSymbols(  
   [in] ULONG32 nativeRVA,  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugVariableSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `nativeRVA`  
 [in] Die systemeigene relative virtuelle Adresse der Methode.  
  
 `cRequestedSymbols`  
 [in] Die Anzahl der angeforderten lokalen Symbole.  
  
 `pcFetchedSymbols`  
 [out] Ein Zeiger auf die Anzahl der von der Methode abgerufenen Symbole.  
  
 `pcFetchedSymbols`  
 vorgenommen Ein Zeiger auf ein [icordebugvariablesymbol](icordebugvariablesymbol-interface.md) -Array, das die lokalen Symbole der Methode enthält.  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Methode ist nur mit .NET Native verfügbar.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [GetMethodLocalSymbols-Methode](icordebugsymbolprovider-getmethodlocalsymbols-method.md)
- [ICorDebugSymbolProvider-Schnittstelle](icordebugsymbolprovider-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
