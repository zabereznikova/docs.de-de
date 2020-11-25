---
title: DacpMethodDescData-Struktur
ms.date: 02/01/2019
api.name:
- DacpMethodDescData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpMethodDescData Structure
helpviewer.keywords:
- DacpMethodDescData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: dcf01c00a106c131646a16597dca4092a06c5983
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723063"
---
# <a name="dacpmethoddescdata-structure"></a><span data-ttu-id="15f3d-102">DacpMethodDescData-Struktur</span><span class="sxs-lookup"><span data-stu-id="15f3d-102">DacpMethodDescData Structure</span></span>

<span data-ttu-id="15f3d-103">Definiert einen Transport Puffer für die Laufzeitinformationen einer Methode.</span><span class="sxs-lookup"><span data-stu-id="15f3d-103">Defines a transport buffer for a method's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="15f3d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="15f3d-104">Syntax</span></span>

```cpp
struct DacpMethodDescData
{
    int             bHasNativeCode;
    int             bIsDynamic;
    unsigned short  wSlotNumber;
    CLRDATA_ADDRESS NativeCodeAddr;
    CLRDATA_ADDRESS data;
    CLRDATA_ADDRESS MethodDescPtr;
    CLRDATA_ADDRESS nativeCodeInfo;
    CLRDATA_ADDRESS moduleInfo;
    mdToken         MDToken;
    CLRDATA_ADDRESS payloadGC;
    CLRDATA_ADDRESS payloadGC2;
    CLRDATA_ADDRESS managedDynamicMethodObject;
    CLRDATA_ADDRESS requestedIP;
    DacpReJitData   rejitDataCurrent;
    DacpReJitData   rejitDataRequested;
    unsigned long   cJittedRejitVersions;
};
```

## <a name="members"></a><span data-ttu-id="15f3d-105">Member</span><span class="sxs-lookup"><span data-stu-id="15f3d-105">Members</span></span>

