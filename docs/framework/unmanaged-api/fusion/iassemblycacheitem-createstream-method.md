---
title: IAssemblyCacheItem::CreateStream-Methode
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem.CreateStream
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem::CreateStream
helpviewer_keywords:
- CreateStream method [.NET Framework fusion]
- IAssemblyCacheItem::CreateStream method [.NET Framework fusion]
ms.assetid: 697ab0f4-470c-4baa-a415-4a975c42d0d5
topic_type:
- apiref
ms.openlocfilehash: 0660621f465f2ba3610e06bd1df38baa1bc5c907
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134471"
---
# <a name="iassemblycacheitemcreatestream-method"></a><span data-ttu-id="91d61-102">IAssemblyCacheItem::CreateStream-Methode</span><span class="sxs-lookup"><span data-stu-id="91d61-102">IAssemblyCacheItem::CreateStream Method</span></span>

<span data-ttu-id="91d61-103">Erstellt einen Stream mit dem angegebenen Namen und Format.</span><span class="sxs-lookup"><span data-stu-id="91d61-103">Creates a stream with the specified name and format.</span></span>

## <a name="syntax"></a><span data-ttu-id="91d61-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="91d61-104">Syntax</span></span>

```cpp
HRESULT CreateStream (
    [in]  DWORD dwFlags,
    [in]  LPCWSTR pszStreamName,
    [in]  DWORD dwFormat,
    [in]  DWORD dwFormatFlags,
    [out] IStream **ppIStream,
    [in, optional] ULARGE_INTEGER *puliMaxSize
);
```

## <a name="parameters"></a><span data-ttu-id="91d61-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="91d61-105">Parameters</span></span>

`dwFlags`\
<span data-ttu-id="91d61-106">in In Fusion. idl definierte Flags.</span><span class="sxs-lookup"><span data-stu-id="91d61-106">[in] Flags defined in Fusion.idl.</span></span>

`pszStreamName`\
<span data-ttu-id="91d61-107">in Der Name des Streams, der erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="91d61-107">[in] The name of the stream to be created.</span></span>

`dwFormat`\
<span data-ttu-id="91d61-108">in Das Format der Datei, die gestreamt werden soll.</span><span class="sxs-lookup"><span data-stu-id="91d61-108">[in] The format of the file to be streamed.</span></span>

`dwFormatFlags`\
<span data-ttu-id="91d61-109">in Format spezifische Flags, die in Fusion. idl definiert sind.</span><span class="sxs-lookup"><span data-stu-id="91d61-109">[in] Format-specific flags defined in Fusion.idl.</span></span>

`ppIStream`\
<span data-ttu-id="91d61-110">vorgenommen Ein Zeiger auf die Adresse der zurückgegebenen [IStream](/windows/desktop/api/objidl/nn-objidl-istream) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="91d61-110">[out] A pointer to the address of the returned [IStream](/windows/desktop/api/objidl/nn-objidl-istream) instance.</span></span>

`puliMaxSize`\
<span data-ttu-id="91d61-111">[in, optional] Die maximale Größe des Streams, auf den von `ppIStream`verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="91d61-111">[in, optional] The maximum size of the stream referenced by `ppIStream`.</span></span>

## <a name="requirements"></a><span data-ttu-id="91d61-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="91d61-112">Requirements</span></span>

<span data-ttu-id="91d61-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91d61-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="91d61-114">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="91d61-114">**Header:** Fusion.h</span></span>

<span data-ttu-id="91d61-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91d61-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="91d61-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91d61-116">See also</span></span>

- [<span data-ttu-id="91d61-117">IAssemblyCacheItem-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="91d61-117">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)
