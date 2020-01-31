---
title: ICorDebugSymbolProvider2::GetGenericDictionaryInfo-Methode
ms.date: 03/30/2017
ms.assetid: ba28fe4e-5491-4670-bff7-7fde572d7593
ms.openlocfilehash: 02ecaf56e845680472f42c04f3978e54e7a69272
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791510"
---
# <a name="icordebugsymbolprovider2getgenericdictionaryinfo-method"></a><span data-ttu-id="330d6-102">ICorDebugSymbolProvider2::GetGenericDictionaryInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="330d6-102">ICorDebugSymbolProvider2::GetGenericDictionaryInfo Method</span></span>

<span data-ttu-id="330d6-103">Ruft eine generische Wörterbuchzuordnung ab.</span><span class="sxs-lookup"><span data-stu-id="330d6-103">Retrieves a generic dictionary map.</span></span>

## <a name="syntax"></a><span data-ttu-id="330d6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="330d6-104">Syntax</span></span>

```cpp
HRESULT GetGenericDictionaryInfo(
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer
);
```

## <a name="parameters"></a><span data-ttu-id="330d6-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="330d6-105">Parameters</span></span>

`ppMemoryBuffer`\
<span data-ttu-id="330d6-106">vorgenommen Ein Zeiger auf die Adresse eines [icorentbugmemorybuffer](icordebugmemorybuffer-interface.md) -Objekts, das die generische Wörterbuch Zuordnung enthält.</span><span class="sxs-lookup"><span data-stu-id="330d6-106">[out] A pointer to the address of an [ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) object containing the generic dictionary map.</span></span> <span data-ttu-id="330d6-107">Weitere Informationen finden Sie im Abschnitt Hinweise.</span><span class="sxs-lookup"><span data-stu-id="330d6-107">See the Remarks section for more information.</span></span>

## <a name="remarks"></a><span data-ttu-id="330d6-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="330d6-108">Remarks</span></span>

> [!NOTE]
> <span data-ttu-id="330d6-109">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="330d6-109">This method is available with .NET Native only.</span></span>

<span data-ttu-id="330d6-110">Die Zuordnung besteht aus zwei Abschnitten auf oberster Ebene:</span><span class="sxs-lookup"><span data-stu-id="330d6-110">The map consists of two top-level sections:</span></span>

