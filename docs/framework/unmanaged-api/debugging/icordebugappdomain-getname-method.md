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
ms.openlocfilehash: 3db37576f5da7b26e7bd9d3343f8bb8b97f2ba82
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895236"
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
 vorgenommen Ein Zeiger auf die Größe des Namens oder die Anzahl von Zeichen, die tatsächlich in `szName`zurückgegeben werden. Im Abfrage Modus kann der Aufrufer mit diesem Wert ermitteln, wie groß ein Puffer ist, der für den Namen zuzuordnen ist.  
  
 `szName`  
 vorgenommen Ein Array, in dem der Name der Anwendungsdomäne gespeichert wird.  
  
## <a name="remarks"></a>Hinweise  
 Ein Debugger ruft die `GetName` -Methode einmal auf, um die Größe eines Puffers zu erhalten, der für den Namen benötigt wird. Der-Debugger ordnet den Puffer zu und ruft dann die-Methode ein zweites Mal auf, um den Puffer zu füllen. Der erste-Befehl, um die Größe des Namens abzurufen, wird als *Abfrage Modus*bezeichnet.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
