---
title: ICorDebugDataTarget2::GetImageFromPointer-Methode
ms.date: 03/30/2017
ms.assetid: 939cabe1-b647-4090-b662-eeec23c6c58d
ms.openlocfilehash: 41385fe915733f052af67c82d984c8b9d853c579
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713820"
---
# <a name="icordebugdatatarget2getimagefrompointer-method"></a>ICorDebugDataTarget2::GetImageFromPointer-Methode

Gibt die Basisadresse des Moduls und die Größe von einer Adresse in diesem Modul aus.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetImageFromPointer(  
   [in] CORDB_ADDRESS addr,
   [out] CORDB_ADDRESS *pImageBase,
   [out] ULONG32 *pSize  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `addr`  
 Ein [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) Wert, der eine Adresse in einem Modul darstellt.  
  
 `pImageBase`  
 vorgenommen Ein [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) Wert, der die Basisadresse des Moduls darstellt.  
  
 `pSize`  
 Ein Zeiger auf die Modulgröße.  
  
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
