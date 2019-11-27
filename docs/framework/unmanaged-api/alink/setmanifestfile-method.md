---
title: SetManifestFile-Methode
ms.date: 03/30/2017
api_name:
- IALink3.SetManifestFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetManifestFile
helpviewer_keywords:
- SetManifestFile method
ms.assetid: 1b33de4c-19cb-4a36-a93f-8675b2a36d58
topic_type:
- apiref
ms.openlocfilehash: df97f4c37d8f335ce183685debd7c0933be910ed
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445559"
---
# <a name="setmanifestfile-method"></a>SetManifestFile-Methode
Ermöglicht es Ihnen, die Manifest-Datei anzugeben oder zurückzusetzen, die der Linker beim Erstellen der Assembly verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
## <a name="parameters"></a>Parameter  
 `pszFile`  
  
 Der Name der Manifest-Datei, deren Inhalt in das Win32-Ressourcen-BLOB eingefügt wird.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="remarks"></a>Hinweise  
 Nennen Sie dies, bevor Sie die Win32ResBlob anfordern. Der Wert des `pszFile`-Parameters ist der Name der Manifest-Datei, deren Inhalt in den Win32-Ressourcen mit der ID RT_MANIFEST gelesen und abgelegt wird. Wenn Sie mit einem Parameter von NULL aufgerufen wird, werden alle zuvor gelesenen Manifeste gelöscht. Dadurch kann der Zustand des Linker auf den Zeitpunkt der Initialisierung zurückgesetzt werden.  
  
## <a name="requirements"></a>Voraussetzungen  
 Erfordert "Alink. h"  
  
## <a name="see-also"></a>Siehe auch

- [IALink3-Schnittstelle](ialink3-interface.md)
- [Alink-API](index.md)
- [IALink-Schnittstelle](ialink-interface.md)
- [Al.exe (Assembly Linker-Tool)](../../tools/al-exe-assembly-linker.md)
