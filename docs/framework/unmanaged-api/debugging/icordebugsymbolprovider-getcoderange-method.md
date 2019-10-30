---
title: 'Icordebugsymbolprovider:: getcoderange-Methode'
ms.date: 03/30/2017
ms.assetid: 49a2451f-d250-4e73-aa96-9ff49d9f11c6
ms.openlocfilehash: 84bf545fedf3a6c7915d94fd0c2630268585b6eb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138918"
---
# <a name="icordebugsymbolprovidergetcoderange-method"></a>Icordebugsymbolprovider:: getcoderange-Methode
Ruft die Startadresse und Größe einer Methode ab, wenn eine relative virtuelle Adresse (RVA) in der Methode angegeben ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetCodeRange(  
   [in] ULONG32 codeRva,   
   [out] ULONG32* pCodeStartAddress,   
   [out] ULONG32* pCodeSize  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `codeRva`  
 [in] Die relative virtuelle Adresse (RVA) in einer Methode.  
  
 `pCodeStartAddress`  
 [out] Ein Zeiger auf die Startadresse der Methode.  
  
 `pCodeSize`  
 Ein Zeiger auf die Größe des Codes der Methode (die Anzahl von Bytes des Codes der Methode).  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Methode ist nur mit .NET Native verfügbar.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugSymbolProvider-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
