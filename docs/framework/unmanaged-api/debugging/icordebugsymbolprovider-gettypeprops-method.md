---
title: ICorDebugSymbolProvider::GetTypeProps-Methode
ms.date: 03/30/2017
ms.assetid: 35ac4140-91ea-4c77-b1c4-1daf41986ca5
ms.openlocfilehash: 4738d35aabbc2197c796405e0657607f75ff685d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95694502"
---
# <a name="icordebugsymbolprovidergettypeprops-method"></a>ICorDebugSymbolProvider::GetTypeProps-Methode

Gibt anhand einer relativen virtuellen Adresse (RVA) in einem VTable Informationen zu den Eigenschaften eines Typs wie die Anzahl der Signaturen der generischen Parameter zurück.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetTypeProps(  
   [in]  ULONG32 vtableRva,  
   [in]  ULONG32 cbSignature,  
   [out] ULONG32 *pcbSignature,  
   [out, size_is(cbSignature), length_is(*pcbSignature)] BYTE signature[]  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `tableRva`  
 [in] Eine relative virtuelle Adresse (RVA) in einem VTable.  
  
 `cbSignature`  
 [in] Die Größe des `signature`-Arrays. Weitere Informationen finden Sie im Abschnitt mit den Hinweisen.  
  
 `pcbSignature`  
 [out] [out] Ein Zeiger auf die Größe des zurückgegebenen `signature`-Arrays.  
  
 `signature`  
 [out] Ein Puffer, der die TypeSpec-Signaturen aller generischen Parameter enthält.  
  
## <a name="remarks"></a>Hinweise  

 Um die erforderliche Größe des-Arrays des Typs zu erhalten `signature` , legen Sie das- `cbSignature` Argument auf 0 und `signature` auf **null** fest. Wenn die Methode zurückgegeben wird, enthält `pcbSignature` die Anzahl der für das `signature`-Array erforderlichen Bytes.  
  
> [!NOTE]
> Diese Methode ist nur mit .NET Native verfügbar.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [GetMethodProps-Methode](icordebugsymbolprovider-getmethodprops-method.md)
- [ICorDebugSymbolProvider-Schnittstelle](icordebugsymbolprovider-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
