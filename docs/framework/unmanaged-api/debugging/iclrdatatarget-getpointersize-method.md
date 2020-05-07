---
title: ICLRDataTarget::GetPointerSize-Methode
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetPointerSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetPointerSize
helpviewer_keywords:
- GetPointerSize method [.NET Framework debugging]
- ICLRDataTarget::GetPointerSize method [.NET Framework debugging]
ms.assetid: 51d9f4a4-81a7-4527-8537-5212bdb05c70
topic_type:
- apiref
ms.openlocfilehash: e6c4d5f8cc911198add176cab9c4b9b89128068e
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860625"
---
# <a name="iclrdatatargetgetpointersize-method"></a>ICLRDataTarget::GetPointerSize-Methode
Ruft die Größe (in Bytes) des Zeiger Typs ab, der vom Ziel Prozess verwendet wird. Diese Methode wird vom Common Language Runtime Data Access Services aufgerufen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetPointerSize (  
    [out] ULONG32     *pointerSize  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pointerSize`  
 vorgenommen Ein Zeiger auf einen ganzzahligen Wert, der die Größe eines Zeigers auf dem Ziel Prozess in Bytes angibt.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Writer der Debuganwendung implementiert.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Clrdata. idl, Clrdata. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICLRDataTarget-Schnittstelle](iclrdatatarget-interface.md)
