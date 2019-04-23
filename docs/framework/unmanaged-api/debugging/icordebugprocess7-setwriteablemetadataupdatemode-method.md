---
title: ICorDebugProcess7::SetWriteableMetadataUpdateMode-Methode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugProcess7.SetWriteableMetadataUpdateMode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 8589bba7-7304-45ba-9e31-7bf43dfd5c19
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 94e2f1c13c91c50daa5730898adf0aedf00f6579
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59092616"
---
# <a name="icordebugprocess7setwriteablemetadataupdatemode-method"></a>ICorDebugProcess7::SetWriteableMetadataUpdateMode-Methode
[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]  
  
 Konfiguriert, wie der Debugger speicherinterne Aktualisierungen von Metadaten innerhalb des Zielprozesses behandelt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT SetWriteableMetadataUpdateMode(  
   WriteableMetadataUpdateMode flags  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `flags`  
 Ein [WriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/writeablemetadataupdatemode-enumeration.md) -Enumerationswert, der angibt, ob in-Memory-Aktualisierungen von Metadaten im Zielprozess sichtbar sind (`WriteableMetadataUpdateMode::AlwaysShowUpdates`) oder nicht sichtbar (`WriteableMetadataUpdateMode::LegacyCompatPolicy`) an den Debugger.  
  
## <a name="remarks"></a>Hinweise  
 Aktualisierungen von Metadaten im Zielprozess können durch Bearbeiten und Fortfahren, einen Profiler oder <xref:System.Reflection.Emit?displayProperty=nameWithType> ausgelöst werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugProcess7-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
