---
title: ICorDebugNativeFrame::GetLocalDoubleRegisterValue-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalDoubleRegisterValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalDoubleRegisterValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalDoubleRegisterValue method [.NET Framework debugging]
- GetLocalDoubleRegisterValue method [.NET Framework debugging]
ms.assetid: 1f838215-ac8a-434f-8ce6-03021d3098d9
topic_type:
- apiref
ms.openlocfilehash: a45061b6a3105565fdbb36173731b3c3dfe5aa4f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137295"
---
# <a name="icordebugnativeframegetlocaldoubleregistervalue-method"></a>ICorDebugNativeFrame::GetLocalDoubleRegisterValue-Methode
Ruft den Wert eines Arguments oder einer lokalen Variablen ab, das in den beiden angegebenen Registern für diesen systemeigenen Frame gespeichert ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetLocalDoubleRegisterValue (  
    [in] CorDebugRegister   highWordReg,  
    [in] CorDebugRegister   lowWordReg,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `highWordReg`  
 in Ein Wert der CorDebugRegister-Enumeration, der das Register angibt, das das höchst Wort des Werts enthält.  
  
 `lowWordReg`  
 in Ein Wert der `CorDebugRegister`-Enumeration, die das Register mit dem unteren Wort des Werts angibt.  
  
 `cbSigBlob`  
 in Eine ganze Zahl, die die Größe der binären Metadatensignatur angibt, auf die vom `pvSigBlob`-Parameter verwiesen wird.  
  
 `pvSigBlob`  
 in Ein `PCCOR_SIGNATURE` Wert, der auf die binäre Metadatensignatur des Werttyps zeigt.  
  
 `ppValue`  
 vorgenommen Ein Zeiger auf die Adresse eines icorentbugvalue-Objekts, das den abgerufenen Wert darstellt, der in den angegebenen Registern gespeichert ist.  
  
## <a name="remarks"></a>Hinweise  
 Die `GetLocalDoubleRegisterValue`-Methode kann entweder in einem nativen Frame oder einem JIT-kompilierten Frame (Just-in-Time) verwendet werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
