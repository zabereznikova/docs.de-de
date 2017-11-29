---
title: IValidator::Validate-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IValidator.Validate
api_location: mscoree.dll
api_type: COM
f1_keywords: Validate
helpviewer_keywords:
- IValidator::Validate method [.NET Framework hosting]
- Validate method, IValidator interface [.NET Framework hosting]
ms.assetid: 7d68666a-fb73-4455-bebd-908d49a16abc
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 722c6acc7e152a78ba28bc2730b2fdc7e0c45eb0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ivalidatorvalidate-method"></a>IValidator::Validate-Methode
Überprüft die angegebene Datei (portable Executable) oder Microsoft intermediate Language (MSIL)-Datei.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Validate (  
    [in] IVEHandler            *veh,  
    [in] IUnknown              *pAppDomain,  
    [in] unsigned long          ulFlags,  
    [in] unsigned long          ulMaxError,  
    [in] unsigned long          token,  
    [in] LPWSTR                 fileName,  
    [in, size_is(ulSize)] BYTE *pe,  
    [in] unsigned long          ulSize  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `veh`  
 [in] Ein Zeiger auf eine `IVEHandler` -Instanz, die Validierungsfehler behandelt.  
  
 `pAppDomain`  
 [in] Ein Zeiger auf die Anwendungsdomäne, in der die Datei geladen wird.  
  
 `ulFlags`  
 [in] Eine bitweise Kombination von [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) Werte, der angibt, die Überprüfungen, die ausgeführt werden soll.  
  
 `ulMaxError`  
 [in] Die maximale Anzahl von Fehlern, um zuzulassen, bevor Sie die Überprüfung beendet werden soll.  
  
 `token`  
 [in] Nicht verwendet.  
  
 `fileName`  
 [in] Eine Zeichenfolge, die den Namen der zu überprüfenden Datei angibt.  
  
 `pe`  
 [in] Ein Zeiger auf die Speicherpuffer in dem die Datei gespeichert ist.  
  
 `ulSize`  
 [in] Die Größe in Bytes der Datei überprüft werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** IValidator.idl, IValidator.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 
