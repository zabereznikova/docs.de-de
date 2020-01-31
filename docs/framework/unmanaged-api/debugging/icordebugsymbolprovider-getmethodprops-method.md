---
title: ICorDebugSymbolProvider::GetMethodProps-Methode
ms.date: 03/30/2017
ms.assetid: 8f836b80-b7a5-460b-bf76-5f0e45652aea
ms.openlocfilehash: 58642d0a9b1cfe1fd969f39fa7e5ab22a8dbfa05
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791586"
---
# <a name="icordebugsymbolprovidergetmethodprops-method"></a><span data-ttu-id="59b13-102">ICorDebugSymbolProvider::GetMethodProps-Methode</span><span class="sxs-lookup"><span data-stu-id="59b13-102">ICorDebugSymbolProvider::GetMethodProps Method</span></span>
<span data-ttu-id="59b13-103">Gibt Informationen zu Methodeneigenschaften wie das Metadatentoken der Methode und Informationen zu den generischen Parametern der Methode zurück, wenn eine relative virtuelle Adresse (RVA) in der Methode angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="59b13-103">Returns information about method properties, such as the method's metadata token and information about its generic parameters, given a relative virtual address (RVA) in that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59b13-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="59b13-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodProps(  
   [in]  ULONG32 codeRva,  
   [out] mdToken *pMethodToken,  
   [out] ULONG32 *pcGenericParams,  
   [in]  ULONG32 cbSignature,  
   [out] ULONG32 *pcbSignature,  
   [out, size_is(cbSignature), length_is(*pcbSignature)] BYTE signature[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59b13-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="59b13-105">Parameters</span></span>  
 `codeRVA`  
 <span data-ttu-id="59b13-106">[in] Eine relative virtuelle Adresse in der Methode, zu der Informationen abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="59b13-106">[in] A relative virtual address in the method about which information is to be retrieved.</span></span>  
  
 `pMethodToken`  
 <span data-ttu-id="59b13-107">[out] Ein Zeiger auf das Metadatentoken der Methode.</span><span class="sxs-lookup"><span data-stu-id="59b13-107">[out] A pointer to the method's metadata token.</span></span>  
  
 `pcGenericParams`  
 <span data-ttu-id="59b13-108">[out] Ein Zeiger auf die Anzahl der generischen Parameter, die dieser Methode zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="59b13-108">[out] A pointer to the number of generic parameters associated with this method.</span></span>  
  
 `cbSignature`  
 <span data-ttu-id="59b13-109">[in] Die Größe des `signature`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="59b13-109">[in] The size of the `signature` array.</span></span> <span data-ttu-id="59b13-110">Weitere Informationen finden Sie im Abschnitt "Hinweise".</span><span class="sxs-lookup"><span data-stu-id="59b13-110">See the Remarks section.</span></span>  
  
 `pcbSignature`  
 <span data-ttu-id="59b13-111">[out] Ein Zeiger auf die Größe des zurückgegebenen `signature`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="59b13-111">[out] A pointer to the size of the returned `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="59b13-112">[out] Ein Puffer, der die TypeSpec-Signaturen aller generischen Parameter enthält.</span><span class="sxs-lookup"><span data-stu-id="59b13-112">[out] A buffer that holds the typespec signatures of all generic parameters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59b13-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="59b13-113">Remarks</span></span>  
 <span data-ttu-id="59b13-114">Um die erforderliche Größe des `signature` Arrays der Methode zu erhalten, legen Sie das `cbSignature`-Argument auf 0 und `signature` auf **null**fest.</span><span class="sxs-lookup"><span data-stu-id="59b13-114">To get the required size of the method's `signature` array, set the `cbSignature` argument to 0 and `signature` to **null**.</span></span> <span data-ttu-id="59b13-115">Wenn die Methode zurückgegeben wird, enthält `pcbSignature` die Anzahl der für das `signature`-Array erforderlichen Bytes.</span><span class="sxs-lookup"><span data-stu-id="59b13-115">When the method returns, `pcbSignature` will contain the number of bytes required for the `signature` array.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="59b13-116">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="59b13-116">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59b13-117">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="59b13-117">Requirements</span></span>  
 <span data-ttu-id="59b13-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59b13-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59b13-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="59b13-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="59b13-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59b13-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59b13-121">**.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59b13-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59b13-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="59b13-122">See also</span></span>

- [<span data-ttu-id="59b13-123">GetTypeProps-Methode</span><span class="sxs-lookup"><span data-stu-id="59b13-123">GetTypeProps Method</span></span>](icordebugsymbolprovider-gettypeprops-method.md)
- [<span data-ttu-id="59b13-124">ICorDebugSymbolProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="59b13-124">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="59b13-125">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="59b13-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
