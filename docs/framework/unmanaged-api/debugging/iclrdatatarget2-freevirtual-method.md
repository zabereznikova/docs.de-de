---
title: ICLRDataTarget2::FreeVirtual-Methode
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2.FreeVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2::FreeVirtual
helpviewer_keywords:
- ICLRDataTarget::FreeVirtual method [.NET Framework debugging]
- FreeVirtual method [.NET Framework debugging]
ms.assetid: 26fb69f8-1467-4711-bd24-cb117c63938f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b30bd3e97af8d222f629c5b4f9f318a9b6379e78
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697952"
---
# <a name="iclrdatatarget2freevirtual-method"></a>ICLRDataTarget2::FreeVirtual-Methode
Wird aufgerufen, durch die common Language Runtime (CLR) Datenzugriffsdiensten der um Arbeitsspeicher freizugeben, der zuvor im Adressbereich des Zielprozesses zugewiesen wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT FreeVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `addr`  
 [in] Ein `CLRDATA_ADDRESS` Wert, der angibt, die Startadresse des Arbeitsspeichers freigegeben werden.  
  
 `size`  
 [in] Die Größe in Bytes, des Arbeitsspeichers freigegeben werden.  
  
 `typeFlags`  
 [in] Flags, die das Freigeben von Arbeitsspeicher zu steuern. Finden Sie unter Win32 `VirtualFree` Funktion.  
  
## <a name="remarks"></a>Hinweise  
 Die `FreeVirtual` Methode dient als ein logischer Wrapper für die Win32- `VirtualFree` Funktion.  
  
 Diese Methode wird vom Writer der Debuganwendung implementiert.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** ClrData.idl, ClrData.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRDataTarget2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)
- [AllocVirtual-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-allocvirtual-method.md)
