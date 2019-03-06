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
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57360435"
---
# <a name="corthreadsafetyoptions-enumeration"></a><span data-ttu-id="9df80-102">CorThreadSafetyOptions-Enumeration</span><span class="sxs-lookup"><span data-stu-id="9df80-102">CorThreadSafetyOptions Enumeration</span></span>

<span data-ttu-id="9df80-103">Gibt Flags für die Auswahl von Optionen für die Threadsicherheit an.</span><span class="sxs-lookup"><span data-stu-id="9df80-103">Specifies flags to select options for thread safety.</span></span>

## <a name="syntax"></a><span data-ttu-id="9df80-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9df80-104">Syntax</span></span>

```cpp
typedef enum CorThreadSafetyOptions {
    MDThreadSafetyDefault       = 0x00000000,
    MDThreadSafetyOff           = 0x00000000,
    MDThreadSafetyOn            = 0x00000001,
} CorThreadSafetyOptions;
```

## <a name="members"></a><span data-ttu-id="9df80-105">Member</span><span class="sxs-lookup"><span data-stu-id="9df80-105">Members</span></span>

|<span data-ttu-id="9df80-106">Member</span><span class="sxs-lookup"><span data-stu-id="9df80-106">Member</span></span>|<span data-ttu-id="9df80-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9df80-107">Description</span></span>|
|------------|-----------------|
|`MDThreadSafetyDefault`|<span data-ttu-id="9df80-108">Der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="9df80-108">Default value.</span></span> <span data-ttu-id="9df80-109">Wie in `MDThreadSafetyOff`.</span><span class="sxs-lookup"><span data-stu-id="9df80-109">Same as `MDThreadSafetyOff`.</span></span>|
|`MDThreadSafetyOff`|<span data-ttu-id="9df80-110">Gibt an, dass eine Reader-/Writer-Sperre kann nicht festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="9df80-110">Indicates that a reader/writer lock cannot be set.</span></span>|
|`MDThreadSafetyOn`|<span data-ttu-id="9df80-111">Gibt an, dass eine Reader-/Writer-Sperre festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="9df80-111">Indicates that a reader/writer lock can be set.</span></span>|

## <a name="requirements"></a><span data-ttu-id="9df80-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9df80-112">Requirements</span></span>

<span data-ttu-id="9df80-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9df80-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="9df80-114">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="9df80-114">**Header:** CorHdr.h</span></span>

<span data-ttu-id="9df80-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9df80-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="9df80-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9df80-116">See also</span></span>

- [<span data-ttu-id="9df80-117">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="9df80-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
