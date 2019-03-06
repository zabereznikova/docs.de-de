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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0fefbab6b2ea9fbbfd90e03c41578a924f99c7a0
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364163"
---
# <a name="imetadatatablesgetuserstring-method"></a><span data-ttu-id="0855a-102">IMetaDataTables::GetUserString-Methode</span><span class="sxs-lookup"><span data-stu-id="0855a-102">IMetaDataTables::GetUserString Method</span></span>

<span data-ttu-id="0855a-103">Ruft die hartcodierten Zeichenfolge am angegebenen Index in die Zeichenfolgenspalte im aktuellen Bereich ab.</span><span class="sxs-lookup"><span data-stu-id="0855a-103">Gets the hard-coded string at the specified index in the string column in the current scope.</span></span>

## <a name="syntax"></a><span data-ttu-id="0855a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0855a-104">Syntax</span></span>

```cpp
HRESULT GetUserString (
    [in]  ULONG       ixUserString,
    [out] ULONG       *pcbData,
    [out] const void  **ppData
);
```

## <a name="parameters"></a><span data-ttu-id="0855a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0855a-105">Parameters</span></span>

`ixUserString`\
<span data-ttu-id="0855a-106">[in] Der Indexwert aus dem die hartcodierten Zeichenfolge abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="0855a-106">[in] The index value from which the hard-coded string will be retrieved.</span></span>

`pcbData`\
<span data-ttu-id="0855a-107">[out] Ein Zeiger auf die Größe des `ppData`.</span><span class="sxs-lookup"><span data-stu-id="0855a-107">[out] A pointer to the size of `ppData`.</span></span>

`ppData`\
<span data-ttu-id="0855a-108">[out] Ein Zeiger auf einen Zeiger auf die zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="0855a-108">[out] A pointer to a pointer to the returned string.</span></span>

## <a name="requirements"></a><span data-ttu-id="0855a-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0855a-109">Requirements</span></span>

<span data-ttu-id="0855a-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0855a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="0855a-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0855a-111">**Header:** Cor.h</span></span>

<span data-ttu-id="0855a-112">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="0855a-112">**Library:** Used as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="0855a-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0855a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="0855a-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0855a-114">See also</span></span>

- [<span data-ttu-id="0855a-115">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0855a-115">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="0855a-116">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0855a-116">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)