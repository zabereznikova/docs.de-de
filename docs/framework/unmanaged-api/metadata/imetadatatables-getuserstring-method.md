---
title: IMetaDataTables::GetUserString-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetUserString
helpviewer_keywords:
- IMetaDataTables::GetUserString method [.NET Framework metadata]
- GetUserString method, IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 35b8f0d6-9aba-4714-adb2-62020a38fb7e
topic_type:
- apiref
ms.openlocfilehash: 21ce66722e069573b651ada950b64ef6d97220fb
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501143"
---
# <a name="imetadatatablesgetuserstring-method"></a><span data-ttu-id="7b134-102">IMetaDataTables::GetUserString-Methode</span><span class="sxs-lookup"><span data-stu-id="7b134-102">IMetaDataTables::GetUserString Method</span></span>

<span data-ttu-id="7b134-103">Ruft die hart codierte Zeichenfolge am angegebenen Index in der Zeichen folgen Spalte im aktuellen Bereich ab.</span><span class="sxs-lookup"><span data-stu-id="7b134-103">Gets the hard-coded string at the specified index in the string column in the current scope.</span></span>

## <a name="syntax"></a><span data-ttu-id="7b134-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7b134-104">Syntax</span></span>

```cpp
HRESULT GetUserString (
    [in]  ULONG       ixUserString,
    [out] ULONG       *pcbData,
    [out] const void  **ppData
);
```

## <a name="parameters"></a><span data-ttu-id="7b134-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7b134-105">Parameters</span></span>

`ixUserString`\
<span data-ttu-id="7b134-106">in Der Indexwert, aus dem die hart codierte Zeichenfolge abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="7b134-106">[in] The index value from which the hard-coded string will be retrieved.</span></span>

`pcbData`\
<span data-ttu-id="7b134-107">vorgenommen Ein Zeiger auf die Größe von `ppData` .</span><span class="sxs-lookup"><span data-stu-id="7b134-107">[out] A pointer to the size of `ppData`.</span></span>

`ppData`\
<span data-ttu-id="7b134-108">vorgenommen Ein Zeiger auf einen Zeiger auf die zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="7b134-108">[out] A pointer to a pointer to the returned string.</span></span>

## <a name="requirements"></a><span data-ttu-id="7b134-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7b134-109">Requirements</span></span>

<span data-ttu-id="7b134-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b134-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="7b134-111">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7b134-111">**Header:** Cor.h</span></span>

<span data-ttu-id="7b134-112">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="7b134-112">**Library:** Used as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="7b134-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b134-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="7b134-114">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="7b134-114">See also</span></span>

- [<span data-ttu-id="7b134-115">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7b134-115">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="7b134-116">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7b134-116">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
