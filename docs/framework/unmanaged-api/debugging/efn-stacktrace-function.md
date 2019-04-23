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
ms.openlocfilehash: dfbdbb389f9945ffeea649bcddd45bee8caf2496
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59119989"
---
# <a name="efnstacktrace-function"></a>_EFN_StackTrace-Funktion
Stellt eine Textdarstellung einer verwalteten Stapelüberwachung und ein Array von `CONTEXT`-Datensätzen bereit, einen Datensatz für jeden Übergang zwischen nicht verwaltetem und verwaltetem Code.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
 [in] Der Client, der gedebuggt wird.  
  
 `wszTextOut`  
 [out] Der Text-Darstellung der stapelüberwachung.  
  
 `puiTextLength`  
 [out] Ein Zeiger auf die Anzahl der Zeichen in `wszTextOut`.  
  
 `pTransitionContexts`  
 [out] Das Array von Übergang Kontexte.  
  
 `puiTransitionContextCount`  
 [out] Ein Zeiger auf die Anzahl der von Übergangskontexten im Array.  
  
 `uiSizeOfContext`  
 [in] Die Größe der Context-Struktur.  
  
 `Flags`  
 [in] Auf 0 oder SOS_STACKTRACE_SHOWADDRESSES (0 x 01) festgelegt, um die EBP-Register und die EINGABETASTE Stack Pointer (ESP) vor jeder `module!functionname` Zeile.  
  
## <a name="remarks"></a>Hinweise  
 Die `_EFN_StackTrace` Struktur kann von einer programmgesteuerten Schnittstelle von WinDbg aufgerufen werden. Parameter werden wie folgt verwendet:  
  
-   Wenn `wszTextOut` ist null und `puiTextLength` ist nicht null ist, die Funktion gibt die Länge der Zeichenfolge in `puiTextLength`.  
  
-   Wenn `wszTextOut` ist nicht null ist, speichert die Funktion Text in `wszTextOut` bis zu dessen Speicherort vom `puiTextLength`. Es zurückgegeben war es genügend Platz im Puffer oder E_OUTOFMEMORY zurückgegeben, wenn der Puffer nicht groß genug war erfolgreich.  
  
-   Der Übergangsteil der Funktion wird ignoriert, wenn `pTransitionContexts` und `puiTransitionContextCount` beide null sind. In diesem Fall stellt die Funktion Aufrufern nur die Funktionsnamen Textausgabe.  
  
-   Wenn `pTransitionContexts` ist null und `puiTransitionContextCount` ist nicht null ist, gibt die Funktion die erforderliche Anzahl von Kontext-Einträge im `puiTransitionContextCount`.  
  
-   Wenn `pTransitionContexts` ist nicht null ist, die Funktion behandelt es als ein Array von Strukturen der Länge `puiTransitionContextCount`. Die Größe der Struktur erhält von `uiSizeOfContext`, muss die Größe des [SimpleContext](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) oder `CONTEXT` für die Architektur.  
  
-   `wszTextOut` Im folgenden Format geschrieben:  
  
    ```  
    "<ModuleName>!<Function Name>[+<offset in hex>]  
    ...  
    (TRANSITION)  
    ..."  
    ```  
  
-   Wenn der Offset in hexadezimal 0 x 0 ist, wird kein Offset geschrieben.  
  
-   Es ist kein verwalteter Code für den Thread aktuell im Kontext, gibt die Funktion SOS_E_NOMANAGEDCODE zurück.  
  
-   Die `Flags` Parameter ist entweder 0 oder SOS_STACKTRACE_SHOWADDRESSES um EBP und ESP vor jeder `module!functionname` Zeile. Standardmäßig ist es 0.  
  
    ```  
    #define SOS_STACKTRACE_SHOWADDRESSES   0x00000001  
    ```  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** SOS_Stacktrace.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von globalen statischen Funktionen](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
