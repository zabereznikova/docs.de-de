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
ms.openlocfilehash: 8c0527a7bc3cde7344bf809dc8e6f5a3fac04852
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007506"
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
|`MDThreadSafetyDefault`|Standardwert. Wie in `MDThreadSafetyOff`.|
|`MDThreadSafetyOff`|Gibt an, dass keine Lese-/Schreibsperre festgelegt werden kann.|
|`MDThreadSafetyOn`|Gibt an, dass eine Lese-/Schreibsperre festgelegt werden kann.|

## <a name="requirements"></a>Requirements (Anforderungen)

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

**Header:** Corhdr. h

**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](metadata-enumerations.md)
