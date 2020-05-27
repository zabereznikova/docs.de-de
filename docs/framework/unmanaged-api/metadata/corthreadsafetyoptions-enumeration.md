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
# <a name="corthreadsafetyoptions-enumeration"></a><span data-ttu-id="5d4f1-102">CorThreadSafetyOptions-Enumeration</span><span class="sxs-lookup"><span data-stu-id="5d4f1-102">CorThreadSafetyOptions Enumeration</span></span>

<span data-ttu-id="5d4f1-103">Gibt Flags für die Auswahl von Optionen für die Threadsicherheit an.</span><span class="sxs-lookup"><span data-stu-id="5d4f1-103">Specifies flags to select options for thread safety.</span></span>

## <a name="syntax"></a><span data-ttu-id="5d4f1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5d4f1-104">Syntax</span></span>

```cpp
typedef enum CorThreadSafetyOptions {
    MDThreadSafetyDefault       = 0x00000000,
    MDThreadSafetyOff           = 0x00000000,
    MDThreadSafetyOn            = 0x00000001,
} CorThreadSafetyOptions;
```

## <a name="members"></a><span data-ttu-id="5d4f1-105">Member</span><span class="sxs-lookup"><span data-stu-id="5d4f1-105">Members</span></span>

|<span data-ttu-id="5d4f1-106">Member</span><span class="sxs-lookup"><span data-stu-id="5d4f1-106">Member</span></span>|<span data-ttu-id="5d4f1-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5d4f1-107">Description</span></span>|
|------------|-----------------|
|`MDThreadSafetyDefault`|<span data-ttu-id="5d4f1-108">Standardwert.</span><span class="sxs-lookup"><span data-stu-id="5d4f1-108">Default value.</span></span> <span data-ttu-id="5d4f1-109">Wie in `MDThreadSafetyOff`.</span><span class="sxs-lookup"><span data-stu-id="5d4f1-109">Same as `MDThreadSafetyOff`.</span></span>|
|`MDThreadSafetyOff`|<span data-ttu-id="5d4f1-110">Gibt an, dass keine Lese-/Schreibsperre festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="5d4f1-110">Indicates that a reader/writer lock cannot be set.</span></span>|
|`MDThreadSafetyOn`|<span data-ttu-id="5d4f1-111">Gibt an, dass eine Lese-/Schreibsperre festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="5d4f1-111">Indicates that a reader/writer lock can be set.</span></span>|

## <a name="requirements"></a><span data-ttu-id="5d4f1-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5d4f1-112">Requirements</span></span>

<span data-ttu-id="5d4f1-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d4f1-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="5d4f1-114">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="5d4f1-114">**Header:** CorHdr.h</span></span>

<span data-ttu-id="5d4f1-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d4f1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="5d4f1-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d4f1-116">See also</span></span>

- [<span data-ttu-id="5d4f1-117">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="5d4f1-117">Metadata Enumerations</span></span>](metadata-enumerations.md)
