---
title: ICorDebugMergedAssemblyRecord::GetCulture-Methode
ms.date: 03/30/2017
ms.assetid: 030b2f8c-8c21-40b7-855d-3afa78975a17
ms.openlocfilehash: 636d0fd25d345f513e00504b9eb5adb4f0c03b0f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710648"
---
# <a name="icordebugmergedassemblyrecordgetculture-method"></a>ICorDebugMergedAssemblyRecord::GetCulture-Methode

Ruft die Kulturnamen-Zeichenfolge der Assembly ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetCulture(  
   [in] ULONG32 cchCulture,
   [out] ULONG32 *pcchCulture,
   [out, size_is(cchCulture), length_is(*pcchCulture)] WCHAR szCulture[]  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `cchCulture`  
 [in] Die Anzahl der Zeichen im `szCulture`-Puffer.  
  
 `pcchCulture`  
 [out] Die Anzahl der tatsächlich in den `szCulture`-Puffer geschriebenen Zeichen.  
  
 `szCulture`  
 [out] Ein Zeichenarray, das den Kulturnamen enthält.  
  
## <a name="remarks"></a>Hinweise  

 Der Kulturname ist eine eindeutige Zeichenfolge, die eine Kultur identifiziert, z. B. "en-US" (für die Kultur Englisch (USA)), oder "neutral" (für eine neutrale Kultur).  
  
> [!NOTE]
> Diese Methode ist nur mit .NET Native verfügbar.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugMergedAssemblyRecord-Schnittstelle](icordebugmergedassemblyrecord-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
