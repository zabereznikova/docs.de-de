---
title: ICorDebugProcess6::EnableVirtualModuleSplitting-Methode
ms.date: 03/30/2017
ms.assetid: e7733bd3-68da-47f9-82ef-477db5f2e32d
ms.openlocfilehash: 56795c6879d95253383c26c92e060f252a018914
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690211"
---
# <a name="icordebugprocess6enablevirtualmodulesplitting-method"></a><span data-ttu-id="ef7ee-102">ICorDebugProcess6::EnableVirtualModuleSplitting-Methode</span><span class="sxs-lookup"><span data-stu-id="ef7ee-102">ICorDebugProcess6::EnableVirtualModuleSplitting Method</span></span>

<span data-ttu-id="ef7ee-103">Aktiviert oder deaktiviert die virtuelle Modulteilung.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-103">Enables or disables virtual module splitting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef7ee-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ef7ee-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableVirtualModuleSplitting(  
   BOOL enableSplitting  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef7ee-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ef7ee-105">Parameters</span></span>  

 `enableSplitting`  
 <span data-ttu-id="ef7ee-106">`true`, um die virtuelle Modulteilung zu aktivieren; `false`, um sie zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-106">`true` to enable virtual module splitting; `false` to disable it.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef7ee-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ef7ee-107">Remarks</span></span>  

 <span data-ttu-id="ef7ee-108">Durch die Aufteilung virtueller Module erkennt [ICorDebug](icordebug-interface.md) Module, die während des Buildprozesses zusammengeführt wurden, und stellt Sie als eine Gruppe von separaten Modulen anstelle eines einzelnen großen Moduls dar.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-108">Virtual module splitting causes [ICorDebug](icordebug-interface.md) to recognize modules that were merged together during the build process and present them as a group of separate modules rather than a single large module.</span></span> <span data-ttu-id="ef7ee-109">Dadurch wird das Verhalten der verschiedenen [ICorDebug](icordebug-interface.md) -Methoden geändert, die unten beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-109">Doing this changes the behavior of various [ICorDebug](icordebug-interface.md) methods described below.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ef7ee-110">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-110">This method is available with .NET Native only.</span></span>  
  
 <span data-ttu-id="ef7ee-111">Diese Methode ist aufrufbar, und der `enableSplitting`-Wert kann jederzeit geändert werden.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-111">This method can be called and the value of `enableSplitting` can be changed at any time.</span></span> <span data-ttu-id="ef7ee-112">Sie verursacht keine Zustands behafteten funktionalen Änderungen in einem [ICorDebug](icordebug-interface.md) -Objekt, außer das Ändern des Verhaltens der Methoden, die in der [Aufteilung virtueller Module und der nicht verwalteten Debug-APIs](#APIs) zum Zeitpunkt des Aufrufs aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-112">It does not cause any stateful functional changes in an [ICorDebug](icordebug-interface.md) object, other than altering the behavior of the methods listed in the [Virtual module splitting and the unmanaged debugging APIs](#APIs) section at the time they are called.</span></span> <span data-ttu-id="ef7ee-113">Die Verwendung virtueller Module führt beim Aufrufen dieser Methoden durchaus zu Leistungseinbußen.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-113">Using virtual modules does incur a performance penalty when calling those methods.</span></span> <span data-ttu-id="ef7ee-114">Außerdem ist möglicherweise ein signifikantes in-Memory-Caching der virtualisierten Metadaten erforderlich, um die [IMetaDataImport](../metadata/imetadataimport-interface.md) -APIs ordnungsgemäß zu implementieren. Diese Caches können auch nach der Deaktivierung der virtuellen Modul Aufteilung beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-114">In addition, significant in-memory caching of the virtualized metadata may be required to correctly implement the [IMetaDataImport](../metadata/imetadataimport-interface.md) APIs, and these caches may be retained even after virtual module splitting has been turned off.</span></span>  
  
## <a name="terminology"></a><span data-ttu-id="ef7ee-115">Begriff</span><span class="sxs-lookup"><span data-stu-id="ef7ee-115">Terminology</span></span>  

 <span data-ttu-id="ef7ee-116">Die folgenden Begriffe werden verwendet, um das Teilen virtueller Module zu beschreiben:</span><span class="sxs-lookup"><span data-stu-id="ef7ee-116">The following terms are used when describing virtual module splitting:</span></span>  
  
 <span data-ttu-id="ef7ee-117">Container-Module oder Container</span><span class="sxs-lookup"><span data-stu-id="ef7ee-117">container modules, or containers</span></span>  
 <span data-ttu-id="ef7ee-118">Die aggregierten Module.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-118">The aggregate modules.</span></span>  
  
 <span data-ttu-id="ef7ee-119">Untergeordnete Module oder virtuelle Module</span><span class="sxs-lookup"><span data-stu-id="ef7ee-119">sub-modules, or virtual modules</span></span>  
 <span data-ttu-id="ef7ee-120">Die Module, die sich in einem Container befinden.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-120">The modules found in a container.</span></span>  
  
 <span data-ttu-id="ef7ee-121">reguläre Module</span><span class="sxs-lookup"><span data-stu-id="ef7ee-121">regular modules</span></span>  
 <span data-ttu-id="ef7ee-122">Module, die zur Zeit der Erstellung nicht zusammengeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-122">Modules that were not merged at build time.</span></span> <span data-ttu-id="ef7ee-123">Hierbei handelt es sich weder um Containermodule noch um untergeordnete Module.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-123">They are neither container modules nor sub-modules.</span></span>  
  
 <span data-ttu-id="ef7ee-124">Containermodule und untergeordnete Module werden durch ICorDebugModule-Oberflächenobjekte dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-124">Both container modules and sub-modules are represented by ICorDebugModule interface objects.</span></span> <span data-ttu-id="ef7ee-125">Das Verhalten der-Schnittstelle unterscheidet sich jedoch in jedem Fall geringfügig, wie im \<x-ref to section> Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-125">However, the behavior of the interface is slightly different in each case, as the \<x-ref to section> section describes.</span></span>  
  
## <a name="modules-and-assemblies"></a><span data-ttu-id="ef7ee-126">Module und Assemblys</span><span class="sxs-lookup"><span data-stu-id="ef7ee-126">Modules and assemblies</span></span>  

 <span data-ttu-id="ef7ee-127">Assemblys mit mehreren Modulen werden nicht bei Zusammenführungen nicht unterstützt, somit stehen ein Modul und eine Assembly im Verhältnis 1:1.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-127">Multi-module assemblies are not supported for assembly merging scenarios, so there is a one-to-one relationship between a module and an assembly.</span></span> <span data-ttu-id="ef7ee-128">Zu jedem ICorDebugModule -Objekt gibt es ein entsprechendes ICorDebugAssembly-Objekt, unabhängig davon, ob es ein Container-Modul oder ein untergeordnetes Modul darstellt.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-128">Each ICorDebugModule object, regardless of whether it represents a container module or a sub-module, has a corresponding ICorDebugAssembly object.</span></span> <span data-ttu-id="ef7ee-129">Die [ICorDebugModule:: GetAssembly](icordebugmodule-getassembly-method.md) -Methode konvertiert vom Modul in die Assembly.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-129">The [ICorDebugModule::GetAssembly](icordebugmodule-getassembly-method.md) method converts from the module to the assembly.</span></span> <span data-ttu-id="ef7ee-130">Um in der anderen Richtung zuzuordnen, listet die [ICorDebugAssembly:: EnumerateModules](icordebugassembly-enumeratemodules-method.md) -Methode nur ein Modul auf.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-130">To map in the other direction, the [ICorDebugAssembly::EnumerateModules](icordebugassembly-enumeratemodules-method.md) method enumerates only 1 module.</span></span> <span data-ttu-id="ef7ee-131">Da Assembly und Modul in diesem Fall eng miteinander verknüpft sind, sind die Begriffe Assembly und Modul weitgehend austauschbar.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-131">Because assembly and module form a tightly coupled pair in this case, the terms assembly and module become largely interchangeable.</span></span>  
  
## <a name="behavioral-differences"></a><span data-ttu-id="ef7ee-132">Verhaltensunterschiede</span><span class="sxs-lookup"><span data-stu-id="ef7ee-132">Behavioral differences</span></span>  

 <span data-ttu-id="ef7ee-133">Container-Module weisen folgende Verhaltensweisen und Merkmale auf:</span><span class="sxs-lookup"><span data-stu-id="ef7ee-133">Container modules have the following behaviors and characteristics:</span></span>  
  
- <span data-ttu-id="ef7ee-134">Die Metadaten sind für alle enthaltenen untergeordneten Module zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-134">Their metadata for all of the constituent sub-modules is merged together.</span></span>  
  
- <span data-ttu-id="ef7ee-135">Ihre Typennamen können geändert werden.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-135">Their type names may be mangled.</span></span>  
  
- <span data-ttu-id="ef7ee-136">Die [ICorDebugModule:: GetName](icordebugmodule-getname-method.md) -Methode gibt den Pfad zu einem Modul auf dem Datenträger zurück.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-136">The [ICorDebugModule::GetName](icordebugmodule-getname-method.md) method returns the path to an on-disk module.</span></span>  
  
- <span data-ttu-id="ef7ee-137">Die [ICorDebugModule:: GetSize](icordebugmodule-getsize-method.md) -Methode gibt die Größe des Bilds zurück.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-137">The [ICorDebugModule::GetSize](icordebugmodule-getsize-method.md) method returns the size of that image.</span></span>  
  
- <span data-ttu-id="ef7ee-138">Mit der ICorDebugAssembly3.EnumerateContainedAssemblies-Methode werden die untergeordneten Module aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-138">The ICorDebugAssembly3.EnumerateContainedAssemblies method lists the sub-modules.</span></span>  
  
- <span data-ttu-id="ef7ee-139">Mit der ICorDebugAssembly3.GetContainerAssembly-Methode wird `S_FALSE` ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-139">The ICorDebugAssembly3.GetContainerAssembly method returns `S_FALSE`.</span></span>  
  
 <span data-ttu-id="ef7ee-140">Untergeordnete Container-Module weisen folgende Verhaltensweisen und Merkmale auf:</span><span class="sxs-lookup"><span data-stu-id="ef7ee-140">Sub-modules have the following behaviors and characteristics:</span></span>  
  
- <span data-ttu-id="ef7ee-141">Sie verfügen über einen reduzierten Satz von Metadaten, der sich nur auf die ursprünglich zugsammengeführte Assembly bezieht.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-141">They have a reduced set of metadata that corresponds only to the original assembly that was merged.</span></span>  
  
- <span data-ttu-id="ef7ee-142">Die Metadatennamen werden nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-142">The metadata names are not mangled.</span></span>  
  
- <span data-ttu-id="ef7ee-143">Die Metadatentoken entsprechen wahrscheinlich nicht den Token in der ursprünglichen Baugruppe vor dem Merge im Erstellungsprozess.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-143">Metadata tokens are unlikely to match the tokens in the original assembly before it was merged in the build process.</span></span>  
  
- <span data-ttu-id="ef7ee-144">Die [ICorDebugModule:: GetName](icordebugmodule-getname-method.md) -Methode gibt den Assemblynamen und keinen Dateipfad zurück.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-144">The [ICorDebugModule::GetName](icordebugmodule-getname-method.md) method returns the assembly name, not a file path.</span></span>  
  
- <span data-ttu-id="ef7ee-145">Die [ICorDebugModule:: GetSize](icordebugmodule-getsize-method.md) -Methode gibt die ursprüngliche Größe des nicht zusammengeführten Bilds zurück.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-145">The [ICorDebugModule::GetSize](icordebugmodule-getsize-method.md) method returns the original unmerged image size.</span></span>  
  
- <span data-ttu-id="ef7ee-146">Mit der ICorDebugAssembly3.GetContainerAssemblies-Methode wird `S_FALSE` ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-146">The ICorDebugModule3.EnumerateContainedAssemblies method returns `S_FALSE`.</span></span>  
  
- <span data-ttu-id="ef7ee-147">Die ICorDebugAssembly3.GetContainerAssembly-Methode gibt das enthaltende Modul aus.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-147">The ICorDebugAssembly3.GetContainerAssembly method returns the containing module.</span></span>  
  
## <a name="interfaces-retrieved-from-modules"></a><span data-ttu-id="ef7ee-148">Aus Modulen abgerufene Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ef7ee-148">Interfaces retrieved from modules</span></span>  

 <span data-ttu-id="ef7ee-149">Es können verschiedene Schnittstellen erstellt oder aus Modulen abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-149">A variety of interfaces can be created or retrieved from modules.</span></span> <span data-ttu-id="ef7ee-150">Dazu zählen:</span><span class="sxs-lookup"><span data-stu-id="ef7ee-150">Some of these include:</span></span>  
  
- <span data-ttu-id="ef7ee-151">Ein ICorDebugClass-Objekt, das von der [ICorDebugModule:: GetClassFromToken](icordebugmodule-getclassfromtoken-method.md) -Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-151">An ICorDebugClass object, which is returned by the [ICorDebugModule::GetClassFromToken](icordebugmodule-getclassfromtoken-method.md) method.</span></span>  
  
- <span data-ttu-id="ef7ee-152">Ein ICorDebugAssembly-Objekt, das von der [ICorDebugModule:: GetAssembly](icordebugmodule-getassembly-method.md) -Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-152">An ICorDebugAssembly object, which is returned by the [ICorDebugModule::GetAssembly](icordebugmodule-getassembly-method.md) method.</span></span>  
  
 <span data-ttu-id="ef7ee-153">Diese Objekte werden immer von [ICorDebug](icordebug-interface.md)zwischengespeichert und weisen die gleiche Zeiger Identität auf, unabhängig davon, ob Sie vom Containermodul oder einem Untermodul erstellt oder abgefragt wurden.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-153">These objects are always cached by [ICorDebug](icordebug-interface.md), and they will have the same pointer identity regardless of whether they were created or queried from the container module or a sub-module.</span></span> <span data-ttu-id="ef7ee-154">Das untergeordnete Modul bietet eine gefilterte Ansicht dieser zwischengespeicherten Objekte, jedoch keinen separaten Cache mit eigenen Kopien.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-154">The sub-module provides a filtered view of these cached objects, not a separate cache with its own copies.</span></span>  
  
<a name="APIs"></a>

## <a name="virtual-module-splitting-and-the-unmanaged-debugging-apis"></a><span data-ttu-id="ef7ee-155">Teilen virtueller Module und nicht verwalteter Debug-APIs</span><span class="sxs-lookup"><span data-stu-id="ef7ee-155">Virtual module splitting and the unmanaged debugging APIs</span></span>  

 <span data-ttu-id="ef7ee-156">In der folgende Tabelle wird gezeigt, wie sich das Teilen virtueller Module auf das Verhalten anderer Methoden in der nicht verwalteten Debug-API auswirkt.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-156">The following table shows how virtual module splitting affects the behavior of other methods in the unmanaged debugging API.</span></span>  
  
|<span data-ttu-id="ef7ee-157">Methode</span><span class="sxs-lookup"><span data-stu-id="ef7ee-157">Method</span></span>|`enableSplitting` = `true`|`enableSplitting` = `false`|  
|------------|---------------------------------|----------------------------------|  
|[<span data-ttu-id="ef7ee-158">ICorDebugFunction::GetModule</span><span class="sxs-lookup"><span data-stu-id="ef7ee-158">ICorDebugFunction::GetModule</span></span>](icordebugfunction-getmodule-method.md)|<span data-ttu-id="ef7ee-159">Gibt das untergeordnete Modul aus, in dem diese Funktion ursprünglich definiert wurde</span><span class="sxs-lookup"><span data-stu-id="ef7ee-159">Returns the sub-module this function was originally defined in</span></span>|<span data-ttu-id="ef7ee-160">Gibt das Containermodul zurück, mit dem diese Funktion zusammengeführt wurde</span><span class="sxs-lookup"><span data-stu-id="ef7ee-160">Returns the container module this function was merged into</span></span>|  
|[<span data-ttu-id="ef7ee-161">ICorDebugClass::GetModule</span><span class="sxs-lookup"><span data-stu-id="ef7ee-161">ICorDebugClass::GetModule</span></span>](icordebugclass-getmodule-method.md)|<span data-ttu-id="ef7ee-162">Gibt das untergeordnete Modul aus, in dem diese Klasse ursprünglich definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-162">Returns the sub-module this class was originally defined in.</span></span>|<span data-ttu-id="ef7ee-163">Gibt das Containermodul aus, mit dem diese Klasse zusammengeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-163">Returns the container module this class was merged into.</span></span>|  
|<span data-ttu-id="ef7ee-164">ICorDebugModuleDebugEvent::GetModule</span><span class="sxs-lookup"><span data-stu-id="ef7ee-164">ICorDebugModuleDebugEvent::GetModule</span></span>|<span data-ttu-id="ef7ee-165">Gibt das Containermodul aus, das geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-165">Returns the container module that was loaded.</span></span> <span data-ttu-id="ef7ee-166">Untergeordnete Module erhalten unabhängig von dieser Einstellung keine Ladeereignisse.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-166">Sub-modules are not given load events regardless of this setting.</span></span>|<span data-ttu-id="ef7ee-167">Gibt das Containermodul aus, das geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-167">Returns the container module that was loaded.</span></span>|  
|[<span data-ttu-id="ef7ee-168">ICorDebugAppDomain::EnumerateAssemblies</span><span class="sxs-lookup"><span data-stu-id="ef7ee-168">ICorDebugAppDomain::EnumerateAssemblies</span></span>](icordebugappdomain-enumerateassemblies-method.md)|<span data-ttu-id="ef7ee-169">Gibt eine Liste aller untergeordneten und regulären Assemblys aus; Container-Assemblys sind nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-169">Returns a list of sub-assemblies and regular assemblies; no container assemblies are included.</span></span> <span data-ttu-id="ef7ee-170">**Hinweis:**  Wenn in einer containerassembly Symbole fehlen, wird keine der zugehörigen untergeordneten Assemblys aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-170">**Note:**  If any container assembly is missing symbols, none of its sub-assemblies will be enumerated.</span></span> <span data-ttu-id="ef7ee-171">Wenn in einer regulären Baugruppe Symbole fehlen, kann die Auflistung u.U. erfolgen.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-171">If any regular assembly is missing symbols, it may or may not be enumerated.</span></span>|<span data-ttu-id="ef7ee-172">Gibt eine Liste der Container-Assemblys und regulären Assemblys aus; untergeordnete Assemblys sind nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-172">Returns a list of container assemblies and regular assemblies; no sub-assemblies are included.</span></span> <span data-ttu-id="ef7ee-173">**Hinweis:**  Wenn in einer regulären Assembly Symbole fehlen, kann diese nicht aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-173">**Note:**  If any regular assembly is missing symbols, it may or may not be enumerated.</span></span>|  
|<span data-ttu-id="ef7ee-174">[ICorDebugCode:: GetCode](icordebugcode-getcode-method.md) (nur bei verweisen auf IL-Code)</span><span class="sxs-lookup"><span data-stu-id="ef7ee-174">[ICorDebugCode::GetCode](icordebugcode-getcode-method.md) (when referring to IL code only)</span></span>|<span data-ttu-id="ef7ee-175">Gibt die IL aus, die in einem Assemblybild vor dem Merge gültig wäre.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-175">Returns IL that would be valid in a pre-merge assembly image.</span></span> <span data-ttu-id="ef7ee-176">Insbesondere werden Inline-Metadatentoken korrekt zu TypeRef-Token oder MemberRef-Token, wenn die Typen, auf die verwiesen wird, nicht im virtuellen Modul definiert werden, das den IL-Code enthält.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-176">Specifically, any inline metadata tokens will correctly be TypeRef or MemberRef tokens when the types being referred to are not defined in the virtual module containing the IL.</span></span> <span data-ttu-id="ef7ee-177">Diese TypeRef-oder Mitgliedschafts Token können im [IMetaDataImport](../metadata/imetadataimport-interface.md) -Objekt für das entsprechende virtuelle ICorDebug Module-Objekt gesucht werden.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-177">These TypeRef or MemberRef tokens can be looked up in the [IMetaDataImport](../metadata/imetadataimport-interface.md) object for the corresponding virtual ICorDebugModule object.</span></span>|<span data-ttu-id="ef7ee-178">Gibt die IL im Assemblybild nach der Zusammenführung aus.</span><span class="sxs-lookup"><span data-stu-id="ef7ee-178">Returns the IL in the post-merge assembly image.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ef7ee-179">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ef7ee-179">Requirements</span></span>  

 <span data-ttu-id="ef7ee-180">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef7ee-180">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef7ee-181">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ef7ee-181">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ef7ee-182">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef7ee-182">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef7ee-183">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef7ee-183">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef7ee-184">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ef7ee-184">See also</span></span>

- [<span data-ttu-id="ef7ee-185">ICorDebugProcess6-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ef7ee-185">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="ef7ee-186">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="ef7ee-186">Debugging Interfaces</span></span>](debugging-interfaces.md)
