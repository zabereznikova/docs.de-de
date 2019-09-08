---
title: StrongNameTokenFromAssembly-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromAssembly
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameTokenFromAssembly
helpviewer_keywords:
- StrongNameTokenFromAssembly function [.NET Framework strong naming]
ms.assetid: 0a4b47ee-02f6-4a98-864e-a6f11ca3f2d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 71058a1ff82335b2a341904805d06738e662c296
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798870"
---
# <a name="strongnametokenfromassembly-function"></a>StrongNameTokenFromAssembly-Funktion
Erstellt ein Token mit starkem Namen aus der angegebenen Assemblydatei.  
  
 Diese Funktion ist veraltet. Verwenden Sie stattdessen die [ICLRStrongName:: StrongNameTokenFromAssembly](../hosting/iclrstrongname-strongnametokenfromassembly-method.md) -Methode.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
BOOLEAN StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `wszFilePath`  
 in Der Pfad zur PE-Datei (portable ausführbare Datei) für die Assembly.  
  
 `ppbStrongNameToken`  
 vorgenommen Das zurückgegebene Token für den starken Namen.  
  
 `pcbStrongNameToken`  
 vorgenommen Die Größe (in Bytes) des Tokens für einen starken Namen.  
  
## <a name="return-value"></a>Rückgabewert  
 `true`nach erfolgreichem Abschluss: `false`andernfalls.  
  
## <a name="remarks"></a>Hinweise  
 Ein Token mit starkem Namen ist die verkürzte Form eines öffentlichen Schlüssels. Das Token ist ein 64-Bit-Hash, der aus dem öffentlichen Schlüssel, der zum Signieren der Assembly verwendet wird, erstellt wird. Das Token ist Teil des starken Namens für die Assembly und kann aus den Assemblymetadaten gelesen werden.  
  
 Nachdem das Token erstellt wurde, sollten Sie die [strongnamefrebuffer](strongnamefreebuffer-function.md) -Funktion zum Freigeben des zugewiesenen Speichers aufzurufen.  
  
 Wenn die `StrongNameTokenFromAssembly` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](strongnameerrorinfo-function.md) -Funktion auf, um den zuletzt generierten Fehler abzurufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** StrongName. h  
  
 **Fern** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [StrongNameTokenFromAssembly-Methode](../hosting/iclrstrongname-strongnametokenfromassembly-method.md)
- [StrongNameTokenFromAssemblyEx-Methode](../hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [ICLRStrongName-Schnittstelle](../hosting/iclrstrongname-interface.md)
