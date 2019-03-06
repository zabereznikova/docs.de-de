---
title: ISymUnmanagedSourceServerModule::GetSourceServerData-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSourceServerModule.GetSourceServerData
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSourceServerModule::GetSourceServerData
helpviewer_keywords:
- ISymUnmanagedSourceServerModule::GetSourceServerData method [.NET Framework debugging]
- GetSourceServerData method [.NET Framework debugging]
ms.assetid: 20bdf8ff-2d15-4c64-8950-6888f642d6c0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 69e83a5ff489881938c1e8410f765fd63f3b5d84
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479440"
---
# <a name="isymunmanagedsourceservermodulegetsourceserverdata-method"></a>ISymUnmanagedSourceServerModule::GetSourceServerData-Methode
Gibt die Quelldaten für die Server für das Modul zurück. Der Aufrufer muss Ressourcen freigeben, mithilfe von `CoTaskMemFree`.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetSourceServerData(  
    [out] ULONG* pDataByteCount,   
    [out, size_is (, *pDataByteCount)] BYTE** ppData);  
```  
  
## <a name="parameters"></a>Parameter  
 `pDataByteCount`  
 [out] Ein Zeiger auf eine `ULONG32` , der die Größe in Bytes der Source Server-Daten empfängt.  
  
 `ppData`  
 [out] Ein Zeiger auf das zurückgegebene `pDataByteCount` Wert.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch
- [ISymUnmanagedSourceServerModule-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)
