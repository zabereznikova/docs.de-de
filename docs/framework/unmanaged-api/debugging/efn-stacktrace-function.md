---
title: _EFN_StackTrace-Funktion
ms.date: 03/30/2017
api_name:
- _EFN_StackTrace
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_StackTrace
helpviewer_keywords:
- _EFN_StackTrace function [.NET Framework debugging]
ms.assetid: caea7754-867c-4360-a65c-5ced4408fd9d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9035d9a53c4b0c8822b79e641aef092b4a48c418
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2019
ms.locfileid: "70895046"
---
# <a name="_efn_stacktrace-function"></a>\_EFN\_StackTrace-Funktion
Stellt eine Textdarstellung einer verwalteten Stapelüberwachung und ein Array von `CONTEXT`-Datensätzen bereit, einen Datensatz für jeden Übergang zwischen nicht verwaltetem und verwaltetem Code.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CALLBACK _EFN_StackTrace(  
    [in]  PDEBUG_CLIENT  Client,  
    [out] WCHAR          wszTextOut[],  
    [out] size_t         *puiTextLength,  
    [out] LPVOID         pTransitionContexts,  
    [out] size_t         *puiTransitionContextCount,  
    [in]  size_t         uiSizeOfContext,  
    [in]  DWORD          Flags  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `Client`  
 in Der Client, der deentschlgt wird.  
  
 `wszTextOut`  
 vorgenommen Die Textdarstellung der Stapel Überwachung.  
  
 `puiTextLength`  
 vorgenommen Ein Zeiger auf die Anzahl von Zeichen in `wszTextOut`.  
  
 `pTransitionContexts`  
 vorgenommen Das Array von Übergangs Kontexten.  
  
 `puiTransitionContextCount`  
 vorgenommen Ein Zeiger auf die Anzahl der Übergangs Kontexte im Array.  
  
 `uiSizeOfContext`  
 in Die Größe der Kontext Struktur.  
  
 `Flags`  
 in Legen Sie entweder auf 0 oder SOS_STACKTRACE_SHOWADDRESSES (0x01) fest, um das EBP-Register und den Eingabe Stapelzeiger (ESP) vor `module!functionname` jeder Zeile anzuzeigen.  
  
## <a name="remarks"></a>Hinweise  
 Die `_EFN_StackTrace` Struktur kann von einer WinDbg-programmgesteuerten Schnittstelle aufgerufen werden. Parameter werden wie folgt verwendet:  
  
- Wenn `wszTextOut` NULL ist und `puiTextLength` nicht NULL ist, gibt die Funktion die Zeichen folgen Länge `puiTextLength`in zurück.  
  
- Wenn `wszTextOut` nicht NULL ist, speichert die Funktion Text in `wszTextOut` bis zu dem Speicherort, `puiTextLength`der von angegeben wird. Es wird erfolgreich zurückgegeben, wenn genügend Platz im Puffer vorhanden ist, oder gibt E_OUTOFMEMORY zurück, wenn der Puffer nicht lang genug ist.  
  
- Der Übergangsteil der Funktion wird ignoriert, wenn `pTransitionContexts` und `puiTransitionContextCount` beide NULL sind. In diesem Fall stellt die-Funktion Aufrufern nur die Textausgabe der Funktionsnamen bereit.  
  
- Wenn `pTransitionContexts` NULL ist und `puiTransitionContextCount` nicht NULL ist, gibt die-Funktion die erforderliche Anzahl von Kontext Einträgen `puiTransitionContextCount`in zurück.  
  
- Wenn `pTransitionContexts` nicht NULL ist, behandelt die Funktion Sie als Array von Längen `puiTransitionContextCount`-Strukturen. Die Struktur Größe wird von `uiSizeOfContext`angegeben, und es muss sich um die Größe von [SimpleContext](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) oder `CONTEXT` für die-Architektur handeln.  
  
- `wszTextOut`wird im folgenden Format geschrieben:  
  
    ```output  
    "<ModuleName>!<Function Name>[+<offset in hex>]  
    ...  
    (TRANSITION)  
    ..."  
    ```  
  
- Wenn der Offset in Hex 0x0 ist, wird kein Offset geschrieben.  
  
- Wenn im Thread derzeit kein verwalteter Code vorhanden ist, gibt die Funktion SOS_E_NOMANAGEDCODE zurück.  
  
- Der `Flags` -Parameter ist entweder 0 oder SOS_STACKTRACE_SHOWADDRESSES, um EBP und ESP vor jeder `module!functionname` Zeile anzuzeigen. Standardmäßig ist der Wert 0.  
  
    ```cpp  
    #define SOS_STACKTRACE_SHOWADDRESSES   0x00000001  
    ```  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** SOS_Stacktrace.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von globalen statischen Funktionen](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
