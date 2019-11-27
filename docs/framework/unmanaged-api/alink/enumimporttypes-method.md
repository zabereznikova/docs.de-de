---
title: EnumImportTypes-Methode
ms.date: 03/30/2017
api_name:
- EnumImportTypes
- IALink.EnumImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumImportTypes
helpviewer_keywords:
- EnumImportTypes method
ms.assetid: 83a0e4e7-ec06-40cb-9b63-700b9695bb04
topic_type:
- apiref
ms.openlocfilehash: ca7c7570aff63aa328dddc0626648fa74397addc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448734"
---
# <a name="enumimporttypes-method"></a><span data-ttu-id="2c689-102">EnumImportTypes-Methode</span><span class="sxs-lookup"><span data-stu-id="2c689-102">EnumImportTypes Method</span></span>

<span data-ttu-id="2c689-103">Listet jeden Typ in jedem Bereich auf.</span><span class="sxs-lookup"><span data-stu-id="2c689-103">Enumerates each type in each scope.</span></span>

## <a name="syntax"></a><span data-ttu-id="2c689-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2c689-104">Syntax</span></span>

```cpp
HRESULT EnumImportTypes(
    HALINKENUM   hEnum,
    DWORD        dwMax,
    mdTypeDef    aTypeDefs[],
    DWORD*       pdwCount
) PURE;
```

## <a name="parameters"></a><span data-ttu-id="2c689-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2c689-105">Parameters</span></span>

`hEnum`\
<span data-ttu-id="2c689-106">Handle für Enumerator.</span><span class="sxs-lookup"><span data-stu-id="2c689-106">Handle for enumerator.</span></span>

`dwMax`\
<span data-ttu-id="2c689-107">Maximale Anzahl der abzurufenden Typen.</span><span class="sxs-lookup"><span data-stu-id="2c689-107">Maximum number of types to retrieve.</span></span>

`aTypeDefs`\
<span data-ttu-id="2c689-108">Empfängt Typtoken, ohne dass die `dwMax`überschritten wird.</span><span class="sxs-lookup"><span data-stu-id="2c689-108">Receives type tokens, not to exceed `dwMax`.</span></span>

`pdwCount`\
<span data-ttu-id="2c689-109">Empfängt die tatsächliche Anzahl von Typen in `aTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="2c689-109">Receives actual number of type in `aTypeDefs`.</span></span>

## <a name="return-value"></a><span data-ttu-id="2c689-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2c689-110">Return Value</span></span>

<span data-ttu-id="2c689-111">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="2c689-111">Returns S_OK if the method succeeds.</span></span>

## <a name="requirements"></a><span data-ttu-id="2c689-112">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="2c689-112">Requirements</span></span>

<span data-ttu-id="2c689-113">Erfordert "Alink. h"</span><span class="sxs-lookup"><span data-stu-id="2c689-113">Requires alink.h</span></span>

## <a name="see-also"></a><span data-ttu-id="2c689-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2c689-114">See also</span></span>

- [<span data-ttu-id="2c689-115">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2c689-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="2c689-116">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2c689-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="2c689-117">Alink-API</span><span class="sxs-lookup"><span data-stu-id="2c689-117">ALink API</span></span>](index.md)
