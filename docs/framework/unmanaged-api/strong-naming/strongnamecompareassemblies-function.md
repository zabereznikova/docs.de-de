---
title: StrongNameCompareAssemblies-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameCompareAssemblies
helpviewer_keywords:
- StrongNameCompareAssemblies function [.NET Framework strong naming]
ms.assetid: 763f2375-efc6-4219-8806-a3b0567ef72b
topic_type:
- apiref
ms.openlocfilehash: e7292635ea0344f1c77c8d44908a9a811e464ff9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732306"
---
# <a name="strongnamecompareassemblies-function"></a>StrongNameCompareAssemblies-Funktion

Bestimmt, ob sich zwei Assemblys nur durch die Signaturen ihrer starken Namen unterscheiden.  
  
 Diese Funktion ist veraltet. Verwenden Sie stattdessen die [ICLRStrongName:: strongnamecompareassemblymethode](../hosting/iclrstrongname-strongnamecompareassemblies-method.md) .  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
BOOLEAN StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `wszAssembly1`  
 in Der Pfad zur ersten Assembly.  
  
 `wszAssembly2`  
 in Der Pfad zur zweiten Assembly.  
  
 `pdwResult`  
 vorgenommen Einer der folgenden Werte:  
  
- `SN_CMP_DIFFERENT` (0): gibt an, dass die Assemblys unterschiedliche Daten enthalten.  
  
- `SN_CMP_IDENTICAL` (1): gibt an, dass die Assemblys exakt identisch sind, einschließlich ihrer Signaturen und Prüfsumme.  
  
- `SN_CMP_SIGONLY` (2): gibt an, dass sich die Assemblys nur durch Signatur und Prüfsumme unterscheiden.  
  
## <a name="return-value"></a>Rückgabewert  

 `true` nach erfolgreichem Abschluss: andernfalls `false` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** StrongName. h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="remarks"></a>Hinweise  

 Die starke namens Signatur einer Assembly besteht aus dem Textnamen, der Version, der Kultur und dem öffentlichen Schlüssel Token der Assembly.  
  
 Wenn die `StrongNameCompareAssemblies` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](strongnameerrorinfo-function.md) -Funktion auf, um den zuletzt generierten Fehler abzurufen.  
  
## <a name="see-also"></a>Weitere Informationen

- [StrongNameCompareAssemblies-Methode](../hosting/iclrstrongname-strongnamecompareassemblies-method.md)
- [ICLRStrongName-Schnittstelle](../hosting/iclrstrongname-interface.md)
