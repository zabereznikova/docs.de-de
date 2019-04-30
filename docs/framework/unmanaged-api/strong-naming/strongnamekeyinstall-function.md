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
ms.openlocfilehash: 6b3fc69b2edf611383402b13555cf33be10dbad3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000388"
---
# <a name="strongnamekeyinstall-function"></a>StrongNameKeyInstall-Funktion

Importiert ein öffentliches/privates Schlüsselpaar in einen Container.

Diese Funktion wurde als veraltet markiert. Verwenden der [ICLRStrongName:: StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md) Methode stattdessen.

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
[in] Der Name des Containers mit dem Schlüssel. `wszKeyContainer` eine nicht leere Zeichenfolge muss sein.

`pbKeyBlob`\
[in] Das binäre Schlüsselpaar.

`cbKeyBlob`\
[in] Die Größe in Bytes, des `pbKeyBlob`.

## <a name="return-value"></a>Rückgabewert

`true` Bei erfolgreichem Abschluss; andernfalls `false`.

## <a name="remarks"></a>Hinweise

Verwenden der [StrongNameKeyDelete](strongnamekeydelete-function.md) Funktion, um den Schlüsselcontainer zu löschen.

Wenn die `StrongNameKeyInstall` Funktion nicht erfolgreich abgeschlossen wurde, rufen Sie die [StrongNameErrorInfo](strongnameerrorinfo-function.md) Funktion, um den letzten generierten Fehler abzurufen.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).

**Header:** StrongName.h

**Bibliothek:** Als Ressource in MsCorEE.dll enthalten

**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>Siehe auch

- [StrongNameKeyInstall-Methode](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [StrongNameKeyDelete-Methode](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [ICLRStrongName-Schnittstelle](../hosting/iclrstrongname-interface.md)