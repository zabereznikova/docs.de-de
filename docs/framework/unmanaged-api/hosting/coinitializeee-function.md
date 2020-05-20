---
title: CoInitializeEE-Funktion
ms.date: 03/30/2017
api_name:
- CoInitializeEE
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoInitializeEE
helpviewer_keywords:
- CoInitializeEE function [.NET Framework hosting]
ms.assetid: 7e42a928-5068-4ba6-b8c3-806551a01fa8
topic_type:
- apiref
ms.openlocfilehash: 57508a2df3a49c39d25347f2a3038442c37278da
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616761"
---
# <a name="coinitializeee-function"></a>CoInitializeEE-Funktion
Stellt sicher, dass die Common Language Runtime Ausführungs-Engine in einen Prozess geladen wird. Diese Funktion ist in der .NET Framework 4 veraltet. Verwenden Sie stattdessen die [ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md) -Methode.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CoInitializeEE (  
   [in] DWORD fFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `fFlags`  
 in Eine der [COINITIEE](../metadata/coinitiee-enumeration.md) -Enumerationskonstanten.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt in WinError. h definierte Standard-COM-Fehlercodes und die Werte in der folgenden Tabelle zurück.  
  
|Rückgabecode|BESCHREIBUNG|  
|-----------------|-----------------|  
|S_OK|Die Ausführungs-Engine wurde erfolgreich geladen.|  
|S_FALSE|Die Ausführungs-Engine ist bereits geladen.|  
|E_FAIL|Die Ausführungs-Engine konnte nicht geladen werden.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode lädt die Ausführungs-Engine, wenn Sie noch nicht geladen wurde.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Globale statische Metadatenfunktionen](../metadata/metadata-global-static-functions.md)
