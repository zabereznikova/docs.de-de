---
title: ICLRDataTarget::GetTLSValue-Methode
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetTLSValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetTLSValue
helpviewer_keywords:
- GetTLSValue method [.NET Framework debugging]
- ICLRDataTarget::GetTLSValue method [.NET Framework debugging]
ms.assetid: 0d8a7730-edc9-4728-898f-41b219cf5a28
topic_type:
- apiref
ms.openlocfilehash: 141dc8632812ab4a2ce82864cde56337025baa28
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860584"
---
# <a name="iclrdatatargetgettlsvalue-method"></a>ICLRDataTarget::GetTLSValue-Methode
Ruft einen Wert aus dem lokalen Thread Speicher (TLS) des angegebenen Threads im Ziel Prozess ab. Diese Methode wird vom Common Language Runtime (CLR)-Datenzugriffs Dienst aufgerufen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [out] CLRDATA_ADDRESS   *value  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `threadID`  
 in Der Betriebssystem Bezeichner eines Threads im Ziel Prozess.  
  
 `index`  
 in Der Index des Speicher Orts. Dieser Wert muss ein gültiger Index im lokalen Speicher des angegebenen Threads sein.  
  
 `value`  
 vorgenommen Ein Zeiger auf einen `CLRDATA_ADDRESS` -Wert, der den Wert angibt, der vom angegebenen TLS-Speicherort zurückgegeben wird.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Writer der Debuganwendung implementiert.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Clrdata. idl, Clrdata. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICLRDataTarget-Schnittstelle](iclrdatatarget-interface.md)
