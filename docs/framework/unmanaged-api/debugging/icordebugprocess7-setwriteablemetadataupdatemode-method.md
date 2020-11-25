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
ms.openlocfilehash: 5671f8cb51210c27dffdedba28b4b145b3fedc55
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732553"
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
 Ein [WriteableMetadataUpdateMode](writeablemetadataupdatemode-enumeration.md) -Enumerationswert, der angibt, ob Speicher interne Aktualisierungen von Metadaten im Ziel Prozess `WriteableMetadataUpdateMode::AlwaysShowUpdates` für den Debugger sichtbar () oder nicht sichtbar ( `WriteableMetadataUpdateMode::LegacyCompatPolicy` ) sind.  
  
## <a name="remarks"></a>Hinweise  

 Aktualisierungen von Metadaten im Zielprozess können durch Bearbeiten und Fortfahren, einen Profiler oder <xref:System.Reflection.Emit?displayProperty=nameWithType> ausgelöst werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugProcess7-Schnittstelle](icordebugprocess7-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
