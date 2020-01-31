---
title: ICorDebugDataTarget2::CreateVirtualUnwinder-Methode
ms.date: 03/30/2017
ms.assetid: 354c8b4c-7d23-45c6-a7d7-3be4c2a5b772
ms.openlocfilehash: 9fc4facda6253d0c68dcf89b2a1b06e639734efe
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788854"
---
# <a name="icordebugdatatarget2createvirtualunwinder-method"></a>ICorDebugDataTarget2::CreateVirtualUnwinder-Methode
Erstellt einen neuen Stapelentlader, der mit dem Entladen bei einem Anfangskontext beginnt (welcher nicht unbedingt das Blatt eines Threads ist).  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CreateVirtualUnwinder(  
    [in] DWORD nativeThreadID,  
    [in] ULONG32 contextFlags,  
    [in] ULONG32 cbContext,  
    [in, size_is(cbContext)] BYTE initialContext[],  
    [out] ICorDebugVirtualUnwinder ** ppUnwinder);  
};  
```  
  
## <a name="parameters"></a>Parameters  
 nativeThreadID  
 [in] Die systemeigene Thread-ID für den Thread, dessen Stapel entladen wird.  
  
 contextFlags  
 [in] Flags, die angeben, welche Teile des Kontexts in `initialContext` definiert sind.  
  
 cbContext  
 [in] Die Größe des `initialContext`.  
  
 initialContext  
 [in] Die Daten im Kontext.  
  
 ppUnwinder  
 [out] Ein Zeiger auf die Adresse eines ICorDebugVirtualUnwinder-Oberflächenobjekts.  
  
## <a name="return-value"></a>Rückgabewert  
 Bei Erfolg `S_OK`. Alle anderen `HRESULT` weisen auf Fehler hin. Alle von "mscordbi empfangenen fehlerhaften `HRESULT` werden als schwerwiegend angesehen und bewirken, dass [ICorDebug](icordebug-interface.md) -Methoden `CORDBG_E_DATA_TARGET_ERROR`zurückgeben.  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Methode ist nur mit .NET Native verfügbar.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugDataTarget2-Schnittstelle](icordebugdatatarget2-interface.md)
- [Debuggen von Schnittstellen](debugging-interfaces.md)
