---
title: <useLegacyJit>-Element
ms.date: 04/26/2017
ms.assetid: c2cf97f0-9262-4f1f-a754-5568b51110ad
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d79479d1836963fcbdaaf8d40bfc3648b88c4a3
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663413"
---
# <a name="uselegacyjit-element"></a><span data-ttu-id="af146-102">\<useLegacyJit>-Element</span><span class="sxs-lookup"><span data-stu-id="af146-102">\<useLegacyJit> Element</span></span>

<span data-ttu-id="af146-103">Legt fest, ob die Runtime den 64-Bit-JIT-Legacycompiler für die Just-in-Time-Kompilierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="af146-103">Determines whether the common language runtime uses the legacy 64-bit JIT compiler for just-in-time compilation.</span></span>  
  
<span data-ttu-id="af146-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="af146-104">\<configuration></span></span>  
<span data-ttu-id="af146-105">\<Lauf Zeit ></span><span class="sxs-lookup"><span data-stu-id="af146-105">\<runtime></span></span>  
<span data-ttu-id="af146-106">\<useLegacyJit></span><span class="sxs-lookup"><span data-stu-id="af146-106">\<useLegacyJit></span></span>
  
## <a name="syntax"></a><span data-ttu-id="af146-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="af146-107">Syntax</span></span>  
  
```xml
<useLegacyJit enabled=0|1 />
```

<span data-ttu-id="af146-108">Beim Elementnamen `useLegacyJit` wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="af146-108">The element name `useLegacyJit` is case-sensitive.</span></span>
  
## <a name="attributes-and-elements"></a><span data-ttu-id="af146-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="af146-109">Attributes and elements</span></span>

<span data-ttu-id="af146-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="af146-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af146-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="af146-111">Attributes</span></span>  
  
| <span data-ttu-id="af146-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="af146-112">Attribute</span></span> | <span data-ttu-id="af146-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af146-113">Description</span></span>                                                                                   |  
| --------- | --------------------------------------------------------------------------------------------- |  
| `enabled` | <span data-ttu-id="af146-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="af146-114">Required attribute.</span></span><br><br><span data-ttu-id="af146-115">Gibt an, ob die Laufzeit den Legacy-JIT-Compiler mit 64-Bit verwendet.</span><span class="sxs-lookup"><span data-stu-id="af146-115">Specifies whether the runtime uses the legacy 64-bit JIT compiler.</span></span> |  
  
### <a name="enabled-attribute"></a><span data-ttu-id="af146-116">aktiviertes Attribut</span><span class="sxs-lookup"><span data-stu-id="af146-116">enabled attribute</span></span>  
  
| <span data-ttu-id="af146-117">Wert</span><span class="sxs-lookup"><span data-stu-id="af146-117">Value</span></span> | <span data-ttu-id="af146-118">Description</span><span class="sxs-lookup"><span data-stu-id="af146-118">Description</span></span>                                                                                                         |  
| ----- | ------------------------------------------------------------------------------------------------------------------- |  
| <span data-ttu-id="af146-119">0</span><span class="sxs-lookup"><span data-stu-id="af146-119">0</span></span>     | <span data-ttu-id="af146-120">Der Common Language Runtime verwendet den neuen 64-Bit-JIT-Compiler, der in der .NET Framework 4,6 und höheren Versionen enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="af146-120">The common language runtime uses the new 64-bit JIT compiler included in the .NET Framework 4.6 and later versions.</span></span> |  
| <span data-ttu-id="af146-121">1</span><span class="sxs-lookup"><span data-stu-id="af146-121">1</span></span>     | <span data-ttu-id="af146-122">Der Common Language Runtime verwendet den älteren JIT-Compiler von 64 Bit.</span><span class="sxs-lookup"><span data-stu-id="af146-122">The common language runtime uses the older 64-bit JIT compiler.</span></span>                                                     |  
  
### <a name="child-elements"></a><span data-ttu-id="af146-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="af146-123">Child elements</span></span>

<span data-ttu-id="af146-124">None</span><span class="sxs-lookup"><span data-stu-id="af146-124">None</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="af146-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="af146-125">Parent elements</span></span>  
  
