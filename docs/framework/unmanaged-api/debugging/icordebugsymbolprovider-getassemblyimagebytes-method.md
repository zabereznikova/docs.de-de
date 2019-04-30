---
title: ICorDebugSymbolProvider::GetAssemblyImageBytes-Methode
ms.date: 03/30/2017
ms.assetid: 3db215aa-e180-4f70-8d23-6d5a0ffbc8e5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 103e724c37ae356729dd5bba3ff66c0f443f6eaa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61953529"
---
# <a name="icordebugsymbolprovidergetassemblyimagebytes-method"></a><span data-ttu-id="b34a6-102">ICorDebugSymbolProvider::GetAssemblyImageBytes-Methode</span><span class="sxs-lookup"><span data-stu-id="b34a6-102">ICorDebugSymbolProvider::GetAssemblyImageBytes Method</span></span>
<span data-ttu-id="b34a6-103">Liest Daten aus einer zusammengeführten Assembly, wenn eine relative virtuelle Adresse (RVA) in der zusammengeführten Assembly angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="b34a6-103">Reads data from a merged assembly given a relative virtual address (RVA) in the merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b34a6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b34a6-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyImageBytes(  
   [in] CORDB_ADDRESS rva,   
   [in] ULONG32 length,   
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b34a6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b34a6-105">Parameters</span></span>  
 `rva`  
 <span data-ttu-id="b34a6-106">[in] Eine relative virtuelle Adresse (RVA) in einer zusammengeführten Assembly.</span><span class="sxs-lookup"><span data-stu-id="b34a6-106">[in] A relative virtual address (RVA) in a merged assembly.</span></span>  
  
 `length`  
 <span data-ttu-id="b34a6-107">Die Anzahl der Bytes, die aus der zusammengeführten Assembly gelesen. werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b34a6-107">The number of bytes to read from the merged assembly.</span></span>  
  
 `ppMemoryBuffer`  
 <span data-ttu-id="b34a6-108">Ein Zeiger auf die Adresse einer [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) -Objekt, das Informationen zu dem Speicherpuffer mit Metadaten der zusammengeführten Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="b34a6-108">A pointer to the address of an [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) object that contains information about the memory buffer with merged assembly metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b34a6-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b34a6-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b34a6-110">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b34a6-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b34a6-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b34a6-111">Requirements</span></span>  
 <span data-ttu-id="b34a6-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b34a6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b34a6-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b34a6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b34a6-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b34a6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b34a6-115">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b34a6-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b34a6-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b34a6-116">See also</span></span>

- [<span data-ttu-id="b34a6-117">ICorDebugSymbolProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b34a6-117">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="b34a6-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b34a6-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
