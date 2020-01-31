---
title: ICorDebugSymbolProvider::GetTypeProps-Methode
ms.date: 03/30/2017
ms.assetid: 35ac4140-91ea-4c77-b1c4-1daf41986ca5
ms.openlocfilehash: 5fa091eaf2cf93b0c645effeec3c959d42665fc9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791548"
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
  
## <a name="parameters"></a>Parameters  
 `tableRva`  
 [in] Eine relative virtuelle Adresse (RVA) in einem VTable.  
  
 `cbSignature`  
 [in] Die Größe des `signature`-Arrays. Weitere Informationen finden Sie im Abschnitt "Hinweise".  
  
 `pcbSignature`  
 [out] [out] Ein Zeiger auf die Größe des zurückgegebenen `signature`-Arrays.  
  
 `signature`  
 [out] Ein Puffer, der die TypeSpec-Signaturen aller generischen Parameter enthält.  
  
## <a name="remarks"></a>Hinweise  
 Um die erforderliche Größe des `signature` Arrays des Typs zu erhalten, legen Sie das `cbSignature`-Argument auf 0 und `signature` auf **null**fest. Wenn die Methode zurückgegeben wird, enthält `pcbSignature` die Anzahl der für das `signature`-Array erforderlichen Bytes.  
  
> [!NOTE]
> Diese Methode ist nur mit .NET Native verfügbar.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [GetMethodProps-Methode](icordebugsymbolprovider-getmethodprops-method.md)
- [ICorDebugSymbolProvider-Schnittstelle](icordebugsymbolprovider-interface.md)
- [Debuggen von Schnittstellen](debugging-interfaces.md)
