---
title: ICLRDataTarget2::AllocVirtual-Methode
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2.AllocVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2::AllocVirtual
helpviewer_keywords:
- ICLRDataTarget2::AllocVirtual method [.NET Framework debugging]
- AllocVirtual method [.NET Framework debugging]
ms.assetid: e3226230-964b-47fb-9f53-d6fdbeda1e9e
topic_type:
- apiref
ms.openlocfilehash: 20b73549d30fe210e4d44902d2f459ea9c682360
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860492"
---
# <a name="iclrdatatarget2allocvirtual-method"></a>ICLRDataTarget2::AllocVirtual-Methode
Wird von den Common Language Runtime (CLR)-Datenzugriffs Diensten aufgerufen, um Speicher im Adressraum dieses Ziel Prozesses zuzuordnen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT AllocVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags,  
    [in] ULONG32 protectFlags,  
    [out] CLRDATA_ADDRESS* virt  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `addr`  
 in Ein `CLRDATA_ADDRESS` -Wert, der die angeforderte Startadresse des zugeordneten Speichers angibt.  
  
 `size`  
 in Die Größe des zugeordneten Speichers in Byte.  
  
 `typeFlags`  
 in Flags, die die Speicher Belegung steuern. Siehe die Win32 `VirtualAlloc` -Funktion.  
  
 `protectFlags`  
 in Die Schutz Attribute für den zugewiesenen Arbeitsspeicher. Siehe die Win32 `VirtualAlloc` -Funktion.  
  
 `virt`  
 vorgenommen Ein Zeiger auf einen `CLRDATA_ADDRESS` -Wert, der die tatsächliche Startadresse des zugeordneten Speichers angibt.  
  
## <a name="remarks"></a>Hinweise  
 Die `AllocVirtual` -Methode dient als logischer Wrapper für die Win32 `VirtualAlloc` -Funktion.  
  
 Diese Methode wird vom Writer der Debuganwendung implementiert.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Clrdata. idl, Clrdata. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICLRDataTarget2-Schnittstelle](iclrdatatarget2-interface.md)
- [FreeVirtual-Methode](iclrdatatarget2-freevirtual-method.md)
