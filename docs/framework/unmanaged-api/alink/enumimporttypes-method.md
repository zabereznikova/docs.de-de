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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1d0aefea7345bc3bf37bdb8d13cb2cda19cfe527
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355739"
---
# <a name="enumimporttypes-method"></a><span data-ttu-id="453af-102">EnumImportTypes-Methode</span><span class="sxs-lookup"><span data-stu-id="453af-102">EnumImportTypes Method</span></span>

<span data-ttu-id="453af-103">Listet jeden Typ in jedem Bereich an.</span><span class="sxs-lookup"><span data-stu-id="453af-103">Enumerates each type in each scope.</span></span>

## <a name="syntax"></a><span data-ttu-id="453af-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="453af-104">Syntax</span></span>

```cpp
HRESULT EnumImportTypes(
    HALINKENUM   hEnum,
    DWORD        dwMax,
    mdTypeDef    aTypeDefs[],
    DWORD*       pdwCount
) PURE;
```

## <a name="parameters"></a><span data-ttu-id="453af-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="453af-105">Parameters</span></span>

`hEnum`\
<span data-ttu-id="453af-106">Handle für Enumerator.</span><span class="sxs-lookup"><span data-stu-id="453af-106">Handle for enumerator.</span></span>

`dwMax`\
<span data-ttu-id="453af-107">Maximale Anzahl von Typen, die abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="453af-107">Maximum number of types to retrieve.</span></span>

`aTypeDefs`\
<span data-ttu-id="453af-108">Typtoken, nicht zu überschreiten erhält `dwMax`.</span><span class="sxs-lookup"><span data-stu-id="453af-108">Receives type tokens, not to exceed `dwMax`.</span></span>

`pdwCount`\
<span data-ttu-id="453af-109">Empfängt die tatsächliche Anzahl der Typen in `aTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="453af-109">Receives actual number of type in `aTypeDefs`.</span></span>

## <a name="return-value"></a><span data-ttu-id="453af-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="453af-110">Return Value</span></span>

<span data-ttu-id="453af-111">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="453af-111">Returns S_OK if the method succeeds.</span></span>

## <a name="requirements"></a><span data-ttu-id="453af-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="453af-112">Requirements</span></span>

<span data-ttu-id="453af-113">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="453af-113">Requires alink.h</span></span>

## <a name="see-also"></a><span data-ttu-id="453af-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="453af-114">See also</span></span>

- [<span data-ttu-id="453af-115">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="453af-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="453af-116">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="453af-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="453af-117">Alink-API</span><span class="sxs-lookup"><span data-stu-id="453af-117">ALink API</span></span>](index.md)