---
title: StrongNameTokenFromAssemblyEx-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromAssemblyEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameTokenFromAssemblyEx
helpviewer_keywords:
- StrongNameTokenFromAssemblyEx function [.NET Framework strong naming]
ms.assetid: 67a8a9f2-dee3-44b2-a1c0-f307a3bdf90f
topic_type:
- apiref
ms.openlocfilehash: 8b7866b92be3195b0a767a823a0d7fb1c0aa4918
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73104244"
---
# <a name="strongnametokenfromassemblyex-function"></a>StrongNameTokenFromAssemblyEx-Funktion
Erstellt ein Token für einen starken Namen aus der angegebenen Assemblydatei und gibt den öffentlichen Schlüssel zurück, den das Token darstellt.  
  
 Diese Funktion ist veraltet. Verwenden Sie stattdessen die [ICLRStrongName:: StrongNameTokenFromAssemblyEx](../hosting/iclrstrongname-strongnametokenfromassemblyex-method.md) -Methode.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
BOOLEAN StrongNameTokenFromAssemblyEx (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `wszFilePath`  
 in Der Pfad zur PE-Datei (portable ausführbare Datei) für die Assembly.  
  
 `ppbStrongNameToken`  
 vorgenommen Das zurückgegebene Token für den starken Namen.  
  
 `pcbStrongNameToken`  
 vorgenommen Die Größe (in Bytes) des Tokens für einen starken Namen.  
  
 `ppbPublicKeyBlob`  
 vorgenommen Der zurückgegebene öffentliche Schlüssel.  
  
 `pcbPublicKeyBlob`  
 vorgenommen Die Größe des öffentlichen Schlüssels in Bytes.  
  
## <a name="return-value"></a>Rückgabewert  
 `true` nach erfolgreichem Abschluss. Andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 Ein Token mit starkem Namen ist die verkürzte Form eines öffentlichen Schlüssels. Das Token ist ein 64-Bit-Hash, der aus dem öffentlichen Schlüssel, der zum Signieren der Assembly verwendet wird, erstellt wird. Das Token ist Teil des starken Namens für die Assembly und kann aus den Assemblymetadaten gelesen werden.  
  
 Nachdem der Schlüssel abgerufen und das Token erstellt wurde, sollten Sie die [strongnamefrebuffer](strongnamefreebuffer-function.md) -Funktion zum Freigeben des zugewiesenen Speichers aufzurufen.  
  
 Wenn die `StrongNameTokenFromAssemblyEx`-Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](strongnameerrorinfo-function.md) -Funktion auf, um den zuletzt generierten Fehler abzurufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** StrongName. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [StrongNameTokenFromAssemblyEx-Methode](../hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [StrongNameTokenFromAssembly-Methode](../hosting/iclrstrongname-strongnametokenfromassembly-method.md)
- [ICLRStrongName-Schnittstelle](../hosting/iclrstrongname-interface.md)