| <span data-ttu-id="af146-126">Element</span><span class="sxs-lookup"><span data-stu-id="af146-126">Element</span></span>         | <span data-ttu-id="af146-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af146-127">Description</span></span>                                                                                                       |  
| --------------- | ----------------------------------------------------------------------------------------------------------------- |  
| `configuration` | <span data-ttu-id="af146-128">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="af146-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |  
| `runtime`       | <span data-ttu-id="af146-129">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="af146-129">Contains information about runtime initialization options.</span></span>                                                        |  
  
## <a name="remarks"></a><span data-ttu-id="af146-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="af146-130">Remarks</span></span>  

<span data-ttu-id="af146-131">Beginnend mit dem .NET Framework 4,6 verwendet die Common Language Runtime standardmäßig einen neuen 64-Bit-Compiler für die Just-in-time (JIT)-Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="af146-131">Starting with the .NET Framework 4.6, the common language runtime uses a new 64-bit compiler for Just-In-Time (JIT) compilation by default.</span></span> <span data-ttu-id="af146-132">In einigen Fällen kann dies zu einem Unterschied im Verhalten von Anwendungscode führen, der von der vorherigen Version des JIT-Compilers der 64-Bit-Version JIT-kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="af146-132">In some cases, this may result in a difference in behavior from application code that was JIT-compiled by the previous version of the 64-bit JIT compiler.</span></span> <span data-ttu-id="af146-133">Indem Sie das `enabled` -Attribut `<useLegacyJit>` des-Elements `1`auf festlegen, können Sie den neuen 64-Bit-JIT-Compiler deaktivieren und stattdessen die App mithilfe des Legacy-JIT-Compilers (64-Bit) kompilieren.</span><span class="sxs-lookup"><span data-stu-id="af146-133">By setting the `enabled` attribute of the `<useLegacyJit>` element to `1`, you can disable the new 64-bit JIT compiler and instead compile your app using the legacy 64-bit JIT compiler.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="af146-134">Das `<useLegacyJit>` Element wirkt sich nur auf die JIT-Kompilierung 64-Bit aus</span><span class="sxs-lookup"><span data-stu-id="af146-134">The `<useLegacyJit>` element affects 64-bit JIT compilation only.</span></span> <span data-ttu-id="af146-135">Die Kompilierung mit dem 32-Bit-JIT-Compiler ist nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="af146-135">Compilation with the 32-bit JIT compiler is unaffected.</span></span>  
  
<span data-ttu-id="af146-136">Anstatt eine Konfigurationsdatei Einstellung zu verwenden, können Sie den Legacy-JIT-Compiler von 64 auf zwei weitere Arten aktivieren:</span><span class="sxs-lookup"><span data-stu-id="af146-136">Instead of using a configuration file setting, you can enable the legacy 64-bit JIT compiler in two other ways:</span></span>  
  
- <span data-ttu-id="af146-137">Festlegen einer Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="af146-137">Setting an environment variable</span></span>

  <span data-ttu-id="af146-138">Legen Sie `COMPLUS_useLegacyJit` die Umgebungsvariable entweder `0` auf (verwenden Sie den neuen 64-Bit-JIT `1` -Compiler) oder (verwenden Sie den älteren 64-Bit-JIT-Compiler):</span><span class="sxs-lookup"><span data-stu-id="af146-138">Set the `COMPLUS_useLegacyJit` environment variable to either `0` (use the new 64-bit JIT compiler) or `1` (use the older 64-bit JIT compiler):</span></span>
  
  ```  
  COMPLUS_useLegacyJit=0|1  
  ```  
  
  <span data-ttu-id="af146-139">Die Umgebungsvariable verfügt über einen globalen Gültigkeits *Bereich*. Dies bedeutet, dass Sie sich auf alle auf dem Computer durchgeführten Anwendungen auswirkt.</span><span class="sxs-lookup"><span data-stu-id="af146-139">The environment variable has *global scope*, which means that it affects all applications run on the machine.</span></span> <span data-ttu-id="af146-140">Wenn diese Einstellung festgelegt ist, kann Sie von der Einstellung für die Anwendungs Konfigurationsdatei überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="af146-140">If set, it can be overridden by the application configuration file setting.</span></span> <span data-ttu-id="af146-141">Beim Namen der Umgebungsvariablen wird die Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="af146-141">The environment variable name is not case-sensitive.</span></span>
  
