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
ms.openlocfilehash: d623fe862eaf5902fd89d0e512dd07f73a03246f
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860821"
---
# <a name="dacpmethoddescdata-structure"></a><span data-ttu-id="199fe-102">DacpMethodDescData-Struktur</span><span class="sxs-lookup"><span data-stu-id="199fe-102">DacpMethodDescData Structure</span></span>

<span data-ttu-id="199fe-103">Definiert einen Transport Puffer für die Laufzeitinformationen einer Methode.</span><span class="sxs-lookup"><span data-stu-id="199fe-103">Defines a transport buffer for a method's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="199fe-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="199fe-104">Syntax</span></span>

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

## <a name="members"></a><span data-ttu-id="199fe-105">Members</span><span class="sxs-lookup"><span data-stu-id="199fe-105">Members</span></span>

| <span data-ttu-id="199fe-106">Member</span><span class="sxs-lookup"><span data-stu-id="199fe-106">Member</span></span>                       | <span data-ttu-id="199fe-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="199fe-107">Description</span></span>                                                                                     |
| ---------------------------- | ----------------------------------------------------------------------------------------------- |
| `bHasNativeCode`             | <span data-ttu-id="199fe-108">Gibt an, ob die Laufzeit nativen Code für die angegebene Instanziierung der Methode verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="199fe-108">Indicates if the runtime has native code available for the given instantiation of the method.</span></span> |
| `bIsDynamic`                 | <span data-ttu-id="199fe-109">Gibt an, ob die Methode mithilfe der Lightweight-Codegenerierung dynamisch generiert wird.</span><span class="sxs-lookup"><span data-stu-id="199fe-109">Indicates if the method is generated dynamically through lightweight code generation.</span></span>           |
| `wSlotNumber`                | <span data-ttu-id="199fe-110">Die Slotnummer der Methode in der Methoden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="199fe-110">The method's slot number in the method table.</span></span>                                                   |
| `NativeCodeAddr`             | <span data-ttu-id="199fe-111">Die ursprüngliche Native Adresse der Methode.</span><span class="sxs-lookup"><span data-stu-id="199fe-111">The method's initial native address.</span></span>                                                            |
| `data`                       | <span data-ttu-id="199fe-112">Zeiger auf einen Puffer, der intern von der Laufzeit verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="199fe-112">Pointer to a buffer used internally by the runtime.</span></span>                                             |
| `MethodDescPtr`              | <span data-ttu-id="199fe-113">Zeiger auf den `MethodDesc` in der Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="199fe-113">Pointer to the `MethodDesc` in the runtime.</span></span>                                                     |
| `nativeCodeInfo`             | <span data-ttu-id="199fe-114">Zeiger auf einen Puffer, der intern von der Laufzeit verwendet wird, um Methoden zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="199fe-114">Pointer to a buffer used internally by the runtime to track methods.</span></span>                            |
| `moduleInfo`                 | <span data-ttu-id="199fe-115">Zeiger auf einen Puffer, der von der Common Language Runtime für Modul Informationen intern verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="199fe-115">Pointer to a buffer used internally by the runtime for module information.</span></span>                      |
| `MDToken`                    | <span data-ttu-id="199fe-116">Token, das mit der angegebenen Methode verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="199fe-116">Token associated with the given method.</span></span>                                                         |
| `payloadGC`                  | <span data-ttu-id="199fe-117">Zeiger auf einen Garbage Collection Puffer, der intern von der Laufzeit verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="199fe-117">Pointer to a garbage collection buffer used internally by the runtime.</span></span>                          |
| `payloadGC2`                 | <span data-ttu-id="199fe-118">Zeiger auf einen Garbage Collection Puffer, der intern von der Laufzeit verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="199fe-118">Pointer to a garbage collection buffer used internally by the runtime.</span></span>                          |
| `managedDynamicMethodObject` | <span data-ttu-id="199fe-119">Wenn die Methode dynamisch ist, verwendet die Common Language Runtime diesen Puffer intern für die Informations Verfolgung.</span><span class="sxs-lookup"><span data-stu-id="199fe-119">If the method is dynamic, the runtime uses this buffer internally for information tracking.</span></span>     |
| `requestedIP`                | <span data-ttu-id="199fe-120">Wird verwendet, um die Struktur pro Anforderung aufzufüllen, wenn eine systemeigene Code Adresse angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="199fe-120">Used to populate the structure per request when given a native code address.</span></span>                    |
| `rejitDataCurrent`           | <span data-ttu-id="199fe-121">Informationen zur neuesten instrumentierten Version der-Methode.</span><span class="sxs-lookup"><span data-stu-id="199fe-121">Information about the latest instrumented version of the method.</span></span>                                   |
| `rejitDataRequested`         | <span data-ttu-id="199fe-122">ReJIT-Informationen für die angeforderte Native Adresse.</span><span class="sxs-lookup"><span data-stu-id="199fe-122">Rejit information for the requested native address.</span></span>                                             |
| `cJittedRejitVersions`       | <span data-ttu-id="199fe-123">Gibt an, wie oft die Methode durch Instrumentation erneut generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="199fe-123">Number of times the method has been rejitted through instrumentation.</span></span>                           |

## <a name="remarks"></a><span data-ttu-id="199fe-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="199fe-124">Remarks</span></span>

<span data-ttu-id="199fe-125">Diese Struktur befindet sich innerhalb der Laufzeit und wird nicht durch Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="199fe-125">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="199fe-126">Um es zu verwenden, definieren Sie die Struktur wie oben angegeben.</span><span class="sxs-lookup"><span data-stu-id="199fe-126">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="199fe-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="199fe-127">Requirements</span></span>
<span data-ttu-id="199fe-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="199fe-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="199fe-129">**Header:** Gar</span><span class="sxs-lookup"><span data-stu-id="199fe-129">**Header:** None</span></span>  
<span data-ttu-id="199fe-130">**Bibliothek:** Gar</span><span class="sxs-lookup"><span data-stu-id="199fe-130">**Library:** None</span></span>  
<span data-ttu-id="199fe-131">**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="199fe-131">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="199fe-132">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="199fe-132">See also</span></span>

- [<span data-ttu-id="199fe-133">Debuggen</span><span class="sxs-lookup"><span data-stu-id="199fe-133">Debugging</span></span>](index.md)
- [<span data-ttu-id="199fe-134">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="199fe-134">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="199fe-135">Allgemeine Datentypen</span><span class="sxs-lookup"><span data-stu-id="199fe-135">Common Data Types</span></span>](../common-data-types-unmanaged-api-reference.md)
