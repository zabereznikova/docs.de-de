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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d696326ff8861ed8496474f76e9eaf89b4ead3e8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795394"
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
 vorgenommen Der zurück `IInstallReferenceEnum` gegebene Zeiger.  
  
 `pName`  
 in Der [IAssemblyName](iassemblyname-interface.md) , der die Assembly identifiziert, für die Verweise aufgelistet werden sollen.  
  
 `dwFlags`  
 in Flags, die das Verhalten des Enumerators beeinflussen.  
  
 `pvReserved`  
 [in] Für zukünftige Erweiterungen reserviert. `pvReserved`muss ein NULL-Verweis sein.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Fusion. h  
  
 **Fern** "Fusion. dll" und "mscorwert. dll". Verwenden Sie "Fusion. dll" anstelle von "mscorwert. dll", um sicherzustellen, dass Sie die richtige Version des .NET Framework als Ziel verwenden.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IInstallReferenceEnum-Schnittstelle](iinstallreferenceenum-interface.md)
- [IAssemblyName-Schnittstelle](iassemblyname-interface.md)
- [Fusion: Globale statistische Funktionen](fusion-global-static-functions.md)