- <span data-ttu-id="af146-142">Hinzufügen eines Registrierungsschlüssels</span><span class="sxs-lookup"><span data-stu-id="af146-142">Adding a registry key</span></span>

  <span data-ttu-id="af146-143">Sie können den Legacy-JIT-Compiler von 64 aktivieren, indem `REG_DWORD` Sie dem `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` -oder `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` -Schlüssel in der Registrierung einen-Wert hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="af146-143">You can enable the legacy 64-bit JIT compiler by adding a `REG_DWORD` value to either the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` or `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` key in the registry.</span></span> <span data-ttu-id="af146-144">Der Wert hat den `useLegacyJit`Namen.</span><span class="sxs-lookup"><span data-stu-id="af146-144">The value is named `useLegacyJit`.</span></span> <span data-ttu-id="af146-145">Wenn der Wert 0 ist, wird der neue Compiler verwendet.</span><span class="sxs-lookup"><span data-stu-id="af146-145">If the value is 0, the new compiler is used.</span></span> <span data-ttu-id="af146-146">Wenn der Wert 1 ist, ist der ältere 64-Bit-JIT-Compiler aktiviert.</span><span class="sxs-lookup"><span data-stu-id="af146-146">If the value is 1, the legacy 64-bit JIT compiler is enabled.</span></span> <span data-ttu-id="af146-147">Beim Namen des Registrierungs Werts wird die Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="af146-147">The registry value name is not case-sensitive.</span></span>
  
  <span data-ttu-id="af146-148">Das Hinzufügen des Werts `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` zum Schlüssel betrifft alle apps, die auf dem Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="af146-148">Adding the value to the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` key affects all apps running on the machine.</span></span> <span data-ttu-id="af146-149">Das Hinzufügen des Werts `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` zum Schlüssel wirkt sich auf alle apps aus, die vom aktuellen Benutzer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="af146-149">Adding the value to the `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` key affects all apps run by the current user.</span></span> <span data-ttu-id="af146-150">Wenn ein Computer mit mehreren Benutzerkonten konfiguriert ist, wirkt sich dies nur auf apps aus, die vom aktuellen Benutzer ausgeführt werden, es sei denn, der Wert wird den Registrierungs Schlüsseln für andere Benutzer ebenfalls hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="af146-150">If a machine is configured with multiple user accounts, only apps run by the current user are affected, unless the value is added to the registry keys for other users as well.</span></span> <span data-ttu-id="af146-151">Das hinzu `<useLegacyJit>` fügen des-Elements zu einer Konfigurationsdatei überschreibt die Registrierungs Einstellungen, sofern diese vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="af146-151">Adding the `<useLegacyJit>` element to a configuration file overrides the registry settings, if they're present.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af146-152">Beispiel</span><span class="sxs-lookup"><span data-stu-id="af146-152">Example</span></span>  

<span data-ttu-id="af146-153">Die folgende Konfigurationsdatei deaktiviert die Kompilierung mit dem neuen 64-Bit-JIT-Compiler und verwendet stattdessen den älteren 64-Bit-JIT-Compiler.</span><span class="sxs-lookup"><span data-stu-id="af146-153">The following configuration file disables compilation with the new 64-bit JIT compiler and instead uses the legacy 64-bit JIT compiler.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
  <runtime>  
    <useLegacyJit enabled="1" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="af146-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af146-154">See also</span></span>

- [<span data-ttu-id="af146-155">\<Runtime-> Element</span><span class="sxs-lookup"><span data-stu-id="af146-155">\<runtime> Element</span></span>](runtime-element.md)
- [<span data-ttu-id="af146-156">\<configuration> Element</span><span class="sxs-lookup"><span data-stu-id="af146-156">\<configuration> Element</span></span>](../configuration-element.md)
- [<span data-ttu-id="af146-157">MIL Neuer 64-Bit-JIT-Compiler</span><span class="sxs-lookup"><span data-stu-id="af146-157">Mitigation: New 64-bit JIT Compiler</span></span>](../../../migration-guide/mitigation-new-64-bit-jit-compiler.md)
