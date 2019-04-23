---
title: ICorDebugSymbolProvider2::GetGenericDictionaryInfo-Methode
ms.date: 03/30/2017
ms.assetid: ba28fe4e-5491-4670-bff7-7fde572d7593
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f171af8dbfa4e812711e95e5587b314753cd9350
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59216820"
---
# <a name="icordebugsymbolprovider2getgenericdictionaryinfo-method"></a><span data-ttu-id="99865-102">ICorDebugSymbolProvider2::GetGenericDictionaryInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="99865-102">ICorDebugSymbolProvider2::GetGenericDictionaryInfo Method</span></span>
<span data-ttu-id="99865-103">Ruft eine generische Wörterbuchzuordnung ab.</span><span class="sxs-lookup"><span data-stu-id="99865-103">Retrieves a generic dictionary map.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99865-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="99865-104">Syntax</span></span>  
  
```  
HRESULT GetGenericDictionaryInfo(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99865-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="99865-105">Parameters</span></span>  
 `ppMemoryBuffer`  
 <span data-ttu-id="99865-106">[out] Ein Zeiger auf die Adresse einer [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) -Objekt, das die generische wörterbuchzuordnung enthält.</span><span class="sxs-lookup"><span data-stu-id="99865-106">[out] A pointer to the address of an [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) object containing the generic dictionary map.</span></span> <span data-ttu-id="99865-107">Weitere Informationen finden Sie im Abschnitt Hinweise.</span><span class="sxs-lookup"><span data-stu-id="99865-107">See the Remarks section for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99865-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="99865-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="99865-109">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="99865-109">This method is available with .NET Native only.</span></span>  
  
 <span data-ttu-id="99865-110">Die Zuordnung besteht aus zwei Abschnitten auf oberster Ebene:</span><span class="sxs-lookup"><span data-stu-id="99865-110">The map consists of two top-level sections:</span></span>  
  
-   <span data-ttu-id="99865-111">Ein [Directory](#Directory) mit den relativen virtuellen Adressen (RVA) aller Wörterbücher, die in dieser Zuordnung enthalten.</span><span class="sxs-lookup"><span data-stu-id="99865-111">A [directory](#Directory) containing the relative virtual addresses (RVA) of all dictionaries included in this map.</span></span>  
  
-   <span data-ttu-id="99865-112">Einem byteausgerichteten [Heap](#Heap) , die Informationen zur Objektinstanziierung enthält.</span><span class="sxs-lookup"><span data-stu-id="99865-112">A byte-aligned [heap](#Heap) that contains object instantiation information.</span></span> <span data-ttu-id="99865-113">Er beginnt unmittelbar nach dem letzten Verzeichniseintrag.</span><span class="sxs-lookup"><span data-stu-id="99865-113">It starts immediately after the last directory entry.</span></span>  
  
<a name="Directory"></a>   
## <a name="the-directory"></a><span data-ttu-id="99865-114">Das Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="99865-114">The Directory</span></span>  
 <span data-ttu-id="99865-115">Jeder Eintrag im Verzeichnis verweist auf einen Offset innerhalb des Heaps. Dieser Offset ist relativ zum Beginn des Heaps.</span><span class="sxs-lookup"><span data-stu-id="99865-115">Each entry in the directory refers to an offset inside the heap; that is, it is an offset that is relative to the start of the heap.</span></span> <span data-ttu-id="99865-116">Der Wert der einzelnen Einträge ist nicht notwendigerweise eindeutig. Es ist möglich, dass mehrere Verzeichniseinträge auf den gleichen Offset im Heap zeigen.</span><span class="sxs-lookup"><span data-stu-id="99865-116">The value of individual entries is not necessarily unique; it is possible for multiple directory entries to point to the same offset in the heap.</span></span>  
  
 <span data-ttu-id="99865-117">Der Verzeichnisteil der generischen Wörterbuchzuordnung weist die folgende Struktur auf:</span><span class="sxs-lookup"><span data-stu-id="99865-117">The directory portion of the generic dictionary map has the following structure:</span></span>  
  
-   <span data-ttu-id="99865-118">Die ersten 4 Bytes enthalten die Anzahl der Wörterbucheinträge (d. h. die Anzahl der relativen virtuellen Adressen im Wörterbuch).</span><span class="sxs-lookup"><span data-stu-id="99865-118">The first 4 bytes contains the number of dictionary entries (that is, the number of relative virtual addresses in the dictionary).</span></span> <span data-ttu-id="99865-119">Wir bezeichnen diesen Wert als *N*. Wenn das High-Bit festgelegt ist, werden die Einträge anhand der relativen virtuellen Adresse in aufsteigender Reihenfolge sortiert.</span><span class="sxs-lookup"><span data-stu-id="99865-119">We will refer to this value as *N*. If the high bit is set, the entries are sorted by relative virtual address in ascending order.</span></span>  
  
-   <span data-ttu-id="99865-120">Die *N* Verzeichniseinträge folgen.</span><span class="sxs-lookup"><span data-stu-id="99865-120">The *N* directory entries follow.</span></span> <span data-ttu-id="99865-121">Jeder Eintrag besteht aus 8 Bytes in zwei 4-Byte-Segmenten:</span><span class="sxs-lookup"><span data-stu-id="99865-121">Each entry consists of 8 bytes, in two 4-byte segments:</span></span>  
  
    -   <span data-ttu-id="99865-122">Bytes 0-3: RVA; relative virtuelle Adresse des Wörterbuchs.</span><span class="sxs-lookup"><span data-stu-id="99865-122">Bytes 0-3: RVA; the dictionary's relative virtual address.</span></span>  
  
    -   <span data-ttu-id="99865-123">Bytes 4-7: Offset; ein Offset relativ zum Beginn des Heaps.</span><span class="sxs-lookup"><span data-stu-id="99865-123">Bytes 4-7: Offset; an offset relative to the start of the heap.</span></span>  
  
<a name="Heap"></a>   
## <a name="the-heap"></a><span data-ttu-id="99865-124">Der Heap</span><span class="sxs-lookup"><span data-stu-id="99865-124">The Heap</span></span>  
 <span data-ttu-id="99865-125">Die Größe des Heaps kann von einem StreamReader durch Subtrahieren der Länge des Datenstroms von der Verzeichnisgröße + 4 berechnet werden.</span><span class="sxs-lookup"><span data-stu-id="99865-125">The heap’s size can be computed by a stream reader by subtracting the length of the stream from the directory size + 4.</span></span> <span data-ttu-id="99865-126">Anders ausgedrückt:</span><span class="sxs-lookup"><span data-stu-id="99865-126">In other words:</span></span>  
  
```  
Heap Size = Stream.Length – (Directory Size + 4)  
```  
  
 <span data-ttu-id="99865-127">Dabei ist die Verzeichnisgröße `N * 8`.</span><span class="sxs-lookup"><span data-stu-id="99865-127">where the directory size is `N * 8`.</span></span>  
  
 <span data-ttu-id="99865-128">Das folgende Format wird für jedes Instanziierungsinformationselement auf dem Heap verwendet:</span><span class="sxs-lookup"><span data-stu-id="99865-128">The format for each instantiation information item on the heap is:</span></span>  
  
-   <span data-ttu-id="99865-129">Die Länge dieses Instanziierungsinformationselements in Bytes im komprimierten ECMA-Metadatenformat.</span><span class="sxs-lookup"><span data-stu-id="99865-129">The length of this instantiation information item in bytes in compressed ECMA metadata format.</span></span> <span data-ttu-id="99865-130">Der Wert schließt diese Längeninformationen aus.</span><span class="sxs-lookup"><span data-stu-id="99865-130">The value excludes this length information.</span></span>  
  
-   <span data-ttu-id="99865-131">Die Anzahl der generischen instanziierungstypen oder *T*, im komprimierten ECMA-Metadatenformat.</span><span class="sxs-lookup"><span data-stu-id="99865-131">The number of generic instantiation types, or *T*, in compressed ECMA metadata format.</span></span>  
  
-   <span data-ttu-id="99865-132">*T* Typen, die jeweils im ECMA-typsignaturformat dargestellt.</span><span class="sxs-lookup"><span data-stu-id="99865-132">*T* types, each represented in ECMA type signature format.</span></span>  
  
 <span data-ttu-id="99865-133">Die Berücksichtigung der Länge für jedes Heapelement ermöglicht eine einfache Sortierung des Verzeichnisabschnitts ohne Auswirkungen auf den Heap.</span><span class="sxs-lookup"><span data-stu-id="99865-133">The inclusion of the length for each heap element enables simple sorting of the directory section without affecting the heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99865-134">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="99865-134">Requirements</span></span>  
 <span data-ttu-id="99865-135">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99865-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99865-136">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="99865-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="99865-137">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99865-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99865-138">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99865-138">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99865-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="99865-139">See also</span></span>

- [<span data-ttu-id="99865-140">ICorDebugSymbolProvider2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="99865-140">ICorDebugSymbolProvider2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-interface.md)
- [<span data-ttu-id="99865-141">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="99865-141">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
