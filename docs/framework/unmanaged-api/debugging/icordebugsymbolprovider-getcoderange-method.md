---
title: ICorDebugSymbolProvider::GetCodeRange-Methode
ms.date: 03/30/2017
ms.assetid: 49a2451f-d250-4e73-aa96-9ff49d9f11c6
ms.openlocfilehash: dbe042641cadae182efac30502a70631be359bbe
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791643"
---
# <a name="icordebugsymbolprovidergetcoderange-method"></a><span data-ttu-id="4480a-102">ICorDebugSymbolProvider::GetCodeRange-Methode</span><span class="sxs-lookup"><span data-stu-id="4480a-102">ICorDebugSymbolProvider::GetCodeRange Method</span></span>
<span data-ttu-id="4480a-103">Ruft die Startadresse und Größe einer Methode ab, wenn eine relative virtuelle Adresse (RVA) in der Methode angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="4480a-103">Gets the method start address and size given a relative virtual address (RVA) in a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4480a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4480a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCodeRange(  
   [in] ULONG32 codeRva,   
   [out] ULONG32* pCodeStartAddress,   
   [out] ULONG32* pCodeSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4480a-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="4480a-105">Parameters</span></span>  
 `codeRva`  
 <span data-ttu-id="4480a-106">[in] Die relative virtuelle Adresse (RVA) in einer Methode.</span><span class="sxs-lookup"><span data-stu-id="4480a-106">[in] The relative virtual address (RVA) in a method.</span></span>  
  
 `pCodeStartAddress`  
 <span data-ttu-id="4480a-107">[out] Ein Zeiger auf die Startadresse der Methode.</span><span class="sxs-lookup"><span data-stu-id="4480a-107">[out] A pointer to the starting address of the method.</span></span>  
  
 `pCodeSize`  
 <span data-ttu-id="4480a-108">Ein Zeiger auf die Größe des Codes der Methode (die Anzahl von Bytes des Codes der Methode).</span><span class="sxs-lookup"><span data-stu-id="4480a-108">A pointer to the method code size (the number of bytes of the method's code).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4480a-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4480a-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4480a-110">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4480a-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4480a-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4480a-111">Requirements</span></span>  
 <span data-ttu-id="4480a-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4480a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4480a-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4480a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4480a-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4480a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4480a-115">**.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4480a-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4480a-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4480a-116">See also</span></span>

- [<span data-ttu-id="4480a-117">ICorDebugSymbolProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4480a-117">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="4480a-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="4480a-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
