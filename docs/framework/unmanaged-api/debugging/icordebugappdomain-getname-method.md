---
title: ICorDebugAppDomain::GetName-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetName
helpviewer_keywords:
- ICorDebugAppDomain::GetName method [.NET Framework debugging]
- GetName method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 02c596d7-00b0-4e2c-856b-5425158fcefd
topic_type:
- apiref
ms.openlocfilehash: 2c9aa6792885c685195049948a540453b1f5235e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73110311"
---
# <a name="icordebugappdomaingetname-method"></a>ICorDebugAppDomain::GetName-Methode
Ruft den Namen der Anwendungsdomäne ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32           cchName,  
    [out] ULONG32           *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
         WCHAR              szName[]  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `cchName`  
 [in] Die Größe des `szName`-Arrays. Legen Sie diesen Wert auf NULL fest, um diese Methode in den Abfrage Modus zu versetzen.  
  
 `pcchName`  
 vorgenommen Ein Zeiger auf die Größe des Namens oder die Anzahl der Zeichen, die tatsächlich in `szName`zurückgegeben werden. Im Abfrage Modus kann der Aufrufer mit diesem Wert ermitteln, wie groß ein Puffer ist, der für den Namen zuzuordnen ist.  
  
 `szName`  
 vorgenommen Ein Array, in dem der Name der Anwendungsdomäne gespeichert wird.  
  
## <a name="remarks"></a>Hinweise  
 Ein Debugger ruft die `GetName`-Methode einmal auf, um die Größe eines Puffers zu erhalten, der für den Namen benötigt wird. Der-Debugger ordnet den Puffer zu und ruft dann die-Methode ein zweites Mal auf, um den Puffer zu füllen. Der erste-Befehl, um die Größe des Namens abzurufen, wird als *Abfrage Modus*bezeichnet.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
