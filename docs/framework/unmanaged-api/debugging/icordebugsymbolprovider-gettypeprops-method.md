---
title: ICorDebugSymbolProvider::GetTypeProps-Methode
ms.date: 03/30/2017
ms.assetid: 35ac4140-91ea-4c77-b1c4-1daf41986ca5
ms.openlocfilehash: 4738d35aabbc2197c796405e0657607f75ff685d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95694502"
---
# <a name="icordebugsymbolprovidergettypeprops-method"></a><span data-ttu-id="93a28-102">ICorDebugSymbolProvider::GetTypeProps-Methode</span><span class="sxs-lookup"><span data-stu-id="93a28-102">ICorDebugSymbolProvider::GetTypeProps Method</span></span>

<span data-ttu-id="93a28-103">Gibt anhand einer relativen virtuellen Adresse (RVA) in einem VTable Informationen zu den Eigenschaften eines Typs wie die Anzahl der Signaturen der generischen Parameter zurück.</span><span class="sxs-lookup"><span data-stu-id="93a28-103">Returns information about a type's properties, such as the number of signature of its generic parameters, given a relative virtual address (RVA) in a vtable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93a28-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="93a28-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeProps(  
   [in]  ULONG32 vtableRva,  
   [in]  ULONG32 cbSignature,  
   [out] ULONG32 *pcbSignature,  
   [out, size_is(cbSignature), length_is(*pcbSignature)] BYTE signature[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="93a28-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="93a28-105">Parameters</span></span>  

 `tableRva`  
 <span data-ttu-id="93a28-106">[in] Eine relative virtuelle Adresse (RVA) in einem VTable.</span><span class="sxs-lookup"><span data-stu-id="93a28-106">[in] A relative virtual address (RVA) in a vtable.</span></span>  
  
 `cbSignature`  
 <span data-ttu-id="93a28-107">[in] Die Größe des `signature`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="93a28-107">[in] The size of the `signature` array.</span></span> <span data-ttu-id="93a28-108">Weitere Informationen finden Sie im Abschnitt mit den Hinweisen.</span><span class="sxs-lookup"><span data-stu-id="93a28-108">See the Remarks section.</span></span>  
  
 `pcbSignature`  
 <span data-ttu-id="93a28-109">[out] [out] Ein Zeiger auf die Größe des zurückgegebenen `signature`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="93a28-109">[out] [out] A pointer to the size of the returned `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="93a28-110">[out] Ein Puffer, der die TypeSpec-Signaturen aller generischen Parameter enthält.</span><span class="sxs-lookup"><span data-stu-id="93a28-110">[out] A buffer that holds the typespec signatures of all generic parameters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="93a28-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="93a28-111">Remarks</span></span>  

 <span data-ttu-id="93a28-112">Um die erforderliche Größe des-Arrays des Typs zu erhalten `signature` , legen Sie das- `cbSignature` Argument auf 0 und `signature` auf **null** fest.</span><span class="sxs-lookup"><span data-stu-id="93a28-112">To get the required size of the type's `signature` array, set the `cbSignature` argument to 0 and `signature` to **null**.</span></span> <span data-ttu-id="93a28-113">Wenn die Methode zurückgegeben wird, enthält `pcbSignature` die Anzahl der für das `signature`-Array erforderlichen Bytes.</span><span class="sxs-lookup"><span data-stu-id="93a28-113">When the method returns, `pcbSignature` will contain the number of bytes required for the `signature` array.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="93a28-114">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="93a28-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93a28-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="93a28-115">Requirements</span></span>  

 <span data-ttu-id="93a28-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93a28-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93a28-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="93a28-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="93a28-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="93a28-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="93a28-119">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93a28-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93a28-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="93a28-120">See also</span></span>

- [<span data-ttu-id="93a28-121">GetMethodProps-Methode</span><span class="sxs-lookup"><span data-stu-id="93a28-121">GetMethodProps Method</span></span>](icordebugsymbolprovider-getmethodprops-method.md)
- [<span data-ttu-id="93a28-122">ICorDebugSymbolProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="93a28-122">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="93a28-123">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="93a28-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
