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
ms.openlocfilehash: 717d2104db8addf40e5187cee4cc8c46e5dc355e
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636743"
---
# <a name="strongnamekeydelete-function"></a>StrongNameKeyDelete-Funktion

Löscht den angegebenen Schlüsselcontainer.

Diese Funktion wurde als veraltet markiert. Verwenden der [ICLRStrongName:: StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) Methode stattdessen.

## <a name="syntax"></a>Syntax

```cpp
BOOLEAN StrongNameKeyDelete (
    [in]  LPCWSTR   wszKeyContainer
);
```

## <a name="parameters"></a>Parameter

`wszKeyContainer`\
[in] Der Name des Containers mit dem Schlüssel zu löschen.

## <a name="return-value"></a>Rückgabewert

`true` Bei erfolgreichem Abschluss; andernfalls `false`.

## <a name="remarks"></a>Hinweise

Verwenden der [StrongNameKeyInstall](strongnamekeyinstall-function.md) Funktion, um ein öffentliches/privates Schlüsselpaar in einem Container zu importieren.

Wenn die `StrongNameKeyDelete` Funktion nicht erfolgreich abgeschlossen wurde, rufen Sie die [StrongNameErrorInfo](strongnameerrorinfo-function.md) Funktion, um den letzten generierten Fehler abzurufen.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).

**Header:** StrongName.h

**Bibliothek:** Als Ressource in MsCorEE.dll enthalten

**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>Siehe auch

- [StrongNameKeyDelete-Methode](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [StrongNameKeyInstall-Methode](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [ICLRStrongName-Schnittstelle](../hosting/iclrstrongname-interface.md)
