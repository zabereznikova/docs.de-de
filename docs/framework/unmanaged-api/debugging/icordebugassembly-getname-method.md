---
title: ICorDebugAssembly::GetName-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetName
helpviewer_keywords:
- ICorDebugAssembly::GetName method [.NET Framework debugging]
- GetName method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: cdeda721-b214-4503-a291-c70b68b5f36b
topic_type:
- apiref
ms.openlocfilehash: 3794a3b308bd5c96a38337d8b81e61167e4dc988
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734048"
---
# <a name="icordebugassemblygetname-method"></a>ICorDebugAssembly::GetName-Methode

Ruft den Namen der Assembly ab, die diese `ICorDebugAssembly` Instanz darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetName (  
    [in] ULONG32  cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `cchName`  
 [in] Die Größe des `szName`-Arrays.  
  
 `pcchName`  
 vorgenommen Ein Zeiger auf eine ganze Zahl, die die tatsächliche Länge des Namens angibt.  
  
 `szName`  
 vorgenommen Ein Array, in dem der Name gespeichert wird.  
  
## <a name="remarks"></a>Hinweise  

 Die `GetName` -Methode gibt den vollständigen Pfad und den Dateinamen der Assembly zurück.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
