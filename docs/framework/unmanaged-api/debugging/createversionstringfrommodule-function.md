---
title: CreateVersionStringFromModule-Funktion
ms.date: 03/30/2017
api_name:
- CreateVersionStringFromModule
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- CreateVersionStringFromModule
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
- CreateVersionStringFromModule function
ms.assetid: 3d2fe9bd-75ef-4364-84a6-da1e1994ac1a
topic_type:
- apiref
ms.openlocfilehash: 609d6e47c951aa104cb23084b65e98827a6851f1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789176"
---
# <a name="createversionstringfrommodule-function"></a>CreateVersionStringFromModule-Funktion
Erstellt eine Versionszeichenfolge aus einem CLR-Pfad (Common Language Runtime) in einem Zielprozess.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CreateVersionStringFromModule (  
    [in]  DWORD      pidDebuggee,  
    [in]  LPCWSTR    szModuleName,  
    [out, size_is(cchBuffer),  
          length_is(*pdwLength)] LPWSTR Buffer,  
    [in]  DWORD      cchBuffer,  
    [out] DWORD*     pdwLength  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `pidDebuggee`  
 [in] Bezeichner des Prozesses, in den die Ziel-CLR geladen wird.  
  
 `szModuleName`  
 [in] Vollständiger oder relativer Pfad zur im Prozess geladenen Ziel-CLR.  
  
 `pBuffer`  
 [out] Rückgabepuffer zum Speichern der Versionszeichenfolge für die Ziel-CLR.  
  
 `cchBuffer`  
 [in] Größe von `pBuffer`.  
  
 `pdwLength`  
 [out] Länge der von `pBuffer` zurückgegebenen Versionszeichenfolge.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK  
 Die Versionszeichenfolge für die Ziel-CLR wurde erfolgreich in `pBuffer` zurückgegeben.  
  
 E_INVALIDARG  
 `szModuleName` ist NULL, oder `pBuffer` oder `cchBuffer` ist NULL. `pBuffer` und `cchBuffer` müssen beide NULL oder nicht NULL sein.  
  
 HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)  
 `pdwLength` ist größer als `cchBuffer`. Dies kann ein erwartetes Ergebnis sein, wenn Sie NULL für `pBuffer` und `cchBuffer` übergeben haben und die erforderliche Puffergröße mithilfe von `pdwLength` abgefragt haben.  
  
 HRESULT_FROM_WIN32(ERROR_MOD_NOT_FOUND)  
 `szModuleName` enthält keinen Pfad zu einer gültigen CLR im Zielprozess.  
  
 E_FAIL (oder andere E_-Rückgabecodes)  
 `pidDebuggee` verweist auf keinen gültigen Prozess, oder anderer Fehler,  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion akzeptiert einen CLR-Prozess, der von `pidDebuggee` und einem Zeichenfolgepfad identifiziert wird, der durch `szModuleName` angegeben wird. Die Versionszeichenfolge wird im Puffer zurückgegeben, auf den `pBuffer` zeigt. Diese Zeichenfolge ist für den Funktionsbenutzer nicht transparent. Das heißt, gibt es keine systeminterne Bedeutung in der Versionszeichenfolge selbst. Sie wird nur im Kontext dieser Funktion und der Funktion "| [atedebugginginterfakefromversion](createdebugginginterfacefromversion-function-for-silverlight.md)" verwendet.  
  
 Diese Funktion sollte zweimal aufgerufen werden. Übergeben Sie beim ersten Aufruf NULL für `pBuffer` und `cchBuffer`. In diesem Fall wird die für `pBuffer` erforderliche Größe des Puffers in `pdwLength` zurückgegeben. Sie können dann die Funktion ein zweites Mal aufrufen und den Puffer in `pBuffer` und dessen Größe in `cchBuffer` übergeben.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** dbgshim. h  
  
 **Bibliothek:** dbgshim. dll  
  
 **.NET Framework Versionen:** 3,5 SP1
