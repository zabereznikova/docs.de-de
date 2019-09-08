---
title: StrongNameKeyInstall-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameKeyInstall
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyInstall
helpviewer_keywords:
- StrongNameKeyInstall function [.NET Framework strong naming]
ms.assetid: e32fd546-7757-4681-be3d-658e93281e50
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 353898b72f41acd0c49a43ff05e54f61b99444c4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798996"
---
# <a name="strongnamekeyinstall-function"></a>StrongNameKeyInstall-Funktion

Importiert ein öffentliches/privates Schlüsselpaar in einen Container.

Diese Funktion ist veraltet. Verwenden Sie stattdessen die [ICLRStrongName:: StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md) -Methode.

## <a name="syntax"></a>Syntax

```cpp
BOOLEAN StrongNameKeyInstall (
    [in]  LPCWSTR   wszKeyContainer,
    [in]  BYTE      *pbKeyBlob,
    [in]  ULONG     cbKeyBlob
);
```

## <a name="parameters"></a>Parameter

`wszKeyContainer`\
in Der Name des Schlüssel Containers. `wszKeyContainer`muss eine nicht leere Zeichenfolge sein.

`pbKeyBlob`\
in Das binäre Schlüsselpaar.

`cbKeyBlob`\
in Die Größe von `pbKeyBlob`in Bytes.

## <a name="return-value"></a>Rückgabewert

`true`nach erfolgreichem Abschluss: `false`andernfalls.

## <a name="remarks"></a>Hinweise

Verwenden Sie die [StrongNameKeyDelete](strongnamekeydelete-function.md) -Funktion, um den Schlüssel Container zu löschen.

Wenn die `StrongNameKeyInstall` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](strongnameerrorinfo-function.md) -Funktion auf, um den zuletzt generierten Fehler abzurufen.

## <a name="requirements"></a>Anforderungen

**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

**Header:** StrongName. h

**Fern** Als Ressource in Mscoree. dll enthalten

**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>Siehe auch

- [StrongNameKeyInstall-Methode](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [StrongNameKeyDelete-Methode](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [ICLRStrongName-Schnittstelle](../hosting/iclrstrongname-interface.md)
