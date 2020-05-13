---
title: ICorDebugStaticFieldSymbol::GetAddress-Methode
ms.date: 03/30/2017
ms.assetid: 5a6c9a5a-ec72-4c40-a9c3-cee7baa63687
ms.openlocfilehash: 7b8072234df172eeafd77db90287ea3319c08ec7
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378764"
---
# <a name="icordebugstaticfieldsymbolgetaddress-method"></a>ICorDebugStaticFieldSymbol::GetAddress-Methode
Ruft die Adresse eines statischen Felds ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetAddress(  
   [out] CORDB_ADDRESS *pRVA  
);  
```  
  
## <a name="parameters"></a>Parameter  
 pRVA  
 [out] Ein Zeiger auf die relative virtuelle Adresse (RVA) des statischen Felds.  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Methode ist nur mit .NET Native verfügbar.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugStaticFieldSymbol-Schnittstelle](icordebugstaticfieldsymbol-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
