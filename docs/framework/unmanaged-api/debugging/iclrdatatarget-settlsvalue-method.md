---
title: ICLRDataTarget::SetTLSValue-Methode
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.SetTLSValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::SetTLSValue
helpviewer_keywords:
- ICLRDataTarget::SetTLSValue method [.NET Framework debugging]
- SetTLSValue method [.NET Framework debugging]
ms.assetid: 4a2d6a24-749a-47ad-9f01-4517203d3f35
topic_type:
- apiref
ms.openlocfilehash: 6c98fc93fd659ccfc0ccd42eec7d95382cf342f8
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860510"
---
# <a name="iclrdatatargetsettlsvalue-method"></a>ICLRDataTarget::SetTLSValue-Methode
Legt einen Wert im lokalen Thread Speicher (TLS) des angegebenen Threads im Ziel Prozess fest. Diese Methode wird vom Common Language Runtime (CLR)-Datenzugriffs Dienst aufgerufen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [in] CLRDATA_ADDRESS    value  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `threadID`  
 in Der Betriebssystem Bezeichner eines Threads im Ziel Prozess.  
  
 `index`  
 in Der Index des Speicher Orts. Dieser Wert muss ein gültiger Index im lokalen Speicher des angegebenen Threads sein.  
  
 `value`  
 in Ein `CLRDATA_ADDRESS` -Wert, der den Wert angibt, der im angegebenen TLS-Speicherort platziert werden soll.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Writer der Debuganwendung implementiert.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Clrdata. idl, Clrdata. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICLRDataTarget-Schnittstelle](iclrdatatarget-interface.md)
