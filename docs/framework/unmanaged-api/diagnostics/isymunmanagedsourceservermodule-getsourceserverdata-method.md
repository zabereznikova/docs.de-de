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
ms.openlocfilehash: 6904271ed90cf733b9221178927bc680d76b58a6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176577"
---
# <a name="isymunmanagedsourceservermodulegetsourceserverdata-method"></a>ISymUnmanagedSourceServerModule::GetSourceServerData-Methode
Gibt die Quellserverdaten für das Modul zurück. Der Aufrufer muss Ressourcen `CoTaskMemFree`mithilfe von freimachen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetSourceServerData(  
    [out] ULONG* pDataByteCount,
    [out, size_is (, *pDataByteCount)] BYTE** ppData);  
```  
  
## <a name="parameters"></a>Parameter  
 `pDataByteCount`  
 [out] Ein Zeiger auf `ULONG32` eine, der die Größe der Quellserverdaten in Bytes empfängt.  
  
 `ppData`  
 [out] Ein Zeiger auf `pDataByteCount` den zurückgegebenen Wert.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, ob die Methode erfolgreich ist. andernfalls E_FAIL oder einem anderen Fehlercode.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Kopfzeile:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Weitere Informationen

- [ISymUnmanagedSourceServerModule-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)
