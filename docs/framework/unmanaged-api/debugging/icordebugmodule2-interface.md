---
title: ICorDebugModule2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugModule2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2
helpviewer_keywords:
- ICorDebugModule2 interface [.NET Framework debugging]
ms.assetid: 0847e64f-fdbe-4c96-8168-da20fdc84d80
topic_type:
- apiref
ms.openlocfilehash: 2b8e6048dd6b8df71ac3dddcc4397f6d512127c7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695880"
---
# <a name="icordebugmodule2-interface"></a><span data-ttu-id="d75ff-102">ICorDebugModule2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d75ff-102">ICorDebugModule2 Interface</span></span>

<span data-ttu-id="d75ff-103">Dient als logische Erweiterung der ICorDebugModule-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="d75ff-103">Serves as a logical extension to the ICorDebugModule interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d75ff-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="d75ff-104">Methods</span></span>  
  
|<span data-ttu-id="d75ff-105">Methode</span><span class="sxs-lookup"><span data-stu-id="d75ff-105">Method</span></span>|<span data-ttu-id="d75ff-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d75ff-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d75ff-107">ApplyChanges-Methode</span><span class="sxs-lookup"><span data-stu-id="d75ff-107">ApplyChanges Method</span></span>](icordebugmodule2-applychanges-method.md)|<span data-ttu-id="d75ff-108">Wendet die Änderungen an den Metadaten und den Änderungen im MSIL-Code (Microsoft Intermediate Language) auf den laufenden Prozess an.</span><span class="sxs-lookup"><span data-stu-id="d75ff-108">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>|  
|[<span data-ttu-id="d75ff-109">GetJITCompilerFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="d75ff-109">GetJITCompilerFlags Method</span></span>](icordebugmodule2-getjitcompilerflags-method.md)|<span data-ttu-id="d75ff-110">Ruft die Flags ab, die die JIT-Kompilierung (Just-in-Time) für dieses Steuerelement steuern `ICorDebugModule2` .</span><span class="sxs-lookup"><span data-stu-id="d75ff-110">Gets the flags that control the just-in-time (JIT) compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="d75ff-111">ResolveAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="d75ff-111">ResolveAssembly Method</span></span>](icordebugmodule2-resolveassembly-method.md)|<span data-ttu-id="d75ff-112">Löst die Assembly auf, auf die vom angegebenen Metadatentoken verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="d75ff-112">Resolves the assembly referenced by the specified metadata token.</span></span>|  
|[<span data-ttu-id="d75ff-113">SetJITCompilerFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="d75ff-113">SetJITCompilerFlags Method</span></span>](icordebugmodule2-setjitcompilerflags-method.md)|<span data-ttu-id="d75ff-114">Legt die Flags fest, die die JIT-Kompilierung für dieses Steuern `ICorDebugModule2` .</span><span class="sxs-lookup"><span data-stu-id="d75ff-114">Sets the flags that control the JIT compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="d75ff-115">SetJMCStatus-Methode</span><span class="sxs-lookup"><span data-stu-id="d75ff-115">SetJMCStatus Method</span></span>](icordebugmodule2-setjmcstatus-method.md)|<span data-ttu-id="d75ff-116">Legt den JMC-Status (nur eigenen Code) aller Methoden aller-Klassen in diesem `ICorDebugModule2` auf den angegebenen Wert fest, mit Ausnahme der Werte im- `pTokens` Array, die auf den umgekehrten Wert festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="d75ff-116">Sets the Just My Code (JMC) status of all methods of all the classes in this `ICorDebugModule2` to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d75ff-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d75ff-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d75ff-118">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d75ff-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d75ff-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d75ff-119">Requirements</span></span>  

 <span data-ttu-id="d75ff-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d75ff-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d75ff-121">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d75ff-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d75ff-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d75ff-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d75ff-123">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d75ff-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d75ff-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d75ff-124">See also</span></span>

- [<span data-ttu-id="d75ff-125">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="d75ff-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
