---
title: MemoryStream. internalgetoriginandlength-Methode (System.IO)
author: mairaw
ms.author: mairaw
ms.date: 11/19/2019
topic_type:
- apiref
api_name:
- System.IO.MemoryStream.InternalGetOriginAndLength
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: d2bfa087fe2fb247f963cfa687c27056363d5696
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74284042"
---
# <a name="memorystreaminternalgetoriginandlength-method"></a><span data-ttu-id="137f3-102">MemoryStream. internalgetoriginandlength-Methode</span><span class="sxs-lookup"><span data-stu-id="137f3-102">MemoryStream.InternalGetOriginAndLength method</span></span>

<span data-ttu-id="137f3-103">Ruft die internen Werte des Ursprungs und der Länge des Arbeitsspeicherstreams ab.</span><span class="sxs-lookup"><span data-stu-id="137f3-103">Gets the internal values of origin and length of the memory stream.</span></span>

```csharp
internal void InternalGetOriginAndLength(out int origin, out int length)
```

## <a name="parameters"></a><span data-ttu-id="137f3-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="137f3-104">Parameters</span></span>

- <span data-ttu-id="137f3-105">`origin` <xref:System.Int32></span><span class="sxs-lookup"><span data-stu-id="137f3-105">`origin` <xref:System.Int32></span></span>\
  <span data-ttu-id="137f3-106">Wenn diese Methode zurückgegeben wird, der Offset des Bytearrays, das beim Erstellen eines neuen <xref:System.IO.MemoryStream>-Objekts angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="137f3-106">When this method returns, the offset of the byte array specified when creating a new <xref:System.IO.MemoryStream> object.</span></span> <span data-ttu-id="137f3-107">Enthält 0, wenn das Bytearray von <xref:System.IO.MemoryStream>erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="137f3-107">Contains 0 if the byte array was created by <xref:System.IO.MemoryStream>.</span></span>

- <span data-ttu-id="137f3-108">`length` <xref:System.Int32></span><span class="sxs-lookup"><span data-stu-id="137f3-108">`length` <xref:System.Int32></span></span>\
  <span data-ttu-id="137f3-109">Wenn diese Methode zurückgegeben wird, wird die Anzahl der Bytes im Arbeitsspeicherstream angezeigt.</span><span class="sxs-lookup"><span data-stu-id="137f3-109">When this method returns, the number of bytes within the memory stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="137f3-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="137f3-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="137f3-111">Die `MemoryStream.InternalGetOriginAndLength`-Methode ist intern und sollte nicht direkt im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="137f3-111">The `MemoryStream.InternalGetOriginAndLength` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="137f3-112">Microsoft unterstützt die Verwendung dieser Methode in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="137f3-112">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="137f3-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="137f3-113">Requirements</span></span>

<span data-ttu-id="137f3-114">**Namespace:** <xref:System.IO></span><span class="sxs-lookup"><span data-stu-id="137f3-114">**Namespace:** <xref:System.IO></span></span>

<span data-ttu-id="137f3-115">**Assembly:** mscorlib. dll (in "mscorlib. dll")</span><span class="sxs-lookup"><span data-stu-id="137f3-115">**Assembly:** mscorlib.dll (in mscorlib.dll)</span></span>

<span data-ttu-id="137f3-116">**.NET Framework Versionen:** Verfügbar seit 2,0.</span><span class="sxs-lookup"><span data-stu-id="137f3-116">**.NET Framework versions:** Available since 2.0.</span></span>
