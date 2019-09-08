---
title: StrongNameKeyDelete-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameKeyDelete
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyDelete
helpviewer_keywords:
- StrongNameKeyDelete function [.NET Framework strong naming]
ms.assetid: 313e71e4-1790-4d2f-b68b-5040ebd1c149
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 17d35193f69966e02ac5e483924fcb3ee2e06758
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799021"
---
# <a name="strongnamekeydelete-function"></a>StrongNameKeyDelete-Funktion

Löscht den angegebenen Schlüsselcontainer.

Diese Funktion ist veraltet. Verwenden Sie stattdessen die [ICLRStrongName:: StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) -Methode.

## <a name="syntax"></a>Syntax

```cpp
BOOLEAN StrongNameKeyDelete (
    [in]  LPCWSTR   wszKeyContainer
);
```

## <a name="parameters"></a>Parameter

`wszKeyContainer`\
in Der Name des zu löschenden Schlüssel Containers.

## <a name="return-value"></a>Rückgabewert

`true`nach erfolgreichem Abschluss: `false`andernfalls.

## <a name="remarks"></a>Hinweise

Verwenden Sie die [StrongNameKeyInstall](strongnamekeyinstall-function.md) -Funktion, um ein öffentliches/privates Schlüsselpaar in einen Container zu importieren.

Wenn die `StrongNameKeyDelete` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](strongnameerrorinfo-function.md) -Funktion auf, um den zuletzt generierten Fehler abzurufen.

## <a name="requirements"></a>Anforderungen

**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

**Header:** StrongName. h

**Fern** Als Ressource in Mscoree. dll enthalten

**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>Siehe auch

- [StrongNameKeyDelete-Methode](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [StrongNameKeyInstall-Methode](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [ICLRStrongName-Schnittstelle](../hosting/iclrstrongname-interface.md)
