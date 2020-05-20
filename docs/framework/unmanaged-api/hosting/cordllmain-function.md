---
title: _CorDllMain-Funktion
ms.date: 03/30/2017
api_name:
- _CorDllMain
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorDllMain
helpviewer_keywords:
- _CorDllMain function [.NET Framework hosting]
ms.assetid: bc7b51cf-39d3-48ec-a5cb-2f179fbefff8
topic_type:
- apiref
ms.openlocfilehash: 3b2322f708afed08172f87e843c225aa9c60d9d3
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616605"
---
# <a name="_cordllmain-function"></a>\_Cordllmain-Funktion

Initialisiert die Common Language Runtime (CLR), gibt den verwalteten Einstiegspunkt im CLR-Header der dll-Assembly an und beginnt die Ausführung.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `hInst`  
 in Der Instanzhandle des geladenen Moduls.  
  
 `dwReason`  
 in Gibt an, warum die DLL-Einstiegspunkt Funktion aufgerufen wird. Dieser Parameter kann einen der folgenden Werte aufweisen: DLL- \_ PROCESS_ATTACH, DLL- \_ Thread \_ Anfügen, Anfügen von DLL- \_ Threads \_ oder Trennen von DLL- \_ Prozessen \_ . Beschreibungen dieser Werte finden Sie `DllMain` in der Dokumentation im Platform SDK.  
  
 `lpReserved`  
 [in] Nicht verwendet.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt `true` für Erfolg und `false` bei Auftreten eines Fehlers zurück.  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion wird vom Betriebssystem-Lade Modul für dll-Assemblys aufgerufen. Bei ausführbaren Assemblys Ruft das Lade Programm stattdessen die [ \_ CORExeMain](corexemain-function.md) -Funktion auf.  
  
 Das Betriebssystem-Lade Modul ruft diese Methode unabhängig vom Einstiegspunkt auf, der in der DLL-Datei angegeben ist.  
  
Die- `_CorDllMain` Funktion wird direkt vom Betriebssystem-Lade Modul aufgerufen.
  
 Weitere Informationen finden Sie im Abschnitt "Hinweise" im Thema [ \_ CorValidateImage](corvalidateimage-function.md) .  
  
## <a name="requirements"></a>Anforderungen  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Globale statische Metadatenfunktionen](../metadata/metadata-global-static-functions.md)
