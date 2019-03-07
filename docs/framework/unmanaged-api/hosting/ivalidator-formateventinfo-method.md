---
title: IValidator::FormatEventInfo-Methode
ms.date: 03/30/2017
api_name:
- IValidator.FormatEventInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FormatEventInfo
helpviewer_keywords:
- IValidator::FormatEventInfo method [.NET Framework hosting]
- FormatEventInfo method, IValidator interface [.NET Framework hosting]
ms.assetid: 4c0c7477-05ba-461b-b21b-cbfba95f1db1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 084b80e90ea3950245606c56de7ed3e18fd27662
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57486432"
---
# <a name="ivalidatorformateventinfo-method"></a>IValidator::FormatEventInfo-Methode
Ruft die Fehlermeldung, die für den angegebenen Validierungsfehler ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT FormatEventInfo(  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `hVECode`  
 [in] Der HRESULT-Wert, der an den Fehlerhandler für die Überprüfung übergeben wurde.  
  
 `Context`  
 [in] Ein `VEContext` -Instanz, die Kontextinformationen zum Validierungsfehler enthält.  
  
 `msg`  
 [in, out] Eine Zeichenfolge, die die zurückgegebene Fehlermeldung enthält.  
  
 `ulMaxLength`  
 [in] Die maximale Länge der Fehlermeldung.  
  
 `psa`  
 [in] Ein sicheres Array, das zusätzliche Parameter, die Beschreibung des Fehlers enthält.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** IValidator.idl, IValidator.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

