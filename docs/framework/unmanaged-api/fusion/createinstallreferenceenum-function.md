---
title: CreateInstallReferenceEnum-Funktion
ms.date: 03/30/2017
api_name:
- CreateInstallReferenceEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateInstallReference
helpviewer_keywords:
- CreateInstallReference function [.NET Framework fusion]
ms.assetid: 80dbbbf8-54fc-4894-b74a-0179d3201083
topic_type:
- apiref
ms.openlocfilehash: 0f62b05ebbd8b27dba160c8281c1d40748c90fc9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688834"
---
# <a name="createinstallreferenceenum-function"></a>CreateInstallReferenceEnum-Funktion

Ruft einen Zeiger auf eine [IInstallReferenceEnum](iinstallreferenceenum-interface.md) -Instanz ab, die eine Liste der Verweise einer Anwendung auf die angegebene Assembly darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CreateInstallReferenceEnum (  
    [out] IInstallReferenceEnum **ppRefEnum,  
    [in]  IAssemblyName         *pName,  
    [in]  DWORD                 dwFlags,  
    [in]  LPVOID                pvReserved  
 );  
```  
  
## <a name="parameters"></a>Parameter  

 `ppRefEnum`  
 vorgenommen Der zurückgegebene `IInstallReferenceEnum` Zeiger.  
  
 `pName`  
 in Der [IAssemblyName](iassemblyname-interface.md) , der die Assembly identifiziert, für die Verweise aufgelistet werden sollen.  
  
 `dwFlags`  
 in Flags, die das Verhalten des Enumerators beeinflussen.  
  
 `pvReserved`  
 [in] Für zukünftige Erweiterungen reserviert. `pvReserved` muss ein NULL-Verweis sein.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Fusion. h  
  
 **Bibliothek:** Fusion.dll und Mscorwks.dll. Verwenden Sie Fusion.dll anstelle von Mscorwks.dll, um sicherzustellen, dass Sie die richtige Version der .NET Framework als Ziel verwenden.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IInstallReferenceEnum-Schnittstelle](iinstallreferenceenum-interface.md)
- [IAssemblyName-Schnittstelle](iassemblyname-interface.md)
- [Fusion – Globale statistische Funktionen](fusion-global-static-functions.md)
