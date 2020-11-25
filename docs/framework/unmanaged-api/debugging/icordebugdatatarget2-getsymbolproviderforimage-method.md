---
title: ICorDebugDataTarget2::GetSymbolProviderForImage-Methode
ms.date: 03/30/2017
ms.assetid: b7c0a2f0-e904-43b3-98e1-d669e8a589e8
ms.openlocfilehash: 5a5ccaeb36dcda82c0189026e19c6a7c023f3e1c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713768"
---
# <a name="icordebugdatatarget2getsymbolproviderforimage-method"></a>ICorDebugDataTarget2::GetSymbolProviderForImage-Methode

Gibt anhand der Basisadresse des Moduls den Symbol-Anbieter für ein Modul aus.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetSymbolProviderForImage(  
    [in] CORDB_ADDRESS imageBaseAddress,
    [out] ICorDebugSymbolProvider **ppSymProvider  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `imageBaseAddress`  
 in Ein [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) Wert, der die Basisadresse eines Moduls darstellt.  
  
 `ppSymProvider`  
 vorgenommen Ein Zeiger auf die Adresse eines [icorentbugsymbolprovider](icordebugsymbolprovider-interface.md) -Objekts.  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Methode ist nur mit .NET Native verfügbar.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugDataTarget2-Schnittstelle](icordebugdatatarget2-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
