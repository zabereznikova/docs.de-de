---
title: CorThreadSafetyOptions-Enumeration
ms.date: 03/30/2017
api_name:
- CorThreadSafetyOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorThreadSafetyOptions
helpviewer_keywords:
- CorThreadSafetyOptions enumeration [.NET Framework metadata]
ms.assetid: dae07d9b-df51-488c-b17e-52d6e48217bd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d71d2a5b3007d4e877900443af426a9643b29125
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045226"
---
# <a name="corthreadsafetyoptions-enumeration"></a>CorThreadSafetyOptions-Enumeration

Gibt Flags für die Auswahl von Optionen für die Threadsicherheit an.

## <a name="syntax"></a>Syntax

```cpp
typedef enum CorThreadSafetyOptions {
    MDThreadSafetyDefault       = 0x00000000,
    MDThreadSafetyOff           = 0x00000000,
    MDThreadSafetyOn            = 0x00000001,
} CorThreadSafetyOptions;
```

## <a name="members"></a>Member

|Member|Beschreibung|
|------------|-----------------|
|`MDThreadSafetyDefault`|Der Standardwert. Wie in `MDThreadSafetyOff`.|
|`MDThreadSafetyOff`|Gibt an, dass eine Reader-/Writer-Sperre kann nicht festgelegt werden.|
|`MDThreadSafetyOn`|Gibt an, dass eine Reader-/Writer-Sperre festgelegt werden kann.|

## <a name="requirements"></a>Anforderungen

**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).

**Header:** CorHdr.h

**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