- <span data-ttu-id="330d6-111">Ein [Verzeichnis](#Directory) mit den relativen virtuellen Adressen (RVA) aller Wörterbücher, die in dieser Zuordnung enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="330d6-111">A [directory](#Directory) containing the relative virtual addresses (RVA) of all dictionaries included in this map.</span></span>

- <span data-ttu-id="330d6-112">Ein Byte-ausgerichteter [Heap](#Heap) , der objektinstanziationsinformationen enthält.</span><span class="sxs-lookup"><span data-stu-id="330d6-112">A byte-aligned [heap](#Heap) that contains object instantiation information.</span></span> <span data-ttu-id="330d6-113">Er beginnt unmittelbar nach dem letzten Verzeichniseintrag.</span><span class="sxs-lookup"><span data-stu-id="330d6-113">It starts immediately after the last directory entry.</span></span>

<a name="Directory"></a>

## <a name="the-directory"></a><span data-ttu-id="330d6-114">Das Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="330d6-114">The Directory</span></span>

<span data-ttu-id="330d6-115">Jeder Eintrag im Verzeichnis verweist auf einen Offset innerhalb des Heaps. Dieser Offset ist relativ zum Beginn des Heaps.</span><span class="sxs-lookup"><span data-stu-id="330d6-115">Each entry in the directory refers to an offset inside the heap; that is, it is an offset that is relative to the start of the heap.</span></span> <span data-ttu-id="330d6-116">Der Wert der einzelnen Einträge ist nicht notwendigerweise eindeutig. Es ist möglich, dass mehrere Verzeichniseinträge auf den gleichen Offset im Heap zeigen.</span><span class="sxs-lookup"><span data-stu-id="330d6-116">The value of individual entries is not necessarily unique; it is possible for multiple directory entries to point to the same offset in the heap.</span></span>

<span data-ttu-id="330d6-117">Der Verzeichnisteil der generischen Wörterbuchzuordnung weist die folgende Struktur auf:</span><span class="sxs-lookup"><span data-stu-id="330d6-117">The directory portion of the generic dictionary map has the following structure:</span></span>

- <span data-ttu-id="330d6-118">Die ersten 4 Bytes enthalten die Anzahl der Wörterbucheinträge (d. h. die Anzahl der relativen virtuellen Adressen im Wörterbuch).</span><span class="sxs-lookup"><span data-stu-id="330d6-118">The first 4 bytes contains the number of dictionary entries (that is, the number of relative virtual addresses in the dictionary).</span></span> <span data-ttu-id="330d6-119">Dieser Wert wird als *N*bezeichnet. Wenn das hohe Bit festgelegt ist, werden die Einträge anhand der relativen virtuellen Adresse in aufsteigender Reihenfolge sortiert.</span><span class="sxs-lookup"><span data-stu-id="330d6-119">We will refer to this value as *N*. If the high bit is set, the entries are sorted by relative virtual address in ascending order.</span></span>

- <span data-ttu-id="330d6-120">Die *N* -Verzeichniseinträge folgen.</span><span class="sxs-lookup"><span data-stu-id="330d6-120">The *N* directory entries follow.</span></span> <span data-ttu-id="330d6-121">Jeder Eintrag besteht aus 8 Bytes in zwei 4-Byte-Segmenten:</span><span class="sxs-lookup"><span data-stu-id="330d6-121">Each entry consists of 8 bytes, in two 4-byte segments:</span></span>

  - <span data-ttu-id="330d6-122">Bytes 0 - 3: RVA - die relative virtuelle Adresse des Wörterbuchs.</span><span class="sxs-lookup"><span data-stu-id="330d6-122">Bytes 0-3: RVA; the dictionary's relative virtual address.</span></span>

  - <span data-ttu-id="330d6-123">Bytes 4 - 7: Offset - ein Offset relativ zum Beginn des Heaps.</span><span class="sxs-lookup"><span data-stu-id="330d6-123">Bytes 4-7: Offset; an offset relative to the start of the heap.</span></span>

<a name="Heap"></a>

## <a name="the-heap"></a><span data-ttu-id="330d6-124">Der Heap</span><span class="sxs-lookup"><span data-stu-id="330d6-124">The Heap</span></span>

<span data-ttu-id="330d6-125">Die Größe des Heaps kann von einem StreamReader durch Subtrahieren der Länge des Datenstroms von der Verzeichnisgröße + 4 berechnet werden.</span><span class="sxs-lookup"><span data-stu-id="330d6-125">The heap’s size can be computed by a stream reader by subtracting the length of the stream from the directory size + 4.</span></span> <span data-ttu-id="330d6-126">Anders ausgedrückt:</span><span class="sxs-lookup"><span data-stu-id="330d6-126">In other words:</span></span>

```csharp
Heap Size = Stream.Length – (Directory Size + 4)
```

<span data-ttu-id="330d6-127">Dabei ist die Verzeichnisgröße `N * 8`.</span><span class="sxs-lookup"><span data-stu-id="330d6-127">where the directory size is `N * 8`.</span></span>

<span data-ttu-id="330d6-128">Das folgende Format wird für jedes Instanziierungsinformationselement auf dem Heap verwendet:</span><span class="sxs-lookup"><span data-stu-id="330d6-128">The format for each instantiation information item on the heap is:</span></span>

- <span data-ttu-id="330d6-129">Die Länge dieses Instanziierungsinformationselements in Bytes im komprimierten ECMA-Metadatenformat.</span><span class="sxs-lookup"><span data-stu-id="330d6-129">The length of this instantiation information item in bytes in compressed ECMA metadata format.</span></span> <span data-ttu-id="330d6-130">Der Wert schließt diese Längeninformationen aus.</span><span class="sxs-lookup"><span data-stu-id="330d6-130">The value excludes this length information.</span></span>

- <span data-ttu-id="330d6-131">Die Anzahl der generischen instanziationstypen oder *T*im komprimierten ECMA-Metadatenformat.</span><span class="sxs-lookup"><span data-stu-id="330d6-131">The number of generic instantiation types, or *T*, in compressed ECMA metadata format.</span></span>

- <span data-ttu-id="330d6-132">*T* -Typen, die jeweils im ECMA-Typsignatur Format dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="330d6-132">*T* types, each represented in ECMA type signature format.</span></span>

<span data-ttu-id="330d6-133">Die Berücksichtigung der Länge für jedes Heapelement ermöglicht eine einfache Sortierung des Verzeichnisabschnitts ohne Auswirkungen auf den Heap.</span><span class="sxs-lookup"><span data-stu-id="330d6-133">The inclusion of the length for each heap element enables simple sorting of the directory section without affecting the heap.</span></span>

## <a name="requirements"></a><span data-ttu-id="330d6-134">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="330d6-134">Requirements</span></span>

<span data-ttu-id="330d6-135">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="330d6-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="330d6-136">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="330d6-136">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="330d6-137">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="330d6-137">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="330d6-138">**.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="330d6-138">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="330d6-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="330d6-139">See also</span></span>

- [<span data-ttu-id="330d6-140">ICorDebugSymbolProvider2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="330d6-140">ICorDebugSymbolProvider2 Interface</span></span>](icordebugsymbolprovider2-interface.md)
- [<span data-ttu-id="330d6-141">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="330d6-141">Debugging Interfaces</span></span>](debugging-interfaces.md)
