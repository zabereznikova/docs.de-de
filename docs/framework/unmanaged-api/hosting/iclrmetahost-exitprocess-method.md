---
title: ICLRMetaHost::ExitProcess-Methode
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.ExitProcess
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::ExitProcess
helpviewer_keywords:
- ICLRMetaHost::ExitProcess method [.NET Framework hosting]
- ExitProcess method, ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: b4df98cc-4e4e-407b-b8f4-e0076afef3a4
topic_type:
- apiref
ms.openlocfilehash: 6d601ac3ece801353b630c74ed852c2657f25d7f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730462"
---
# <a name="iclrmetahostexitprocess-method"></a>ICLRMetaHost::ExitProcess-Methode

Versucht, alle geladenen Laufzeiten ordnungsgemäß herunterzufahren, und beendet dann den Vorgang. Ersetzt die [CorExitProcess](corexitprocess-function.md) -Funktion.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ExitProcess (  
    [in] INT32 iExitCode);  
```  
  
## <a name="parameters"></a>Parameter  

 `iExitCode`  
 in Der Exitcode für den Prozess.  
  
## <a name="return-value"></a>Rückgabewert  

 Diese Methode gibt nie zurück, sodass Ihr Rückgabewert nicht definiert ist.  
  
## <a name="remarks"></a>Bemerkungen  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRMetaHost-Schnittstelle](iclrmetahost-interface.md)
- [Hosting](index.md)
