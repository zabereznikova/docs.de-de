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
ms.openlocfilehash: 1fb701a40abe2dc6e51443837c07ee5ba05ddfbe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723648"
---
# <a name="iclrdatatarget2freevirtual-method"></a>ICLRDataTarget2::FreeVirtual-Methode

Wird von den Common Language Runtime (CLR)-Datenzugriffs Diensten aufgerufen, um Arbeitsspeicher freizugeben, der zuvor im Adressraum des Ziel Prozesses belegt wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT FreeVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `addr`  
 in Ein- `CLRDATA_ADDRESS` Wert, der die Startadresse des frei zufügenden Speichers angibt.  
  
 `size`  
 in Die Größe des frei zufügenden Speichers in Byte.  
  
 `typeFlags`  
 in Flags, die die Freigabe von Arbeitsspeicher steuern. Siehe die Win32- `VirtualFree` Funktion.  
  
## <a name="remarks"></a>Hinweise  

 Die- `FreeVirtual` Methode dient als logischer Wrapper für die Win32- `VirtualFree` Funktion.  
  
 Diese Methode wird vom Writer der Debuganwendung implementiert.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Clrdata. idl, Clrdata. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRDataTarget2-Schnittstelle](iclrdatatarget2-interface.md)
- [AllocVirtual-Methode](iclrdatatarget2-allocvirtual-method.md)