| <span data-ttu-id="15f3d-106">Member</span><span class="sxs-lookup"><span data-stu-id="15f3d-106">Member</span></span>                       | <span data-ttu-id="15f3d-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="15f3d-107">Description</span></span>                                                                                     |
| ---------------------------- | ----------------------------------------------------------------------------------------------- |
| `bHasNativeCode`             | <span data-ttu-id="15f3d-108">Gibt an, ob die Laufzeit nativen Code für die angegebene Instanziierung der Methode verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="15f3d-108">Indicates if the runtime has native code available for the given instantiation of the method.</span></span> |
| `bIsDynamic`                 | <span data-ttu-id="15f3d-109">Gibt an, ob die Methode mithilfe der Lightweight-Codegenerierung dynamisch generiert wird.</span><span class="sxs-lookup"><span data-stu-id="15f3d-109">Indicates if the method is generated dynamically through lightweight code generation.</span></span>           |
| `wSlotNumber`                | <span data-ttu-id="15f3d-110">Die Slotnummer der Methode in der Methoden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="15f3d-110">The method's slot number in the method table.</span></span>                                                   |
| `NativeCodeAddr`             | <span data-ttu-id="15f3d-111">Die ursprüngliche Native Adresse der Methode.</span><span class="sxs-lookup"><span data-stu-id="15f3d-111">The method's initial native address.</span></span>                                                            |
| `data`                       | <span data-ttu-id="15f3d-112">Zeiger auf einen Puffer, der intern von der Laufzeit verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="15f3d-112">Pointer to a buffer used internally by the runtime.</span></span>                                             |
| `MethodDescPtr`              | <span data-ttu-id="15f3d-113">Zeiger auf den `MethodDesc` in der Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="15f3d-113">Pointer to the `MethodDesc` in the runtime.</span></span>                                                     |
| `nativeCodeInfo`             | <span data-ttu-id="15f3d-114">Zeiger auf einen Puffer, der intern von der Laufzeit verwendet wird, um Methoden zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="15f3d-114">Pointer to a buffer used internally by the runtime to track methods.</span></span>                            |
| `moduleInfo`                 | <span data-ttu-id="15f3d-115">Zeiger auf einen Puffer, der von der Common Language Runtime für Modul Informationen intern verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="15f3d-115">Pointer to a buffer used internally by the runtime for module information.</span></span>                      |
| `MDToken`                    | <span data-ttu-id="15f3d-116">Token, das mit der angegebenen Methode verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="15f3d-116">Token associated with the given method.</span></span>                                                         |
| `payloadGC`                  | <span data-ttu-id="15f3d-117">Zeiger auf einen Garbage Collection Puffer, der intern von der Laufzeit verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="15f3d-117">Pointer to a garbage collection buffer used internally by the runtime.</span></span>                          |
| `payloadGC2`                 | <span data-ttu-id="15f3d-118">Zeiger auf einen Garbage Collection Puffer, der intern von der Laufzeit verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="15f3d-118">Pointer to a garbage collection buffer used internally by the runtime.</span></span>                          |
| `managedDynamicMethodObject` | <span data-ttu-id="15f3d-119">Wenn die Methode dynamisch ist, verwendet die Common Language Runtime diesen Puffer intern für die Informations Verfolgung.</span><span class="sxs-lookup"><span data-stu-id="15f3d-119">If the method is dynamic, the runtime uses this buffer internally for information tracking.</span></span>     |
| `requestedIP`                | <span data-ttu-id="15f3d-120">Wird verwendet, um die Struktur pro Anforderung aufzufüllen, wenn eine systemeigene Code Adresse angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="15f3d-120">Used to populate the structure per request when given a native code address.</span></span>                    |
| `rejitDataCurrent`           | <span data-ttu-id="15f3d-121">Informationen zur neuesten instrumentierten Version der-Methode.</span><span class="sxs-lookup"><span data-stu-id="15f3d-121">Information about the latest instrumented version of the method.</span></span>                                   |
| `rejitDataRequested`         | <span data-ttu-id="15f3d-122">ReJIT-Informationen für die angeforderte Native Adresse.</span><span class="sxs-lookup"><span data-stu-id="15f3d-122">Rejit information for the requested native address.</span></span>                                             |
| `cJittedRejitVersions`       | <span data-ttu-id="15f3d-123">Gibt an, wie oft die Methode durch Instrumentation erneut generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="15f3d-123">Number of times the method has been rejitted through instrumentation.</span></span>                           |

## <a name="remarks"></a><span data-ttu-id="15f3d-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="15f3d-124">Remarks</span></span>

<span data-ttu-id="15f3d-125">Diese Struktur befindet sich innerhalb der Laufzeit und wird nicht durch Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="15f3d-125">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="15f3d-126">Um es zu verwenden, definieren Sie die Struktur wie oben angegeben.</span><span class="sxs-lookup"><span data-stu-id="15f3d-126">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="15f3d-127">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="15f3d-127">Requirements</span></span>

<span data-ttu-id="15f3d-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15f3d-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="15f3d-129">**Header:** Gar</span><span class="sxs-lookup"><span data-stu-id="15f3d-129">**Header:** None</span></span>  
<span data-ttu-id="15f3d-130">**Bibliothek:** Gar</span><span class="sxs-lookup"><span data-stu-id="15f3d-130">**Library:** None</span></span>  
<span data-ttu-id="15f3d-131">**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="15f3d-131">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="15f3d-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="15f3d-132">See also</span></span>

- [<span data-ttu-id="15f3d-133">Debuggen</span><span class="sxs-lookup"><span data-stu-id="15f3d-133">Debugging</span></span>](index.md)
- [<span data-ttu-id="15f3d-134">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="15f3d-134">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="15f3d-135">Allgemeine Datentypen</span><span class="sxs-lookup"><span data-stu-id="15f3d-135">Common Data Types</span></span>](../common-data-types-unmanaged-api-reference.md)
